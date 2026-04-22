# PHP 8.5 Moderno: Criando sua Própria API REST

**Capítulo 36: APIs — Do Conceito à Implementação Completa**

---

## Índice do Capítulo

1. [O que é uma API?](#361-o-que-é-uma-api)
2. [Como APIs Funcionam](#362-como-apis-funcionam)
3. [REST API — Conceitos](#363-rest-api--conceitos)
4. [Estrutura de Projeto](#364-estrutura-de-projeto)
5. [Roteamento](#365-roteamento)
6. [Controladores](#366-controladores)
7. [Respostas JSON Padronizadas](#367-respostas-json-padronizadas)
8. [Autenticação JWT](#368-autenticação-jwt)
9. [Middleware](#369-middleware)
10. [Validação de Requisições](#3610-validação-de-requisições)
11. [Rate Limiting](#3611-rate-limiting)
12. [Versionamento](#3612-versionamento)
13. [Documentação](#3613-documentação)
14. [API Completa — Projeto Final](#3614-api-completa--projeto-final)

---

## 36.1 O que é uma API?

```php
<?php

declare(strict_types=1);

/**
 * API (Application Programming Interface)
 *
 * Uma API é uma "ponte" que permite que diferentes sistemas
 * conversem entre si, sem que um precise saber como o outro funciona internamente.
 *
 * ══════════════════════════════════════
 * ANALOGIA DO RESTAURANTE
 * ══════════════════════════════════════
 *
 * Imagine um restaurante:
 *
 *   VOCÊ (Cliente)    = Aplicação Frontend (React, Vue, Mobile)
 *   GARÇOM            = API (recebe pedidos, entrega respostas)
 *   COZINHA           = Backend + Banco de Dados
 *   CARDÁPIO          = Documentação da API (endpoints disponíveis)
 *
 * Fluxo:
 *   1. Você consulta o CARDÁPIO (documentação)
 *   2. Faz o PEDIDO ao garçom (requisição HTTP)
 *   3. O garçom leva à COZINHA (servidor processa)
 *   4. A cozinha PREPARA (consulta banco, aplica regras)
 *   5. O garçom TRAZ o prato (resposta JSON)
 *   6. Você CONSOME (frontend exibe os dados)
 *
 * Você NUNCA entra na cozinha. Você não precisa saber:
 *   - Qual fogão é usado
 *   - Quem é o cozinheiro
 *   - De onde vêm os ingredientes
 *
 * ══════════════════════════════════════
 * EXEMPLO PRÁTICO: API de Clima
 * ══════════════════════════════════════
 *
 * Seu site faz:
 *   GET https://api.weather.com/current?city=SaoPaulo
 *
 * API retorna:
 *   { "temperature": 25, "city": "São Paulo", "condition": "sunny" }
 *
 * Seu site exibe:
 *   "☀️ 25°C em São Paulo"
 *
 * Você NÃO precisa ter estações meteorológicas!
 * Você SÓ precisa saber fazer uma requisição HTTP.
 */

// ── Exemplo: consumir API externa ──

function fetchWeather(string $city, string $apiKey): array
{
    $url = sprintf(
        'https://api.openweathermap.org/data/2.5/weather?q=%s&appid=%s&units=metric',
        urlencode($city),
        $apiKey,
    );

    $context = stream_context_create([
        'http' => [
            'method'  => 'GET',
            'header'  => 'Accept: application/json',
            'timeout' => 10,
        ],
    ]);

    $response = file_get_contents($url, false, $context);

    if ($response === false) {
        throw new RuntimeException("Falha ao conectar com a API de clima.");
    }

    return json_decode($response, true, 512, JSON_THROW_ON_ERROR);
}

// Uso
try {
    $weather = fetchWeather('Sao Paulo', 'SUA_API_KEY');
    echo "🌡️ Temperatura: {$weather['main']['temp']}°C" . PHP_EOL;
    echo "📍 Cidade: {$weather['name']}" . PHP_EOL;
} catch (Throwable $e) {
    echo "❌ Erro: {$e->getMessage()}" . PHP_EOL;
}
```

### Por que Criar sua Própria API?

```php
<?php

declare(strict_types=1);

/**
 * ══════════════════════════════════════
 * MOTIVOS PARA CRIAR UMA API
 * ══════════════════════════════════════
 *
 * 1. SEPARAÇÃO FRONTEND / BACKEND
 *    ┌──────────────┐     ┌──────────────┐
 *    │ React / Vue  │────▶│   PHP API    │
 *    │  (Frontend)  │◀────│  (Backend)   │
 *    └──────────────┘     └──────────────┘
 *    Times diferentes, deploy independente
 *
 * 2. MÚLTIPLOS CLIENTES — MESMA API
 *    ┌─ Site Web ─────┐
 *    ├─ App iOS ──────┤───▶ API PHP
 *    ├─ App Android ──┤
 *    └─ App Desktop ──┘
 *
 * 3. INTEGRAÇÃO COM TERCEIROS
 *    Permitir que outros devs consumam seus dados
 *    Ex: API do Twitter, Stripe, Google Maps
 *
 * 4. MICROSERVIÇOS
 *    ┌─ Auth Service ─────┐
 *    ├─ Payment Service ──┤  Cada um com sua API
 *    ├─ Email Service ────┤
 *    └─ Storage Service ──┘
 *
 * 5. REUTILIZAÇÃO
 *    Mesma lógica de negócio → múltiplas interfaces
 *    API é o "contrato" entre sistemas
 */
```

---

## 36.2 Como APIs Funcionam

```php
<?php

declare(strict_types=1);

/**
 * ══════════════════════════════════════
 * CICLO DE VIDA DE UMA REQUISIÇÃO API
 * ══════════════════════════════════════
 *
 *  CLIENTE                          SERVIDOR
 *  ───────                          ────────
 *  1. Monta requisição HTTP
 *     GET /api/v1/users/123
 *     Headers: Authorization: Bearer TOKEN
 *                    │
 *                    ▼
 *              2. Recebe requisição
 *                 → Middleware (auth, rate limit)
 *                 → Router (encontra controller)
 *                 → Valida dados
 *                    │
 *                    ▼
 *              3. Processa lógica de negócio
 *                 → SELECT * FROM users WHERE id = 123
 *                    │
 *                    ▼
 *              4. Monta resposta
 *                 Status: 200 OK
 *                 Content-Type: application/json
 *                 Body: { "id": 123, "name": "João" }
 *                    │
 *                    ▼
 *  5. Recebe e processa resposta
 *     → Exibe dados na tela
 */

// ══════════════════════════════════════
// MÉTODOS HTTP (Verbos)
// ══════════════════════════════════════

// Cada método tem uma semântica clara:
//
// GET     → Buscar dados (idempotente, sem efeitos colaterais)
//           GET /users/123 → retorna dados do usuário 123
//
// POST    → Criar novo recurso
//           POST /users → cria novo usuário com dados do body
//
// PUT     → Atualizar recurso COMPLETO (substitui tudo)
//           PUT /users/123 → substitui TODOS os campos
//
// PATCH   → Atualizar PARCIALMENTE
//           PATCH /users/123 → atualiza apenas campos enviados
//
// DELETE  → Remover recurso
//           DELETE /users/123 → remove o usuário 123
//
// OPTIONS → Verificar métodos permitidos (usado em CORS preflight)
//           OPTIONS /users → retorna métodos aceitos
//
// HEAD    → Igual ao GET mas sem body (apenas headers)
//           HEAD /users/123 → verifica se existe

// ══════════════════════════════════════
// STATUS CODES — Códigos de Resposta
// ══════════════════════════════════════

// ── 2xx: SUCESSO ──
const HTTP_OK                    = 200; // Sucesso geral
const HTTP_CREATED               = 201; // Recurso criado (POST)
const HTTP_ACCEPTED              = 202; // Aceito para processamento assíncrono
const HTTP_NO_CONTENT            = 204; // Sucesso sem body (DELETE)

// ── 3xx: REDIRECIONAMENTO ──
const HTTP_MOVED_PERMANENTLY     = 301; // URL mudou permanentemente
const HTTP_NOT_MODIFIED          = 304; // Usar versão em cache

// ── 4xx: ERRO DO CLIENTE ──
const HTTP_BAD_REQUEST           = 400; // Requisição malformada
const HTTP_UNAUTHORIZED          = 401; // Não autenticado (precisa de login)
const HTTP_FORBIDDEN             = 403; // Autenticado mas sem permissão
const HTTP_NOT_FOUND             = 404; // Recurso não existe
const HTTP_METHOD_NOT_ALLOWED    = 405; // Método HTTP não aceito na rota
const HTTP_CONFLICT              = 409; // Conflito (ex: email duplicado)
const HTTP_UNPROCESSABLE_ENTITY  = 422; // Validação de dados falhou
const HTTP_TOO_MANY_REQUESTS     = 429; // Rate limit excedido

// ── 5xx: ERRO DO SERVIDOR ──
const HTTP_INTERNAL_SERVER_ERROR = 500; // Erro genérico do servidor
const HTTP_BAD_GATEWAY           = 502; // Gateway/proxy recebeu resposta inválida
const HTTP_SERVICE_UNAVAILABLE   = 503; // Servidor temporariamente indisponível

// ══════════════════════════════════════
// HEADERS HTTP IMPORTANTES
// ══════════════════════════════════════

// Content-Type → Tipo do conteúdo enviado/recebido
//   application/json            → JSON (padrão em APIs)
//   application/x-www-form-urlencoded → Formulário
//   multipart/form-data         → Upload de arquivo

// Authorization → Credenciais de autenticação
//   Bearer <JWT_TOKEN>          → Token JWT (mais comum)
//   Basic <BASE64_CREDENTIALS>  → Basic Auth

// Accept → O que o cliente aceita receber
//   application/json            → Quero JSON
//   application/xml             → Quero XML

// Cache-Control → Controle de cache
//   no-cache                    → Não cachear
//   max-age=3600                → Válido por 1 hora

// X-Request-Id → Identificador único da requisição (rastreabilidade)
// X-RateLimit-Remaining → Requisições restantes no período

// ══════════════════════════════════════
// FORMATOS DE RESPOSTA JSON
// ══════════════════════════════════════

// ── Sucesso: recurso único ──
$singleResource = [
    'success' => true,
    'data'    => [
        'id'    => 123,
        'name'  => 'João Silva',
        'email' => 'joao@example.com',
    ],
];

// ── Sucesso: lista com paginação ──
$paginatedList = [
    'success' => true,
    'data'    => [
        ['id' => 1, 'name' => 'João'],
        ['id' => 2, 'name' => 'Maria'],
    ],
    'meta' => [
        'total'     => 100,
        'page'      => 1,
        'per_page'  => 10,
        'last_page' => 10,
    ],
];

// ── Erro: validação ──
$validationError = [
    'success' => false,
    'error'   => [
        'code'    => 'VALIDATION_ERROR',
        'message' => 'Os dados fornecidos são inválidos.',
        'details' => [
            'email' => ['O campo email é obrigatório.'],
            'name'  => ['O campo nome deve ter no mínimo 3 caracteres.'],
        ],
    ],
];

// ── Erro: não encontrado ──
$notFoundError = [
    'success' => false,
    'error'   => [
        'code'    => 'NOT_FOUND',
        'message' => 'Usuário não encontrado.',
    ],
];
```

---

## 36.3 REST API — Conceitos

```php
<?php

declare(strict_types=1);

/**
 * REST (Representational State Transfer)
 * ======================================
 *
 * REST é um estilo arquitetural para APIs baseado em:
 *   - HTTP methods para ações (GET, POST, PUT, DELETE)
 *   - URLs para identificar RECURSOS (substantivos)
 *   - JSON para representação de dados
 *   - Stateless: cada requisição é independente
 *
 * ══════════════════════════════════════
 * PRINCÍPIOS REST
 * ══════════════════════════════════════
 *
 * ┌─────────────────────────────────────────────────┐
 * │ REGRA 1: Recursos são SUBSTANTIVOS              │
 * ├─────────────────────────────────────────────────┤
 * │ ✅ GET /users            ❌ GET /getUsers        │
 * │ ✅ GET /products         ❌ GET /listProducts    │
 * │ ✅ POST /orders          ❌ POST /createOrder    │
 * │ ✅ DELETE /users/123     ❌ GET /deleteUser/123  │
 * └─────────────────────────────────────────────────┘
 *
 * ┌─────────────────────────────────────────────────┐
 * │ REGRA 2: Métodos HTTP definem a AÇÃO            │
 * ├─────────────────────────────────────────────────┤
 * │ GET    /users        → Listar todos             │
 * │ POST   /users        → Criar novo               │
 * │ GET    /users/123    → Buscar um (por ID)        │
 * │ PUT    /users/123    → Atualizar completo        │
 * │ PATCH  /users/123    → Atualizar parcial         │
 * │ DELETE /users/123    → Remover                   │
 * └─────────────────────────────────────────────────┘
 *
 * ┌─────────────────────────────────────────────────┐
 * │ REGRA 3: STATELESS (sem estado)                 │
 * ├─────────────────────────────────────────────────┤
 * │ Cada requisição contém TUDO que o servidor      │
 * │ precisa. Nada é armazenado entre requisições.   │
 * │ Use tokens JWT para autenticação.               │
 * └─────────────────────────────────────────────────┘
 *
 * ┌─────────────────────────────────────────────────┐
 * │ REGRA 4: URLs HIERÁRQUICAS                      │
 * ├─────────────────────────────────────────────────┤
 * │ GET /users/123/orders       → Pedidos do user   │
 * │ GET /users/123/orders/456   → Pedido específico  │
 * │ GET /categories/5/products  → Produtos da cat.   │
 * └─────────────────────────────────────────────────┘
 *
 * ┌─────────────────────────────────────────────────┐
 * │ REGRA 5: Filtros via QUERY PARAMETERS           │
 * ├─────────────────────────────────────────────────┤
 * │ GET /users?active=true                          │
 * │ GET /products?category=electronics&max_price=1000│
 * │ GET /orders?start_date=2026-01-01               │
 * └─────────────────────────────────────────────────┘
 *
 * ┌─────────────────────────────────────────────────┐
 * │ REGRA 6: Paginação e Ordenação                  │
 * ├─────────────────────────────────────────────────┤
 * │ GET /users?page=2&per_page=20                   │
 * │ GET /products?sort=price                        │
 * │ GET /products?sort=-price  (descendente com -)  │
 * └─────────────────────────────────────────────────┘
 *
 * ┌─────────────────────────────────────────────────┐
 * │ REGRA 7: Versionamento                          │
 * ├─────────────────────────────────────────────────┤
 * │ GET /api/v1/users                               │
 * │ GET /api/v2/users  (versão com breaking changes)│
 * └─────────────────────────────────────────────────┘
 */

// ══════════════════════════════════════
// MAPA COMPLETO DE ENDPOINTS REST
// ══════════════════════════════════════

// USUÁRIOS
// GET    /api/v1/users              → Listar todos (com paginação)
// GET    /api/v1/users/{id}         → Buscar um
// POST   /api/v1/users              → Criar
// PUT    /api/v1/users/{id}         → Atualizar completo
// PATCH  /api/v1/users/{id}         → Atualizar parcial
// DELETE /api/v1/users/{id}         → Remover

// PEDIDOS DO USUÁRIO (sub-recurso)
// GET    /api/v1/users/{id}/orders  → Pedidos do usuário
// POST   /api/v1/users/{id}/orders  → Criar pedido para o usuário

// PRODUTOS
// GET    /api/v1/products                               → Listar
// GET    /api/v1/products/{id}                           → Buscar
// GET    /api/v1/products?category=electronics&sort=-price → Filtrar

// AUTENTICAÇÃO
// POST   /api/v1/auth/login         → Login (retorna JWT)
// POST   /api/v1/auth/register      → Cadastro
// POST   /api/v1/auth/refresh       → Renovar token
// POST   /api/v1/auth/logout        → Invalidar token
// GET    /api/v1/auth/me            → Dados do usuário autenticado
```

---

## 36.4 Estrutura de Projeto

```php
<?php

declare(strict_types=1);

/**
 * ══════════════════════════════════════
 * ESTRUTURA DE DIRETÓRIOS
 * ══════════════════════════════════════
 *
 * api-rest/
 * ├── public/
 * │   ├── index.php                  # Entry point único (Front Controller)
 * │   └── .htaccess                  # Reescrita de URL (Apache)
 * ├── src/
 * │   ├── Config/
 * │   │   ├── Database.php           # Conexão PDO singleton
 * │   │   └── AppConfig.php          # Configurações da aplicação
 * │   ├── Controllers/
 * │   │   ├── AuthController.php     # Login, registro, JWT
 * │   │   ├── UserController.php     # CRUD de usuários
 * │   │   └── ProductController.php  # CRUD de produtos
 * │   ├── Models/
 * │   │   ├── User.php               # Entidade User (readonly DTO)
 * │   │   └── Product.php            # Entidade Product
 * │   ├── Repositories/
 * │   │   ├── UserRepository.php     # Queries de usuário (PDO)
 * │   │   └── ProductRepository.php  # Queries de produto
 * │   ├── Services/
 * │   │   ├── AuthService.php        # Lógica de autenticação
 * │   │   └── ValidationService.php  # Validação de dados
 * │   ├── Middleware/
 * │   │   ├── AuthMiddleware.php     # Verificação JWT
 * │   │   ├── CorsMiddleware.php     # Headers CORS
 * │   │   └── RateLimitMiddleware.php# Limite de requisições
 * │   ├── Http/
 * │   │   ├── Request.php            # Abstração da requisição
 * │   │   ├── Response.php           # Abstração da resposta
 * │   │   ├── JsonResponse.php       # Respostas JSON padronizadas
 * │   │   └── Router.php             # Sistema de rotas
 * │   └── Helpers/
 * │       └── JWT.php                # Encode/decode de tokens
 * ├── .env                           # Variáveis de ambiente
 * ├── .env.example                   # Template de .env
 * └── composer.json                  # Autoload PSR-4
 *
 * ══════════════════════════════════════
 * POR QUE ESSA ESTRUTURA?
 * ══════════════════════════════════════
 *
 * public/ → Único diretório acessível pela web (segurança!)
 * src/    → Código-fonte organizado por responsabilidade
 *
 * Controllers → Recebem requisição, delegam para services/repos
 * Models      → Representam entidades do domínio (DTOs imutáveis)
 * Repositories→ Comunicação com banco de dados (queries)
 * Services    → Lógica de negócio complexa
 * Middleware  → Processamento antes/depois do controller
 * Http        → Infraestrutura HTTP (request, response, router)
 */
```

### Configuração Apache (.htaccess)

```apache
# public/.htaccess
# Redirecionar todas as requisições para index.php (Front Controller)

RewriteEngine On

# Não redirecionar arquivos e diretórios existentes
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d

# Redirecionar tudo para index.php
RewriteRule ^(.*)$ index.php [QSA,L]

# Headers CORS globais
Header always set Access-Control-Allow-Origin "*"
Header always set Access-Control-Allow-Methods "GET, POST, PUT, PATCH, DELETE, OPTIONS"
Header always set Access-Control-Allow-Headers "Content-Type, Authorization, X-Requested-With"

# Responder OPTIONS imediatamente (preflight CORS)
RewriteCond %{REQUEST_METHOD} OPTIONS
RewriteRule ^(.*)$ $1 [R=200,L]
```

### Configuração Nginx

```nginx
# /etc/nginx/sites-available/api.conf

server {
    listen 80;
    server_name api.example.com;
    root /var/www/api-rest/public;

    index index.php;

    # Charset UTF-8
    charset utf-8;

    # Front Controller — tudo vai para index.php
    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    # Processar PHP via PHP-FPM 8.5
    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.5-fpm.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;

        # Timeout para APIs lentas
        fastcgi_read_timeout 30s;
    }

    # Bloquear acesso a arquivos ocultos (.env, .git)
    location ~ /\. {
        deny all;
        access_log off;
        log_not_found off;
    }
}
```

### Entry Point (index.php)

```php
<?php
// public/index.php — Front Controller

declare(strict_types=1);

// Autoload PSR-4
require_once __DIR__ . '/../vendor/autoload.php';

use App\Http\Request;
use App\Http\Router;
use App\Controllers\AuthController;
use App\Controllers\UserController;
use App\Controllers\ProductController;
use App\Middleware\CorsMiddleware;

// ── Tratamento global de erros ──
set_exception_handler(function (Throwable $e) {
    $statusCode = match (true) {
        $e instanceof \App\Exceptions\NotFoundException     => 404,
        $e instanceof \App\Exceptions\ValidationException   => 422,
        $e instanceof \App\Exceptions\UnauthorizedException => 401,
        $e instanceof \App\Exceptions\ForbiddenException    => 403,
        default                                             => 500,
    };

    http_response_code($statusCode);
    header('Content-Type: application/json; charset=utf-8');

    $response = [
        'success' => false,
        'error'   => [
            'code'    => $e->getCode() ?: 'SERVER_ERROR',
            'message' => $statusCode === 500
                ? 'Erro interno do servidor.'
                : $e->getMessage(),
        ],
    ];

    echo json_encode($response, JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES);
});

// ── CORS ──
CorsMiddleware::handle();

// ── Criar request e router ──
$request = new Request();
$router  = new Router();

// ══════════════════════════════════════
// Registro de Rotas
// ══════════════════════════════════════

// Autenticação (público)
$router->post('/api/v1/auth/login',    [AuthController::class, 'login']);
$router->post('/api/v1/auth/register', [AuthController::class, 'register']);
$router->post('/api/v1/auth/refresh',  [AuthController::class, 'refresh']);

// Usuários (autenticado)
$router->get('/api/v1/users',          [UserController::class, 'index']);
$router->get('/api/v1/users/{id}',     [UserController::class, 'show']);
$router->post('/api/v1/users',         [UserController::class, 'store']);
$router->put('/api/v1/users/{id}',     [UserController::class, 'update']);
$router->patch('/api/v1/users/{id}',   [UserController::class, 'patch']);
$router->delete('/api/v1/users/{id}',  [UserController::class, 'destroy']);

// Produtos (autenticado)
$router->get('/api/v1/products',         [ProductController::class, 'index']);
$router->get('/api/v1/products/{id}',    [ProductController::class, 'show']);
$router->post('/api/v1/products',        [ProductController::class, 'store']);
$router->put('/api/v1/products/{id}',    [ProductController::class, 'update']);
$router->delete('/api/v1/products/{id}', [ProductController::class, 'destroy']);

// ── Despachar ──
$response = $router->dispatch($request);
$response->send();
```

---

## 36.5 Roteamento

```php
<?php
// src/Http/Router.php

declare(strict_types=1);

namespace App\Http;

class Router
{
    private array $routes = [];

    // ── Registro de rotas por método HTTP ──

    public function get(string $path, callable|array $handler): self
    {
        return $this->addRoute('GET', $path, $handler);
    }

    public function post(string $path, callable|array $handler): self
    {
        return $this->addRoute('POST', $path, $handler);
    }

    public function put(string $path, callable|array $handler): self
    {
        return $this->addRoute('PUT', $path, $handler);
    }

    public function patch(string $path, callable|array $handler): self
    {
        return $this->addRoute('PATCH', $path, $handler);
    }

    public function delete(string $path, callable|array $handler): self
    {
        return $this->addRoute('DELETE', $path, $handler);
    }

    private function addRoute(string $method, string $path, callable|array $handler): self
    {
        // Converter parâmetros nomeados para regex:
        //   /users/{id}        → /users/(?P<id>[^/]+)
        //   /users/{id:\d+}    → /users/(?P<id>\d+)
        $pattern = preg_replace_callback(
            '/\{([a-zA-Z]+)(?::([^}]+))?\}/',
            fn(array $m): string => isset($m[2])
                ? "(?P<{$m[1]}>{$m[2]})"
                : "(?P<{$m[1]}>[^/]+)",
            $path,
        );

        $this->routes[] = [
            'method'  => $method,
            'path'    => $path,
            'pattern' => '#^' . $pattern . '$#',
            'handler' => $handler,
        ];

        return $this;
    }

    // ── Despacho da requisição ──

    public function dispatch(Request $request): Response
    {
        $method = $request->getMethod();
        $uri    = $request->getUri();

        // Preflight CORS — responder imediatamente
        if ($method === 'OPTIONS') {
            return Response::json(null, 204);
        }

        $methodMatched = false;

        foreach ($this->routes as $route) {
            if (!preg_match($route['pattern'], $uri, $matches)) {
                continue;
            }

            $methodMatched = true;

            if ($route['method'] !== $method) {
                continue;
            }

            // Extrair apenas parâmetros nomeados (ignorar índices numéricos)
            $params = array_filter($matches, 'is_string', ARRAY_FILTER_USE_KEY);

            $handler = $route['handler'];

            // Se handler é [Controller::class, 'method']
            if (is_array($handler)) {
                [$controllerClass, $action] = $handler;
                $controller = new $controllerClass();

                return $controller->$action($request, $params);
            }

            // Se handler é closure/callable
            return $handler($request, $params);
        }

        // Rota existe mas método errado → 405
        if ($methodMatched) {
            return JsonResponse::error(
                'METHOD_NOT_ALLOWED',
                "Método {$method} não permitido nesta rota.",
                status: 405,
            );
        }

        // Rota não encontrada → 404
        return JsonResponse::notFound('Rota');
    }
}
```

### Classe Request

```php
<?php
// src/Http/Request.php

declare(strict_types=1);

namespace App\Http;

class Request
{
    private readonly array $query;
    private readonly array $body;
    private readonly array $headers;
    private readonly string $method;
    private readonly string $uri;

    public function __construct()
    {
        $this->method  = $_SERVER['REQUEST_METHOD'];
        $this->uri     = parse_url($_SERVER['REQUEST_URI'], PHP_URL_PATH);
        $this->query   = $_GET;
        $this->headers = $this->parseHeaders();

        // Decodificar body JSON (POST, PUT, PATCH)
        $rawBody    = file_get_contents('php://input');
        $this->body = ($rawBody !== '' && $rawBody !== false)
            ? (json_decode($rawBody, true, 512, JSON_THROW_ON_ERROR) ?? [])
            : [];
    }

    private function parseHeaders(): array
    {
        $headers = [];

        foreach ($_SERVER as $key => $value) {
            if (str_starts_with($key, 'HTTP_')) {
                $header = strtolower(str_replace('_', '-', substr($key, 5)));
                $headers[$header] = $value;
            }
        }

        if (isset($_SERVER['CONTENT_TYPE'])) {
            $headers['content-type'] = $_SERVER['CONTENT_TYPE'];
        }

        return $headers;
    }

    public function getMethod(): string  { return $this->method; }
    public function getUri(): string     { return $this->uri; }

    public function query(string $key, mixed $default = null): mixed
    {
        return $this->query[$key] ?? $default;
    }

    public function input(string $key, mixed $default = null): mixed
    {
        return $this->body[$key] ?? $default;
    }

    public function all(): array
    {
        return $this->body;
    }

    public function only(string ...$keys): array
    {
        return array_intersect_key($this->body, array_flip($keys));
    }

    public function header(string $key, mixed $default = null): mixed
    {
        return $this->headers[strtolower($key)] ?? $default;
    }

    public function bearerToken(): ?string
    {
        $auth = $this->header('authorization', '');

        return str_starts_with($auth, 'Bearer ')
            ? substr($auth, 7)
            : null;
    }

    public function ip(): string
    {
        return $_SERVER['HTTP_X_FORWARDED_FOR']
            ?? $_SERVER['HTTP_X_REAL_IP']
            ?? $_SERVER['REMOTE_ADDR']
            ?? '0.0.0.0';
    }
}
```

### Classe Response

```php
<?php
// src/Http/Response.php

declare(strict_types=1);

namespace App\Http;

class Response
{
    private const JSON_FLAGS = JSON_UNESCAPED_UNICODE
                             | JSON_UNESCAPED_SLASHES
                             | JSON_THROW_ON_ERROR;

    public function __construct(
        private readonly mixed $data,
        private readonly int $status = 200,
        private readonly array $headers = [],
    ) {}

    public static function json(mixed $data, int $status = 200, array $headers = []): self
    {
        return new self($data, $status, $headers);
    }

    public function send(): never
    {
        http_response_code($this->status);
        header('Content-Type: application/json; charset=utf-8');

        foreach ($this->headers as $key => $value) {
            header("{$key}: {$value}");
        }

        // 204 No Content — sem body
        if ($this->status !== 204 && $this->data !== null) {
            echo json_encode($this->data, self::JSON_FLAGS);
        }

        exit;
    }
}
```

---

## 36.6 Controladores

```php
<?php
// src/Controllers/UserController.php

declare(strict_types=1);

namespace App\Controllers;

use App\Http\Request;
use App\Http\Response;
use App\Http\JsonResponse;
use App\Repositories\UserRepository;
use App\Services\ValidationService;

class UserController
{
    public function __construct(
        private readonly UserRepository $repository = new UserRepository(),
        private readonly ValidationService $validator = new ValidationService(),
    ) {}

    /**
     * GET /api/v1/users
     * Listar todos os usuários com paginação e filtros.
     */
    public function index(Request $request): Response
    {
        $page    = max(1, (int) $request->query('page', 1));
        $perPage = min(100, max(1, (int) $request->query('per_page', 10)));
        $search  = $request->query('search');

        $users = $this->repository->paginate($page, $perPage, $search);
        $total = $this->repository->count($search);

        return JsonResponse::success(
            data: $users,
            meta: [
                'total'     => $total,
                'page'      => $page,
                'per_page'  => $perPage,
                'last_page' => (int) ceil($total / $perPage),
            ],
        );
    }

    /**
     * GET /api/v1/users/{id}
     */
    public function show(Request $request, array $params): Response
    {
        $id   = (int) $params['id'];
        $user = $this->repository->find($id);

        if ($user === null) {
            return JsonResponse::notFound('Usuário');
        }

        return JsonResponse::success(data: $user);
    }

    /**
     * POST /api/v1/users
     */
    public function store(Request $request): Response
    {
        $errors = $this->validator->validate($request->all(), [
            'name'     => ['required', 'min:3', 'max:100'],
            'email'    => ['required', 'email', 'unique:users'],
            'password' => ['required', 'min:8'],
        ]);

        if ($errors !== []) {
            return JsonResponse::validationError($errors);
        }

        $userData = [
            'name'          => $request->input('name'),
            'email'         => $request->input('email'),
            'password_hash' => password_hash(
                $request->input('password'),
                PASSWORD_ARGON2ID,
                ['memory_cost' => 65536, 'time_cost' => 4, 'threads' => 3],
            ),
        ];

        $id   = $this->repository->create($userData);
        $user = $this->repository->find($id);

        return JsonResponse::created($user);
    }

    /**
     * PUT /api/v1/users/{id}
     */
    public function update(Request $request, array $params): Response
    {
        $id = (int) $params['id'];

        if (!$this->repository->exists($id)) {
            return JsonResponse::notFound('Usuário');
        }

        $errors = $this->validator->validate($request->all(), [
            'name'  => ['required', 'min:3', 'max:100'],
            'email' => ['required', 'email', "unique:users,id,{$id}"],
        ]);

        if ($errors !== []) {
            return JsonResponse::validationError($errors);
        }

        $this->repository->update($id, $request->only('name', 'email'));
        $user = $this->repository->find($id);

        return JsonResponse::success(data: $user, message: 'Usuário atualizado.');
    }

    /**
     * PATCH /api/v1/users/{id}
     */
    public function patch(Request $request, array $params): Response
    {
        $id = (int) $params['id'];

        if (!$this->repository->exists($id)) {
            return JsonResponse::notFound('Usuário');
        }

        // Validar apenas campos presentes no body
        $data  = $request->all();
        $rules = [];

        if (isset($data['name'])) {
            $rules['name'] = ['min:3', 'max:100'];
        }
        if (isset($data['email'])) {
            $rules['email'] = ['email', "unique:users,id,{$id}"];
        }

        $errors = $this->validator->validate($data, $rules);

        if ($errors !== []) {
            return JsonResponse::validationError($errors);
        }

        $allowed = array_intersect_key($data, array_flip(['name', 'email']));

        if ($allowed === []) {
            return JsonResponse::error('NO_DATA', 'Nenhum campo válido enviado.');
        }

        $this->repository->update($id, $allowed);
        $user = $this->repository->find($id);

        return JsonResponse::success(data: $user, message: 'Usuário atualizado.');
    }

    /**
     * DELETE /api/v1/users/{id}
     */
    public function destroy(Request $request, array $params): Response
    {
        $id = (int) $params['id'];

        if (!$this->repository->exists($id)) {
            return JsonResponse::notFound('Usuário');
        }

        $this->repository->delete($id);

        return Response::json(null, 204);
    }
}
```

---

## 36.7 Respostas JSON Padronizadas

```php
<?php
// src/Http/JsonResponse.php

declare(strict_types=1);

namespace App\Http;

/**
 * Factory de respostas JSON padronizadas para API REST.
 *
 * Sucesso: { "success": true,  "data": {...}, "message": "...", "meta": {...} }
 * Erro:    { "success": false, "error": { "code": "...", "message": "...", "details": {...} } }
 */
class JsonResponse
{
    // ── SUCESSO ──

    public static function success(
        mixed $data = null,
        ?string $message = null,
        ?array $meta = null,
        int $status = 200,
    ): Response {
        $response = ['success' => true];

        if ($data !== null)    { $response['data']    = $data; }
        if ($message !== null) { $response['message'] = $message; }
        if ($meta !== null)    { $response['meta']    = $meta; }

        return Response::json($response, $status);
    }

    public static function created(mixed $data, ?string $message = 'Recurso criado.'): Response
    {
        return self::success($data, $message, status: 201);
    }

    // ── ERROS ──

    public static function error(
        string $code,
        string $message,
        mixed $details = null,
        int $status = 400,
    ): Response {
        $error = ['code' => $code, 'message' => $message];

        if ($details !== null) {
            $error['details'] = $details;
        }

        return Response::json(['success' => false, 'error' => $error], $status);
    }

    public static function validationError(array $errors): Response
    {
        return self::error('VALIDATION_ERROR', 'Os dados fornecidos são inválidos.', $errors, 422);
    }

    public static function notFound(string $resource = 'Recurso'): Response
    {
        return self::error('NOT_FOUND', "{$resource} não encontrado.", status: 404);
    }

    public static function unauthorized(string $message = 'Token inválido ou expirado.'): Response
    {
        return self::error('UNAUTHORIZED', $message, status: 401);
    }

    public static function forbidden(string $message = 'Acesso negado.'): Response
    {
        return self::error('FORBIDDEN', $message, status: 403);
    }

    public static function conflict(string $message = 'Conflito de recursos.'): Response
    {
        return self::error('CONFLICT', $message, status: 409);
    }

    public static function tooManyRequests(int $retryAfter = 60): Response
    {
        return Response::json([
            'success' => false,
            'error'   => [
                'code'        => 'TOO_MANY_REQUESTS',
                'message'     => 'Limite de requisições excedido.',
                'retry_after' => $retryAfter,
            ],
        ], 429, ['Retry-After' => (string) $retryAfter]);
    }

    public static function serverError(string $message = 'Erro interno do servidor.'): Response
    {
        return self::error('INTERNAL_ERROR', $message, status: 500);
    }
}
```

---

## 36.8 Autenticação JWT

```php
<?php

declare(strict_types=1);

/**
 * JWT (JSON Web Token)
 * ====================
 *
 * Um JWT é um token compacto e seguro para transmitir informações entre partes.
 *
 * ESTRUTURA (3 partes separadas por ponto):
 * ─────────────────────────────────────────
 *
 *   HEADER.PAYLOAD.SIGNATURE
 *
 *   1. HEADER  → Algoritmo e tipo
 *      { "alg": "HS256", "typ": "JWT" }
 *
 *   2. PAYLOAD → Dados do usuário (claims)
 *      { "sub": 123, "email": "joao@test.com", "exp": 1700000000 }
 *
 *   3. SIGNATURE → Assinatura HMAC para garantir integridade
 *      HMAC_SHA256(base64(header) + "." + base64(payload), SECRET_KEY)
 *
 * FLUXO DE AUTENTICAÇÃO:
 * ──────────────────────
 *
 *   1. Cliente envia POST /auth/login com email + senha
 *   2. Servidor valida credenciais
 *   3. Servidor gera JWT e retorna ao cliente
 *   4. Cliente armazena JWT (localStorage, cookie, etc.)
 *   5. Em cada requisição: Authorization: Bearer <JWT>
 *   6. Servidor valida JWT antes de processar a requisição
 *
 * CLAIMS RESERVADAS:
 *   sub (subject)    → ID do usuário
 *   iat (issued at)  → Quando foi gerado
 *   exp (expiration) → Quando expira
 *   iss (issuer)     → Quem emitiu
 *   aud (audience)   → Para quem é destinado
 *   jti (JWT ID)     → Identificador único do token
 */
```

### Classe JWT (sem dependências externas)

```php
<?php
// src/Helpers/JWT.php

declare(strict_types=1);

namespace App\Helpers;

class JWT
{
    public function __construct(
        private readonly string $secretKey,
        private readonly string $algorithm = 'sha256',
    ) {}

    /**
     * Gerar um token JWT.
     *
     * @param array $payload Dados a serem incluídos (sub, email, role, etc.)
     * @param int   $ttl     Tempo de vida em segundos (padrão: 1 hora)
     */
    public function encode(array $payload, int $ttl = 3600): string
    {
        // Header
        $header = $this->base64Encode(json_encode([
            'alg' => 'HS256',
            'typ' => 'JWT',
        ], JSON_THROW_ON_ERROR));

        // Payload com claims automáticas
        $payload['iat'] = time();
        $payload['exp'] = time() + $ttl;
        $payload['jti'] = bin2hex(random_bytes(16));

        $payloadEncoded = $this->base64Encode(
            json_encode($payload, JSON_THROW_ON_ERROR),
        );

        // Signature
        $signature = $this->base64Encode(
            hash_hmac($this->algorithm, "{$header}.{$payloadEncoded}", $this->secretKey, true),
        );

        return "{$header}.{$payloadEncoded}.{$signature}";
    }

    /**
     * Decodificar e validar um token JWT.
     *
     * @return array Payload decodificado
     * @throws \RuntimeException Se o token for inválido ou expirado
     */
    public function decode(string $token): array
    {
        $parts = explode('.', $token);

        if (count($parts) !== 3) {
            throw new \RuntimeException('Token JWT malformado.');
        }

        [$header, $payload, $signature] = $parts;

        // Verificar assinatura (timing-safe comparison)
        $expectedSignature = $this->base64Encode(
            hash_hmac($this->algorithm, "{$header}.{$payload}", $this->secretKey, true),
        );

        if (!hash_equals($expectedSignature, $signature)) {
            throw new \RuntimeException('Assinatura JWT inválida.');
        }

        // Decodificar payload
        $data = json_decode(
            $this->base64Decode($payload),
            true,
            512,
            JSON_THROW_ON_ERROR,
        );

        // Verificar expiração
        if (isset($data['exp']) && $data['exp'] < time()) {
            throw new \RuntimeException('Token JWT expirado.');
        }

        return $data;
    }

    // ── Helpers de Base64 URL-safe ──

    private function base64Encode(string $data): string
    {
        return rtrim(strtr(base64_encode($data), '+/', '-_'), '=');
    }

    private function base64Decode(string $data): string
    {
        $remainder = strlen($data) % 4;

        if ($remainder) {
            $data .= str_repeat('=', 4 - $remainder);
        }

        return base64_decode(strtr($data, '-_', '+/'), true)
            ?: throw new \RuntimeException('Falha ao decodificar Base64.');
    }
}
```

### AuthController

```php
<?php
// src/Controllers/AuthController.php

declare(strict_types=1);

namespace App\Controllers;

use App\Http\{Request, Response, JsonResponse};
use App\Helpers\JWT;
use App\Repositories\UserRepository;

class AuthController
{
    private readonly JWT $jwt;

    public function __construct(
        private readonly UserRepository $repository = new UserRepository(),
    ) {
        // Em produção, use variável de ambiente!
        $this->jwt = new JWT($_ENV['JWT_SECRET'] ?? 'sua-chave-secreta-aqui');
    }

    /**
     * POST /api/v1/auth/login
     */
    public function login(Request $request): Response
    {
        $email    = $request->input('email', '');
        $password = $request->input('password', '');

        if ($email === '' || $password === '') {
            return JsonResponse::validationError([
                'email'    => $email === '' ? ['Campo obrigatório.'] : [],
                'password' => $password === '' ? ['Campo obrigatório.'] : [],
            ]);
        }

        // Buscar usuário pelo email
        $user = $this->repository->findByEmail($email);

        if ($user === null || !password_verify($password, $user['password_hash'])) {
            return JsonResponse::unauthorized('Credenciais inválidas.');
        }

        // Gerar tokens
        $accessToken  = $this->jwt->encode([
            'sub'   => $user['id'],
            'email' => $user['email'],
            'role'  => $user['role'] ?? 'user',
        ], ttl: 3600); // 1 hora

        $refreshToken = $this->jwt->encode([
            'sub'  => $user['id'],
            'type' => 'refresh',
        ], ttl: 86400 * 7); // 7 dias

        return JsonResponse::success([
            'access_token'  => $accessToken,
            'refresh_token' => $refreshToken,
            'token_type'    => 'Bearer',
            'expires_in'    => 3600,
            'user'          => [
                'id'    => $user['id'],
                'name'  => $user['name'],
                'email' => $user['email'],
            ],
        ], message: 'Login realizado com sucesso.');
    }

    /**
     * POST /api/v1/auth/register
     */
    public function register(Request $request): Response
    {
        // Validar... (omitido por brevidade — igual ao UserController::store)

        $userData = [
            'name'          => $request->input('name'),
            'email'         => $request->input('email'),
            'password_hash' => password_hash(
                $request->input('password'),
                PASSWORD_ARGON2ID,
            ),
        ];

        $id   = $this->repository->create($userData);
        $user = $this->repository->find($id);

        $token = $this->jwt->encode([
            'sub'   => $id,
            'email' => $user['email'],
        ]);

        return JsonResponse::success([
            'access_token' => $token,
            'token_type'   => 'Bearer',
            'expires_in'   => 3600,
            'user'         => $user,
        ], message: 'Conta criada com sucesso.', status: 201);
    }

    /**
     * POST /api/v1/auth/refresh
     */
    public function refresh(Request $request): Response
    {
        $refreshToken = $request->input('refresh_token', '');

        if ($refreshToken === '') {
            return JsonResponse::validationError([
                'refresh_token' => ['Campo obrigatório.'],
            ]);
        }

        try {
            $payload = $this->jwt->decode($refreshToken);

            if (($payload['type'] ?? '') !== 'refresh') {
                return JsonResponse::unauthorized('Token inválido — não é um refresh token.');
            }

            $user = $this->repository->find($payload['sub']);

            if ($user === null) {
                return JsonResponse::unauthorized('Usuário não encontrado.');
            }

            // Gerar novo access token
            $newAccessToken = $this->jwt->encode([
                'sub'   => $user['id'],
                'email' => $user['email'],
                'role'  => $user['role'] ?? 'user',
            ]);

            return JsonResponse::success([
                'access_token' => $newAccessToken,
                'token_type'   => 'Bearer',
                'expires_in'   => 3600,
            ]);
        } catch (\RuntimeException $e) {
            return JsonResponse::unauthorized($e->getMessage());
        }
    }
}
```

---

## 36.9 Middleware

```php
<?php

declare(strict_types=1);

/**
 * MIDDLEWARE — O que é?
 * =====================
 *
 * Middleware são "filtros" que processam a requisição ANTES de chegar
 * ao controller. Funcionam como camadas de uma cebola:
 *
 *   Requisição HTTP
 *       ↓
 *   ┌─ CorsMiddleware ─────────────┐
 *   │  ┌─ RateLimitMiddleware ───┐ │
 *   │  │  ┌─ AuthMiddleware ───┐ │ │
 *   │  │  │                    │ │ │
 *   │  │  │   CONTROLLER       │ │ │
 *   │  │  │                    │ │ │
 *   │  │  └────────────────────┘ │ │
 *   │  └─────────────────────────┘ │
 *   └──────────────────────────────┘
 *       ↓
 *   Resposta HTTP
 *
 * Cada middleware pode:
 *   - Continuar (passar para o próximo)
 *   - Bloquear (retornar erro, ex: 401 Unauthorized)
 *   - Modificar request/response (adicionar headers, logar)
 */
```

### CorsMiddleware

```php
<?php
// src/Middleware/CorsMiddleware.php

declare(strict_types=1);

namespace App\Middleware;

class CorsMiddleware
{
    /**
     * Configurar headers CORS para permitir requisições cross-origin.
     *
     * Em produção, substitua '*' pelo domínio do seu frontend!
     */
    public static function handle(): void
    {
        $allowedOrigin = $_ENV['CORS_ORIGIN'] ?? '*';

        header("Access-Control-Allow-Origin: {$allowedOrigin}");
        header('Access-Control-Allow-Methods: GET, POST, PUT, PATCH, DELETE, OPTIONS');
        header('Access-Control-Allow-Headers: Content-Type, Authorization, X-Requested-With');
        header('Access-Control-Max-Age: 86400'); // Cachear preflight por 24h

        // Preflight — responder imediatamente
        if ($_SERVER['REQUEST_METHOD'] === 'OPTIONS') {
            http_response_code(204);
            exit;
        }
    }
}
```

### AuthMiddleware

```php
<?php
// src/Middleware/AuthMiddleware.php

declare(strict_types=1);

namespace App\Middleware;

use App\Http\{Request, Response, JsonResponse};
use App\Helpers\JWT;

class AuthMiddleware
{
    private readonly JWT $jwt;

    public function __construct()
    {
        $this->jwt = new JWT($_ENV['JWT_SECRET'] ?? 'sua-chave-secreta-aqui');
    }

    /**
     * Verificar se a requisição possui um JWT válido.
     * Retorna Response em caso de erro, ou null para continuar.
     */
    public function handle(Request $request): ?Response
    {
        $token = $request->bearerToken();

        if ($token === null) {
            return JsonResponse::unauthorized('Token não fornecido. Envie: Authorization: Bearer <token>');
        }

        try {
            $payload = $this->jwt->decode($token);

            // Disponibilizar dados do usuário autenticado
            // Em um framework real, você injetaria isso na Request
            $GLOBALS['auth_user'] = [
                'id'    => $payload['sub'],
                'email' => $payload['email'] ?? '',
                'role'  => $payload['role'] ?? 'user',
            ];

            return null; // Continuar para o controller
        } catch (\RuntimeException $e) {
            return JsonResponse::unauthorized($e->getMessage());
        }
    }
}
```

### RateLimitMiddleware

```php
<?php
// src/Middleware/RateLimitMiddleware.php

declare(strict_types=1);

namespace App\Middleware;

use App\Http\{Request, Response, JsonResponse};

class RateLimitMiddleware
{
    /**
     * @param int    $maxRequests Máximo de requisições permitidas
     * @param int    $windowSeconds Janela de tempo em segundos
     * @param string $storagePath  Diretório para armazenar contadores
     */
    public function __construct(
        private readonly int $maxRequests = 60,
        private readonly int $windowSeconds = 60,
        private readonly string $storagePath = '/tmp/rate_limit',
    ) {
        if (!is_dir($this->storagePath)) {
            mkdir($this->storagePath, 0755, true);
        }
    }

    public function handle(Request $request): ?Response
    {
        $clientIp = $request->ip();
        $key      = md5($clientIp);
        $file     = "{$this->storagePath}/{$key}.json";

        // Carregar dados existentes
        $data = file_exists($file)
            ? json_decode(file_get_contents($file), true)
            : ['count' => 0, 'reset_at' => time() + $this->windowSeconds];

        // Resetar janela se expirou
        if (time() >= $data['reset_at']) {
            $data = ['count' => 0, 'reset_at' => time() + $this->windowSeconds];
        }

        $data['count']++;

        // Salvar contagem atualizada
        file_put_contents($file, json_encode($data), LOCK_EX);

        // Adicionar headers informativos
        $remaining = max(0, $this->maxRequests - $data['count']);
        header("X-RateLimit-Limit: {$this->maxRequests}");
        header("X-RateLimit-Remaining: {$remaining}");
        header("X-RateLimit-Reset: {$data['reset_at']}");

        // Bloquear se excedeu
        if ($data['count'] > $this->maxRequests) {
            $retryAfter = $data['reset_at'] - time();

            return JsonResponse::tooManyRequests($retryAfter);
        }

        return null; // Continuar
    }
}
```

---

## 36.10 Validação de Requisições

```php
<?php
// src/Services/ValidationService.php

declare(strict_types=1);

namespace App\Services;

class ValidationService
{
    /**
     * Validar dados contra um conjunto de regras.
     *
     * Regras suportadas:
     *   required     → Campo obrigatório
     *   email        → Formato de email válido
     *   min:N        → Mínimo de N caracteres
     *   max:N        → Máximo de N caracteres
     *   numeric      → Deve ser numérico
     *   integer      → Deve ser inteiro
     *   in:a,b,c     → Deve ser um dos valores listados
     *   url          → Formato de URL válida
     *   date         → Formato de data válida (Y-m-d)
     *   unique:table → Valor deve ser único na tabela (simplificado)
     *   confirmed    → Deve ter campo {field}_confirmation igual
     *
     * @param array<string, mixed>    $data  Dados a validar
     * @param array<string, string[]> $rules Regras por campo
     * @return array<string, string[]> Erros por campo (vazio se válido)
     */
    public function validate(array $data, array $rules): array
    {
        $errors = [];

        foreach ($rules as $field => $fieldRules) {
            $value = $data[$field] ?? null;

            foreach ($fieldRules as $rule) {
                $error = $this->applyRule($field, $value, $rule, $data);

                if ($error !== null) {
                    $errors[$field][] = $error;
                }
            }
        }

        return $errors;
    }

    private function applyRule(
        string $field,
        mixed $value,
        string $rule,
        array $allData,
    ): ?string {
        // Extrair parâmetro: "min:3" → rule="min", param="3"
        $param = null;
        if (str_contains($rule, ':')) {
            [$rule, $param] = explode(':', $rule, 2);
        }

        return match ($rule) {
            'required' => ($value === null || $value === '')
                ? "O campo {$field} é obrigatório."
                : null,

            'email' => ($value !== null && $value !== '' && !filter_var($value, FILTER_VALIDATE_EMAIL))
                ? "O campo {$field} deve ser um email válido."
                : null,

            'min' => ($value !== null && mb_strlen((string) $value) < (int) $param)
                ? "O campo {$field} deve ter no mínimo {$param} caracteres."
                : null,

            'max' => ($value !== null && mb_strlen((string) $value) > (int) $param)
                ? "O campo {$field} deve ter no máximo {$param} caracteres."
                : null,

            'numeric' => ($value !== null && $value !== '' && !is_numeric($value))
                ? "O campo {$field} deve ser numérico."
                : null,

            'integer' => ($value !== null && $value !== '' && !ctype_digit((string) $value))
                ? "O campo {$field} deve ser um número inteiro."
                : null,

            'in' => ($value !== null && !in_array($value, explode(',', $param ?? ''), true))
                ? "O campo {$field} deve ser um dos valores: {$param}."
                : null,

            'url' => ($value !== null && $value !== '' && !filter_var($value, FILTER_VALIDATE_URL))
                ? "O campo {$field} deve ser uma URL válida."
                : null,

            'date' => ($value !== null && $value !== '' && !$this->isValidDate($value))
                ? "O campo {$field} deve ser uma data válida (YYYY-MM-DD)."
                : null,

            'confirmed' => ($value !== ($allData["{$field}_confirmation"] ?? null))
                ? "A confirmação de {$field} não confere."
                : null,

            default => null, // Regra desconhecida — ignorar
        };
    }

    private function isValidDate(string $date): bool
    {
        $d = \DateTimeImmutable::createFromFormat('Y-m-d', $date);

        return $d !== false && $d->format('Y-m-d') === $date;
    }
}
```

### Uso da Validação no Controller

```php
<?php

declare(strict_types=1);

// Exemplo prático de validação em um ProductController

namespace App\Controllers;

use App\Http\{Request, Response, JsonResponse};
use App\Services\ValidationService;

class ProductController
{
    public function __construct(
        private readonly ValidationService $validator = new ValidationService(),
    ) {}

    /**
     * POST /api/v1/products
     */
    public function store(Request $request): Response
    {
        // Regras de validação detalhadas
        $errors = $this->validator->validate($request->all(), [
            'name'        => ['required', 'min:3', 'max:200'],
            'description' => ['max:1000'],
            'price'       => ['required', 'numeric'],
            'category'    => ['required', 'in:electronics,clothing,food,books'],
            'sku'         => ['required', 'min:3', 'max:50'],
            'stock'       => ['required', 'integer'],
        ]);

        if ($errors !== []) {
            return JsonResponse::validationError($errors);
        }

        // Processamento... (criar produto no banco)

        return JsonResponse::created([
            'id'       => 1,
            'name'     => $request->input('name'),
            'price'    => (float) $request->input('price'),
            'category' => $request->input('category'),
        ]);
    }
```

---

## 36.11 Rate Limiting

```php
<?php

declare(strict_types=1);

/**
 * RATE LIMITING — Proteção contra abuso
 * ======================================
 *
 * Rate limiting controla quantas requisições um cliente pode fazer
 * em um período de tempo. Essencial para:
 *
 *   1. PROTEÇÃO contra ataques de força bruta
 *   2. JUSTIÇA — impedir que um cliente monopolize recursos
 *   3. ESTABILIDADE — evitar sobrecarga do servidor
 *   4. CUSTOS — limitar uso de APIs pagas (OpenAI, AWS, etc.)
 *
 * ESTRATÉGIAS COMUNS:
 * ──────────────────
 *
 *   Fixed Window     → 60 req/min (reseta a cada minuto)
 *   Sliding Window   → 60 req nos últimos 60 segundos
 *   Token Bucket     → Tokens repostos gradualmente
 *   Leaky Bucket     → Processamento constante, fila de espera
 *
 * HEADERS DE RESPOSTA:
 * ───────────────────
 *
 *   X-RateLimit-Limit: 60          → Limite total do período
 *   X-RateLimit-Remaining: 45      → Requisições restantes
 *   X-RateLimit-Reset: 1700000060  → Timestamp de reset
 *   Retry-After: 30                → Segundos até poder tentar de novo
 *
 * LIMITES DIFERENCIADOS POR PLANO:
 * ────────────────────────────────
 *
 *   Free:       60 req/min    │  1.000 req/dia
 *   Pro:       300 req/min    │ 10.000 req/dia
 *   Enterprise: ilimitado     │       SLA 99.9%
 */
```

### Rate Limiter Avançado com Planos

```php
<?php
// src/Middleware/AdvancedRateLimiter.php

declare(strict_types=1);

namespace App\Middleware;

use App\Http\{Request, Response, JsonResponse};

enum RateLimitPlan: string
{
    case Free       = 'free';
    case Pro        = 'pro';
    case Enterprise = 'enterprise';

    /**
     * Limite de requisições por minuto para cada plano.
     */
    public function requestsPerMinute(): int
    {
        return match ($this) {
            self::Free       => 60,
            self::Pro        => 300,
            self::Enterprise => PHP_INT_MAX,
        };
    }

    /**
     * Limite diário de requisições.
     */
    public function requestsPerDay(): int
    {
        return match ($this) {
            self::Free       => 1_000,
            self::Pro        => 10_000,
            self::Enterprise => PHP_INT_MAX,
        };
    }
}

class AdvancedRateLimiter
{
    public function __construct(
        private readonly string $storagePath = '/tmp/rate_limit',
    ) {
        if (!is_dir($this->storagePath)) {
            mkdir($this->storagePath, 0755, true);
        }
    }

    public function handle(Request $request, RateLimitPlan $plan = RateLimitPlan::Free): ?Response
    {
        $identifier = $this->getIdentifier($request);
        $limit      = $plan->requestsPerMinute();

        // Enterprise — sem limite
        if ($plan === RateLimitPlan::Enterprise) {
            return null;
        }

        $data = $this->loadData($identifier);

        // Resetar se janela expirou
        if (time() >= $data['reset_at']) {
            $data = ['count' => 0, 'reset_at' => time() + 60];
        }

        $data['count']++;
        $this->saveData($identifier, $data);

        // Headers informativos
        $remaining = max(0, $limit - $data['count']);
        header("X-RateLimit-Limit: {$limit}");
        header("X-RateLimit-Remaining: {$remaining}");
        header("X-RateLimit-Reset: {$data['reset_at']}");
        header("X-RateLimit-Plan: {$plan->value}");

        if ($data['count'] > $limit) {
            $retryAfter = $data['reset_at'] - time();

            return JsonResponse::tooManyRequests($retryAfter);
        }

        return null;
    }

    /**
     * Identificar cliente por: API Key > Bearer Token > IP.
     */
    private function getIdentifier(Request $request): string
    {
        return md5(
            $request->header('x-api-key')
            ?? $request->bearerToken()
            ?? $request->ip(),
        );
    }

    private function loadData(string $key): array
    {
        $file = "{$this->storagePath}/{$key}.json";

        return file_exists($file)
            ? json_decode(file_get_contents($file), true)
            : ['count' => 0, 'reset_at' => time() + 60];
    }

    private function saveData(string $key, array $data): void
    {
        file_put_contents(
            "{$this->storagePath}/{$key}.json",
            json_encode($data),
            LOCK_EX,
        );
    }
}
```

---

## 36.12 Versionamento

```php
<?php

declare(strict_types=1);

/**
 * VERSIONAMENTO DE API
 * ====================
 *
 * Quando você muda o comportamento de um endpoint de forma que
 * QUEBRARIA clientes existentes, você precisa criar uma nova versão.
 *
 * ESTRATÉGIAS:
 * ───────────
 *
 * 1. VIA URL (mais comum, recomendada)
 *    GET /api/v1/users
 *    GET /api/v2/users
 *
 * 2. VIA HEADER
 *    Accept: application/vnd.myapi.v1+json
 *    Accept: application/vnd.myapi.v2+json
 *
 * 3. VIA QUERY PARAMETER
 *    GET /api/users?version=1
 *    GET /api/users?version=2
 *
 * QUANDO CRIAR NOVA VERSÃO:
 * ────────────────────────
 *
 *   ✅ Remover campo da resposta
 *   ✅ Renomear campo (name → full_name)
 *   ✅ Mudar tipo de dado (string → int)
 *   ✅ Mudar estrutura da resposta
 *
 *   ❌ Adicionar campo novo (backward compatible)
 *   ❌ Adicionar novo endpoint (não quebra nada)
 *   ❌ Melhorar performance (transparente)
 *
 * BOAS PRÁTICAS:
 * ─────────────
 *
 *   - Manter no MÁXIMO 2 versões ativas simultaneamente
 *   - Deprecar versão antiga com header: Sunset: Sat, 01 Jan 2027
 *   - Documentar diferenças entre versões
 *   - Avisar clientes com antecedência (mínimo 6 meses)
 */
```

### Router com Versionamento

```php
<?php
// Exemplo: versionamento via URL no Router

declare(strict_types=1);

namespace App\Http;

// No index.php, registre rotas para cada versão:

// ═══ V1 — Versão original ═══
$router->get('/api/v1/users',      [V1\UserController::class, 'index']);
$router->get('/api/v1/users/{id}', [V1\UserController::class, 'show']);

// ═══ V2 — Nova versão com breaking changes ═══
$router->get('/api/v2/users',      [V2\UserController::class, 'index']);
$router->get('/api/v2/users/{id}', [V2\UserController::class, 'show']);
```

### Controllers Versionados

```php
<?php
// src/Controllers/V1/UserController.php

declare(strict_types=1);

namespace App\Controllers\V1;

use App\Http\{Request, Response, JsonResponse};
use App\Repositories\UserRepository;

class UserController
{
    public function __construct(
        private readonly UserRepository $repository = new UserRepository(),
    ) {}

    /**
     * V1: retorna "name" como campo único.
     */
    public function show(Request $request, array $params): Response
    {
        $user = $this->repository->find((int) $params['id']);

        if ($user === null) {
            return JsonResponse::notFound('Usuário');
        }

        // V1 — formato original
        return JsonResponse::success([
            'id'    => $user['id'],
            'name'  => $user['name'],     // Campo único "name"
            'email' => $user['email'],
        ]);
    }
}
```

```php
<?php
// src/Controllers/V2/UserController.php

declare(strict_types=1);

namespace App\Controllers\V2;

use App\Http\{Request, Response, JsonResponse};
use App\Repositories\UserRepository;

class UserController
{
    public function __construct(
        private readonly UserRepository $repository = new UserRepository(),
    ) {}

    /**
     * V2: "name" dividido em "first_name" e "last_name" (breaking change!).
     * Adiciona "avatar_url" e timestamps.
     */
    public function show(Request $request, array $params): Response
    {
        $user = $this->repository->find((int) $params['id']);

        if ($user === null) {
            return JsonResponse::notFound('Usuário');
        }

        // V2 — novo formato (quebraria clientes da V1)
        [$firstName, $lastName] = explode(' ', $user['name'], 2) + [1 => ''];

        return JsonResponse::success([
            'id'         => $user['id'],
            'first_name' => $firstName,   // Breaking: era "name"
            'last_name'  => $lastName,    // Novo campo
            'email'      => $user['email'],
            'avatar_url' => "https://i.pravatar.cc/150?u={$user['id']}",
            'created_at' => $user['created_at'] ?? now(),
            'updated_at' => $user['updated_at'] ?? now(),
        ]);
    }
}
```

---

## 36.13 Documentação

```php
<?php

declare(strict_types=1);

/**
 * DOCUMENTAÇÃO DE API
 * ===================
 *
 * Uma API sem documentação é inútil. Boas práticas:
 *
 * 1. OPENAPI (Swagger) — Padrão da indústria
 *    - Formato YAML/JSON que descreve toda a API
 *    - Interface interativa para testar endpoints
 *    - Geração automática de SDKs
 *
 * 2. README claro com exemplos cURL
 *
 * 3. Coleção Postman/Insomnia exportável
 *
 * 4. Exemplos em múltiplas linguagens
 *
 * FERRAMENTAS:
 * ───────────
 *   - Swagger UI — interface visual interativa
 *   - Redoc      — documentação elegante
 *   - Postman    — testes e documentação
 *   - Insomnia   — alternativa ao Postman
 */
```

### Gerador de Documentação OpenAPI

```php
<?php
// src/Documentation/OpenApiGenerator.php

declare(strict_types=1);

namespace App\Documentation;

class OpenApiGenerator
{
    private array $spec;

    public function __construct(
        string $title = 'API REST PHP 8.5',
        string $version = '1.0.0',
        string $description = 'API REST completa construída com PHP 8.5 moderno.',
    ) {
        $this->spec = [
            'openapi' => '3.0.3',
            'info'    => [
                'title'       => $title,
                'version'     => $version,
                'description' => $description,
                'contact'     => ['email' => 'dev@example.com'],
                'license'     => ['name' => 'MIT'],
            ],
            'servers' => [
                ['url' => 'http://localhost:8080/api/v1', 'description' => 'Desenvolvimento'],
                ['url' => 'https://api.example.com/v1',   'description' => 'Produção'],
            ],
            'paths'      => [],
            'components' => [
                'securitySchemes' => [
                    'BearerAuth' => [
                        'type'         => 'http',
                        'scheme'       => 'bearer',
                        'bearerFormat' => 'JWT',
                    ],
                ],
                'schemas' => [],
            ],
        ];
    }

    /**
     * Adicionar endpoint à documentação.
     */
    public function addEndpoint(
        string $path,
        string $method,
        string $summary,
        string $tag,
        array $parameters = [],
        ?array $requestBody = null,
        array $responses = [],
        bool $requiresAuth = true,
    ): self {
        $operation = [
            'summary' => $summary,
            'tags'    => [$tag],
        ];

        if ($requiresAuth) {
            $operation['security'] = [['BearerAuth' => []]];
        }

        if ($parameters !== []) {
            $operation['parameters'] = $parameters;
        }

        if ($requestBody !== null) {
            $operation['requestBody'] = [
                'required' => true,
                'content'  => [
                    'application/json' => [
                        'schema' => $requestBody,
                    ],
                ],
            ];
        }

        if ($responses !== []) {
            $operation['responses'] = $responses;
        }

        $this->spec['paths'][$path][strtolower($method)] = $operation;

        return $this;
    }

    /**
     * Adicionar schema reutilizável.
     */
    public function addSchema(string $name, array $schema): self
    {
        $this->spec['components']['schemas'][$name] = $schema;

        return $this;
    }

    /**
     * Gerar especificação completa como JSON.
     */
    public function toJson(): string
    {
        return json_encode(
            $this->spec,
            JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES,
        );
    }
}
```

### Exemplo: Documentando a API de Usuários

```php
<?php
// scripts/generate-docs.php

declare(strict_types=1);

require_once __DIR__ . '/../vendor/autoload.php';

use App\Documentation\OpenApiGenerator;

$docs = new OpenApiGenerator();

// ── Schema: User ──
$docs->addSchema('User', [
    'type'       => 'object',
    'properties' => [
        'id'         => ['type' => 'integer', 'example' => 1],
        'name'       => ['type' => 'string',  'example' => 'João Silva'],
        'email'      => ['type' => 'string',  'format' => 'email', 'example' => 'joao@example.com'],
        'created_at' => ['type' => 'string',  'format' => 'date-time'],
    ],
]);

// ── Schema: Error ──
$docs->addSchema('Error', [
    'type'       => 'object',
    'properties' => [
        'success' => ['type' => 'boolean', 'example' => false],
        'error'   => [
            'type'       => 'object',
            'properties' => [
                'code'    => ['type' => 'string',  'example' => 'NOT_FOUND'],
                'message' => ['type' => 'string',  'example' => 'Recurso não encontrado.'],
            ],
        ],
    ],
]);

// ── Endpoint: Listar Usuários ──
$docs->addEndpoint(
    path: '/users',
    method: 'GET',
    summary: 'Listar todos os usuários (com paginação)',
    tag: 'Usuários',
    parameters: [
        ['name' => 'page',     'in' => 'query', 'schema' => ['type' => 'integer', 'default' => 1]],
        ['name' => 'per_page', 'in' => 'query', 'schema' => ['type' => 'integer', 'default' => 10]],
        ['name' => 'search',   'in' => 'query', 'schema' => ['type' => 'string']],
    ],
    responses: [
        '200' => [
            'description' => 'Lista de usuários',
            'content' => ['application/json' => [
                'schema' => [
                    'type'       => 'object',
                    'properties' => [
                        'success' => ['type' => 'boolean'],
                        'data'    => ['type' => 'array', 'items' => ['$ref' => '#/components/schemas/User']],
                        'meta'    => ['type' => 'object'],
                    ],
                ],
            ]],
        ],
    ],
);

// ── Endpoint: Criar Usuário ──
$docs->addEndpoint(
    path: '/users',
    method: 'POST',
    summary: 'Criar novo usuário',
    tag: 'Usuários',
    requestBody: [
        'type'       => 'object',
        'required'   => ['name', 'email', 'password'],
        'properties' => [
            'name'     => ['type' => 'string',  'minLength' => 3, 'example' => 'João Silva'],
            'email'    => ['type' => 'string',  'format' => 'email'],
            'password' => ['type' => 'string',  'minLength' => 8],
        ],
    ],
    responses: [
        '201' => ['description' => 'Usuário criado com sucesso'],
        '422' => ['description' => 'Erro de validação'],
    ],
);

// ── Endpoint: Login ──
$docs->addEndpoint(
    path: '/auth/login',
    method: 'POST',
    summary: 'Autenticar usuário e obter JWT',
    tag: 'Autenticação',
    requiresAuth: false,
    requestBody: [
        'type'       => 'object',
        'required'   => ['email', 'password'],
        'properties' => [
            'email'    => ['type' => 'string', 'format' => 'email'],
            'password' => ['type' => 'string'],
        ],
    ],
    responses: [
        '200' => ['description' => 'Token JWT retornado'],
        '401' => ['description' => 'Credenciais inválidas'],
    ],
);

// Salvar documentação
$json = $docs->toJson();
file_put_contents(__DIR__ . '/../public/openapi.json', $json);

echo "✅ Documentação OpenAPI gerada: public/openapi.json" . PHP_EOL;
echo "📖 Acesse via Swagger UI: https://petstore.swagger.io/?url=SUA_URL/openapi.json" . PHP_EOL;
```

---

## 36.14 API Completa — Projeto Final

Nesta seção, unimos **tudo** que foi ensinado em uma API funcional com banco de dados real.

### Configuração do Banco de Dados

```php
<?php
// src/Config/Database.php

declare(strict_types=1);

namespace App\Config;

class Database
{
    private static ?\PDO $instance = null;

    /**
     * Singleton para conexão PDO.
     */
    public static function getConnection(): \PDO
    {
        if (self::$instance === null) {
            $host = $_ENV['DB_HOST'] ?? 'localhost';
            $port = $_ENV['DB_PORT'] ?? '3306';
            $name = $_ENV['DB_NAME'] ?? 'api_rest';
            $user = $_ENV['DB_USER'] ?? 'root';
            $pass = $_ENV['DB_PASS'] ?? '';

            $dsn = "mysql:host={$host};port={$port};dbname={$name};charset=utf8mb4";

            self::$instance = new \PDO($dsn, $user, $pass, [
                \PDO::ATTR_ERRMODE            => \PDO::ERRMODE_EXCEPTION,
                \PDO::ATTR_DEFAULT_FETCH_MODE => \PDO::FETCH_ASSOC,
                \PDO::ATTR_EMULATE_PREPARES   => false,
                \PDO::ATTR_STRINGIFY_FETCHES   => false,
            ]);
        }

        return self::$instance;
    }
}
```

### SQL de Criação das Tabelas

```sql
-- migrations/001_create_users.sql

CREATE TABLE IF NOT EXISTS users (
    id            INT AUTO_INCREMENT PRIMARY KEY,
    name          VARCHAR(100)  NOT NULL,
    email         VARCHAR(255)  NOT NULL UNIQUE,
    password_hash VARCHAR(255)  NOT NULL,
    role          ENUM('user', 'admin') DEFAULT 'user',
    active        BOOLEAN       DEFAULT TRUE,
    created_at    TIMESTAMP     DEFAULT CURRENT_TIMESTAMP,
    updated_at    TIMESTAMP     DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,

    INDEX idx_email  (email),
    INDEX idx_active (active)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- migrations/002_create_products.sql

CREATE TABLE IF NOT EXISTS products (
    id          INT AUTO_INCREMENT PRIMARY KEY,
    name        VARCHAR(200)   NOT NULL,
    description TEXT,
    price       DECIMAL(10, 2) NOT NULL,
    stock       INT            NOT NULL DEFAULT 0,
    category    VARCHAR(50)    NOT NULL,
    sku         VARCHAR(50)    NOT NULL UNIQUE,
    active      BOOLEAN        DEFAULT TRUE,
    created_at  TIMESTAMP      DEFAULT CURRENT_TIMESTAMP,
    updated_at  TIMESTAMP      DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,

    INDEX idx_category (category),
    INDEX idx_sku      (sku)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

### UserRepository Completo

```php
<?php
// src/Repositories/UserRepository.php

declare(strict_types=1);

namespace App\Repositories;

use App\Config\Database;

class UserRepository
{
    private readonly \PDO $db;

    public function __construct()
    {
        $this->db = Database::getConnection();
    }

    /**
     * Buscar usuário por ID.
     */
    public function find(int $id): ?array
    {
        $stmt = $this->db->prepare(
            'SELECT id, name, email, role, active, created_at, updated_at
             FROM users WHERE id = :id',
        );
        $stmt->execute(['id' => $id]);

        return $stmt->fetch() ?: null;
    }

    /**
     * Buscar usuário por email (inclui password_hash para autenticação).
     */
    public function findByEmail(string $email): ?array
    {
        $stmt = $this->db->prepare(
            'SELECT id, name, email, password_hash, role, active
             FROM users WHERE email = :email AND active = 1',
        );
        $stmt->execute(['email' => $email]);

        return $stmt->fetch() ?: null;
    }

    /**
     * Verificar se usuário existe.
     */
    public function exists(int $id): bool
    {
        $stmt = $this->db->prepare('SELECT 1 FROM users WHERE id = :id');
        $stmt->execute(['id' => $id]);

        return $stmt->fetchColumn() !== false;
    }

    /**
     * Listar com paginação e busca.
     */
    public function paginate(
        int $page,
        int $perPage,
        ?string $search = null,
    ): array {
        $offset = ($page - 1) * $perPage;

        $sql = 'SELECT id, name, email, role, active, created_at
                FROM users WHERE active = 1';
        $params = [];

        if ($search !== null && $search !== '') {
            $sql .= ' AND (name LIKE :search OR email LIKE :search)';
            $params['search'] = "%{$search}%";
        }

        $sql .= ' ORDER BY id DESC LIMIT :limit OFFSET :offset';

        $stmt = $this->db->prepare($sql);

        foreach ($params as $key => $value) {
            $stmt->bindValue($key, $value);
        }
        $stmt->bindValue('limit', $perPage, \PDO::PARAM_INT);
        $stmt->bindValue('offset', $offset, \PDO::PARAM_INT);

        $stmt->execute();

        return $stmt->fetchAll();
    }

    /**
     * Contar total de registros.
     */
    public function count(?string $search = null): int
    {
        $sql = 'SELECT COUNT(*) FROM users WHERE active = 1';
        $params = [];

        if ($search !== null && $search !== '') {
            $sql .= ' AND (name LIKE :search OR email LIKE :search)';
            $params['search'] = "%{$search}%";
        }

        $stmt = $this->db->prepare($sql);
        $stmt->execute($params);

        return (int) $stmt->fetchColumn();
    }

    /**
     * Criar novo usuário.
     */
    public function create(array $data): int
    {
        $stmt = $this->db->prepare(
            'INSERT INTO users (name, email, password_hash)
             VALUES (:name, :email, :password_hash)',
        );

        $stmt->execute([
            'name'          => $data['name'],
            'email'         => $data['email'],
            'password_hash' => $data['password_hash'],
        ]);

        return (int) $this->db->lastInsertId();
    }

    /**
     * Atualizar usuário (campos dinâmicos).
     */
    public function update(int $id, array $data): bool
    {
        if ($data === []) {
            return false;
        }

        $fields = [];
        $params = ['id' => $id];

        foreach ($data as $key => $value) {
            $fields[] = "{$key} = :{$key}";
            $params[$key] = $value;
        }

        $sql = 'UPDATE users SET ' . implode(', ', $fields) . ' WHERE id = :id';

        $stmt = $this->db->prepare($sql);

        return $stmt->execute($params);
    }

    /**
     * Soft delete (desativar usuário).
     */
    public function delete(int $id): bool
    {
        $stmt = $this->db->prepare(
            'UPDATE users SET active = 0 WHERE id = :id',
        );

        return $stmt->execute(['id' => $id]);
    }
}
```

### Testando a API com cURL

```bash
# ══════════════════════════════════════
# TESTANDO A API COM cURL
# ══════════════════════════════════════

# Variável base
BASE_URL="http://localhost:8080/api/v1"

# ── 1. Registrar novo usuário ──
curl -s -X POST "$BASE_URL/auth/register" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "João Silva",
    "email": "joao@example.com",
    "password": "senha_segura_123"
  }' | jq .

# ── 2. Login (obter JWT) ──
TOKEN=$(curl -s -X POST "$BASE_URL/auth/login" \
  -H "Content-Type: application/json" \
  -d '{
    "email": "joao@example.com",
    "password": "senha_segura_123"
  }' | jq -r '.data.access_token')

echo "Token: $TOKEN"

# ── 3. Listar usuários (com paginação) ──
curl -s -X GET "$BASE_URL/users?page=1&per_page=5" \
  -H "Authorization: Bearer $TOKEN" | jq .

# ── 4. Buscar usuário específico ──
curl -s -X GET "$BASE_URL/users/1" \
  -H "Authorization: Bearer $TOKEN" | jq .

# ── 5. Criar novo usuário ──
curl -s -X POST "$BASE_URL/users" \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Maria Santos",
    "email": "maria@example.com",
    "password": "outra_senha_456"
  }' | jq .

# ── 6. Atualizar parcialmente (PATCH) ──
curl -s -X PATCH "$BASE_URL/users/2" \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"name": "Maria S. Oliveira"}' | jq .

# ── 7. Deletar usuário ──
curl -s -X DELETE "$BASE_URL/users/2" \
  -H "Authorization: Bearer $TOKEN" -w "\nHTTP Status: %{http_code}\n"

# ── 8. Testar erro de validação ──
curl -s -X POST "$BASE_URL/users" \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"name": "AB", "email": "invalido"}' | jq .

# ── 9. Testar sem autenticação (401) ──
curl -s -X GET "$BASE_URL/users" | jq .

# ── 10. Testar rota inexistente (404) ──
curl -s -X GET "$BASE_URL/nao_existe" | jq .
```

---

## Exercícios

```php
<?php

declare(strict_types=1);

/**
 * ══════════════════════════════════════════════════════════
 * EXERCÍCIOS — APIs REST com PHP 8.5
 * ══════════════════════════════════════════════════════════
 *
 * BÁSICO:
 * ───────
 *
 * 1. Crie um endpoint GET /api/v1/health que retorne:
 *    { "status": "ok", "timestamp": "2026-...", "version": "1.0.0" }
 *    Dica: use DateTimeImmutable e JsonResponse::success().
 *
 * 2. Implemente o ProductController completo com CRUD.
 *    Inclua validação de preço (numeric, > 0) e SKU (unique).
 *
 * 3. Adicione busca com filtros: GET /api/v1/products?category=books&min_price=10
 *    Implemente os filtros no ProductRepository.
 *
 * INTERMEDIÁRIO:
 * ──────────────
 *
 * 4. Implemente o endpoint PATCH /api/v1/users/{id}/role
 *    que permite APENAS admins alterarem o role de outros usuários.
 *    Dica: use o AuthMiddleware + verificação de $GLOBALS['auth_user']['role'].
 *
 * 5. Crie um RateLimitMiddleware diferenciado por endpoint:
 *    POST /auth/login → 5 req/min (proteção contra brute force)
 *    GET  /users      → 60 req/min (leitura normal)
 *    POST /users      → 10 req/min (criação)
 *
 * 6. Implemente cache de respostas GET usando arquivo:
 *    - Se cache existe e tem < 60s, retorne do cache.
 *    - Se cache expirou, processe normalmente e salve.
 *    - Adicione header X-Cache: HIT ou X-Cache: MISS.
 *
 * AVANÇADO:
 * ─────────
 *
 * 7. Implemente um sistema de API Keys:
 *    - Tabela api_keys com: key, user_id, plan, active, created_at
 *    - Middleware que valida X-API-Key header
 *    - Rate limit baseado no plano da API Key
 *
 * 8. Crie um endpoint POST /api/v1/upload que aceite imagens:
 *    - Valide tipo (jpeg, png, webp), tamanho (máx 5MB)
 *    - Salve com nome único (UUID)
 *    - Retorne URL do arquivo
 *    Dica: use $_FILES e move_uploaded_file().
 *
 * 9. Implemente paginação baseada em cursor (cursor-based pagination):
 *    GET /api/v1/products?cursor=eyJpZCI6MX0=&limit=10
 *    Retorne: { "data": [...], "meta": { "next_cursor": "...", "has_more": true } }
 *    Dica: o cursor é o ID base64-encoded do último item.
 *
 * 10. Crie um sistema de webhooks:
 *     - Endpoint POST /api/v1/webhooks para registrar URLs de callback
 *     - Ao criar/atualizar/deletar um recurso, envie notificação
 *     - Inclua retry com backoff exponencial (1s, 2s, 4s, 8s)
 *     Dica: use curl_multi para enviar webhooks de forma assíncrona.
 */
```

---

## Regras de Ouro para APIs REST

```php
<?php

declare(strict_types=1);

/**
 * ╔═══════════════════════════════════════════════════════════╗
 * ║          REGRAS DE OURO PARA APIs REST EM PHP            ║
 * ╠═══════════════════════════════════════════════════════════╣
 * ║                                                           ║
 * ║  1. SEMPRE use declare(strict_types=1)                    ║
 * ║                                                           ║
 * ║  2. SEMPRE valide TODOS os dados de entrada               ║
 * ║     → Nunca confie em dados do cliente                    ║
 * ║                                                           ║
 * ║  3. SEMPRE use prepared statements (PDO)                  ║
 * ║     → SQL Injection é inadmissível em 2026                ║
 * ║                                                           ║
 * ║  4. SEMPRE hash senhas com PASSWORD_ARGON2ID              ║
 * ║     → Nunca MD5, SHA1 ou texto puro                       ║
 * ║                                                           ║
 * ║  5. SEMPRE retorne JSON padronizado                       ║
 * ║     → { success, data/error, meta }                       ║
 * ║                                                           ║
 * ║  6. SEMPRE use status codes HTTP corretos                 ║
 * ║     → 201 para criação, 204 para delete, 422 para validação║
 * ║                                                           ║
 * ║  7. SEMPRE implemente autenticação (JWT/OAuth)            ║
 * ║     → APIs públicas são raras e perigosas                 ║
 * ║                                                           ║
 * ║  8. SEMPRE implemente rate limiting                       ║
 * ║     → Sem limite = convite para DDOS                      ║
 * ║                                                           ║
 * ║  9. NUNCA exponha detalhes internos em erros              ║
 * ║     → Em produção: "Erro interno" (sem stack trace)       ║
 * ║                                                           ║
 * ║ 10. NUNCA armazene tokens JWT no servidor                 ║
 * ║     → JWT é stateless por design                          ║
 * ║                                                           ║
 * ║ 11. SEMPRE documente sua API (OpenAPI/Swagger)            ║
 * ║     → API sem docs é API morta                            ║
 * ║                                                           ║
 * ║ 12. SEMPRE versione sua API                               ║
 * ║     → Breaking changes precisam de nova versão            ║
 * ║                                                           ║
 * ║ 13. SEMPRE use HTTPS em produção                          ║
 * ║     → HTTP é interceptável e inseguro                     ║
 * ║                                                           ║
 * ║ 14. SEMPRE implemente CORS corretamente                   ║
 * ║     → Em produção: domínio específico, não "*"            ║
 * ║                                                           ║
 * ║ 15. SEMPRE logue requisições para debugging               ║
 * ║     → request_id, IP, método, rota, status, tempo         ║
 * ║                                                           ║
 * ╚═══════════════════════════════════════════════════════════╝
 */
```

---

# PHP 8.5 Moderno: Criando sua Própria API REST — Parte 2

**Continuação do Capítulo 36**

> Nesta segunda parte, implementamos os componentes avançados que transformam uma
> API básica em uma aplicação profissional: autenticação JWT, middlewares,
> validação, rate limiting, versionamento, documentação e um projeto final
> completo integrando todos os conceitos.

---

## 36.8 Autenticação JWT

JWT (JSON Web Token) é o padrão de autenticação **stateless** para APIs REST. O servidor não armazena sessões — todas as informações necessárias estão codificadas no próprio token, assinado com uma chave secreta.

### Estrutura de um JWT

Um token JWT é composto por três partes separadas por pontos:

```text
HEADER.PAYLOAD.SIGNATURE

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.    ← Header (algoritmo + tipo)
eyJ1c2VyX2lkIjoxLCJlbWFpbCI6ImpvYW9AZX... ← Payload (dados do usuário)
SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQ... ← Signature (assinatura HMAC)
```

### Classe JWT Helper

```php
<?php
// src/Helpers/JWT.php

declare(strict_types=1);

namespace App\Helpers;

/**
 * Helper para criação e validação de tokens JWT (JSON Web Token).
 *
 * Implementa o padrão RFC 7519 com assinatura HMAC-SHA256.
 * Para produção, considere usar a biblioteca firebase/php-jwt.
 *
 * @see https://datatracker.ietf.org/doc/html/rfc7519
 */
final class JWT
{
    /** Algoritmo de assinatura — HMAC com SHA-256 */
    private const string ALGORITHM = 'HS256';

    /** Tempo padrão de expiração: 1 hora */
    private const int DEFAULT_EXPIRATION = 3_600;

    public function __construct(
        private readonly string $secretKey,
    ) {
        if (strlen($this->secretKey) < 32) {
            throw new \InvalidArgumentException(
                'Chave secreta JWT deve ter no mínimo 32 caracteres.',
            );
        }
    }

    /**
     * Cria um token JWT assinado.
     *
     * @param array<string, mixed> $payload Dados a incluir no token
     * @param int $expiresIn Tempo de expiração em segundos
     * @return string Token JWT completo (header.payload.signature)
     */
    #[\NoDiscard('O token gerado deve ser retornado ao cliente.')]
    public function encode(array $payload, int $expiresIn = self::DEFAULT_EXPIRATION): string
    {
        // Header do token — identifica algoritmo e tipo
        $header = [
            'typ' => 'JWT',
            'alg' => self::ALGORITHM,
        ];

        // Claims padrão (registrados no RFC 7519)
        $payload['iat'] = time();                   // Issued At — quando foi criado
        $payload['exp'] = time() + $expiresIn;      // Expiration — quando expira
        $payload['jti'] = bin2hex(random_bytes(16)); // JWT ID — identificador único

        // Codificar header e payload em Base64URL
        $headerEncoded  = $this->base64UrlEncode(
            json_encode($header, JSON_THROW_ON_ERROR),
        );
        $payloadEncoded = $this->base64UrlEncode(
            json_encode($payload, JSON_THROW_ON_ERROR),
        );

        // Criar assinatura HMAC-SHA256
        $signature = hash_hmac(
            'sha256',
            "{$headerEncoded}.{$payloadEncoded}",
            $this->secretKey,
            binary: true,
        );

        $signatureEncoded = $this->base64UrlEncode($signature);

        // Token final: header.payload.signature
        return "{$headerEncoded}.{$payloadEncoded}.{$signatureEncoded}";
    }

    /**
     * Decodifica e valida um token JWT.
     *
     * Verifica a assinatura (timing-safe) e a expiração.
     *
     * @param string $token Token JWT completo
     * @return array<string, mixed>|null Payload decodificado ou null se inválido
     */
    public function decode(string $token): ?array
    {
        // JWT deve conter exatamente 3 partes
        $parts = explode('.', $token);

        if (count($parts) !== 3) {
            return null;
        }

        [$headerEncoded, $payloadEncoded, $signatureEncoded] = $parts;

        // Recalcular assinatura para validação
        $expectedSignature = hash_hmac(
            'sha256',
            "{$headerEncoded}.{$payloadEncoded}",
            $this->secretKey,
            binary: true,
        );

        $expectedEncoded = $this->base64UrlEncode($expectedSignature);

        // ⚠️ SEGURANÇA: Comparação timing-safe para evitar timing attacks
        if (!hash_equals($expectedEncoded, $signatureEncoded)) {
            return null; // Assinatura inválida — token foi adulterado
        }

        // Decodificar payload
        $payload = json_decode(
            $this->base64UrlDecode($payloadEncoded),
            associative: true,
            flags: JSON_THROW_ON_ERROR,
        );

        // Verificar expiração
        if (isset($payload['exp']) && $payload['exp'] < time()) {
            return null; // Token expirado
        }

        return $payload;
    }

    /**
     * Codifica dados em Base64URL (RFC 4648 §5).
     * Diferente de base64 padrão: usa - e _ ao invés de + e /, sem padding =
     */
    private function base64UrlEncode(string $data): string
    {
        return rtrim(strtr(base64_encode($data), '+/', '-_'), '=');
    }

    /**
     * Decodifica dados de Base64URL para string original.
     */
    private function base64UrlDecode(string $data): string
    {
        return base64_decode(strtr($data, '-_', '+/'));
    }
}
```

### Controller de Autenticação

```php
<?php
// src/Controllers/AuthController.php

declare(strict_types=1);

namespace App\Controllers;

use App\Http\Request;
use App\Http\Response;
use App\Http\JsonResponse;
use App\Repositories\UserRepository;
use App\Helpers\JWT;

/**
 * Controller de autenticação.
 *
 * Gerencia registro, login e perfil do usuário autenticado.
 * Utiliza JWT para autenticação stateless.
 */
final class AuthController
{
    public function __construct(
        private readonly UserRepository $repository = new UserRepository(),
        private readonly JWT $jwt = new JWT(
            $_ENV['JWT_SECRET'] ?? throw new \RuntimeException(
                'JWT_SECRET não configurado. Defina no arquivo .env.',
            ),
        ),
    ) {}

    /**
     * POST /api/v1/auth/register
     * Registra um novo usuário e retorna token de acesso.
     */
    public function register(Request $request): Response
    {
        $name     = $request->input('name');
        $email    = $request->input('email');
        $password = $request->input('password');

        // Validação dos campos obrigatórios
        $errors = [];

        if (empty($name)) {
            $errors['name'] = 'O campo nome é obrigatório.';
        }

        if (empty($email) || !filter_var($email, FILTER_VALIDATE_EMAIL)) {
            $errors['email'] = 'Informe um email válido.';
        }

        if (empty($password) || strlen($password) < 8) {
            $errors['password'] = 'A senha deve ter no mínimo 8 caracteres.';
        }

        if (!empty($errors)) {
            return JsonResponse::validationError($errors);
        }

        // Verificar se email já está cadastrado
        if ($this->repository->findByEmail($email)) {
            return JsonResponse::conflict('Este email já está em uso.');
        }

        // Criar usuário com senha hash segura
        $userId = $this->repository->create([
            'name'          => $name,
            'email'         => $email,
            'password_hash' => password_hash($password, PASSWORD_ARGON2ID, [
                'memory_cost' => 65_536,
                'time_cost'   => 4,
                'threads'     => 3,
            ]),
        ]);

        $user = $this->repository->find($userId);

        // Gerar token JWT (expira em 24 horas)
        $token = $this->jwt->encode(
            payload:   ['user_id' => $user['id'], 'email' => $user['email']],
            expiresIn: 86_400,
        );

        return JsonResponse::success(
            data:    [
                'user'  => [
                    'id'    => $user['id'],
                    'name'  => $user['name'],
                    'email' => $user['email'],
                ],
                'token' => $token,
            ],
            message: 'Usuário registrado com sucesso.',
            status:  201,
        );
    }

    /**
     * POST /api/v1/auth/login
     * Autentica um usuário e retorna token JWT.
     */
    public function login(Request $request): Response
    {
        $email    = $request->input('email');
        $password = $request->input('password');

        if (empty($email) || empty($password)) {
            return JsonResponse::validationError([
                'email'    => 'O campo email é obrigatório.',
                'password' => 'O campo senha é obrigatório.',
            ]);
        }

        // Buscar usuário pelo email
        $user = $this->repository->findByEmail($email);

        // ⚠️ SEGURANÇA: mensagem genérica para não revelar se email existe
        if (!$user || !password_verify($password, $user['password_hash'])) {
            return JsonResponse::unauthorized('Credenciais inválidas.');
        }

        // Gerar token JWT (expira em 24 horas)
        $token = $this->jwt->encode(
            payload:   ['user_id' => $user['id'], 'email' => $user['email']],
            expiresIn: 86_400,
        );

        return JsonResponse::success([
            'user'  => [
                'id'    => $user['id'],
                'name'  => $user['name'],
                'email' => $user['email'],
            ],
            'token' => $token,
        ], 'Login realizado com sucesso.');
    }

    /**
     * GET /api/v1/auth/me
     * Retorna dados do usuário autenticado.
     * Requer: AuthMiddleware (injeta auth_user_id no request).
     */
    public function me(Request $request): Response
    {
        // O middleware de autenticação adiciona o user_id ao request
        $userId = (int) $request->input('auth_user_id');
        $user   = $this->repository->find($userId);

        if (!$user) {
            return JsonResponse::notFound('Usuário');
        }

        return JsonResponse::success([
            'id'         => $user['id'],
            'name'       => $user['name'],
            'email'      => $user['email'],
            'created_at' => $user['created_at'],
        ]);
    }
}
```

---

## 36.9 Middleware

Middlewares são **camadas de processamento** que interceptam a requisição **antes** e/ou **depois** do controller. Funcionam como filtros encadeados — cada um pode modificar o request, modificar o response, ou interromper o fluxo.

```text
Requisição → [CORS] → [RateLimit] → [Auth] → Controller → Response
```

### Interface de Middleware

```php
<?php
// src/Middleware/MiddlewareInterface.php

declare(strict_types=1);

namespace App\Middleware;

use App\Http\Request;
use App\Http\Response;

/**
 * Contrato para todos os middlewares da aplicação.
 *
 * Cada middleware recebe um Request e decide:
 *   - Retornar null → continuar para o próximo middleware/controller
 *   - Retornar Response → interromper o fluxo (ex: 401, 429)
 */
interface MiddlewareInterface
{
    /**
     * Processa a requisição.
     *
     * @param Request $request Requisição HTTP atual
     * @return Response|null Response para interromper, null para continuar
     */
    public function handle(Request $request): ?Response;
}
```

### Middleware de Autenticação

```php
<?php
// src/Middleware/AuthMiddleware.php

declare(strict_types=1);

namespace App\Middleware;

use App\Http\Request;
use App\Http\Response;
use App\Http\JsonResponse;
use App\Helpers\JWT;

/**
 * Middleware de autenticação JWT.
 *
 * Verifica se a requisição contém um token Bearer válido.
 * Se válido, injeta o user_id no request para uso posterior.
 * Se inválido, retorna 401 Unauthorized.
 */
final class AuthMiddleware implements MiddlewareInterface
{
    public function __construct(
        private readonly JWT $jwt = new JWT(
            $_ENV['JWT_SECRET'] ?? throw new \RuntimeException(
                'JWT_SECRET não configurado.',
            ),
        ),
    ) {}

    public function handle(Request $request): ?Response
    {
        // Extrair token do header Authorization: Bearer <token>
        $token = $request->bearerToken();

        if ($token === null) {
            return JsonResponse::unauthorized(
                'Token de autenticação não fornecido. '
                . 'Envie no header: Authorization: Bearer <seu_token>',
            );
        }

        // Decodificar e validar token
        $payload = $this->jwt->decode($token);

        if ($payload === null) {
            return JsonResponse::unauthorized(
                'Token inválido ou expirado. Faça login novamente.',
            );
        }

        // Injetar user_id no request para o controller usar
        $_REQUEST['auth_user_id'] = $payload['user_id'];

        // null = continuar para o próximo middleware/controller
        return null;
    }
}
```

### Middleware CORS

```php
<?php
// src/Middleware/CorsMiddleware.php

declare(strict_types=1);

namespace App\Middleware;

use App\Http\Request;
use App\Http\Response;

/**
 * Middleware de CORS (Cross-Origin Resource Sharing).
 *
 * Define quais origens, métodos e headers são permitidos
 * em requisições cross-origin. Em produção, use origens específicas!
 *
 * @see https://developer.mozilla.org/pt-BR/docs/Web/HTTP/CORS
 */
final class CorsMiddleware implements MiddlewareInterface
{
    /** Métodos HTTP permitidos */
    private const string ALLOWED_METHODS = 'GET, POST, PUT, PATCH, DELETE, OPTIONS';

    /** Headers permitidos na requisição */
    private const string ALLOWED_HEADERS = 'Content-Type, Authorization, X-Requested-With';

    /** Cache do preflight em segundos (24 horas) */
    private const int MAX_AGE = 86_400;

    /**
     * @param string $allowedOrigin Origem permitida ('*' apenas em desenvolvimento!)
     */
    public function __construct(
        private readonly string $allowedOrigin = '*',
    ) {}

    public function handle(Request $request): ?Response
    {
        // ⚠️ Em produção, NUNCA use '*' — especifique o domínio exato
        // Exemplo: 'https://meusite.com.br'
        header("Access-Control-Allow-Origin: {$this->allowedOrigin}");
        header('Access-Control-Allow-Methods: ' . self::ALLOWED_METHODS);
        header('Access-Control-Allow-Headers: ' . self::ALLOWED_HEADERS);
        header('Access-Control-Max-Age: ' . self::MAX_AGE);

        // Requisição OPTIONS (preflight) — responder imediatamente
        if ($request->getMethod() === 'OPTIONS') {
            http_response_code(200);
            exit;
        }

        return null;
    }
}
```

### Pipeline de Middleware

```php
<?php
// src/Http/MiddlewareStack.php

declare(strict_types=1);

namespace App\Http;

use App\Middleware\MiddlewareInterface;

/**
 * Pipeline de execução de middlewares.
 *
 * Executa middlewares na ordem em que foram adicionados.
 * Se qualquer middleware retornar um Response, a cadeia é interrompida.
 *
 * Exemplo de uso:
 *   $stack = new MiddlewareStack();
 *   $stack->add(new CorsMiddleware());
 *   $stack->add(new RateLimitMiddleware());
 *   $stack->add(new AuthMiddleware());
 *   $response = $stack->handle($request, fn($req) => $controller->action($req));
 */
final class MiddlewareStack
{
    /** @var MiddlewareInterface[] */
    private array $middlewares = [];

    /**
     * Adiciona um middleware à pilha.
     * A ordem de adição define a ordem de execução.
     */
    public function add(MiddlewareInterface $middleware): self
    {
        $this->middlewares[] = $middleware;
        return $this;
    }

    /**
     * Executa todos os middlewares e, se nenhum interromper, o handler final.
     *
     * @param Request $request Requisição HTTP
     * @param callable(Request): Response $next Handler final (controller)
     * @return Response Resposta do middleware que interrompeu ou do controller
     */
    public function handle(Request $request, callable $next): Response
    {
        // Percorrer middlewares na ordem — qualquer um pode interromper
        foreach ($this->middlewares as $middleware) {
            $response = $middleware->handle($request);

            // Se retornou Response, interromper a cadeia
            if ($response instanceof Response) {
                return $response;
            }
        }

        // Todos os middlewares passaram — executar o controller
        return $next($request);
    }
}
```

---

## 36.10 Validação de Requisições

Um **ValidationService** centralizado permite reaproveitar regras de validação em qualquer controller, mantendo a lógica limpa e desacoplada. As regras seguem um formato declarativo inspirado no Laravel.

### Serviço de Validação

```php
<?php
// src/Services/ValidationService.php

declare(strict_types=1);

namespace App\Services;

/**
 * Serviço de validação de dados.
 *
 * Valida arrays de dados contra regras declarativas.
 * Formato de regras: ['campo' => ['required', 'email', 'min:3', 'max:255']]
 *
 * Exemplo de uso:
 *   $validator = new ValidationService();
 *   $errors = $validator->validate($data, [
 *       'name'     => ['required', 'min:3', 'max:100'],
 *       'email'    => ['required', 'email', 'unique:users'],
 *       'password' => ['required', 'min:8', 'confirmed'],
 *   ]);
 */
final class ValidationService
{
    /**
     * Valida dados contra um conjunto de regras.
     *
     * @param array<string, mixed> $data Dados a validar
     * @param array<string, list<string>> $rules Regras por campo
     * @return array<string, list<string>> Erros agrupados por campo (vazio = válido)
     */
    #[\NoDiscard('Sempre verifique o resultado da validação antes de prosseguir.')]
    public function validate(array $data, array $rules): array
    {
        $errors = [];

        foreach ($rules as $field => $fieldRules) {
            $value = $data[$field] ?? null;

            foreach ($fieldRules as $rule) {
                $error = $this->applyRule($field, $value, $rule, $data);

                if ($error !== null) {
                    $errors[$field][] = $error;
                }
            }
        }

        return $errors;
    }

    /**
     * Aplica uma regra individual a um campo.
     * Formato da regra: 'nome_regra' ou 'nome_regra:param1,param2'
     */
    private function applyRule(
        string $field,
        mixed $value,
        string $rule,
        array $allData,
    ): ?string {
        // Separar nome da regra e parâmetros: "min:3" → ['min', '3']
        $parts     = explode(':', $rule, limit: 2);
        $ruleName  = $parts[0];
        $ruleParam = $parts[1] ?? null;

        return match ($ruleName) {
            'required'  => $this->validateRequired($value),
            'email'     => $this->validateEmail($value),
            'url'       => $this->validateUrl($value),
            'numeric'   => $this->validateNumeric($value),
            'min'       => $this->validateMin($value, (int) $ruleParam),
            'max'       => $this->validateMax($value, (int) $ruleParam),
            'confirmed' => $this->validateConfirmed($field, $value, $allData),
            default     => null, // Regra desconhecida — ignorar
        };
    }

    // ── Regras de validação individuais ──

    private function validateRequired(mixed $value): ?string
    {
        // Aceitar '0' e 0 como válidos (são valores reais)
        if ($value === null || $value === '' || $value === []) {
            return 'Este campo é obrigatório.';
        }

        return null;
    }

    private function validateEmail(mixed $value): ?string
    {
        if (empty($value)) {
            return null; // Deixar para a regra 'required' validar presença
        }

        if (!filter_var($value, FILTER_VALIDATE_EMAIL)) {
            return 'Informe um email válido.';
        }

        return null;
    }

    private function validateUrl(mixed $value): ?string
    {
        if (empty($value)) {
            return null;
        }

        // ✅ PHP 8.5: usar a nova extensão URI para validação robusta
        try {
            new \Uri\Rfc3986\Uri((string) $value);
            return null;
        } catch (\Throwable) {
            return 'Informe uma URL válida.';
        }
    }

    private function validateNumeric(mixed $value): ?string
    {
        if (empty($value)) {
            return null;
        }

        if (!is_numeric($value)) {
            return 'Este campo deve ser um número.';
        }

        return null;
    }

    private function validateMin(mixed $value, int $min): ?string
    {
        if (empty($value)) {
            return null;
        }

        // Para strings: verificar comprimento (multibyte-safe)
        if (is_string($value) && mb_strlen($value) < $min) {
            return "Deve ter no mínimo {$min} caracteres.";
        }

        // Para números: verificar valor
        if (is_numeric($value) && (float) $value < $min) {
            return "O valor mínimo é {$min}.";
        }

        return null;
    }

    private function validateMax(mixed $value, int $max): ?string
    {
        if (empty($value)) {
            return null;
        }

        if (is_string($value) && mb_strlen($value) > $max) {
            return "Deve ter no máximo {$max} caracteres.";
        }

        if (is_numeric($value) && (float) $value > $max) {
            return "O valor máximo é {$max}.";
        }

        return null;
    }

    private function validateConfirmed(string $field, mixed $value, array $allData): ?string
    {
        // Procurar campo de confirmação: 'password' → 'password_confirmation'
        $confirmationField = "{$field}_confirmation";
        $confirmationValue = $allData[$confirmationField] ?? null;

        if ($value !== $confirmationValue) {
            return 'Os campos não coincidem.';
        }

        return null;
    }
}
```

### Uso no Controller

```php
<?php
// Exemplo de uso do ValidationService em um controller

declare(strict_types=1);

// No método store() de qualquer controller:
public function store(Request $request): Response
{
    $validator = new ValidationService();

    $errors = $validator->validate($request->all(), [
        'name'                  => ['required', 'min:3', 'max:100'],
        'email'                 => ['required', 'email'],
        'password'              => ['required', 'min:8', 'confirmed'],
        'password_confirmation' => ['required'],
    ]);

    // Se há erros, retornar 422
    if (!empty($errors)) {
        return JsonResponse::validationError($errors);
    }

    // Dados válidos — prosseguir com a criação
    // ...
}
```

---

## 36.11 Rate Limiting

Rate limiting protege sua API contra **abuso** e **ataques de força bruta**, limitando o número de requisições que um cliente pode fazer em um período de tempo. Sem ele, qualquer pessoa pode sobrecarregar seu servidor.

### Middleware de Rate Limiting

```php
<?php
// src/Middleware/RateLimitMiddleware.php

declare(strict_types=1);

namespace App\Middleware;

use App\Http\Request;
use App\Http\Response;
use App\Http\JsonResponse;

/**
 * Middleware de rate limiting (janela deslizante).
 *
 * Limita o número de requisições por cliente (IP ou token)
 * dentro de uma janela de tempo configurável.
 *
 * Headers adicionados em todas as respostas:
 *   X-RateLimit-Limit:     Limite total de requisições por janela
 *   X-RateLimit-Remaining: Requisições restantes na janela atual
 *   X-RateLimit-Reset:     Timestamp Unix de quando o contador reseta
 */
final class RateLimitMiddleware implements MiddlewareInterface
{
    /** Diretório para armazenar contadores de requisição */
    private const string CACHE_DIR = __DIR__ . '/../../storage/rate_limit';

    /**
     * @param int $maxRequests Máximo de requisições permitidas na janela
     * @param int $windowSeconds Tamanho da janela em segundos
     */
    public function __construct(
        private readonly int $maxRequests = 60,
        private readonly int $windowSeconds = 60,
    ) {
        // Criar diretório de cache se não existir
        if (!is_dir(self::CACHE_DIR)) {
            mkdir(self::CACHE_DIR, 0o755, recursive: true);
        }
    }

    public function handle(Request $request): ?Response
    {
        $identifier = $this->getClientIdentifier($request);
        $cacheFile  = self::CACHE_DIR . '/' . hash('xxh3', $identifier) . '.json';

        // Carregar histórico de requisições
        $history = $this->loadHistory($cacheFile);

        // Remover requisições fora da janela atual (sliding window)
        $now     = time();
        $history = array_values(
            array_filter($history, fn(int $ts): bool => ($now - $ts) < $this->windowSeconds),
        );

        // Verificar se atingiu o limite
        if (count($history) >= $this->maxRequests) {
            $retryAfter = $this->windowSeconds - ($now - (int) array_first($history));

            // Adicionar headers informativos mesmo na resposta de erro
            header("X-RateLimit-Limit: {$this->maxRequests}");
            header('X-RateLimit-Remaining: 0');
            header("X-RateLimit-Reset: " . ($now + $retryAfter));
            header("Retry-After: {$retryAfter}");

            return JsonResponse::error(
                code:    'RATE_LIMIT_EXCEEDED',
                message: "Muitas requisições. Tente novamente em {$retryAfter} segundos.",
                details: ['retry_after_seconds' => $retryAfter],
                status:  429,
            );
        }

        // Registrar requisição atual
        $history[] = $now;

        // Salvar histórico atualizado (com file locking para concorrência)
        $this->saveHistory($cacheFile, $history);

        // Adicionar headers informativos
        $remaining = $this->maxRequests - count($history);
        header("X-RateLimit-Limit: {$this->maxRequests}");
        header("X-RateLimit-Remaining: {$remaining}");
        header("X-RateLimit-Reset: " . ($now + $this->windowSeconds));

        return null; // Dentro do limite — continuar
    }

    /**
     * Identifica o cliente: token JWT (se autenticado) ou IP.
     */
    private function getClientIdentifier(Request $request): string
    {
        // Preferir identificação por token (mais precisa que IP)
        $token = $request->bearerToken();

        if ($token !== null) {
            return "token:{$token}";
        }

        // Fallback: identificar por IP
        return 'ip:' . ($_SERVER['REMOTE_ADDR'] ?? 'unknown');
    }

    /**
     * Carrega histórico de timestamps de requisições.
     *
     * @return list<int>
     */
    private function loadHistory(string $file): array
    {
        if (!file_exists($file)) {
            return [];
        }

        $content = file_get_contents($file);

        if ($content === false) {
            return [];
        }

        return json_decode($content, associative: true) ?? [];
    }

    /**
     * Salva histórico com file locking para evitar race conditions.
     *
     * @param list<int> $history
     */
    private function saveHistory(string $file, array $history): void
    {
        file_put_contents(
            $file,
            json_encode($history, JSON_THROW_ON_ERROR),
            flags: LOCK_EX, // File locking para segurança em concorrência
        );
    }
}
```

---

## 36.12 Versionamento

Ao mudar o contrato da API (campos renomeados, endpoints removidos, formatos alterados), você **não pode quebrar** os clientes existentes. A solução é **versionar** a URL da API — cada versão convive independente.

### Estratégia: Versionamento por URL

```php
<?php
// public/index.php — Roteamento com versionamento

declare(strict_types=1);

require_once __DIR__ . '/../vendor/autoload.php';

use App\Http\{Request, Router, MiddlewareStack};
use App\Middleware\{CorsMiddleware, RateLimitMiddleware, AuthMiddleware};

// ── Controllers V1 ──
use App\Controllers\V1\AuthController  as AuthControllerV1;
use App\Controllers\V1\UserController  as UserControllerV1;

// ── Controllers V2 (nova versão com breaking changes) ──
use App\Controllers\V2\UserController  as UserControllerV2;

// ── Tratamento global de erros ──
set_exception_handler(function (Throwable $e): void {
    $statusCode = match (true) {
        $e instanceof \App\Exceptions\NotFoundException     => 404,
        $e instanceof \App\Exceptions\ValidationException   => 422,
        $e instanceof \App\Exceptions\UnauthorizedException => 401,
        default                                             => 500,
    };

    http_response_code($statusCode);
    header('Content-Type: application/json; charset=utf-8');

    echo json_encode([
        'success' => false,
        'error'   => [
            'code'    => $e->getCode() ?: 'SERVER_ERROR',
            'message' => $statusCode === 500
                ? 'Erro interno do servidor.'
                : $e->getMessage(),
        ],
    ], JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES);
});

// ── Middlewares globais ──
$globalStack = new MiddlewareStack();
$globalStack->add(new CorsMiddleware(allowedOrigin: $_ENV['CORS_ORIGIN'] ?? '*'));
$globalStack->add(new RateLimitMiddleware(maxRequests: 60, windowSeconds: 60));

// ── Middleware de autenticação (aplicado em rotas protegidas) ──
$authStack = new MiddlewareStack();
$authStack->add(new AuthMiddleware());

$request = new Request();
$router  = new Router();

// ══════════════════════════════════════
// API v1 — Versão estável
// ══════════════════════════════════════

// Autenticação (rotas públicas)
$router->post('/api/v1/auth/register', [AuthControllerV1::class, 'register']);
$router->post('/api/v1/auth/login',    [AuthControllerV1::class, 'login']);

// Rota protegida — requer token JWT
$router->get('/api/v1/auth/me', function (Request $req) use ($authStack): \App\Http\Response {
    return $authStack->handle($req, fn($r) => (new AuthControllerV1())->me($r));
});

// Usuários v1 (rotas protegidas)
$router->get('/api/v1/users',         [UserControllerV1::class, 'index']);
$router->get('/api/v1/users/{id}',    [UserControllerV1::class, 'show']);
$router->post('/api/v1/users',        [UserControllerV1::class, 'store']);
$router->put('/api/v1/users/{id}',    [UserControllerV1::class, 'update']);
$router->delete('/api/v1/users/{id}', [UserControllerV1::class, 'destroy']);

// ══════════════════════════════════════
// API v2 — Nova versão (breaking changes)
// ══════════════════════════════════════
//
// Mudanças em v2:
//   - Campo 'name' dividido em 'first_name' e 'last_name'
//   - Paginação usa cursor em vez de offset
//   - Resposta inclui campo 'links' (HATEOAS)

$router->get('/api/v2/users',         [UserControllerV2::class, 'index']);
$router->get('/api/v2/users/{id}',    [UserControllerV2::class, 'show']);
$router->post('/api/v2/users',        [UserControllerV2::class, 'store']);

// ── Executar middleware global + despachar ──
$response = $globalStack->handle(
    $request,
    fn(Request $req): \App\Http\Response => $router->dispatch($req),
);

$response->send();
```

### Organização de Diretórios por Versão

```text
src/Controllers/
├── V1/
│   ├── AuthController.php     # Autenticação v1
│   ├── UserController.php     # Usuários v1 (campo 'name')
│   └── ProductController.php  # Produtos v1
└── V2/
    └── UserController.php     # Usuários v2 (first_name + last_name, cursor)
```

---

## 36.13 Documentação

Uma API bem documentada é uma API que os desenvolvedores **conseguem usar**. Sem documentação, sua API é inútil — não importa quão bem escrita seja.

### Documentação da API — Referência Completa

```markdown
# Minha API REST v1

## Base URL

    https://api.example.com/api/v1

## Autenticação

Todas as rotas protegidas exigem o header `Authorization`:

    Authorization: Bearer <seu_token_jwt>

Para obter um token, use os endpoints `/auth/login` ou `/auth/register`.

---

### POST /auth/register

Cria uma nova conta de usuário.

**Request:**

    POST /api/v1/auth/register
    Content-Type: application/json

    {
        "name": "João Silva",
        "email": "joao@example.com",
        "password": "senha_segura_123"
    }

**Response (201 Created):**

    {
        "success": true,
        "data": {
            "user": {
                "id": 1,
                "name": "João Silva",
                "email": "joao@example.com"
            },
            "token": "eyJhbGciOiJIUzI1NiIs..."
        },
        "message": "Usuário registrado com sucesso."
    }

---

### POST /auth/login

Autentica um usuário existente.

**Request:**

    POST /api/v1/auth/login
    Content-Type: application/json

    {
        "email": "joao@example.com",
        "password": "senha_segura_123"
    }

**Response (200 OK):**

    {
        "success": true,
        "data": {
            "user": {
                "id": 1,
                "name": "João Silva",
                "email": "joao@example.com"
            },
            "token": "eyJhbGciOiJIUzI1NiIs..."
        },
        "message": "Login realizado com sucesso."
    }

---

### GET /auth/me 🔒

Retorna o perfil do usuário autenticado.

**Request:**

    GET /api/v1/auth/me
    Authorization: Bearer <token>

**Response (200 OK):**

    {
        "success": true,
        "data": {
            "id": 1,
            "name": "João Silva",
            "email": "joao@example.com",
            "created_at": "2026-01-15 10:30:00"
        }
    }

---

### GET /users 🔒

Lista todos os usuários com paginação.

**Query Parameters:**

| Parâmetro | Tipo   | Padrão | Descrição                  |
| --------- | ------ | ------ | -------------------------- |
| page      | int    | 1      | Número da página           |
| per_page  | int    | 10     | Itens por página (max 100) |
| sort      | string | id     | Campo para ordenação       |
| order     | string | asc    | Direção: asc ou desc       |

**Response (200 OK):**

    {
        "success": true,
        "data": [
            {"id": 1, "name": "João", "email": "joao@example.com"},
            {"id": 2, "name": "Maria", "email": "maria@example.com"}
        ],
        "meta": {
            "total": 50,
            "page": 1,
            "per_page": 10,
            "last_page": 5
        }
    }

---

### POST /users 🔒

Cria um novo usuário.

**Request:**

    POST /api/v1/users
    Authorization: Bearer <token>
    Content-Type: application/json

    {
        "name": "Maria Santos",
        "email": "maria@example.com",
        "password": "outra_senha_456"
    }

**Response (201 Created):**

    {
        "success": true,
        "data": {
            "id": 2,
            "name": "Maria Santos",
            "email": "maria@example.com"
        },
        "message": "Usuário criado com sucesso."
    }

---

### Códigos de Erro

| Código | Significado           | Quando ocorre                         |
| ------ | --------------------- | ------------------------------------- |
| 400    | Bad Request           | Requisição malformada / JSON inválido |
| 401    | Unauthorized          | Token ausente, inválido ou expirado   |
| 403    | Forbidden             | Autenticado mas sem permissão         |
| 404    | Not Found             | Recurso não existe                    |
| 409    | Conflict              | Conflito (email duplicado etc.)       |
| 422    | Unprocessable Entity  | Dados de validação inválidos          |
| 429    | Too Many Requests     | Rate limit excedido                   |
| 500    | Internal Server Error | Erro interno do servidor              |

### Rate Limiting

Todas as respostas incluem headers de rate limit:

    X-RateLimit-Limit: 60          # Máximo de requisições por minuto
    X-RateLimit-Remaining: 58      # Requisições restantes
    X-RateLimit-Reset: 1706140800  # Timestamp Unix do próximo reset

Se o limite for excedido (429), aguarde o valor em `Retry-After` (em segundos).
```

---

## 36.14 API Completa — Projeto Final

Nesta seção, integramos **todos os componentes** construídos ao longo do capítulo em uma aplicação funcional completa. Depois, criamos um **ApiClient** em PHP para demonstrar como consumir a API.

### Entry Point Final (index.php)

```php
<?php
// public/index.php — Front Controller completo

declare(strict_types=1);

/**
 * ══════════════════════════════════════
 * API REST PHP 8.5 — PROJETO FINAL
 * ══════════════════════════════════════
 *
 * Este arquivo integra todos os componentes do capítulo:
 *   - Autoloading (PSR-4 via Composer)
 *   - Tratamento global de erros
 *   - Middleware stack (CORS, Rate Limit, Auth)
 *   - Roteamento versionado (v1 / v2)
 *   - Controllers com validação e JWT
 */

// ── Autoloading ──
// Em produção: use Composer (require_once __DIR__ . '/../vendor/autoload.php')
// Para estudo: autoloader manual PSR-4 simplificado
spl_autoload_register(function (string $class): void {
    // Converter namespace para caminho de arquivo
    // App\Controllers\AuthController → src/Controllers/AuthController.php
    $prefix  = 'App\\';
    $baseDir = __DIR__ . '/../src/';

    if (!str_starts_with($class, $prefix)) {
        return;
    }

    $relativeClass = substr($class, strlen($prefix));
    $file          = $baseDir . str_replace('\\', '/', $relativeClass) . '.php';

    if (file_exists($file)) {
        require_once $file;
    }
});

use App\Http\{Request, Router, Response, JsonResponse, MiddlewareStack};
use App\Middleware\{CorsMiddleware, RateLimitMiddleware, AuthMiddleware};
use App\Controllers\AuthController;
use App\Controllers\UserController;

// ── Variáveis de ambiente (.env) ──
// Em produção: use vlucas/phpdotenv ou similar
if (file_exists(__DIR__ . '/../.env')) {
    $lines = file(__DIR__ . '/../.env', FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);
    foreach ($lines as $line) {
        if (str_starts_with(trim($line), '#')) {
            continue; // Ignorar comentários
        }
        if (str_contains($line, '=')) {
            [$key, $value]   = explode('=', $line, 2);
            $_ENV[trim($key)] = trim($value);
        }
    }
}

// ── Tratamento global de erros ──
set_error_handler(function (int $severity, string $message, string $file, int $line): never {
    throw new ErrorException($message, 0, $severity, $file, $line);
});

set_exception_handler(function (Throwable $e): void {
    $statusCode = match (true) {
        $e instanceof \App\Exceptions\NotFoundException     => 404,
        $e instanceof \App\Exceptions\ValidationException   => 422,
        $e instanceof \App\Exceptions\UnauthorizedException => 401,
        $e instanceof \App\Exceptions\ForbiddenException    => 403,
        default                                             => 500,
    };

    // Em produção: logar o erro completo, retornar mensagem genérica
    if ($statusCode === 500) {
        error_log("[API ERROR] {$e->getMessage()} in {$e->getFile()}:{$e->getLine()}");
    }

    http_response_code($statusCode);
    header('Content-Type: application/json; charset=utf-8');

    echo json_encode([
        'success' => false,
        'error'   => [
            'code'    => $e->getCode() ?: 'SERVER_ERROR',
            'message' => $statusCode === 500
                ? 'Erro interno do servidor.'
                : $e->getMessage(),
        ],
    ], JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES);
});

// ══════════════════════════════════════
// CONFIGURAÇÃO DE MIDDLEWARES
// ══════════════════════════════════════

$request     = new Request();
$router      = new Router();
$globalStack = new MiddlewareStack();

// Middlewares globais (executam em TODAS as requisições)
$globalStack->add(new CorsMiddleware(
    allowedOrigin: $_ENV['CORS_ORIGIN'] ?? '*',
));
$globalStack->add(new RateLimitMiddleware(
    maxRequests:   (int) ($_ENV['RATE_LIMIT_MAX'] ?? 60),
    windowSeconds: (int) ($_ENV['RATE_LIMIT_WINDOW'] ?? 60),
));

// Middleware de autenticação (aplicado apenas em rotas protegidas)
$authMiddleware = new AuthMiddleware();

// ══════════════════════════════════════
// REGISTRO DE ROTAS — API v1
// ══════════════════════════════════════

// ── Rotas públicas ──
$router->post('/api/v1/auth/register', [AuthController::class, 'register']);
$router->post('/api/v1/auth/login',    [AuthController::class, 'login']);

// ── Rotas protegidas (requerem JWT) ──
$authStack = new MiddlewareStack();
$authStack->add($authMiddleware);

// Auth
$router->get('/api/v1/auth/me', function (Request $req) use ($authStack): Response {
    return $authStack->handle($req, fn(Request $r): Response => (new AuthController())->me($r));
});

// Usuários
$router->get('/api/v1/users', function (Request $req) use ($authStack): Response {
    return $authStack->handle($req, fn(Request $r): Response => (new UserController())->index($r));
});

$router->get('/api/v1/users/{id}', function (Request $req, array $params) use ($authStack): Response {
    return $authStack->handle($req, fn(Request $r): Response => (new UserController())->show($r, $params));
});

$router->post('/api/v1/users', function (Request $req) use ($authStack): Response {
    return $authStack->handle($req, fn(Request $r): Response => (new UserController())->store($r));
});

$router->put('/api/v1/users/{id}', function (Request $req, array $params) use ($authStack): Response {
    return $authStack->handle($req, fn(Request $r): Response => (new UserController())->update($r, $params));
});

$router->delete('/api/v1/users/{id}', function (Request $req, array $params) use ($authStack): Response {
    return $authStack->handle($req, fn(Request $r): Response => (new UserController())->destroy($r, $params));
});

// Health check (público)
$router->get('/api/v1/health', function (): Response {
    return JsonResponse::success([
        'status'  => 'ok',
        'version' => '1.0.0',
        'time'    => (new \DateTimeImmutable())->format('c'),
        'php'     => PHP_VERSION,
    ]);
});

// ── Despachar requisição ──
$response = $globalStack->handle(
    $request,
    fn(Request $req): Response => $router->dispatch($req),
);

$response->send();
```

### Cliente API (ApiClient)

```php
<?php
// examples/ApiClient.php

declare(strict_types=1);

/**
 * Cliente HTTP para consumir a API REST.
 *
 * Demonstra como integrar com a API usando cURL.
 * Em projetos reais, use bibliotecas como Guzzle ou Symfony HttpClient.
 */
final class ApiClient
{
    private ?string $token = null;

    public function __construct(
        private readonly string $baseUrl = 'http://localhost:8080/api/v1',
        private readonly int $timeout = 30,
    ) {}

    // ── Autenticação ──

    /**
     * Registra um novo usuário e armazena o token.
     */
    public function register(string $name, string $email, string $password): array
    {
        $response = $this->post('/auth/register', [
            'name'     => $name,
            'email'    => $email,
            'password' => $password,
        ]);

        if ($response['success'] && isset($response['data']['token'])) {
            $this->token = $response['data']['token'];
        }

        return $response;
    }

    /**
     * Faz login e armazena o token para requisições subsequentes.
     */
    public function login(string $email, string $password): array
    {
        $response = $this->post('/auth/login', [
            'email'    => $email,
            'password' => $password,
        ]);

        if ($response['success'] && isset($response['data']['token'])) {
            $this->token = $response['data']['token'];
        }

        return $response;
    }

    /**
     * Retorna o perfil do usuário autenticado.
     */
    public function me(): array
    {
        return $this->get('/auth/me');
    }

    // ── CRUD de Usuários ──

    public function listUsers(int $page = 1, int $perPage = 10): array
    {
        return $this->get("/users?page={$page}&per_page={$perPage}");
    }

    public function getUser(int $id): array
    {
        return $this->get("/users/{$id}");
    }

    public function createUser(string $name, string $email, string $password): array
    {
        return $this->post('/users', [
            'name'     => $name,
            'email'    => $email,
            'password' => $password,
        ]);
    }

    public function updateUser(int $id, array $data): array
    {
        return $this->put("/users/{$id}", $data);
    }

    public function deleteUser(int $id): array
    {
        return $this->delete("/users/{$id}");
    }

    // ── Métodos HTTP internos ──

    private function get(string $endpoint): array
    {
        return $this->request('GET', $endpoint);
    }

    private function post(string $endpoint, array $data = []): array
    {
        return $this->request('POST', $endpoint, $data);
    }

    private function put(string $endpoint, array $data = []): array
    {
        return $this->request('PUT', $endpoint, $data);
    }

    private function delete(string $endpoint): array
    {
        return $this->request('DELETE', $endpoint);
    }

    /**
     * Executa uma requisição HTTP via cURL.
     */
    private function request(string $method, string $endpoint, ?array $data = null): array
    {
        $url = $this->baseUrl . $endpoint;
        $ch  = curl_init();

        // Headers padrão
        $headers = [
            'Content-Type: application/json',
            'Accept: application/json',
        ];

        // Adicionar token JWT se autenticado
        if ($this->token !== null) {
            $headers[] = "Authorization: Bearer {$this->token}";
        }

        curl_setopt_array($ch, [
            CURLOPT_URL            => $url,
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_TIMEOUT        => $this->timeout,
            CURLOPT_HTTPHEADER     => $headers,
            CURLOPT_CUSTOMREQUEST  => $method,
        ]);

        // Adicionar body para POST/PUT/PATCH
        if ($data !== null && in_array($method, ['POST', 'PUT', 'PATCH'], strict: true)) {
            curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data, JSON_THROW_ON_ERROR));
        }

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

        if ($response === false) {
            $error = curl_error($ch);
            curl_close($ch);
            throw new \RuntimeException("Erro cURL: {$error}");
        }

        curl_close($ch);

        $decoded = json_decode($response, associative: true, flags: JSON_THROW_ON_ERROR);
        $decoded['http_code'] = $httpCode;

        return $decoded;
    }
}

// ══════════════════════════════════════
// EXEMPLO DE USO DO CLIENTE
// ══════════════════════════════════════

$api = new ApiClient('http://localhost:8080/api/v1');

try {
    // 1. Registrar novo usuário
    echo "📝 Registrando usuário..." . PHP_EOL;
    $result = $api->register('João Silva', 'joao@example.com', 'senha_segura_123');
    echo "✅ Registrado! Token: " . substr($result['data']['token'], 0, 30) . "..." . PHP_EOL;

    // 2. Obter perfil
    echo PHP_EOL . "👤 Buscando perfil..." . PHP_EOL;
    $profile = $api->me();
    echo "Nome: {$profile['data']['name']}" . PHP_EOL;
    echo "Email: {$profile['data']['email']}" . PHP_EOL;

    // 3. Listar usuários
    echo PHP_EOL . "📋 Listando usuários..." . PHP_EOL;
    $users = $api->listUsers(page: 1, perPage: 5);
    foreach ($users['data'] as $user) {
        echo "  → [{$user['id']}] {$user['name']} ({$user['email']})" . PHP_EOL;
    }

    // 4. Criar outro usuário
    echo PHP_EOL . "➕ Criando usuário..." . PHP_EOL;
    $newUser = $api->createUser('Maria Santos', 'maria@example.com', 'outra_senha_456');
    echo "✅ Criado com ID: {$newUser['data']['id']}" . PHP_EOL;

    // 5. Atualizar usuário
    echo PHP_EOL . "✏️ Atualizando..." . PHP_EOL;
    $updated = $api->updateUser($newUser['data']['id'], ['name' => 'Maria S. Oliveira']);
    echo "✅ Atualizado: {$updated['data']['name']}" . PHP_EOL;

    // 6. Deletar usuário
    echo PHP_EOL . "🗑️ Deletando..." . PHP_EOL;
    $api->deleteUser($newUser['data']['id']);
    echo "✅ Deletado com sucesso!" . PHP_EOL;

} catch (Throwable $e) {
    echo "❌ Erro: {$e->getMessage()}" . PHP_EOL;
}
```

---

## Exercícios — Parte 2

```php
<?php

declare(strict_types=1);

/**
 * ══════════════════════════════════════════════════════════════
 * EXERCÍCIOS — APIs REST Avançadas com PHP 8.5
 * ══════════════════════════════════════════════════════════════
 *
 * INICIANTE (⭐):
 * ──────────────
 *
 *  1. No AuthController, adicione um endpoint POST /auth/logout
 *     que invalide o token adicionando-o a uma "blacklist" (arquivo JSON).
 *     O AuthMiddleware deve verificar a blacklist antes de aceitar um token.
 *
 *  2. Adicione a regra de validação 'in:valor1,valor2,valor3'
 *     ao ValidationService. Deve verificar se o valor está na lista.
 *     Exemplo: 'role' => ['required', 'in:admin,user,moderator']
 *
 *  3. Crie um endpoint GET /api/v1/health que retorne:
 *     { "status": "ok", "uptime": 12345, "version": "1.0.0", "php": "8.5.0" }
 *     Calcule o uptime em segundos desde que o servidor iniciou.
 *
 * INTERMEDIÁRIO (⭐⭐):
 * ─────────────────────
 *
 *  4. Implemente um ProductController completo com CRUD e validação:
 *     - name: required, min:3, max:200
 *     - price: required, numeric, min:0.01
 *     - sku: required, unique:products
 *     - category: required, in:electronics,books,clothing,food
 *     Use o ValidationService para todas as validações.
 *
 *  5. Implemente refresh token: ao fazer login, retorne um
 *     access_token (1h) e um refresh_token (30 dias).
 *     Crie endpoint POST /auth/refresh que aceite o refresh_token
 *     e retorne um novo access_token.
 *
 *  6. Implemente rate limiting diferenciado por endpoint:
 *     - POST /auth/login → 5 req/min (proteção contra brute force)
 *     - GET /users        → 100 req/min (leitura)
 *     - POST /users       → 10 req/min (escrita)
 *     Dica: configure o RateLimitMiddleware com parâmetros diferentes.
 *
 *  7. Adicione soft delete ao UserController:
 *     - DELETE não remove, apenas marca deleted_at = NOW()
 *     - GET não retorna usuários com deleted_at preenchido
 *     - Crie POST /users/{id}/restore para restaurar
 *
 * AVANÇADO (⭐⭐⭐):
 * ──────────────────
 *
 *  8. Implemente upload de imagens via API:
 *     - POST /api/v1/upload (multipart/form-data)
 *     - Valide tipo (jpeg, png, webp), tamanho (máx 5MB)
 *     - Salve com nome UUID + extensão original
 *     - Retorne URL pública do arquivo
 *     Dica: $_FILES + move_uploaded_file() + getimagesize()
 *
 *  9. Crie um sistema de permissões baseado em roles:
 *     - Roles: admin, manager, user
 *     - admin: acesso total
 *     - manager: CRUD de usuários e produtos
 *     - user: apenas leitura + editar próprio perfil
 *     Crie um RoleMiddleware que verifique permissões.
 *
 * 10. Implemente cache de respostas GET com ETag:
 *     - Calcule hash MD5 do conteúdo da resposta
 *     - Retorne header ETag: "hash..."
 *     - Se cliente enviar If-None-Match com mesmo hash, retorne 304
 *     - Adicione header X-Cache: HIT ou X-Cache: MISS
 *
 * 11. Crie um sistema de webhooks:
 *     - POST /api/v1/webhooks para registrar URLs de callback
 *     - Ao criar/atualizar/deletar recurso, envie notificação
 *     - Inclua retry com backoff exponencial (1s, 2s, 4s, 8s)
 *     - Assine o payload com HMAC-SHA256 para o webhook verificar
 */
```

---

## Resumo do Capítulo 36 — Parte 2

```php
<?php

declare(strict_types=1);

/**
 * ╔═══════════════════════════════════════════════════════════════╗
 * ║           RESUMO: APIs REST AVANÇADAS COM PHP 8.5            ║
 * ╠═══════════════════════════════════════════════════════════════╣
 * ║                                                               ║
 * ║  AUTENTICAÇÃO JWT (36.8):                                     ║
 * ║  ├── JWT = Header + Payload + Signature (Base64URL + HMAC)    ║
 * ║  ├── hash_equals() para comparação timing-safe                ║
 * ║  ├── password_hash(PASSWORD_ARGON2ID) para senhas             ║
 * ║  └── Token expira em tempo configurável (iat + exp)           ║
 * ║                                                               ║
 * ║  MIDDLEWARE (36.9):                                           ║
 * ║  ├── MiddlewareInterface → contrato para todos os middlewares ║
 * ║  ├── AuthMiddleware → verifica JWT e injeta user_id           ║
 * ║  ├── CorsMiddleware → headers CORS + preflight OPTIONS        ║
 * ║  └── MiddlewareStack → pipeline encadeado de middlewares      ║
 * ║                                                               ║
 * ║  VALIDAÇÃO (36.10):                                           ║
 * ║  ├── ValidationService com regras declarativas                ║
 * ║  ├── match expression para dispatch de regras                 ║
 * ║  ├── mb_strlen() para strings multibyte                       ║
 * ║  └── Uri\Rfc3986\Uri (PHP 8.5) para validação de URLs        ║
 * ║                                                               ║
 * ║  RATE LIMITING (36.11):                                       ║
 * ║  ├── Sliding window com cache em arquivo                      ║
 * ║  ├── LOCK_EX para evitar race conditions                      ║
 * ║  ├── array_first() (PHP 8.5) para dados do histórico         ║
 * ║  └── Headers X-RateLimit-* e Retry-After                      ║
 * ║                                                               ║
 * ║  VERSIONAMENTO (36.12):                                       ║
 * ║  ├── Versionamento por URL: /api/v1/ e /api/v2/              ║
 * ║  ├── Controllers organizados em namespaces por versão         ║
 * ║  └── Versões coexistem independentemente                      ║
 * ║                                                               ║
 * ║  DOCUMENTAÇÃO (36.13):                                        ║
 * ║  ├── Referência completa de endpoints com exemplos            ║
 * ║  ├── Tabela de códigos de erro e seus significados            ║
 * ║  └── Detalhes de rate limiting e autenticação                 ║
 * ║                                                               ║
 * ║  PROJETO FINAL (36.14):                                       ║
 * ║  ├── index.php integrando todos os componentes                ║
 * ║  ├── ApiClient completo com cURL                              ║
 * ║  └── Exercícios para 3 níveis de dificuldade                  ║
 * ║                                                               ║
 * ║  FEATURES PHP 8.5 UTILIZADAS:                                 ║
 * ║  ├── declare(strict_types=1) em todos os arquivos             ║
 * ║  ├── readonly properties + constructor promotion              ║
 * ║  ├── match expression para decisões complexas                 ║
 * ║  ├── first-class callables (fn($r) => ...)                    ║
 * ║  ├── named arguments (binary: true, status: 429)              ║
 * ║  ├── typed class constants (const string, const int)          ║
 * ║  ├── #[\NoDiscard] attribute para retornos críticos           ║
 * ║  ├── array_first() / array_last() (PHP 8.5)                  ║
 * ║  ├── Uri\Rfc3986\Uri para validação de URLs (PHP 8.5)        ║
 * ║  ├── never return type para handlers de erro                  ║
 * ║  ├── Closure e arrow functions                                ║
 * ║  └── union types, nullable types, intersection types          ║
 * ║                                                               ║
 * ╚═══════════════════════════════════════════════════════════════╝
 */
```

---

**Capítulo 36 completo!** 🎉

Com as duas partes deste capítulo, você agora domina a criação de APIs REST profissionais com PHP 8.5 — desde a teoria (verbos HTTP, status codes, REST) até a implementação completa com autenticação JWT, middlewares, validação, rate limiting, versionamento e documentação. Use os exercícios para consolidar o aprendizado e avance para projetos reais! 🚀

---
---

# 🤖 Bônus: Conectando a API do Gemini com PHP 8.5

**Guia Completo — Da Configuração ao Chat Interativo**

> Neste bônus, aplicamos tudo que aprendemos no Capítulo 36 (cURL, JSON,
> autenticação por API Key, tratamento de erros) para integrar a
> **Generative Language API do Google** (Gemini) em projetos PHP.

---

## Índice

1. [O que é o Gemini?](#1-o-que-é-o-gemini)
2. [Obtendo sua API Key](#2-obtendo-sua-api-key)
3. [Primeira Requisição](#3-primeira-requisição)
4. [Classe GeminiClient](#4-classe-geminiclient)
5. [Exemplos Práticos](#5-exemplos-práticos)
6. [Chat Interativo](#6-chat-interativo)
7. [Análise de Imagens (Multimodal)](#7-análise-de-imagens-multimodal)
8. [Tratamento de Erros](#8-tratamento-de-erros)
9. [Boas Práticas e Segurança](#9-boas-práticas-e-segurança)

---

## 1. O que é o Gemini?

```php
<?php

declare(strict_types=1);

/**
 * GEMINI — Inteligência Artificial do Google
 * ===========================================
 *
 * O Gemini é a família de modelos de IA generativa do Google, acessível
 * via API REST. Você envia um prompt (texto, imagem ou ambos) e recebe
 * uma resposta gerada pelo modelo.
 *
 * MODELOS DISPONÍVEIS:
 * ────────────────────
 *
 *   gemini-2.0-flash  → Rápido e eficiente (recomendado para a maioria dos usos)
 *   gemini-2.5-flash  → Mais recente, com raciocínio avançado
 *   gemini-1.5-pro    → Contexto longo (até 1M tokens)
 *
 * O QUE A API FAZ:
 * ────────────────
 *
 *   ✅ Gerar textos e respostas a perguntas
 *   ✅ Manter conversas com contexto (chat multi-turn)
 *   ✅ Analisar e descrever imagens (multimodal)
 *   ✅ Traduzir idiomas
 *   ✅ Resumir documentos
 *   ✅ Gerar e explicar código
 *
 * PREÇO:
 * ──────
 *   Tier gratuito: até 15 requisições por minuto (RPM) — perfeito para aprender!
 *   Planos pagos: limites maiores, prioridade, SLA
 *
 * COMO FUNCIONA NO PHP:
 * ─────────────────────
 *
 *   1. Obter API Key no Google AI Studio (gratuito)
 *   2. Enviar POST HTTP para a API com JSON do prompt
 *   3. Receber resposta JSON com texto gerado
 *   4. Processar e exibir o resultado
 */
```

### Casos de uso reais

```php
<?php

declare(strict_types=1);

/**
 * EXEMPLOS DE APLICAÇÕES:
 * =======================
 *
 *  1. CHATBOT NO SITE
 *     → Atendimento automático 24/7
 *     → Respostas instantâneas a dúvidas frequentes
 *
 *  2. GERADOR DE CONTEÚDO
 *     → Descrições de produtos para e-commerce
 *     → Posts de blog, emails marketing
 *     → SEO: meta descriptions automáticas
 *
 *  3. ANÁLISE DE IMAGENS (Multimodal)
 *     → Categorizar fotos de produtos
 *     → OCR — extrair texto de imagens
 *     → Descrever imagens para acessibilidade (alt text)
 *
 *  4. TRADUTOR AUTOMÁTICO
 *     → Internacionalizar conteúdo do site
 *     → Tradução de reviews de clientes
 *
 *  5. ASSISTENTE DE CÓDIGO
 *     → Code review automatizado
 *     → Gerar testes unitários
 *     → Documentar funções automaticamente
 *
 *  6. MODERAÇÃO DE CONTEÚDO
 *     → Detectar linguagem ofensiva em comentários
 *     → Classificar conteúdo por categoria
 *     → Filtrar spam inteligente
 */
```

---

## 2. Obtendo sua API Key

### 2.1 Passo a Passo

```text
COMO OBTER A CHAVE DA API (GRÁTIS):
════════════════════════════════════

1. Acesse: https://aistudio.google.com/apikey

2. Faça login com sua conta Google

3. Clique em "Create API Key"

4. Selecione um projeto do Google Cloud (ou crie um novo)

5. Copie a chave gerada:
   AIzaSyBxXxXxXxXxXxXxXxXxXxXxXxXxXxXxXxX

╔══════════════════════════════════════════════╗
║  ⚠️  REGRAS DE SEGURANÇA:                    ║
║  • NUNCA commitar a chave no Git             ║
║  • NUNCA expor no frontend (JavaScript)      ║
║  • SEMPRE usar variáveis de ambiente         ║
║  • Rotacionar a chave se comprometida        ║
╚══════════════════════════════════════════════╝
```

### 2.2 Armazenar a Chave com Segurança

```php
<?php
// config/gemini.php

declare(strict_types=1);

/**
 * ❌ NUNCA faça isso:
 *    const API_KEY = 'AIzaSy...'; // Hardcoded — inseguro!
 *
 * ✅ Use SEMPRE variáveis de ambiente:
 */

// ── Método 1: Carregar de arquivo .env ──

function loadEnv(string $path): void
{
    if (!file_exists($path)) {
        throw new RuntimeException("Arquivo .env não encontrado: {$path}");
    }

    $lines = file($path, FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);

    foreach ($lines as $line) {
        $line = trim($line);

        // Ignorar comentários e linhas vazias
        if ($line === '' || str_starts_with($line, '#')) {
            continue;
        }

        // Separar KEY=VALUE (suporta valores com '=' dentro)
        $pos = strpos($line, '=');

        if ($pos === false) {
            continue;
        }

        $key   = trim(substr($line, 0, $pos));
        $value = trim(substr($line, $pos + 1));

        // Remover aspas envolventes
        $value = trim($value, '"\'');

        $_ENV[$key]    = $value;
        $_SERVER[$key] = $value;
    }
}

// Carregar variáveis
loadEnv(__DIR__ . '/../.env');

// Validar presença da chave
$geminiApiKey = $_ENV['GEMINI_API_KEY']
    ?? throw new RuntimeException(
        'GEMINI_API_KEY não configurada. Adicione ao arquivo .env',
    );
```

```ini
# .env (na raiz do projeto)
GEMINI_API_KEY=AIzaSyBxXxXxXxXxXxXxXxXxXxXxXxXxXxXxXxX
GEMINI_MODEL=gemini-3-flash-preview
```

```gitignore
# .gitignore — NUNCA esqueça!
.env
.env.*
config/gemini.php
```

---

## 3. Primeira Requisição

### 3.1 Requisição Simples com cURL

```php
<?php
// test_gemini.php — Seu primeiro contato com a API

declare(strict_types=1);

require_once __DIR__ . '/config/gemini.php';

// ── Configuração ──
$apiKey = $_ENV['GEMINI_API_KEY'];
$model  = $_ENV['GEMINI_MODEL'] ?? 'gemini-3-flash-preview';

$url = "https://generativelanguage.googleapis.com/v1beta/models/{$model}:generateContent?key={$apiKey}";

// ── Prompt (sua pergunta/instrução) ──
$prompt = 'Explique o que é PHP em 3 linhas simples, em português.';

// ── Corpo da requisição ──
$body = json_encode([
    'contents' => [
        [
            'parts' => [
                ['text' => $prompt],
            ],
        ],
    ],
    // Configurações opcionais de geração
    'generationConfig' => [
        'temperature'     => 0.7,  // 0.0 = determinístico, 1.0 = criativo
        'maxOutputTokens' => 256,  // Limite de tokens na resposta
    ],
], JSON_THROW_ON_ERROR);

// ── Requisição cURL ──
$ch = curl_init();

curl_setopt_array($ch, [
    CURLOPT_URL            => $url,
    CURLOPT_POST           => true,
    CURLOPT_POSTFIELDS     => $body,
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_TIMEOUT        => 30,
    CURLOPT_HTTPHEADER     => ['Content-Type: application/json'],
]);

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
$curlError = curl_error($ch);

curl_close($ch);

// ── Tratar resposta ──
if ($response === false) {
    echo "❌ Erro de conexão: {$curlError}" . PHP_EOL;
    exit(1);
}

if ($httpCode !== 200) {
    echo "❌ Erro HTTP {$httpCode}:" . PHP_EOL;
    echo $response . PHP_EOL;
    exit(1);
}

$data = json_decode($response, true, flags: JSON_THROW_ON_ERROR);

// Extrair texto da resposta
$text = $data['candidates'][0]['content']['parts'][0]['text']
    ?? 'Sem resposta.';

echo "✅ RESPOSTA DO GEMINI:" . PHP_EOL . PHP_EOL;
echo $text . PHP_EOL;
```

**Executar:**

```bash
php test_gemini.php
```

**Saída esperada:**

```text
✅ RESPOSTA DO GEMINI:

PHP é uma linguagem de programação server-side criada em 1994, usada para
construir sites e aplicações web dinâmicas. É open-source, roda em todos
os sistemas operacionais e está por trás de sites como WordPress e Facebook.
```

---

## 4. Classe GeminiClient

### 4.1 Tipos e Exceção

```php
<?php
// src/Gemini/GeminiModel.php

declare(strict_types=1);

namespace App\Gemini;

/**
 * Modelos disponíveis na API do Gemini.
 */
enum GeminiModel: string
{
    case Flash20     = 'gemini-2.0-flash';
    case Flash25     = 'gemini-2.5-flash';
    case Pro15       = 'gemini-1.5-pro';

    /**
     * Indica se o modelo suporta entrada multimodal (texto + imagem).
     */
    public function supportsVision(): bool
    {
        return true; // Todos os modelos atuais suportam visão
    }

    /**
     * Limite máximo de tokens de saída recomendado.
     */
    public function defaultMaxTokens(): int
    {
        return match ($this) {
            self::Flash20 => 8_192,
            self::Flash25 => 8_192,
            self::Pro15   => 8_192,
        };
    }
}
```

```php
<?php
// src/Gemini/GeminiException.php

declare(strict_types=1);

namespace App\Gemini;

/**
 * Exceção específica para erros da API do Gemini.
 */
class GeminiException extends \RuntimeException
{
    public function __construct(
        string $message,
        public readonly int $httpCode = 0,
        public readonly ?string $errorCode = null,
        ?\Throwable $previous = null,
    ) {
        parent::__construct($message, $httpCode, $previous);
    }

    /**
     * Criar exceção a partir da resposta de erro da API.
     */
    public static function fromApiResponse(int $httpCode, string $responseBody): self
    {
        $data = json_decode($responseBody, true);

        $message   = $data['error']['message'] ?? 'Erro desconhecido da API.';
        $errorCode = $data['error']['status']  ?? null;

        return new self(
            message:   "Gemini API [{$httpCode}]: {$message}",
            httpCode:  $httpCode,
            errorCode: $errorCode,
        );
    }
}
```

### 4.2 Cliente Completo

```php
<?php
// src/Gemini/GeminiClient.php

declare(strict_types=1);

namespace App\Gemini;

/**
 * Cliente PHP 8.5 para a Generative Language API (Gemini).
 *
 * Suporta:
 *   - Geração de texto (generateContent)
 *   - Chat multi-turn com histórico
 *   - Análise de imagens (multimodal)
 *   - Configuração de temperatura, maxOutputTokens, topP, topK
 *
 * @example
 *   $client = new GeminiClient('AIzaSy...');
 *   $resposta = $client->generateText('Explique o que é PHP.');
 */
final class GeminiClient
{
    private const string BASE_URL = 'https://generativelanguage.googleapis.com/v1beta';

    public function __construct(
        private readonly string $apiKey,
        private readonly GeminiModel $model = GeminiModel::Flash20,
        private readonly int $timeout = 30,
        private readonly float $temperature = 0.7,
        private readonly int $maxOutputTokens = 2048,
    ) {
        if (trim($this->apiKey) === '') {
            throw new \InvalidArgumentException('API Key do Gemini é obrigatória.');
        }
    }

    // ═══════════════════════════════════════════
    // MÉTODOS PÚBLICOS
    // ═══════════════════════════════════════════

    /**
     * Gerar texto a partir de um prompt.
     *
     * @param string $prompt Pergunta ou instrução
     * @return string Texto gerado pelo modelo
     * @throws GeminiException
     */
    #[\NoDiscard('A resposta gerada deve ser utilizada.')]
    public function generateText(string $prompt): string
    {
        $body = [
            'contents' => [
                ['parts' => [['text' => $prompt]]],
            ],
            'generationConfig' => $this->generationConfig(),
        ];

        return $this->extractText(
            $this->request($this->endpoint('generateContent'), $body),
        );
    }

    /**
     * Chat multi-turn — mantém contexto da conversa.
     *
     * @param list<array{role: string, text: string}> $messages Histórico
     * @return string Resposta do modelo
     * @throws GeminiException
     */
    #[\NoDiscard('A resposta do chat deve ser utilizada.')]
    public function chat(array $messages): string
    {
        $contents = array_map(
            fn(array $msg): array => [
                'role'  => $msg['role'],  // 'user' ou 'model'
                'parts' => [['text' => $msg['text']]],
            ],
            $messages,
        );

        $body = [
            'contents'         => $contents,
            'generationConfig' => $this->generationConfig(),
        ];

        return $this->extractText(
            $this->request($this->endpoint('generateContent'), $body),
        );
    }

    /**
     * Analisar imagem com prompt (multimodal).
     *
     * @param string $prompt   Instrução sobre a imagem
     * @param string $imagePath Caminho absoluto do arquivo
     * @return string Descrição/análise gerada
     * @throws GeminiException
     */
    #[\NoDiscard('A análise da imagem deve ser utilizada.')]
    public function analyzeImage(string $prompt, string $imagePath): string
    {
        if (!file_exists($imagePath)) {
            throw new \InvalidArgumentException("Imagem não encontrada: {$imagePath}");
        }

        // Detectar MIME type
        $finfo    = new \finfo(FILEINFO_MIME_TYPE);
        $mimeType = $finfo->file($imagePath);

        $allowedMimes = ['image/jpeg', 'image/png', 'image/webp', 'image/gif'];

        if (!in_array($mimeType, $allowedMimes, true)) {
            throw new \InvalidArgumentException(
                "Tipo de imagem não suportado: {$mimeType}. " .
                'Use: ' . implode(', ', $allowedMimes),
            );
        }

        // Converter para Base64
        $imageData = base64_encode(file_get_contents($imagePath));

        $body = [
            'contents' => [
                [
                    'parts' => [
                        ['text' => $prompt],
                        [
                            'inlineData' => [
                                'mimeType' => $mimeType,
                                'data'     => $imageData,
                            ],
                        ],
                    ],
                ],
            ],
            'generationConfig' => $this->generationConfig(),
        ];

        return $this->extractText(
            $this->request($this->endpoint('generateContent'), $body),
        );
    }

    // ═══════════════════════════════════════════
    // MÉTODOS PRIVADOS
    // ═══════════════════════════════════════════

    /**
     * Montar URL do endpoint.
     */
    private function endpoint(string $action): string
    {
        return self::BASE_URL . "/models/{$this->model->value}:{$action}";
    }

    /**
     * Configuração de geração (temperatura, tokens, etc.).
     */
    private function generationConfig(): array
    {
        return [
            'temperature'     => $this->temperature,
            'maxOutputTokens' => $this->maxOutputTokens,
            'topP'            => 0.95,
            'topK'            => 40,
        ];
    }

    /**
     * Executar requisição HTTP POST para a API.
     *
     * @return array Resposta decodificada
     * @throws GeminiException
     */
    private function request(string $url, array $body): array
    {
        $url .= "?key={$this->apiKey}";

        $ch = curl_init();

        curl_setopt_array($ch, [
            CURLOPT_URL            => $url,
            CURLOPT_POST           => true,
            CURLOPT_POSTFIELDS     => json_encode($body, JSON_THROW_ON_ERROR),
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_TIMEOUT        => $this->timeout,
            CURLOPT_HTTPHEADER     => [
                'Content-Type: application/json',
            ],
        ]);

        $response  = curl_exec($ch);
        $httpCode  = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        $curlError = curl_error($ch);

        curl_close($ch);

        if ($response === false) {
            throw new GeminiException("Erro de conexão cURL: {$curlError}");
        }

        if ($httpCode !== 200) {
            throw GeminiException::fromApiResponse($httpCode, $response);
        }

        return json_decode($response, true, flags: JSON_THROW_ON_ERROR);
    }

    /**
     * Extrair texto da resposta da API.
     */
    private function extractText(array $response): string
    {
        return $response['candidates'][0]['content']['parts'][0]['text']
            ?? throw new GeminiException(
                'Resposta inesperada: campo de texto não encontrado.',
            );
    }
}
```

### 4.3 Usando a Classe

```php
<?php
// examples/simple_usage.php

declare(strict_types=1);

require_once __DIR__ . '/../config/gemini.php';

use App\Gemini\{GeminiClient, GeminiModel};

// Criar cliente (usa gemini-2.0-flash por padrão)
$gemini = new GeminiClient(
    apiKey: $_ENV['GEMINI_API_KEY'],
);

// ── 1. Pergunta simples ──
echo "🤖 " . $gemini->generateText('Qual a capital do Brasil?') . PHP_EOL . PHP_EOL;

// ── 2. Gerar conteúdo criativo ──
$gemini2 = new GeminiClient(
    apiKey:      $_ENV['GEMINI_API_KEY'],
    temperature: 0.9,  // Mais criativo
);
echo "✨ " . $gemini2->generateText(
    'Crie um slogan para uma loja de roupas sustentáveis.'
) . PHP_EOL . PHP_EOL;

// ── 3. Gerar código ──
echo "💻 " . $gemini->generateText(
    'Crie uma função PHP 8.5 que valida CPF com strict_types.'
) . PHP_EOL . PHP_EOL;

// ── 4. Tradução ──
echo "🌍 " . $gemini->generateText(
    'Traduza para inglês: "Olá, como você está?"'
) . PHP_EOL;

// ── 5. Usar modelo diferente ──
$geminiPro = new GeminiClient(
    apiKey: $_ENV['GEMINI_API_KEY'],
    model:  GeminiModel::Pro15,  // Modelo com contexto longo
);
echo "📚 " . $geminiPro->generateText(
    'Resuma os princípios SOLID em 5 linhas.'
) . PHP_EOL;
```

---

## 5. Exemplos Práticos

### 5.1 Gerador de Descrições de Produtos

```php
<?php
// examples/product_description.php

declare(strict_types=1);

require_once __DIR__ . '/../config/gemini.php';

use App\Gemini\GeminiClient;

/**
 * Gera descrições profissionais para e-commerce usando IA.
 */
final class ProductDescriptionGenerator
{
    public function __construct(
        private readonly GeminiClient $gemini,
    ) {}

    /**
     * Gerar descrição atraente para produto.
     *
     * @param array{nome: string, categoria: string, caracteristicas: string} $product
     */
    #[\NoDiscard]
    public function generate(array $product): string
    {
        $prompt = <<<PROMPT
        Crie uma descrição atraente para e-commerce do seguinte produto:

        Nome: {$product['nome']}
        Categoria: {$product['categoria']}
        Características: {$product['caracteristicas']}

        Regras:
        - Escreva 3 parágrafos curtos
        - Seja persuasivo e destaque benefícios
        - Use linguagem profissional mas acessível
        - Inclua call-to-action no final
        PROMPT;

        return $this->gemini->generateText($prompt);
    }

    /**
     * Gerar SEO: meta description para o produto.
     */
    #[\NoDiscard]
    public function generateMetaDescription(array $product): string
    {
        $prompt = <<<PROMPT
        Crie uma meta description de SEO (máximo 155 caracteres) para:
        Produto: {$product['nome']}
        Categoria: {$product['categoria']}
        PROMPT;

        return $this->gemini->generateText($prompt);
    }
}

// ── Uso ──

$gemini    = new GeminiClient(apiKey: $_ENV['GEMINI_API_KEY']);
$generator = new ProductDescriptionGenerator($gemini);

$produto = [
    'nome'             => 'Notebook Dell Inspiron 15',
    'categoria'        => 'Informática',
    'caracteristicas'  => 'Intel Core i5 13ª gen, 16GB RAM DDR5, SSD 512GB NVMe, Tela 15.6" Full HD IPS',
];

echo "📦 PRODUTO: {$produto['nome']}" . PHP_EOL . PHP_EOL;

echo "📝 DESCRIÇÃO:" . PHP_EOL;
echo $generator->generate($produto) . PHP_EOL . PHP_EOL;

echo "🔍 META DESCRIPTION (SEO):" . PHP_EOL;
echo $generator->generateMetaDescription($produto) . PHP_EOL;
```

### 5.2 Corretor e Melhorador de Textos

```php
<?php
// examples/text_corrector.php

declare(strict_types=1);

require_once __DIR__ . '/../config/gemini.php';

use App\Gemini\GeminiClient;

/**
 * Corrige gramática, melhora estilo e analisa qualidade de textos.
 */
final class TextCorrector
{
    public function __construct(
        private readonly GeminiClient $gemini,
    ) {}

    /**
     * Corrigir erros de gramática e ortografia.
     */
    #[\NoDiscard]
    public function correct(string $text): string
    {
        $prompt = <<<PROMPT
        Corrija os erros de gramática e ortografia do texto abaixo.
        Mantenha o estilo e tom originais.
        Retorne APENAS o texto corrigido, sem explicações.

        Texto:
        {$text}
        PROMPT;

        return $this->gemini->generateText($prompt);
    }

    /**
     * Melhorar estilo e clareza mantendo a mensagem.
     */
    #[\NoDiscard]
    public function improve(string $text): string
    {
        $prompt = <<<PROMPT
        Reescreva o texto abaixo para torná-lo mais claro, profissional e impactante.
        Mantenha a mensagem original.
        Retorne APENAS o texto melhorado, sem explicações.

        Texto:
        {$text}
        PROMPT;

        return $this->gemini->generateText($prompt);
    }

    /**
     * Analisar qualidade do texto com nota e sugestões.
     */
    #[\NoDiscard]
    public function analyze(string $text): string
    {
        $prompt = <<<PROMPT
        Analise a qualidade do texto abaixo e retorne:
        1. Nota de 0 a 10
        2. Pontos fortes
        3. Pontos a melhorar
        4. Sugestões específicas

        Texto:
        {$text}
        PROMPT;

        return $this->gemini->generateText($prompt);
    }
}

// ── Uso ──

$gemini    = new GeminiClient(apiKey: $_ENV['GEMINI_API_KEY']);
$corrector = new TextCorrector($gemini);

$original = 'Nosso produto é muito bom e tem varios recurso legal que voce vai gostar muito mesmo.';

echo "📄 ORIGINAL:" . PHP_EOL . $original . PHP_EOL . PHP_EOL;
echo "✅ CORRIGIDO:" . PHP_EOL . $corrector->correct($original) . PHP_EOL . PHP_EOL;
echo "✨ MELHORADO:" . PHP_EOL . $corrector->improve($original) . PHP_EOL;
```

---

## 6. Chat Interativo

### 6.1 ChatBot com Histórico

```php
<?php
// src/Gemini/ChatBot.php

declare(strict_types=1);

namespace App\Gemini;

/**
 * ChatBot com memória de conversa (multi-turn).
 *
 * Mantém o histórico de mensagens para que o modelo tenha
 * contexto das interações anteriores.
 */
final class ChatBot
{
    /** @var list<array{role: string, text: string}> */
    private array $history = [];

    public function __construct(
        private readonly GeminiClient $client,
        string $systemPrompt = '',
    ) {
        // Se há system prompt, simular como primeira interação
        if ($systemPrompt !== '') {
            $this->history[] = ['role' => 'user', 'text' => $systemPrompt];

            // Obter confirmação do modelo
            $response = $this->client->chat($this->history);

            $this->history[] = ['role' => 'model', 'text' => $response];
        }
    }

    /**
     * Enviar mensagem ao chatbot e receber resposta.
     *
     * @param string $message Mensagem do usuário
     * @return string Resposta do modelo
     * @throws GeminiException
     */
    #[\NoDiscard('A resposta do ChatBot deve ser exibida ao usuário.')]
    public function send(string $message): string
    {
        // Adicionar mensagem do usuário
        $this->history[] = ['role' => 'user', 'text' => $message];

        // Enviar conversa completa para manter contexto
        $response = $this->client->chat($this->history);

        // Salvar resposta no histórico
        $this->history[] = ['role' => 'model', 'text' => $response];

        return $response;
    }

    /**
     * Resetar histórico de conversa.
     */
    public function clear(): void
    {
        $this->history = [];
    }

    /**
     * Obter histórico completo da conversa.
     *
     * @return list<array{role: string, text: string}>
     */
    public function getHistory(): array
    {
        return $this->history;
    }

    /**
     * Total de mensagens trocadas.
     */
    public function messageCount(): int
    {
        return count($this->history);
    }
}
```

### 6.2 Chat no Terminal (CLI)

```php
<?php
// examples/chat_cli.php

declare(strict_types=1);

require_once __DIR__ . '/../config/gemini.php';

use App\Gemini\{GeminiClient, ChatBot, GeminiException};

$client = new GeminiClient(apiKey: $_ENV['GEMINI_API_KEY']);

$bot = new ChatBot(
    client: $client,
    systemPrompt: 'Você é um assistente especialista em PHP 8.5. '
        . 'Responda de forma clara, objetiva e com exemplos de código quando apropriado.',
);

echo "🤖 CHATBOT PHP 8.5 — Digite 'sair' para encerrar" . PHP_EOL;
echo str_repeat('═', 55) . PHP_EOL . PHP_EOL;

while (true) {
    echo "👤 Você: ";
    $input = trim(fgets(STDIN));

    if ($input === '' || $input === false) {
        continue;
    }

    if (strtolower($input) === 'sair') {
        echo PHP_EOL . "👋 Até logo! ({$bot->messageCount()} mensagens trocadas)" . PHP_EOL;
        break;
    }

    try {
        $response = $bot->send($input);
        echo PHP_EOL . "🤖 Gemini: {$response}" . PHP_EOL . PHP_EOL;
    } catch (GeminiException $e) {
        echo PHP_EOL . "❌ Erro: {$e->getMessage()}" . PHP_EOL . PHP_EOL;
    }
}
```

**Executar:**

```bash
php examples/chat_cli.php
```

**Exemplo de conversa:**

```text
🤖 CHATBOT PHP 8.5 — Digite 'sair' para encerrar
═══════════════════════════════════════════════════════

👤 Você: Como criar um array em PHP?

🤖 Gemini: Você pode criar arrays em PHP de várias formas:

1. Sintaxe curta (recomendada):
   $frutas = ['maçã', 'banana', 'uva'];

2. Associativo:
   $pessoa = ['nome' => 'João', 'idade' => 25];

3. Multidimensional:
   $matrix = [[1, 2], [3, 4]];

👤 Você: E como adicionar um elemento?

🤖 Gemini: Para adicionar elementos:

1. No final: $frutas[] = 'manga';
2. Com chave: $pessoa['email'] = 'joao@test.com';
3. array_push(): array_push($frutas, 'pera', 'kiwi');
4. Spread (PHP 8.5): $novo = [...$frutas, 'abacaxi'];

👤 Você: sair

👋 Até logo! (6 mensagens trocadas)
```

---

## 7. Análise de Imagens (Multimodal)

### 7.1 Analisador de Imagens

```php
<?php
// src/Gemini/ImageAnalyzer.php

declare(strict_types=1);

namespace App\Gemini;

/**
 * Analisa imagens usando o Gemini (multimodal).
 *
 * Suporta: JPEG, PNG, WebP, GIF.
 * Usa Base64 inline para enviar a imagem na requisição.
 */
final class ImageAnalyzer
{
    public function __construct(
        private readonly GeminiClient $client,
    ) {}

    /**
     * Descrever o conteúdo de uma imagem.
     */
    #[\NoDiscard]
    public function describe(string $imagePath): string
    {
        return $this->client->analyzeImage(
            prompt:    'Descreva esta imagem em detalhes, em português.',
            imagePath: $imagePath,
        );
    }

    /**
     * Identificar e listar objetos na imagem.
     */
    #[\NoDiscard]
    public function identifyObjects(string $imagePath): string
    {
        return $this->client->analyzeImage(
            prompt:    'Liste todos os objetos visíveis nesta imagem, em português.',
            imagePath: $imagePath,
        );
    }

    /**
     * Extrair texto visível na imagem (OCR).
     */
    #[\NoDiscard]
    public function extractText(string $imagePath): string
    {
        return $this->client->analyzeImage(
            prompt:    'Extraia todo o texto visível nesta imagem. '
                     . 'Se não houver texto, responda "Nenhum texto encontrado."',
            imagePath: $imagePath,
        );
    }

    /**
     * Gerar alt text acessível para a imagem (para HTML/SEO).
     */
    #[\NoDiscard]
    public function generateAltText(string $imagePath): string
    {
        return $this->client->analyzeImage(
            prompt:    'Crie um texto alternativo (alt text) conciso e descritivo '
                     . 'para esta imagem, com no máximo 125 caracteres. '
                     . 'Retorne APENAS o alt text, sem aspas.',
            imagePath: $imagePath,
        );
    }

    /**
     * Categorizar produto a partir de sua foto.
     *
     * @param list<string> $categories Categorias válidas
     */
    #[\NoDiscard]
    public function categorizeProduct(string $imagePath, array $categories): string
    {
        $categoriesStr = implode(', ', $categories);

        return $this->client->analyzeImage(
            prompt:    "Analise a imagem do produto e classifique em UMA das "
                     . "seguintes categorias: {$categoriesStr}. "
                     . 'Retorne APENAS o nome da categoria.',
            imagePath: $imagePath,
        );
    }
}
```

### 7.2 Uso do Analisador

```php
<?php
// examples/image_analysis.php

declare(strict_types=1);

require_once __DIR__ . '/../config/gemini.php';

use App\Gemini\{GeminiClient, ImageAnalyzer, GeminiException};

$client   = new GeminiClient(apiKey: $_ENV['GEMINI_API_KEY']);
$analyzer = new ImageAnalyzer($client);

$imagePath = __DIR__ . '/produto.jpg';

if (!file_exists($imagePath)) {
    echo "❌ Imagem não encontrada: {$imagePath}" . PHP_EOL;
    echo "💡 Coloque uma imagem chamada 'produto.jpg' na pasta examples/" . PHP_EOL;
    exit(1);
}

try {
    echo "🖼️  ANÁLISE DE IMAGEM" . PHP_EOL;
    echo str_repeat('═', 50) . PHP_EOL . PHP_EOL;

    // 1. Descrição completa
    echo "📝 DESCRIÇÃO:" . PHP_EOL;
    echo $analyzer->describe($imagePath) . PHP_EOL . PHP_EOL;

    // 2. Objetos identificados
    echo "🔍 OBJETOS:" . PHP_EOL;
    echo $analyzer->identifyObjects($imagePath) . PHP_EOL . PHP_EOL;

    // 3. Alt text para acessibilidade
    echo "♿ ALT TEXT:" . PHP_EOL;
    echo $analyzer->generateAltText($imagePath) . PHP_EOL . PHP_EOL;

    // 4. Categorização de produto
    echo "📂 CATEGORIA:" . PHP_EOL;
    echo $analyzer->categorizeProduct($imagePath, [
        'Eletrônicos', 'Roupas', 'Alimentos', 'Livros', 'Casa e Jardim',
    ]) . PHP_EOL;

} catch (GeminiException $e) {
    echo "❌ Erro: {$e->getMessage()}" . PHP_EOL;
}
```

---

## 8. Tratamento de Erros

### 8.1 Erros Comuns da API

```php
<?php

declare(strict_types=1);

/**
 * ERROS COMUNS DA API DO GEMINI:
 * ══════════════════════════════
 *
 * ┌──────────┬──────────────────────────────────────────────────────┐
 * │ HTTP     │ Significado                                          │
 * ├──────────┼──────────────────────────────────────────────────────┤
 * │ 400      │ Requisição malformada (JSON inválido, prompt vazio) │
 * │ 401      │ API Key inválida ou ausente                         │
 * │ 403      │ API Key sem permissão para o modelo/recurso         │
 * │ 404      │ Modelo não encontrado (nome errado)                 │
 * │ 429      │ Rate limit excedido — aguardar antes de re-tentar   │
 * │ 500      │ Erro interno do servidor do Google                  │
 * │ 503      │ Serviço temporariamente indisponível                │
 * └──────────┴──────────────────────────────────────────────────────┘
 *
 * SAFETY FILTERS:
 * ───────────────
 * A API pode bloquear respostas se o conteúdo violar as políticas de
 * segurança. Nesse caso, o campo 'candidates' pode estar vazio ou
 * conter 'finishReason' = 'SAFETY'.
 */
```

### 8.2 GeminiClient com Retry Automático

```php
<?php
// src/Gemini/GeminiClientWithRetry.php

declare(strict_types=1);

namespace App\Gemini;

/**
 * Extensão do GeminiClient com mecanismo de retry automático.
 *
 * Re-tenta a requisição em caso de erros transitórios (429, 500, 503)
 * usando exponential backoff — dobra o tempo de espera a cada tentativa.
 */
final class GeminiClientWithRetry
{
    public function __construct(
        private readonly GeminiClient $client,
        private readonly int $maxRetries = 3,
        private readonly int $baseDelayMs = 1_000,
    ) {}

    /**
     * Gerar texto com retry automático.
     *
     * @throws GeminiException Quando todas as tentativas falham
     */
    #[\NoDiscard]
    public function generateText(string $prompt): string
    {
        return $this->withRetry(
            fn(): string => $this->client->generateText($prompt),
        );
    }

    /**
     * Chat com retry automático.
     *
     * @param list<array{role: string, text: string}> $messages
     * @throws GeminiException
     */
    #[\NoDiscard]
    public function chat(array $messages): string
    {
        return $this->withRetry(
            fn(): string => $this->client->chat($messages),
        );
    }

    /**
     * Executar callable com retry e exponential backoff.
     *
     * @template T
     * @param callable(): T $operation
     * @return T
     * @throws GeminiException
     */
    private function withRetry(callable $operation): mixed
    {
        $lastException = null;

        for ($attempt = 0; $attempt <= $this->maxRetries; $attempt++) {
            try {
                return $operation();

            } catch (GeminiException $e) {
                $lastException = $e;

                // Só re-tentar em erros transitórios
                if (!$this->isRetryable($e->httpCode)) {
                    throw $e;
                }

                // Última tentativa? Não esperar, só lançar
                if ($attempt === $this->maxRetries) {
                    break;
                }

                // Exponential backoff: 1s → 2s → 4s → ...
                $delayMs = $this->baseDelayMs * (2 ** $attempt);

                // Adicionar jitter aleatório (±25%)
                $jitter = (int) ($delayMs * 0.25);
                $delayMs += random_int(-$jitter, $jitter);

                error_log(
                    "Gemini API: tentativa {$attempt}/{$this->maxRetries} "
                    . "falhou (HTTP {$e->httpCode}). Re-tentando em {$delayMs}ms...",
                );

                usleep($delayMs * 1_000); // Converter ms → µs
            }
        }

        throw new GeminiException(
            message:  "Todas as {$this->maxRetries} tentativas falharam. "
                    . "Último erro: {$lastException->getMessage()}",
            httpCode: $lastException->httpCode ?? 0,
            previous: $lastException,
        );
    }

    /**
     * Verificar se o erro HTTP é transitório (vale re-tentar).
     */
    private function isRetryable(int $httpCode): bool
    {
        return in_array($httpCode, [429, 500, 502, 503], strict: true);
    }
}
```

### 8.3 Uso com Retry

```php
<?php
// examples/with_retry.php

declare(strict_types=1);

require_once __DIR__ . '/../config/gemini.php';

use App\Gemini\{GeminiClient, GeminiClientWithRetry, GeminiException};

$client = new GeminiClient(apiKey: $_ENV['GEMINI_API_KEY']);

// Envolver com retry automático
$resilientClient = new GeminiClientWithRetry(
    client:      $client,
    maxRetries:  3,        // Até 3 tentativas
    baseDelayMs: 1_000,    // Espera inicial: 1 segundo
);

try {
    $response = $resilientClient->generateText(
        'Liste 5 frameworks PHP populares em 2026.',
    );
    echo "✅ {$response}" . PHP_EOL;

} catch (GeminiException $e) {
    // Erros persistentes (após todas as tentativas) ou não-transitórios (401, 403)
    echo "❌ Erro definitivo: {$e->getMessage()}" . PHP_EOL;
    echo "   HTTP Code: {$e->httpCode}" . PHP_EOL;
    echo "   Error Code: {$e->errorCode}" . PHP_EOL;
}
```

---

## 9. Boas Práticas e Segurança

```php
<?php

declare(strict_types=1);

/**
 * ╔═══════════════════════════════════════════════════════════════════╗
 * ║        BOAS PRÁTICAS — API DO GEMINI COM PHP 8.5                 ║
 * ╠═══════════════════════════════════════════════════════════════════╣
 * ║                                                                   ║
 * ║  🔒 SEGURANÇA:                                                    ║
 * ║  ├── NUNCA expor a API Key no frontend ou repositório             ║
 * ║  ├── Usar variáveis de ambiente (.env) ou secrets manager         ║
 * ║  ├── Rotacionar chaves periodicamente                             ║
 * ║  ├── Sanitizar input do usuário antes de enviar ao modelo         ║
 * ║  ├── Validar e filtrar a resposta do modelo antes de exibir       ║
 * ║  └── Limitar tamanho do prompt para evitar abuso                  ║
 * ║                                                                   ║
 * ║  ⚡ PERFORMANCE:                                                  ║
 * ║  ├── Usar timeout adequado (30-60s para geração de texto)         ║
 * ║  ├── Cachear respostas para prompts repetidos (Redis/Memcached)   ║
 * ║  ├── Usar streaming para respostas longas (chunked transfer)      ║
 * ║  ├── Processar em background (fila de jobs) para alto volume      ║
 * ║  └── Monitorar uso e custos com quotas de projeto                 ║
 * ║                                                                   ║
 * ║  🛡️ RESILIÊNCIA:                                                 ║
 * ║  ├── Implementar retry com exponential backoff (429, 5xx)         ║
 * ║  ├── Circuit breaker para falhas consecutivas                     ║
 * ║  ├── Fallback (resposta padrão) quando API estiver indisponível   ║
 * ║  ├── Logging de todas as chamadas (prompt, resposta, latência)    ║
 * ║  └── Alertas quando rate limit estiver próximo do máximo          ║
 * ║                                                                   ║
 * ║  📝 PROMPTS EFICIENTES:                                           ║
 * ║  ├── Ser específico e direto na instrução                         ║
 * ║  ├── Definir formato de saída esperado (JSON, lista, parágrafo)  ║
 * ║  ├── Usar few-shot examples quando necessário                     ║
 * ║  ├── Definir restrições claras (max caracteres, idioma, tom)      ║
 * ║  └── Usar temperature baixa (0.1-0.3) para tarefas factuais      ║
 * ║       e alta (0.7-0.9) para tarefas criativas                    ║
 * ║                                                                   ║
 * ║  🔧 CONFIGURAÇÃO DE GERAÇÃO:                                     ║
 * ║  ├── temperature: controla aleatoriedade (0.0 a 1.0)              ║
 * ║  ├── maxOutputTokens: limita tamanho da resposta                  ║
 * ║  ├── topP: nucleus sampling (0.0 a 1.0)                          ║
 * ║  ├── topK: limita vocabulário considerado (1 a 40)               ║
 * ║  └── stopSequences: strings que encerram a geração               ║
 * ║                                                                   ║
 * ║  📊 RATE LIMITS (Tier Gratuito):                                  ║
 * ║  ├── gemini-2.0-flash: 15 RPM, 1M TPM, 1.500 RPD                ║
 * ║  ├── gemini-1.5-pro:   2 RPM, 32K TPM, 50 RPD                   ║
 * ║  └── RPM = Requests/min, TPM = Tokens/min, RPD = Requests/dia   ║
 * ║                                                                   ║
 * ╚═══════════════════════════════════════════════════════════════════╝
 */
```

### Exemplo: Cache de Respostas

```php
<?php
// src/Gemini/CachedGeminiClient.php

declare(strict_types=1);

namespace App\Gemini;

/**
 * Decorator que adiciona cache ao GeminiClient.
 *
 * Evita chamadas repetidas à API para o mesmo prompt,
 * economizando quota e melhorando tempo de resposta.
 */
final class CachedGeminiClient
{
    private const string CACHE_DIR = __DIR__ . '/../../storage/gemini_cache';

    public function __construct(
        private readonly GeminiClient $client,
        private readonly int $ttlSeconds = 3_600, // 1 hora padrão
    ) {
        if (!is_dir(self::CACHE_DIR)) {
            mkdir(self::CACHE_DIR, 0o755, recursive: true);
        }
    }

    /**
     * Gerar texto com cache.
     *
     * Se o mesmo prompt foi feito recentemente (dentro do TTL),
     * retorna a resposta cacheada sem chamar a API.
     */
    #[\NoDiscard]
    public function generateText(string $prompt): string
    {
        $cacheKey  = hash('xxh128', $prompt);
        $cacheFile = self::CACHE_DIR . "/{$cacheKey}.json";

        // Verificar cache
        if (file_exists($cacheFile)) {
            $cached = json_decode(
                file_get_contents($cacheFile),
                associative: true,
                flags: JSON_THROW_ON_ERROR,
            );

            // Verificar se não expirou
            if ($cached['expires_at'] > time()) {
                return $cached['response'];
            }

            // Expirou — remover
            unlink($cacheFile);
        }

        // Sem cache — chamar API
        $response = $this->client->generateText($prompt);

        // Salvar no cache
        file_put_contents(
            $cacheFile,
            json_encode([
                'prompt'     => $prompt,
                'response'   => $response,
                'created_at' => time(),
                'expires_at' => time() + $this->ttlSeconds,
            ], JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE),
            flags: LOCK_EX,
        );

        return $response;
    }
}
```

---

## 📝 Exercícios — Gemini API

```php
<?php

declare(strict_types=1);

/**
 * ══════════════════════════════════════════════════════════════
 * EXERCÍCIOS — Integração Gemini API com PHP 8.5
 * ══════════════════════════════════════════════════════════════
 *
 * INICIANTE (⭐):
 * ──────────────
 *
 *  1. Crie um script que recebe uma pergunta como argumento CLI
 *     e exibe a resposta do Gemini. Exemplo:
 *     php ask.php "O que é programação orientada a objetos?"
 *
 *  2. Crie um tradutor automático que recebe texto em português
 *     e traduz para inglês, espanhol e francês simultaneamente.
 *
 *  3. Adicione o método `countTokens()` ao GeminiClient para
 *     estimar o número de tokens de um prompt antes de enviá-lo.
 *     (Dica: endpoint countTokens da API)
 *
 * INTERMEDIÁRIO (⭐⭐):
 * ─────────────────────
 *
 *  4. Crie um ContentModerator que analisa comentários de usuários
 *     e retorna: { safe: bool, reason: string, severity: 'low'|'medium'|'high' }
 *     usando JSON mode (responseType: 'application/json').
 *
 *  5. Implemente um gerador de testes unitários: dado o código-fonte
 *     de uma classe PHP, gere testes PHPUnit automaticamente.
 *
 *  6. Crie um endpoint REST (usando o que aprendemos no Cap. 36):
 *     POST /api/v1/ai/generate que recebe { prompt, temperature }
 *     e retorna a resposta do Gemini. Proteja com JWT e rate limiting.
 *
 * AVANÇADO (⭐⭐⭐):
 * ──────────────────
 *
 *  7. Implemente streaming de respostas usando Server-Sent Events (SSE)
 *     para exibir o texto do Gemini em tempo real no navegador.
 *     (Dica: endpoint streamGenerateContent e Transfer-Encoding: chunked)
 *
 *  8. Crie um sistema de RAG (Retrieval Augmented Generation):
 *     - Indexe documentos .md em um array de chunks
 *     - Dado uma pergunta, encontre os chunks mais relevantes (TF-IDF)
 *     - Envie o contexto + pergunta ao Gemini para resposta embasada
 *
 *  9. Implemente function calling: registre funções PHP como "tools"
 *     disponíveis ao modelo e processe as chamadas automaticamente.
 *     Exemplo: buscar clima, consultar banco, enviar email.
 */
```

---

## Resumo — API do Gemini com PHP 8.5

```php
<?php

declare(strict_types=1);

/**
 * ╔═══════════════════════════════════════════════════════════════════╗
 * ║       RESUMO: GEMINI API + PHP 8.5 MODERNO                       ║
 * ╠═══════════════════════════════════════════════════════════════════╣
 * ║                                                                   ║
 * ║  ARQUITETURA:                                                     ║
 * ║  ├── GeminiModel enum → modelos tipados (Flash20, Flash25, Pro15)║
 * ║  ├── GeminiException → erros com httpCode e errorCode             ║
 * ║  ├── GeminiClient → geração de texto, chat, análise de imagem    ║
 * ║  ├── ChatBot → conversa multi-turn com histórico                  ║
 * ║  ├── ImageAnalyzer → OCR, categorização, alt text                ║
 * ║  ├── GeminiClientWithRetry → resiliência com exponential backoff ║
 * ║  └── CachedGeminiClient → cache em arquivo com TTL               ║
 * ║                                                                   ║
 * ║  API:                                                             ║
 * ║  ├── Endpoint: generativelanguage.googleapis.com/v1beta           ║
 * ║  ├── Autenticação: API Key via query parameter (?key=)           ║
 * ║  ├── Método: POST (generateContent)                               ║
 * ║  ├── Formato: JSON (contents → parts → text / inlineData)       ║
 * ║  └── Rate limits: 15 RPM / 1.500 RPD (tier gratuito)             ║
 * ║                                                                   ║
 * ║  FEATURES PHP 8.5 UTILIZADAS:                                     ║
 * ║  ├── declare(strict_types=1) em todos os arquivos                 ║
 * ║  ├── backed enum (GeminiModel: string)                            ║
 * ║  ├── readonly + constructor promotion                              ║
 * ║  ├── match expression para decisões                                ║
 * ║  ├── named arguments em todas as chamadas                         ║
 * ║  ├── #[\NoDiscard] para retornos obrigatórios                     ║
 * ║  ├── JSON_THROW_ON_ERROR em todo json_encode/decode               ║
 * ║  ├── Heredoc (<<<PROMPT) para prompts multi-linha                ║
 * ║  ├── first-class callables (fn(): string => ...)                  ║
 * ║  ├── arrow functions com array_map                                 ║
 * ║  ├── ?? throw (null coalesce + throw expression)                  ║
 * ║  └── curl_setopt_array com named parameters                       ║
 * ║                                                                   ║
 * ║  BOAS PRÁTICAS:                                                   ║
 * ║  ├── API Key em .env (nunca hardcoded)                            ║
 * ║  ├── Exceções específicas (GeminiException)                       ║
 * ║  ├── Retry com exponential backoff + jitter                       ║
 * ║  ├── Cache para prompts repetidos                                  ║
 * ║  ├── Validação de MIME type para imagens                          ║
 * ║  └── Separação de responsabilidades (SRP)                         ║
 * ║                                                                   ║
 * ╚═══════════════════════════════════════════════════════════════════╝
 */
```

---

**Capítulo 36 + Bônus completos!** 🎉

Agora você domina tanto a criação de APIs REST profissionais com PHP 8.5 quanto a integração com a API do Gemini — desde requisições simples até chat interativo, análise de imagens, retry automático e cache. Com essas ferramentas, você pode construir aplicações inteligentes e escaláveis! 🚀


---

# Gemini API Professional Manual

> **Note:** This manual is a consolidated and structured version of the official Gemini API documentation.

---

# Part 1: Introduction

## 1. Welcome to Gemini 3

### Gemini 3 Developer Guide

Gemini 3 is our most intelligent model family to date, built on a foundation of state-of-the-art reasoning. It is designed to bring any idea to life by mastering agentic workflows, autonomous coding, and complex multimodal tasks. This guide covers key features of the Gemini 3 model family and how to get the most out of it.
[Try Gemini 3 Pro](https://aistudio.google.com/?model=gemini-3-pro-preview) [Try Gemini 3 Flash](https://aistudio.google.com/?model=gemini-3-flash-preview) [Try Nano Banana Pro](https://aistudio.google.com/?model=gemini-3-pro-image-preview)

Explore our [collection of Gemini 3 apps](https://aistudio.google.com/app/apps?source=showcase&showcaseTag=gemini-3) to see how the model handles advanced reasoning, autonomous coding, and complex multimodal tasks.

Get started with a few lines of code:

```python
from google import genai

client = genai.Client()

response = client.models.generate_content(
    model="gemini-3-pro-preview",
    contents="Find the race condition in this multi-threaded C++ snippet: [code here]",
)

print(response.text)
```

```javascript
import { GoogleGenAI } from "@google/genai";

const ai = new GoogleGenAI({});

async function run() {
  const response = await ai.models.generateContent({
    model: "gemini-3-pro-preview",
    contents: "Find the race condition in this multi-threaded C++ snippet: [code here]",
  });

  console.log(response.text);
}

run();
```

```bash
curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-3-pro-preview:generateContent" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -H 'Content-Type: application/json' \
  -X POST \
  -d '{
    "contents": [{
      "parts": [{"text": "Find the race condition in this multi-threaded C++ snippet: [code here]"}]
    }]
  }'
```

#### Meet the Gemini 3 series

Gemini 3 Pro, the first model in the new series, is best for complex tasks that require broad world knowledge and advanced reasoning across modalities.

Gemini 3 Flash is our latest 3-series model, with Pro-level intelligence at the speed and pricing of Flash.

Nano Banana Pro (also known as Gemini 3 Pro Image) is our highest quality image generation model yet.

All Gemini 3 models are currently in preview.

| Model ID                   | Context Window (In / Out) | Knowledge Cutoff | Pricing (Input / Output)*                         |
| -------------------------- | ------------------------- | ---------------- | ------------------------------------------------- |
| gemini-3-pro-preview       | 1M / 64k                  | Jan 2025         | $2 / $12 (<200k tokens) — $4 / $18 (>200k tokens) |
| gemini-3-flash-preview     | 1M / 64k                  | Jan 2025         | $0.50 / $3                                        |
| gemini-3-pro-image-preview | 65k / 32k                 | Jan 2025         | $2 (Text Input) / $0.134 (Image Output)**         |

\* Pricing is per 1 million tokens unless otherwise noted. \*\* Image pricing varies by resolution. See the [pricing page](https://ai.google.dev/gemini-api/docs/pricing) for details.

For detailed limits, pricing, and additional information, see the [models page](https://ai.google.dev/gemini-api/docs/models/gemini).

#### New API features in Gemini 3

Gemini 3 introduces new parameters designed to give developers more control over latency, cost, and multimodal fidelity.

##### Thinking level

Gemini 3 series models use dynamic thinking by default to reason through prompts. You can use the `thinking_level` parameter, which controls the maximum depth of the model's internal reasoning process before it produces a response. Gemini 3 treats these levels as relative allowances for thinking rather than strict token guarantees.

If `thinking_level` is not specified, Gemini 3 will default to `high`. For faster, lower-latency responses when complex reasoning isn't required, you can constrain the model's thinking level to `low`.

**Gemini 3 Pro and Flash thinking levels:**

The following thinking levels are supported by both Gemini 3 Pro and Flash:

- `low`: Minimizes latency and cost. Best for simple instruction following, chat, or high-throughput applications
- `high` (Default, dynamic): Maximizes reasoning depth. The model may take significantly longer to reach a first token, but the output will be more carefully reasoned.

**Gemini 3 Flash thinking levels:**

In addition to the levels above, Gemini 3 Flash also supports the following thinking levels that are not currently supported by Gemini 3 Pro:

- `minimal`: Matches the "no thinking" setting for most queries. The model may think very minimally for complex coding tasks. Minimizes latency for chat or high throughput applications.

> **Note:** Circulation of [thought signatures](https://ai.google.dev/gemini-api/docs/thought-signatures) is required even when thinking level is set to `minimal` for Gemini 3 Flash.

- `medium`: Balanced thinking for most tasks.

```python
from google import genai
from google.genai import types

client = genai.Client()

response = client.models.generate_content(
    model="gemini-3-pro-preview",
    contents="How does AI work?",
    config=types.GenerateContentConfig(
        thinking_config=types.ThinkingConfig(thinking_level="low")
    ),
)

print(response.text)
```

```javascript
import { GoogleGenAI } from "@google/genai";

const ai = new GoogleGenAI({});

const response = await ai.models.generateContent({
    model: "gemini-3-pro-preview",
    contents: "How does AI work?",
    config: {
      thinkingConfig: {
        thinkingLevel: "low",
      }
    },
  });

console.log(response.text);
```

```bash
curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-3-pro-preview:generateContent" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -H 'Content-Type: application/json' \
  -X POST \
  -d '{
    "contents": [{
      "parts": [{"text": "How does AI work?"}]
    }],
    "generationConfig": {
      "thinkingConfig": {
        "thinkingLevel": "low"
      }
    }
  }'
```

> **Important:** You cannot use both `thinking_level` and the legacy `thinking_budget` parameter in the same request. Doing so will return a 400 error.

##### Media resolution

Gemini 3 introduces granular control over multimodal vision processing via the `media_resolution` parameter. Higher resolutions improve the model's ability to read fine text or identify small details, but increase token usage and latency. The `media_resolution` parameter determines the maximum number of tokens allocated per input image or video frame.

You can now set the resolution to `media_resolution_low`, `media_resolution_medium`, `media_resolution_high`, or `media_resolution_ultra_high` per individual media part or globally (via `generation_config`, global not available for ultra high). If unspecified, the model uses optimal defaults based on the media type.

**Recommended settings:**

| Media Type         | Recommended Setting                               | Max Tokens      | Usage Guidance                                                                                                                                                                |
| ------------------ | ------------------------------------------------- | --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Images             | media_resolution_high                             | 1120            | Recommended for most image analysis tasks to ensure maximum quality.                                                                                                          |
| PDFs               | media_resolution_medium                           | 560             | Optimal for document understanding; quality typically saturates at medium. Increasing to high rarely improves OCR results for standard documents.                             |
| Video (General)    | media_resolution_low (or media_resolution_medium) | 70 (per frame)  | Note: For video, low and medium settings are treated identically (70 tokens) to optimize context usage. This is sufficient for most action recognition and description tasks. |
| Video (Text-heavy) | media_resolution_high                             | 280 (per frame) | Required only when the use case involves reading dense text (OCR) or small details within video frames.                                                                       |

> **Note:** The `media_resolution` parameter maps to different token counts depending on the input type. While images scale linearly (`media_resolution_low`: 280, `media_resolution_medium`: 560, `media_resolution_high`: 1120), Video is compressed more aggressively. For Video, both `media_resolution_low` and `media_resolution_medium` are capped at 70 tokens per frame, and `media_resolution_high` is capped at 280 tokens. See full details [here](https://ai.google.dev/gemini-api/docs/media-resolution#token-counts).

```python
from google import genai
from google.genai import types
import base64

# The media_resolution parameter is currently only available in the v1alpha API version.
client = genai.Client(http_options={'api_version': 'v1alpha'})

response = client.models.generate_content(
    model="gemini-3-pro-preview",
    contents=[
        types.Content(
            parts=[
                types.Part(text="What is in this image?"),
                types.Part(
                    inline_data=types.Blob(
                        mime_type="image/jpeg",
                        data=base64.b64decode("..."),
                    ),
                    media_resolution={"level": "media_resolution_high"}
                )
            ]
        )
    ]
)

print(response.text)
```

```javascript
import { GoogleGenAI } from "@google/genai";

// The media_resolution parameter is currently only available in the v1alpha API version.
const ai = new GoogleGenAI({ apiVersion: "v1alpha" });

async function run() {
  const response = await ai.models.generateContent({
    model: "gemini-3-pro-preview",
    contents: [
      {
        parts: [
          { text: "What is in this image?" },
          {
            inlineData: {
              mimeType: "image/jpeg",
              data: "...",
            },
            mediaResolution: {
              level: "media_resolution_high"
            }
          }
        ]
      }
    ]
  });

  console.log(response.text);
}

run();
```

```bash
curl "https://generativelanguage.googleapis.com/v1alpha/models/gemini-3-pro-preview:generateContent" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -H 'Content-Type: application/json' \
  -X POST \
  -d '{
    "contents": [{
      "parts": [
        { "text": "What is in this image?" },
        {
          "inlineData": {
            "mimeType": "image/jpeg",
            "data": "..."
          },
          "mediaResolution": {
            "level": "media_resolution_high"
          }
        }
      ]
    }]
  }'
```

##### Temperature

For Gemini 3, we strongly recommend keeping the temperature parameter at its default value of `1.0`.

While previous models often benefited from tuning temperature to control creativity versus determinism, Gemini 3's reasoning capabilities are optimized for the default setting. Changing the temperature (setting it below 1.0) may lead to unexpected behavior, such as looping or degraded performance, particularly in complex mathematical or reasoning tasks.

##### Thought signatures

Gemini 3 uses [Thought signatures](https://ai.google.dev/gemini-api/docs/thought-signatures) to maintain reasoning context across API calls. These signatures are encrypted representations of the model's internal thought process. To ensure the model maintains its reasoning capabilities you must return these signatures back to the model in your request exactly as they were received:

- **Function Calling (Strict):** The API enforces strict validation on the "Current Turn". Missing signatures will result in a 400 error.

> **Note:** Circulation of thought signatures is required even when [thinking level](https://ai.google.dev/gemini-api/docs/gemini-3#thinking_level) is set to `minimal` for Gemini 3 Flash.

- **Text/Chat:** Validation is not strictly enforced, but omitting signatures will degrade the model's reasoning and answer quality.

- **Image generation/editing (Strict):** The API enforces strict validation on all Model parts including a `thoughtSignature`. Missing signatures will result in a 400 error.

> **Success:** If you use the [official SDKs (Python, Node, Java)](https://ai.google.dev/gemini-api/docs/function-calling?example=meeting#thinking) and standard chat history, Thought Signatures are handled automatically. You do not need to manually manage these fields.

###### Function calling (strict validation)

When Gemini generates a `functionCall`, it relies on the `thoughtSignature` to process the tool's output correctly in the next turn. The "Current Turn" includes all Model (`functionCall`) and User (`functionResponse`) steps that occurred since the last standard User `text` message.

- **Single Function Call:** The `functionCall` part contains a signature. You must return it.
- **Parallel Function Calls:** Only the first `functionCall` part in the list will contain the signature. You must return the parts in the exact order received.
- **Multi-Step (Sequential):** If the model calls a tool, receives a result, and calls another tool (within the same turn), both function calls have signatures. You must return all accumulated signatures in the history.

###### Text and streaming

For standard chat or text generation, the presence of a signature is not guaranteed.

- **Non-Streaming:** The final content part of the response may contain a `thoughtSignature`, though it is not always present. If one is returned, you should send it back to maintain best performance.
- **Streaming:** If a signature is generated, it may arrive in a final chunk that contains an empty text part. Ensure your stream parser checks for signatures even if the text field is empty.

###### Image generation and editing

For `gemini-3-pro-image-preview`, thought signatures are critical for conversational editing. When you ask the model to modify an image it relies on the `thoughtSignature` from the previous turn to understand the composition and logic of the original image.

- **Editing:** Signatures are guaranteed on the first part after the thoughts of the response (`text` or `inlineData`) and on every subsequent `inlineData` part. You must return all of these signatures to avoid errors.

###### Code examples

**Multi-step Function Calling (Sequential)**

The user asks a question requiring two separate steps (Check Flight -> Book Taxi) in one turn.

Step 1: Model calls Flight Tool. The model returns a signature `<Sig_A>`:

```json
// Model Response (Turn 1, Step 1)
{
  "role": "model",
  "parts": [
    {
      "functionCall": { "name": "check_flight", "args": {...} },
      "thoughtSignature": "<Sig_A>" // SAVE THIS
    }
  ]
}
```

Step 2: User sends Flight Result. We must send back `<Sig_A>` to keep the model's train of thought:

```json
// User Request (Turn 1, Step 2)
[
  { "role": "user", "parts": [{ "text": "Check flight AA100..." }] },
  {
    "role": "model",
    "parts": [
      {
        "functionCall": { "name": "check_flight", "args": {...} },
        "thoughtSignature": "<Sig_A>" // REQUIRED
      }
    ]
  },
  { "role": "user", "parts": [{ "functionResponse": { "name": "check_flight", "response": {...} } }] }
]
```

Step 3: Model calls Taxi Tool. The model remembers the flight delay via `<Sig_A>` and now decides to book a taxi. It generates a new signature `<Sig_B>`:

```json
// Model Response (Turn 1, Step 3)
{
  "role": "model",
  "parts": [
    {
      "functionCall": { "name": "book_taxi", "args": {...} },
      "thoughtSignature": "<Sig_B>" // SAVE THIS
    }
  ]
}
```

Step 4: User sends Taxi Result. To complete the turn, you must send back the entire chain: `<Sig_A>` AND `<Sig_B>`:

```json
// User Request (Turn 1, Step 4)
[
  // ... previous history ...
  {
    "role": "model",
    "parts": [
       { "functionCall": { "name": "check_flight", ... }, "thoughtSignature": "<Sig_A>" }
    ]
  },
  { "role": "user", "parts": [{ "functionResponse": {...} }] },
  {
    "role": "model",
    "parts": [
       { "functionCall": { "name": "book_taxi", ... }, "thoughtSignature": "<Sig_B>" }
    ]
  },
  { "role": "user", "parts": [{ "functionResponse": {...} }] }
]
```

**Parallel Function Calling**

The user asks: "Check the weather in Paris and London." The model returns two function calls in one response:

```json
// User Request (Sending Parallel Results)
[
  {
    "role": "user",
    "parts": [
      { "text": "Check the weather in Paris and London." }
    ]
  },
  {
    "role": "model",
    "parts": [
      // 1. First Function Call has the signature
      {
        "functionCall": { "name": "check_weather", "args": { "city": "Paris" } },
        "thoughtSignature": "<Signature_A>"
      },
      // 2. Subsequent parallel calls DO NOT have signatures
      {
        "functionCall": { "name": "check_weather", "args": { "city": "London" } }
      }
    ]
  },
  {
    "role": "user",
    "parts": [
      // 3. Function Responses are grouped together in the next block
      {
        "functionResponse": { "name": "check_weather", "response": { "temp": "15C" } }
      },
      {
        "functionResponse": { "name": "check_weather", "response": { "temp": "12C" } }
      }
    ]
  }
]
```

**Text/In-Context Reasoning (No Validation)**

The user asks a question that requires in-context reasoning without external tools. While not strictly validated, including the signature helps the model maintain the reasoning chain for follow-up questions:

```json
// User Request (Follow-up question)
[
  {
    "role": "user",
    "parts": [{ "text": "What are the risks of this investment?" }]
  },
  {
    "role": "model",
    "parts": [
      {
        "text": "I need to calculate the risk step-by-step. First, I'll look at volatility...",
        "thoughtSignature": "<Signature_C>" // Recommended to include
      }
    ]
  },
  {
    "role": "user",
    "parts": [{ "text": "Summarize that in one sentence." }]
  }
]
```

**Image Generation & Editing**

For image generation, signatures are strictly validated. They appear on the first part (text or image) and all subsequent image parts. All must be returned in the next turn:

```json
// Model Response (Turn 1)
{
  "role": "model",
  "parts": [
    // 1. First part ALWAYS has a signature (even if text)
    {
      "text": "I will generate a cyberpunk city...",
      "thoughtSignature": "<Signature_D>"
    },
    // 2. ALL InlineData (Image) parts ALWAYS have signatures
    {
      "inlineData": { ... },
      "thoughtSignature": "<Signature_E>"
    }
  ]
}

// User Request (Turn 2 - Requesting an Edit)
{
  "contents": [
    // History must include ALL signatures received
    {
      "role": "user",
      "parts": [{ "text": "Generate a cyberpunk city" }]
    },
    {
      "role": "model",
      "parts": [
         { "text": "...", "thoughtSignature": "<Signature_D>" },
         { "inlineData": "...", "thoughtSignature": "<Signature_E>" }
      ]
    },
    // New User Prompt
    {
      "role": "user",
      "parts": [{ "text": "Make it daytime." }]
    }
  ]
}
```

###### Migrating from other models

If you are transferring a conversation trace from another model (e.g., Gemini 2.5) or injecting a custom function call that was not generated by Gemini 3, you will not have a valid signature.

To bypass strict validation in these specific scenarios, populate the field with this specific dummy string:

```json
"thoughtSignature": "context_engineering_is_the_way_to_go"
```

##### Structured Outputs with tools

Gemini 3 models allow you to combine [Structured Outputs](https://ai.google.dev/gemini-api/docs/structured-output) with built-in tools, including [Grounding with Google Search](https://ai.google.dev/gemini-api/docs/google-search), [URL Context](https://ai.google.dev/gemini-api/docs/url-context), [Code Execution](https://ai.google.dev/gemini-api/docs/code-execution), and [Function Calling](https://ai.google.dev/gemini-api/docs/function-calling).

```python
from google import genai
from google.genai import types
from pydantic import BaseModel, Field
from typing import List

class MatchResult(BaseModel):
    winner: str = Field(description="The name of the winner.")
    final_match_score: str = Field(description="The final match score.")
    scorers: List[str] = Field(description="The name of the scorer.")

client = genai.Client()

response = client.models.generate_content(
    model="gemini-3-pro-preview",
    contents="Search for all details for the latest Euro.",
    config={
        "tools": [
            {"google_search": {}},
            {"url_context": {}}
        ],
        "response_mime_type": "application/json",
        "response_json_schema": MatchResult.model_json_schema(),
    },
)

result = MatchResult.model_validate_json(response.text)
print(result)
```

```javascript
import { GoogleGenAI } from "@google/genai";
import { z } from "zod";
import { zodToJsonSchema } from "zod-to-json-schema";

const ai = new GoogleGenAI({});

const matchSchema = z.object({
  winner: z.string().describe("The name of the winner."),
  final_match_score: z.string().describe("The final score."),
  scorers: z.array(z.string()).describe("The name of the scorer.")
});

async function run() {
  const response = await ai.models.generateContent({
    model: "gemini-3-pro-preview",
    contents: "Search for all details for the latest Euro.",
    config: {
      tools: [
        { googleSearch: {} },
        { urlContext: {} }
      ],
      responseMimeType: "application/json",
      responseJsonSchema: zodToJsonSchema(matchSchema),
    },
  });

  const match = matchSchema.parse(JSON.parse(response.text));
  console.log(match);
}

run();
```

```bash
curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-3-pro-preview:generateContent" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -H 'Content-Type: application/json' \
  -X POST \
  -d '{
    "contents": [{
      "parts": [{"text": "Search for all details for the latest Euro."}]
    }],
    "tools": [
      {"googleSearch": {}},
      {"urlContext": {}}
    ],
    "generationConfig": {
        "responseMimeType": "application/json",
        "responseJsonSchema": {
            "type": "object",
            "properties": {
                "winner": {"type": "string", "description": "The name of the winner."},
                "final_match_score": {"type": "string", "description": "The final score."},
                "scorers": {
                    "type": "array",
                    "items": {"type": "string"},
                    "description": "The name of the scorer."
                }
            },
            "required": ["winner", "final_match_score", "scorers"]
        }
    }
  }'
```

##### Image generation

Gemini 3 Pro Image lets you generate and edit images from text prompts. It uses reasoning to "think" through a prompt and can retrieve real-time data—such as weather forecasts or stock charts—before using [Google Search](https://ai.google.dev/gemini-api/docs/google-search) grounding before generating high-fidelity images.

**New & improved capabilities:**

- **4K & text rendering:** Generate sharp, legible text and diagrams with up to 2K and 4K resolutions.
- **Grounded generation:** Use the `google_search` tool to verify facts and generate imagery based on real-world information.
- **Conversational editing:** Multi-turn image editing by simply asking for changes (e.g., "Make the background a sunset"). This workflow relies on Thought Signatures to preserve visual context between turns.

For complete details on aspect ratios, editing workflows, and configuration options, see the [Image Generation guide](https://ai.google.dev/gemini-api/docs/image-generation).

```python
from google import genai
from google.genai import types

client = genai.Client()

response = client.models.generate_content(
    model="gemini-3-pro-image-preview",
    contents="Generate an infographic of the current weather in Tokyo.",
    config=types.GenerateContentConfig(
        tools=[{"google_search": {}}],
        image_config=types.ImageConfig(
            aspect_ratio="16:9",
            image_size="4K"
        )
    )
)

image_parts = [part for part in response.parts if part.inline_data]

if image_parts:
    image = image_parts[0].as_image()
    image.save('weather_tokyo.png')
    image.show()
```

```javascript
import { GoogleGenAI } from "@google/genai";
import * as fs from "node:fs";

const ai = new GoogleGenAI({});

async function run() {
  const response = await ai.models.generateContent({
    model: "gemini-3-pro-image-preview",
    contents: "Generate a visualization of the current weather in Tokyo.",
    config: {
      tools: [{ googleSearch: {} }],
      imageConfig: {
        aspectRatio: "16:9",
        imageSize: "4K"
      }
    }
  });

  for (const part of response.candidates[0].content.parts) {
    if (part.inlineData) {
      const imageData = part.inlineData.data;
      const buffer = Buffer.from(imageData, "base64");
      fs.writeFileSync("weather_tokyo.png", buffer);
    }
  }
}

run();
```

```bash
curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-3-pro-image-preview:generateContent" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -H 'Content-Type: application/json' \
  -X POST \
  -d '{
    "contents": [{
      "parts": [{"text": "Generate a visualization of the current weather in Tokyo."}]
    }],
    "tools": [{"googleSearch": {}}],
    "generationConfig": {
        "imageConfig": {
          "aspectRatio": "16:9",
          "imageSize": "4K"
      }
    }
  }'
```

##### Code Execution with images

Gemini 3 Flash can treat vision as an active investigation, not just a static glance. By combining reasoning with [code execution](https://ai.google.dev/gemini-api/docs/code-execution), the model formulates a plan, then writes and executes Python code to zoom in, crop, annotate, or otherwise manipulate images step-by-step to visually ground its answers.

**Use cases:**

- **Zoom and inspect:** The model implicitly detects when details are too small (e.g., reading a distant gauge or serial number) and writes code to crop and re-examine the area at higher resolution.
- **Visual math and plotting:** The model can run multi-step calculations using code (e.g., summing line items on a receipt, or generating a Matplotlib chart from extracted data).
- **Image annotation:** The model can draw arrows, bounding boxes, or other annotations directly onto images to answer spatial questions like "Where should this item go?".

To enable visual thinking, configure [Code Execution](https://ai.google.dev/gemini-api/docs/code-execution) as a tool. The model will automatically use code to manipulate images when needed.

```python
from google import genai
from google.genai import types
import requests
from PIL import Image
import io

image_path = "https://goo.gle/instrument-img"
image_bytes = requests.get(image_path).content
image = types.Part.from_bytes(data=image_bytes, mime_type="image/jpeg")

client = genai.Client()

response = client.models.generate_content(
    model="gemini-3-flash-preview",
    contents=[
        image,
        "Zoom into the expression pedals and tell me how many pedals are there?"
    ],
    config=types.GenerateContentConfig(
        tools=[types.Tool(code_execution=types.ToolCodeExecution)]
    ),
)

for part in response.candidates[0].content.parts:
    if part.text is not None:
        print(part.text)
    if part.executable_code is not None:
        print(part.executable_code.code)
    if part.code_execution_result is not None:
        print(part.code_execution_result.output)
    if part.as_image() is not None:
        display(Image.open(io.BytesIO(part.as_image().image_bytes)))
```

```javascript
import { GoogleGenAI } from "@google/genai";

const ai = new GoogleGenAI({});

async function main() {
  const imageUrl = "https://goo.gle/instrument-img";
  const response = await fetch(imageUrl);
  const imageArrayBuffer = await response.arrayBuffer();
  const base64ImageData = Buffer.from(imageArrayBuffer).toString("base64");

  const result = await ai.models.generateContent({
    model: "gemini-3-flash-preview",
    contents: [
      {
        inlineData: {
          mimeType: "image/jpeg",
          data: base64ImageData,
        },
      },
      {
        text: "Zoom into the expression pedals and tell me how many pedals are there?",
      },
    ],
    config: {
      tools: [{ codeExecution: {} }],
    },
  });

  for (const part of result.candidates[0].content.parts) {
    if (part.text) {
      console.log("Text:", part.text);
    }
    if (part.executableCode) {
      console.log("Code:", part.executableCode.code);
    }
    if (part.codeExecutionResult) {
      console.log("Output:", part.codeExecutionResult.output);
    }
  }
}

main();
```

```bash
IMG_URL="https://goo.gle/instrument-img"
MODEL="gemini-3-flash-preview"

MIME_TYPE=$(curl -sIL "$IMG_URL" | grep -i '^content-type:' | awk -F ': ' '{print $2}' | sed 's/\r$//' | head -n 1)
if [[ -z "$MIME_TYPE" || ! "$MIME_TYPE" == image/* ]]; then
  MIME_TYPE="image/jpeg"
fi

if [[ "$(uname)" == "Darwin" ]]; then
  IMAGE_B64=$(curl -sL "$IMG_URL" | base64 -b 0)
elif [[ "$(base64 --version 2>&1)" = *"FreeBSD"* ]]; then
  IMAGE_B64=$(curl -sL "$IMG_URL" | base64)
else
  IMAGE_B64=$(curl -sL "$IMG_URL" | base64 -w0)
fi

curl "https://generativelanguage.googleapis.com/v1beta/models/$MODEL:generateContent" \
    -H "x-goog-api-key: $GEMINI_API_KEY" \
    -H 'Content-Type: application/json' \
    -X POST \
    -d '{
      "contents": [{
        "parts":[
            {
              "inline_data": {
                "mime_type":"'"$MIME_TYPE"'",
                "data": "'"$IMAGE_B64"'"
              }
            },
            {"text": "Zoom into the expression pedals and tell me how many pedals are there?"}
        ]
      }],
      "tools": [{"code_execution": {}}]
    }'
```

For more details on code execution with images, see [Code Execution](https://ai.google.dev/gemini-api/docs/code-execution#images).

##### Multimodal function responses

[Multimodal function calling](https://ai.google.dev/gemini-api/docs/function-calling#multimodal) allows users to have function responses containing multimodal objects allowing for improved utilization of function calling capabilities of the model. Standard function calling only supports text-based function responses:

```python
from google import genai
from google.genai import types

import requests

client = genai.Client()

# This is a manual, two turn multimodal function calling workflow:

# 1. Define the function tool
get_image_declaration = types.FunctionDeclaration(
  name="get_image",
  description="Retrieves the image file reference for a specific order item.",
  parameters={
      "type": "object",
      "properties": {
          "item_name": {
              "type": "string",
              "description": "The name or description of the item ordered (e.g., 'instrument')."
          }
      },
      "required": ["item_name"],
  },
)
tool_config = types.Tool(function_declarations=[get_image_declaration])

# 2. Send a message that triggers the tool
prompt = "Show me the instrument I ordered last month."
response_1 = client.models.generate_content(
  model="gemini-3-flash-preview",
  contents=[prompt],
  config=types.GenerateContentConfig(
      tools=[tool_config],
  )
)

# 3. Handle the function call
function_call = response_1.function_calls[0]
requested_item = function_call.args["item_name"]
print(f"Model wants to call: {function_call.name}")

# Execute your tool (e.g., call an API)
# (This is a mock response for the example)
print(f"Calling external tool for: {requested_item}")

function_response_data = {
  "image_ref": {"$ref": "instrument.jpg"},
}
image_path = "https://goo.gle/instrument-img"
image_bytes = requests.get(image_path).content
function_response_multimodal_data = types.FunctionResponsePart(
  inline_data=types.FunctionResponseBlob(
    mime_type="image/jpeg",
    display_name="instrument.jpg",
    data=image_bytes,
  )
)

# 4. Send the tool's result back
# Append this turn's messages to history for a final response.
history = [
  types.Content(role="user", parts=[types.Part(text=prompt)]),
  response_1.candidates[0].content,
  types.Content(
    role="tool",
    parts=[
        types.Part.from_function_response(
          name=function_call.name,
          response=function_response_data,
          parts=[function_response_multimodal_data]
        )
    ],
  )
]

response_2 = client.models.generate_content(
  model="gemini-3-flash-preview",
  contents=history,
  config=types.GenerateContentConfig(
      tools=[tool_config],
      thinking_config=types.ThinkingConfig(include_thoughts=True)
  ),
)

print(f"\nFinal model response: {response_2.text}")
```

```javascript
import { GoogleGenAI, Type } from '@google/genai';

const client = new GoogleGenAI({ apiKey: process.env.GEMINI_API_KEY });

// This is a manual, two turn multimodal function calling workflow:
// 1. Define the function tool
const getImageDeclaration = {
  name: 'get_image',
  description: 'Retrieves the image file reference for a specific order item.',
  parameters: {
    type: Type.OBJECT,
    properties: {
      item_name: {
        type: Type.STRING,
        description: "The name or description of the item ordered (e.g., 'instrument').",
      },
    },
    required: ['item_name'],
  },
};

const toolConfig = {
  functionDeclarations: [getImageDeclaration],
};

// 2. Send a message that triggers the tool
const prompt = 'Show me the instrument I ordered last month.';
const response1 = await client.models.generateContent({
  model: 'gemini-3-flash-preview',
  contents: prompt,
  config: {
    tools: [toolConfig],
  },
});

// 3. Handle the function call
const functionCall = response1.functionCalls[0];
const requestedItem = functionCall.args.item_name;
console.log(`Model wants to call: ${functionCall.name}`);

// Execute your tool (e.g., call an API)
// (This is a mock response for the example)
console.log(`Calling external tool for: ${requestedItem}`);

const functionResponseData = {
  image_ref: { $ref: 'instrument.jpg' },
};

const imageUrl = "https://goo.gle/instrument-img";
const response = await fetch(imageUrl);
const imageArrayBuffer = await response.arrayBuffer();
const base64ImageData = Buffer.from(imageArrayBuffer).toString('base64');

const functionResponseMultimodalData = {
  inlineData: {
    mimeType: 'image/jpeg',
    displayName: 'instrument.jpg',
    data: base64ImageData,
  },
};

// 4. Send the tool's result back
// Append this turn's messages to history for a final response.
const history = [
  { role: 'user', parts: [{ text: prompt }] },
  response1.candidates[0].content,
  {
    role: 'tool',
    parts: [
      {
        functionResponse: {
          name: functionCall.name,
          response: functionResponseData,
          parts: [functionResponseMultimodalData],
        },
      },
    ],
  },
];

const response2 = await client.models.generateContent({
  model: 'gemini-3-flash-preview',
  contents: history,
  config: {
    tools: [toolConfig],
    thinkingConfig: { includeThoughts: true },
  },
});

console.log(`\nFinal model response: ${response2.text}`);
```

```bash
IMG_URL="https://goo.gle/instrument-img"

MIME_TYPE=$(curl -sIL "$IMG_URL" | grep -i '^content-type:' | awk -F ': ' '{print $2}' | sed 's/\r$//' | head -n 1)
if [[ -z "$MIME_TYPE" || ! "$MIME_TYPE" == image/* ]]; then
  MIME_TYPE="image/jpeg"
fi

# Check for macOS
if [[ "$(uname)" == "Darwin" ]]; then
  IMAGE_B64=$(curl -sL "$IMG_URL" | base64 -b 0)
elif [[ "$(base64 --version 2>&1)" = *"FreeBSD"* ]]; then
  IMAGE_B64=$(curl -sL "$IMG_URL" | base64)
else
  IMAGE_B64=$(curl -sL "$IMG_URL" | base64 -w0)
fi

curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -H 'Content-Type: application/json' \
  -X POST \
  -d '{
    "contents": [
      ...,
      {
        "role": "user",
        "parts": [
        {
            "functionResponse": {
              "name": "get_image",
              "response": {
                "image_ref": {
                  "$ref": "instrument.jpg"
                }
              },
              "parts": [
                {
                  "inlineData": {
                    "displayName": "instrument.jpg",
                    "mimeType":"'"$MIME_TYPE"'",
                    "data": "'"$IMAGE_B64"'"
                  }
                }
              ]
            }
          }
        ]
      }
    ]
  }'
```

#### Migrating from Gemini 2.5

Gemini 3 is our most capable model family to date and offers a stepwise improvement over Gemini 2.5. When migrating, consider the following:

- **Thinking:** If you were previously using complex prompt engineering (like chain of thought) to force Gemini 2.5 to reason, try Gemini 3 with `thinking_level: "high"` and simplified prompts.
- **Temperature settings:** If your existing code explicitly sets temperature (especially to low values for deterministic outputs), we recommend removing this parameter and using the Gemini 3 default of 1.0 to avoid potential looping issues or performance degradation on complex tasks.
- **PDF & document understanding:** Default OCR resolution for PDFs has changed. If you relied on specific behavior for dense document parsing, test the new `media_resolution_high` setting to ensure continued accuracy.
- **Token consumption:** Migrating to Gemini 3 defaults may increase token usage for PDFs but decrease token usage for video. If requests now exceed the context window due to higher default resolutions, we recommend explicitly reducing the media resolution.
- **Image segmentation:** Image segmentation capabilities (returning pixel-level masks for objects) are not supported in Gemini 3 Pro or Gemini 3 Flash. For workloads requiring native image segmentation, we recommend continuing to utilize Gemini 2.5 Flash with thinking turned off or [Gemini Robotics-ER 1.5](https://ai.google.dev/gemini-api/docs/robotics-overview).
- **Computer Use:** Gemini 3 Pro and Gemini 3 Flash support Computer Use. Unlike the 2.5 series, you don't need to use a separate model to access the Computer Use tool.
- **Tool support:** Maps grounding is not yet supported for Gemini 3 models, so won't migrate. Additionally, combining built-in tools with function calling is not yet supported.

#### OpenAI compatibility

For users utilizing the OpenAI compatibility layer, standard parameters are automatically mapped to Gemini equivalents:

- `reasoning_effort` (OAI) maps to `thinking_level` (Gemini). Note that `reasoning_effort` medium maps to `thinking_level` high on Gemini 3 Flash.

#### Prompting best practices

Gemini 3 is a reasoning model, which changes how you should prompt.

- **Precise instructions:** Be concise in your input prompts. Gemini 3 responds best to direct, clear instructions. It may over-analyze verbose or overly complex prompt engineering techniques used for older models.
- **Output verbosity:** By default, Gemini 3 is less verbose and prefers providing direct, efficient answers. If your use case requires a more conversational or "chatty" persona, you must explicitly steer the model in the prompt (e.g., "Explain this as a friendly, talkative assistant").
- **Context management:** When working with large datasets (e.g., entire books, codebases, or long videos), place your specific instructions or questions at the end of the prompt, after the data context. Anchor the model's reasoning to the provided data by starting your question with a phrase like, "Based on the information above...".

Learn more about prompt design strategies in the [prompt engineering guide](https://ai.google.dev/gemini-api/docs/prompting-strategies).

#### FAQ

- **What is the knowledge cutoff for Gemini 3?** Gemini 3 models have a knowledge cutoff of January 2025. For more recent information, use the [Search Grounding](https://ai.google.dev/gemini-api/docs/google-search) tool.

- **What are the context window limits?** Gemini 3 models support a 1 million token input context window and up to 64k tokens of output.

- **Is there a free tier for Gemini 3?** Gemini 3 Flash `gemini-3-flash-preview` has a free tier in the Gemini API. You can try both Gemini 3 Pro and Flash for free in Google AI Studio, but currently, there is no free tier available for `gemini-3-pro-preview` in the Gemini API.

- **Will my old `thinking_budget` code still work?** Yes, `thinking_budget` is still supported for backward compatibility, but we recommend migrating to `thinking_level` for more predictable performance. Do not use both in the same request.

- **Does Gemini 3 support the Batch API?** Yes, Gemini 3 supports the [Batch API](https://ai.google.dev/gemini-api/docs/batch-api).

- **Is Context Caching supported?** Yes, [Context Caching](https://ai.google.dev/gemini-api/docs/caching) is supported for Gemini 3.

- **Which tools are supported in Gemini 3?** Gemini 3 supports [Google Search](https://ai.google.dev/gemini-api/docs/google-search), [File Search](https://ai.google.dev/gemini-api/docs/file-search), [Code Execution](https://ai.google.dev/gemini-api/docs/code-execution), and [URL Context](https://ai.google.dev/gemini-api/docs/url-context). It also supports standard [Function Calling](https://ai.google.dev/gemini-api/docs/function-calling?example=meeting) for your own custom tools (but not with built-in tools). Please note that [Grounding with Google Maps](https://ai.google.dev/gemini-api/docs/maps-grounding) and [Computer Use](https://ai.google.dev/gemini-api/docs/computer-use) are currently not supported.

> **Note:** Gemini 3 billing for [Grounding with Google Search](https://ai.google.dev/gemini-api/docs/google-search) will begin on January 5, 2026.

#### Next steps

- Get started with the [Gemini 3 Cookbook](https://colab.research.google.com/github/google-gemini/cookbook/blob/main/quickstarts/Get_started.ipynb#templateParams=%7B%22MODEL_ID%22%3A+%22gemini-3-pro-preview%22%7D)
- Check the dedicated Cookbook guide on [thinking levels](https://colab.research.google.com/github/google-gemini/cookbook/blob/main/quickstarts/Get_started_thinking_REST.ipynb#gemini3) and how to migrate from thinking budget to thinking levels.

---
---
data_documento: "2026-02-20"
contexto: "rag"
tecnologia: "php 8.5"
api: "gemini 3"
modelo_ia: "claude-opus-4-6"
tags: ["rag", "php8.5", "gemini-api", "claude-opus-4-6", "sdk", "chatbot"]
---

# Gemini 3 API — PHP 8.5 SDK Integration Guide

> **Data:** 2026-02-20
> **PHP:** 8.5 | **API:** Gemini 3 (Pro / Flash / Image)
> Todos os exemplos seguem `declare(strict_types=1)` e tipagem rigorosa.

---

## Sumário

### Parte I — Integração com API Gemini 3

1. [Conexão Otimizada com cURL Persistente (PHP 8.5)](#1-conexão-otimizada-com-curl-persistente-php-85)
2. [Autenticação 2FA com Análise de Risco Gemini 3](#2-autenticação-2fa-com-análise-de-risco-gemini-3)
3. [Geração de Senhas com Gemini 3 Flash](#3-geração-de-senhas-com-gemini-3-flash)
4. [Detecção de Fraude em Documentos com Code Execution](#4-detecção-de-fraude-em-documentos-com-code-execution)
5. [Segurança PHP 8.5 no Contexto de APIs Gemini](#5-segurança-php-85-no-contexto-de-apis-gemini)

### Parte II — Projeto Prático: Chatbot com Gemini Pro

51. [Projeto Prático — Sistema Completo de Chatbot com Gemini Pro](#51-projeto-prático--sistema-completo-de-chatbot-com-gemini-pro)

### Parte III — Cliente HTTP para Gemini

98. [Integração Gemini API com cURL](#98-integração-gemini-api-com-curl)

---

## 1. Conexão Otimizada com cURL Persistente (PHP 8.5)

O PHP 8.5 introduz `curl_share_init_persistent()`, que muda fundamentalmente como comunicamos com APIs externas como a do Gemini 3 em ambientes de alta concorrência. Este capítulo explora o problema de latência em conexões repetidas, a solução com handles persistentes e a sinergia com o Gemini 3 Flash.

### 1.1 O Problema Anterior

Antes do PHP 8.5, cada execução de script refazia toda a negociação de conexão (DNS → TCP → SSL/TLS). Para payloads grandes como imagens Base64 enviadas ao Gemini, isso adicionava latência significativa:

### 1.2 A Solução no PHP 8.5

A nova função `curl_share_init_persistent()` mantém os handles compartilhados vivos na memória do processo do servidor (como o PHP-FPM) entre requisições diferentes.

**Como funciona:**

1.  **Identificação:** Você fornece um identificador único (ex: `"gemini_shared_handle"`).
2.  **Busca ou Criação:** O PHP verifica se já existe um handle ativo com esse ID e mesmas opções.
    *   Se existir: Reutiliza a conexão imediatamente.
    *   Se não existir: Cria uma nova e a mantém viva.
3.  **Economia:** Elimina o custo de renegociar SSL/TLS a cada requisição.

### 1.3 Integração com Gemini 3

Essa melhoria é vital para o Gemini 3, pois a API exige que imagens e mídia sejam enviados como strings Base64 dentro do campo `inlineData`.

*   **Fluxo Otimizado:** O túnel seguro permanece aberto, permitindo "rajadas" de envios de imagens sem overhead de conexão.

### 1.4 Sinergia Flash + cURL Persistente

Ao combinar o **Gemini 3 Flash** (configurado com `thinking_level: "minimal"`) com `curl_share_init_persistent`, você elimina quase toda a latência de rede e processamento, criando um sistema "invisível" para o usuário.

---

## 2. Autenticação 2FA com Análise de Risco Gemini 3

Este capítulo demonstra como o Gemini 3 Flash pode analisar metadados de login (IP, User-Agent, horário) e decidir em tempo real se exige verificação 2FA. A extensão URI do PHP 8.5 garante que os redirecionamentos pós-login não sejam exploráveis.

### 2.1 SafeRedirect com Extensão URI (PHP 8.5)

Ao integrar 2FA acionado pelo Gemini, é crucial validar URLs de redirecionamento para evitar Open Redirect. A classe usa `Uri\URL` (WHATWG) para parsing rigoroso:

```php
<?php

declare(strict_types=1);

namespace App\Security;

use URI\URL;
use URI\URIException;

class SafeRedirect
{
    private const ALLOWED_HOSTS = ['meusite.com', 'app.meusite.com', 'localhost'];

    public static function validate(string $url, string $default = '/dashboard'): string
    {
        try {
            // PHP 8.5: Parsing rigoroso conforme RFC 3986 e WHATWG URL
            $uri = new URL($url);

            $host = $uri->getHost();

            // Se tem host, DEVE estar na lista permitida
            if ($host !== null && !in_array($host, self::ALLOWED_HOSTS, true)) {
                return $default;
            }

            // Garante protocolo seguro
            if ($uri->getScheme() !== null && $uri->getScheme() !== 'https') {
                if ($host !== 'localhost') {
                    return $default;
                }
            }

            return (string) $uri;

        } catch (URIException $e) {
            return $default;
        }
    }
}
```

### 2.2 Controller de Login com Gemini + SafeRedirect

O `match` expression orquestra 3 fluxos: sucesso direto, 2FA obrigatório (risco alto) e falha:

```php
<?php

declare(strict_types=1);

use App\Auth\Authenticator;
use App\Auth\LoginStatus;
use App\Security\SafeRedirect;

// Tenta logar
$status = $authenticator->login($email, $password, $metaData);
$targetUrl = $_GET['redirect'] ?? '/dashboard';

match ($status) {
    LoginStatus::SUCCESS => ((function () use ($targetUrl) {
        // Risco Baixo: Valida URL e redireciona
        $safeUrl = SafeRedirect::validate($targetUrl);
        header("Location: $safeUrl");
        exit;
    })()),

    LoginStatus::REQUIRE_2FA => ((function () use ($targetUrl) {
        // Risco Alto detectado pelo Gemini:
        if (session_status() === PHP_SESSION_NONE) {
            session_start();
        }

        // URL é validada ANTES de entrar na sessão
        $_SESSION['2fa_pending']['redirect_after_auth'] = SafeRedirect::validate($targetUrl);

        header("Location: /auth/verify-2fa");
        exit;
    })()),

    LoginStatus::FAILED => ((function () {
        header("Location: /login?error=credentials");
        exit;
    })()),
};
```

### 2.3 Verificação 2FA com Redirecionamento Seguro

Após validar o código OTP, o destino já foi sanitizado no passo anterior:

```php
<?php

declare(strict_types=1);

// verify_2fa_controller.php
session_start();

// ... validação do código OTP ...

if ($codeIsValid) {
    $_SESSION['user_id'] = $_SESSION['2fa_pending']['user_id'];

    // URL de destino já foi sanitizada pela Extensão URI no login
    $destination = $_SESSION['2fa_pending']['redirect_after_auth'] ?? '/dashboard';

    unset($_SESSION['2fa_pending']);
    header("Location: $destination");
    exit;
}
```

---

## 3. Geração de Senhas com Gemini 3 Flash

O Gemini 3 Flash é rápido, barato e suporta **Saída Estruturada (JSON)** — o modelo retorna JSON válido conforme um schema definido, eliminando parsing manual. Use a IA para **gerar** sugestões, nunca para **validar** senhas do usuário.

### 3.1 Implementação

Payload com `responseMimeType: application/json` e `responseSchema` garante saída tipada:

```php
<?php

declare(strict_types=1);

class GeminiPasswordAssistant
{
    public function suggestStrongPasswords(): array
    {
        $prompt = "Gere 3 senhas fortes (estilo passphrase, ex: Cavalo-Azul-Toca-Piano). "
                . "Inclua um mnemônico para cada. Responda apenas JSON.";

        $payload = [
            "model"    => "gemini-3-flash-preview",
            "contents" => [
                ["parts" => [["text" => $prompt]]],
            ],
            "generationConfig" => [
                "responseMimeType" => "application/json",
                "responseSchema"   => [
                    "type"       => "object",
                    "properties" => [
                        "suggestions" => [
                            "type"  => "array",
                            "items" => [
                                "type"       => "object",
                                "properties" => [
                                    "password"  => ["type" => "string"],
                                    "mnemonic"  => ["type" => "string"],
                                ],
                            ],
                        ],
                    ],
                ],
            ],
        ];

        // Envio via cURL persistente do PHP 8.5
        // ... implementação do envio ...

        return $result['suggestions'];
    }
}
```

**Resultado para o usuário:**

*   **Senha:** `Gato#Voa#Copo#Verde`
*   **Dica:** "O **Gato** que **Voa** derrubou o **Copo** na grama **Verde**."

> ⚠️ **Importante:** Nunca envie a senha que o usuário digitou para o Gemini verificar a força. Use a IA para **gerar** sugestões, e o PHP (Regex) para **validar** regras locais.

---

## 4. Detecção de Fraude em Documentos com Code Execution

O recurso de **Code Execution** do Gemini 3 Flash transforma o modelo de um observador passivo em um investigador ativo. Para detecção de fraudes em documentos, o modelo pode escrever e executar scripts Python (usando OpenCV e NumPy) para inspecionar pixels, verificar alinhamentos e detectar anomalias invisíveis a olho nu. A habilitação requer apenas adicionar `codeExecution` como ferramenta no payload.

### 4.1 Casos de Uso

*   **Análise de assinaturas:** Comparar padrões de traço e pressão.
*   **Detecção de adulteração:** Identificar edições em PDFs ou imagens de documentos.
*   **Verificação de identidade (KYC):** Extrair dados de documentos e comparar com informações cadastradas.

### 4.2 Configuração

Imagem enviada como Base64 no campo `inlineData`, com Code Execution habilitado:

```php
<?php

declare(strict_types=1);

// Para habilitar Code Execution, adicione como ferramenta
$payload = [
    "model"    => "gemini-3-flash-preview",
    "contents" => [
        [
            "parts" => [
                ["inlineData" => [
                    "mimeType" => "image/jpeg",
                    "data"     => base64_encode(file_get_contents('documento.jpg')),
                ]],
                ["text" => "Analise este documento. Verifique se há sinais de adulteração."],
            ],
        ],
    ],
    "tools" => [
        ["codeExecution" => new \stdClass()],
    ],
];
```

---

## 5. Segurança PHP 8.5 no Contexto de APIs Gemini

Práticas de segurança específicas para integrações com APIs de IA: `#[\NoDiscard]` para resultados de análise de risco, cookies particionados para widgets embarcados, e drivers PDO atualizados.

### 5.1 Atributo `#[\NoDiscard]` para Operações Críticas

Ignorar o resultado de `analyzeRisk()` é um bug grave — o atacante passa sem verificação:

```php
<?php

declare(strict_types=1);

class GeminiSecurityService
{
    #[\NoDiscard("O resultado da análise de risco DEVE ser verificado")]
    public function analyzeRisk(array $metadata): array
    {
        // Chamada ao Gemini 3 Flash
        // ...
        return ['risk_level' => 'HIGH', 'reason' => 'IP suspeito'];
    }
}

// ❌ PHP 8.5 emitirá WARNING — resultado ignorado!
$service->analyzeRisk($meta);

// ✅ Correto
$risk = $service->analyzeRisk($meta);
if ($risk['risk_level'] === 'HIGH') {
    // Bloquear acesso
}
```

### 5.2 Cookies Particionados (PHP 8.5)

PHP 8.5 adiciona suporte a `cookie_partitioned` para sessões em iframes/widgets de terceiros:

```php
<?php

declare(strict_types=1);

session_start([
    'cookie_httponly'     => true,
    'cookie_secure'       => true,
    'cookie_samesite'     => 'Strict',
    'cookie_partitioned'  => true, // PHP 8.5: Para iframes/widgets seguros
]);
```

### 5.3 Drivers PDO Atualizados

Drivers com manutenção ativa no PHP 8.5:

*   `PDO_PGSQL` (PostgreSQL)
*   `PDO_MYSQL` (MySQL)
*   `PDO_SQLITE` (SQLite)
*   `PDO_SQLSRV` (Microsoft SQL Server)

> **Regra de Ouro:** Use sempre `PDO::prepare()` com placeholders. Nunca use `PDO::quote()` — o escape manual é propenso a erros humanos.

---
---

## 51. Projeto Prático — Sistema Completo de Chatbot com Gemini Pro

Projeto fullstack production-ready: backend PHP 8.5 com `strict_types`, frontend responsivo com AJAX, banco MySQL com histórico e analytics, e painel administrativo. Cada arquivo é apresentado com código completo e comentado.

### Índice do Capítulo

1. Visão geral e arquitetura
2. Estrutura do projeto
3. Banco de dados MySQL
4. Configuração (`.env`, `database.php`, `gemini.php`)
5. `Database.php` — Conexão Singleton
6. `GeminiClient.php` — Integração com a API
7. `ChatRepository.php` — Operações CRUD
8. `ChatSession.php` — Gerenciamento de sessão
9. `api.php` — Endpoint AJAX
10. `index.php` — Interface web completa
11. `style.css` — CSS moderno responsivo
12. `chatbot.js` — JavaScript AJAX em tempo real
13. `admin.php` — Painel administrativo
14. Configuração de servidor (Apache/Nginx)
15. Instalação, deploy e troubleshooting

---

### 51.1 Visão Geral e Arquitetura

Um **chatbot production-ready** conectado à API Gemini Pro do Google, com:

- ⚡ AJAX em tempo real (sem recarregar página)
- 💬 Chat fluido com animações, typing indicator e tema claro/escuro
- 🗄️ Banco de dados MySQL com histórico, sessões, feedback e analytics
- 🎛️ Painel administrativo com dashboard e estatísticas
- 🔧 Backend PHP 8.5 com `strict_types`, prepared statements, PSR-12

```
┌─────────────────────────────────────────────────┐
│              FRONTEND (Browser)                 │
│  ┌──────────────────────────────────────────┐  │
│  │   index.php (HTML Interface)             │  │
│  │   chatbot.js (JavaScript AJAX)           │  │
│  └──────────────────────────────────────────┘  │
└────────────────┬────────────────────────────────┘
                 │ HTTP POST/GET (JSON)
                 ▼
┌─────────────────────────────────────────────────┐
│              BACKEND (PHP 8.5)                  │
│  ┌──────────────────────────────────────────┐  │
│  │   api.php → ChatSession → GeminiClient   │  │
│  │                         → ChatRepository │  │
│  └──────────────────────────────────────────┘  │
└────────────────┬────────────────┬───────────────┘
                 │                │
        ┌────────▼──────┐  ┌─────▼──────────┐
        │ MySQL Database│  │ Gemini Pro API  │
        │ (sessions,    │  │ (Google)        │
        │  messages,    │  └────────────────┘
        │  feedback)    │
        └───────────────┘
```

---

### 51.2 Estrutura do Projeto

```plaintext
gemini-chatbot/
│
├── config/
│   ├── database.php          # Configuração do banco
│   └── gemini.php            # API Key do Gemini
│
├── src/
│   ├── Database.php          # Conexão PDO Singleton
│   ├── GeminiClient.php      # Cliente da API Gemini
│   ├── ChatRepository.php    # Operações CRUD
│   └── ChatSession.php       # Lógica de negócio
│
├── public/
│   ├── index.php             # Interface principal
│   ├── api.php               # Endpoint AJAX
│   ├── admin.php             # Painel administrativo
│   ├── css/
│   │   └── style.css         # Estilos modernos
│   └── js/
│       └── chatbot.js        # JavaScript AJAX
│
├── uploads/                  # Imagens (opcional)
├── .env                      # Variáveis de ambiente
└── database.sql              # Schema SQL
```

---

### 51.3 Banco de Dados MySQL

```sql
-- database.sql

CREATE DATABASE IF NOT EXISTS gemini_chatbot
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;

USE gemini_chatbot;

-- Tabela de sessões
CREATE TABLE chat_sessions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    session_id VARCHAR(64) UNIQUE NOT NULL,
    user_ip VARCHAR(45),
    user_agent TEXT,
    started_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    last_activity TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,

    INDEX idx_session (session_id),
    INDEX idx_started (started_at)
) ENGINE=InnoDB;

-- Tabela de mensagens
CREATE TABLE chat_messages (
    id INT AUTO_INCREMENT PRIMARY KEY,
    session_id VARCHAR(64) NOT NULL,
    role ENUM('user', 'assistant') NOT NULL,
    message TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,

    FOREIGN KEY (session_id) REFERENCES chat_sessions(session_id) ON DELETE CASCADE,
    INDEX idx_session (session_id),
    INDEX idx_created (created_at)
) ENGINE=InnoDB;

-- Tabela de feedback
CREATE TABLE message_feedback (
    id INT AUTO_INCREMENT PRIMARY KEY,
    message_id INT NOT NULL,
    rating ENUM('positive', 'negative') NOT NULL,
    comment TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,

    FOREIGN KEY (message_id) REFERENCES chat_messages(id) ON DELETE CASCADE,
    INDEX idx_message (message_id)
) ENGINE=InnoDB;

-- View para estatísticas
CREATE VIEW chat_statistics AS
SELECT
    DATE(started_at) AS date,
    COUNT(DISTINCT session_id) AS total_sessions,
    COUNT(*) AS total_messages,
    AVG(message_count) AS avg_messages_per_session
FROM (
    SELECT
        cs.session_id,
        cs.started_at,
        COUNT(cm.id) AS message_count
    FROM chat_sessions cs
    LEFT JOIN chat_messages cm ON cs.session_id = cm.session_id
    GROUP BY cs.session_id, cs.started_at
) AS session_stats
GROUP BY DATE(started_at)
ORDER BY date DESC;
```

---

### 51.4 Configuração

#### `.env`

```env
# Banco de Dados
DB_HOST=localhost
DB_NAME=gemini_chatbot
DB_USER=root
DB_PASS=

# Gemini API
GEMINI_API_KEY=YOUR_API_KEY_HERE

# Configurações
APP_DEBUG=true
SESSION_LIFETIME=3600
MAX_MESSAGE_LENGTH=1000
```

#### `config/database.php`

```php
<?php
// config/database.php

declare(strict_types=1);

function loadEnv(string $path): void
{
    if (!file_exists($path)) {
        throw new RuntimeException('.env file not found');
    }

    $lines = file($path, FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);

    foreach ($lines as $line) {
        if (str_starts_with(trim($line), '#')) {
            continue;
        }

        if (!str_contains($line, '=')) {
            continue;
        }

        [$key, $value] = explode('=', $line, 2);
        $_ENV[trim($key)] = trim($value);
    }
}

loadEnv(__DIR__ . '/../.env');

define('DB_HOST', $_ENV['DB_HOST'] ?? 'localhost');
define('DB_NAME', $_ENV['DB_NAME'] ?? 'gemini_chatbot');
define('DB_USER', $_ENV['DB_USER'] ?? 'root');
define('DB_PASS', $_ENV['DB_PASS'] ?? '');
define('DB_CHARSET', 'utf8mb4');

define('DB_DSN', 'mysql:host=' . DB_HOST . ';dbname=' . DB_NAME . ';charset=' . DB_CHARSET);

define('DB_OPTIONS', [
    PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
    PDO::ATTR_EMULATE_PREPARES   => false,
]);
```

#### `config/gemini.php`

```php
<?php
// config/gemini.php

declare(strict_types=1);

require_once __DIR__ . '/database.php';

define('GEMINI_API_KEY', $_ENV['GEMINI_API_KEY'] ?? '');

if (GEMINI_API_KEY === '') {
    throw new RuntimeException('❌ GEMINI_API_KEY não configurada no .env');
}

define('APP_DEBUG', ($_ENV['APP_DEBUG'] ?? 'false') === 'true');
define('SESSION_LIFETIME', (int) ($_ENV['SESSION_LIFETIME'] ?? 3600));
define('MAX_MESSAGE_LENGTH', (int) ($_ENV['MAX_MESSAGE_LENGTH'] ?? 1000));
```


---

### 51.5 Database.php — Conexão Singleton

Singleton com construtor privado e lazy initialization:

```php
<?php
// src/Database.php

declare(strict_types=1);

final class Database
{
    private static ?PDO $connection = null;

    // Construtor privado — Singleton
    private function __construct() {}

    public static function getConnection(): PDO
    {
        if (self::$connection === null) {
            try {
                self::$connection = new PDO(DB_DSN, DB_USER, DB_PASS, DB_OPTIONS);
            } catch (PDOException $e) {
                error_log('Database connection error: ' . $e->getMessage());
                throw new RuntimeException('Erro ao conectar ao banco de dados');
            }
        }

        return self::$connection;
    }
}
```

---

### 51.6 GeminiClient.php — Integração com a API

Cliente HTTP com cURL, validação de API Key no construtor, chat com histórico e extração segura da resposta:

```php
<?php
// src/GeminiClient.php

declare(strict_types=1);

final class GeminiClient
{
    private const string BASE_URL = 'https://generativelanguage.googleapis.com/v1';
    private const string MODEL   = 'gemini-pro';

    public function __construct(
        private readonly string $apiKey,
        private readonly int $timeout = 30
    ) {
        if ($this->apiKey === '') {
            throw new InvalidArgumentException('API Key é obrigatória');
        }
    }

    /**
     * Chat com histórico de mensagens
     */
    public function chat(array $messages): string
    {
        $url = self::BASE_URL . '/models/' . self::MODEL . ':generateContent';

        $contents = [];

        foreach ($messages as $message) {
            $contents[] = [
                'role'  => $message['role'] === 'user' ? 'user' : 'model',
                'parts' => [['text' => $message['message']]],
            ];
        }

        $response = $this->makeRequest($url, ['contents' => $contents]);

        return $this->extractText($response);
    }

    /**
     * Gerar resposta a partir de prompt simples
     */
    public function generateText(string $prompt): string
    {
        $url = self::BASE_URL . '/models/' . self::MODEL . ':generateContent';

        $body = [
            'contents' => [
                ['parts' => [['text' => $prompt]]],
            ],
        ];

        $response = $this->makeRequest($url, $body);

        return $this->extractText($response);
    }

    /**
     * Requisição HTTP via cURL
     */
    private function makeRequest(string $url, array $body): array
    {
        $url .= '?key=' . $this->apiKey;

        $ch = curl_init();

        curl_setopt_array($ch, [
            CURLOPT_URL            => $url,
            CURLOPT_POST           => true,
            CURLOPT_POSTFIELDS     => json_encode($body, JSON_THROW_ON_ERROR),
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_TIMEOUT        => $this->timeout,
            CURLOPT_HTTPHEADER     => ['Content-Type: application/json'],
        ]);

        $response = curl_exec($ch);
        $httpCode = (int) curl_getinfo($ch, CURLINFO_HTTP_CODE);
        $error    = curl_error($ch);

        curl_close($ch);

        if ($response === false) {
            throw new RuntimeException("Erro cURL: {$error}");
        }

        /** @var array $data */
        $data = json_decode($response, true, flags: JSON_THROW_ON_ERROR);

        if ($httpCode !== 200) {
            $errorMessage = $data['error']['message'] ?? 'Erro desconhecido';
            throw new RuntimeException("Erro API ({$httpCode}): {$errorMessage}");
        }

        return $data;
    }

    /**
     * Extrair texto da resposta da API
     */
    private function extractText(array $response): string
    {
        return $response['candidates'][0]['content']['parts'][0]['text']
            ?? throw new RuntimeException('Resposta inválida da API');
    }
}
```

---

### 51.7 ChatRepository.php — Operações CRUD

Repository com prepared statements, heredoc SQL e `ON DUPLICATE KEY UPDATE` para upsert de sessão:

```php
<?php
// src/ChatRepository.php

declare(strict_types=1);

final class ChatRepository
{
    public function __construct(
        private readonly PDO $pdo
    ) {}

    /**
     * Criar ou atualizar sessão
     */
    public function createSession(string $sessionId, string $userIp, string $userAgent): bool
    {
        $sql = <<<'SQL'
            INSERT INTO chat_sessions (session_id, user_ip, user_agent)
            VALUES (:session_id, :user_ip, :user_agent)
            ON DUPLICATE KEY UPDATE last_activity = CURRENT_TIMESTAMP
        SQL;

        $stmt = $this->pdo->prepare($sql);

        return $stmt->execute([
            'session_id' => $sessionId,
            'user_ip'    => $userIp,
            'user_agent' => $userAgent,
        ]);
    }

    /**
     * Salvar mensagem e retornar ID
     */
    public function saveMessage(string $sessionId, string $role, string $message): int
    {
        $sql = 'INSERT INTO chat_messages (session_id, role, message) VALUES (?, ?, ?)';

        $stmt = $this->pdo->prepare($sql);
        $stmt->execute([$sessionId, $role, $message]);

        return (int) $this->pdo->lastInsertId();
    }

    /**
     * Obter histórico de mensagens da sessão
     */
    public function getMessages(string $sessionId, int $limit = 50): array
    {
        $sql = <<<'SQL'
            SELECT role, message, created_at
            FROM chat_messages
            WHERE session_id = :session_id
            ORDER BY created_at ASC
            LIMIT :limit
        SQL;

        $stmt = $this->pdo->prepare($sql);
        $stmt->bindValue(':session_id', $sessionId);
        $stmt->bindValue(':limit', $limit, PDO::PARAM_INT);
        $stmt->execute();

        return $stmt->fetchAll();
    }

    /**
     * Limpar todas as mensagens de uma sessão
     */
    public function clearSession(string $sessionId): bool
    {
        $stmt = $this->pdo->prepare('DELETE FROM chat_messages WHERE session_id = ?');

        return $stmt->execute([$sessionId]);
    }

    /**
     * Obter estatísticas agregadas (últimos 30 dias)
     */
    public function getStatistics(): array
    {
        return $this->pdo->query('SELECT * FROM chat_statistics LIMIT 30')->fetchAll();
    }

    /**
     * Contar mensagens de uma sessão
     */
    public function countMessages(string $sessionId): int
    {
        $stmt = $this->pdo->prepare('SELECT COUNT(*) FROM chat_messages WHERE session_id = ?');
        $stmt->execute([$sessionId]);

        return (int) $stmt->fetchColumn();
    }

    /**
     * Salvar feedback de uma mensagem
     */
    public function saveFeedback(int $messageId, string $rating, ?string $comment = null): bool
    {
        $sql = 'INSERT INTO message_feedback (message_id, rating, comment) VALUES (?, ?, ?)';

        $stmt = $this->pdo->prepare($sql);

        return $stmt->execute([$messageId, $rating, $comment]);
    }
}
```

---

### 51.8 ChatSession.php — Gerenciamento de Sessão

Orquestra o fluxo: valida input → salva mensagem → busca histórico → consulta Gemini → salva resposta:

```php
<?php
// src/ChatSession.php

declare(strict_types=1);

final class ChatSession
{
    public function __construct(
        private readonly GeminiClient $gemini,
        private readonly ChatRepository $repository,
        private readonly string $sessionId
    ) {
        // Criar/atualizar sessão no banco
        $this->repository->createSession(
            sessionId: $sessionId,
            userIp: $_SERVER['REMOTE_ADDR'] ?? '0.0.0.0',
            userAgent: $_SERVER['HTTP_USER_AGENT'] ?? 'Unknown',
        );
    }

    /**
     * Enviar mensagem e obter resposta da IA
     */
    public function sendMessage(string $message): array
    {
        $message = trim($message);

        if ($message === '') {
            throw new InvalidArgumentException('Mensagem não pode ser vazia');
        }

        if (mb_strlen($message) > MAX_MESSAGE_LENGTH) {
            throw new InvalidArgumentException(
                "Mensagem muito longa (máx " . MAX_MESSAGE_LENGTH . " caracteres)"
            );
        }

        // 1. Salvar mensagem do usuário
        $this->repository->saveMessage($this->sessionId, 'user', $message);

        // 2. Obter últimas 10 mensagens para contexto
        $history = $this->repository->getMessages($this->sessionId, limit: 10);

        // 3. Obter resposta do Gemini
        $response = $this->gemini->chat($history);

        // 4. Salvar resposta do assistente
        $messageId = $this->repository->saveMessage($this->sessionId, 'assistant', $response);

        return [
            'id'        => $messageId,
            'role'      => 'assistant',
            'message'   => $response,
            'timestamp' => date('Y-m-d H:i:s'),
        ];
    }

    public function getHistory(): array
    {
        return $this->repository->getMessages($this->sessionId);
    }

    public function clearHistory(): bool
    {
        return $this->repository->clearSession($this->sessionId);
    }

    public function getSessionId(): string
    {
        return $this->sessionId;
    }
}
```


---

### 51.9 api.php — Endpoint AJAX

Router baseado em `match` com 4 actions: `send`, `history`, `clear` e `feedback`:

```php
<?php
// public/api.php

declare(strict_types=1);

header('Content-Type: application/json; charset=utf-8');

require_once __DIR__ . '/../config/gemini.php';
require_once __DIR__ . '/../src/Database.php';
require_once __DIR__ . '/../src/GeminiClient.php';
require_once __DIR__ . '/../src/ChatRepository.php';
require_once __DIR__ . '/../src/ChatSession.php';

session_start();

// Criar ou recuperar session_id
if (!isset($_SESSION['chat_session_id'])) {
    $_SESSION['chat_session_id'] = bin2hex(random_bytes(32));
}

$sessionId  = $_SESSION['chat_session_id'];
$pdo        = Database::getConnection();
$gemini     = new GeminiClient(GEMINI_API_KEY);
$repository = new ChatRepository($pdo);
$session    = new ChatSession($gemini, $repository, $sessionId);

try {
    $action = $_POST['action'] ?? $_GET['action'] ?? null;

    match ($action) {
        'send' => (function () use ($session): void {
            $message  = $_POST['message'] ?? '';
            $response = $session->sendMessage($message);

            echo json_encode(['success' => true, 'data' => $response], JSON_THROW_ON_ERROR);
        })(),

        'history' => (function () use ($session): void {
            $history = $session->getHistory();

            echo json_encode(['success' => true, 'data' => $history], JSON_THROW_ON_ERROR);
        })(),

        'clear' => (function () use ($session): void {
            $cleared = $session->clearHistory();

            echo json_encode([
                'success' => $cleared,
                'message' => $cleared ? 'Histórico limpo' : 'Erro ao limpar',
            ], JSON_THROW_ON_ERROR);
        })(),

        'feedback' => (function () use ($repository): void {
            $messageId = (int) ($_POST['message_id'] ?? 0);
            $rating    = $_POST['rating'] ?? '';
            $comment   = $_POST['comment'] ?? null;

            if ($messageId === 0 || !in_array($rating, ['positive', 'negative'], true)) {
                throw new InvalidArgumentException('Dados de feedback inválidos');
            }

            $saved = $repository->saveFeedback($messageId, $rating, $comment);

            echo json_encode([
                'success' => $saved,
                'message' => 'Obrigado pelo feedback!',
            ], JSON_THROW_ON_ERROR);
        })(),

        default => throw new InvalidArgumentException('Ação inválida'),
    };
} catch (Exception $e) {
    http_response_code(400);

    echo json_encode([
        'success' => false,
        'error'   => $e->getMessage(),
    ], JSON_THROW_ON_ERROR);

    if (APP_DEBUG) {
        error_log('Chat API Error: ' . $e->getMessage());
    }
}
```

---

### 51.10 index.php — Interface Web Completa

HTML semântico com typing indicator, quick actions e toast notifications:

```php
<?php
// public/index.php

declare(strict_types=1);

session_start();

if (!isset($_SESSION['chat_session_id'])) {
    $_SESSION['chat_session_id'] = bin2hex(random_bytes(32));
}
?>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💬 Chatbot IA - Powered by Gemini Pro</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <div class="chat-container">
        <!-- Header -->
        <div class="chat-header">
            <div class="header-content">
                <div class="bot-avatar">🤖</div>
                <div class="bot-info">
                    <h1>Assistente Virtual</h1>
                    <p class="bot-status">
                        <span class="status-indicator"></span>
                        Online - Powered by Gemini Pro
                    </p>
                </div>
            </div>
            <div class="header-actions">
                <button id="clearChat" class="btn-icon" title="Limpar conversa">🗑️</button>
                <button id="toggleTheme" class="btn-icon" title="Alternar tema">🌙</button>
            </div>
        </div>

        <!-- Área de mensagens -->
        <div class="chat-messages" id="chatMessages">
            <div class="message assistant-message">
                <div class="message-avatar">🤖</div>
                <div class="message-content">
                    <div class="message-text">
                        <p>👋 Olá! Eu sou seu assistente virtual.</p>
                        <p>Como posso ajudar você hoje?</p>
                    </div>
                    <div class="message-time"><?= date('H:i') ?></div>
                </div>
            </div>
        </div>

        <!-- Typing Indicator -->
        <div class="typing-indicator" id="typingIndicator" style="display: none;">
            <div class="message-avatar">🤖</div>
            <div class="typing-dots">
                <span></span><span></span><span></span>
            </div>
        </div>

        <!-- Input -->
        <div class="chat-input">
            <form id="chatForm">
                <div class="input-wrapper">
                    <textarea
                        id="messageInput"
                        placeholder="Digite sua mensagem..."
                        rows="1"
                        maxlength="1000"
                    ></textarea>
                    <div class="input-actions">
                        <span class="char-counter"><span id="charCount">0</span>/1000</span>
                        <button type="submit" class="btn-send" id="sendButton">
                            <span class="send-icon">📤</span>
                            <span class="send-text">Enviar</span>
                        </button>
                    </div>
                </div>
            </form>
        </div>

        <!-- Quick Actions -->
        <div class="quick-actions" id="quickActions">
            <button class="quick-action" data-message="Me explique como funciona a inteligência artificial">
                🧠 Como funciona IA?
            </button>
            <button class="quick-action" data-message="Crie um código PHP para validar email">
                💻 Exemplo de código
            </button>
            <button class="quick-action" data-message="Me conte uma curiosidade interessante">
                🎯 Curiosidade
            </button>
        </div>
    </div>

    <!-- Toast Notifications -->
    <div id="toastContainer" class="toast-container"></div>

    <script src="js/chatbot.js"></script>
</body>
</html>
```


---

### 51.11 style.css — CSS Moderno Responsivo

Design system com CSS custom properties, dark theme, animações e responsividade mobile-first:

```css
/* public/css/style.css */

/* === RESET E VARIÁVEIS === */
* { margin: 0; padding: 0; box-sizing: border-box; }

:root {
    --primary: #667eea;
    --primary-dark: #5568d3;
    --secondary: #764ba2;
    --accent: #f093fb;
    --bg-main: #f5f7fa;
    --bg-chat: #ffffff;
    --bg-message-user: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    --bg-message-assistant: #f0f2f5;
    --text-primary: #2d3748;
    --text-secondary: #718096;
    --border-color: #e2e8f0;
    --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
    --shadow-md: 0 4px 16px rgba(0, 0, 0, 0.1);
    --shadow-lg: 0 8px 32px rgba(0, 0, 0, 0.12);
    --transition: all 0.3s ease;
}

body.dark-theme {
    --bg-main: #1a202c;
    --bg-chat: #2d3748;
    --bg-message-assistant: #4a5568;
    --text-primary: #f7fafc;
    --text-secondary: #cbd5e0;
    --border-color: #4a5568;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    background: var(--bg-main);
    color: var(--text-primary);
    line-height: 1.6;
    transition: var(--transition);
}

/* === CONTAINER === */
.chat-container {
    max-width: 900px;
    margin: 0 auto;
    height: 100vh;
    display: flex;
    flex-direction: column;
    background: var(--bg-chat);
    box-shadow: var(--shadow-lg);
}

/* === HEADER === */
.chat-header {
    background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
    color: white;
    padding: 20px 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: var(--shadow-md);
    z-index: 10;
}

.header-content { display: flex; align-items: center; gap: 15px; }

.bot-avatar { font-size: 48px; animation: float 3s ease-in-out infinite; }

@keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
}

.bot-info h1 { font-size: 24px; font-weight: 600; }

.bot-status {
    font-size: 14px;
    opacity: 0.9;
    display: flex;
    align-items: center;
    gap: 8px;
}

.status-indicator {
    width: 8px; height: 8px;
    background: #48bb78;
    border-radius: 50%;
    animation: pulse 2s infinite;
}

@keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }

.btn-icon {
    background: rgba(255, 255, 255, 0.2);
    border: none;
    width: 40px; height: 40px;
    border-radius: 50%;
    font-size: 20px;
    cursor: pointer;
    transition: var(--transition);
}

.btn-icon:hover { background: rgba(255, 255, 255, 0.3); transform: scale(1.1); }

/* === MENSAGENS === */
.chat-messages {
    flex: 1;
    overflow-y: auto;
    padding: 30px;
    display: flex;
    flex-direction: column;
    gap: 20px;
    scroll-behavior: smooth;
}

.message {
    display: flex;
    gap: 12px;
    animation: messageSlideIn 0.3s ease-out;
    max-width: 85%;
}

@keyframes messageSlideIn {
    from { opacity: 0; transform: translateY(10px); }
    to   { opacity: 1; transform: translateY(0); }
}

.user-message      { align-self: flex-end; flex-direction: row-reverse; }
.assistant-message  { align-self: flex-start; }
.message-avatar     { font-size: 32px; flex-shrink: 0; }

.message-text {
    padding: 15px 20px;
    border-radius: 18px;
    line-height: 1.5;
}

.user-message .message-text {
    background: var(--bg-message-user);
    color: white;
    border-bottom-right-radius: 4px;
}

.assistant-message .message-text {
    background: var(--bg-message-assistant);
    color: var(--text-primary);
    border-bottom-left-radius: 4px;
}

.message-text code {
    background: rgba(0, 0, 0, 0.1);
    padding: 2px 6px;
    border-radius: 4px;
    font-family: 'Courier New', monospace;
}

.message-text pre {
    background: rgba(0, 0, 0, 0.1);
    padding: 12px;
    border-radius: 8px;
    overflow-x: auto;
    margin: 10px 0;
}

.message-time { font-size: 12px; color: var(--text-secondary); padding: 0 5px; }

.feedback-btn {
    background: none; border: none;
    font-size: 16px; cursor: pointer;
    opacity: 0.6; transition: var(--transition);
}

.feedback-btn:hover { opacity: 1; transform: scale(1.2); }

/* === TYPING INDICATOR === */
.typing-indicator {
    display: flex; gap: 12px; align-items: center;
    padding: 0 30px; margin-bottom: 20px;
}

.typing-dots {
    background: var(--bg-message-assistant);
    padding: 15px 20px;
    border-radius: 18px;
    display: flex; gap: 6px;
}

.typing-dots span {
    width: 8px; height: 8px;
    background: var(--text-secondary);
    border-radius: 50%;
    animation: typing 1.4s infinite;
}

.typing-dots span:nth-child(2) { animation-delay: 0.2s; }
.typing-dots span:nth-child(3) { animation-delay: 0.4s; }

@keyframes typing {
    0%, 60%, 100% { transform: translateY(0); opacity: 0.7; }
    30%           { transform: translateY(-10px); opacity: 1; }
}

/* === INPUT === */
.chat-input {
    padding: 20px 30px;
    border-top: 1px solid var(--border-color);
}

.input-wrapper {
    background: var(--bg-main);
    border-radius: 24px;
    padding: 12px 20px;
    border: 2px solid transparent;
    transition: var(--transition);
}

.input-wrapper:focus-within { border-color: var(--primary); }

#messageInput {
    width: 100%;
    background: transparent;
    border: none; outline: none;
    font-size: 15px;
    color: var(--text-primary);
    resize: none;
    font-family: inherit;
    max-height: 120px;
}

.input-actions { display: flex; justify-content: space-between; align-items: center; }

.btn-send {
    background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
    color: white; border: none;
    padding: 10px 24px; border-radius: 20px;
    font-size: 14px; font-weight: 600;
    cursor: pointer;
    display: flex; align-items: center; gap: 8px;
    transition: var(--transition);
}

.btn-send:hover:not(:disabled) {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
}

.btn-send:disabled { opacity: 0.5; cursor: not-allowed; }

/* === QUICK ACTIONS === */
.quick-actions { padding: 0 30px 20px; display: flex; gap: 10px; flex-wrap: wrap; }

.quick-action {
    background: var(--bg-main);
    border: 2px solid var(--border-color);
    padding: 10px 16px;
    border-radius: 20px;
    font-size: 13px;
    color: var(--text-primary);
    cursor: pointer;
    transition: var(--transition);
}

.quick-action:hover {
    border-color: var(--primary);
    background: var(--primary);
    color: white;
    transform: translateY(-2px);
}

/* === TOAST === */
.toast-container {
    position: fixed; bottom: 30px; right: 30px;
    display: flex; flex-direction: column; gap: 10px; z-index: 1000;
}

.toast {
    background: white; padding: 16px 24px;
    border-radius: 12px; box-shadow: var(--shadow-lg);
    display: flex; align-items: center; gap: 12px;
    min-width: 300px;
    animation: toastSlideIn 0.3s ease-out;
}

@keyframes toastSlideIn {
    from { opacity: 0; transform: translateX(100%); }
    to   { opacity: 1; transform: translateX(0); }
}

.toast.success { border-left: 4px solid #48bb78; }
.toast.error   { border-left: 4px solid #f56565; }
.toast.info    { border-left: 4px solid #4299e1; }

/* === RESPONSIVE === */
@media (max-width: 768px) {
    .chat-header { padding: 15px 20px; }
    .bot-info h1 { font-size: 18px; }
    .bot-avatar  { font-size: 36px; }
    .chat-messages { padding: 20px; }
    .message { max-width: 90%; }
    .send-text { display: none; }
}
```


---

### 51.12 chatbot.js — JavaScript AJAX em Tempo Real

Classe ES6 com fetch API, auto-resize do textarea, markdown básico e sistema de feedback:

```javascript
// public/js/chatbot.js

'use strict';

class Chatbot {
    constructor() {
        this.messagesContainer = document.getElementById('chatMessages');
        this.messageInput      = document.getElementById('messageInput');
        this.chatForm          = document.getElementById('chatForm');
        this.sendButton        = document.getElementById('sendButton');
        this.clearButton       = document.getElementById('clearChat');
        this.typingIndicator   = document.getElementById('typingIndicator');
        this.charCount         = document.getElementById('charCount');
        this.quickActions      = document.querySelectorAll('.quick-action');
        this.themeToggle       = document.getElementById('toggleTheme');

        this.init();
    }

    init() {
        this.chatForm.addEventListener('submit', (e) => this.handleSubmit(e));
        this.clearButton.addEventListener('click', () => this.clearHistory());
        this.messageInput.addEventListener('input', () => {
            this.updateCharCount();
            this.autoResize();
        });
        this.messageInput.addEventListener('keydown', (e) => this.handleKeyDown(e));
        this.themeToggle.addEventListener('click', () => this.toggleTheme());

        this.quickActions.forEach(btn => {
            btn.addEventListener('click', () => {
                this.messageInput.value = btn.dataset.message;
                this.messageInput.focus();
                this.autoResize();
            });
        });

        this.loadHistory();
        this.messageInput.focus();
    }

    // ✅ Enviar mensagem
    async handleSubmit(e) {
        e.preventDefault();

        const message = this.messageInput.value.trim();
        if (!message) return;

        this.addMessage(message, 'user');
        this.messageInput.value = '';
        this.updateCharCount();
        this.autoResize();
        this.setLoading(true);
        this.showTyping();

        try {
            const response = await this.sendToAPI(message);
            this.hideTyping();
            this.addMessage(response.data.message, 'assistant', response.data.id);
        } catch (error) {
            this.hideTyping();
            this.showToast('Erro: ' + error.message, 'error');
        } finally {
            this.setLoading(false);
        }
    }

    // ✅ Requisição AJAX
    async sendToAPI(message) {
        const formData = new FormData();
        formData.append('action', 'send');
        formData.append('message', message);

        const response = await fetch('api.php', { method: 'POST', body: formData });

        if (!response.ok) throw new Error('Erro na requisição');

        const data = await response.json();

        if (!data.success) throw new Error(data.error || 'Erro desconhecido');

        return data;
    }

    // ✅ Adicionar mensagem na interface
    addMessage(text, role, messageId = null) {
        const div     = document.createElement('div');
        div.className = `message ${role}-message fade-in`;

        const avatar = role === 'user' ? '👤' : '🤖';
        const time   = new Date().toLocaleTimeString('pt-BR', {
            hour: '2-digit', minute: '2-digit'
        });

        div.innerHTML = `
            <div class="message-avatar">${avatar}</div>
            <div class="message-content">
                <div class="message-text">${this.formatMessage(text)}</div>
                <div class="message-time">${time}</div>
                ${role === 'assistant' && messageId
                    ? this.createFeedbackButtons(messageId) : ''}
            </div>
        `;

        this.messagesContainer.appendChild(div);
        this.scrollToBottom();
    }

    // ✅ Markdown básico
    formatMessage(text) {
        return text
            .replace(/```(.*?)```/gs, '<pre><code>$1</code></pre>')
            .replace(/`(.*?)`/g, '<code>$1</code>')
            .replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>')
            .replace(/\*(.*?)\*/g, '<em>$1</em>')
            .replace(/\n/g, '<br>');
    }

    createFeedbackButtons(messageId) {
        return `
            <div class="message-feedback" style="display:flex;gap:8px;padding:0 5px">
                <button class="feedback-btn"
                    onclick="chatbot.sendFeedback(${messageId}, 'positive')">👍</button>
                <button class="feedback-btn"
                    onclick="chatbot.sendFeedback(${messageId}, 'negative')">👎</button>
            </div>
        `;
    }

    async sendFeedback(messageId, rating) {
        const formData = new FormData();
        formData.append('action', 'feedback');
        formData.append('message_id', messageId);
        formData.append('rating', rating);

        try {
            const res  = await fetch('api.php', { method: 'POST', body: formData });
            const data = await res.json();
            if (data.success) this.showToast('Obrigado pelo feedback!', 'success');
        } catch (err) {
            console.error('Erro ao enviar feedback:', err);
        }
    }

    // ✅ Histórico
    async loadHistory() {
        try {
            const res  = await fetch('api.php?action=history');
            const data = await res.json();

            if (data.success && data.data.length > 0) {
                this.messagesContainer.innerHTML = '';
                data.data.forEach(msg => this.addMessage(msg.message, msg.role));
            }
        } catch (err) {
            console.error('Erro ao carregar histórico:', err);
        }
    }

    async clearHistory() {
        if (!confirm('Deseja limpar todo o histórico?')) return;

        const formData = new FormData();
        formData.append('action', 'clear');

        try {
            const res  = await fetch('api.php', { method: 'POST', body: formData });
            const data = await res.json();

            if (data.success) {
                const time = new Date().toLocaleTimeString('pt-BR', {
                    hour: '2-digit', minute: '2-digit'
                });

                this.messagesContainer.innerHTML = `
                    <div class="message assistant-message">
                        <div class="message-avatar">🤖</div>
                        <div class="message-content">
                            <div class="message-text">
                                <p>👋 Olá! Eu sou seu assistente virtual.</p>
                                <p>Como posso ajudar você hoje?</p>
                            </div>
                            <div class="message-time">${time}</div>
                        </div>
                    </div>
                `;
                this.showToast('Histórico limpo!', 'success');
            }
        } catch (err) {
            this.showToast('Erro ao limpar histórico', 'error');
        }
    }

    // ✅ UI helpers
    showTyping()  { this.typingIndicator.style.display = 'flex'; this.scrollToBottom(); }
    hideTyping()  { this.typingIndicator.style.display = 'none'; }
    scrollToBottom() {
        setTimeout(() => {
            this.messagesContainer.scrollTop = this.messagesContainer.scrollHeight;
        }, 100);
    }

    setLoading(loading) {
        this.sendButton.disabled    = loading;
        this.messageInput.disabled  = loading;
        this.sendButton.innerHTML   = loading
            ? '<span class="send-icon">⏳</span><span class="send-text">Enviando...</span>'
            : '<span class="send-icon">📤</span><span class="send-text">Enviar</span>';
        if (!loading) this.messageInput.focus();
    }

    updateCharCount() {
        const count = this.messageInput.value.length;
        this.charCount.textContent = count;
        this.charCount.style.color = count > 900 ? '#f56565' : 'var(--text-secondary)';
    }

    autoResize() {
        this.messageInput.style.height = 'auto';
        this.messageInput.style.height = this.messageInput.scrollHeight + 'px';
    }

    handleKeyDown(e) {
        if (e.key === 'Enter' && !e.shiftKey) {
            e.preventDefault();
            this.chatForm.dispatchEvent(new Event('submit'));
        }
    }

    toggleTheme() {
        document.body.classList.toggle('dark-theme');
        const isDark = document.body.classList.contains('dark-theme');
        this.themeToggle.textContent = isDark ? '☀️' : '🌙';
        localStorage.setItem('theme', isDark ? 'dark' : 'light');
    }

    showToast(message, type = 'info') {
        const icons = { success: '✅', error: '❌', info: 'ℹ️' };
        const toast = document.createElement('div');
        toast.className = `toast ${type}`;
        toast.innerHTML = `
            <div class="toast-icon">${icons[type]}</div>
            <div class="toast-content">
                <div class="toast-message">${message}</div>
            </div>
        `;
        document.getElementById('toastContainer').appendChild(toast);
        setTimeout(() => toast.remove(), 3000);
    }
}

// Inicializar
const chatbot = new Chatbot();

// Carregar tema salvo
if (localStorage.getItem('theme') === 'dark') {
    document.body.classList.add('dark-theme');
    document.getElementById('toggleTheme').textContent = '☀️';
}
```


---

### 51.13 admin.php — Painel Administrativo

Dashboard com estatísticas, gráfico de barras CSS puro e tabela de sessões recentes:

```php
<?php
// public/admin.php

declare(strict_types=1);

require_once __DIR__ . '/../config/gemini.php';
require_once __DIR__ . '/../src/Database.php';
require_once __DIR__ . '/../src/ChatRepository.php';

session_start();

// ⚠️ Autenticação BÁSICA — em produção use sistema completo!
$adminPassword = 'admin123';

if ($_SERVER['REQUEST_METHOD'] === 'POST' && isset($_POST['password'])) {
    if ($_POST['password'] === $adminPassword) {
        $_SESSION['admin_logged'] = true;
    } else {
        $loginError = 'Senha incorreta';
    }
}

if (isset($_GET['logout'])) {
    unset($_SESSION['admin_logged']);
    header('Location: admin.php');
    exit;
}

$isLogged = $_SESSION['admin_logged'] ?? false;

// --- TELA DE LOGIN ---
if (!$isLogged) { ?>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin - Login</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex; align-items: center; justify-content: center;
        }
        .login-box {
            background: white; padding: 40px; border-radius: 10px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.2); width: 100%; max-width: 400px;
        }
        h1 { margin-bottom: 30px; text-align: center; }
        input {
            width: 100%; padding: 12px; border: 2px solid #ddd;
            border-radius: 5px; font-size: 16px; margin-bottom: 20px;
        }
        button {
            width: 100%; padding: 12px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white; border: none; border-radius: 5px;
            font-size: 16px; cursor: pointer; font-weight: 600;
        }
        .error { background: #fee; color: #c33; padding: 10px; border-radius: 5px; margin-bottom: 20px; text-align: center; }
    </style>
</head>
<body>
    <div class="login-box">
        <h1>🔐 Admin Login</h1>
        <?php if (isset($loginError)): ?>
            <div class="error"><?= htmlspecialchars($loginError) ?></div>
        <?php endif; ?>
        <form method="POST">
            <input type="password" name="password" placeholder="Senha" required autofocus>
            <button type="submit">Entrar</button>
        </form>
    </div>
</body>
</html>
<?php exit; }

// --- DASHBOARD (logado) ---
$pdo        = Database::getConnection();
$repository = new ChatRepository($pdo);
$stats      = $repository->getStatistics();

$recentSessions = $pdo->query("
    SELECT cs.session_id, cs.user_ip, cs.started_at, cs.last_activity,
           COUNT(cm.id) AS message_count
    FROM chat_sessions cs
    LEFT JOIN chat_messages cm ON cs.session_id = cm.session_id
    GROUP BY cs.session_id
    ORDER BY cs.last_activity DESC
    LIMIT 20
")->fetchAll();

$todayMessages = (int) $pdo->query("
    SELECT COUNT(*) FROM chat_messages WHERE DATE(created_at) = CURDATE()
")->fetchColumn();

$totalSessions = (int) $pdo->query("SELECT COUNT(*) FROM chat_sessions")->fetchColumn();
?>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>📊 Painel Administrativo - Chatbot</title>
    <style>
        /* Estilos do admin — ver CSS completo no arquivo original */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: -apple-system, sans-serif; background: #f5f7fa; color: #2d3748; }
        .header {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white; padding: 20px 40px;
            display: flex; justify-content: space-between; align-items: center;
        }
        .header a { color: white; text-decoration: none; padding: 8px 16px; background: rgba(255,255,255,0.2); border-radius: 5px; }
        .container { max-width: 1400px; margin: 0 auto; padding: 40px 20px; }
        .stats-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; margin-bottom: 40px; }
        .stat-card { background: white; padding: 30px; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.05); }
        .stat-number { font-size: 48px; font-weight: bold; color: #667eea; }
        .section { background: white; padding: 30px; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.05); margin-bottom: 30px; }
        table { width: 100%; border-collapse: collapse; }
        th { background: #f7fafc; padding: 12px; text-align: left; border-bottom: 2px solid #e2e8f0; }
        td { padding: 12px; border-bottom: 1px solid #e2e8f0; }
        .bar { display: flex; align-items: center; margin-bottom: 15px; }
        .bar-label { width: 100px; font-size: 14px; }
        .bar-track { flex: 1; height: 30px; background: #e2e8f0; border-radius: 5px; overflow: hidden; }
        .bar-fill { height: 100%; background: linear-gradient(135deg, #667eea, #764ba2); border-radius: 5px; display: flex; align-items: center; justify-content: flex-end; padding: 0 10px; color: white; font-weight: 600; font-size: 12px; }
    </style>
</head>
<body>
    <div class="header">
        <h1>📊 Painel Administrativo</h1>
        <div>
            <a href="index.php">💬 Chatbot</a>
            <a href="?logout">🚪 Sair</a>
        </div>
    </div>
    <div class="container">
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number"><?= $totalSessions ?></div>
                <div>Total de Sessões</div>
            </div>
            <div class="stat-card">
                <div class="stat-number"><?= $todayMessages ?></div>
                <div>Mensagens Hoje</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">
                    <?= $totalSessions > 0 ? round($todayMessages / max(1, $totalSessions), 1) : 0 ?>
                </div>
                <div>Média por Sessão</div>
            </div>
        </div>

        <?php if (!empty($stats)): ?>
        <div class="section">
            <h2>📈 Uso nos Últimos Dias</h2>
            <?php
            $maxMessages = max(array_column($stats, 'total_messages'));
            foreach (array_slice($stats, 0, 7) as $stat):
                $pct = $maxMessages > 0 ? ($stat['total_messages'] / $maxMessages) * 100 : 0;
            ?>
                <div class="bar">
                    <div class="bar-label"><?= date('d/m', strtotime($stat['date'])) ?></div>
                    <div class="bar-track">
                        <div class="bar-fill" style="width: <?= $pct ?>%"><?= $stat['total_messages'] ?></div>
                    </div>
                </div>
            <?php endforeach; ?>
        </div>
        <?php endif; ?>

        <div class="section">
            <h2>🕐 Sessões Recentes</h2>
            <table>
                <thead><tr><th>Session ID</th><th>IP</th><th>Msgs</th><th>Início</th></tr></thead>
                <tbody>
                <?php foreach ($recentSessions as $s): ?>
                    <tr>
                        <td><code><?= substr($s['session_id'], 0, 16) ?>…</code></td>
                        <td><?= htmlspecialchars($s['user_ip']) ?></td>
                        <td><?= $s['message_count'] ?></td>
                        <td><?= date('d/m H:i', strtotime($s['started_at'])) ?></td>
                    </tr>
                <?php endforeach; ?>
                </tbody>
            </table>
        </div>
    </div>
</body>
</html>
```

---

### 51.14 Configuração de Servidor

Configuração para Apache (`.htaccess`) e Nginx com bloqueio de arquivos sensíveis e GZIP:

#### `.htaccess` (Apache)

```apache
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteBase /
    RewriteCond %{REQUEST_URI} !^/public/
    RewriteRule ^(.*)$ public/$1 [L]
</IfModule>

# Bloquear arquivos sensíveis
<FilesMatch "\.(env|sql|log)$">
    Order allow,deny
    Deny from all
</FilesMatch>

<DirectoryMatch "^/.*(config|src|vendor)/">
    Order deny,allow
    Deny from all
</DirectoryMatch>

# GZIP
<IfModule mod_deflate.c>
    AddOutputFilterByType DEFLATE text/html text/plain text/css application/javascript application/json
</IfModule>

php_flag display_errors Off
php_value upload_max_filesize 10M
php_value max_execution_time 30
```

#### `nginx.conf` (Nginx)

```nginx
server {
    listen 80;
    server_name seu-dominio.com;
    root /var/www/gemini-chatbot/public;
    index index.php;

    location ~ /\.    { deny all; }
    location ~ \.(env|sql|log)$ { deny all; }
    location ~ ^/(config|src|vendor)/ { deny all; }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php8.5-fpm.sock;
    }

    location ~* \.(css|js|jpg|png|gif|ico)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }

    location / { try_files $uri $uri/ =404; }
}
```

---

### 51.15 Instalação, Deploy e Troubleshooting

Quick start em 5 minutos, checklist de produção e solução de problemas comuns:

#### Quick Start (5 Minutos)

```bash
# 1. Obter API Key — https://makersuite.google.com/app/apikey

# 2. Criar banco
mysql -u root -p < database.sql

# 3. Configurar .env
cp .env.example .env
# Editar DB_HOST, DB_NAME, DB_USER, DB_PASS, GEMINI_API_KEY

# 4. Permissões (Linux)
chmod 755 -R .
chmod 777 uploads/
chown -R www-data:www-data .

# 5. Acessar
# Chat:  http://localhost/gemini-chatbot/public/
# Admin: http://localhost/gemini-chatbot/public/admin.php (senha: admin123)
```

#### Checklist de Produção

- ☐ HTTPS/SSL configurado
- ☐ `APP_DEBUG=false` no `.env`
- ☐ Senha do admin alterada
- ☐ `.env` com permissão `600`
- ☐ Firewall habilitado
- ☐ Backup automático do banco
- ☐ OPcache habilitado
- ☐ GZIP ativado
- ☐ Teste em múltiplos navegadores e dispositivos

#### Troubleshooting

| Problema                    | Solução                                                        |
| --------------------------- | -------------------------------------------------------------- |
| "Erro ao conectar ao banco" | Verificar credenciais no `.env` e status do MySQL              |
| "Invalid API key"           | Verificar `GEMINI_API_KEY` — obtenha em makersuite.google.com  |
| "Mensagens não são salvas"  | Verificar se `database.sql` foi executado corretamente         |
| "CSS/JS não carregam"       | Verificar caminhos e `.htaccess`; limpar cache do navegador    |
| "Timeout nas respostas"     | Aumentar `max_execution_time`; verificar conectividade com API |

---

### 🏋️ Exercícios

**Iniciante:**
1. Altere as cores do chatbot via variáveis CSS em `:root`
2. Adicione 3 novas quick actions personalizadas
3. Mude a mensagem de boas-vindas para refletir sua empresa

**Intermediário:**
4. Implemente sistema de "typing speed" — a resposta aparece caractere por caractere
5. Adicione suporte a upload de imagem com preview antes do envio
6. Crie endpoint `/api.php?action=stats` que retorna estatísticas em JSON

**Avançado:**
7. Implemente autenticação JWT no painel admin substituindo o login simples
8. Adicione suporte a WebSocket para notificações em tempo real
9. Crie sistema de "conversation branches" — permitindo ao usuário voltar a pontos anteriores
10. Implemente rate limiting no endpoint da API (máx 10 requisições/minuto por IP)

---

### 🔑 Regras de Ouro do Chatbot

1. **SEMPRE** use `prepared statements` — nunca concatene dados do usuário em SQL
2. **SEMPRE** escape output com `htmlspecialchars()` — previna XSS
3. **SEMPRE** valide e sanitize toda entrada do usuário antes de processar
4. **SEMPRE** proteja a API Key — nunca exponha no frontend ou commits
5. **NUNCA** confie em dados vindos do cliente — valide no backend também
6. **SEMPRE** implemente rate limiting em endpoints públicos
7. **SEMPRE** use HTTPS em produção — especialmente para dados do chat


---

## 98. Integração Gemini API com cURL

Cliente moderno usando Pipe Operator para pós-processamento, `array_first()` do PHP 8.5, `#[\NoDiscard]` e autenticação via header `x-goog-api-key`.

### 98.1 GeminiApiClient

Pipeline funcional: resposta bruta → trim → decode → extrair texto do primeiro candidato:

```php
<?php

declare(strict_types=1);

namespace App\Service;

final class GeminiApiClient
{
    private const string API_URL =
        'https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent';

    public function __construct(
        private readonly string $apiKey,
    ) {}

    #[\NoDiscard]
    public function generateText(string $prompt): ?string
    {
        $payload = [
            'contents' => [
                [
                    'parts' => [
                        ['text' => $prompt],
                    ],
                ],
            ],
        ];

        $handle = curl_init(self::API_URL);

        curl_setopt_array($handle, [
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_POST           => true,
            CURLOPT_POSTFIELDS     => json_encode($payload),
            CURLOPT_TIMEOUT        => 30,
            CURLOPT_HTTPHEADER     => [
                'Content-Type: application/json',
                'x-goog-api-key: ' . $this->apiKey,
            ],
        ]);

        $response = curl_exec($handle);
        $httpCode = curl_getinfo($handle, CURLINFO_HTTP_CODE);
        curl_close($handle);

        if (!is_string($response) || $response === '' || $httpCode >= 400) {
            return null;
        }

        return $response
            |> trim(...)
            |> (fn(string $json): array => json_decode($json, true) ?? [])
            |> $this->extractTextFromResponse(...);
    }

    private function extractTextFromResponse(array $data): ?string
    {
        $candidates = $data['candidates'] ?? [];
        $first      = array_first($candidates);

        if (!$first) {
            return null;
        }

        $parts     = $first['content']['parts'] ?? [];
        $firstPart = array_first($parts);

        return $firstPart['text'] ?? null;
    }
}
```

### 98.2 Conceitos-Chave

1.  **`x-goog-api-key`:** Header de autenticação da API Gemini.
2.  **Estrutura `contents > parts`:** Contrato obrigatório do endpoint `generateContent`.
3.  **`array_first()` (PHP 8.5):** Obtém primeiro candidato sem erros se vazio.
4.  **`#[\NoDiscard]`:** Garante que o texto gerado não seja ignorado.


