# PHP 8.5 — Guia Definitivo e Completo

> **Referência completa de PHP 8.5** combinando tutorial, aprofundamento, casos de uso práticos,
> comparações e alternativas, armadilhas comuns, melhores práticas e exemplos do mundo real.
>
> **Padrão:** PHP 8.5 | **Estilo:** PER-CS v3.0 | **Idioma:** pt-BR (comentários) · en-US (código)
>
> **Baseado em:** W3Schools PHP Tutorial · PHP-FIG PSR Standards · PHP 8.5 Release Notes · OWASP Top 10
>
> **Última revisão:** Abril 2026

---

## Índice Geral das Três Partes

| Parte | Conteúdo | Capítulos |
|-------|----------|-----------|
| **Parte 1** | Tutorial Completo — Referência de sintaxe, todos os recursos PHP 8.5 | 1–84 |
| **Parte 2** | Tutorial Aprofundado — Casos de uso, comparações, armadilhas, exemplos reais | 1–20 |
| **Parte 3** | Guia de Contexto Avançado — Armadilhas adicionais, SOLID, OWASP, performance | 1–18 |

> **Como usar este guia:**
> - **Aprender um tópico novo** → Parte 1 (referência rápida de sintaxe)
> - **Entender por que e quando usar** → Parte 2 (contexto e casos de uso)
> - **Evitar erros e otimizar** → Parte 3 (armadilhas avançadas e boas práticas)

---


---

# PARTE 1 — TUTORIAL COMPLETO (Referência de Sintaxe e Exemplos)

---


1. [Introdução ao PHP](#1-introdução-ao-php)
2. [Instalação e Ambiente](#2-instalação-e-ambiente)
3. [Sintaxe Básica](#3-sintaxe-básica)
4. [Comentários](#4-comentários)
5. [Variáveis](#5-variáveis)
6. [Escopo de Variáveis](#6-escopo-de-variáveis)
7. [echo e print](#7-echo-e-print)
8. [Tipos de Dados](#8-tipos-de-dados)
9. [Strings](#9-strings)
10. [Funções de String](#10-funções-de-string)
11. [Modificação de Strings](#11-modificação-de-strings)
12. [Concatenação de Strings](#12-concatenação-de-strings)
13. [Fatiamento de Strings (Slicing)](#13-fatiamento-de-strings-slicing)
14. [Caracteres de Escape](#14-caracteres-de-escape)
15. [Números](#15-números)
16. [Type Casting (Conversão de Tipos)](#16-type-casting-conversão-de-tipos)
17. [Funções Matemáticas](#17-funções-matemáticas)
18. [Constantes](#18-constantes)
19. [Constantes Mágicas](#19-constantes-mágicas)
20. [Operadores](#20-operadores)
21. [Estruturas Condicionais — if / else](#21-estruturas-condicionais--if--else)
22. [switch vs match](#22-switch-vs-match)
23. [Loops](#23-loops)
24. [Funções](#24-funções)
25. [Arrays](#25-arrays)
26. [PHP 8.5 — Features Exclusivas](#26-php-85--features-exclusivas)
27. [Arrays Multidimensionais](#27-arrays-multidimensionais)
28. [Referência de Funções de Array](#28-referência-de-funções-de-array)
29. [Superglobais](#29-superglobais)
30. [$GLOBALS](#30-globals)
31. [$_SERVER](#31-_server)
32. [$_REQUEST](#32-_request)
33. [$_POST](#33-_post)
34. [$_GET](#34-_get)
35. [Expressões Regulares (RegEx)](#35-expressões-regulares-regex)
36. [Funções de RegEx](#36-funções-de-regex)
37. [Formulários HTML — Coleta de Dados](#37-formulários-html--coleta-de-dados)
38. [Validação de Formulários](#38-validação-de-formulários)
39. [Campos Obrigatórios e Mensagens de Erro](#39-campos-obrigatórios-e-mensagens-de-erro)
40. [Validação de E-mail e URL](#40-validação-de-e-mail-e-url)
41. [Formulário Completo — Exemplo Final](#41-formulário-completo--exemplo-final)
42. [Data e Hora](#42-data-e-hora)
43. [Include e Require](#43-include-e-require)
44. [Manipulação de Arquivos — Leitura](#44-manipulação-de-arquivos--leitura)
45. [Manipulação de Arquivos — Escrita e Criação](#45-manipulação-de-arquivos--escrita-e-criação)
46. [Upload de Arquivos](#46-upload-de-arquivos)
47. [Cookies](#47-cookies)
48. [Sessões (Sessions)](#48-sessões-sessions)
49. [Filtros PHP — Validação e Sanitização](#49-filtros-php--validação-e-sanitização)
50. [Filtros Avançados](#50-filtros-avançados)
51. [Funções de Callback](#51-funções-de-callback)
52. [PHP e JSON](#52-php-e-json)
53. [Exceções (Exceptions)](#53-exceções-exceptions)
54. [Orientação a Objetos — Introdução](#54-orientação-a-objetos--introdução)
55. [Classes e Objetos](#55-classes-e-objetos)
56. [Constructor e Destructor](#56-constructor-e-destructor)
57. [Modificadores de Acesso](#57-modificadores-de-acesso)
58. [Herança (Inheritance)](#58-herança-inheritance)
59. [Constantes de Classe](#59-constantes-de-classe)
60. [Classes Abstratas](#60-classes-abstratas)
61. [Interfaces](#61-interfaces)
62. [Traits](#62-traits)
63. [Métodos Estáticos](#63-métodos-estáticos)
64. [Propriedades Estáticas](#64-propriedades-estáticas)
65. [Namespaces](#65-namespaces)
66. [Iterables e Iterator](#66-iterables-e-iterator)
67. [Banco de Dados com PDO — Introdução](#67-banco-de-dados-com-pdo--introdução)
68. [PDO — Conexão com MySQL](#68-pdo--conexão-com-mysql)
69. [PDO — Criando Banco e Tabelas](#69-pdo--criando-banco-e-tabelas)
70. [PDO — INSERT e lastInsertId()](#70-pdo--insert-e-lastinsertid)
71. [PDO — Inserindo Múltiplos Registros](#71-pdo--inserindo-múltiplos-registros)
72. [PDO — Prepared Statements em Profundidade](#72-pdo--prepared-statements-em-profundidade)
73. [PDO — SELECT (Consultando Dados)](#73-pdo--select-consultando-dados)
74. [PDO — WHERE (Filtrando Dados)](#74-pdo--where-filtrando-dados)
75. [PDO — ORDER BY, LIMIT e Paginação](#75-pdo--order-by-limit-e-paginação)
76. [PDO — DELETE (Excluindo Dados)](#76-pdo--delete-excluindo-dados)
77. [PDO — UPDATE (Atualizando Dados)](#77-pdo--update-atualizando-dados)
78. [XML — Parsers e Tipos](#78-xml--parsers-e-tipos)
79. [XML — SimpleXML Parser](#79-xml--simplexml-parser)
80. [XML — DOM Parser](#80-xml--dom-parser)
81. [XML — Expat Parser (Event-based)](#81-xml--expat-parser-event-based)
82. [AJAX com PHP — Introdução](#82-ajax-com-php--introdução)
83. [AJAX com PHP — Autocomplete e Banco de Dados](#83-ajax-com-php--autocomplete-e-banco-de-dados)
84. [Referência Rápida Final — Índice de Exemplos](#84-referência-rápida-final--índice-de-exemplos)
60. [Classes Abstratas](#60-classes-abstratas)
61. [Interfaces](#61-interfaces)
62. [Traits](#62-traits)
63. [Métodos Estáticos](#63-métodos-estáticos)
64. [Propriedades Estáticas](#64-propriedades-estáticas)
65. [Namespaces](#65-namespaces)
66. [Iterables e Iterator](#66-iterables-e-iterator)
67. [PHP e MySQL — Introdução](#67-php-e-mysql--introdução)

---

## 1. Introdução ao PHP

### O que é PHP?

**PHP** é uma sigla recursiva para *"PHP: Hypertext Preprocessor"*. É uma linguagem de script
server-side amplamente utilizada para criar páginas web dinâmicas e interativas.

Características principais:

- **Open source e gratuito** — disponível em [php.net](https://www.php.net/)
- **Cross-platform** — roda em Windows, Linux, macOS, Unix
- **Compatível** com os principais servidores web (Nginx, Apache, IIS, Cloudflare)
- **Suporte a bancos de dados** — MySQL/MariaDB, PostgreSQL, SQLite, MongoDB, Oracle, etc.
- **Execução no servidor** — o cliente (navegador) recebe apenas o HTML resultante

### O que PHP pode fazer?

- Gerar conteúdo de página dinâmico
- Criar, ler, escrever, deletar e fechar arquivos no servidor
- Coletar dados de formulários
- Enviar e receber cookies
- Adicionar, deletar e modificar dados em bancos de dados
- Controlar acesso de usuários
- Criptografar dados
- Gerar saídas em qualquer formato: HTML, JSON, XML, PDF, imagens

### PHP 8.x — Linha do Tempo de Features Importantes

| Versão | Feature Destacada |
|--------|-------------------|
| PHP 8.0 | JIT Compiler, Union Types, Named Arguments, `match`, `?->` (Nullsafe), Attributes |
| PHP 8.1 | Enums, Readonly Properties, Fibers, Intersection Types |
| PHP 8.2 | Readonly Classes, DNF Types, `true`/`false`/`null` como tipos standalone |
| PHP 8.3 | Typed Class Constants, `json_validate()`, `array_find()` |
| PHP 8.4 | Property Hooks, Asymmetric Visibility, `array_find_key()` |
| **PHP 8.5** | **Pipe Operator (`\|>`), Clone With, `#[\NoDiscard]`, `array_first()`/`array_last()`, URI Extension** |

> ⚠️ **Este guia usa PHP 8.5 como padrão.** Padrões anteriores são marcados como legados.

---

## 2. Instalação e Ambiente

### Opções para começar

**Opção 1 — Hospedagem com suporte a PHP**
A maioria dos provedores de hospedagem já inclui PHP. Basta criar arquivos `.php` no diretório web.

**Opção 2 — Ambiente local**
Para desenvolvimento local, recomenda-se:

- **Linux/macOS:** PHP via gerenciador de pacotes (`apt`, `brew`)
- **Windows:** [XAMPP](https://www.apachefriends.org/) ou [Laragon](https://laragon.org/)
- **Docker:** imagem oficial `php:8.5-fpm`

### Verificando a versão do PHP

```php
<?php

declare(strict_types=1);

// Exibe a versão atual do PHP — útil para confirmar o ambiente
echo PHP_VERSION;           // Ex: 8.5.0
echo phpversion();          // Equivalente
echo PHP_MAJOR_VERSION;     // Exibe: 8
echo PHP_MINOR_VERSION;     // Exibe: 5
```

> 💡 **PHP_VERSION** é uma constante predefinida mais expressiva que `phpversion()`.

---

## 3. Sintaxe Básica

### Abertura e fechamento de tags

Todo código PHP fica dentro das tags `<?php` e `?>`. Em arquivos puramente PHP,
a tag de fechamento `?>` **deve ser omitida** — isso evita espaços em branco acidentais
antes de headers HTTP.

```php
<?php

declare(strict_types=1);

// Arquivo puramente PHP — sem fechamento ?>
echo 'Meu primeiro script PHP!';
```

Quando misturar PHP com HTML (em templates), use assim:

```php
<!DOCTYPE html>
<html lang="pt-BR">
<body>

<h1>Minha primeira página PHP</h1>

<?php
declare(strict_types=1);

echo 'Olá, Mundo!';
?>

</body>
</html>
```

> ⚠️ **Regra PER-CS v3.0:** `<?php` sempre na primeira linha, sozinho.
> `declare(strict_types=1)` obrigatório em todo arquivo PHP.

### Case sensitivity

Palavras-chave do PHP (`echo`, `if`, `else`, `while`, etc.), nomes de classes e funções
**não** são case-sensitive. Mas **variáveis são case-sensitive**.

```php
<?php

declare(strict_types=1);

// Palavras-chave: case-insensitive (mas use sempre minúsculas por convenção)
ECHO 'PHP é flexível, mas...';
echo '...use sempre minúsculas!';

// Variáveis: CASE-SENSITIVE — $color e $COLOR são variáveis DIFERENTES
$color = 'red';
echo $color;   // ✅ Exibe: red
// echo $COLOR; // ❌ Erro: variável indefinida
```

---

## 4. Comentários

Comentários são ignorados pelo interpretador PHP. Servem para documentar o código,
explicar lógica e deixar notas para outros desenvolvedores (ou para você mesmo no futuro).

### Comentário de linha única

Use `//` para comentários inline e no início de linha:

```php
<?php

declare(strict_types=1);

// Calcula o desconto aplicado ao preço original
$discount = 0.15;

$price = 100.0;
$finalPrice = $price - ($price * $discount); // Remove o percentual de desconto
echo $finalPrice;
```

> ⚠️ O `#` também é suportado para comentários de linha, mas **não é recomendado** pelo PER-CS v3.0.
> Use sempre `//`.

### Comentário de múltiplas linhas

Use `/* ... */` para blocos de comentário:

```php
<?php

declare(strict_types=1);

/*
 * Esta função valida um endereço de e-mail recebido como input do usuário.
 * Retorna o e-mail sanitizado ou lança uma exceção em caso de formato inválido.
 * Nunca confie em dados externos sem validação!
 */
function validateEmail(string $email): string
{
    $sanitized = filter_var($email, FILTER_VALIDATE_EMAIL);

    if ($sanitized === false) {
        throw new \InvalidArgumentException('Formato de e-mail inválido.');
    }

    return $sanitized;
}
```

### PHPDoc — Documentação Formal

Para funções, classes e métodos, use blocos PHPDoc. Descrições em pt-BR, tags em inglês:

```php
<?php

declare(strict_types=1);

/**
 * Calcula o preço final após aplicar o desconto percentual.
 *
 * @param float $originalPrice Preço original do produto
 * @param float $discountRate  Taxa de desconto entre 0.0 e 1.0
 *
 * @return float Preço final após o desconto
 *
 * @throws \InvalidArgumentException Se a taxa de desconto estiver fora do intervalo válido
 */
function applyDiscount(float $originalPrice, float $discountRate): float
{
    if ($discountRate < 0.0 || $discountRate > 1.0) {
        throw new \InvalidArgumentException(
            "Taxa de desconto inválida: {$discountRate}. Use um valor entre 0.0 e 1.0."
        );
    }

    return $originalPrice * (1.0 - $discountRate);
}
```

---

## 5. Variáveis

### Regras para nomes de variáveis

- Iniciam com `$` seguido do nome
- O nome deve começar com letra ou `_` (nunca com número)
- Podem conter letras, números e `_`
- São **case-sensitive** (`$age` ≠ `$Age` ≠ `$AGE`)
- Siga **camelCase** (PER-CS v3.0): `$userName`, `$totalAmount`, `$isActive`

### Declaração e atribuição

```php
<?php

declare(strict_types=1);

// Variáveis simples com tipo implícito
$userName = 'Maria Silva';   // string
$userAge  = 28;              // int
$userScore = 9.75;           // float
$isActive = true;            // bool
$lastLogin = null;           // null

// Exibe o valor de cada variável
echo $userName;
echo $userAge;
```

> ⚠️ **PHP é loosely typed por padrão.** Mas com `declare(strict_types=1)`,
> o interpretador aplica verificação estrita de tipos em chamadas de função com type hints.

### Tipos de dados suportados

| Tipo | Exemplo | Descrição |
|------|---------|-----------|
| `string` | `'Olá'` | Sequência de caracteres |
| `int` | `42` | Número inteiro |
| `float` | `3.14` | Número decimal (ponto flutuante) |
| `bool` | `true` / `false` | Valor booleano |
| `array` | `[1, 2, 3]` | Coleção de valores |
| `object` | `new MyClass()` | Instância de classe |
| `null` | `null` | Ausência de valor |
| `resource` | `fopen(...)` | Referência a recurso externo |

### Inspecionando variáveis com var_dump()

```php
<?php

declare(strict_types=1);

// var_dump() é a ferramenta de debug mais útil — exibe tipo E valor
var_dump(42);           // int(42)
var_dump('PHP 8.5');    // string(6) "PHP 8.5"
var_dump(3.14);         // float(3.14)
var_dump(true);         // bool(true)
var_dump([1, 2, 3]);    // array(3) { [0]=> int(1) ... }
var_dump(null);         // NULL
```

### Atribuição múltipla

```php
<?php

declare(strict_types=1);

// Atribui o mesmo valor a múltiplas variáveis em uma linha
$x = $y = $z = 0;
```

---

## 6. Escopo de Variáveis

O **escopo** define em quais partes do código uma variável pode ser acessada.

### Escopo global

Variáveis declaradas **fora** de funções têm escopo global, mas **não são automaticamente
acessíveis dentro de funções**:

```php
<?php

declare(strict_types=1);

$siteName = 'PHP Dev';  // Escopo global

function showSiteName(): void
{
    // ❌ Não funciona — variável global não é visível dentro da função por padrão
    // echo $siteName;
    echo 'Variável global não acessível diretamente.';
}

showSiteName();
echo $siteName; // ✅ Funciona aqui fora
```

> 💡 **Boa prática:** Em vez de usar `global`, passe valores como parâmetros de função.
> Isso torna o código mais testável e previsível.

### Escopo local

Variáveis declaradas **dentro** de funções existem apenas enquanto a função executa:

```php
<?php

declare(strict_types=1);

function calculateTotal(): float
{
    $subtotal = 100.0;  // Escopo local — existe apenas nesta função
    $tax = 0.12;

    return $subtotal * (1 + $tax);
}

echo calculateTotal();  // ✅ Funciona
// echo $subtotal;      // ❌ Erro: variável indefinida fora da função
```

### Escopo estático

Variáveis `static` mantêm seu valor entre chamadas da função:

```php
<?php

declare(strict_types=1);

// Contador de chamadas — mantém o valor entre execuções
function countCalls(): int
{
    static $callCount = 0; // Inicializado apenas na primeira chamada
    $callCount++;

    return $callCount;
}

echo countCalls(); // 1
echo countCalls(); // 2
echo countCalls(); // 3
```

### Passando valores globais para funções (forma correta)

```php
<?php

declare(strict_types=1);

$basePrice = 200.0;
$taxRate = 0.15;

// ✅ CORRETO: Passe como parâmetro — não use 'global'
function calculateFinalPrice(float $price, float $tax): float
{
    return $price * (1 + $tax);
}

echo calculateFinalPrice($basePrice, $taxRate); // 230.0
```

---

## 7. echo e print

Ambos exibem dados na saída, mas há diferenças:

| Característica | `echo` | `print` |
|----------------|--------|---------|
| Valor de retorno | Nenhum | Sempre `1` |
| Múltiplos argumentos | ✅ Sim | ❌ Não (apenas 1) |
| Performance | Ligeiramente mais rápido | Ligeiramente mais lento |
| Uso em expressão | ❌ Não | ✅ Sim |

> 💡 **Use sempre `echo`** no dia a dia. `print` é raramente necessário.

```php
<?php

declare(strict_types=1);

// echo — forma mais comum de output
echo 'Olá, Mundo!';
echo 'PHP ', '8.5 ', 'é incrível!'; // Aceita múltiplos argumentos

// echo com HTML
echo '<h2>PHP é divertido!</h2>';
echo '<p>Aprendendo PHP 8.5</p>';

// Variáveis no echo
$siteName = 'PHP Dev';
$version = '8.5';

// ✅ Interpolação com aspas duplas — forma preferida para strings simples
echo "Bem-vindo ao {$siteName} v{$version}!";

// ✅ Concatenação com aspas simples — preferida para strings fixas (sem variáveis)
echo 'Site: ' . $siteName . ' | Versão: ' . $version;
```

### Aspas simples vs. duplas

```php
<?php

declare(strict_types=1);

$name = 'Carlos';

// Aspas DUPLAS: interpola variáveis e processa \n, \t, etc.
echo "Olá, {$name}!\n";    // Exibe: Olá, Carlos! (com quebra de linha)
echo "Tab:\there\n";        // Exibe: Tab:    here

// Aspas SIMPLES: tudo é literal — mais performático para strings fixas
echo 'Olá, {$name}!\n';    // Exibe literalmente: Olá, {$name}!\n
echo 'Texto fixo sem variáveis.';
```

---

## 8. Tipos de Dados

PHP é uma linguagem de tipagem dinâmica — o tipo de uma variável é determinado pelo valor atribuído. Com `declare(strict_types=1)`, o PHP aplica verificação estrita de tipos nas chamadas de função, tornando o código mais previsível e seguro.

**Quando usar cada tipo:**
- `string` — texto, CPF, slugs, datas em formato texto, qualquer sequência de caracteres
- `int` — IDs, contadores, índices, quantidades, **valores monetários em centavos**
- `float` — coordenadas GPS, medidas físicas, taxas percentuais (nunca para dinheiro!)
- `bool` — estados binários (`$isActive`, `$hasPermission`, `$isVerified`)
- `array` — coleções de dados, listas, mapas chave→valor
- `null` — ausência intencional de valor (campo não preenchido, resultado não encontrado)
- `object` — instâncias de classes, estruturas de dados complexas

> ⚠️ **Armadilha crítica — float para dinheiro:** `0.1 + 0.2` em PHP resulta em `0.30000000000000004`, não `0.3`. **Nunca use float para valores monetários.** Armazene em centavos como `int` e divida por 100 apenas na exibição.

> 💡 **Melhores práticas:** Use `var_dump()` para inspecionar tipo e valor durante o desenvolvimento. Em produção, use `get_debug_type()` (PHP 8.0+) que retorna o nome correto (`"int"` em vez de `"integer"`).

### String

```php
<?php

declare(strict_types=1);

$greeting = 'Olá, Mundo!';
var_dump($greeting); // string(11) "Olá, Mundo!"
```

### Integer (int)

Número inteiro sem parte decimal. Suporta notações decimal, hexadecimal, octal e binária:

```php
<?php

declare(strict_types=1);

$decimal     = 255;      // Base 10
$hexadecimal = 0xFF;     // Base 16 (prefixo 0x) — também 255
$octal       = 0377;     // Base 8 (prefixo 0)   — também 255
$binary      = 0b11111111; // Base 2 (prefixo 0b) — também 255

// Separador de milhar com underscore (PHP 7.4+) — melhora legibilidade
$million = 1_000_000;
$price   = 29_990;

var_dump($million); // int(1000000)

// Limites do sistema
echo PHP_INT_MAX;  // 9223372036854775807 (em sistemas 64-bit)
echo PHP_INT_MIN;  // -9223372036854775808
echo PHP_INT_SIZE; // 8 (bytes)
```

### Float

```php
<?php

declare(strict_types=1);

$price    = 9.99;
$pi       = 3.14159265;
$scientific = 1.5e3;    // 1500.0
$small      = 1.5e-3;   // 0.0015

// Separador de milhar em floats (PHP 7.4+)
$bigFloat = 1_234_567.89;

echo PHP_FLOAT_MAX;     // 1.7976931348623E+308
echo PHP_FLOAT_EPSILON; // Menor diferença representável
```

### Bool

```php
<?php

declare(strict_types=1);

$isLoggedIn   = true;
$hasPermission = false;

// Valores que resultam em false quando convertidos para bool:
// 0, 0.0, '', '0', [], null
var_dump((bool) 0);    // bool(false)
var_dump((bool) '');   // bool(false)
var_dump((bool) []);   // bool(false)
var_dump((bool) -1);   // bool(true) — qualquer não-zero é true!
```

### Null

```php
<?php

declare(strict_types=1);

// Variável criada sem valor é automaticamente null
$data = null;
var_dump($data); // NULL

// Verificação segura com nullsafe e coalescing
$userName = null;
$displayName = $userName ?? 'Visitante'; // Operador null coalescing (??)
echo $displayName; // Visitante
```

### Object

```php
<?php

declare(strict_types=1);

// ✅ MODERNO PHP 8.5: Constructor Property Promotion + readonly + final
final class Car
{
    public function __construct(
        public readonly string $brand,
        public readonly string $model,
        public readonly int    $year,
    ) {}

    public function describe(): string
    {
        return "{$this->year} {$this->brand} {$this->model}";
    }
}

$myCar = new Car(brand: 'Toyota', model: 'Corolla', year: 2025);
echo $myCar->describe(); // 2025 Toyota Corolla
var_dump($myCar);
```

```php
// ❌ LEGACY CODE — PHP < 8.0
// ✅ Alternativa moderna: Constructor Property Promotion (veja acima)
class CarLegacy {
    public $color;
    public $model;
    public function __construct($color, $model) {
        $this->color = $color;
        $this->model = $model;
    }
}
```

---

## 9. Strings

Uma string é uma sequência de caracteres. Em PHP, strings podem ser delimitadas por aspas simples `'...'`, aspas duplas `"..."`, Heredoc (`<<<LABEL`) ou Nowdoc (`<<<'LABEL'`).

**Quando usar cada forma:**
- **Aspas simples** — strings estáticas sem variáveis ou sequências de escape. São ligeiramente mais rápidas pois o PHP não precisa analisar o conteúdo.
- **Aspas duplas** — quando há variáveis a interpolar (`{$name}`) ou sequências de escape (`\n`, `\t`).
- **Heredoc** — blocos de texto multiline com interpolação de variáveis (templates HTML, SQL complexo).
- **Nowdoc** — blocos multiline SEM interpolação (código, templates com `$` e `{}`).

> ⚠️ **Armadilha — UTF-8:** `strlen()` conta **bytes**, não caracteres. `'Olá'` tem 3 caracteres mas 4 bytes em UTF-8. Para qualquer texto em português (ou outro idioma com acentos), use sempre as funções `mb_*` (`mb_strlen`, `mb_substr`, `mb_strtolower`).

> 💡 **Melhor prática:** Prefira aspas simples para strings sem variáveis — o código fica mais legível e indica claramente que não há substituição de variáveis.

### Aspas simples vs. duplas — resumo completo

```php
<?php

declare(strict_types=1);

$name    = 'Ana';
$product = 'PHP 8.5';

// Aspas DUPLAS — interpolação e sequências de escape
echo "Olá, {$name}!\n";              // Quebra de linha real
echo "Produto: {$product}\tPreço: R\$9,99\n"; // Tab + cifrão escapado

// Aspas SIMPLES — literal puro, sem processamento
echo 'Olá, {$name}!\n';             // Saída literal: Olá, {$name}!\n
echo 'Mais rápido para strings fixas sem variáveis.';
```

| Feature | Simples `'` | Duplas `"` |
|---------|-------------|------------|
| Interpolação de variáveis | ❌ Não | ✅ Sim |
| `\n`, `\t`, `\r` | ❌ Literal | ✅ Processado |
| `\'` e `\\` | ✅ Escape | ✅ Escape |
| Performance | Ligeiramente mais rápido | Ligeiramente mais lento |
| Uso recomendado | Strings fixas, sem variáveis | Strings com variáveis ou escapes |

---

## 10. Funções de String

PHP possui mais de 100 funções nativas para manipulação de strings. As mais usadas no dia a dia são divididas em dois grupos:

**Funções de byte (padrão):** `strlen()`, `substr()`, `strtolower()` — operam em bytes. Funcionam corretamente apenas com ASCII. Para texto em português ou qualquer idioma com acentos, produzem resultados incorretos.

**Funções multibyte (`mb_*`):** `mb_strlen()`, `mb_substr()`, `mb_strtolower()` — operam em caracteres Unicode. **Use estas para qualquer texto em produção.**

**Funções de busca modernas (PHP 8.0+):**
- `str_contains()` — substitui o padrão propenso a erros `strpos() !== false`
- `str_starts_with()` — verifica prefixo de forma semântica
- `str_ends_with()` — verifica sufixo de forma semântica

> ⚠️ **Armadilha — `strpos()` retorna `0` ou `false`:** A posição `0` (início da string) é falsy em PHP. Sempre compare com `!== false`, nunca com `if (!strpos(...))`.

> 💡 **Melhor prática:** Para projetos novos, prefira sempre `str_contains()`, `str_starts_with()` e `str_ends_with()` — são mais legíveis e não têm a armadilha do `strpos()`.

### strlen() — comprimento da string

```php
<?php

declare(strict_types=1);

$message = 'Olá, PHP 8.5!';
echo strlen($message); // 14
```

> ⚠️ `strlen()` conta **bytes**, não caracteres. Para UTF-8 com acentos, use `mb_strlen()`:

```php
<?php

declare(strict_types=1);

$text = 'Olá';
echo strlen($text);    // 4 (ô ocupa 2 bytes em UTF-8)
echo mb_strlen($text); // 3 (3 caracteres reais) — ✅ Correto para UTF-8
```

### str_word_count() — contagem de palavras

```php
<?php

declare(strict_types=1);

$sentence = 'PHP é uma linguagem poderosa';
echo str_word_count($sentence); // 5
```

### str_contains() — verifica se contém substring (PHP 8.0+)

```php
<?php

declare(strict_types=1);

$text = 'Eu realmente amo PHP 8.5!';

// ✅ MODERNO: str_contains() — PHP 8.0+
var_dump(str_contains($text, 'amo'));   // bool(true)
var_dump(str_contains($text, 'AMO'));   // bool(false) — case-sensitive!

// ❌ LEGACY CODE — PHP < 8.0
// ✅ Alternativa moderna: str_contains() (acima)
// $found = strpos($text, 'amo') !== false; // Verboso e propício a erros
```

### str_starts_with() e str_ends_with() — (PHP 8.0+)

```php
<?php

declare(strict_types=1);

$filename = 'relatorio-2025.pdf';

// ✅ MODERNO: verificações claras e semânticas
var_dump(str_starts_with($filename, 'relatorio')); // bool(true)
var_dump(str_ends_with($filename, '.pdf'));         // bool(true)
var_dump(str_ends_with($filename, '.PDF'));         // bool(false) — case-sensitive
```

### strpos() — posição de uma substring

```php
<?php

declare(strict_types=1);

$text = 'PHP é ótimo. PHP é rápido.';

// Retorna o índice da PRIMEIRA ocorrência (base 0), ou false se não encontrar
$position = strpos($text, 'PHP');
var_dump($position); // int(0)

// Para a segunda ocorrência, use o terceiro parâmetro (offset)
$secondPosition = strpos($text, 'PHP', 1);
var_dump($secondPosition); // int(13)

// ⚠️ Sempre compare com === false (não == false), pois posição 0 é falsy!
if (strpos($text, 'PHP') !== false) {
    echo 'Encontrado!';
}
```

---

## 11. Modificação de Strings

Modificar strings é uma das operações mais frequentes em PHP — normalizar inputs de usuário, formatar dados para exibição, converter entre formatos. PHP oferece funções específicas para cada transformação.

**Casos de uso comuns:**
- `trim()` — limpar espaços antes de validar ou armazenar inputs de formulário
- `strtolower()` / `mb_strtolower()` — normalizar e-mails e usernames para comparação
- `str_replace()` — substituir placeholders em templates, criar slugs de URL
- `explode()` / `implode()` — converter entre strings CSV e arrays

> 💡 **PHP 8.5 — Pipe Operator:** Em vez de aninhar chamadas de função (difícil de ler da direita para a esquerda), use o pipe operator `|>` para encadear transformações da esquerda para a direita, como uma "linha de montagem" de dados.

> ⚠️ **Armadilha — strtolower() com acentos:** `strtolower('JOÃO')` retorna `'joÃo'` — não funciona para caracteres não-ASCII. Use sempre `mb_strtolower()` para texto em português.

> ⚠️ **Armadilha — concatenação em loop:** `$str .= 'item'` dentro de um loop com muitas iterações é O(n²) — cria uma nova string a cada passo. Acumule em array e use `implode()` ao final.

### Pipeline de transformação — PHP 8.5 com Pipe Operator

```php
<?php

declare(strict_types=1);

// ✅ MODERNO PHP 8.5: Pipe Operator para encadeamento legível
$rawInput = '  PHP É Incrível!  ';

$slug = $rawInput
    |> trim(...)                                                    // Remove espaços
    |> strtolower(...)                                             // Minúsculas
    |> (fn(string $s): string => str_replace(' ', '-', $s))       // Espaços → hífens
    |> (fn(string $s): string => str_replace(['é', 'ê', 'è'], 'e', $s)); // Normaliza acentos

echo $slug; // php-e-incrivel!

// ❌ LEGACY CODE — PHP < 8.5
// ✅ Alternativa moderna: pipe operator (acima)
// $slug = str_replace(' ', '-', strtolower(trim($rawInput))); // Difícil de ler
```

### Funções de modificação individuais

```php
<?php

declare(strict_types=1);

$text = 'Hello World!';

// Maiúsculas / minúsculas
echo strtoupper($text);   // HELLO WORLD!
echo strtolower($text);   // hello world!

// Substituição de texto
echo str_replace('World', 'PHP 8.5', $text); // Hello PHP 8.5!

// Inversão
echo strrev($text); // !dlroW olleH

// Remoção de espaços nas bordas
$padded = '   Texto com espaços   ';
echo trim($padded);       // 'Texto com espaços' (ambos os lados)
echo ltrim($padded);      // 'Texto com espaços   ' (só esquerda)
echo rtrim($padded);      // '   Texto com espaços' (só direita)

// Explosão (split) em array
$csv = 'PHP,Python,JavaScript,Go';
$languages = explode(',', $csv);
print_r($languages); // Array com 4 elementos

// Implosão (join) de array em string
echo implode(' | ', $languages); // PHP | Python | JavaScript | Go
```

---

## 12. Concatenação de Strings

Em PHP, o operador de concatenação é o ponto `.` (não o `+` como em JavaScript). O operador `.=` acumula texto em uma variável existente.

**Quando usar concatenação vs interpolação:**
- **Concatenação `.`** — strings com aspas simples, expressões complexas, quando a lógica precisa ficar explícita
- **Interpolação `"...{$var}..."`** — strings com poucas variáveis simples, mais legível para templates
- **`sprintf()`** — quando há formatação numérica, alinhamento, ou o template precisa ser reutilizável/traduzível

> ⚠️ **Armadilha — concatenação em loop:** Usar `.=` em loops com milhares de iterações é lento (O(n²)). Prefira acumular em `array` e usar `implode()` uma única vez no final.

> 💡 **Melhor prática:** Para templates com muitas variáveis, use interpolação com aspas duplas e chaves `{$var}` — é mais legível que concatenações longas. Para formatação numérica precisa (casas decimais, padding), use `sprintf()` ou `number_format()`.

### Operador `.` e `.=`

```php
<?php

declare(strict_types=1);

// Concatenação com .
$firstName = 'Maria';
$lastName  = 'Silva';
$fullName  = $firstName . ' ' . $lastName;
echo $fullName; // Maria Silva

// Concatenação acumulativa com .=
$message  = 'PHP ';
$message .= '8.5 ';
$message .= 'é incrível!';
echo $message; // PHP 8.5 é incrível!
```

### Interpolação — forma recomendada para strings com variáveis

```php
<?php

declare(strict_types=1);

$productName = 'Notebook';
$price       = 2999.90;
$stock       = 15;

// ✅ Interpolação com aspas duplas — mais legível
echo "Produto: {$productName} | Preço: R$ {$price} | Estoque: {$stock} unidades";

// Interpolação com expressões (use llaves para clareza)
$items = ['maçã', 'banana', 'laranja'];
echo "Primeiro item: {$items[0]}";
```

---

## 13. Fatiamento de Strings (Slicing)

Fatiar uma string significa extrair uma parte dela a partir de uma posição e com um comprimento definidos. A função `substr()` é a ferramenta padrão — e `mb_substr()` é sua versão segura para UTF-8.

**Casos de uso práticos:**
- Truncar descrições longas para exibição em cards (`mb_substr($desc, 0, 150) . '…'`)
- Extrair extensão de arquivo (`substr($filename, strrpos($filename, '.') + 1)`)
- Obter os últimos N caracteres de um token ou código
- Remover um prefixo ou sufixo conhecido de uma string

**Índices negativos:** contam a partir do **final** da string. `-1` é o último caractere, `-4` são os últimos 4.

> ⚠️ **Armadilha — substr() com UTF-8:** `substr('Ação', 0, 2)` pode retornar caracteres corrompidos porque opera em bytes. Use sempre `mb_substr()` para texto em português ou qualquer idioma com acentos.

> 💡 **Melhor prática:** Crie uma função utilitária `truncate()` que usa `mb_strlen()` e `mb_substr()` para truncar texto de forma segura — reutilize em todo o projeto em vez de escrever a lógica repetidamente.

### substr() — extrai parte de uma string

```php
<?php

declare(strict_types=1);

$text = 'Hello, PHP 8.5!';
//       0123456789...

// substr($string, $start, $length)
echo substr($text, 7, 3);   // 'PHP' (início no índice 7, 3 chars)
echo substr($text, 7);      // 'PHP 8.5!' (do índice 7 até o fim)

// Índices negativos contam do fim da string
echo substr($text, -4);     // '8.5!' (últimos 4 caracteres)
echo substr($text, -4, 3);  // '8.5' (3 chars a partir do -4)

// Length negativo: exclui N caracteres do fim
echo substr($text, 7, -1);  // 'PHP 8.5' (do índice 7, excluindo o último char)
```

### mb_substr() — para strings UTF-8 (recomendado)

```php
<?php

declare(strict_types=1);

// ✅ Para qualquer texto com caracteres especiais, use mb_substr()
$text = 'Ação de PHP';
echo mb_substr($text, 0, 4); // 'Ação' (4 caracteres reais, não bytes)
```

---

## 14. Caracteres de Escape

Caracteres de escape permitem inserir caracteres especiais dentro de strings — como aspas dentro de uma string delimitada por aspas, ou caracteres de controle como quebra de linha e tabulação.

**Quando usar:**
- `\"` / `\'` — incluir o mesmo tipo de aspas usado para delimitar a string
- `\n` — quebras de linha em e-mails, logs, arquivos de texto gerados pelo PHP
- `\t` — separadores em CSVs tabulados, alinhamento em saídas de console
- `\$` — exibir o símbolo `$` literalmente dentro de aspas duplas
- `\u{XXXX}` — caracteres Unicode por código (emojis, símbolos especiais)

> ⚠️ **Armadilha — escape em aspas simples:** Dentro de aspas simples, **apenas** `\'` e `\\` são processados. Todos os outros escapes (`\n`, `\t`, etc.) são tratados como texto literal — o que pode ser uma surpresa.

> 💡 **Melhor prática:** Em vez de usar `\n` para quebras de linha no código, prefira a constante `PHP_EOL` — ela usa a quebra de linha correta para o sistema operacional atual (`\r\n` no Windows, `\n` no Linux/macOS).

```php
<?php

declare(strict_types=1);

// Aspas dentro de strings
$msg1 = "Ela disse: \"Olá!\"";         // Aspas duplas escapadas em string dupla
$msg2 = 'Ele respondeu: \'Oi!\'';      // Aspas simples escapadas em string simples
$msg3 = "String com \$variable literal"; // Cifrão escapado

echo $msg1; // Ela disse: "Olá!"
echo $msg2; // Ele respondeu: 'Oi!'
echo $msg3; // String com $variable literal
```

### Tabela de sequências de escape

| Código | Resultado | Descrição |
|--------|-----------|-----------|
| `\\` | `\` | Barra invertida literal |
| `\'` | `'` | Aspas simples (apenas em `'...'`) |
| `\"` | `"` | Aspas duplas (apenas em `"..."`) |
| `\$` | `$` | Cifrão literal |
| `\n` | Nova linha | Line Feed (LF) |
| `\r` | Retorno de carro | Carriage Return (CR) |
| `\t` | Tabulação | Tab |
| `\f` | Form Feed | Avanço de página |
| `\ooo` | Valor octal | Ex: `\101` = `A` |
| `\xhh` | Valor hexadecimal | Ex: `\x41` = `A` |
| `\u{hhhh}` | Unicode | Ex: `\u{1F600}` = 😀 |

---

## 15. Números

PHP suporta três tipos numéricos principais: `int`, `float` e strings numéricas. Cada um tem comportamentos específicos que é essencial conhecer.

**Quando usar cada tipo:**
- `int` — IDs, contadores, quantidades, **valores monetários em centavos** (`$priceCents = 999`)
- `float` — coordenadas geográficas, medidas físicas, taxas de conversão (nunca para valores monetários finais)
- Strings numéricas — inputs de formulário antes de validar; use `filter_var()` para converter com segurança

**Valores especiais:**
- `INF` / `-INF` — resultado de operações fora do range do float (ex: `1.9e308 * 10`)
- `NAN` — resultado de operação matemática inválida (ex: `acos(8)`)

> ⚠️ **Armadilha crítica — float para dinheiro:** Floats em binário não representam exatamente a maioria das frações decimais. `0.1 + 0.2` não é `0.3`. Para cálculos financeiros, armazene valores em **centavos como `int`** e use `bcmath` para cálculos complexos.

> ⚠️ **Armadilha — is_nan() com cast em PHP 8.5:** Cast de `NAN` para int gera warning. Sempre verifique com `is_nan()` antes de converter.

> 💡 **Melhor prática:** Use `PHP_INT_MAX`, `PHP_FLOAT_EPSILON` e `PHP_FLOAT_MAX` para verificar limites em vez de hardcodar valores numéricos.

### Tipos numéricos em PHP

```php
<?php

declare(strict_types=1);

// Verificação de tipo numérico
$intValue   = 42;
$floatValue = 3.14;
$numString  = '123';    // String numérica

var_dump(is_int($intValue));       // bool(true)
var_dump(is_float($floatValue));   // bool(true)
var_dump(is_numeric($numString));  // bool(true) — string que representa número

// Limites
echo PHP_INT_MAX;           // Maior inteiro suportado
echo PHP_FLOAT_MAX;         // Maior float suportado
echo PHP_FLOAT_EPSILON;     // Diferença mínima entre floats
```

### Infinito e NaN

```php
<?php

declare(strict_types=1);

// Infinito — valor fora do range de float
$infinite = 1.9e308 * 10;
var_dump(is_infinite($infinite)); // bool(true)
var_dump(is_finite($infinite));   // bool(false)

// NaN — resultado de operação matemática inválida
$nan = acos(8); // Arco cosseno de valor > 1 é matematicamente impossível
var_dump($nan);         // float(NAN)
var_dump(is_nan($nan)); // bool(true)

// ⚠️ PHP 8.5: Verifique com is_nan() ANTES de fazer cast de NAN
// Cast de NAN para int gera warning em PHP 8.5
if (!is_nan($nan)) {
    $intValue = (int) $nan;
}
```

### Conversão para inteiro

```php
<?php

declare(strict_types=1);

// intval() para conversão controlada
echo intval(23.9);      // 23 (trunca, não arredonda)
echo intval('42px');    // 42 (para no primeiro char não-numérico)
echo intval('hello');   // 0

// ⚠️ PHP 8.5: Cast float→int com perda de dados gera warning
$pi = 3.14159;
// $int = (int) $pi; // ⚠️ Warning se a parte decimal for significativa
$int = intval($pi);   // ✅ Forma mais explícita e segura
```

---

## 16. Type Casting (Conversão de Tipos)

Type casting é a conversão explícita de um valor de um tipo para outro. Em vez de deixar o PHP fazer conversões implícitas (que podem ser surpreendentes), você declara exatamente o tipo que quer.

**Casos de uso práticos:**
- `(int)` — converter parâmetros de URL antes de usar em queries: `(int) $_GET['id']`
- `(string)` — converter valores para log ou mensagens de exibição
- `(bool)` — normalizar inputs de formulários checkbox (`'on'`, `'1'`, `true` → `bool`)
- `(array)` — garantir que uma variável seja sempre array ao iterar

**Comparação: `(int)` vs `intval()` vs `filter_var()`:**
- `(int)` — rápido, trunca, pode gerar warning com float em PHP 8.5
- `intval($val, 10)` — explícito sobre a base numérica, evita surpresas com octal
- `filter_var($val, FILTER_VALIDATE_INT)` — valida E converte, retorna `false` se inválido

> ⚠️ **Armadilha — (bool) com string 'false':** `(bool) 'false'` retorna `true`! Qualquer string não-vazia é truthy — exceto `'0'`. Para converter strings `'true'`/`'false'`, use `filter_var($val, FILTER_VALIDATE_BOOLEAN)`.

> ⚠️ **Depreciação PHP 8.5:** Os aliases `(boolean)`, `(integer)`, `(double)` e `(binary)` estão depreciados. Use apenas `(bool)`, `(int)`, `(float)` e `(string)`.

> 💡 **Melhor prática:** Com `declare(strict_types=1)`, o PHP aplica verificação de tipos em chamadas de função — o que reduz a necessidade de cast manual e torna bugs de tipo visíveis em vez de silenciosos.

O type casting converte explicitamente um valor de um tipo para outro.

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.5: Operadores de cast modernos
$intValue   = 42;
$floatValue = 3.14;
$strValue   = 'hello';
$boolValue  = true;
$nullValue  = null;

// Cast para string
var_dump((string) $intValue);   // string(2) "42"
var_dump((string) $floatValue); // string(4) "3.14"
var_dump((string) $boolValue);  // string(1) "1"
var_dump((string) $nullValue);  // string(0) ""

// Cast para int
var_dump((int) $floatValue);    // int(3) — trunca a parte decimal
var_dump((int) '25px');         // int(25)
var_dump((int) 'hello');        // int(0)
var_dump((int) true);           // int(1)
var_dump((int) false);          // int(0)
var_dump((int) null);           // int(0)

// Cast para float
var_dump((float) '3.99 kg');    // float(3.99)
var_dump((float) true);         // float(1)

// Cast para bool — false se: 0, 0.0, '', '0', [], null
var_dump((bool) 0);             // bool(false)
var_dump((bool) '');            // bool(false)
var_dump((bool) []);            // bool(false)
var_dump((bool) -1);            // bool(true) — qualquer não-zero é true!
var_dump((bool) 'false');       // bool(true) — string não-vazia é true!
```

> ⚠️ **Depreciações PHP 8.5:** Os aliases antigos `(boolean)`, `(integer)`, `(double)` e `(binary)`
> estão **depreciados**. Use sempre `(bool)`, `(int)`, `(float)` e `(string)`.

```php
// ❌ LEGACY CODE — PHP < 8.5 (depreciado em 8.5)
// $val = (boolean) $x; // ⚠️ Depreciado
// $val = (integer) $x; // ⚠️ Depreciado
// $val = (double)  $x; // ⚠️ Depreciado

// ✅ Alternativa moderna:
// $val = (bool)  $x;
// $val = (int)   $x;
// $val = (float) $x;
```

### Cast para array e object

```php
<?php

declare(strict_types=1);

// Escalar → array indexado com um elemento
$arr = (array) 42;
var_dump($arr); // array(1) { [0]=> int(42) }

// null → array vazio
$empty = (array) null;
var_dump($empty); // array(0) {}

// Object → array associativo (propriedades como chaves)
final class Point
{
    public function __construct(
        public readonly float $x,
        public readonly float $y,
    ) {}
}

$point = new Point(x: 3.0, y: 4.0);
$arr   = (array) $point;
var_dump($arr); // array(2) { ["x"]=> float(3) ["y"]=> float(4) }
```

---

## 17. Funções Matemáticas

PHP inclui um conjunto completo de funções matemáticas nativas — nenhuma extensão adicional necessária para operações cotidianas.

**Casos de uso práticos:**
- `round()`, `ceil()`, `floor()` — arredondar preços, calcular páginas (`ceil($total / $perPage)`)
- `abs()` — calcular diferença entre dois valores sem importar a ordem
- `min()` / `max()` — validar ranges, limitar valores dentro de intervalos aceitos
- `random_int()` — gerar tokens, códigos de verificação, embaralhar itens **com segurança criptográfica**
- `sqrt()`, `pow()` — cálculos geométricos, algoritmos matemáticos

**Comparação: `rand()` vs `random_int()`:**
| | `rand()` | `random_int()` |
|--|----------|----------------|
| Criptograficamente seguro | ❌ Não | ✅ Sim |
| Uso recomendado | Jogos, demos, testes | Tokens, senhas, IDs únicos |
| Disponível desde | PHP 4 | PHP 7.0 |

> ⚠️ **Armadilha — `rand()` para segurança:** Nunca use `rand()` ou `mt_rand()` para gerar tokens de segurança, links de redefinição de senha ou qualquer valor que precise ser imprevisível. Use `random_int()` ou `random_bytes()`.

> 💡 **Melhor prática:** Use `PHP_ROUND_HALF_EVEN` (arredondamento bancário) para cálculos financeiros — evita acúmulo sistemático de erro ao arredondar valores `.5` sempre para o mesmo lado.

```php
<?php

declare(strict_types=1);

// Constante Pi
echo M_PI;        // 3.1415926535898
echo pi();        // 3.1415926535898 (função equivalente)

// Mínimo e máximo
echo min(0, 150, -8, -200);  // -200
echo max(0, 150, -8, -200);  // 150

// Valor absoluto
echo abs(-6.7);  // 6.7

// Raiz quadrada e potência
echo sqrt(64);   // 8
echo pow(2, 10); // 1024 — equivalente a 2 ** 10

// Arredondamento
echo round(3.6);     // 4 — arredonda para o inteiro mais próximo
echo round(3.4);     // 3
echo round(3.556, 2); // 3.56 — 2 casas decimais
echo ceil(4.1);      // 5 — arredonda sempre para cima
echo floor(4.9);     // 4 — arredonda sempre para baixo

// Logaritmos e exponencial
echo log(M_E);   // 1 (logaritmo natural)
echo log10(100); // 2

// Números aleatórios SEGUROS criptograficamente (use para segurança!)
$secureRandom = random_int(1, 100); // ✅ Criptograficamente seguro
echo $secureRandom;

// ⚠️ rand() NÃO é criptograficamente seguro — use apenas para jogos/demos
echo rand(1, 100); // ❌ Para segurança, prefira random_int()
```

---

## 18. Constantes

Constantes são identificadores de valor fixo — uma vez definidas, não podem ser alteradas.

### define() vs const

```php
<?php

declare(strict_types=1);

// ✅ const: definição em compile-time — preferida para constantes globais e de classe
const APP_VERSION  = '8.5.0';
const MAX_RETRIES  = 3;
const API_BASE_URL = 'https://api.example.com/v1';
const SUPPORTED_FORMATS = ['json', 'xml', 'csv']; // Array constante

echo APP_VERSION;         // 8.5.0
echo SUPPORTED_FORMATS[0]; // json

// define(): definição em runtime — útil em condicionais (raro)
if (PHP_OS_FAMILY === 'Windows') {
    define('PATH_SEPARATOR_OS', '\\');
} else {
    define('PATH_SEPARATOR_OS', '/');
}

echo PATH_SEPARATOR_OS;
```

> ⚠️ **Prefira `const` a `define()`** para constantes globais e de classe.
> `define()` só é necessário quando o nome ou valor da constante é dinâmico.

### Constantes de classe e Enum (PHP 8.1+)

```php
<?php

declare(strict_types=1);

// ✅ MODERNO PHP 8.1+: Enum substitui constantes agrupadas
enum HttpStatus: int
{
    case Ok        = 200;
    case Created   = 201;
    case NotFound  = 404;
    case ServerError = 500;

    public function label(): string
    {
        return match($this) {
            self::Ok          => 'OK',
            self::Created     => 'Created',
            self::NotFound    => 'Not Found',
            self::ServerError => 'Internal Server Error',
        };
    }
}

$status = HttpStatus::Ok;
echo $status->value;   // 200
echo $status->label(); // OK
echo $status->name;    // Ok
```

```php
// ❌ LEGACY CODE — PHP < 8.1
// ✅ Alternativa moderna: enum (veja acima)
// define('HTTP_OK', 200);
// define('HTTP_NOT_FOUND', 404);
// const HTTP_OK = 200;       // Constantes soltas, sem agrupamento ou tipo
```

---

## 19. Constantes Mágicas

Constantes mágicas são valores especiais predefinidos pelo PHP que mudam conforme o contexto de onde são usadas — diferente das constantes normais, que têm valor fixo.

**Casos de uso práticos:**
- `__DIR__` — construir caminhos de arquivo portáveis: `require __DIR__ . '/../config/app.php'`
- `__FILE__` — logs de erro com localização exata
- `__CLASS__` / `__METHOD__` — mensagens de erro e logging com contexto da classe
- `__LINE__` — debugging, rastreamento de erros em parsers
- `ClassName::class` — forma moderna e refactor-safe de obter o nome completo da classe (com namespace)

**Comparação: `__CLASS__` vs `ClassName::class` vs `get_class($this)`:**
- `__CLASS__` — nome da classe onde está definido (não respeita herança da mesma forma)
- `ClassName::class` — ✅ resolve aliases de `use` e namespace — **preferido em código moderno**
- `get_class($this)` — nome da classe do objeto em runtime (respeita herança)

> ⚠️ **Armadilha — `__DIR__` vs `dirname(__FILE__)`:** Ambos retornam o mesmo resultado, mas `__DIR__` é mais legível e deve ser preferido desde PHP 5.3.

> 💡 **Melhor prática:** Use `__DIR__` para todos os `require`/`include` em vez de caminhos relativos — o PHP resolve o caminho a partir do arquivo atual, não do diretório de trabalho (`cwd`), evitando erros quando o script é chamado de locais diferentes.

```php
<?php

declare(strict_types=1);

namespace App\Service;

// __LINE__ — número da linha atual no arquivo
echo __LINE__;

// __FILE__ — caminho absoluto do arquivo atual
echo __FILE__;

// __DIR__ — diretório do arquivo atual (sem barra final)
echo __DIR__;
// Uso prático: include relativo ao arquivo atual
// require __DIR__ . '/../config/database.php';

// __FUNCTION__ — nome da função atual
function getCurrentFunction(): string
{
    return __FUNCTION__; // 'getCurrentFunction'
}

// __CLASS__ — nome da classe atual
class UserService
{
    public function getClassName(): string
    {
        return __CLASS__; // 'App\Service\UserService' (com namespace)
    }
}

// __METHOD__ — nome do método (inclui a classe)
class OrderService
{
    public function processOrder(): string
    {
        return __METHOD__; // 'App\Service\OrderService::processOrder'
    }
}

// __NAMESPACE__ — namespace atual
echo __NAMESPACE__; // 'App\Service'

// ClassName::class — nome completo com namespace (preferível a __CLASS__)
echo UserService::class; // 'App\Service\UserService'
```

| Constante | Retorna |
|-----------|---------|
| `__LINE__` | Número da linha atual |
| `__FILE__` | Caminho completo do arquivo |
| `__DIR__` | Diretório do arquivo |
| `__FUNCTION__` | Nome da função atual |
| `__CLASS__` | Nome da classe (com namespace) |
| `__METHOD__` | Classe::método atual |
| `__NAMESPACE__` | Namespace atual |
| `__TRAIT__` | Nome do trait atual |
| `ClassName::class` | Nome completo da classe |

---

## 20. Operadores

Operadores são símbolos que executam operações sobre valores (operandos). PHP possui um conjunto rico de operadores divididos em categorias. Conhecer suas precedências e casos de borda é essencial para evitar bugs silenciosos.

**Operadores mais importantes no PHP moderno:**
- `===` (identidade) — **sempre prefira** ao `==` para comparações seguras de tipo
- `<=>` (spaceship) — retorna -1, 0 ou 1; fundamental para `usort()` com múltiplos critérios
- `??` (null coalescing) — substitui `isset() ? x : y` de forma concisa e legível
- `??=` (null coalescing assignment) — inicializa uma variável somente se for null
- `?->` (nullsafe) — encadeia chamadas em objetos que podem ser null sem verificar cada passo

**Comparação: `==` (frouxa) vs `===` (estrita):**
- `==` converte tipos antes de comparar: `0 == 'texto'` → `true` (perigoso!)
- `===` compara valor E tipo: `0 === 'texto'` → `false` (correto)
- **Regra:** Com `declare(strict_types=1)`, sempre use `===`

**Comparação: `and`/`or` vs `&&`/`||`:**
- `and` e `or` têm precedência **menor** que `=` — `$result = true and false` atribui `true` a `$result`!
- `&&` e `||` têm precedência **maior** que `=` — comportamento esperado
- **Regra:** Use sempre `&&` e `||` em expressões de atribuição

> ⚠️ **Armadilha — `and`/`or` com atribuição:** `$result = doA() and doB()` é equivalente a `($result = doA()) and doB()`. O resultado de `doB()` é ignorado e `$result` recebe apenas o de `doA()`.

> 💡 **Melhor prática — spaceship para ordenação:** `usort($arr, fn($a, $b) => $a['nome'] <=> $b['nome'])` é a forma mais limpa de ordenar arrays — substitui múltiplos `if/else` de comparação.

### Aritméticos

```php
<?php

declare(strict_types=1);

$x = 10;
$y = 3;

echo $x + $y;   // 13  — Adição
echo $x - $y;   // 7   — Subtração
echo $x * $y;   // 30  — Multiplicação
echo $x / $y;   // 3.333... — Divisão (retorna float se não divisível)
echo $x % $y;   // 1   — Módulo (resto)
echo $x ** $y;  // 1000 — Exponenciação (PHP 5.6+)
echo intdiv($x, $y); // 3 — Divisão inteira
```

### Atribuição

```php
<?php

declare(strict_types=1);

$value = 10;
$value += 5;   // $value = $value + 5   → 15
$value -= 3;   // $value = $value - 3   → 12
$value *= 2;   // $value = $value * 2   → 24
$value /= 4;   // $value = $value / 4   → 6
$value %= 4;   // $value = $value % 4   → 2
$value **= 3;  // $value = $value ** 3  → 8

// Null coalescing assignment (PHP 7.4+)
$config = [];
$config['timeout'] ??= 30; // Atribui 30 apenas se não existir ou for null
echo $config['timeout']; // 30
```

### Comparação

```php
<?php

declare(strict_types=1);

$a = 5;
$b = '5';

// == compara VALOR (com coerção de tipo — evite!)
var_dump($a == $b);  // bool(true) — ⚠️ perigoso com strict_types

// === compara VALOR e TIPO (sempre prefira este!)
var_dump($a === $b); // bool(false) — int !== string

// Spaceship operator <=> (PHP 7.0+): -1, 0 ou 1
echo 1 <=> 2;  // -1 (menor)
echo 2 <=> 2;  //  0 (igual)
echo 3 <=> 2;  //  1 (maior)
// Muito útil em ordenação: usort($arr, fn($a, $b) => $a <=> $b)
```

### Lógicos

```php
<?php

declare(strict_types=1);

$isAdmin = true;
$isActive = false;

// && e || têm precedência MAIOR que 'and' e 'or' — prefira && e ||
var_dump($isAdmin && $isActive);   // bool(false)
var_dump($isAdmin || $isActive);   // bool(true)
var_dump(!$isAdmin);               // bool(false)
var_dump($isAdmin xor $isActive);  // bool(true) — verdadeiro se APENAS um for true
```

### Null Coalescing e Nullsafe

```php
<?php

declare(strict_types=1);

// ?? — retorna o lado esquerdo se não for null, senão o direito
$username = $_GET['user'] ?? 'anônimo';

// ?-> — acessa propriedade/método apenas se o objeto não for null
$user = null; // Poderia ser um objeto User ou null
$email = $user?->getEmail() ?? 'sem e-mail'; // Não lança erro se $user for null

// Encadeamento de nullsafe
// $city = $order?->getUser()?->getAddress()?->getCity() ?? 'desconhecida';
```

### Ternário

```php
<?php

declare(strict_types=1);

$age = 20;

// Ternário completo: condição ? valor_true : valor_false
$status = $age >= 18 ? 'adulto' : 'menor de idade';
echo $status; // adulto

// Elvis operator ?: — retorna o próprio valor se truthy, senão o alternativo
$name = '' ?: 'Visitante'; // '' é falsy, então retorna 'Visitante'
echo $name; // Visitante
```

---

## 21. Estruturas Condicionais — if / else

Estruturas condicionais permitem executar blocos de código diferentes com base em condições. São a base do fluxo de controle em qualquer programa.

**Quando usar cada estrutura:**
- `if` simples — uma única condição que executa ou não um bloco
- `if...else` — dois caminhos excludentes
- `if...elseif...else` — múltiplos caminhos com condições independentes e complexas
- `match` (PHP 8.0+) — **prefira ao switch** quando o resultado é um valor e as condições são discretas

**Casos de uso práticos:**
- Verificar autenticação antes de exibir conteúdo protegido
- Adaptar mensagens conforme horário do dia, status do usuário, papel
- Validar dados antes de processar formulários

> ⚠️ **Armadilha — `empty()` em condicionais:** `empty(0)` retorna `true` — zero é considerado "vazio"! Isso pode causar bugs ao verificar resultados de contagem. Seja específico: `$count === 0` em vez de `empty($count)`.

> ⚠️ **Armadilha — `if` sem chaves:** `if ($ok) doA(); doB();` — `doB()` executa sempre, independente da condição. **Sempre use chaves** `{}`, mesmo para uma linha.

> ⚠️ **Armadilha — `==` null:** `0 == null` é `true` com comparação frouxa. Use sempre `=== null` para verificar nulidade.

> 💡 **Melhor prática:** Para múltiplas condições sobre o mesmo valor, use `match` em vez de `if...elseif` encadeado — é mais legível, usa comparação estrita e retorna valor diretamente.

### if simples

```php
<?php

declare(strict_types=1);

$temperature = 28;

if ($temperature > 25) {
    echo 'Está quente hoje!';
}
```

### if...else

```php
<?php

declare(strict_types=1);

$hour = (int) date('H'); // Hora atual (0-23)

if ($hour < 12) {
    echo 'Bom dia!';
} else {
    echo 'Boa tarde ou boa noite!';
}
```

### if...elseif...else

```php
<?php

declare(strict_types=1);

$hour = (int) date('H');

if ($hour < 12) {
    echo 'Bom dia!';
} elseif ($hour < 18) {
    echo 'Boa tarde!';
} else {
    echo 'Boa noite!';
}
```

### Operadores em condicionais

```php
<?php

declare(strict_types=1);

$score = 85;
$attempts = 3;

// Combinando condições com &&, ||, !
if ($score >= 70 && $attempts <= 5) {
    echo 'Aprovado!';
}

// Verificação de múltiplos valores — use match ou in_array ao invés de || encadeados
$validStatuses = ['active', 'pending', 'trial'];
$currentStatus = 'active';

if (in_array($currentStatus, $validStatuses, strict: true)) { // ✅ strict: true
    echo 'Status válido';
}
```

### Ternário e null coalescing (shorthand)

```php
<?php

declare(strict_types=1);

$points = 150;

// Ternário: substitui if/else simples de atribuição
$badge = $points >= 100 ? 'Ouro' : 'Prata';
echo $badge; // Ouro

// Null coalescing: substitui isset() + ternário
$userId = $_GET['id'] ?? null;
$displayId = $userId ?? 'N/A';
```

### if aninhado (nested if)

```php
<?php

declare(strict_types=1);

$userLevel = 'premium';
$accountBalance = 500.0;

if ($userLevel === 'premium') {
    echo 'Usuário Premium';

    if ($accountBalance >= 1000.0) {
        echo ' com saldo alto';
    } else {
        echo ' com saldo baixo';
    }
}
```

---

## 22. switch vs match

`switch` e `match` executam blocos de código diferentes com base no valor de uma expressão. O `match`, introduzido no PHP 8.0, é a versão moderna, segura e mais expressiva do `switch`.

**Quando usar `match`:**
- Quando você precisa do **valor retornado** (atribuição direta)
- Quando a **comparação estrita** (`===`) é necessária (evita coerção de tipo)
- Quando cada caso é uma **expressão simples** — sem múltiplos statements
- Em código novo — `match` é o padrão moderno

**Quando ainda usar `switch`:**
- Em código legado ou quando compatibilidade com PHP < 8.0 é necessária
- Quando **fall-through intencional** é requerido (múltiplos cases compartilham o mesmo bloco com lógica complexa)

**Exemplo do mundo real — roteamento HTTP:**
```php
$action = match($_SERVER['REQUEST_METHOD']) {
    'GET'    => 'read',
    'POST'   => 'create',
    'PUT'    => 'update',
    'DELETE' => 'delete',
    default  => throw new \InvalidArgumentException('Método não suportado'),
};
```

> ⚠️ **Armadilha — `match` sem `default`:** Se nenhum caso combinar e não houver `default`, o PHP lança `UnhandledMatchError`. Sempre inclua `default` ou use `default => throw new \Exception(...)` para sinalizar casos inválidos.

> ⚠️ **Armadilha — `switch` sem `break`:** Esquecer o `break` em um case faz o PHP continuar executando o próximo case (fall-through acidental) — um dos bugs mais comuns com `switch`.

### switch — legado (use apenas para compatibilidade)

```php
<?php

declare(strict_types=1);

$dayOfWeek = 3;

// ❌ switch tem comparação FROUXA (==), sem retorno de valor,
//    e requer break manual — propenso a erros (fall-through acidental)
switch ($dayOfWeek) {
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
        echo 'Dia útil';
        break;
    case 6:
    case 0:
        echo 'Final de semana';
        break;
    default:
        echo 'Dia inválido';
}
```

### match — moderno (PHP 8.0+)

```php
<?php

declare(strict_types=1);

$dayOfWeek = 3;

// ✅ MODERNO: match usa comparação ESTRITA (===), retorna valor,
//    quebra automaticamente e lança UnhandledMatchError se sem default
$dayLabel = match(true) {
    in_array($dayOfWeek, [1, 2, 3, 4, 5]) => 'Dia útil',
    in_array($dayOfWeek, [0, 6])          => 'Final de semana',
    default                               => throw new \UnexpectedValueException(
        "Dia inválido: {$dayOfWeek}"
    ),
};

echo $dayLabel; // Dia útil
```

```php
<?php

declare(strict_types=1);

// Exemplo prático: status HTTP com match
$statusCode = 404;

$message = match($statusCode) {
    200, 201 => 'Sucesso',
    301, 302 => 'Redirecionamento',
    400      => 'Requisição inválida',
    401      => 'Não autorizado',
    403      => 'Proibido',
    404      => 'Não encontrado',
    500, 503 => 'Erro no servidor',
    default  => "Código desconhecido: {$statusCode}",
};

echo $message; // Não encontrado
```

```php
<?php

declare(strict_types=1);

// ✅ match com exception no default — força tratamento de todos os casos
$role = 'editor';

$permissions = match($role) {
    'admin'  => ['read', 'write', 'delete', 'manage'],
    'editor' => ['read', 'write'],
    'viewer' => ['read'],
    default  => throw new \InvalidArgumentException("Papel inválido: {$role}"),
};

echo implode(', ', $permissions); // read, write
```

**Comparação switch vs match:**

| | `switch` | `match` |
|--|----------|---------|
| Comparação | `==` (frouxa) | `===` (estrita) |
| Retorna valor | ❌ Não | ✅ Sim |
| Break automático | ❌ Não (requer `break`) | ✅ Sim |
| Fall-through | ✅ Possível (armadilha) | ❌ Impossível |
| Sem match + sem default | Continua silenciosamente | Lança `UnhandledMatchError` |

---

## 23. Loops

Loops repetem um bloco de código enquanto uma condição for verdadeira ou enquanto houver elementos para iterar. Escolher o tipo certo de loop torna o código mais legível e eficiente.

**Guia de escolha do loop correto:**
| Loop | Use quando |
|------|-----------|
| `foreach` | Percorrer arrays, objetos iteráveis, Generators — **padrão para coleções** |
| `for` | Contador com lógica de incremento complexa, dois ponteiros simultâneos |
| `while` | Condição de parada não é um contador previsível (leitura de arquivo, polling) |
| `do...while` | O bloco DEVE executar pelo menos uma vez (menus, validação interativa) |

**Casos de uso práticos:**
- `foreach` — exibir listas de produtos, iterar sobre resultados de banco
- `for` — gerar N elementos, algoritmos two-pointer, matrizes bidimensionais
- `while` — ler arquivo linha por linha, consumir fila de mensagens
- `do...while` — solicitar input do usuário até receber valor válido

> ⚠️ **Armadilha — `foreach` por referência sem `unset()`:** Após `foreach ($arr as &$item)`, a variável `$item` continua apontando para o último elemento. Qualquer atribuição posterior a `$item` modifica o array! Sempre chame `unset($item)` após o loop.

> ⚠️ **Armadilha — `count()` no `for`:** `for ($i = 0; $i < count($arr); $i++)` chama `count()` a cada iteração. Guarde o resultado antes: `$len = count($arr); for ($i = 0; $i < $len; $i++)`.

> ⚠️ **Armadilha — modificar array no `foreach`:** `foreach ($arr as $item)` copia o valor. Modificar `$item` não afeta o array original. Use `&$item` (com referência) ou `array_map()`.

> 💡 **Melhor prática:** Prefira `foreach` sempre que possível — é mais legível, evita off-by-one errors (erros de +1/-1 nos índices) e funciona com qualquer `iterable`, não apenas arrays.

### while

```php
<?php

declare(strict_types=1);

// Executa enquanto a condição for verdadeira
// A condição é verificada ANTES de cada iteração
$counter = 1;

while ($counter <= 5) {
    echo $counter; // 1 2 3 4 5
    $counter++;
}

// Com break e continue
$i = 0;

while ($i < 10) {
    $i++;

    if ($i === 3) {
        continue; // Pula o 3
    }

    if ($i === 7) {
        break; // Para no 7
    }

    echo $i; // 1 2 4 5 6
}
```

### do...while

```php
<?php

declare(strict_types=1);

// Executa pelo menos UMA vez — a condição é verificada DEPOIS
$attempts = 0;

do {
    echo "Tentativa: {$attempts}";
    $attempts++;
} while ($attempts < 3);
// Saída: Tentativa: 0 Tentativa: 1 Tentativa: 2

// Útil para menus e validações que devem executar ao menos uma vez
$value = 8;

do {
    echo $value; // Exibe 8 mesmo com condição falsa desde o início
    $value++;
} while ($value < 5); // Condição falsa, mas executa uma vez
```

### for

```php
<?php

declare(strict_types=1);

// Estrutura: for (inicialização; condição; incremento)
for ($i = 0; $i < 5; $i++) {
    echo $i; // 0 1 2 3 4
}

// Contando de trás para frente
for ($i = 10; $i >= 0; $i -= 2) {
    echo $i; // 10 8 6 4 2 0
}

// Percorrendo array com índice (use foreach quando possível)
$colors = ['vermelho', 'verde', 'azul'];

for ($i = 0; $i < count($colors); $i++) {
    echo "{$i}: {$colors[$i]}";
}
```

### foreach

```php
<?php

declare(strict_types=1);

// ✅ PREFERIDO para percorrer arrays — mais legível e seguro
$fruits = ['maçã', 'banana', 'laranja', 'uva'];

// Array indexado — apenas valor
foreach ($fruits as $fruit) {
    echo $fruit;
}

// Array indexado — chave e valor
foreach ($fruits as $index => $fruit) {
    echo "{$index}: {$fruit}";
}

// Array associativo — chave e valor
$person = [
    'name'  => 'Ana Costa',
    'age'   => 30,
    'email' => 'ana@example.com',
];

foreach ($person as $key => $value) {
    echo "{$key}: {$value}";
}

// Percorrendo objetos
final class Car
{
    public function __construct(
        public readonly string $brand,
        public readonly int    $year,
    ) {}
}

$cars = [
    new Car('Toyota', 2023),
    new Car('Honda', 2024),
    new Car('BMW', 2025),
];

foreach ($cars as $car) {
    echo "{$car->brand} ({$car->year})";
}

// break e continue em foreach
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

foreach ($numbers as $number) {
    if ($number % 2 === 0) {
        continue; // Pula números pares
    }

    if ($number > 7) {
        break; // Para depois do 7
    }

    echo $number; // 1 3 5 7
}
```

> ⚠️ **Modificação por referência em foreach:** use com cuidado e sempre chame `unset()` depois.

```php
<?php

declare(strict_types=1);

$prices = [10.0, 20.0, 30.0];

// Modifica os valores originais do array com &
foreach ($prices as &$price) {
    $price *= 1.1; // Aplica 10% de aumento
}
unset($price); // ✅ OBRIGATÓRIO: desfaz a referência após o loop

var_dump($prices); // [11.0, 22.0, 33.0]
```

---

## 24. Funções

Funções são blocos de código nomeados e reutilizáveis que realizam uma tarefa específica. São a base da organização e do princípio DRY (Don't Repeat Yourself) em PHP.

**Tipos de funções em PHP:**
- **Funções nomeadas** — declaradas com `function nome()`, chamadas por nome, reutilizáveis em todo o escopo
- **Closures (anônimas)** — `function() use ($var) {}`, capturam o escopo externo, usadas como callbacks
- **Arrow functions** — `fn($x) => $x * 2`, capturam escopo automaticamente por valor, concisas para expressões simples
- **FCC (First-Class Callable)** — `trim(...)`, converte função nomeada em Closure de forma segura (PHP 8.1+)

**Casos de uso práticos:**
- Funções nomeadas — lógica de negócio reutilizável (`calculateDiscount()`, `validateEmail()`)
- Closures — callbacks em `array_map()`, `array_filter()`, handlers de evento
- Arrow functions — transformações simples em pipelines funcionais
- FCC — passar funções nativas como callbacks sem risco de typo em strings

**Comparação: closure com `use()` vs arrow function:**
| | Closure com `use()` | Arrow function |
|--|---------------------|----------------|
| Captura de variáveis | Manual com `use ($var)` | Automática por valor |
| Múltiplas linhas | ✅ Sim | ❌ Apenas expressão |
| Modifica escopo externo | Com `use (&$var)` | ❌ Não (sempre por valor) |
| Legibilidade | Explícita | Mais concisa |

> ⚠️ **Armadilha — `declare(strict_types=1)` e type hints:** Com strict types ativo, passar `"5"` (string) para um parâmetro `int` lança `TypeError`. Sem ele, o PHP converte silenciosamente — fonte de bugs difíceis de rastrear.

> ⚠️ **Armadilha — parâmetro variádico não é o último:** `function fn(int $a, ...$rest, int $b)` gera Fatal Error. O parâmetro `...$rest` deve ser sempre o último.

> 💡 **Melhor prática:** Declare sempre o tipo de todos os parâmetros e o tipo de retorno. Funções com type hints completos são autodocumentadas e têm erros detectados em tempo de análise, não em produção.

> 💡 **PHP 8.1+ FCC:** Prefira `array_map(strtolower(...), $arr)` a `array_map('strtolower', $arr)` — o FCC detecta typos em tempo de análise, enquanto a string só falha em runtime.

### Declaração e chamada

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.5: type hints completos em parâmetros e retorno
function greet(string $name): string
{
    return "Olá, {$name}!";
}

echo greet('PHP 8.5'); // Olá, PHP 8.5!
```

### Parâmetros com valor padrão

```php
<?php

declare(strict_types=1);

/**
 * Formata um preço com símbolo de moeda.
 *
 * @param float  $amount   Valor a formatar
 * @param string $currency Símbolo da moeda
 * @param int    $decimals Casas decimais
 *
 * @return string Preço formatado
 */
function formatPrice(
    float  $amount,
    string $currency = 'R$',
    int    $decimals = 2,
): string {
    return $currency . ' ' . number_format($amount, $decimals, ',', '.');
}

echo formatPrice(1234.5);            // R$ 1.234,50
echo formatPrice(1234.5, 'USD', 2);  // USD 1.234,50
echo formatPrice(1234.5, '€');       // € 1.234,50
```

### Named Arguments (PHP 8.0+)

```php
<?php

declare(strict_types=1);

// ✅ Named arguments: mais legível, ordem não importa, ignora padrões opcionais
function createUser(
    string $name,
    string $email,
    string $role    = 'viewer',
    bool   $active  = true,
    int    $level   = 1,
): array {
    return compact('name', 'email', 'role', 'active', 'level');
}

// Sem named args — posicional, precisa passar todos até o que quer mudar
$user1 = createUser('Ana', 'ana@example.com', 'admin', true, 1);

// ✅ Com named args — claro, pulamos parâmetros com valor padrão
$user2 = createUser(
    name:  'Carlos',
    email: 'carlos@example.com',
    role:  'admin',
);

var_dump($user2);
```

### Retorno de múltiplos valores

```php
<?php

declare(strict_types=1);

/**
 * Divide dois números e retorna o quociente e o resto.
 *
 * @return array{quotient: int, remainder: int}
 */
function divideWithRemainder(int $dividend, int $divisor): array
{
    if ($divisor === 0) {
        throw new \DivisionByZeroError('Divisor não pode ser zero.');
    }

    return [
        'quotient'  => intdiv($dividend, $divisor),
        'remainder' => $dividend % $divisor,
    ];
}

['quotient' => $q, 'remainder' => $r] = divideWithRemainder(17, 5);
echo "Quociente: {$q}, Resto: {$r}"; // Quociente: 3, Resto: 2
```

### Funções variádicas (...)

```php
<?php

declare(strict_types=1);

// Aceita número variável de argumentos com spread operator
function sumAll(int|float ...$numbers): float
{
    return array_sum($numbers);
}

echo sumAll(1, 2, 3);         // 6
echo sumAll(1.5, 2.5, 3.0);   // 7

// Parâmetro regular + variádico (variádico deve ser o ÚLTIMO)
function greetAll(string $greeting, string ...$names): string
{
    return $greeting . ': ' . implode(', ', $names) . '!';
}

echo greetAll('Olá', 'Ana', 'Carlos', 'Maria'); // Olá: Ana, Carlos, Maria!
```

### Passagem por referência

```php
<?php

declare(strict_types=1);

// Modifica a variável original — use com cautela, dificulta rastreamento
function addSuffix(string &$value, string $suffix): void
{
    $value .= $suffix;
}

$name = 'PHP';
addSuffix($name, ' 8.5');
echo $name; // PHP 8.5

// ✅ PREFERÍVEL: retornar o novo valor ao invés de modificar por referência
function withSuffix(string $value, string $suffix): string
{
    return $value . $suffix;
}

$name = 'PHP';
$name = withSuffix($name, ' 8.5');
echo $name; // PHP 8.5
```

### Strict Types e Type Declarations

```php
<?php

declare(strict_types=1); // ✅ Obrigatório — ativa verificação estrita de tipos

function addNumbers(int $a, int $b): int
{
    return $a + $b;
}

echo addNumbers(5, 10);    // 15
// addNumbers(5, '10');    // ❌ Fatal error com strict_types=1

// Union types (PHP 8.0+): aceita int OU float
function multiply(int|float $a, int|float $b): int|float
{
    return $a * $b;
}

echo multiply(3, 2.5); // 7.5

// Return types avançados
function findUser(int $id): ?array  // Nullable — pode retornar null
{
    // Simulação de busca no banco
    return $id === 1 ? ['name' => 'Ana', 'id' => 1] : null;
}

$user = findUser(1);
echo $user?->offsetGet('name') ?? 'Não encontrado';

// never: indica que a função NUNCA retorna (sempre lança exceção ou exit)
function fail(string $message): never
{
    throw new \RuntimeException($message);
}
```

### Closures e Arrow Functions

```php
<?php

declare(strict_types=1);

// Closure — função anônima com captura explícita de variáveis
$multiplier = 3;

$multiply = function(int $value) use ($multiplier): int {
    return $value * $multiplier;
};

echo $multiply(5); // 15

// Arrow function (PHP 7.4+): captura automaticamente o escopo externo
$multiplier = 4;
$multiplyArrow = fn(int $value): int => $value * $multiplier;

echo $multiplyArrow(5); // 20

// ✅ PHP 8.5: Arrow functions em pipelines (com parênteses obrigatórios!)
$result = 10
    |> (fn(int $n): int => $n * 2)
    |> (fn(int $n): int => $n + 5);

echo $result; // 25
```

---

## 25. Arrays

Arrays em PHP são estruturas de dados extremamente flexíveis — podem funcionar como listas indexadas, dicionários (chave→valor), pilhas, filas e muito mais. Todo array em PHP é internamente um mapa ordenado.

**Tipos de arrays e quando usar cada um:**
- **Indexado** — chaves numéricas automáticas (`0, 1, 2...`). Use para listas e sequências ordenadas.
- **Associativo** — chaves string nomeadas. Use para registros estruturados (como rows do banco).
- **Multidimensional** — arrays dentro de arrays. Use para tabelas, matrizes e dados hierárquicos.

**Sintaxe moderna obrigatória (PER-CS v3.0):**
- Use `[]` em vez de `array()` — mais conciso, é o padrão moderno
- Trailing comma obrigatória em arrays multiline (facilita diffs no git e evita erros ao adicionar itens)

**PHP 8.5 — novas funções:**
- `array_first($arr)` — retorna o primeiro elemento **sem side effects** (substitui `reset()`)
- `array_last($arr)` — retorna o último elemento **sem side effects** (substitui `end()`)

> ⚠️ **Armadilha — `in_array()` sem strict:** `in_array('1', [1, 2, 3])` retorna `true` por comparação frouxa. Sempre passe `strict: true` como terceiro argumento.

> ⚠️ **Armadilha — `array_filter()` preserva chaves:** Após filtrar, as chaves originais são mantidas (criando "buracos" nos índices). Use `array_values(array_filter(...))` para re-indexar de 0.

> ⚠️ **Armadilha — `reset()` e `end()` têm side effects:** Ambas movem o ponteiro interno do array, podendo causar comportamento inesperado em iterações subsequentes. Use `array_first()` e `array_last()` do PHP 8.5.

> 💡 **Melhor prática:** Use `array_column($arr, null, 'id')` para criar lookups indexados por ID em O(1) em vez de percorrer o array a cada busca — a diferença de performance é significativa em arrays grandes.

### Tipos de arrays

PHP tem três tipos de arrays:

1. **Indexado** — chaves numéricas automáticas (`0`, `1`, `2`, ...)
2. **Associativo** — chaves nomeadas (`'brand'`, `'model'`, ...)
3. **Multidimensional** — arrays dentro de arrays

### Criação

```php
<?php

declare(strict_types=1);

// ✅ Sintaxe moderna com [] (obrigatória pelo PER-CS v3.0)
$fruits  = ['maçã', 'banana', 'laranja'];   // Indexado
$car     = ['brand' => 'Toyota', 'year' => 2025]; // Associativo

// ❌ LEGACY CODE — PHP < 5.4
// ✅ Alternativa moderna: sintaxe [] (acima)
// $fruits = array('maçã', 'banana', 'laranja');

// Array multilinha — trailing comma é OBRIGATÓRIA (PER-CS v3.0)
$config = [
    'host'     => 'localhost',
    'port'     => 3306,
    'database' => 'my_app',
    'charset'  => 'utf8mb4',  // ← trailing comma obrigatória em multilinha
];
```

### Acesso a elementos

```php
<?php

declare(strict_types=1);

$cars = ['Volvo', 'BMW', 'Toyota'];

echo $cars[0];  // Volvo (índice base 0)
echo $cars[2];  // Toyota

// ✅ PHP 8.5: array_first() e array_last() — sem side effects!
echo array_first($cars); // Volvo
echo array_last($cars);  // Toyota

// ❌ LEGACY CODE — PHP < 8.5
// ✅ Alternativa moderna: array_first() / array_last()
// $first = reset($cars); // reset() move o ponteiro interno — side effect!
// $last  = end($cars);   // end() também move o ponteiro

// Acesso em array associativo
$person = ['name' => 'Ana', 'age' => 30, 'city' => 'São Paulo'];
echo $person['name']; // Ana
echo $person['city']; // São Paulo
```

### Adição de elementos

```php
<?php

declare(strict_types=1);

$fruits = ['maçã', 'banana'];

// Adiciona ao final com []
$fruits[] = 'laranja';

// Adiciona múltiplos ao final
array_push($fruits, 'uva', 'kiwi');

// Adiciona ao início
array_unshift($fruits, 'abacaxi');

// Adiciona em posição específica com array_splice()
array_splice($fruits, 2, 0, ['morango']); // Insere 'morango' no índice 2

var_dump($fruits);
```

### Remoção de elementos

```php
<?php

declare(strict_types=1);

$cars = ['Volvo', 'BMW', 'Toyota', 'Honda'];

// Remove o último elemento
$last = array_pop($cars);     // Retorna 'Honda'

// Remove o primeiro elemento
$first = array_shift($cars);  // Retorna 'Volvo' e re-indexa o array

// Remove por índice (NÃO re-indexa — cria "gap")
unset($cars[1]);

// Remove por valor — cria novo array sem os valores especificados
$filtered = array_diff($cars, ['BMW']);

// array_splice() — remove e re-indexa automaticamente
$cars = ['Volvo', 'BMW', 'Toyota'];
array_splice($cars, 1, 1); // Remove BMW (índice 1, quantidade 1)
var_dump($cars); // ['Volvo', 'Toyota']
```

### Ordenação

```php
<?php

declare(strict_types=1);

$numbers = [4, 6, 2, 22, 11];
$names   = ['Carlos', 'Ana', 'Maria', 'Bruno'];
$ages    = ['Pedro' => 35, 'Ana' => 28, 'Zé' => 42];

// Arrays indexados
sort($numbers);   // Crescente numérico → [2, 4, 6, 11, 22]
rsort($numbers);  // Decrescente       → [22, 11, 6, 4, 2]
sort($names);     // Crescente alfabético

// Arrays associativos — por valor
asort($ages);     // Crescente por valor (mantém chaves)
arsort($ages);    // Decrescente por valor

// Arrays associativos — por chave
ksort($ages);     // Crescente por chave
krsort($ages);    // Decrescente por chave

// Ordenação customizada com usort()
$people = [
    ['name' => 'Carlos', 'age' => 35],
    ['name' => 'Ana',    'age' => 28],
    ['name' => 'Maria',  'age' => 42],
];

// ✅ Ordenar por idade com spaceship operator
usort($people, fn(array $a, array $b): int => $a['age'] <=> $b['age']);
```

### Funções de array avançadas

```php
<?php

declare(strict_types=1);

$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// array_filter() — filtra elementos
$evens = array_filter($numbers, fn(int $n): bool => $n % 2 === 0);
// [2, 4, 6, 8, 10]

// array_map() — transforma elementos
$squared = array_map(fn(int $n): int => $n ** 2, $numbers);
// [1, 4, 9, 16, 25, ...]

// array_reduce() — reduz a um único valor
$sum = array_reduce($numbers, fn(int $carry, int $n): int => $carry + $n, 0);
// 55

// ✅ PHP 8.5: Pipeline com Pipe Operator para transformações em cadeia
$result = $numbers
    |> (fn(array $arr): array => array_filter($arr, fn(int $n): bool => $n % 2 === 0))
    |> (fn(array $arr): array => array_map(fn(int $n): int => $n ** 2, $arr))
    |> (fn(array $arr): int   => array_sum($arr));

echo $result; // 4 + 16 + 36 + 64 + 100 = 220

// Busca em arrays
$fruits = ['maçã', 'banana', 'laranja'];
var_dump(in_array('banana', $fruits, strict: true));  // bool(true)
var_dump(array_search('banana', $fruits));            // int(1)

// array_unique() — remove duplicatas
$withDupes = [1, 2, 2, 3, 3, 3, 4];
$unique = array_unique($withDupes); // [1, 2, 3, 4]

// array_chunk() — divide em pedaços
$chunks = array_chunk([1, 2, 3, 4, 5], 2);
// [[1, 2], [3, 4], [5]]

// array_combine() — combina duas arrays em associativo
$keys   = ['name', 'age', 'city'];
$values = ['Ana', 28, 'SP'];
$person = array_combine($keys, $values);
// ['name' => 'Ana', 'age' => 28, 'city' => 'SP']
```

### Arrays multidimensionais

```php
<?php

declare(strict_types=1);

// Array bidimensional — matriz
$matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
];

echo $matrix[1][2]; // 6 (linha 1, coluna 2)

// Array associativo de objetos/arrays
$employees = [
    ['name' => 'Ana',    'dept' => 'TI',      'salary' => 8500.0],
    ['name' => 'Carlos', 'dept' => 'RH',      'salary' => 6200.0],
    ['name' => 'Maria',  'dept' => 'TI',      'salary' => 9100.0],
];

// Percorrendo e filtrando
$itTeam = array_filter(
    $employees,
    fn(array $emp): bool => $emp['dept'] === 'TI'
);

foreach ($itTeam as $employee) {
    echo "{$employee['name']}: R$ {$employee['salary']}";
}
```

---

## 26. PHP 8.5 — Features Exclusivas

### Pipe Operator (`|>`)

```php
<?php

declare(strict_types=1);

// ✅ Encadeamento left-to-right — elimina aninhamento de funções
$text = '  PHP 8.5 Released!  ';

// Antes (legado): leitura de dentro para fora — confuso
// $result = strtolower(trim($text)); // Confuso com muitos passos

// PHP 8.5: pipe — leitura natural, da esquerda para direita
$slug = $text
    |> trim(...)
    |> strtolower(...)
    |> (fn(string $s): string => str_replace(' ', '-', $s))
    |> (fn(string $s): string => str_replace('!', '', $s));

echo $slug; // php-8.5-released

// ⚠️ Regra crítica: funções com múltiplos argumentos DEVEM usar closure
// O pipe passa o valor como ÚNICO argumento
// Errado: |> str_replace(' ', '-', ...) — TypeError!
// Correto: |> (fn($s) => str_replace(' ', '-', $s))
```

### Clone With

```php
<?php

declare(strict_types=1);

// ✅ Clone com propriedades alteradas — perfeito para classes readonly
final class Money
{
    public function __construct(
        public readonly float  $amount,
        public readonly string $currency,
    ) {}

    public function add(float $value): self
    {
        // clone() com mapa de alterações — sem violar readonly
        return clone($this, ['amount' => $this->amount + $value]);
    }

    public function toCurrency(string $newCurrency): self
    {
        return clone($this, ['currency' => $newCurrency]);
    }
}

$price     = new Money(100.0, 'BRL');
$newPrice  = $price->add(50.0);          // Money(150.0, 'BRL')
$usdPrice  = $price->toCurrency('USD');  // Money(100.0, 'USD')

// Objeto original permanece imutável
echo $price->amount;    // 100.0
echo $newPrice->amount; // 150.0
```

### `#[\NoDiscard]` Attribute

```php
<?php

declare(strict_types=1);

// ✅ Avisa quando o valor de retorno é ignorado acidentalmente
final class UserRepository
{
    private array $users = [];

    /**
     * Salva o usuário e retorna o ID gerado.
     * Ignorar o retorno é quase sempre um erro!
     */
    #[\NoDiscard('O ID do usuário criado deve ser armazenado')]
    public function save(string $name, string $email): int
    {
        $id = count($this->users) + 1;
        $this->users[$id] = ['name' => $name, 'email' => $email];

        return $id;
    }
}

$repo = new UserRepository();

$userId = $repo->save('Ana', 'ana@example.com'); // ✅ Correto: captura o ID
echo $userId;

// $repo->save('Carlos', 'c@example.com'); // ⚠️ Warning: return value ignored!

// Para ignorar intencionalmente, use (void):
(void) $repo->save('Maria', 'm@example.com'); // ✅ Suprime o warning explicitamente
```

### `array_first()` e `array_last()`

```php
<?php

declare(strict_types=1);

$scores = [85, 92, 78, 95, 88];
$empty  = [];

// ✅ PHP 8.5: sem side effects, seguro com arrays vazios
$first = array_first($scores); // 85
$last  = array_last($scores);  // 88

var_dump(array_first($empty)); // NULL (seguro — não lança erro)
var_dump(array_last($empty));  // NULL

// ❌ LEGACY CODE — PHP < 8.5
// ✅ Alternativa moderna: array_first() / array_last()
// $first = reset($scores); // Modifica o ponteiro interno do array
// $last  = end($scores);   // Também modifica o ponteiro

// Exemplo prático: top scorer e lowest scorer
$players = [
    ['name' => 'Ana',    'score' => 95],
    ['name' => 'Carlos', 'score' => 82],
    ['name' => 'Maria',  'score' => 78],
];

usort($players, fn(array $a, array $b): int => $b['score'] <=> $a['score']);

$topPlayer    = array_first($players);
$bottomPlayer = array_last($players);

echo "Melhor: {$topPlayer['name']} ({$topPlayer['score']})";
echo "Pior: {$bottomPlayer['name']} ({$bottomPlayer['score']})";
```

### URI Extension

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.5: Classes OOP nativas para manipulação de URIs
$url = new Uri\Rfc3986\Uri('https://user:pass@example.com:8080/path?q=php&v=8.5#section');

echo $url->getScheme();    // https
echo $url->getHost();      // example.com
echo $url->getPort();      // 8080
echo $url->getPath();      // /path
echo $url->getQuery();     // q=php&v=8.5
echo $url->getFragment();  // section

// WHATWG URL (compatível com browsers)
$whatwg = new Uri\WhatWg\Url('https://example.com/products?category=php');
echo $whatwg->hostname;    // example.com
echo $whatwg->pathname;    // /products
echo $whatwg->search;      // ?category=php

// ❌ LEGACY CODE — PHP < 8.5
// ✅ Alternativa moderna: Uri\Rfc3986\Uri (acima)
// $parts = parse_url($rawUrl); // Retorna array sem validação — propenso a erros
```

### Closures em Expressões Constantes

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.5: Closures e FCC (First-Class Callable) em contextos constantes
const SANITIZERS = [
    'trim'      => trim(...),
    'lowercase' => strtolower(...),
    'uppercase' => strtoupper(...),
];

// Uso em atributos de classe
#[Attribute]
final class Validate
{
    public function __construct(
        public readonly \Closure $rule = static fn(mixed $v): bool => $v !== null,
    ) {}
}
```

---

## Referência Rápida — Funções Essenciais PHP 8.5

### Strings
| Função | Descrição |
|--------|-----------|
| `strlen($s)` | Comprimento em bytes |
| `mb_strlen($s)` | Comprimento em caracteres (UTF-8) |
| `strtolower($s)` | Minúsculas |
| `strtoupper($s)` | Maiúsculas |
| `trim($s)` | Remove espaços nas bordas |
| `str_replace($old, $new, $s)` | Substitui texto |
| `str_contains($s, $needle)` | Verifica se contém substring |
| `str_starts_with($s, $prefix)` | Verifica início |
| `str_ends_with($s, $suffix)` | Verifica fim |
| `substr($s, $start, $len)` | Fatia a string |
| `explode($sep, $s)` | String → array |
| `implode($sep, $arr)` | Array → string |
| `sprintf($format, ...)` | Formata string |
| `htmlspecialchars($s)` | ✅ Escapa para HTML (segurança!) |

### Arrays
| Função | Descrição |
|--------|-----------|
| `array_first($arr)` | 🆕 PHP 8.5: primeiro elemento |
| `array_last($arr)` | 🆕 PHP 8.5: último elemento |
| `count($arr)` | Número de elementos |
| `array_push($arr, ...)` | Adiciona ao final |
| `array_pop($arr)` | Remove e retorna o último |
| `array_shift($arr)` | Remove e retorna o primeiro |
| `array_unshift($arr, ...)` | Adiciona ao início |
| `array_splice($arr, ...)` | Remove/insere em posição |
| `array_merge($a, $b)` | Mescla arrays |
| `array_filter($arr, $fn)` | Filtra elementos |
| `array_map($fn, $arr)` | Transforma elementos |
| `array_reduce($arr, $fn, $init)` | Reduz a um valor |
| `array_unique($arr)` | Remove duplicatas |
| `in_array($val, $arr, true)` | Verifica se existe (strict!) |
| `array_search($val, $arr)` | Retorna a chave do valor |
| `sort($arr)` / `rsort($arr)` | Ordena indexado |
| `asort($arr)` / `arsort($arr)` | Ordena associativo por valor |
| `ksort($arr)` / `krsort($arr)` | Ordena associativo por chave |

### Matemática
| Função | Descrição |
|--------|-----------|
| `abs($n)` | Valor absoluto |
| `round($n, $dec)` | Arredonda |
| `ceil($n)` | Arredonda para cima |
| `floor($n)` | Arredonda para baixo |
| `sqrt($n)` | Raiz quadrada |
| `pow($base, $exp)` | Potência (ou `**`) |
| `min(...)` / `max(...)` | Mínimo / máximo |
| `random_int($min, $max)` | ✅ Aleatório seguro criptograficamente |
| `is_nan($n)` | Verifica NaN |
| `is_infinite($n)` | Verifica infinito |

### Segurança — Funções Obrigatórias
| Função | Uso |
|--------|-----|
| `htmlspecialchars($s, ENT_QUOTES\|ENT_HTML5, 'UTF-8')` | Escape de output HTML |
| `filter_var($val, FILTER_VALIDATE_EMAIL)` | Validação de e-mail |
| `password_hash($pass, PASSWORD_ARGON2ID)` | Hash de senha |
| `password_verify($pass, $hash)` | Verificação de senha |
| `random_bytes($len)` | Bytes aleatórios seguros |
| `hash_equals($known, $user)` | Comparação timing-safe |

---

## 27. Arrays Multidimensionais

Um array multidimensional é um array que contém outros arrays como elementos.
PHP suporta dois, três, quatro ou mais níveis de profundidade — na prática, três níveis
já são difíceis de gerenciar sem abstração.

### Array bidimensional — tabela de dados

```php
<?php

declare(strict_types=1);

// ✅ PER-CS v3.0: sintaxe [], trailing comma em multilinha
// Cada linha interna representa um registro com colunas: [marca, estoque, vendido]
$cars = [
    ['Volvo',      22, 18],
    ['BMW',        15, 13],
    ['Saab',        5,  2],
    ['Land Rover', 17, 15],
];

// Acesso via dois índices: [linha][coluna]
echo $cars[0][0]; // Volvo
echo $cars[0][1]; // 22
echo $cars[3][2]; // 15
```

### Array associativo bidimensional — mais legível

```php
<?php

declare(strict_types=1);

// ✅ PREFERIDO: chaves nomeadas tornam o código autodocumentado
$inventory = [
    ['brand' => 'Volvo',      'stock' => 22, 'sold' => 18],
    ['brand' => 'BMW',        'stock' => 15, 'sold' => 13],
    ['brand' => 'Saab',       'stock' =>  5, 'sold' =>  2],
    ['brand' => 'Land Rover', 'stock' => 17, 'sold' => 15],
];

// Acesso semântico — mais claro que [0][1]
echo $inventory[0]['brand']; // Volvo
echo $inventory[2]['stock']; // 5

// Calculando disponível por registro
foreach ($inventory as $item) {
    $available = $item['stock'] - $item['sold'];
    echo "{$item['brand']}: disponível = {$available}";
}
```

### Percorrendo com foreach aninhado

```php
<?php

declare(strict_types=1);

$cars = [
    ['Volvo',      22, 18],
    ['BMW',        15, 13],
    ['Saab',        5,  2],
    ['Land Rover', 17, 15],
];

// ✅ foreach dentro de foreach — legível e sem índices manuais
foreach ($cars as $row) {
    echo '<tr>';
    foreach ($row as $cell) {
        // ✅ Sempre escape output HTML — previne XSS
        echo '<td>' . htmlspecialchars((string) $cell, ENT_QUOTES | ENT_HTML5, 'UTF-8') . '</td>';
    }
    echo '</tr>';
}
```

### Percorrendo com for aninhado (quando o tamanho é fixo)

```php
<?php

declare(strict_types=1);

$matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
];

$rows = count($matrix);
$cols = count($matrix[0]);

for ($row = 0; $row < $rows; $row++) {
    for ($col = 0; $col < $cols; $col++) {
        echo $matrix[$row][$col]; // 1 2 3 4 5 6 7 8 9
    }
}
```

### Array tridimensional — exemplo prático

```php
<?php

declare(strict_types=1);

// Catálogo: marca → modelos → especificações
$catalog = [
    'Toyota' => [
        'Corolla' => ['year' => 2024, 'fuel' => 'flex',    'doors' => 4],
        'Hilux'   => ['year' => 2024, 'fuel' => 'diesel',  'doors' => 4],
    ],
    'Honda' => [
        'Civic'   => ['year' => 2025, 'fuel' => 'flex',    'doors' => 4],
        'HR-V'    => ['year' => 2025, 'fuel' => 'híbrido', 'doors' => 5],
    ],
];

// Acesso por três níveis de chave
echo $catalog['Toyota']['Corolla']['fuel']; // flex
echo $catalog['Honda']['HR-V']['doors'];    // 5

// Percorrendo todos os níveis
foreach ($catalog as $brand => $models) {
    foreach ($models as $model => $specs) {
        echo "{$brand} {$model} ({$specs['year']}) — {$specs['fuel']}";
    }
}
```

### Funções úteis para arrays multidimensionais

```php
<?php

declare(strict_types=1);

$employees = [
    ['name' => 'Ana',    'dept' => 'TI',  'salary' => 9100.0],
    ['name' => 'Carlos', 'dept' => 'RH',  'salary' => 6200.0],
    ['name' => 'Maria',  'dept' => 'TI',  'salary' => 8500.0],
    ['name' => 'Bruno',  'dept' => 'TI',  'salary' => 7800.0],
];

// array_column() — extrai uma "coluna" de um array bidimensional
$names    = array_column($employees, 'name');    // ['Ana', 'Carlos', 'Maria', 'Bruno']
$salaries = array_column($employees, 'salary');  // [9100.0, 6200.0, 8500.0, 7800.0]

// Reindexar pelo campo 'name'
$byName = array_column($employees, null, 'name');
echo $byName['Ana']['salary']; // 9100.0

// array_multisort() — ordena por múltiplas colunas
// Ordenar por departamento (asc) e depois por salário (desc)
$depts    = array_column($employees, 'dept');
$sals     = array_column($employees, 'salary');
array_multisort($depts, SORT_ASC, $sals, SORT_DESC, $employees);

// ✅ usort() com spaceship — ordenação customizada
usort($employees, fn(array $a, array $b): int => $b['salary'] <=> $a['salary']);
$topEarner = array_first($employees); // PHP 8.5
echo $topEarner['name']; // Ana
```

---

## 28. Referência de Funções de Array

PHP possui mais de 80 funções nativas para arrays. Abaixo as mais usadas no dia a dia,
organizadas por categoria com exemplos práticos em PHP 8.5.

### Criação e estrutura

```php
<?php

declare(strict_types=1);

// range() — cria array com intervalo de valores
$numbers = range(1, 10);        // [1, 2, 3, ..., 10]
$evens   = range(2, 20, 2);     // [2, 4, 6, ..., 20]
$letters = range('a', 'z');     // ['a', 'b', ..., 'z']

// array_fill() — preenche com valor repetido
$zeros   = array_fill(0, 5, 0);       // [0, 0, 0, 0, 0]
$defaults = array_fill_keys(['name', 'email', 'age'], null); // chaves nomeadas

// array_combine() — combina chaves e valores de dois arrays
$keys   = ['brand', 'model', 'year'];
$values = ['Toyota', 'Corolla', 2025];
$car    = array_combine($keys, $values);
// ['brand' => 'Toyota', 'model' => 'Corolla', 'year' => 2025]

// compact() — cria array associativo a partir de variáveis
$name  = 'Ana';
$email = 'ana@example.com';
$age   = 30;
$user  = compact('name', 'email', 'age');
// ['name' => 'Ana', 'email' => 'ana@example.com', 'age' => 30]
```

### Inspeção e busca

```php
<?php

declare(strict_types=1);

$fruits = ['maçã', 'banana', 'laranja', 'banana'];

// count() — número de elementos (array_key_exists é para chaves)
echo count($fruits); // 4

// in_array() — verifica existência (strict: true é OBRIGATÓRIO)
var_dump(in_array('banana', $fruits, strict: true)); // bool(true)

// array_key_exists() — verifica se chave existe (difere de isset — detecta null)
$data = ['score' => null];
var_dump(array_key_exists('score', $data)); // bool(true)
var_dump(isset($data['score']));            // bool(false) — null é tratado como ausente

// array_search() — retorna a chave do valor encontrado
$key = array_search('banana', $fruits); // int(1) — primeira ocorrência

// array_keys() e array_values() — extração de chaves ou valores
$car = ['brand' => 'Toyota', 'model' => 'Corolla', 'year' => 2025];
$keys   = array_keys($car);    // ['brand', 'model', 'year']
$values = array_values($car);  // ['Toyota', 'Corolla', 2025]

// array_count_values() — conta ocorrências de cada valor
$votes = ['sim', 'não', 'sim', 'sim', 'não'];
$tally = array_count_values($votes); // ['sim' => 3, 'não' => 2]
```

### Transformação

```php
<?php

declare(strict_types=1);

$prices = [10.0, 25.5, 8.0, 42.0, 15.75];

// array_map() — aplica função a cada elemento, retorna novo array
$withTax = array_map(fn(float $p): float => round($p * 1.12, 2), $prices);

// array_filter() — filtra elementos, preserva chaves por padrão
$expensive = array_filter($prices, fn(float $p): bool => $p > 15.0);
// Para re-indexar: array_values(array_filter(...))

// array_reduce() — reduz array a um único valor escalar
$total = array_reduce($prices, fn(float $carry, float $item): float => $carry + $item, 0.0);
echo $total; // 101.25

// ✅ PHP 8.5 Pipeline: filter → map → reduce
$result = $prices
    |> (fn(array $arr): array => array_filter($arr, fn(float $p): bool => $p > 10.0))
    |> (fn(array $arr): array => array_map(fn(float $p): float => $p * 1.12, $arr))
    |> (fn(array $arr): float => array_sum($arr));

echo round($result, 2);

// array_flip() — troca chaves com valores
$status = ['ativo' => 1, 'inativo' => 0, 'pendente' => 2];
$flipped = array_flip($status); // [1 => 'ativo', 0 => 'inativo', 2 => 'pendente']

// array_reverse() — inverte a ordem
$reversed = array_reverse([1, 2, 3, 4, 5]); // [5, 4, 3, 2, 1]

// array_unique() — remove duplicatas (mantém a primeira ocorrência)
$tags = ['php', 'web', 'php', 'backend', 'web'];
$unique = array_unique($tags); // ['php', 'web', 'backend']
```

### Fatiamento e mesclagem

```php
<?php

declare(strict_types=1);

$letters = ['a', 'b', 'c', 'd', 'e', 'f'];

// array_slice() — extrai pedaço SEM modificar o original
$slice = array_slice($letters, 2, 3);         // ['c', 'd', 'e']
$slice = array_slice($letters, -3);           // ['d', 'e', 'f']
$slice = array_slice($letters, 1, 3, true);   // Preserva chaves originais

// array_chunk() — divide em pedaços de tamanho fixo
$chunks = array_chunk($letters, 2);
// [['a', 'b'], ['c', 'd'], ['e', 'f']]

// array_merge() — mescla (valores duplicados são mantidos, chaves numéricas re-indexadas)
$a = ['maçã', 'banana'];
$b = ['laranja', 'uva'];
$merged = array_merge($a, $b); // ['maçã', 'banana', 'laranja', 'uva']

// Spread operator [...] — alternativa moderna ao array_merge para arrays indexados
$merged = [...$a, ...$b]; // ['maçã', 'banana', 'laranja', 'uva']

// array_diff() e array_intersect() — comparação por valores
$all      = [1, 2, 3, 4, 5];
$selected = [2, 4];
$diff     = array_diff($all, $selected);      // [1, 3, 5] — está em $all mas não em $selected
$common   = array_intersect($all, $selected); // [2, 4] — está em ambos
```

### Funções de percurso avançado

```php
<?php

declare(strict_types=1);

$scores = [85, 92, 78, 95, 88];

// array_walk() — modifica elementos in-place (usa referência)
array_walk($scores, function(int &$score, int $key): void {
    $score = min(100, $score + 5); // Bônus de 5 pontos, máximo 100
});

// array_pad() — preenche array até tamanho desejado
$padded = array_pad([1, 2, 3], 5, 0);   // [1, 2, 3, 0, 0]
$padded = array_pad([1, 2, 3], -5, 0);  // [0, 0, 1, 2, 3] (negativo = preenche à esquerda)

// shuffle() — embaralha aleatoriamente (modifica in-place)
// ⚠️ Não é criptograficamente seguro — use apenas para exibição
$items = ['A', 'B', 'C', 'D'];
shuffle($items);

// array_rand() — retorna chave(s) aleatória(s)
$randomKey  = array_rand($items);        // Uma chave
$randomKeys = array_rand($items, 2);     // Array com 2 chaves

// array_product() — produto de todos os elementos
echo array_product([1, 2, 3, 4, 5]); // 120 (fatorial de 5)
```

> ⚠️ **Funções com side effects** (`reset()`, `end()`, `next()`, `prev()`, `current()`)
> movem o ponteiro interno do array e devem ser **evitadas**. Use `array_first()` e
> `array_last()` do PHP 8.5 ou acesso direto por índice/chave.

---

## 29. Superglobais

**Superglobais** são variáveis predefinidas pelo PHP que estão disponíveis em qualquer
escopo — dentro de funções, classes ou arquivos — sem necessidade da keyword `global`.

| Superglobal | Descrição |
|-------------|-----------|
| `$GLOBALS` | Referências a todas as variáveis globais do script |
| `$_SERVER` | Informações do servidor web (headers, caminhos, protocolo) |
| `$_REQUEST` | Dados de `$_GET`, `$_POST` e `$_COOKIE` combinados |
| `$_POST` | Variáveis recebidas via HTTP POST |
| `$_GET` | Variáveis recebidas via HTTP GET (URL query string) |
| `$_FILES` | Arquivos enviados via upload |
| `$_ENV` | Variáveis de ambiente do sistema |
| `$_COOKIE` | Variáveis enviadas via cookies HTTP |
| `$_SESSION` | Variáveis de sessão do usuário |

> 🔒 **Segurança:** Todas as superglobais recebem dados externos — **NUNCA** use
> seus valores diretamente sem validação e sanitização. Dados externos são sempre
> não confiáveis por definição.

---

## 30. $GLOBALS

`$GLOBALS` é um array que contém referências a todas as variáveis globais do script.
É a única superglobal que dá acesso ao escopo global de dentro de funções.

```php
<?php

declare(strict_types=1);

$basePrice = 100.0;
$taxRate   = 0.15;

// ✅ CORRETO: Passe valores como parâmetros — forma profissional
function calculatePrice(float $price, float $tax): float
{
    return $price * (1 + $tax);
}

echo calculatePrice($basePrice, $taxRate); // 115.0

// $GLOBALS como alternativa quando a refatoração não é possível
function legacyCalculate(): float
{
    // Acesso via $GLOBALS — aceitável em código de manutenção
    return $GLOBALS['basePrice'] * (1 + $GLOBALS['taxRate']);
}
```

> ⚠️ **Evite `$GLOBALS` e `global` em código novo.** Eles criam acoplamento implícito
> dificultando testes e manutenção. Prefira sempre passar valores como parâmetros.

### Criando variáveis globais dentro de funções (evite)

```php
<?php

declare(strict_types=1);

$subtotal = 0.0;
$discount = 0.0;

function applyDiscount(float $amount, float $rate): void
{
    // ❌ Criar variáveis globais dentro de funções é má prática
    // $GLOBALS['result'] = $amount * (1 - $rate);

    // ✅ CORRETO: Retorne o valor
    // return $amount * (1 - $rate);
}
```

---

## 31. $_SERVER

`$_SERVER` contém informações fornecidas pelo servidor web: headers HTTP recebidos,
caminhos de arquivo, protocolo, IP do cliente, etc.

> ⚠️ **Atenção:** Entradas de `$_SERVER` são criadas pelo servidor e podem não estar
> disponíveis em todos os ambientes. Headers `HTTP_*` podem ser **forjados pelo cliente** —
> nunca confie neles para decisões de segurança sem validação adicional.

```php
<?php

declare(strict_types=1);

// Informações sobre a requisição atual
$method     = $_SERVER['REQUEST_METHOD'] ?? 'GET';   // 'GET', 'POST', 'PUT', etc.
$scriptName = $_SERVER['SCRIPT_NAME']    ?? '';       // '/index.php'
$queryStr   = $_SERVER['QUERY_STRING']   ?? '';       // 'page=2&sort=name'
$protocol   = $_SERVER['SERVER_PROTOCOL'] ?? 'HTTP/1.1'; // 'HTTP/1.1' ou 'HTTP/2'

// Informações do servidor
$serverName = $_SERVER['SERVER_NAME'] ?? 'localhost'; // 'example.com'
$serverPort = (int) ($_SERVER['SERVER_PORT'] ?? 80);  // 80 ou 443

// Informações do cliente — ⚠️ PODEM SER FORJADAS, use apenas para logging
$remoteAddr  = $_SERVER['REMOTE_ADDR']      ?? '';    // IP do cliente
$userAgent   = $_SERVER['HTTP_USER_AGENT']  ?? '';    // Agente do navegador
$referer     = $_SERVER['HTTP_REFERER']     ?? '';    // Página anterior

// Verificando se a conexão é HTTPS
$isHttps = isset($_SERVER['HTTPS']) && $_SERVER['HTTPS'] !== 'off';

// ✅ Verificação correta do método HTTP
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // Processar dados POST
}

// ✅ Sanitização antes de qualquer output
echo htmlspecialchars($serverName, ENT_QUOTES | ENT_HTML5, 'UTF-8');
```

### Entradas mais importantes do $_SERVER

| Entrada | Descrição |
|---------|-----------|
| `$_SERVER['REQUEST_METHOD']` | Método HTTP da requisição (GET, POST, PUT, DELETE...) |
| `$_SERVER['SCRIPT_NAME']` | Caminho do script atual (ex: `/index.php`) |
| `$_SERVER['QUERY_STRING']` | Query string da URL (ex: `page=2&sort=name`) |
| `$_SERVER['SERVER_NAME']` | Nome do servidor (ex: `example.com`) |
| `$_SERVER['SERVER_PORT']` | Porta do servidor (80, 443...) |
| `$_SERVER['HTTPS']` | Definido se conexão é HTTPS |
| `$_SERVER['REMOTE_ADDR']` | IP do cliente ⚠️ pode ser forjado |
| `$_SERVER['HTTP_USER_AGENT']` | User agent do cliente ⚠️ pode ser forjado |
| `$_SERVER['HTTP_REFERER']` | URL de origem ⚠️ não confiável |
| `$_SERVER['SERVER_PROTOCOL']` | Protocolo HTTP (ex: `HTTP/1.1`) |
| `$_SERVER['PHP_SELF']` | Nome do arquivo atual ⚠️ escapar antes de exibir |
| `$_SERVER['SCRIPT_FILENAME']` | Caminho absoluto do script |
| `$_SERVER['DOCUMENT_ROOT']` | Diretório raiz do servidor web |

---

## 32. $_REQUEST

`$_REQUEST` é a combinação de `$_GET`, `$_POST` e `$_COOKIE` em um único array.
Por ser genérico demais, é **desencorajado** — prefira sempre a superglobal específica.

```php
<?php

declare(strict_types=1);

// ⚠️ $_REQUEST combina GET, POST e COOKIE — ambíguo e potencialmente inseguro
// ✅ PREFIRA: use $_POST, $_GET ou $_COOKIE conforme a fonte esperada

// Razões para evitar $_REQUEST:
// 1. Não documenta a origem esperada dos dados
// 2. Um parâmetro GET pode sobrescrever um POST (ou vice-versa)
// 3. Dificulta análise de segurança e auditoria

// ❌ Evite:
// $name = $_REQUEST['name'];

// ✅ Seja explícito sobre a origem esperada:
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $name = filter_input(INPUT_POST, 'name', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
}
```

---

## 33. $_POST

`$_POST` contém dados enviados via HTTP POST — tipicamente de formulários HTML
com `method="post"`. Os dados **não aparecem na URL** e não têm limite prático de tamanho.

```php
<?php

declare(strict_types=1);

// ✅ Processamento seguro de dados POST
function sanitizeString(string $input): string
{
    // Pipeline de sanitização com pipe operator (PHP 8.5)
    return $input
        |> trim(...)
        |> stripslashes(...)
        |> (fn(string $s): string => htmlspecialchars($s, ENT_QUOTES | ENT_HTML5, 'UTF-8'));
}

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // ✅ filter_input() é mais seguro que acessar $_POST diretamente
    $rawName  = filter_input(INPUT_POST, 'name',  FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
    $rawEmail = filter_input(INPUT_POST, 'email', FILTER_SANITIZE_EMAIL)          ?? '';

    // Validação de e-mail
    $email = filter_var($rawEmail, FILTER_VALIDATE_EMAIL);

    if ($email === false) {
        echo 'E-mail inválido!';
    } else {
        $name = sanitizeString($rawName);

        if (empty($name)) {
            echo 'Nome é obrigatório!';
        } else {
            // ✅ Exibe com escape — nunca exiba dados do usuário sem htmlspecialchars()
            echo 'Bem-vindo, ' . htmlspecialchars($name, ENT_QUOTES | ENT_HTML5, 'UTF-8') . '!';
        }
    }
}
```

Formulário HTML correspondente (arquivo separado ou mesmo arquivo):

```html
<!DOCTYPE html>
<html lang="pt-BR">
<body>

<form method="POST" action="<?php echo htmlspecialchars($_SERVER['PHP_SELF'], ENT_QUOTES | ENT_HTML5, 'UTF-8'); ?>">
    <label for="name">Nome:</label>
    <input type="text" id="name" name="name" required>

    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email" required>

    <button type="submit">Enviar</button>
</form>

</body>
</html>
```

### Quando usar POST?

- Envio de senhas ou dados sensíveis
- Criação, atualização ou exclusão de registros (operações de escrita)
- Upload de arquivos
- Dados que não devem aparecer na URL ou no histórico do navegador
- Payloads grandes (sem limite prático no body HTTP)

---

## 34. $_GET

`$_GET` contém dados enviados via URL query string ou formulários com `method="get"`.
Os dados **aparecem na URL**, podem ser favoritados e têm limite de tamanho (~2000 caracteres).

```php
<?php

declare(strict_types=1);

// URL de exemplo: /products.php?category=eletronicos&page=2&sort=price

// ✅ filter_input() — forma segura de acessar $_GET
$category = filter_input(INPUT_GET, 'category', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
$page     = filter_input(INPUT_GET, 'page',     FILTER_VALIDATE_INT, [
    'options' => ['default' => 1, 'min_range' => 1],
]) ?? 1;
$sort     = filter_input(INPUT_GET, 'sort', FILTER_SANITIZE_SPECIAL_CHARS) ?? 'name';

// Whitelist de valores permitidos para sort — nunca confie no input direto
$allowedSorts = ['name', 'price', 'date'];
$sort = in_array($sort, $allowedSorts, strict: true) ? $sort : 'name';

// Exibição segura
echo 'Categoria: ' . htmlspecialchars($category, ENT_QUOTES | ENT_HTML5, 'UTF-8');
echo 'Página: ' . $page;
echo 'Ordenar por: ' . htmlspecialchars($sort, ENT_QUOTES | ENT_HTML5, 'UTF-8');
```

### Quando usar GET?

- Filtros, buscas e navegação (operações de leitura)
- Parâmetros que o usuário pode favoritar ou compartilhar (a URL carrega o estado)
- Paginação (`?page=3`), ordenação (`?sort=price`), filtros (`?category=php`)
- **Nunca** para senhas, tokens ou dados sensíveis — aparecem em logs e histórico

### Comparação GET vs POST

| | `$_GET` | `$_POST` |
|--|---------|---------|
| Visibilidade | URL pública | Body HTTP privado |
| Favoritável | ✅ Sim | ❌ Não |
| Limite de tamanho | ~2000 caracteres | Sem limite prático |
| Cache do navegador | ✅ Pode ser cacheado | ❌ Não |
| Senhas/dados sensíveis | ❌ **NUNCA** | ✅ Use POST |
| Operações de escrita | ❌ Evite (não idempotente) | ✅ Correto |
| Recarregar página | Reexecuta (seguro) | Re-envia dados (perigoso) |

---

## 35. Expressões Regulares (RegEx)

Uma expressão regular (RegEx) é um padrão de busca que descreve uma sequência de caracteres.
Em PHP, regex são delimitadas por `/padrão/modificadores` e usadas pelas funções `preg_*`.

### Sintaxe básica

```
/padrão/modificadores
```

- **Delimitador** — qualquer caractere não alfanumérico, geralmente `/`
- **Padrão** — a sequência de busca
- **Modificadores** — alteram o comportamento da busca

```php
<?php

declare(strict_types=1);

// Padrão simples: busca case-insensitive por "php"
$pattern = '/php/i';

// Padrão de e-mail simplificado
$emailPattern = '/^[a-zA-Z0-9._%+\-]+@[a-zA-Z0-9.\-]+\.[a-zA-Z]{2,}$/';

// Padrão de CEP brasileiro: 00000-000
$cepPattern = '/^\d{5}-?\d{3}$/';

// Padrão de CPF: 000.000.000-00
$cpfPattern = '/^\d{3}\.\d{3}\.\d{3}-\d{2}$/';
```

### Modificadores

| Modificador | Descrição |
|-------------|-----------|
| `i` | Case-insensitive (ignora maiúsculas/minúsculas) |
| `m` | Multiline — `^` e `$` se aplicam a cada linha |
| `s` | Dotall — `.` passa a incluir `\n` |
| `u` | Unicode — habilita suporte correto a UTF-8 |
| `x` | Estendido — ignora espaços e permite comentários no padrão |

### Metacaracteres e classes de caractere

| Expressão | Descrição |
|-----------|-----------|
| `.` | Qualquer caractere (exceto `\n` sem `/s`) |
| `^` | Início da string (ou da linha com `/m`) |
| `$` | Fim da string (ou da linha com `/m`) |
| `\d` | Dígito `[0-9]` |
| `\D` | Não-dígito |
| `\w` | Alfanumérico + underscore `[a-zA-Z0-9_]` |
| `\W` | Não-alfanumérico |
| `\s` | Espaço em branco (`\t`, `\n`, `\r`, espaço) |
| `\S` | Não-espaço |
| `\b` | Limite de palavra (word boundary) |
| `[abc]` | Um dos caracteres listados |
| `[^abc]` | Qualquer caractere EXCETO os listados |
| `[a-z]` | Intervalo de caracteres |
| `a\|b` | "a" OU "b" |

### Quantificadores

| Quantificador | Descrição |
|---------------|-----------|
| `+` | 1 ou mais |
| `*` | 0 ou mais |
| `?` | 0 ou 1 (opcional) |
| `{n}` | Exatamente n vezes |
| `{n,m}` | Entre n e m vezes |
| `{n,}` | Pelo menos n vezes |

---

## 36. Funções de RegEx

### preg_match() — verifica se o padrão existe

```php
<?php

declare(strict_types=1);

$text = 'Bem-vindo ao PHP 8.5!';

// Retorna 1 (encontrou), 0 (não encontrou), false (erro)
$found = preg_match('/php/i', $text);
var_dump($found); // int(1)

// Capturando grupos com o terceiro parâmetro
$version = '2025-04-07';
preg_match('/^(\d{4})-(\d{2})-(\d{2})$/', $version, $matches);
// $matches[0] = '2025-04-07' (match completo)
// $matches[1] = '2025' (grupo 1)
// $matches[2] = '04'   (grupo 2)
// $matches[3] = '07'   (grupo 3)

[$fullMatch, $year, $month, $day] = $matches;

// Validação de e-mail com regex (use filter_var em produção!)
function isValidEmail(string $email): bool
{
    return (bool) preg_match(
        '/^[a-zA-Z0-9._%+\-]+@[a-zA-Z0-9.\-]+\.[a-zA-Z]{2,}$/u',
        $email
    );
}

var_dump(isValidEmail('usuario@example.com')); // bool(true)
var_dump(isValidEmail('inválido@'));           // bool(false)
```

### preg_match_all() — conta e captura todas as ocorrências

```php
<?php

declare(strict_types=1);

$html = '<p>Visite <a href="https://php.net">PHP.net</a> e <a href="https://example.com">Example</a></p>';

// Extrai todos os URLs do HTML
$count = preg_match_all('/href="([^"]+)"/', $html, $matches);

echo "Links encontrados: {$count}";
// $matches[0] = array de matches completos
// $matches[1] = array de grupos capturados (os URLs)
foreach ($matches[1] as $url) {
    echo htmlspecialchars($url, ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
// https://php.net
// https://example.com
```

### preg_replace() — substitui matches

```php
<?php

declare(strict_types=1);

$text = 'Contato: (11) 98765-4321 ou (21) 3456-7890';

// Mascara números de telefone
$masked = preg_replace('/\((\d{2})\) \d{4,5}-\d{4}/', '(**) ****-****', $text);
echo $masked; // Contato: (**) ****-**** ou (**) ****-****

// Normaliza múltiplos espaços em um único
$normalized = preg_replace('/\s+/', ' ', '  Texto   com   espaços  extras  ');
echo trim($normalized); // 'Texto com espaços extras'

// preg_replace_callback() — substitui com lógica customizada
$template = 'Olá, {{name}}! Você tem {{count}} mensagens.';
$data = ['name' => 'Ana', 'count' => '5'];

$result = preg_replace_callback(
    '/\{\{(\w+)\}\}/',
    fn(array $matches): string => htmlspecialchars(
        $data[$matches[1]] ?? '',
        ENT_QUOTES | ENT_HTML5,
        'UTF-8'
    ),
    $template
);

echo $result; // Olá, Ana! Você tem 5 mensagens.
```

### preg_split() — divide string usando regex como separador

```php
<?php

declare(strict_types=1);

// Divide por vírgula, ponto-e-vírgula ou espaço (qualquer combinação)
$csv = 'PHP; Python, JavaScript  Go,Ruby';
$languages = preg_split('/[\s,;]+/', $csv, flags: PREG_SPLIT_NO_EMPTY);

// ✅ Pipe operator para limpar e processar cada elemento
$cleaned = array_map(
    fn(string $lang): string => $lang |> trim(...),
    $languages
);

print_r($cleaned); // ['PHP', 'Python', 'JavaScript', 'Go', 'Ruby']
```

### preg_grep() — filtra array por padrão

```php
<?php

declare(strict_types=1);

$items = ['Maçã', 'Manga', 'Banana', 'Melancia', 'Laranja', 'Melão'];

// Filtra itens que começam com "M" (case-insensitive)
$withM = preg_grep('/^m/iu', $items);
// ['Manga', 'Melancia', 'Melão']

// PREG_GREP_INVERT — inverte: retorna os que NÃO correspondem
$withoutM = preg_grep('/^m/iu', $items, PREG_GREP_INVERT);
// ['Maçã', 'Banana', 'Laranja']
```

### Grupos e lookahead

```php
<?php

declare(strict_types=1);

// Grupos nomeados — mais legível que grupos numerados
$date = '07/04/2025';
preg_match('/(?P<day>\d{2})\/(?P<month>\d{2})\/(?P<year>\d{4})/', $date, $m);

echo $m['day'];   // 07
echo $m['month']; // 04
echo $m['year'];  // 2025

// Lookahead positivo — "PHP" seguido de espaço e número
$text = 'PHP 8.5 é incrível. PHP é server-side.';
preg_match_all('/PHP(?=\s\d)/', $text, $matches);
// Encontra apenas 'PHP 8.5', não o segundo 'PHP'

// Lookahead negativo — palavras que NÃO são seguidas por dígito
preg_match_all('/PHP(?!\s\d)/', $text, $matches);
// Encontra apenas o segundo 'PHP'
```

---

## 37. Formulários HTML — Coleta de Dados

Formulários HTML são a principal forma de coletar dados do usuário no backend PHP.
**Segurança é a prioridade número 1** ao processar qualquer dado de formulário.

### GET vs POST — escolha correta

```
✅ POST para: login, cadastro, pagamentos, deletar registros, uploads
✅ GET  para: busca, filtros, paginação, navegação — dados não sensíveis
```

### Formulário POST completo e seguro

```php
<?php

declare(strict_types=1);

/**
 * Sanitiza input de texto: remove espaços extras, backslashes e escapa HTML.
 * Use APENAS para exibição — não substitui validação de domínio.
 */
function sanitizeInput(string $input): string
{
    return $input
        |> trim(...)
        |> stripslashes(...)
        |> (fn(string $s): string => htmlspecialchars($s, ENT_QUOTES | ENT_HTML5, 'UTF-8'));
}

$errors = [];
$name   = '';
$email  = '';

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // ✅ Lê com null coalescing — nunca acesse $_POST sem fallback
    $rawName  = $_POST['name']  ?? '';
    $rawEmail = $_POST['email'] ?? '';

    // Validação de nome
    $name = sanitizeInput($rawName);

    if (empty($name)) {
        $errors[] = 'Nome é obrigatório.';
    } elseif (!preg_match('/^[a-zA-ZÀ-ÿ\s]{2,100}$/u', $name)) {
        $errors[] = 'Nome deve conter apenas letras e espaços (2-100 caracteres).';
    }

    // Validação de e-mail com filter_var
    $email = filter_var(trim($rawEmail), FILTER_VALIDATE_EMAIL);

    if ($email === false) {
        $errors[] = 'E-mail inválido.';
        $email = '';
    }

    // Processa apenas se não houver erros
    if (empty($errors)) {
        // ✅ Dados validados — pode usar com segurança
        echo 'Bem-vindo, ' . htmlspecialchars($name, ENT_QUOTES | ENT_HTML5, 'UTF-8') . '!';
    }
}
?>

<!DOCTYPE html>
<html lang="pt-BR">
<body>

<?php if (!empty($errors)): ?>
    <ul class="errors">
        <?php foreach ($errors as $error): ?>
            <li><?= htmlspecialchars($error, ENT_QUOTES | ENT_HTML5, 'UTF-8') ?></li>
        <?php endforeach; ?>
    </ul>
<?php endif; ?>

<form method="POST" action="<?= htmlspecialchars($_SERVER['PHP_SELF'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>">
    <label for="name">Nome:</label>
    <input type="text" id="name" name="name"
           value="<?= htmlspecialchars($name, ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>"
           required maxlength="100">

    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email"
           value="<?= htmlspecialchars($email, ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>"
           required>

    <button type="submit">Enviar</button>
</form>

</body>
</html>
```

### Formulário GET para busca/filtro

```php
<?php

declare(strict_types=1);

// ✅ GET é ideal para busca — a URL pode ser favoritada e compartilhada
$search = filter_input(INPUT_GET, 'q', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
$page   = filter_input(INPUT_GET, 'page', FILTER_VALIDATE_INT, [
    'options' => ['default' => 1, 'min_range' => 1, 'max_range' => 1000],
]) ?? 1;
?>

<form method="GET" action="/search">
    <input type="search" name="q"
           value="<?= htmlspecialchars($search, ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>"
           placeholder="Buscar...">
    <button type="submit">Buscar</button>
</form>

<?php if ($search !== ''): ?>
    <p>Resultados para: <strong><?= htmlspecialchars($search, ENT_QUOTES | ENT_HTML5, 'UTF-8') ?></strong></p>
<?php endif; ?>
```

---

## 38. Validação de Formulários

Validação robusta é a linha de defesa mais importante contra dados maliciosos.
PHP oferece as funções `filter_var()` e `filter_input()` como ferramentas nativas.

### Classe de validação reutilizável (PHP 8.5)

```php
<?php

declare(strict_types=1);

/**
 * Serviço de validação de inputs de formulário.
 * Centraliza regras de validação com mensagens em português.
 */
final class FormValidator
{
    /** @var array<string, string[]> */
    private array $errors = [];

    /**
     * Valida e retorna um nome de pessoa.
     *
     * @throws void — acumula erros internamente
     */
    public function validateName(string $rawName, string $field = 'name'): string
    {
        $name = trim($rawName);

        if (empty($name)) {
            $this->errors[$field][] = 'O nome é obrigatório.';
            return '';
        }

        if (mb_strlen($name) < 2 || mb_strlen($name) > 100) {
            $this->errors[$field][] = 'O nome deve ter entre 2 e 100 caracteres.';
        }

        if (!preg_match('/^[\p{L}\s\'-]+$/u', $name)) {
            $this->errors[$field][] = 'O nome contém caracteres inválidos.';
        }

        return $name;
    }

    /**
     * Valida e retorna um endereço de e-mail.
     */
    public function validateEmail(string $rawEmail, string $field = 'email'): string
    {
        $email = filter_var(trim($rawEmail), FILTER_VALIDATE_EMAIL);

        if ($email === false) {
            $this->errors[$field][] = 'Informe um e-mail válido.';
            return '';
        }

        return $email;
    }

    /**
     * Valida e retorna uma URL (campo opcional).
     */
    public function validateUrl(string $rawUrl, string $field = 'website'): string
    {
        if (empty(trim($rawUrl))) {
            return ''; // Campo opcional — vazio é válido
        }

        $url = filter_var(trim($rawUrl), FILTER_VALIDATE_URL);

        if ($url === false) {
            $this->errors[$field][] = 'Informe uma URL válida (ex: https://example.com).';
            return '';
        }

        return $url;
    }

    /**
     * Valida radio button com lista de valores permitidos.
     *
     * @param string[] $allowed
     */
    public function validateChoice(string $rawValue, array $allowed, string $field): string
    {
        $value = trim($rawValue);

        if (!in_array($value, $allowed, strict: true)) {
            $this->errors[$field][] = "Selecione uma opção válida.";
            return '';
        }

        return $value;
    }

    /** @return array<string, string[]> */
    public function getErrors(): array
    {
        return $this->errors;
    }

    public function hasErrors(): bool
    {
        return !empty($this->errors);
    }

    public function isValid(): bool
    {
        return empty($this->errors);
    }
}
```

### Uso completo do FormValidator

```php
<?php

declare(strict_types=1);

$validator = new FormValidator();
$formData  = [];

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $formData = [
        'name'    => $validator->validateName($_POST['name']    ?? ''),
        'email'   => $validator->validateEmail($_POST['email']  ?? ''),
        'website' => $validator->validateUrl($_POST['website']  ?? ''),
        'gender'  => $validator->validateChoice(
            $_POST['gender'] ?? '',
            allowed: ['female', 'male', 'other', 'prefer_not'],
            field: 'gender'
        ),
    ];

    if ($validator->isValid()) {
        // ✅ Todos os dados estão validados — processa com segurança
        // Ex: salvar no banco, enviar e-mail, redirecionar...
        echo 'Formulário válido! Dados processados.';
    }
}

// Exibe erros na view
$errors = $validator->getErrors();

foreach ($errors as $field => $fieldErrors) {
    foreach ($fieldErrors as $errorMessage) {
        echo "<p class='error'>{$field}: "
            . htmlspecialchars($errorMessage, ENT_QUOTES | ENT_HTML5, 'UTF-8')
            . "</p>";
    }
}
```

### Funções nativas de validação — referência

```php
<?php

declare(strict_types=1);

// filter_var() — validação e sanitização
$email = filter_var('usuario@example.com', FILTER_VALIDATE_EMAIL); // string ou false
$url   = filter_var('https://php.net',     FILTER_VALIDATE_URL);   // string ou false
$int   = filter_var('42',                  FILTER_VALIDATE_INT);   // int ou false
$float = filter_var('3.14',               FILTER_VALIDATE_FLOAT);  // float ou false
$ip    = filter_var('192.168.1.1',        FILTER_VALIDATE_IP);     // string ou false
$bool  = filter_var('true',               FILTER_VALIDATE_BOOLEAN, FILTER_NULL_ON_FAILURE);

// filter_input() — acessa superglobal com validação em uma etapa
$name = filter_input(INPUT_POST, 'name', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
$age  = filter_input(INPUT_GET,  'age',  FILTER_VALIDATE_INT, [
    'options' => ['min_range' => 0, 'max_range' => 150, 'default' => 0],
]);

// Verificações manuais úteis
$cpf  = preg_match('/^\d{3}\.\d{3}\.\d{3}-\d{2}$/', $_POST['cpf'] ?? '');
$cep  = preg_match('/^\d{5}-?\d{3}$/',               $_POST['cep'] ?? '');
$date = \DateTime::createFromFormat('d/m/Y', $_POST['date'] ?? '');
```

### Regras de segurança para formulários — checklist

| Regra | Razão |
|-------|-------|
| ✅ Sempre use `htmlspecialchars()` no output | Previne XSS |
| ✅ Use `filter_var()` ou regex para validar | Dados não confiáveis por definição |
| ✅ Use HTTPS em formulários com dados sensíveis | Criptografa o tráfego |
| ✅ Implemente token CSRF em formulários POST | Previne Cross-Site Request Forgery |
| ✅ Escape `$_SERVER['PHP_SELF']` no `action` | Previne XSS via URL forjada |
| ✅ Use `password_hash()` para senhas | Nunca armazene senha em texto plano |
| ✅ Prefira `$_POST` / `$_GET` a `$_REQUEST` | Torna a origem dos dados explícita |
| ❌ Nunca concatene dados do usuário em SQL | SQL Injection |
| ❌ Nunca use `extract()` em `$_POST` / `$_GET` | Injeção de variáveis |
| ❌ Nunca confie em `$_SERVER['HTTP_*']` para segurança | Headers podem ser forjados |

### Token CSRF — implementação básica

```php
<?php

declare(strict_types=1);

// Configurar sessão segura ANTES de session_start()
ini_set('session.cookie_httponly', '1');
ini_set('session.cookie_secure',   '1');
ini_set('session.cookie_samesite', 'Strict');
ini_set('session.use_strict_mode', '1');
session_start();

// Gera token CSRF na primeira visita
if (empty($_SESSION['csrf_token'])) {
    $_SESSION['csrf_token'] = bin2hex(random_bytes(32)); // 64 caracteres hex
}

// Validação no processamento POST
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $submittedToken = $_POST['csrf_token'] ?? '';

    // ✅ hash_equals() previne timing attacks
    if (!hash_equals($_SESSION['csrf_token'], $submittedToken)) {
        http_response_code(403);
        exit('Token CSRF inválido. Requisição rejeitada.');
    }

    // Regenera o token após uso (one-time token)
    $_SESSION['csrf_token'] = bin2hex(random_bytes(32));

    // ... processar formulário com segurança
}
?>

<!-- Inclua o token como campo oculto em TODOS os formulários POST -->
<form method="POST" action="/process">
    <input type="hidden" name="csrf_token"
           value="<?= htmlspecialchars($_SESSION['csrf_token'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>">
    <!-- demais campos -->
    <button type="submit">Enviar</button>
</form>
```

---

## Referência Rápida — Funções Essenciais PHP 8.5

### Strings
| Função | Descrição |
|--------|-----------|
| `strlen($s)` | Comprimento em bytes |
| `mb_strlen($s)` | Comprimento em caracteres (UTF-8) |
| `strtolower($s)` | Minúsculas |
| `strtoupper($s)` | Maiúsculas |
| `trim($s)` | Remove espaços nas bordas |
| `str_replace($old, $new, $s)` | Substitui texto |
| `str_contains($s, $needle)` | Verifica se contém substring |
| `str_starts_with($s, $prefix)` | Verifica início |
| `str_ends_with($s, $suffix)` | Verifica fim |
| `substr($s, $start, $len)` | Fatia a string |
| `explode($sep, $s)` | String → array |
| `implode($sep, $arr)` | Array → string |
| `sprintf($format, ...)` | Formata string |
| `htmlspecialchars($s)` | ✅ Escapa para HTML (segurança!) |

### Arrays
| Função | Descrição |
|--------|-----------|
| `array_first($arr)` | 🆕 PHP 8.5: primeiro elemento |
| `array_last($arr)` | 🆕 PHP 8.5: último elemento |
| `count($arr)` | Número de elementos |
| `array_push($arr, ...)` | Adiciona ao final |
| `array_pop($arr)` | Remove e retorna o último |
| `array_shift($arr)` | Remove e retorna o primeiro |
| `array_unshift($arr, ...)` | Adiciona ao início |
| `array_splice($arr, ...)` | Remove/insere em posição |
| `array_merge($a, $b)` | Mescla arrays |
| `array_filter($arr, $fn)` | Filtra elementos |
| `array_map($fn, $arr)` | Transforma elementos |
| `array_reduce($arr, $fn, $init)` | Reduz a um valor |
| `array_unique($arr)` | Remove duplicatas |
| `in_array($val, $arr, true)` | Verifica se existe (strict!) |
| `array_search($val, $arr)` | Retorna a chave do valor |
| `array_column($arr, $col)` | Extrai coluna de array 2D |
| `sort($arr)` / `rsort($arr)` | Ordena indexado |
| `asort($arr)` / `arsort($arr)` | Ordena associativo por valor |
| `ksort($arr)` / `krsort($arr)` | Ordena associativo por chave |
| `usort($arr, $fn)` | Ordenação customizada |

### RegEx
| Função | Descrição |
|--------|-----------|
| `preg_match($pat, $str)` | Verifica se padrão existe |
| `preg_match_all($pat, $str)` | Conta e captura todas ocorrências |
| `preg_replace($pat, $rep, $str)` | Substitui matches |
| `preg_replace_callback($pat, $fn, $str)` | Substitui com lógica customizada |
| `preg_split($pat, $str)` | Divide string pelo padrão |
| `preg_grep($pat, $arr)` | Filtra array por padrão |

### Formulários e Filtros
| Função | Descrição |
|--------|-----------|
| `filter_var($val, FILTER_*)` | Valida ou sanitiza um valor |
| `filter_input(INPUT_*, $name, FILTER_*)` | Lê e filtra superglobal |
| `htmlspecialchars($s, ENT_QUOTES\|ENT_HTML5, 'UTF-8')` | ✅ Escape de output |
| `strip_tags($s)` | Remove tags HTML/XML |
| `trim($s)` / `ltrim()` / `rtrim()` | Remove espaços |
| `stripslashes($s)` | Remove backslashes |
| `random_bytes($len)` | Gera bytes aleatórios seguros |
| `bin2hex($bytes)` | Converte bytes em hex (para tokens) |
| `hash_equals($known, $user)` | Comparação timing-safe |

### Matemática
| Função | Descrição |
|--------|-----------|
| `abs($n)` | Valor absoluto |
| `round($n, $dec)` | Arredonda |
| `ceil($n)` | Arredonda para cima |
| `floor($n)` | Arredonda para baixo |
| `sqrt($n)` | Raiz quadrada |
| `pow($base, $exp)` | Potência (ou `**`) |
| `min(...)` / `max(...)` | Mínimo / máximo |
| `random_int($min, $max)` | ✅ Aleatório seguro criptograficamente |
| `is_nan($n)` | Verifica NaN |
| `is_infinite($n)` | Verifica infinito |

### Segurança — Funções Obrigatórias
| Função | Uso |
|--------|-----|
| `htmlspecialchars($s, ENT_QUOTES\|ENT_HTML5, 'UTF-8')` | Escape de output HTML |
| `filter_var($val, FILTER_VALIDATE_EMAIL)` | Validação de e-mail |
| `password_hash($pass, PASSWORD_ARGON2ID)` | Hash de senha |
| `password_verify($pass, $hash)` | Verificação de senha |
| `random_bytes($len)` | Bytes aleatórios seguros |
| `hash_equals($known, $user)` | Comparação timing-safe |

---

## 39. Campos Obrigatórios e Mensagens de Erro

Formulários raramente aceitam todo tipo de input. Campos obrigatórios precisam de
validação explícita, com mensagens de erro claras exibidas próximas ao campo problemático.

### Estratégia de validação com acumulação de erros

A abordagem profissional é acumular **todos** os erros antes de exibir — nunca pare
na primeira falha e force o usuário a descobrir os erros um por um.

```php
<?php

declare(strict_types=1);

/**
 * Sanitiza input: remove espaços, backslashes e escapa HTML.
 * Adequado para exibição — não substitui validação de domínio.
 */
function sanitizeInput(string $rawInput): string
{
    return $rawInput
        |> trim(...)
        |> stripslashes(...)
        |> (fn(string $s): string => htmlspecialchars($s, ENT_QUOTES | ENT_HTML5, 'UTF-8'));
}

// Inicializa variáveis de erro e de valor — sempre inicialize antes de usar
$errors = [
    'name'    => '',
    'email'   => '',
    'gender'  => '',
    'website' => '',
];

$formValues = [
    'name'    => '',
    'email'   => '',
    'gender'  => '',
    'website' => '',
    'comment' => '',
];

if ($_SERVER['REQUEST_METHOD'] === 'POST') {

    // ── Campo obrigatório: Nome ─────────────────────────────────────────────
    $rawName = $_POST['name'] ?? '';

    if (empty(trim($rawName))) {
        $errors['name'] = 'O nome é obrigatório.';
    } else {
        $formValues['name'] = sanitizeInput($rawName);

        // Validação de formato: apenas letras, espaços, hifens e apóstrofos
        if (!preg_match('/^[\p{L}\s\'\-]{2,100}$/u', $formValues['name'])) {
            $errors['name'] = 'O nome deve conter apenas letras e espaços (2–100 caracteres).';
        }
    }

    // ── Campo obrigatório: E-mail ───────────────────────────────────────────
    $rawEmail = $_POST['email'] ?? '';

    if (empty(trim($rawEmail))) {
        $errors['email'] = 'O e-mail é obrigatório.';
    } else {
        $validEmail = filter_var(trim($rawEmail), FILTER_VALIDATE_EMAIL);

        if ($validEmail === false) {
            $errors['email'] = 'Informe um e-mail válido (ex: usuario@dominio.com).';
        } else {
            $formValues['email'] = $validEmail;
        }
    }

    // ── Campo opcional: Website ─────────────────────────────────────────────
    $rawWebsite = $_POST['website'] ?? '';

    if (!empty(trim($rawWebsite))) {
        $validUrl = filter_var(trim($rawWebsite), FILTER_VALIDATE_URL);

        if ($validUrl === false) {
            $errors['website'] = 'Informe uma URL válida (ex: https://example.com).';
        } else {
            $formValues['website'] = $validUrl;
        }
    }

    // ── Campo opcional: Comentário ──────────────────────────────────────────
    $rawComment = $_POST['comment'] ?? '';
    $formValues['comment'] = sanitizeInput($rawComment); // Sempre sanitize, mesmo opcional

    // ── Campo obrigatório: Gênero (radio button) ────────────────────────────
    $allowedGenders = ['female', 'male', 'other', 'prefer_not'];
    $rawGender      = $_POST['gender'] ?? '';

    if (empty($rawGender)) {
        $errors['gender'] = 'Selecione uma opção de gênero.';
    } elseif (!in_array($rawGender, $allowedGenders, strict: true)) {
        $errors['gender'] = 'Opção de gênero inválida.';
    } else {
        $formValues['gender'] = $rawGender;
    }

    // ── Processa apenas se não houver erros ─────────────────────────────────
    $hasErrors = array_filter($errors, fn(string $e): bool => $e !== '');

    if (empty($hasErrors)) {
        // ✅ Dados validados — processar (salvar, enviar e-mail, redirecionar...)
        echo 'Formulário válido! Obrigado, '
            . htmlspecialchars($formValues['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8')
            . '.';
    }
}
```

### Exibindo erros inline no HTML

```html
<form method="POST"
      action="<?= htmlspecialchars($_SERVER['PHP_SELF'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>">

    <!-- Nome -->
    <label for="name">Nome: <span aria-hidden="true">*</span></label>
    <input type="text" id="name" name="name" required maxlength="100"
           value="<?= htmlspecialchars($formValues['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>">
    <?php if ($errors['name'] !== ''): ?>
        <span class="error" role="alert">
            <?= htmlspecialchars($errors['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>
        </span>
    <?php endif; ?>

    <!-- E-mail -->
    <label for="email">E-mail: <span aria-hidden="true">*</span></label>
    <input type="email" id="email" name="email" required
           value="<?= htmlspecialchars($formValues['email'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>">
    <?php if ($errors['email'] !== ''): ?>
        <span class="error" role="alert">
            <?= htmlspecialchars($errors['email'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>
        </span>
    <?php endif; ?>

    <!-- Website (opcional) -->
    <label for="website">Website:</label>
    <input type="url" id="website" name="website"
           value="<?= htmlspecialchars($formValues['website'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>">
    <?php if ($errors['website'] !== ''): ?>
        <span class="error" role="alert">
            <?= htmlspecialchars($errors['website'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>
        </span>
    <?php endif; ?>

    <!-- Comentário (opcional) -->
    <label for="comment">Comentário:</label>
    <textarea id="comment" name="comment" rows="5" cols="40"
    ><?= htmlspecialchars($formValues['comment'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?></textarea>

    <!-- Gênero (radio) -->
    <fieldset>
        <legend>Gênero: <span aria-hidden="true">*</span></legend>

        <?php
        $genderOptions = [
            'female'     => 'Feminino',
            'male'       => 'Masculino',
            'other'      => 'Outro',
            'prefer_not' => 'Prefiro não informar',
        ];

        foreach ($genderOptions as $value => $label):
            $checked = ($formValues['gender'] === $value) ? 'checked' : '';
        ?>
            <label>
                <input type="radio" name="gender"
                       value="<?= htmlspecialchars($value, ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>"
                       <?= $checked ?>>
                <?= htmlspecialchars($label, ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>
            </label>
        <?php endforeach; ?>

        <?php if ($errors['gender'] !== ''): ?>
            <span class="error" role="alert">
                <?= htmlspecialchars($errors['gender'], ENT_QUOTES | ENT_HTML5, 'UTF-8') ?>
            </span>
        <?php endif; ?>
    </fieldset>

    <button type="submit">Enviar</button>
</form>
```

> 💡 **Persistência de valores:** note que cada campo recupera seu valor anterior com
> `$formValues[...]`. Isso evita que o usuário precise redigitar tudo após um erro de validação.

---

## 40. Validação de E-mail e URL

### Validação de nome com Unicode

```php
<?php

declare(strict_types=1);

/**
 * Valida nome de pessoa com suporte a caracteres acentuados (UTF-8).
 *
 * @return string Nome validado ou lança exception
 * @throws \InvalidArgumentException Se o nome for inválido
 */
function validatePersonName(string $rawName): string
{
    $name = trim($rawName);

    if (mb_strlen($name) < 2 || mb_strlen($name) > 100) {
        throw new \InvalidArgumentException('O nome deve ter entre 2 e 100 caracteres.');
    }

    // \p{L} = qualquer letra Unicode; \p{M} = marcas (acentos); /u = modo Unicode
    if (!preg_match('/^[\p{L}\p{M}\s\'\-\.]+$/u', $name)) {
        throw new \InvalidArgumentException(
            'O nome contém caracteres não permitidos. Use apenas letras, espaços, hifens e apóstrofos.'
        );
    }

    // Normaliza múltiplos espaços em um único
    return preg_replace('/\s+/', ' ', $name) ?? $name;
}

// Exemplos de uso
try {
    echo validatePersonName('Maria da Silva');    // ✅ Maria da Silva
    echo validatePersonName("D'Avila");           // ✅ D'Avila
    echo validatePersonName('João Müller');        // ✅ João Müller (Unicode)
    echo validatePersonName('Ana<script>');        // ❌ Exception
} catch (\InvalidArgumentException $e) {
    echo 'Erro: ' . htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
```

### Validação de e-mail

```php
<?php

declare(strict_types=1);

/**
 * Valida um endereço de e-mail.
 * filter_var() com FILTER_VALIDATE_EMAIL é a abordagem oficial do PHP.
 *
 * @return string E-mail validado (lowercase) ou '' se inválido
 */
function validateEmail(string $rawEmail): string
{
    // Normaliza: remove espaços e converte para minúsculas
    $email = strtolower(trim($rawEmail));

    $validated = filter_var($email, FILTER_VALIDATE_EMAIL);

    if ($validated === false) {
        return '';
    }

    // Verifica que o domínio tem ao menos um ponto (ex: "a@b" seria válido para filter_var)
    [, $domain] = explode('@', $validated, 2);

    if (!str_contains($domain, '.')) {
        return '';
    }

    return $validated;
}

// Testes
$emails = [
    'usuario@example.com',   // ✅
    'nome+tag@sub.dominio.br', // ✅
    'invalido@',             // ❌
    'sem-arroba.com',        // ❌
    'espaço @example.com',   // ❌
];

foreach ($emails as $email) {
    $result = validateEmail($email);
    $valid  = $result !== '' ? '✅' : '❌';
    echo "{$valid} '{$email}' → '{$result}'";
}
```

### Validação de URL

```php
<?php

declare(strict_types=1);

/**
 * Valida uma URL, exigindo protocolo HTTPS ou HTTP.
 * Rejeita protocolos inseguros como javascript:, data:, ftp:.
 *
 * @return string URL validada ou '' se inválida
 */
function validateUrl(string $rawUrl): string
{
    $url = trim($rawUrl);

    if (empty($url)) {
        return ''; // Campo opcional — vazio é aceitável
    }

    // Rejeita protocolos perigosos antes de qualquer outra verificação
    $lowerUrl = strtolower($url);

    if (
        str_starts_with($lowerUrl, 'javascript:') ||
        str_starts_with($lowerUrl, 'data:') ||
        str_starts_with($lowerUrl, 'vbscript:')
    ) {
        return ''; // Protocolo proibido — potencial XSS
    }

    // Adiciona https:// se nenhum protocolo for informado
    if (!str_starts_with($lowerUrl, 'http://') && !str_starts_with($lowerUrl, 'https://')) {
        $url = 'https://' . $url;
    }

    $validated = filter_var($url, FILTER_VALIDATE_URL);

    if ($validated === false) {
        return '';
    }

    // ✅ PHP 8.5: URI Extension para análise estruturada
    try {
        $uri = new Uri\Rfc3986\Uri($validated);

        // Exige scheme http ou https
        if (!in_array($uri->getScheme(), ['http', 'https'], strict: true)) {
            return '';
        }

        // Exige que tenha host (ex: rejeita "http://" sozinho)
        if (empty($uri->getHost())) {
            return '';
        }
    } catch (\Throwable) {
        return '';
    }

    return $validated;
}

// Testes
$urls = [
    'https://php.net',              // ✅
    'https://sub.example.com/path?q=1', // ✅
    'php.net',                      // ✅ — adiciona https://
    'javascript:alert(1)',          // ❌ — protocolo proibido
    'ftp://files.example.com',      // ❌ — protocolo não permitido
    'nao-e-url',                    // ❌
];

foreach ($urls as $url) {
    $result = validateUrl($url);
    $valid  = $result !== '' ? '✅' : '❌';
    echo "{$valid} '{$url}' → '{$result}'";
}
```

---

## 41. Formulário Completo — Exemplo Final

Este capítulo reúne todos os conceitos anteriores em um único arquivo PHP autocontido:
validação, persistência de valores, mensagens de erro inline e proteção CSRF.

```php
<?php

declare(strict_types=1);

// ── Sessão segura ───────────────────────────────────────────────────────────
ini_set('session.cookie_httponly', '1');
ini_set('session.cookie_secure',   '1');
ini_set('session.cookie_samesite', 'Strict');
ini_set('session.use_strict_mode', '1');
session_start();

// Token CSRF
if (empty($_SESSION['csrf_token'])) {
    $_SESSION['csrf_token'] = bin2hex(random_bytes(32));
}

// ── Helpers ─────────────────────────────────────────────────────────────────

/** Escapa valor para exibição segura em HTML. */
function e(string $value): string
{
    return htmlspecialchars($value, ENT_QUOTES | ENT_HTML5, 'UTF-8');
}

/** Sanitiza input: trim + stripslashes + escape HTML. */
function sanitize(string $input): string
{
    return $input |> trim(...) |> stripslashes(...) |> e(...);
}

// ── Estado inicial ──────────────────────────────────────────────────────────
$errors = ['name' => '', 'email' => '', 'website' => '', 'gender' => '', 'csrf' => ''];
$values = ['name' => '', 'email' => '', 'website' => '', 'comment' => '', 'gender' => ''];
$success = false;

// ── Processamento POST ──────────────────────────────────────────────────────
if ($_SERVER['REQUEST_METHOD'] === 'POST') {

    // Validação CSRF — sempre primeiro
    $submittedToken = $_POST['csrf_token'] ?? '';

    if (!hash_equals($_SESSION['csrf_token'], $submittedToken)) {
        $errors['csrf'] = 'Requisição inválida. Recarregue a página e tente novamente.';
    } else {
        // Regenera token após uso
        $_SESSION['csrf_token'] = bin2hex(random_bytes(32));

        // Nome (obrigatório)
        $rawName = $_POST['name'] ?? '';

        if (empty(trim($rawName))) {
            $errors['name'] = 'O nome é obrigatório.';
        } else {
            $values['name'] = sanitize($rawName);

            if (!preg_match('/^[\p{L}\p{M}\s\'\-]{2,100}$/u', trim($rawName))) {
                $errors['name'] = 'Use apenas letras e espaços (2–100 caracteres).';
            }
        }

        // E-mail (obrigatório)
        $rawEmail = $_POST['email'] ?? '';

        if (empty(trim($rawEmail))) {
            $errors['email'] = 'O e-mail é obrigatório.';
        } else {
            $validEmail = filter_var(trim($rawEmail), FILTER_VALIDATE_EMAIL);

            if ($validEmail === false) {
                $errors['email'] = 'Informe um e-mail válido.';
            } else {
                $values['email'] = $validEmail;
            }
        }

        // Website (opcional)
        $rawWebsite = $_POST['website'] ?? '';

        if (!empty(trim($rawWebsite))) {
            $validUrl = filter_var(trim($rawWebsite), FILTER_VALIDATE_URL);

            if ($validUrl === false) {
                $errors['website'] = 'Informe uma URL válida (ex: https://example.com).';
            } else {
                $values['website'] = $validUrl;
            }
        }

        // Comentário (opcional)
        $values['comment'] = sanitize($_POST['comment'] ?? '');

        // Gênero (obrigatório, whitelist)
        $allowedGenders = ['female', 'male', 'other', 'prefer_not'];
        $rawGender      = $_POST['gender'] ?? '';

        if (empty($rawGender) || !in_array($rawGender, $allowedGenders, strict: true)) {
            $errors['gender'] = 'Selecione uma opção de gênero.';
        } else {
            $values['gender'] = $rawGender;
        }

        // Sucesso
        if (array_filter($errors, fn(string $e): bool => $e !== '') === []) {
            $success = true;
            // Em produção: redirecione após sucesso (Post/Redirect/Get pattern)
            // header('Location: /obrigado.php');
            // exit;
        }
    }
}
?>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Formulário de Cadastro</title>
    <style>
        .error  { color: #c0392b; font-size: 0.875em; display: block; margin-top: 2px; }
        .success { color: #27ae60; font-weight: bold; }
        label   { display: block; margin-top: 12px; font-weight: bold; }
        input, textarea, select { margin-top: 4px; }
        fieldset { margin-top: 12px; border: 1px solid #ccc; padding: 8px 12px; }
    </style>
</head>
<body>

<?php if ($success): ?>
    <p class="success">
        ✅ Obrigado, <?= e($values['name']) ?>! Seu cadastro foi realizado com sucesso.
    </p>
<?php else: ?>

    <?php if ($errors['csrf'] !== ''): ?>
        <p class="error"><?= e($errors['csrf']) ?></p>
    <?php endif; ?>

    <form method="POST" action="<?= e($_SERVER['PHP_SELF']) ?>" novalidate>
        <!-- Token CSRF oculto -->
        <input type="hidden" name="csrf_token"
               value="<?= e($_SESSION['csrf_token']) ?>">

        <!-- Nome -->
        <label for="name">Nome <span aria-hidden="true">*</span></label>
        <input type="text" id="name" name="name" required maxlength="100"
               value="<?= e($values['name']) ?>"
               aria-describedby="nameErr">
        <?php if ($errors['name'] !== ''): ?>
            <span id="nameErr" class="error" role="alert"><?= e($errors['name']) ?></span>
        <?php endif; ?>

        <!-- E-mail -->
        <label for="email">E-mail <span aria-hidden="true">*</span></label>
        <input type="email" id="email" name="email" required
               value="<?= e($values['email']) ?>"
               aria-describedby="emailErr">
        <?php if ($errors['email'] !== ''): ?>
            <span id="emailErr" class="error" role="alert"><?= e($errors['email']) ?></span>
        <?php endif; ?>

        <!-- Website -->
        <label for="website">Website <em>(opcional)</em></label>
        <input type="url" id="website" name="website" placeholder="https://"
               value="<?= e($values['website']) ?>"
               aria-describedby="websiteErr">
        <?php if ($errors['website'] !== ''): ?>
            <span id="websiteErr" class="error" role="alert"><?= e($errors['website']) ?></span>
        <?php endif; ?>

        <!-- Comentário -->
        <label for="comment">Comentário <em>(opcional)</em></label>
        <textarea id="comment" name="comment" rows="5" cols="40"
        ><?= e($values['comment']) ?></textarea>

        <!-- Gênero -->
        <fieldset aria-describedby="genderErr">
            <legend>Gênero <span aria-hidden="true">*</span></legend>

            <?php
            $genderOptions = [
                'female'     => 'Feminino',
                'male'       => 'Masculino',
                'other'      => 'Outro',
                'prefer_not' => 'Prefiro não informar',
            ];

            foreach ($genderOptions as $val => $label):
            ?>
                <label style="font-weight: normal; display: inline; margin-right: 12px;">
                    <input type="radio" name="gender" value="<?= e($val) ?>"
                           <?= $values['gender'] === $val ? 'checked' : '' ?>>
                    <?= e($label) ?>
                </label>
            <?php endforeach; ?>

            <?php if ($errors['gender'] !== ''): ?>
                <span id="genderErr" class="error" role="alert"><?= e($errors['gender']) ?></span>
            <?php endif; ?>
        </fieldset>

        <p style="margin-top: 16px;">
            <button type="submit">Enviar</button>
        </p>
    </form>

<?php endif; ?>

</body>
</html>
```

---

## 42. Data e Hora

PHP oferece funções robustas para trabalhar com datas, horas e fusos horários.
A abordagem moderna usa a classe `DateTimeImmutable` — imutável e mais segura que `date()` isolado.

### Fuso horário — sempre configure primeiro

```php
<?php

declare(strict_types=1);

// ✅ Configure o fuso antes de qualquer operação de data/hora
// Lista completa: https://www.php.net/manual/en/timezones.america.php
date_default_timezone_set('America/Sao_Paulo');

echo date_default_timezone_get(); // America/Sao_Paulo
```

### date() — formata data/hora atual

```php
<?php

declare(strict_types=1);

date_default_timezone_set('America/Sao_Paulo');

// Formatos de data
echo date('d/m/Y');          // 08/04/2025  (BR padrão)
echo date('Y-m-d');          // 2025-04-08  (ISO 8601 — use em bancos/APIs)
echo date('Y/m/d');          // 2025/04/08
echo date('l, F j, Y');      // Tuesday, April 8, 2025

// Formatos de hora
echo date('H:i:s');          // 14:30:45  (24h)
echo date('h:i:s a');        // 02:30:45 pm (12h)

// Data e hora completos
echo date('Y-m-d H:i:s');   // 2025-04-08 14:30:45

// Ano automático para copyright
echo '&copy; 2020–' . date('Y'); // © 2020–2025
```

| Caractere | Descrição | Exemplo |
|-----------|-----------|---------|
| `d` | Dia com zeros | `01`–`31` |
| `j` | Dia sem zeros | `1`–`31` |
| `m` | Mês com zeros | `01`–`12` |
| `n` | Mês sem zeros | `1`–`12` |
| `Y` | Ano com 4 dígitos | `2025` |
| `y` | Ano com 2 dígitos | `25` |
| `l` | Nome do dia (inglês) | `Tuesday` |
| `D` | Nome abreviado | `Tue` |
| `F` | Nome do mês (inglês) | `April` |
| `M` | Mês abreviado | `Apr` |
| `H` | Hora 24h c/ zeros | `00`–`23` |
| `h` | Hora 12h c/ zeros | `01`–`12` |
| `i` | Minutos | `00`–`59` |
| `s` | Segundos | `00`–`59` |
| `a` | am / pm | `am`, `pm` |
| `U` | Unix timestamp | `1744128645` |

### DateTimeImmutable — abordagem moderna recomendada

```php
<?php

declare(strict_types=1);

// ✅ DateTimeImmutable: imutável, OOP, mais seguro que date() + mktime()
$timezone = new \DateTimeZone('America/Sao_Paulo');
$now      = new \DateTimeImmutable('now', $timezone);

echo $now->format('d/m/Y H:i:s'); // 08/04/2025 14:30:45

// Aritmética de datas — retorna NOVO objeto (imutabilidade)
$tomorrow   = $now->modify('+1 day');
$nextWeek   = $now->modify('+7 days');
$lastMonth  = $now->modify('-1 month');
$nextYear   = $now->add(new \DateInterval('P1Y'));   // P = Period, 1Y = 1 ano

echo $tomorrow->format('d/m/Y');  // 09/04/2025
echo $nextWeek->format('d/m/Y');  // 15/04/2025

// Criar data específica
$birthdate  = new \DateTimeImmutable('1990-06-15', $timezone);
$today      = new \DateTimeImmutable('today', $timezone);
$age        = $today->diff($birthdate); // DateInterval

echo "Idade: {$age->y} anos"; // Ex: 34 anos

// Comparação de datas
var_dump($tomorrow > $now);  // bool(true)
var_dump($lastMonth < $now); // bool(true)

// Formatando para banco de dados (sempre ISO 8601)
$dbFormat = $now->format('Y-m-d H:i:s'); // 2025-04-08 14:30:45

// Criando a partir de formato específico
$parsed = \DateTimeImmutable::createFromFormat('d/m/Y', '25/12/2025', $timezone);

if ($parsed === false) {
    throw new \RuntimeException('Data inválida ou formato incorreto.');
}

echo $parsed->format('Y-m-d'); // 2025-12-25
```

### time() e mktime() — Unix timestamp

```php
<?php

declare(strict_types=1);

// time() — timestamp atual em segundos desde 01/01/1970 00:00:00 UTC
$timestamp = time();
echo $timestamp;                    // Ex: 1744128645
echo date('Y-m-d H:i:s', $timestamp); // Formata o timestamp

// mktime() — cria timestamp para data/hora específica
// mktime(hora, minuto, segundo, mês, dia, ano)
$christmas2025 = mktime(0, 0, 0, 12, 25, 2025);
echo date('l, d/m/Y', $christmas2025); // Thursday, 25/12/2025

// Calculando diferença em dias via timestamp
$start = mktime(0, 0, 0, 1, 1, 2025);
$end   = mktime(0, 0, 0, 12, 31, 2025);
$daysDiff = (int) round(($end - $start) / 86400); // 86400 = segundos por dia
echo "2025 tem {$daysDiff} dias"; // 364
```

### strtotime() — converte texto em timestamp

```php
<?php

declare(strict_types=1);

date_default_timezone_set('America/Sao_Paulo');

// strtotime() interpreta strings em inglês
$timestamps = [
    strtotime('now'),
    strtotime('+5 days'),
    strtotime('+2 weeks'),
    strtotime('+1 month'),
    strtotime('-1 year'),
    strtotime('next monday'),
    strtotime('last sunday'),
    strtotime('first day of next month'),
    strtotime('last day of this month'),
];

foreach ($timestamps as $ts) {
    echo date('d/m/Y H:i:s', $ts);
}

// ⚠️ strtotime() pode ser ambíguo com algumas strings — prefira DateTimeImmutable
// ✅ PREFIRA:
$nextMonday = new \DateTimeImmutable('next monday', new \DateTimeZone('America/Sao_Paulo'));
echo $nextMonday->format('d/m/Y');
```

### Exemplo prático: próximos 6 sábados

```php
<?php

declare(strict_types=1);

date_default_timezone_set('America/Sao_Paulo');

$timezone = new \DateTimeZone('America/Sao_Paulo');
$current  = new \DateTimeImmutable('next saturday', $timezone);

// ✅ Usando DateTimeImmutable com loop — sem side effects
for ($i = 0; $i < 6; $i++) {
    echo $current->format('d/m/Y (l)');
    $current = $current->modify('+1 week');
}
```

---

## 43. Include e Require

PHP permite incluir o conteúdo de um arquivo dentro de outro com `include` e `require`.
Isso é a base da reutilização de código — cabeçalhos, rodapés, configurações, componentes.

### Diferença fundamental

| | `include` | `require` |
|-|-----------|-----------|
| Arquivo não encontrado | `E_WARNING` (script continua) | `E_ERROR` fatal (script para) |
| Uso recomendado | Componentes opcionais (widgets, banners) | Configuração, conexão DB, classes críticas |

### require — para dependências críticas

```php
<?php

declare(strict_types=1);

// ✅ Use __DIR__ para paths absolutos — nunca dependa do diretório de trabalho atual
// __DIR__ = diretório do arquivo atual, independente de onde o script é chamado

require __DIR__ . '/config/database.php';      // Fatal se não encontrar
require __DIR__ . '/src/autoloader.php';       // Fatal se não encontrar
require __DIR__ . '/helpers/functions.php';    // Fatal se não encontrar
```

### include — para componentes opcionais

```php
<?php

declare(strict_types=1);

// Templates — aviso se não encontrar, mas não para o script
include __DIR__ . '/templates/header.php';
include __DIR__ . '/templates/nav.php';

// Conteúdo principal
echo '<main><p>Conteúdo da página.</p></main>';

include __DIR__ . '/templates/footer.php';
```

### require_once e include_once

```php
<?php

declare(strict_types=1);

// _once garante que o arquivo seja incluído NO MÁXIMO UMA VEZ
// Evita redefinição de funções, classes ou constantes

require_once __DIR__ . '/src/Database.php';    // ✅ Inclui apenas se ainda não incluído
require_once __DIR__ . '/src/UserRepository.php';

// include_once para componentes que não devem ser duplicados
include_once __DIR__ . '/templates/header.php';
```

### Passagem de variáveis via include

```php
<?php

// arquivo: config/settings.php
declare(strict_types=1);

$appName    = 'Meu Sistema PHP';
$appVersion = '1.0.0';
$debug      = false;
```

```php
<?php

// arquivo: index.php
declare(strict_types=1);

require __DIR__ . '/config/settings.php';

// Variáveis de settings.php ficam disponíveis aqui
echo $appName;    // Meu Sistema PHP
echo $appVersion; // 1.0.0
```

### Boas práticas de organização de arquivos

```
📂 projeto/
├── 📄 index.php                ← ponto de entrada
├── 📂 config/
│   ├── 📄 database.php         ← credenciais DB (nunca no Git!)
│   └── 📄 settings.php         ← configurações globais
├── 📂 src/
│   ├── 📄 autoloader.php       ← PSR-4 autoloader
│   └── 📂 Service/
│       └── 📄 UserService.php
├── 📂 templates/
│   ├── 📄 header.php
│   ├── 📄 footer.php
│   └── 📄 nav.php
└── 📂 public/                  ← único diretório acessível pelo servidor web
    └── 📄 index.php
```

```php
<?php

// templates/header.php
declare(strict_types=1);

// $pageTitle deve ser definida antes do include
$pageTitle ??= 'Página'; // Valor padrão com null coalescing assignment
?>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title><?= htmlspecialchars($pageTitle, ENT_QUOTES | ENT_HTML5, 'UTF-8') ?></title>
</head>
<body>
```

```php
<?php

// index.php
declare(strict_types=1);

$pageTitle = 'Home — Meu Sistema';

require __DIR__ . '/templates/header.php';

echo '<h1>Bem-vindo!</h1>';

require __DIR__ . '/templates/footer.php';
```

---

## 44. Manipulação de Arquivos — Leitura

PHP possui um conjunto completo de funções para ler arquivos. A escolha da função
depende da quantidade de dados e se você precisa de controle linha a linha.

### Funções de leitura — escolha rápida

| Função | Quando usar |
|--------|------------|
| `file_get_contents()` | ✅ Lê o arquivo inteiro de uma vez — mais simples e rápido |
| `file()` | Lê arquivo em array de linhas |
| `fopen()` + `fgets()` | Arquivos grandes — leitura linha por linha com controle |
| `fopen()` + `fread()` | Leitura de N bytes com precisão |
| `readfile()` | Lê e envia diretamente para o output (browser) |

### file_get_contents() — forma mais simples e recomendada

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/dicionario.txt';

// ✅ Verificar existência antes de ler
if (!file_exists($filePath)) {
    throw new \RuntimeException("Arquivo não encontrado: {$filePath}");
}

if (!is_readable($filePath)) {
    throw new \RuntimeException("Arquivo sem permissão de leitura: {$filePath}");
}

// Lê o arquivo inteiro como string
$content = file_get_contents($filePath);

if ($content === false) {
    throw new \RuntimeException("Falha ao ler o arquivo: {$filePath}");
}

// ✅ Sempre escape ao exibir conteúdo de arquivo no HTML
echo nl2br(htmlspecialchars($content, ENT_QUOTES | ENT_HTML5, 'UTF-8'));
```

### file() — lê em array de linhas

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/nomes.txt';

// FILE_IGNORE_NEW_LINES = remove \n do final de cada linha
// FILE_SKIP_EMPTY_LINES = ignora linhas vazias
$lines = file($filePath, FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);

if ($lines === false) {
    throw new \RuntimeException("Falha ao ler: {$filePath}");
}

foreach ($lines as $lineNumber => $line) {
    $lineNum = $lineNumber + 1;
    $escaped = htmlspecialchars($line, ENT_QUOTES | ENT_HTML5, 'UTF-8');
    echo "Linha {$lineNum}: {$escaped}";
}

echo 'Total de linhas: ' . count($lines);
```

### fopen() — controle granular para arquivos grandes

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/dicionario.txt';

// fopen() retorna resource ou false
$fileHandle = fopen($filePath, 'r');

if ($fileHandle === false) {
    throw new \RuntimeException("Não foi possível abrir: {$filePath}");
}

try {
    // Lê linha por linha até o final do arquivo (EOF)
    while (!feof($fileHandle)) {
        $line = fgets($fileHandle); // Lê uma linha

        if ($line === false) {
            break; // Fim de arquivo ou erro
        }

        // Processa a linha — escape antes de exibir
        echo htmlspecialchars(trim($line), ENT_QUOTES | ENT_HTML5, 'UTF-8') . '<br>';
    }
} finally {
    // ✅ Sempre feche o arquivo — use finally para garantir o fechamento mesmo com exceção
    fclose($fileHandle);
}
```

### fread() — lê N bytes específicos

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/dicionario.txt';
$fileHandle = fopen($filePath, 'r');

if ($fileHandle === false) {
    throw new \RuntimeException("Não foi possível abrir: {$filePath}");
}

try {
    // Lê o arquivo inteiro de uma vez com fread()
    $fileSize = filesize($filePath);

    if ($fileSize === false || $fileSize === 0) {
        echo 'Arquivo vazio.';
        return;
    }

    $content = fread($fileHandle, $fileSize);

    // Lê apenas os primeiros 100 bytes
    rewind($fileHandle);
    $preview = fread($fileHandle, 100);

    echo htmlspecialchars($content, ENT_QUOTES | ENT_HTML5, 'UTF-8');
} finally {
    fclose($fileHandle);
}
```

### Leitura de CSV — exemplo prático

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/produtos.csv';
$products = [];

$fileHandle = fopen($filePath, 'r');

if ($fileHandle === false) {
    throw new \RuntimeException("CSV não encontrado: {$filePath}");
}

try {
    // Lê o cabeçalho (primeira linha)
    $headers = fgetcsv($fileHandle, separator: ',');

    if ($headers === false) {
        throw new \RuntimeException('CSV vazio ou malformado.');
    }

    // Lê os dados restantes
    while (($row = fgetcsv($fileHandle, separator: ',')) !== false) {
        // Combina cabeçalhos com valores — cria array associativo
        $products[] = array_combine($headers, $row);
    }
} finally {
    fclose($fileHandle);
}

// Exibe os produtos
foreach ($products as $product) {
    $name  = htmlspecialchars($product['name']  ?? '', ENT_QUOTES | ENT_HTML5, 'UTF-8');
    $price = htmlspecialchars($product['price'] ?? '', ENT_QUOTES | ENT_HTML5, 'UTF-8');
    echo "{$name}: R$ {$price}";
}
```

### Tabela de modos de abertura de arquivo

| Modo | Descrição | Ponteiro | Cria arquivo? | Apaga conteúdo? |
|------|-----------|----------|---------------|-----------------|
| `r` | Somente leitura | Início | ❌ | ❌ |
| `r+` | Leitura e escrita | Início | ❌ | ❌ |
| `w` | Somente escrita | Início | ✅ | ✅ |
| `w+` | Leitura e escrita | Início | ✅ | ✅ |
| `a` | Somente escrita (append) | Final | ✅ | ❌ |
| `a+` | Leitura e escrita (append) | Final | ✅ | ❌ |
| `x` | Escrita (novo arquivo) | Início | ✅ (só novo) | — |
| `x+` | Leitura/escrita (novo arquivo) | Início | ✅ (só novo) | — |

---

## 45. Manipulação de Arquivos — Escrita e Criação

### file_put_contents() — forma mais simples e recomendada

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/log.txt';

// ✅ Escreve conteúdo completo (sobrescreve se existir)
$bytesWritten = file_put_contents($filePath, "Linha 1\nLinha 2\nLinha 3\n");

if ($bytesWritten === false) {
    throw new \RuntimeException("Falha ao escrever em: {$filePath}");
}

// ✅ Append — acrescenta ao final sem apagar o conteúdo existente
$entry = date('Y-m-d H:i:s') . " — Evento registrado\n";
file_put_contents($filePath, $entry, FILE_APPEND | LOCK_EX);
// LOCK_EX = obtém lock exclusivo — previne escrita concorrente
```

### fopen() + fwrite() — controle granular

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/usuarios.txt';

// 'w' sobrescreve; 'a' acrescenta; 'x' cria novo (falha se existir)
$fileHandle = fopen($filePath, 'w');

if ($fileHandle === false) {
    throw new \RuntimeException("Não foi possível criar: {$filePath}");
}

try {
    $users = [
        ['name' => 'Ana Silva',    'email' => 'ana@example.com'],
        ['name' => 'Carlos Lima',  'email' => 'carlos@example.com'],
        ['name' => 'Maria Santos', 'email' => 'maria@example.com'],
    ];

    foreach ($users as $user) {
        // Formata cada linha — \n é o separador de linha padrão em sistemas Unix
        $line = "{$user['name']};{$user['email']}\n";
        $result = fwrite($fileHandle, $line);

        if ($result === false) {
            throw new \RuntimeException('Falha ao escrever linha no arquivo.');
        }
    }
} finally {
    fclose($fileHandle); // ✅ Sempre no finally
}
```

### Append — acrescenta sem apagar

```php
<?php

declare(strict_types=1);

$logPath = __DIR__ . '/logs/app.log';

/**
 * Registra uma entrada de log com timestamp.
 *
 * @param string $level   Nível: INFO, WARNING, ERROR
 * @param string $message Mensagem do log
 */
function writeLog(string $level, string $message): void
{
    $logPath = __DIR__ . '/logs/app.log';

    // Garante que o diretório existe
    $dir = dirname($logPath);

    if (!is_dir($dir)) {
        mkdir($dir, 0755, recursive: true);
    }

    $timestamp = (new \DateTimeImmutable())->format('Y-m-d H:i:s');
    $entry     = "[{$timestamp}] [{$level}] {$message}" . PHP_EOL;

    // FILE_APPEND + LOCK_EX — thread-safe
    $result = file_put_contents($logPath, $entry, FILE_APPEND | LOCK_EX);

    if ($result === false) {
        // Não jogue exception em logger — pode causar loop
        error_log("CRÍTICO: Falha ao escrever log em {$logPath}");
    }
}

writeLog('INFO',    'Aplicação iniciada.');
writeLog('WARNING', 'Tentativa de login com usuário inválido.');
writeLog('ERROR',   'Falha ao conectar ao banco de dados.');
```

### Deletando arquivos com segurança

```php
<?php

declare(strict_types=1);

/**
 * Remove um arquivo de forma segura com verificações de segurança.
 *
 * @throws \RuntimeException Se o arquivo não puder ser removido
 * @throws \InvalidArgumentException Se o caminho for inválido ou estiver fora do diretório permitido
 */
function deleteFile(string $filePath, string $allowedDir): void
{
    // ✅ Resolve o caminho real — previne path traversal (../../etc/passwd)
    $realPath    = realpath($filePath);
    $realAllowed = realpath($allowedDir);

    if ($realPath === false) {
        throw new \InvalidArgumentException("Arquivo não encontrado: {$filePath}");
    }

    if ($realAllowed === false) {
        throw new \InvalidArgumentException("Diretório permitido inválido: {$allowedDir}");
    }

    // Garante que o arquivo está DENTRO do diretório permitido
    if (!str_starts_with($realPath, $realAllowed . DIRECTORY_SEPARATOR)) {
        throw new \InvalidArgumentException(
            "Acesso negado: '{$realPath}' está fora de '{$realAllowed}'."
        );
    }

    if (!is_file($realPath)) {
        throw new \InvalidArgumentException("Não é um arquivo regular: {$realPath}");
    }

    if (!unlink($realPath)) {
        throw new \RuntimeException("Falha ao deletar: {$realPath}");
    }
}

// Uso seguro
try {
    deleteFile(__DIR__ . '/uploads/arquivo.txt', __DIR__ . '/uploads');
    echo 'Arquivo removido com sucesso.';
} catch (\InvalidArgumentException $e) {
    echo 'Erro de permissão: ' . htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');
} catch (\RuntimeException $e) {
    echo 'Erro ao deletar: ' . htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
```

---

## 46. Upload de Arquivos

Upload de arquivos é uma das operações mais críticas em segurança. Cada etapa de
validação é obrigatória — nunca confie em dados enviados pelo cliente.

### Configuração do php.ini

```ini
; Habilita upload de arquivos (padrão: On)
file_uploads = On

; Tamanho máximo de um único arquivo
upload_max_filesize = 5M

; Tamanho máximo do POST inteiro (deve ser >= upload_max_filesize)
post_max_size = 6M

; Número máximo de arquivos por request
max_file_uploads = 10
```

### Formulário HTML para upload

```html
<!DOCTYPE html>
<html lang="pt-BR">
<body>

<!-- enctype="multipart/form-data" é OBRIGATÓRIO para upload -->
<!-- method="post" é OBRIGATÓRIO — GET não suporta upload -->
<form action="upload.php" method="POST" enctype="multipart/form-data">
    <label for="file">Selecione uma imagem:</label>
    <input type="file" id="file" name="fileToUpload" accept=".jpg,.jpeg,.png,.gif,.webp">
    <button type="submit" name="submit">Enviar</button>
</form>

</body>
</html>
```

### $_FILES — estrutura do array de upload

```php
// $_FILES['fileToUpload'] contém:
[
    'name'     => 'foto.jpg',            // Nome original do arquivo (NÃO confiável)
    'type'     => 'image/jpeg',          // MIME type (NÃO confiável — declarado pelo cliente)
    'tmp_name' => '/tmp/phpAb3cDe',      // Caminho do arquivo temporário no servidor
    'error'    => 0,                     // Código de erro (0 = sem erro)
    'size'     => 204800,                // Tamanho em bytes
]
```

### Script de upload seguro e completo

```php
<?php

declare(strict_types=1);

/**
 * Processa upload de imagem com todas as validações de segurança.
 *
 * @throws \RuntimeException Em caso de falha no upload
 * @throws \InvalidArgumentException Se o arquivo não passar nas validações
 */
final class ImageUploader
{
    // ✅ Whitelist de extensões permitidas — nunca use blacklist!
    private const ALLOWED_EXTENSIONS = ['jpg', 'jpeg', 'png', 'gif', 'webp'];

    // ✅ Whitelist de MIME types reais (verificados com finfo, não pelo cliente)
    private const ALLOWED_MIME_TYPES = [
        'image/jpeg',
        'image/png',
        'image/gif',
        'image/webp',
    ];

    // 5 MB em bytes
    private const MAX_SIZE_BYTES = 5 * 1024 * 1024;

    public function __construct(
        private readonly string $uploadDir,
    ) {
        if (!is_dir($this->uploadDir) || !is_writable($this->uploadDir)) {
            throw new \RuntimeException(
                "Diretório de upload inválido ou sem permissão de escrita: {$this->uploadDir}"
            );
        }
    }

    /**
     * Processa o upload e retorna o caminho final do arquivo.
     *
     * @param array<string, mixed> $fileData Entrada de $_FILES['campo']
     *
     * @return string Caminho absoluto do arquivo salvo
     */
    public function upload(array $fileData): string
    {
        // 1. Verifica código de erro do upload
        $this->checkUploadError((int) $fileData['error']);

        $tmpPath  = (string) $fileData['tmp_name'];
        $origName = (string) $fileData['name'];
        $fileSize = (int)   $fileData['size'];

        // 2. Verifica que é um upload válido (não arquivo local)
        if (!is_uploaded_file($tmpPath)) {
            throw new \InvalidArgumentException('Arquivo inválido — não é um upload HTTP.');
        }

        // 3. Valida tamanho
        if ($fileSize > self::MAX_SIZE_BYTES) {
            $maxMb = self::MAX_SIZE_BYTES / 1024 / 1024;
            throw new \InvalidArgumentException("Arquivo muito grande. Máximo: {$maxMb} MB.");
        }

        // 4. Valida extensão via whitelist (a partir do nome original)
        $extension = strtolower(pathinfo($origName, PATHINFO_EXTENSION));

        if (!in_array($extension, self::ALLOWED_EXTENSIONS, strict: true)) {
            $allowed = implode(', ', self::ALLOWED_EXTENSIONS);
            throw new \InvalidArgumentException(
                "Extensão '{$extension}' não permitida. Use: {$allowed}."
            );
        }

        // 5. ✅ Valida MIME type REAL com finfo — ignora o declarado pelo cliente
        $finfo    = new \finfo(FILEINFO_MIME_TYPE);
        $mimeType = $finfo->file($tmpPath);

        if (!in_array($mimeType, self::ALLOWED_MIME_TYPES, strict: true)) {
            throw new \InvalidArgumentException(
                "Tipo de arquivo não permitido: {$mimeType}."
            );
        }

        // 6. ✅ Valida que é realmente uma imagem (getimagesize detecta arquivos falsos)
        $imageInfo = getimagesize($tmpPath);

        if ($imageInfo === false) {
            throw new \InvalidArgumentException('O arquivo não é uma imagem válida.');
        }

        // 7. ✅ Gera nome único e seguro — NUNCA use o nome original do usuário
        $safeFilename = sprintf(
            '%s_%s.%s',
            date('Ymd_His'),
            bin2hex(random_bytes(8)),  // 16 chars hex aleatórios
            $extension
        );

        $destination = $this->uploadDir . DIRECTORY_SEPARATOR . $safeFilename;

        // 8. Verifica se o destino está dentro do uploadDir (path traversal prevention)
        $realUploadDir = realpath($this->uploadDir);
        $realDest      = realpath(dirname($destination)) . DIRECTORY_SEPARATOR . $safeFilename;

        if (!str_starts_with($realDest, $realUploadDir . DIRECTORY_SEPARATOR)) {
            throw new \InvalidArgumentException('Destino inválido.');
        }

        // 9. Move da pasta temporária para o destino final
        if (!move_uploaded_file($tmpPath, $destination)) {
            throw new \RuntimeException('Falha ao mover arquivo. Verifique permissões.');
        }

        return $destination;
    }

    /** @throws \RuntimeException */
    private function checkUploadError(int $errorCode): void
    {
        $messages = [
            UPLOAD_ERR_INI_SIZE   => 'Arquivo excede o limite do php.ini (upload_max_filesize).',
            UPLOAD_ERR_FORM_SIZE  => 'Arquivo excede o limite definido no formulário HTML.',
            UPLOAD_ERR_PARTIAL    => 'Upload incompleto. Tente novamente.',
            UPLOAD_ERR_NO_FILE    => 'Nenhum arquivo foi enviado.',
            UPLOAD_ERR_NO_TMP_DIR => 'Diretório temporário não encontrado no servidor.',
            UPLOAD_ERR_CANT_WRITE => 'Falha ao gravar no disco. Contate o administrador.',
            UPLOAD_ERR_EXTENSION  => 'Upload bloqueado por extensão PHP.',
        ];

        if ($errorCode !== UPLOAD_ERR_OK) {
            $message = $messages[$errorCode] ?? "Erro desconhecido no upload (código: {$errorCode}).";
            throw new \RuntimeException($message);
        }
    }
}

// ── Uso ──────────────────────────────────────────────────────────────────────
if ($_SERVER['REQUEST_METHOD'] === 'POST' && isset($_FILES['fileToUpload'])) {
    try {
        $uploader = new ImageUploader(uploadDir: __DIR__ . '/uploads');
        $savedPath = $uploader->upload($_FILES['fileToUpload']);

        // ✅ Exibe apenas o nome do arquivo — nunca o caminho absoluto
        $filename = basename($savedPath);
        echo 'Upload realizado: ' . htmlspecialchars($filename, ENT_QUOTES | ENT_HTML5, 'UTF-8');

    } catch (\InvalidArgumentException $e) {
        // Erro de validação — exibe ao usuário
        http_response_code(422);
        echo 'Arquivo inválido: ' . htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');

    } catch (\RuntimeException $e) {
        // Erro do servidor — log interno, mensagem genérica ao usuário
        error_log('Upload error: ' . $e->getMessage());
        http_response_code(500);
        echo 'Erro interno ao processar o upload. Tente novamente.';
    }
}
```

### Checklist de segurança para upload

| Verificação | Por que é obrigatória |
|-------------|----------------------|
| ✅ `is_uploaded_file()` | Garante que veio de um upload HTTP real |
| ✅ Validar `$_FILES['error']` | Detecta uploads incompletos ou bloqueados |
| ✅ Validar tamanho (`size`) | Previne DoS por arquivo gigante |
| ✅ Whitelist de extensões | Bloqueia `.php`, `.exe`, `.sh`, etc. |
| ✅ Validar MIME real com `finfo` | `$_FILES['type']` é declarado pelo cliente — não confiável |
| ✅ `getimagesize()` para imagens | Detecta arquivos falsos com extensão .jpg |
| ✅ Gerar nome com `random_bytes()` | Evita sobrescrita, adivinhação e path traversal |
| ✅ `move_uploaded_file()` | Única função segura para mover uploads |
| ✅ Upload fora do `public/` | Arquivos fora da raiz web não são acessados diretamente |
| ❌ Nunca use o nome original | Pode conter `../`, null bytes ou extensões executáveis |
| ❌ Nunca confie em `$_FILES['type']` | Completamente controlado pelo cliente |

---

## 47. Cookies

Um cookie é um pequeno arquivo de texto que o servidor armazena no navegador do usuário.
A cada requisição HTTP subsequente, o navegador envia o cookie de volta ao servidor.
Cookies são usados para persistir informações entre requisições sem depender de sessão no servidor.

### Casos de uso comuns

- Preferências do usuário (tema, idioma, timezone)
- Token "lembrar-me" de login
- Conteúdo do carrinho de compras
- Rastreamento de atividade (analytics)

> 🔒 **Regra de ouro:** Nunca armazene dados sensíveis (senhas, dados pessoais, tokens de autenticação) em cookies sem criptografia. Cookies são visíveis ao usuário e podem ser manipulados.

### setcookie() — criando um cookie seguro

`setcookie()` **deve ser chamada antes de qualquer saída HTML** — ela envia um header HTTP.

```php
<?php

declare(strict_types=1);

// ✅ Parâmetros nomeados (PHP 8.0+) — muito mais legível que posicionais
setcookie(
    name:     'theme',
    value:    'dark',
    expires:  time() + (86400 * 30), // 30 dias (86400 = segundos por dia)
    path:     '/',                   // Disponível em todo o site
    domain:   '',                    // Domínio atual
    secure:   true,                  // ✅ Apenas via HTTPS
    httponly: true,                  // ✅ Inacessível via JavaScript (previne XSS)
);

// ✅ PHP 8.5: argumento 'partitioned' (CHIPS — Cookies Having Independent Partitioned State)
// Útil para contextos de terceiros em ambientes com restrições de privacidade
setcookie(
    name:        'analytics_id',
    value:       bin2hex(random_bytes(16)),
    expires:     time() + (86400 * 365),
    path:        '/',
    secure:      true,
    httponly:    true,
    partitioned: true, // 🆕 PHP 8.5
);
```

### Lendo cookies com $_COOKIE

```php
<?php

declare(strict_types=1);

// ✅ Sempre use ?? para fallback — cookie pode não existir
$theme = $_COOKIE['theme'] ?? 'light';

// ✅ Valide contra uma whitelist antes de usar qualquer valor de cookie
$allowedThemes = ['light', 'dark', 'high-contrast'];

if (!in_array($theme, $allowedThemes, strict: true)) {
    $theme = 'light'; // Valor padrão seguro
}

echo 'Tema atual: ' . htmlspecialchars($theme, ENT_QUOTES | ENT_HTML5, 'UTF-8');

// Verificando existência
if (isset($_COOKIE['username'])) {
    // ✅ Sempre escape o valor do cookie antes de exibir
    $username = htmlspecialchars($_COOKIE['username'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
    echo "Bem-vindo de volta, {$username}!";
} else {
    echo 'Cookie não encontrado.';
}
```

### Modificando e deletando cookies

```php
<?php

declare(strict_types=1);

// Modificar = recriar com o mesmo nome e novo valor
setcookie(
    name:     'theme',
    value:    'high-contrast', // Novo valor
    expires:  time() + (86400 * 30),
    path:     '/',
    secure:   true,
    httponly: true,
);

// ✅ Deletar = recriar com expires no passado e value vazio
setcookie(
    name:    'theme',
    value:   '',
    expires: time() - 3600, // 1 hora no passado
    path:    '/',
    secure:  true,
    httponly: true,
);

// Também remova do array $_COOKIE na requisição atual
unset($_COOKIE['theme']);
```

### Verificando se cookies estão habilitados

```php
<?php

declare(strict_types=1);

// Técnica: define um cookie de teste, redireciona, verifica se chegou
// Abordagem simples (sem redirecionamento):
setcookie('_cookietest', '1', time() + 60, '/', '', true, true);

// Na próxima requisição:
$cookiesEnabled = isset($_COOKIE['_cookietest']);

if ($cookiesEnabled) {
    echo 'Cookies estão habilitados.';
    // Remove o cookie de teste
    setcookie('_cookietest', '', time() - 3600, '/');
} else {
    echo 'Cookies estão desabilitados neste navegador.';
}
```

### Comparação: cookies vs sessões

| | Cookie | Sessão |
|--|--------|--------|
| Onde fica | Navegador do usuário | Servidor |
| Visível ao usuário | ✅ Sim (pode ser lido/alterado) | ❌ Não |
| Segurança | Menor — dados expostos | Maior — apenas ID no cliente |
| Expiração | Configurável (pode ser permanente) | Fecha com o browser (padrão) |
| Tamanho máximo | ~4 KB por cookie | Praticamente ilimitado |
| Tráfego HTTP | Enviado em toda requisição | Apenas o ID (PHPSESSID) |
| Uso ideal | Preferências, "lembrar-me" | Login, carrinho, dados sensíveis |

---

## 48. Sessões (Sessions)

Sessões armazenam dados do usuário **no servidor**, associados a um ID único enviado
ao cliente via cookie (`PHPSESSID`). São mais seguras que cookies para dados sensíveis
como estado de autenticação.

### Como funcionam

1. Cliente faz a primeira requisição → servidor cria um ID de sessão único
2. ID é enviado ao browser via cookie `PHPSESSID`
3. Dados da sessão ficam armazenados no servidor (arquivo ou banco)
4. Nas próximas requisições, o browser envia o `PHPSESSID`
5. Servidor carrega os dados correspondentes em `$_SESSION`

### Configuração segura obrigatória

```php
<?php

declare(strict_types=1);

// ✅ Configure ANTES de session_start() — sempre
ini_set('session.cookie_httponly',  '1');   // Inacessível via JavaScript
ini_set('session.cookie_secure',    '1');   // Apenas HTTPS
ini_set('session.cookie_samesite',  'Strict'); // Previne CSRF via cookie
ini_set('session.use_strict_mode',  '1');   // Rejeita IDs de sessão não gerados pelo servidor
ini_set('session.gc_maxlifetime',   '1800'); // 30 min de inatividade

session_start();
```

### Iniciando e armazenando dados de sessão

```php
<?php

declare(strict_types=1);

ini_set('session.cookie_httponly', '1');
ini_set('session.cookie_secure',   '1');
ini_set('session.cookie_samesite', 'Strict');
ini_set('session.use_strict_mode', '1');
session_start();

// Armazenando dados na sessão
$_SESSION['userId']    = 42;
$_SESSION['userName']  = 'Ana Silva';
$_SESSION['userRole']  = 'admin';
$_SESSION['loginTime'] = time();

echo 'Sessão iniciada com sucesso.';
```

### Recuperando dados de sessão em outra página

```php
<?php

declare(strict_types=1);

ini_set('session.cookie_httponly', '1');
ini_set('session.cookie_secure',   '1');
ini_set('session.cookie_samesite', 'Strict');
ini_set('session.use_strict_mode', '1');
session_start();

// ✅ Sempre verifique antes de usar
if (isset($_SESSION['userId'], $_SESSION['userName'])) {
    $userId   = (int)    $_SESSION['userId'];
    $userName = (string) $_SESSION['userName'];
    $userRole = (string) ($_SESSION['userRole'] ?? 'viewer');

    echo 'ID: ' . $userId;
    echo 'Nome: ' . htmlspecialchars($userName, ENT_QUOTES | ENT_HTML5, 'UTF-8');
    echo 'Papel: ' . htmlspecialchars($userRole, ENT_QUOTES | ENT_HTML5, 'UTF-8');
} else {
    // Sessão não encontrada — redireciona para login
    header('Location: /login.php');
    exit; // ✅ Sempre exit após header Location
}
```

### Regeneração de ID — prevenção de session fixation

```php
<?php

declare(strict_types=1);

ini_set('session.cookie_httponly', '1');
ini_set('session.cookie_secure',   '1');
ini_set('session.cookie_samesite', 'Strict');
ini_set('session.use_strict_mode', '1');
session_start();

/**
 * Faz login do usuário na sessão com segurança.
 * Regenera o ID para prevenir session fixation attack.
 *
 * @param array<string, mixed> $userData Dados do usuário autenticado
 */
function loginUser(array $userData): void
{
    // ✅ OBRIGATÓRIO: regenera ID após login — previne session fixation
    session_regenerate_id(true); // true = deleta a sessão anterior

    $_SESSION['userId']       = (int) $userData['id'];
    $_SESSION['userName']     = (string) $userData['name'];
    $_SESSION['userRole']     = (string) $userData['role'];
    $_SESSION['loginTime']    = time();
    $_SESSION['lastActivity'] = time();
    $_SESSION['ipAddress']    = $_SERVER['REMOTE_ADDR'] ?? ''; // Para validação adicional
}

/**
 * Verifica se o usuário está autenticado e a sessão não expirou.
 *
 * @param int $timeoutSeconds Tempo máximo de inatividade em segundos
 */
function isAuthenticated(int $timeoutSeconds = 1800): bool
{
    if (!isset($_SESSION['userId'], $_SESSION['lastActivity'])) {
        return false;
    }

    // Verifica timeout por inatividade
    if ((time() - (int) $_SESSION['lastActivity']) > $timeoutSeconds) {
        session_unset();
        session_destroy();
        return false;
    }

    // Atualiza timestamp de última atividade
    $_SESSION['lastActivity'] = time();

    return true;
}

// Middleware de autenticação
if (!isAuthenticated()) {
    header('Location: /login.php?expired=1');
    exit;
}
```

### Modificando variáveis de sessão

```php
<?php

declare(strict_types=1);

session_start();

// Modificar — simplesmente reatribua
$_SESSION['userName'] = 'Ana Costa'; // Atualiza o nome

// Adicionar novo dado
$_SESSION['lastPage'] = '/dashboard';

// Remover uma variável específica
unset($_SESSION['tempData']);

// Verificar e exibir tudo (útil para debug)
// ⚠️ Nunca deixe print_r($_SESSION) em produção
if (($_SERVER['APP_ENV'] ?? 'production') === 'development') {
    echo '<pre>' . print_r($_SESSION, true) . '</pre>';
}
```

### Encerrando a sessão (logout)

```php
<?php

declare(strict_types=1);

ini_set('session.cookie_httponly', '1');
ini_set('session.cookie_secure',   '1');
ini_set('session.cookie_samesite', 'Strict');
session_start();

/**
 * Encerra completamente a sessão do usuário.
 * Segue o processo correto: unset → destroy → remove cookie.
 */
function logoutUser(): void
{
    // 1. Remove todas as variáveis de sessão
    session_unset();

    // 2. Destrói os dados da sessão no servidor
    session_destroy();

    // 3. Remove o cookie PHPSESSID do navegador
    if (ini_get('session.use_cookies')) {
        $params = session_get_cookie_params();
        setcookie(
            name:     session_name(),
            value:    '',
            expires:  time() - 42000,
            path:     $params['path'],
            domain:   $params['domain'],
            secure:   $params['secure'],
            httponly: $params['httponly'],
        );
    }
}

logoutUser();

// ✅ Redireciona após logout (padrão Post/Redirect/Get)
header('Location: /login.php?logout=1');
exit;
```

### Flash messages — mensagens de uma única exibição

```php
<?php

declare(strict_types=1);

session_start();

/**
 * Armazena uma flash message para exibição na próxima requisição.
 *
 * @param string $type    Tipo: 'success', 'error', 'warning', 'info'
 * @param string $message Mensagem a exibir
 */
function setFlash(string $type, string $message): void
{
    $_SESSION['_flash'][$type][] = $message;
}

/**
 * Recupera e remove as flash messages (one-time display).
 *
 * @return array<string, string[]>
 */
function getFlashes(): array
{
    $flashes = $_SESSION['_flash'] ?? [];
    unset($_SESSION['_flash']); // Remove após leitura — "flash" de uso único

    return $flashes;
}

// Definindo mensagens
setFlash('success', 'Cadastro realizado com sucesso!');
setFlash('warning', 'Seu plano expira em 3 dias.');

// Exibindo mensagens (em outro arquivo, após redirect)
$flashes = getFlashes();

$typeClasses = ['success' => 'verde', 'error' => 'vermelho', 'warning' => 'amarelo', 'info' => 'azul'];

foreach ($flashes as $type => $messages) {
    $cssClass = $typeClasses[$type] ?? 'cinza';

    foreach ($messages as $message) {
        $safeMsg = htmlspecialchars($message, ENT_QUOTES | ENT_HTML5, 'UTF-8');
        echo "<div class='alert {$cssClass}'>{$safeMsg}</div>";
    }
}
```

---

## 49. Filtros PHP — Validação e Sanitização

A extensão de filtros do PHP (`filter_*`) é a forma oficial de validar e sanitizar
dados externos. É obrigatória para qualquer input de formulário, URL ou cookie.

### Conceito fundamental

- **Validar** — verifica se o dado está no formato correto; **não altera** o valor (retorna `false` se inválido)
- **Sanitizar** — **remove caracteres ilegais** do dado; altera o valor para torná-lo seguro

> ⚠️ **Sanitizar ≠ validar.** Sanitize primeiro, depois valide — ou valide com `filter_var()` combinando ambos.

### filter_var() — validação e sanitização

```php
<?php

declare(strict_types=1);

// ── Validação de e-mail ──────────────────────────────────────────────────────
$email = 'usuario@example.com';
$validEmail = filter_var($email, FILTER_VALIDATE_EMAIL);

if ($validEmail !== false) {
    echo "E-mail válido: {$validEmail}";
} else {
    echo 'E-mail inválido.';
}

// ── Validação de URL ─────────────────────────────────────────────────────────
$url = 'https://php.net/manual';
$validUrl = filter_var($url, FILTER_VALIDATE_URL);
var_dump($validUrl); // string ou false

// ── Validação de inteiro ─────────────────────────────────────────────────────
$intValue = 42;

// ⚠️ Atenção ao valor 0: filter_var retorna 0 (int), que é falsy em PHP
// Use comparação estrita com false!
$result = filter_var($intValue, FILTER_VALIDATE_INT);

if ($result !== false) {
    echo "Inteiro válido: {$result}";
} else {
    echo 'Não é um inteiro.';
}

// ✅ Tratando o caso 0 corretamente
$zero = 0;
$isValidInt = filter_var($zero, FILTER_VALIDATE_INT) !== false; // ✅ true
var_dump($isValidInt);

// ── Validação de endereço IP ─────────────────────────────────────────────────
$ip = '192.168.1.100';
$validIp = filter_var($ip, FILTER_VALIDATE_IP);
var_dump($validIp); // string ou false

// ── Validação booleana ───────────────────────────────────────────────────────
// Reconhece: true/false, 1/0, on/off, yes/no (case-insensitive)
$trueValues  = ['true', '1', 'on', 'yes', 'TRUE', 'On'];
$falseValues = ['false', '0', 'off', 'no', 'FALSE', 'Off'];

foreach ($trueValues as $val) {
    $result = filter_var($val, FILTER_VALIDATE_BOOLEAN, FILTER_NULL_ON_FAILURE);
    var_dump($result); // bool(true)
}

// Strings inválidas retornam null com FILTER_NULL_ON_FAILURE
$invalid = filter_var('maybe', FILTER_VALIDATE_BOOLEAN, FILTER_NULL_ON_FAILURE);
var_dump($invalid); // NULL
```

### Sanitização — limpeza de dados

```php
<?php

declare(strict_types=1);

// ── Sanitizar e-mail (remove caracteres ilegais) ─────────────────────────────
$dirtyEmail = 'usuario (arroba) example .com';
$cleanEmail = filter_var($dirtyEmail, FILTER_SANITIZE_EMAIL);
// Remove caracteres fora de: letras, dígitos, !#$%&'*+/=?^_`{|}~.-@

echo $cleanEmail; // usuarioarrobaexample.com — ainda pode ser inválido após sanitização!

// ✅ Sanitize ANTES de validar
$rawEmail   = '  USUARIO@EXAMPLE.COM  ';
$cleanEmail = filter_var(trim($rawEmail), FILTER_SANITIZE_EMAIL);
$validEmail = filter_var(strtolower($cleanEmail), FILTER_VALIDATE_EMAIL);

// ── Sanitizar URL ─────────────────────────────────────────────────────────────
$dirtyUrl = 'https://example.com/path with spaces/página';
$cleanUrl = filter_var($dirtyUrl, FILTER_SANITIZE_URL);
// Remove caracteres ilegais em URLs

// ── Sanitizar inteiro (remove tudo exceto dígitos e sinais + -) ───────────────
$dirtyInt = '  -42abc!@# ';
$cleanInt = filter_var($dirtyInt, FILTER_SANITIZE_NUMBER_INT);
echo $cleanInt; // -42

// ── Sanitizar float ───────────────────────────────────────────────────────────
$dirtyFloat = '3,14 reais';
$cleanFloat = filter_var($dirtyFloat, FILTER_SANITIZE_NUMBER_FLOAT, FILTER_FLAG_ALLOW_FRACTION);
echo $cleanFloat; // 314 (vírgula não é separador — use str_replace primeiro)

// ✅ Forma correta para float BR → EN
$brFloat    = '1.234,56';
$normalized = str_replace(['.', ','], ['', '.'], $brFloat); // '1234.56'
$cleanFloat = filter_var($normalized, FILTER_VALIDATE_FLOAT);
echo $cleanFloat; // 1234.56

// ── Sanitizar string especial (remove/escapa HTML) ────────────────────────────
// ⚠️ FILTER_SANITIZE_STRING foi removido no PHP 8.1!
// ✅ Alternativa moderna: htmlspecialchars() ou strip_tags()
$dirtyHtml = '<script>alert("XSS")</script>Texto normal';
$safeHtml  = htmlspecialchars($dirtyHtml, ENT_QUOTES | ENT_HTML5, 'UTF-8');
// &lt;script&gt;alert(&quot;XSS&quot;)&lt;/script&gt;Texto normal

$noTags = strip_tags($dirtyHtml); // Remove tags: 'alert("XSS")Texto normal'
```

### filter_input() — lê e filtra superglobal em uma etapa

```php
<?php

declare(strict_types=1);

// ✅ Mais seguro que acessar $_POST/$_GET diretamente
// INPUT_POST, INPUT_GET, INPUT_COOKIE, INPUT_SERVER, INPUT_ENV

// Lê $_POST['email'] e valida como e-mail
$email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);
// Retorna: string válida | false (inválido) | null (campo ausente)

// Lê $_GET['page'] e valida como inteiro entre 1 e 1000
$page = filter_input(INPUT_GET, 'page', FILTER_VALIDATE_INT, [
    'options' => [
        'default'   => 1,
        'min_range' => 1,
        'max_range' => 1000,
    ],
]);
// Retorna: int válido no range | valor default | false

// Lê $_GET['q'] e sanitiza como string especial
$search = filter_input(INPUT_GET, 'q', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';

// Lê $_SERVER['REMOTE_ADDR'] e valida como IP
$clientIp = filter_input(INPUT_SERVER, 'REMOTE_ADDR', FILTER_VALIDATE_IP) ?? '0.0.0.0';
```

### filter_var_array() — valida múltiplos campos de uma vez

```php
<?php

declare(strict_types=1);

// ✅ Valida todo o $_POST de uma vez — mais eficiente para formulários grandes
$rules = [
    'name'    => FILTER_SANITIZE_SPECIAL_CHARS,
    'email'   => FILTER_VALIDATE_EMAIL,
    'age'     => [
        'filter'  => FILTER_VALIDATE_INT,
        'options' => ['min_range' => 1, 'max_range' => 120],
    ],
    'website' => FILTER_VALIDATE_URL,
    'active'  => FILTER_VALIDATE_BOOLEAN,
];

// Simula dados de formulário
$postData = [
    'name'    => 'Ana Silva',
    'email'   => 'ana@example.com',
    'age'     => '30',
    'website' => 'https://ana.dev',
    'active'  => 'true',
];

$filtered = filter_var_array($postData, $rules);

// $filtered agora tem os valores validados ou false para inválidos
var_dump($filtered['email']);   // string(15) "ana@example.com"
var_dump($filtered['age']);     // int(30)
var_dump($filtered['active']);  // bool(true)
```

### Listando todos os filtros disponíveis

```php
<?php

declare(strict_types=1);

// filter_list() retorna todos os nomes de filtros disponíveis
foreach (filter_list() as $filterName) {
    $filterId = filter_id($filterName);
    echo "{$filterName} (ID: {$filterId})";
}
```

---

## 50. Filtros Avançados

### Validação de inteiro com range

```php
<?php

declare(strict_types=1);

/**
 * Valida um inteiro dentro de um intervalo específico.
 *
 * @param mixed $value    Valor a validar
 * @param int   $minRange Valor mínimo permitido
 * @param int   $maxRange Valor máximo permitido
 *
 * @return int|false Inteiro validado ou false
 */
function validateIntRange(mixed $value, int $minRange, int $maxRange): int|false
{
    return filter_var($value, FILTER_VALIDATE_INT, [
        'options' => [
            'min_range' => $minRange,
            'max_range' => $maxRange,
        ],
    ]);
}

// Usos práticos
$page    = validateIntRange($_GET['page'] ?? 1, 1, 1000);
$rating  = validateIntRange($_POST['rating'] ?? '', 1, 5);
$percent = validateIntRange($_POST['discount'] ?? '', 0, 100);

var_dump($page);    // int(1) ou false
var_dump($rating);  // int(1–5) ou false
var_dump($percent); // int(0–100) ou false

// Usando com fallback seguro
$currentPage = ($page !== false) ? $page : 1;
echo "Página: {$currentPage}";
```

### Validação de endereços IP (IPv4 e IPv6)

```php
<?php

declare(strict_types=1);

$ipv4     = '192.168.1.100';
$ipv6     = '2001:0db8:85a3:08d3:1319:8a2e:0370:7334';
$loopback = '127.0.0.1';
$private  = '10.0.0.1';

// Valida qualquer IP (v4 ou v6)
$validIpv4 = filter_var($ipv4, FILTER_VALIDATE_IP);
$validIpv6 = filter_var($ipv6, FILTER_VALIDATE_IP, FILTER_FLAG_IPV6);

// Flags disponíveis para FILTER_VALIDATE_IP:
$flags = [
    'Qualquer IP'     => 0,
    'Apenas IPv4'     => FILTER_FLAG_IPV4,
    'Apenas IPv6'     => FILTER_FLAG_IPV6,
    'Sem privados'    => FILTER_FLAG_NO_PRIV_RANGE,   // Rejeita 10.x, 192.168.x, etc.
    'Sem reservados'  => FILTER_FLAG_NO_RES_RANGE,    // Rejeita 127.x, 0.x, etc.
];

foreach ($flags as $label => $flag) {
    $result = filter_var($ipv4, FILTER_VALIDATE_IP, $flag);
    $valid  = $result !== false ? '✅' : '❌';
    echo "{$valid} {$label}: '{$ipv4}'";
}

// ✅ Uso prático: log de IP do cliente
// ⚠️ $_SERVER['REMOTE_ADDR'] pode ser forjado via proxy — use apenas para logging
$clientIp = filter_var(
    $_SERVER['REMOTE_ADDR'] ?? '',
    FILTER_VALIDATE_IP,
    FILTER_FLAG_NO_RES_RANGE // Rejeita IPs reservados como 0.0.0.0
) ?: 'ip-desconhecido';

echo "IP do cliente: " . htmlspecialchars($clientIp, ENT_QUOTES | ENT_HTML5, 'UTF-8');
```

### Validação de URL com flags específicas

```php
<?php

declare(strict_types=1);

$urlComQuery    = 'https://example.com/search?q=php&v=8.5';
$urlSemQuery    = 'https://example.com/pagina';
$urlComFragmento = 'https://example.com/docs#secao-3';

// FILTER_FLAG_QUERY_REQUIRED — exige query string (?chave=valor)
$validWithQuery = filter_var(
    $urlComQuery,
    FILTER_VALIDATE_URL,
    FILTER_FLAG_QUERY_REQUIRED
);
var_dump($validWithQuery); // string — válido

$invalidWithQuery = filter_var(
    $urlSemQuery,
    FILTER_VALIDATE_URL,
    FILTER_FLAG_QUERY_REQUIRED
);
var_dump($invalidWithQuery); // false — inválido (sem query string)

// Validação completa de URL para formulário
function validateFormUrl(string $rawUrl, bool $requireHttps = true): string|false
{
    $url = trim($rawUrl);

    if (empty($url)) {
        return false;
    }

    // Adiciona https:// se ausente
    if (!str_contains($url, '://')) {
        $url = 'https://' . $url;
    }

    $validated = filter_var($url, FILTER_VALIDATE_URL);

    if ($validated === false) {
        return false;
    }

    // ✅ PHP 8.5: URI Extension para análise detalhada
    try {
        $uri = new Uri\Rfc3986\Uri($validated);
        $scheme = $uri->getScheme();

        if ($requireHttps && $scheme !== 'https') {
            return false; // Exige HTTPS
        }

        if (!in_array($scheme, ['http', 'https'], strict: true)) {
            return false; // Rejeita ftp://, javascript:, etc.
        }
    } catch (\Throwable) {
        return false;
    }

    return $validated;
}

var_dump(validateFormUrl('php.net'));                 // 'https://php.net'
var_dump(validateFormUrl('http://example.com', true)); // false — exige HTTPS
var_dump(validateFormUrl('ftp://files.example.com')); // false — protocolo inválido
```

### Sanitização avançada de strings

```php
<?php

declare(strict_types=1);

// ── FILTER_SANITIZE_STRING foi REMOVIDO no PHP 8.1 ───────────────────────────
// ✅ Alternativas modernas:

$input = '<h1>Olá, Mundo!</h1><script>alert("XSS")</script>Texto com ñ e ü';

// 1. htmlspecialchars() — escapa caracteres HTML (preserva o texto)
$escaped = htmlspecialchars($input, ENT_QUOTES | ENT_HTML5, 'UTF-8');
// &lt;h1&gt;Olá, Mundo!&lt;/h1&gt;&lt;script&gt;alert(&quot;XSS&quot;)&lt;/script&gt;Texto com ñ e ü

// 2. strip_tags() — remove as tags HTML (preserva o texto interno)
$noTags = strip_tags($input);
// Olá, Mundo!alert("XSS")Texto com ñ e ü

// 3. strip_tags() com whitelist de tags permitidas
$allowedTags = '<p><strong><em><ul><ol><li><a>';
$safeHtml = strip_tags($input, $allowedTags);

// 4. FILTER_SANITIZE_SPECIAL_CHARS — converte caracteres especiais em entidades HTML
$specialChars = filter_var($input, FILTER_SANITIZE_SPECIAL_CHARS);
// Remove ASCII > 127, converte < > " ' &

// 5. Pipeline completo para input de usuário (texto simples)
function sanitizeUserText(string $input, int $maxLength = 500): string
{
    return $input
        |> trim(...)
        |> (fn(string $s): string => mb_substr($s, 0, $maxLength))
        |> (fn(string $s): string => strip_tags($s))
        |> (fn(string $s): string => htmlspecialchars($s, ENT_QUOTES | ENT_HTML5, 'UTF-8'));
}

echo sanitizeUserText('<script>XSS</script>Texto normal do usuário');
// Texto normal do usuário
```

### Referência completa de filtros úteis

**Filtros de validação** — retornam o valor ou `false`:

| Filtro | Valida | Exemplo válido |
|--------|--------|----------------|
| `FILTER_VALIDATE_EMAIL` | E-mail RFC | `user@example.com` |
| `FILTER_VALIDATE_URL` | URL | `https://php.net` |
| `FILTER_VALIDATE_IP` | IPv4 ou IPv6 | `192.168.1.1` |
| `FILTER_VALIDATE_INT` | Inteiro | `42`, `-7` |
| `FILTER_VALIDATE_FLOAT` | Float | `3.14`, `-0.5` |
| `FILTER_VALIDATE_BOOLEAN` | Booleano | `true`, `1`, `on`, `yes` |
| `FILTER_VALIDATE_DOMAIN` | Nome de domínio | `example.com` |

**Filtros de sanitização** — retornam o valor limpo:

| Filtro | Remove/converte |
|--------|----------------|
| `FILTER_SANITIZE_EMAIL` | Caracteres ilegais em e-mails |
| `FILTER_SANITIZE_URL` | Caracteres ilegais em URLs |
| `FILTER_SANITIZE_NUMBER_INT` | Tudo exceto dígitos, `+`, `-` |
| `FILTER_SANITIZE_NUMBER_FLOAT` | Tudo exceto dígitos, `.`, `+`, `-` |
| `FILTER_SANITIZE_SPECIAL_CHARS` | Converte `<>"'` em entidades HTML |
| `FILTER_SANITIZE_ENCODED` | URL-encodes caracteres especiais |
| `FILTER_SANITIZE_ADD_SLASHES` | Adiciona `\` antes de `'`, `"`, `\`, null |

> ⚠️ `FILTER_SANITIZE_STRING` foi **removido no PHP 8.1**. Use `htmlspecialchars()` ou `strip_tags()`.

### Pipeline de validação completa — exemplo production-grade

```php
<?php

declare(strict_types=1);

/**
 * Valida e retorna os dados de um formulário de cadastro.
 * Usa filter_var_array() para processar todos os campos de uma vez.
 *
 * @param array<string, mixed> $rawData Dados brutos (ex: $_POST)
 *
 * @return array{valid: bool, data: array<string, mixed>, errors: array<string, string>}
 */
function validateRegistrationForm(array $rawData): array
{
    $errors = [];
    $data   = [];

    // 1. Sanitização inicial de todos os campos de texto
    $name    = filter_var(trim($rawData['name']    ?? ''), FILTER_SANITIZE_SPECIAL_CHARS);
    $email   = filter_var(trim($rawData['email']   ?? ''), FILTER_SANITIZE_EMAIL);
    $age     = $rawData['age']     ?? null;
    $website = filter_var(trim($rawData['website'] ?? ''), FILTER_SANITIZE_URL);

    // 2. Validação campo por campo
    if (empty($name) || mb_strlen($name) < 2) {
        $errors['name'] = 'Nome deve ter pelo menos 2 caracteres.';
    } else {
        $data['name'] = $name;
    }

    $validEmail = filter_var($email, FILTER_VALIDATE_EMAIL);

    if ($validEmail === false) {
        $errors['email'] = 'E-mail inválido.';
    } else {
        $data['email'] = strtolower($validEmail);
    }

    $validAge = filter_var($age, FILTER_VALIDATE_INT, [
        'options' => ['min_range' => 1, 'max_range' => 120],
    ]);

    if ($validAge === false) {
        $errors['age'] = 'Idade deve ser um número entre 1 e 120.';
    } else {
        $data['age'] = $validAge;
    }

    if (!empty($website)) {
        $validUrl = filter_var($website, FILTER_VALIDATE_URL);

        if ($validUrl === false) {
            $errors['website'] = 'URL inválida.';
        } else {
            $data['website'] = $validUrl;
        }
    }

    return [
        'valid'  => empty($errors),
        'data'   => $data,
        'errors' => $errors,
    ];
}

// Uso
$result = validateRegistrationForm($_POST);

if ($result['valid']) {
    // ✅ Dados validados — use $result['data'] com segurança
    $userName = $result['data']['name'];
    echo 'Cadastro válido para: ' . htmlspecialchars($userName, ENT_QUOTES | ENT_HTML5, 'UTF-8');
} else {
    foreach ($result['errors'] as $field => $message) {
        echo htmlspecialchars("{$field}: {$message}", ENT_QUOTES | ENT_HTML5, 'UTF-8');
    }
}
```

---

## 51. Funções de Callback

Uma **função de callback** é uma função passada como argumento para outra função,
que a executa internamente. É um dos padrões mais poderosos de programação funcional em PHP.

### Formas de definir um callback

```php
<?php

declare(strict_types=1);

// 1. Função nomeada passada como string
function doubleValue(int $n): int
{
    return $n * 2;
}

$numbers = [1, 2, 3, 4, 5];
$doubled = array_map('doubleValue', $numbers);
// [2, 4, 6, 8, 10]

// 2. ✅ FCC — First-Class Callable Syntax (PHP 8.1+): mais seguro que string
$doubled = array_map(doubleValue(...), $numbers);
// Detecta erros em tempo de análise (typos no nome da função)

// 3. Closure anônima
$squared = array_map(fn(int $n): int => $n ** 2, $numbers);
// [1, 4, 9, 16, 25]

// 4. Método de objeto como callback
final class MathHelper
{
    public function triple(int $n): int
    {
        return $n * 3;
    }

    public static function negate(int $n): int
    {
        return -$n;
    }
}

$helper  = new MathHelper();
$tripled = array_map($helper->triple(...), $numbers);   // FCC em método de instância
$negated = array_map(MathHelper::negate(...), $numbers); // FCC em método estático
```

### Callbacks como parâmetro de funções customizadas

```php
<?php

declare(strict_types=1);

/**
 * Aplica um formatador a uma string e retorna o resultado.
 *
 * @param string   $text      Texto a formatar
 * @param callable $formatter Função de formatação
 *
 * @return string Texto formatado
 */
function applyFormatter(string $text, callable $formatter): string
{
    return $formatter($text);
}

// Diferentes formatadores
$shout    = fn(string $s): string => strtoupper($s) . '!!!';
$whisper  = fn(string $s): string => strtolower($s) . '...';
$truncate = fn(string $s): string => mb_substr($s, 0, 10) . (mb_strlen($s) > 10 ? '…' : '');

echo applyFormatter('Hello World', $shout);    // HELLO WORLD!!!
echo applyFormatter('Hello World', $whisper);  // hello world...
echo applyFormatter('Hello World', $truncate); // Hello Worl…
echo applyFormatter('Hello World', trim(...)); // FCC — Hello World
```

### Callbacks em funções nativas de array

```php
<?php

declare(strict_types=1);

$products = [
    ['name' => 'Teclado',  'price' => 250.0,  'stock' => 15],
    ['name' => 'Mouse',    'price' => 89.90,   'stock' => 0],
    ['name' => 'Monitor',  'price' => 1499.0,  'stock' => 8],
    ['name' => 'Headset',  'price' => 320.0,   'stock' => 0],
    ['name' => 'Webcam',   'price' => 199.90,  'stock' => 23],
];

// array_filter() com callback — filtra produtos em estoque
$inStock = array_filter(
    $products,
    fn(array $p): bool => $p['stock'] > 0
);

// array_map() com callback — aplica desconto de 10%
$withDiscount = array_map(
    fn(array $p): array => [...$p, 'price' => round($p['price'] * 0.9, 2)],
    array_values($inStock) // array_values re-indexa após o filter
);

// usort() com callback — ordena por preço crescente
usort($withDiscount, fn(array $a, array $b): int => $a['price'] <=> $b['price']);

// array_reduce() com callback — soma o total
$total = array_reduce(
    $withDiscount,
    fn(float $carry, array $p): float => $carry + $p['price'],
    0.0
);

echo 'Total em estoque (com desconto): R$ ' . number_format($total, 2, ',', '.');
```

### Callable type hint — garantindo tipo

```php
<?php

declare(strict_types=1);

/**
 * Pipeline de processamento de dados com callbacks encadeados.
 *
 * @param mixed      $value    Valor inicial
 * @param callable[] $pipeline Lista de transformações a aplicar
 *
 * @return mixed Valor após todas as transformações
 */
function pipeline(mixed $value, array $pipeline): mixed
{
    foreach ($pipeline as $step) {
        if (!is_callable($step)) {
            throw new \InvalidArgumentException('Todos os passos devem ser callable.');
        }

        $value = $step($value);
    }

    return $value;
}

// ✅ PHP 8.5: combinar pipeline() com pipe operator
$result = pipeline('  PHP 8.5 Released!  ', [
    trim(...),
    strtolower(...),
    fn(string $s): string => str_replace(' ', '-', $s),
    fn(string $s): string => str_replace('!', '', $s),
]);

echo $result; // php-8.5-released

// Equivalente com pipe operator:
$slug = '  PHP 8.5 Released!  '
    |> trim(...)
    |> strtolower(...)
    |> (fn(string $s): string => str_replace(' ', '-', $s))
    |> (fn(string $s): string => str_replace('!', '', $s));
```

### Closure::getCurrent() — recursão em funções anônimas (PHP 8.5)

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.5: Closure::getCurrent() permite recursão sem nomear a função
$factorial = function(int $n): int {
    if ($n <= 1) {
        return 1;
    }

    // Obtém referência à própria closure em execução
    $self = Closure::getCurrent();

    return $n * $self($n - 1);
};

echo $factorial(5);  // 120
echo $factorial(10); // 3628800
```

---

## 52. PHP e JSON

**JSON** (JavaScript Object Notation) é o formato padrão de troca de dados entre APIs,
microsserviços e front-ends. PHP oferece suporte nativo completo via `json_encode()` e `json_decode()`.

### json_encode() — PHP → JSON

```php
<?php

declare(strict_types=1);

// Array associativo → objeto JSON
$user = [
    'id'      => 1,
    'name'    => 'Ana Silva',
    'email'   => 'ana@example.com',
    'active'  => true,
    'score'   => 9.5,
    'tags'    => ['php', 'backend', 'api'],
];

$json = json_encode($user);
echo $json;
// {"id":1,"name":"Ana Silva","email":"ana@example.com","active":true,"score":9.5,"tags":["php","backend","api"]}

// ✅ Flags úteis do json_encode()
$prettyJson = json_encode($user, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES);
// JSON_PRETTY_PRINT      — indentação legível
// JSON_UNESCAPED_UNICODE — mantém acentos (ã, é, ç) sem escape \uXXXX
// JSON_UNESCAPED_SLASHES — mantém / sem escape \/
// JSON_THROW_ON_ERROR    — lança JsonException em vez de retornar false

echo $prettyJson;

// Array indexado → array JSON
$cars = ['Volvo', 'BMW', 'Toyota'];
echo json_encode($cars); // ["Volvo","BMW","Toyota"]

// ✅ Sempre verifique erros de encoding
$invalidUtf8 = "\xB1\x31"; // Sequência UTF-8 inválida
$result = json_encode(['text' => $invalidUtf8]);

if ($result === false) {
    $errorCode    = json_last_error();
    $errorMessage = json_last_error_msg();
    throw new \JsonException("json_encode falhou: {$errorMessage} (código {$errorCode})");
}

// ✅ Prefira JSON_THROW_ON_ERROR — exceção automática em erro
$safeJson = json_encode($user, JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE);
```

### json_decode() — JSON → PHP

```php
<?php

declare(strict_types=1);

$jsonString = '{"id":1,"name":"Ana Silva","role":"admin","active":true}';

// Decodifica para OBJETO stdClass (padrão)
$obj = json_decode($jsonString);
echo $obj->name;   // Ana Silva
echo $obj->role;   // admin
echo $obj->active; // 1

// ✅ Decodifica para ARRAY ASSOCIATIVO (segundo parâmetro true)
// Preferível — mais fácil de tipar e trabalhar em PHP estrito
$arr = json_decode($jsonString, associative: true);
echo $arr['name'];   // Ana Silva
echo $arr['role'];   // admin
var_dump($arr['active']); // bool(true)

// ✅ JSON_THROW_ON_ERROR — exceção automática em JSON inválido
try {
    $data = json_decode('{"malformado": }', associative: true, flags: JSON_THROW_ON_ERROR);
} catch (\JsonException $e) {
    echo 'JSON inválido: ' . $e->getMessage();
}

// Verificação de erro sem exceção (legacy)
$data = json_decode('string invalida', associative: true);

if (json_last_error() !== JSON_ERROR_NONE) {
    throw new \JsonException('JSON inválido: ' . json_last_error_msg());
}
```

### Percorrendo dados JSON decodificados

```php
<?php

declare(strict_types=1);

$usersJson = '[
    {"id": 1, "name": "Ana",    "role": "admin",  "active": true},
    {"id": 2, "name": "Carlos", "role": "editor", "active": false},
    {"id": 3, "name": "Maria",  "role": "viewer", "active": true}
]';

// ✅ Decodifica como array associativo — tipagem mais previsível
$users = json_decode($usersJson, associative: true, flags: JSON_THROW_ON_ERROR);

// Filtra apenas usuários ativos
$activeUsers = array_filter($users, fn(array $u): bool => $u['active'] === true);

// Exibe com escape de segurança
foreach ($activeUsers as $user) {
    $id   = (int)    $user['id'];
    $name = htmlspecialchars((string) $user['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
    $role = htmlspecialchars((string) $user['role'], ENT_QUOTES | ENT_HTML5, 'UTF-8');

    echo "#{$id} {$name} ({$role})";
}
```

### API JSON — resposta bem formada

```php
<?php

declare(strict_types=1);

/**
 * Envia uma resposta JSON padronizada e encerra o script.
 *
 * @param mixed $data       Dados a serializar
 * @param int   $statusCode Código HTTP de status
 *
 * @return never
 */
function sendJsonResponse(mixed $data, int $statusCode = 200): never
{
    http_response_code($statusCode);
    header('Content-Type: application/json; charset=UTF-8');
    header('X-Content-Type-Options: nosniff');

    echo json_encode($data, JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES);
    exit;
}

// Uso:
sendJsonResponse([
    'status'  => 'success',
    'message' => 'Usuário criado com sucesso.',
    'data'    => ['id' => 42, 'name' => 'Ana Silva'],
], 201);
```

### json_validate() — valida sem decodificar (PHP 8.3+)

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.3+: verifica se uma string é JSON válida sem decodificar
$validJson   = '{"name": "PHP", "version": 8.5}';
$invalidJson = '{name: PHP}'; // Chaves sem aspas — inválido

var_dump(json_validate($validJson));   // bool(true)
var_dump(json_validate($invalidJson)); // bool(false)

// Útil para validação antes de processar payloads de API
function processApiPayload(string $rawBody): array
{
    if (!json_validate($rawBody)) {
        throw new \InvalidArgumentException('Payload não é um JSON válido.');
    }

    return json_decode($rawBody, associative: true, flags: JSON_THROW_ON_ERROR);
}
```

---

## 53. Exceções (Exceptions)

Exceções são a forma moderna de lidar com erros em PHP — substituem o antigo padrão
de retornar `false` ou códigos de erro numéricos. Permitem separar o fluxo normal
do tratamento de erros.

### throw — lançando exceções

```php
<?php

declare(strict_types=1);

function divide(float $dividend, float $divisor): float
{
    if ($divisor === 0.0) {
        // ✅ Lança exceção específica — DivisionByZeroError é mais preciso que Exception
        throw new \DivisionByZeroError('Divisor não pode ser zero.');
    }

    return $dividend / $divisor;
}

// Sem try/catch: PHP lança Fatal Error com backtrace completo (PHP 8.5)
// echo divide(10, 0); // Fatal error: Uncaught DivisionByZeroError
```

### try...catch — capturando exceções

```php
<?php

declare(strict_types=1);

function divide(float $dividend, float $divisor): float
{
    if ($divisor === 0.0) {
        throw new \DivisionByZeroError('Divisor não pode ser zero.');
    }

    return $dividend / $divisor;
}

try {
    echo divide(10, 2);  // ✅ 5.0
    echo divide(10, 0);  // ❌ Lança DivisionByZeroError
    echo 'Esta linha nunca executa após a exceção';
} catch (\DivisionByZeroError $e) {
    // Captura erros de divisão por zero
    echo 'Erro de divisão: ' . htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');
} catch (\Throwable $e) {
    // Captura qualquer outro erro ou exceção (fallback genérico)
    echo 'Erro inesperado: ' . htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');
}

echo 'Script continua normalmente após o catch.';
```

### try...catch...finally

```php
<?php

declare(strict_types=1);

function readFileContent(string $filePath): string
{
    $handle = fopen($filePath, 'r');

    if ($handle === false) {
        throw new \RuntimeException("Não foi possível abrir: {$filePath}");
    }

    try {
        $content = fread($handle, filesize($filePath) ?: 0);

        if ($content === false) {
            throw new \RuntimeException("Falha ao ler: {$filePath}");
        }

        return $content;
    } finally {
        // ✅ finally SEMPRE executa — com ou sem exceção
        // Ideal para liberar recursos: fechar arquivos, conexões DB, etc.
        fclose($handle);
    }
}

try {
    $content = readFileContent(__DIR__ . '/data.txt');
    echo $content;
} catch (\RuntimeException $e) {
    echo 'Erro: ' . htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');
} finally {
    echo 'Operação de leitura finalizada.'; // Sempre exibe
}
```

### Múltiplos catch e captura combinada

```php
<?php

declare(strict_types=1);

function processUserInput(string $input): int
{
    if (empty(trim($input))) {
        throw new \InvalidArgumentException('Input não pode ser vazio.');
    }

    if (!is_numeric($input)) {
        throw new \UnexpectedValueException("'{$input}' não é um número.");
    }

    $value = (int) $input;

    if ($value < 0) {
        throw new \RangeException('O valor deve ser positivo.');
    }

    return $value;
}

$inputs = ['42', '', 'abc', '-5'];

foreach ($inputs as $input) {
    try {
        $result = processUserInput($input);
        echo "Válido: {$result}";
    } catch (\InvalidArgumentException | \UnexpectedValueException $e) {
        // ✅ Captura múltiplas exceções com | (PHP 8.0+)
        echo 'Entrada inválida: ' . $e->getMessage();
    } catch (\RangeException $e) {
        echo 'Fora do intervalo: ' . $e->getMessage();
    }
}
```

### Objeto Exception — métodos disponíveis

```php
<?php

declare(strict_types=1);

function riskyOperation(): void
{
    throw new \RuntimeException('Algo deu errado.', code: 500);
}

try {
    riskyOperation();
} catch (\RuntimeException $e) {
    // Métodos do objeto Exception
    echo $e->getMessage();    // 'Algo deu errado.'
    echo $e->getCode();       // 500
    echo $e->getFile();       // Caminho absoluto do arquivo onde ocorreu
    echo $e->getLine();       // Número da linha
    echo $e->getTraceAsString(); // Stack trace completo como string

    // Em PHP 8.5: backtrace incluído automaticamente em Fatal Errors não capturados
}
```

### Hierarquia de exceções — SPL e customizadas

```php
<?php

declare(strict_types=1);

// ✅ Crie exceções customizadas para domínios específicos do negócio
class DomainException extends \RuntimeException {}

class UserNotFoundException extends DomainException
{
    public function __construct(int $userId, \Throwable $previous = null)
    {
        parent::__construct(
            message:  "Usuário #{$userId} não encontrado.",
            code:     404,
            previous: $previous, // ✅ Encadeia a exceção original (exception chaining)
        );
    }
}

class InsufficientFundsException extends DomainException
{
    public function __construct(
        public readonly float $requested,
        public readonly float $available,
    ) {
        parent::__construct(
            message: "Saldo insuficiente. Solicitado: R$ {$requested}, disponível: R$ {$available}.",
            code:    422,
        );
    }
}

// Uso
function findUser(int $id): array
{
    $users = [1 => ['name' => 'Ana'], 2 => ['name' => 'Carlos']];

    return $users[$id] ?? throw new UserNotFoundException($id);
}

try {
    $user = findUser(99);
} catch (UserNotFoundException $e) {
    // Exibe apenas mensagem — nunca exponha stack trace ao usuário final
    echo htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');

    // Log completo internamente
    error_log($e->getMessage() . ' | ' . $e->getFile() . ':' . $e->getLine());
}

// Hierarquia de exceções PHP — do mais específico ao mais genérico:
// Throwable
// ├── Error (erros de engine: TypeError, ParseError, DivisionByZeroError...)
// └── Exception
//     ├── RuntimeException (erros em tempo de execução)
//     │   ├── OutOfRangeException
//     │   └── OverflowException
//     ├── LogicException (erros de lógica de programação)
//     │   ├── InvalidArgumentException
//     │   ├── OutOfBoundsException
//     │   └── UnexpectedValueException
//     └── JsonException
```

---

## 54. Orientação a Objetos — Introdução

**Programação Orientada a Objetos (POO)** organiza o código em **classes** (moldes/templates)
e **objetos** (instâncias concretas). É o paradigma dominante no desenvolvimento PHP moderno.

### Por que usar POO?

| Característica | Benefício |
|----------------|-----------|
| **Encapsulamento** | Controla o acesso ao estado interno via modificadores (`public`, `protected`, `private`) |
| **Herança** | Reutiliza código de classes pai em classes filhas sem duplicação |
| **Polimorfismo** | Diferentes classes respondem ao mesmo método de formas distintas |
| **Abstração** | Esconde a complexidade interna, expõe apenas o necessário |
| **DRY** | "Don't Repeat Yourself" — lógica definida uma vez, usada em vários lugares |
| **Testabilidade** | Classes isoladas são mais fáceis de testar com unit tests |

### Conceitos fundamentais

```
Classe  = molde / template / planta baixa
Objeto  = instância concreta criada a partir da classe

Classe Fruit     → Objeto $apple  (Fruit específica)
Classe Car       → Objeto $myCar  (Car específica)
Classe UserRepo  → Objeto $repo   (repositório concreto)
```

### Procedural vs Orientado a Objetos

```php
<?php

declare(strict_types=1);

// ❌ LEGACY: Abordagem procedural — funções soltas, estado global
$userName  = 'Ana';
$userEmail = 'ana@example.com';
$userAge   = 30;

function getUserFullInfo(string $name, string $email, int $age): string
{
    return "{$name} ({$email}), {$age} anos";
}

echo getUserFullInfo($userName, $userEmail, $userAge);

// ✅ POO: Dados e comportamento encapsulados na classe
final class User
{
    public function __construct(
        private readonly string $name,
        private readonly string $email,
        private readonly int    $age,
    ) {}

    public function getFullInfo(): string
    {
        return "{$this->name} ({$this->email}), {$this->age} anos";
    }
}

$user = new User(name: 'Ana', email: 'ana@example.com', age: 30);
echo $user->getFullInfo();
```

---

## 55. Classes e Objetos

### Definindo uma classe — PHP 8.5 moderno

```php
<?php

declare(strict_types=1);

/**
 * Representa um produto no catálogo.
 *
 * Boas práticas PHP 8.5:
 * - final: previne herança não intencional
 * - readonly: propriedades imutáveis após construção
 * - Constructor Property Promotion: elimina declaração redundante
 * - Type hints completos em propriedades, parâmetros e retornos
 */
final class Product
{
    // Constructor Property Promotion (PHP 8.0+) — mais conciso e sem duplicação
    public function __construct(
        private readonly int    $id,
        private readonly string $name,
        private readonly float  $price,
        private readonly int    $stock = 0,
    ) {
        // Validações no construtor garantem objetos sempre válidos
        if ($this->price < 0.0) {
            throw new \InvalidArgumentException('Preço não pode ser negativo.');
        }

        if (empty(trim($this->name))) {
            throw new \InvalidArgumentException('Nome do produto não pode ser vazio.');
        }
    }

    // Getters — acesso controlado às propriedades privadas
    public function getId(): int    { return $this->id; }
    public function getName(): string { return $this->name; }
    public function getPrice(): float { return $this->price; }
    public function getStock(): int   { return $this->stock; }

    public function isAvailable(): bool
    {
        return $this->stock > 0;
    }

    public function getFormattedPrice(): string
    {
        return 'R$ ' . number_format($this->price, 2, ',', '.');
    }

    // ✅ PHP 8.5: Clone With para modificar readonly sem violar imutabilidade
    public function withPrice(float $newPrice): self
    {
        return clone($this, ['price' => $newPrice]);
    }

    public function withStock(int $newStock): self
    {
        return clone($this, ['stock' => $newStock]);
    }

    /** Representação em string — útil para debug */
    public function __toString(): string
    {
        return "Product#{$this->id}({$this->name}, {$this->getFormattedPrice()})";
    }
}

// Criando objetos com new + Named Arguments
$keyboard = new Product(id: 1, name: 'Teclado Mecânico', price: 350.0, stock: 15);
$mouse    = new Product(id: 2, name: 'Mouse Gamer',       price: 189.90, stock: 0);

echo $keyboard->getName();         // Teclado Mecânico
echo $keyboard->getFormattedPrice(); // R$ 350,00
var_dump($keyboard->isAvailable());  // bool(true)
var_dump($mouse->isAvailable());     // bool(false)

// Clone com preço alterado — objeto original intacto
$saleKeyboard = $keyboard->withPrice(299.0);
echo $keyboard->getFormattedPrice();     // R$ 350,00 (original intacto)
echo $saleKeyboard->getFormattedPrice(); // R$ 299,00 (novo objeto)

// instanceof — verificação de tipo
var_dump($keyboard instanceof Product); // bool(true)

echo $keyboard; // Product#1(Teclado Mecânico, R$ 350,00)
```

### Múltiplos objetos da mesma classe

```php
<?php

declare(strict_types=1);

final class Car
{
    public function __construct(
        public readonly string $brand,
        public readonly string $model,
        public readonly int    $year,
    ) {}

    public function describe(): string
    {
        return "{$this->year} {$this->brand} {$this->model}";
    }
}

// Cada objeto tem seu próprio estado independente
$volvo  = new Car(brand: 'Volvo',  model: 'XC90',   year: 2024);
$bmw    = new Car(brand: 'BMW',    model: 'X5',      year: 2023);
$toyota = new Car(brand: 'Toyota', model: 'Corolla', year: 2025);

$fleet = [$volvo, $bmw, $toyota];

foreach ($fleet as $car) {
    echo $car->describe();
}
```

---

## 56. Constructor e Destructor

### __construct() — inicialização do objeto

```php
<?php

declare(strict_types=1);

/**
 * Conexão com banco de dados — exemplo de uso de constructor.
 * O constructor garante que o objeto nunca seja criado em estado inválido.
 */
final class DatabaseConnection
{
    private \PDO $pdo;

    public function __construct(
        private readonly string $dsn,
        private readonly string $username,
        private readonly string $password,
    ) {
        // ✅ Toda inicialização crítica no constructor — objeto válido ou não existe
        try {
            $this->pdo = new \PDO(
                dsn:      $this->dsn,
                username: $this->username,
                password: $this->password,
                options:  [
                    \PDO::ATTR_ERRMODE            => \PDO::ERRMODE_EXCEPTION,
                    \PDO::ATTR_DEFAULT_FETCH_MODE => \PDO::FETCH_ASSOC,
                    \PDO::ATTR_EMULATE_PREPARES   => false,
                ],
            );
        } catch (\PDOException $e) {
            throw new \RuntimeException(
                message:  'Falha ao conectar ao banco de dados.',
                code:     0,
                previous: $e, // Encadeia a exceção original
            );
        }
    }

    public function getConnection(): \PDO
    {
        return $this->pdo;
    }
}
```

### Constructor Property Promotion — forma moderna e concisa

```php
<?php

declare(strict_types=1);

// ❌ LEGACY CODE — PHP < 8.0: declaração verbosa e redundante
class FruitLegacy
{
    public string $name;
    public string $color;
    public float  $weight;

    public function __construct(string $name, string $color, float $weight)
    {
        $this->name   = $name;
        $this->color  = $color;
        $this->weight = $weight;
    }
}

// ✅ MODERNO PHP 8.0+: Constructor Property Promotion — elimina toda a redundância
final class Fruit
{
    public function __construct(
        public readonly string $name,
        public readonly string $color,
        public readonly float  $weight,
    ) {
        // Validação aqui é opcional mas recomendada
        if ($weight <= 0.0) {
            throw new \InvalidArgumentException('Peso deve ser positivo.');
        }
    }

    public function describe(): string
    {
        return "{$this->name} ({$this->color}), {$this->weight}g";
    }
}

$apple  = new Fruit(name: 'Apple',  color: 'Red',    weight: 182.0);
$banana = new Fruit(name: 'Banana', color: 'Yellow', weight: 120.0);

echo $apple->describe();  // Apple (Red), 182g
echo $banana->describe(); // Banana (Yellow), 120g
```

### __destruct() — limpeza de recursos

```php
<?php

declare(strict_types=1);

/**
 * Gerenciador de arquivo — abre no constructor, fecha no destructor.
 * Garante que o arquivo sempre seja fechado, mesmo com exceção.
 */
final class FileManager
{
    /** @var resource */
    private mixed $handle;

    public function __construct(private readonly string $filePath)
    {
        $this->handle = fopen($filePath, 'r');

        if ($this->handle === false) {
            throw new \RuntimeException("Não foi possível abrir: {$filePath}");
        }
    }

    public function readLine(): string|false
    {
        return fgets($this->handle);
    }

    /**
     * Chamado automaticamente quando o objeto é destruído ou o script termina.
     * ✅ Ideal para liberar recursos: arquivos, conexões, locks.
     */
    public function __destruct()
    {
        if (is_resource($this->handle)) {
            fclose($this->handle);
            // Recurso liberado automaticamente — sem necessidade de fclose() manual
        }
    }
}

// O arquivo é aberto no constructor e fechado automaticamente no destructor
$file = new FileManager(__DIR__ . '/data.txt');
echo $file->readLine();
// $file sai de escopo aqui → __destruct() é chamado → arquivo fechado

// ⚠️ __destruct() NÃO deve lançar exceções — pode causar comportamentos inesperados
```

---

## 57. Modificadores de Acesso

Os modificadores de acesso controlam **de onde** uma propriedade ou método pode ser acessado.
São fundamentais para o princípio de **encapsulamento**.

```
public    → acessível de qualquer lugar
protected → acessível na própria classe e em subclasses (herança)
private   → acessível APENAS na própria classe
```

### Exemplo completo dos três níveis

```php
<?php

declare(strict_types=1);

class BankAccount
{
    private float  $balance;       // Apenas esta classe pode ler/modificar
    protected int  $ownerId;       // Esta classe e subclasses
    public string  $currency;      // Todos podem acessar

    public function __construct(int $ownerId, float $initialBalance, string $currency = 'BRL')
    {
        $this->ownerId = $ownerId;
        $this->balance = $initialBalance;
        $this->currency = $currency;
    }

    // ✅ Acesso controlado ao balance via método público
    public function getBalance(): float
    {
        return $this->balance;
    }

    public function deposit(float $amount): void
    {
        if ($amount <= 0.0) {
            throw new \InvalidArgumentException('Valor de depósito deve ser positivo.');
        }

        $this->balance += $amount; // ✅ Modifica $balance internamente
    }

    public function withdraw(float $amount): void
    {
        if ($amount <= 0.0) {
            throw new \InvalidArgumentException('Valor de saque deve ser positivo.');
        }

        if ($amount > $this->balance) {
            throw new \RuntimeException('Saldo insuficiente.');
        }

        $this->balance -= $amount;
    }

    // Método privado — lógica interna, não exposta
    private function applyInterest(float $rate): void
    {
        $this->balance *= (1 + $rate);
    }
}

$account = new BankAccount(ownerId: 1, initialBalance: 1000.0);

// ✅ Acesso público
echo $account->currency;       // BRL
echo $account->getBalance();   // 1000.0

$account->deposit(500.0);
echo $account->getBalance();   // 1500.0

$account->withdraw(200.0);
echo $account->getBalance();   // 1300.0

// ❌ Erro — $balance é private
// echo $account->balance; // Fatal error: Cannot access private property

// ❌ Erro — applyInterest() é private
// $account->applyInterest(0.05); // Fatal error
```

### Asymmetric Visibility (PHP 8.4+)

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.4+: visibilidade assimétrica — leitura pública, escrita privada
final class UserProfile
{
    public private(set) string $displayName; // Qualquer um lê; apenas a classe escreve
    public protected(set) int  $loginCount;  // Qualquer um lê; a classe e subclasses escrevem

    public function __construct(string $displayName)
    {
        $this->displayName = $displayName;
        $this->loginCount  = 0;
    }

    public function recordLogin(): void
    {
        $this->loginCount++; // ✅ Classe pode modificar
    }
}

$profile = new UserProfile('Ana Silva');
echo $profile->displayName; // ✅ Leitura pública

// $profile->displayName = 'Outro'; // ❌ Erro — escrita é private
$profile->recordLogin();
echo $profile->loginCount;  // 1
```

---

## 58. Herança (Inheritance)

Herança permite que uma **classe filha** (child) herde propriedades e métodos de uma
**classe pai** (parent), adicionando ou sobrescrevendo comportamentos.

### extends — herdando de uma classe pai

```php
<?php

declare(strict_types=1);

// Classe pai — define comportamento base
class Vehicle
{
    public function __construct(
        public readonly string $brand,
        public readonly string $model,
        public readonly int    $year,
    ) {}

    public function describe(): string
    {
        return "{$this->year} {$this->brand} {$this->model}";
    }

    // protected — acessível na própria classe e subclasses
    protected function formatSpeed(int $kmh): string
    {
        return "{$kmh} km/h";
    }
}

// Classe filha — herda tudo de Vehicle e adiciona comportamento próprio
class ElectricCar extends Vehicle
{
    public function __construct(
        string $brand,
        string $model,
        int    $year,
        private readonly int $rangeKm, // Propriedade exclusiva da subclasse
    ) {
        // ✅ parent::__construct() chama o constructor da classe pai
        parent::__construct(brand: $brand, model: $model, year: $year);
    }

    // Sobrescreve (override) o método da classe pai com comportamento específico
    public function describe(): string
    {
        // Chama a implementação do pai e adiciona mais informação
        return parent::describe() . " | Elétrico | Autonomia: {$this->rangeKm} km";
    }

    public function charge(int $hours): string
    {
        $rangeAdded = $hours * 50; // 50 km por hora de carga
        return "Após {$hours}h de carga: +" . $this->formatSpeed($rangeAdded);
        // ✅ Acessa método protected do pai
    }
}

class GasCar extends Vehicle
{
    public function __construct(
        string $brand,
        string $model,
        int    $year,
        private readonly float $fuelConsumptionKpl, // km por litro
    ) {
        parent::__construct(brand: $brand, model: $model, year: $year);
    }

    public function describe(): string
    {
        return parent::describe() . " | Combustão | {$this->fuelConsumptionKpl} km/L";
    }
}

$tesla  = new ElectricCar(brand: 'Tesla',   model: 'Model 3', year: 2024, rangeKm: 500);
$toyota = new GasCar(brand: 'Toyota', model: 'Corolla', year: 2025, fuelConsumptionKpl: 13.5);

echo $tesla->describe();  // 2024 Tesla Model 3 | Elétrico | Autonomia: 500 km
echo $toyota->describe(); // 2025 Toyota Corolla | Combustão | 13.5 km/L
echo $tesla->charge(3);   // Após 3h de carga: +150 km/h

// instanceof verifica a hierarquia completa
var_dump($tesla instanceof ElectricCar); // bool(true)
var_dump($tesla instanceof Vehicle);     // bool(true) — herança!
var_dump($tesla instanceof GasCar);      // bool(false)
```

### #[\Override] — marcando sobrescritas explicitamente (PHP 8.3+)

```php
<?php

declare(strict_types=1);

class BaseLogger
{
    public function log(string $message): void
    {
        echo "[LOG] {$message}";
    }
}

class FileLogger extends BaseLogger
{
    // ✅ #[\Override] — PHP verifica em tempo de análise que este método
    //    realmente sobrescreve um método do pai. Protege contra typos.
    #[\Override]
    public function log(string $message): void
    {
        file_put_contents('/var/log/app.log', $message . PHP_EOL, FILE_APPEND);
    }
}
```

### final — prevenindo herança e override

```php
<?php

declare(strict_types=1);

// final class — não pode ser estendida
final class Singleton
{
    private static ?self $instance = null;

    private function __construct() {}

    public static function getInstance(): self
    {
        return self::$instance ??= new self();
    }
}

// class AnotherClass extends Singleton {} // ❌ Fatal error

// final method — pode ser herdado mas não sobrescrito
class PaymentProcessor
{
    // Método crítico de segurança — não pode ser sobrescrito por subclasses
    final public function validateAmount(float $amount): bool
    {
        return $amount > 0.0 && $amount <= 1_000_000.0;
    }

    public function process(float $amount): void
    {
        if (!$this->validateAmount($amount)) {
            throw new \InvalidArgumentException('Valor inválido.');
        }
        // Processa pagamento...
    }
}

class CreditCardProcessor extends PaymentProcessor
{
    // ❌ Tentativa de sobrescrever método final gera Fatal error
    // public function validateAmount(float $amount): bool { ... }

    // ✅ Pode sobrescrever outros métodos não-final
    public function process(float $amount): void
    {
        // Lógica específica de cartão de crédito
        parent::process($amount);
    }
}
```

---

## 59. Constantes de Classe

Constantes de classe são valores fixos associados à classe — não à instância.
São acessadas via operador `::` e não mudam após definição.

### Definindo e acessando constantes

```php
<?php

declare(strict_types=1);

final class HttpStatus
{
    // ✅ Constantes de classe — UPPER_SNAKE_CASE por convenção
    const int OK                  = 200;
    const int CREATED             = 201;
    const int NO_CONTENT          = 204;
    const int BAD_REQUEST         = 400;
    const int UNAUTHORIZED        = 401;
    const int FORBIDDEN           = 403;
    const int NOT_FOUND           = 404;
    const int UNPROCESSABLE       = 422;
    const int INTERNAL_ERROR      = 500;

    // ✅ PHP 8.3+: typed class constants
    const string DEFAULT_MESSAGE  = 'OK';
}

// Acesso de fora da classe: ClassName::CONSTANT
echo HttpStatus::OK;           // 200
echo HttpStatus::NOT_FOUND;    // 404
echo HttpStatus::DEFAULT_MESSAGE; // OK

// ✅ Constante de classe com valor de array
final class Config
{
    const array ALLOWED_METHODS = ['GET', 'POST', 'PUT', 'PATCH', 'DELETE'];
    const array SUPPORTED_TYPES = ['json', 'xml', 'csv'];
}

echo Config::ALLOWED_METHODS[0]; // GET

// Acesso de dentro da classe com self::
final class MathConstants
{
    const float PI    = 3.14159265358979;
    const float E     = 2.71828182845905;
    const float SQRT2 = 1.41421356237310;

    public static function circleArea(float $radius): float
    {
        return self::PI * $radius ** 2; // Acessa PI com self::
    }
}

echo MathConstants::circleArea(5.0); // 78.539816...
echo MathConstants::PI;               // 3.14159...
```

### Constantes em herança — static:: vs self::

```php
<?php

declare(strict_types=1);

class BaseModel
{
    // ✅ Constantes podem ser sobrescritas em subclasses
    const string TABLE = 'base';

    public static function getTable(): string
    {
        // self:: → sempre retorna a constante da classe onde está definido
        // static:: → late static binding — retorna a constante da classe chamada
        return static::TABLE; // ✅ Use static:: para comportamento polimórfico
    }
}

class UserModel extends BaseModel
{
    const string TABLE = 'users'; // Sobrescreve a constante da classe pai
}

class ProductModel extends BaseModel
{
    const string TABLE = 'products';
}

echo BaseModel::getTable();    // base
echo UserModel::getTable();    // users   (late static binding com static::)
echo ProductModel::getTable(); // products
```

### Constantes de interface — contrato de valores

```php
<?php

declare(strict_types=1);

// Interfaces também podem ter constantes
interface Colorable
{
    const string RED   = '#FF0000';
    const string GREEN = '#00FF00';
    const string BLUE  = '#0000FF';
}

final class Button implements Colorable
{
    public function __construct(
        private readonly string $label,
        private readonly string $color = self::BLUE, // Acessa a constante da interface
    ) {}

    public function render(): string
    {
        return "<button style='background:{$this->color}'>{$this->label}</button>";
    }
}

// ✅ Acesso via interface ou via classe implementadora
echo Colorable::RED;  // #FF0000
echo Button::RED;     // #FF0000

$btn = new Button(label: 'Enviar', color: Colorable::GREEN);
echo $btn->render();
```

### ✅ Enum como alternativa superior a constantes agrupadas (PHP 8.1+)

```php
<?php

declare(strict_types=1);

// ❌ LEGACY CODE — PHP < 8.1: constantes agrupadas sem tipo
// class Status {
//     const ACTIVE   = 'active';
//     const INACTIVE = 'inactive';
//     const PENDING  = 'pending';
// }

// ✅ MODERNO PHP 8.1+: Enum — tipado, com métodos e casos verificados em compilação
enum UserStatus: string
{
    case Active   = 'active';
    case Inactive = 'inactive';
    case Pending  = 'pending';

    public function label(): string
    {
        return match($this) {
            self::Active   => 'Ativo',
            self::Inactive => 'Inativo',
            self::Pending  => 'Pendente',
        };
    }

    public function canLogin(): bool
    {
        return $this === self::Active;
    }
}

$status = UserStatus::Active;
echo $status->value;      // active
echo $status->label();    // Ativo
echo $status->name;       // Active
var_dump($status->canLogin()); // bool(true)

// Criando a partir de string (útil ao ler do banco)
$fromDb = UserStatus::from('pending');   // Lança ValueError se não encontrar
$tryDb  = UserStatus::tryFrom('unknown'); // Retorna null se não encontrar
var_dump($tryDb); // NULL
```

---

## 60. Classes Abstratas

Uma **classe abstrata** é um molde que **não pode ser instanciado diretamente** — existe
apenas para ser estendida. Ela pode conter métodos abstratos (sem implementação) que
forçam as classes filhas a fornecer sua própria implementação.

### Quando usar classe abstrata vs interface

| | Classe abstrata | Interface |
|-|-----------------|-----------|
| Pode ter propriedades | ✅ Sim | ❌ Não (PHP < 8.4) |
| Pode ter métodos concretos | ✅ Sim | ❌ Não |
| Modificadores de acesso | `public`, `protected`, `private` | Apenas `public` |
| Uma classe pode usar quantas | Apenas 1 (herança simples) | Múltiplas (`implements A, B`) |
| Instanciável diretamente | ❌ Não | ❌ Não |

### Definindo e estendendo classe abstrata

```php
<?php

declare(strict_types=1);

/**
 * Classe abstrata: define contrato + comportamento base para veículos.
 * Não pode ser instanciada — serve de base para subclasses concretas.
 */
abstract class Vehicle
{
    // Propriedades concretas — disponíveis para todas as subclasses
    public function __construct(
        protected readonly string $brand,
        protected readonly string $model,
        protected readonly int    $year,
    ) {}

    // Método concreto — implementação compartilhada
    public function getInfo(): string
    {
        return "{$this->year} {$this->brand} {$this->model}";
    }

    // ✅ Método abstrato — cada subclasse DEVE implementar à sua maneira
    abstract public function getFuelType(): string;

    // Método abstrato com parâmetro
    abstract public function calculateRange(float $fuelAmount): float;

    // Template method — usa métodos abstratos internamente
    final public function describe(): string
    {
        $range = $this->calculateRange(50.0);

        return sprintf(
            '%s | Combustível: %s | Autonomia c/ 50L: %.0f km',
            $this->getInfo(),
            $this->getFuelType(),
            $range,
        );
    }
}

// Subclasse concreta — implementa todos os métodos abstratos
final class GasolineCar extends Vehicle
{
    // Modificador da subclasse pode ser igual ou MENOS restritivo que o da classe abstrata
    public function getFuelType(): string
    {
        return 'Gasolina';
    }

    public function calculateRange(float $fuelAmount): float
    {
        return $fuelAmount * 12.5; // 12.5 km/L
    }
}

final class ElectricCar extends Vehicle
{
    public function __construct(
        string $brand,
        string $model,
        int    $year,
        private readonly float $kwh, // Capacidade da bateria em kWh
    ) {
        parent::__construct(brand: $brand, model: $model, year: $year);
    }

    public function getFuelType(): string
    {
        return 'Elétrico';
    }

    // Subclasse pode ter parâmetros opcionais além dos da classe abstrata
    public function calculateRange(float $fuelAmount, float $efficiency = 6.0): float
    {
        // Para elétrico: fuelAmount representa kWh carregados; efficiency = km/kWh
        return $fuelAmount * $efficiency;
    }
}

// ❌ Não é possível instanciar a classe abstrata
// $v = new Vehicle('X', 'Y', 2025); // Fatal error: Cannot instantiate abstract class

$corolla  = new GasolineCar(brand: 'Toyota', model: 'Corolla', year: 2025);
$model3   = new ElectricCar(brand: 'Tesla',  model: 'Model 3', year: 2024, kwh: 75.0);

echo $corolla->describe();
// 2025 Toyota Corolla | Combustível: Gasolina | Autonomia c/ 50L: 625 km

echo $model3->describe();
// 2024 Tesla Model 3 | Combustível: Elétrico | Autonomia c/ 50L: 300 km
```

### Regras fundamentais de classes abstratas

```php
<?php

declare(strict_types=1);

abstract class Shape
{
    // ✅ Método abstrato protected — subclasse pode implementar como protected OU public
    abstract protected function computeArea(): float;

    // Método público que usa o método abstrato (Template Method Pattern)
    public function getArea(): string
    {
        return number_format($this->computeArea(), 2, ',', '.') . ' cm²';
    }
}

final class Circle extends Shape
{
    public function __construct(private readonly float $radius) {}

    // ✅ Implementa como public (menos restritivo que protected — permitido)
    public function computeArea(): float
    {
        return M_PI * $this->radius ** 2;
    }
}

final class Rectangle extends Shape
{
    public function __construct(
        private readonly float $width,
        private readonly float $height,
    ) {}

    public function computeArea(): float
    {
        return $this->width * $this->height;
    }
}

$shapes = [
    new Circle(radius: 5.0),
    new Rectangle(width: 4.0, height: 6.0),
];

foreach ($shapes as $shape) {
    echo get_class($shape) . ': ' . $shape->getArea();
}
// Circle: 78,54 cm²
// Rectangle: 24,00 cm²
```

---

## 61. Interfaces

Uma **interface** define um **contrato** — uma lista de métodos que a classe implementadora
**obrigatoriamente** deve ter. Diferente de herança, uma classe pode implementar
**múltiplas interfaces** simultaneamente.

### Definindo e implementando interfaces

```php
<?php

declare(strict_types=1);

// ✅ Interfaces definem o "o quê", não o "como"
interface Printable
{
    public function toString(): string;
}

interface Serializable
{
    public function serialize(): string;
    public function unserialize(string $data): void;
}

interface Loggable
{
    public function getLogEntry(): string;
}

// Uma classe pode implementar múltiplas interfaces
final class Order implements Printable, Loggable
{
    private string $status = 'pending';

    public function __construct(
        private readonly int    $id,
        private readonly string $customerName,
        private readonly float  $total,
    ) {}

    // ✅ Deve implementar TODOS os métodos de TODAS as interfaces
    public function toString(): string
    {
        return "Pedido #{$this->id} — {$this->customerName} — R$ " .
            number_format($this->total, 2, ',', '.');
    }

    public function getLogEntry(): string
    {
        return sprintf(
            '[%s] Order #%d | customer=%s | total=%.2f | status=%s',
            date('Y-m-d H:i:s'),
            $this->id,
            $this->customerName,
            $this->total,
            $this->status,
        );
    }

    public function confirm(): void
    {
        $this->status = 'confirmed';
    }
}

$order = new Order(id: 42, customerName: 'Ana Silva', total: 350.90);
echo $order->toString();    // Pedido #42 — Ana Silva — R$ 350,90
echo $order->getLogEntry(); // [2025-04-08 14:30:00] Order #42 | customer=Ana Silva | ...

// instanceof funciona para interfaces também
var_dump($order instanceof Printable); // bool(true)
var_dump($order instanceof Loggable);  // bool(true)
```

### Polimorfismo com interfaces

```php
<?php

declare(strict_types=1);

// Interface como tipo — qualquer classe que implemente pode ser usada
interface PaymentMethod
{
    public function charge(float $amount): bool;
    public function getLabel(): string;
}

final class CreditCard implements PaymentMethod
{
    public function __construct(
        private readonly string $lastFour,
        private readonly string $brand,
    ) {}

    public function charge(float $amount): bool
    {
        // Integração com gateway de cartão...
        echo "Cobrando R$ {$amount} no {$this->brand} *{$this->lastFour}";
        return true;
    }

    public function getLabel(): string
    {
        return "{$this->brand} terminando em {$this->lastFour}";
    }
}

final class Pix implements PaymentMethod
{
    public function __construct(private readonly string $key) {}

    public function charge(float $amount): bool
    {
        echo "Gerando QR Code PIX de R$ {$amount} para chave {$this->key}";
        return true;
    }

    public function getLabel(): string
    {
        return "PIX ({$this->key})";
    }
}

// ✅ Polimorfismo: a função aceita QUALQUER PaymentMethod
function processPayment(PaymentMethod $method, float $amount): void
{
    echo "Forma de pagamento: " . $method->getLabel();

    if (!$method->charge($amount)) {
        throw new \RuntimeException('Falha no pagamento.');
    }

    echo "Pagamento de R$ {$amount} confirmado!";
}

// Mesma função, comportamentos diferentes
processPayment(new CreditCard(lastFour: '4242', brand: 'Visa'), 350.90);
processPayment(new Pix(key: 'ana@example.com'), 89.90);
```

### Interface vs Classe Abstrata — quando usar cada um

```
Use INTERFACE quando:
✅ Definir apenas contrato (sem estado, sem implementação)
✅ Precisar de múltipla implementação (uma classe, várias interfaces)
✅ Definir comportamento transversal (Loggable, Serializable, Comparable)

Use CLASSE ABSTRATA quando:
✅ Compartilhar estado (propriedades) entre subclasses
✅ Fornecer implementação base parcial (Template Method Pattern)
✅ Existir uma relação "é um tipo de" clara (Vehicle → Car)
```

---

## 62. Traits

**Traits** são mecanismos de reuso de código para classes — permitem compartilhar
métodos entre classes que não têm relação de herança. Funcionam como um "copiar e colar"
controlado pelo PHP.

> 💡 Use traits para comportamentos transversais: logging, timestamps, serialização, etc.

### Definindo e usando um trait

```php
<?php

declare(strict_types=1);

// Trait: comportamento de timestamp (created_at / updated_at)
trait HasTimestamps
{
    private \DateTimeImmutable $createdAt;
    private \DateTimeImmutable $updatedAt;

    public function initTimestamps(): void
    {
        $this->createdAt = new \DateTimeImmutable();
        $this->updatedAt = new \DateTimeImmutable();
    }

    public function touch(): void
    {
        $this->updatedAt = new \DateTimeImmutable();
    }

    public function getCreatedAt(): \DateTimeImmutable { return $this->createdAt; }
    public function getUpdatedAt(): \DateTimeImmutable { return $this->updatedAt; }
}

// Trait: comportamento de logging
trait Loggable
{
    private array $logs = [];

    public function log(string $level, string $message): void
    {
        $timestamp    = (new \DateTimeImmutable())->format('Y-m-d H:i:s');
        $this->logs[] = "[{$timestamp}] [{$level}] {$message}";
    }

    /** @return string[] */
    public function getLogs(): array
    {
        return $this->logs;
    }
}

// Trait: soft delete
trait SoftDeletable
{
    private ?string $deletedAt = null;

    public function delete(): void
    {
        $this->deletedAt = (new \DateTimeImmutable())->format('Y-m-d H:i:s');
    }

    public function restore(): void
    {
        $this->deletedAt = null;
    }

    public function isDeleted(): bool
    {
        return $this->deletedAt !== null;
    }
}

// ✅ Uma classe pode usar múltiplos traits
final class Post
{
    use HasTimestamps, Loggable, SoftDeletable; // Múltiplos traits separados por vírgula

    public function __construct(
        private readonly int    $id,
        private string          $title,
        private string          $content,
    ) {
        $this->initTimestamps(); // Inicializa o trait HasTimestamps
        $this->log('INFO', "Post #{$id} criado.");
    }

    public function updateTitle(string $newTitle): void
    {
        $this->title = $newTitle;
        $this->touch(); // Atualiza updatedAt via trait
        $this->log('INFO', "Título alterado para: {$newTitle}");
    }
}

$post = new Post(id: 1, title: 'PHP 8.5', content: 'Novidades...');
$post->updateTitle('PHP 8.5 — O que há de novo');
$post->delete();

echo 'Criado: '  . $post->getCreatedAt()->format('d/m/Y H:i:s');
echo 'Deletado: ' . ($post->isDeleted() ? 'Sim' : 'Não');

foreach ($post->getLogs() as $entry) {
    echo $entry;
}
```

### Resolvendo conflitos entre traits

```php
<?php

declare(strict_types=1);

trait TraitA
{
    public function hello(): string
    {
        return 'Olá do TraitA';
    }
}

trait TraitB
{
    public function hello(): string
    {
        return 'Olá do TraitB';
    }
}

class MyClass
{
    use TraitA, TraitB {
        // ✅ Resolve conflito: especifica qual trait "vence"
        TraitA::hello insteadof TraitB;    // TraitA.hello substitui TraitB.hello

        // Mantém a versão do TraitB sob um alias
        TraitB::hello as helloFromB;
    }
}

$obj = new MyClass();
echo $obj->hello();        // Olá do TraitA
echo $obj->helloFromB();   // Olá do TraitB
```

### Trait com método abstrato — força implementação

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.5: #[\Deprecated] pode ser aplicado a traits
trait Validatable
{
    // Método abstrato no trait — força a classe a implementar
    abstract protected function validate(): bool;

    public function saveIfValid(): bool
    {
        if (!$this->validate()) {
            return false;
        }

        $this->persist();
        return true;
    }

    private function persist(): void
    {
        // Lógica de persistência genérica...
    }
}

final class UserForm
{
    use Validatable;

    public function __construct(
        private readonly string $name,
        private readonly string $email,
    ) {}

    // ✅ Obrigatório por causa do abstract no trait
    protected function validate(): bool
    {
        return !empty($this->name) && filter_var($this->email, FILTER_VALIDATE_EMAIL) !== false;
    }
}
```

---

## 63. Métodos Estáticos

Métodos **estáticos** pertencem à **classe** — não a uma instância. São acessados via
`ClassName::method()` sem precisar criar um objeto com `new`.

```php
<?php

declare(strict_types=1);

final class MathHelper
{
    // Constante de classe — acessível via self:: ou MathHelper::
    const float PI = 3.14159265358979;

    // ✅ Método estático — acessado diretamente pela classe
    public static function circleArea(float $radius): float
    {
        return self::PI * $radius ** 2;
    }

    public static function hypotenuse(float $a, float $b): float
    {
        return sqrt($a ** 2 + $b ** 2);
    }

    public static function clamp(float $value, float $min, float $max): float
    {
        return max($min, min($max, $value));
    }
}

// Acesso direto — sem new
echo MathHelper::circleArea(5.0);     // 78.539...
echo MathHelper::hypotenuse(3, 4);    // 5.0
echo MathHelper::clamp(150, 0, 100);  // 100.0
```

### Factory Method — padrão comum com estáticos

```php
<?php

declare(strict_types=1);

final class Money
{
    private function __construct(
        public readonly float  $amount,
        public readonly string $currency,
    ) {}

    // ✅ Factory methods estáticos — nomenclatura clara e semântica
    public static function brl(float $amount): self
    {
        return new self(amount: $amount, currency: 'BRL');
    }

    public static function usd(float $amount): self
    {
        return new self(amount: $amount, currency: 'USD');
    }

    public static function fromString(string $formatted): self
    {
        // Exemplo: "BRL 350.90"
        [$currency, $amount] = explode(' ', $formatted, 2);

        return new self(amount: (float) $amount, currency: $currency);
    }

    public function format(): string
    {
        return "{$this->currency} " . number_format($this->amount, 2, ',', '.');
    }
}

$price    = Money::brl(350.90);
$usdPrice = Money::usd(69.99);
$parsed   = Money::fromString('BRL 1299.00');

echo $price->format();    // BRL 350,90
echo $usdPrice->format(); // USD 69,99
echo $parsed->format();   // BRL 1.299,00
```

### Singleton — padrão com static

```php
<?php

declare(strict_types=1);

/**
 * Singleton: garante que apenas uma instância exista no ciclo de vida da aplicação.
 * Útil para conexões de banco, configurações globais, etc.
 *
 * ⚠️ Use com moderação — dificulta testes. Prefira injeção de dependência.
 */
final class AppConfig
{
    private static ?self $instance = null;

    /** @var array<string, mixed> */
    private array $settings = [];

    private function __construct() {}

    public static function getInstance(): self
    {
        // ✅ Null coalescing assignment — cria apenas se ainda não existe
        return self::$instance ??= new self();
    }

    public function set(string $key, mixed $value): void
    {
        $this->settings[$key] = $value;
    }

    public function get(string $key, mixed $default = null): mixed
    {
        return $this->settings[$key] ?? $default;
    }
}

$config = AppConfig::getInstance();
$config->set('debug', true);
$config->set('version', '8.5.0');

// Mesma instância em qualquer parte do código
$sameConfig = AppConfig::getInstance();
echo $sameConfig->get('version'); // 8.5.0
```

### self:: vs static:: vs parent::

```php
<?php

declare(strict_types=1);

class Base
{
    public static function create(): static // ✅ return type 'static' — retorna o tipo real
    {
        return new static(); // static:: → instancia a classe real (não Base)
    }

    public static function identify(): string
    {
        return 'Sou: ' . static::class; // static::class → classe real (late static binding)
    }
}

class Child extends Base
{
    // Herda create() e identify() — comportamento polimórfico via static::
}

$base  = Base::create();   // Instância de Base
$child = Child::create();  // Instância de Child (não de Base!)

var_dump($base  instanceof Base);  // bool(true)
var_dump($child instanceof Child); // bool(true)

echo Base::identify();   // Sou: Base
echo Child::identify();  // Sou: Child (late static binding!)
```

---

## 64. Propriedades Estáticas

Propriedades **estáticas** pertencem à **classe** e são compartilhadas entre todas as instâncias.
São úteis para contadores, caches compartilhados e registros globais.

```php
<?php

declare(strict_types=1);

class Counter
{
    // ✅ Propriedade estática — compartilhada por TODAS as instâncias
    private static int $count = 0;

    public function __construct()
    {
        self::$count++; // Incrementa o contador de instâncias
    }

    public static function getCount(): int
    {
        return self::$count;
    }

    public static function reset(): void
    {
        self::$count = 0;
    }
}

$a = new Counter();
$b = new Counter();
$c = new Counter();

echo Counter::getCount(); // 3 — compartilhado por todas as instâncias

Counter::reset();
echo Counter::getCount(); // 0
```

### Registry — cache de instâncias com propriedade estática

```php
<?php

declare(strict_types=1);

/**
 * Registry simples de serviços — armazena instâncias por chave.
 * Alternativa leve a um container DI completo.
 */
final class ServiceRegistry
{
    /** @var array<string, object> */
    private static array $services = [];

    public static function register(string $key, object $service): void
    {
        self::$services[$key] = $service;
    }

    public static function get(string $key): object
    {
        return self::$services[$key]
            ?? throw new \RuntimeException("Serviço '{$key}' não registrado.");
    }

    public static function has(string $key): bool
    {
        return isset(self::$services[$key]);
    }
}

// Registrando serviços
ServiceRegistry::register('logger', new class {
    public function info(string $msg): void { echo "[INFO] {$msg}"; }
});

// Recuperando em qualquer parte do código
$logger = ServiceRegistry::get('logger');
$logger->info('Serviço inicializado.');
```

### Asymmetric visibility em propriedades estáticas (PHP 8.4+)

```php
<?php

declare(strict_types=1);

class AppState
{
    // Leitura pública, escrita apenas pela própria classe
    public static private(set) int $requestCount = 0;

    public static function incrementRequest(): void
    {
        self::$requestCount++;
    }
}

AppState::incrementRequest();
AppState::incrementRequest();

echo AppState::$requestCount; // 2 — leitura pública
// AppState::$requestCount = 10; // ❌ Fatal error — escrita é private
```

---

## 65. Namespaces

**Namespaces** organizam o código em grupos lógicos e evitam conflitos de nomes entre
classes, funções e constantes — especialmente em projetos grandes ou ao usar bibliotecas externas.

### Declarando namespaces

```php
<?php

// ✅ namespace deve ser a PRIMEIRA instrução do arquivo (exceto declare)
declare(strict_types=1);

namespace App\Service\Payment;

// Todas as classes/funções/constantes deste arquivo pertencem ao namespace acima
final class PaymentProcessor
{
    public function process(float $amount): bool
    {
        return $amount > 0.0;
    }
}
```

### Estrutura de namespaces — PSR-4

A convenção PSR-4 mapeia namespaces para diretórios de forma 1:1:

```
📂 src/
│
├── 📂 Domain/
│   ├── 📂 User/
│   │   ├── 📄 User.php              → namespace App\Domain\User;
│   │   └── 📄 UserRepository.php   → namespace App\Domain\User;
│   └── 📂 Order/
│       └── 📄 Order.php             → namespace App\Domain\Order;
│
├── 📂 Service/
│   ├── 📄 PaymentService.php        → namespace App\Service;
│   └── 📄 EmailService.php          → namespace App\Service;
│
└── 📂 Infrastructure/
    └── 📄 PdoUserRepository.php     → namespace App\Infrastructure;
```

### Usando classes de outros namespaces

```php
<?php

declare(strict_types=1);

namespace App\Controller;

// ✅ use — importa classes de outros namespaces (sem precisar usar o FQCN completo)
use App\Domain\User\User;
use App\Service\PaymentService;
use App\Service\EmailService;

// Importação com alias — resolve conflitos de nome
use App\Domain\Order\Order as DomainOrder;
use App\DTO\Order as OrderDto;          // Mesmo nome, namespace diferente

// Importação de grupo — namespaces com prefixo comum
use App\Service\{PaymentService, EmailService, NotificationService};

// Importação de funções e constantes
use function App\Helpers\{formatCurrency, formatDate};
use const App\Config\{API_VERSION, MAX_RETRIES};

final class CheckoutController
{
    public function __construct(
        private readonly PaymentService $paymentService,
        private readonly EmailService   $emailService,
    ) {}

    public function checkout(OrderDto $orderDto): void
    {
        // User e PaymentService são usados diretamente após o use
        $user = new User(id: $orderDto->userId, name: $orderDto->userName);

        $this->paymentService->process($orderDto->total);
        $this->emailService->sendConfirmation($user->getEmail());
    }
}
```

### Namespaces aninhados

```php
<?php

declare(strict_types=1);

// Namespaces aninhados com \
namespace App\Infrastructure\Persistence\Mysql;

use App\Domain\User\UserRepository as UserRepositoryInterface;
use App\Domain\User\User;

final class MysqlUserRepository implements UserRepositoryInterface
{
    public function __construct(private readonly \PDO $pdo) {}

    public function findById(int $id): ?User
    {
        $stmt = $this->pdo->prepare('SELECT * FROM users WHERE id = :id');
        $stmt->execute(['id' => $id]);
        $row  = $stmt->fetch();

        if ($row === false) {
            return null;
        }

        return new User(id: (int) $row['id'], name: $row['name']);
    }
}
```

### Funções globais dentro de namespace

```php
<?php

declare(strict_types=1);

namespace App\Utils;

// Dentro de um namespace, funções sem prefixo buscam PRIMEIRO no namespace,
// depois no global. Use \ para forçar o global.

function strlen(string $s): int
{
    return \mb_strlen($s); // Chama a função global mb_strlen com \
}

// Chamada normal dentro do namespace
echo strlen('Olá'); // Usa App\Utils\strlen → mb_strlen('Olá') = 3

// Forçando a função global
echo \strlen('Olá'); // Chama a função strlen global → 4 (bytes, não chars)
```

---

## 66. Iterables e Iterator

**Iterable** é um pseudo-tipo que representa qualquer valor que pode ser percorrido
com `foreach` — seja um array ou um objeto que implemente a interface `Iterator`.

### Usando o tipo iterable

```php
<?php

declare(strict_types=1);

// ✅ iterable aceita arrays OU objetos Iterator — flexível para quem chama a função
function processItems(iterable $items): void
{
    foreach ($items as $key => $item) {
        echo "{$key}: " . htmlspecialchars((string) $item, ENT_QUOTES | ENT_HTML5, 'UTF-8');
    }
}

// Chamada com array
processItems(['maçã', 'banana', 'laranja']);

// Chamada com ArrayIterator
$iterator = new \ArrayIterator(['PHP', 'Python', 'Go']);
processItems($iterator);

// Função que retorna iterable
function generateRange(int $start, int $end): iterable
{
    // Pode retornar array...
    if (($end - $start) < 100) {
        return range($start, $end);
    }

    // ...ou um Generator (também é iterable)
    return (function() use ($start, $end) {
        for ($i = $start; $i <= $end; $i++) {
            yield $i;
        }
    })();
}
```

### Implementando a interface Iterator

```php
<?php

declare(strict_types=1);

/**
 * Iterator que lê um arquivo CSV linha por linha.
 * Carrega apenas uma linha por vez — eficiente para arquivos grandes.
 *
 * @implements \Iterator<int, array<string, string>>
 */
final class CsvIterator implements \Iterator
{
    /** @var resource|false */
    private mixed $fileHandle = false;
    private int   $currentLine = 0;
    private array $currentRow  = [];
    private array $headers     = [];

    public function __construct(private readonly string $filePath) {}

    // Abre o arquivo e lê o cabeçalho
    public function rewind(): void
    {
        if (is_resource($this->fileHandle)) {
            fclose($this->fileHandle);
        }

        $this->fileHandle  = fopen($this->filePath, 'r');
        $this->currentLine = 0;

        if ($this->fileHandle === false) {
            throw new \RuntimeException("Não foi possível abrir: {$this->filePath}");
        }

        // Lê a primeira linha como cabeçalho
        $this->headers = fgetcsv($this->fileHandle, separator: ',') ?: [];
        $this->next();
    }

    // Retorna o elemento atual
    public function current(): array
    {
        return $this->currentRow;
    }

    // Retorna a chave atual (índice da linha)
    public function key(): int
    {
        return $this->currentLine;
    }

    // Avança para o próximo elemento
    public function next(): void
    {
        $row = fgetcsv($this->fileHandle, separator: ',');

        if ($row === false) {
            $this->currentRow = [];
            return;
        }

        // Combina cabeçalhos com valores da linha
        $this->currentRow = array_combine($this->headers, $row);
        $this->currentLine++;
    }

    // Verifica se o elemento atual é válido
    public function valid(): bool
    {
        return !empty($this->currentRow);
    }

    public function __destruct()
    {
        if (is_resource($this->fileHandle)) {
            fclose($this->fileHandle);
        }
    }
}

// Uso — percorre o CSV sem carregar tudo na memória
$csv = new CsvIterator(__DIR__ . '/data/usuarios.csv');

foreach ($csv as $lineNumber => $row) {
    $name  = htmlspecialchars($row['name']  ?? '', ENT_QUOTES | ENT_HTML5, 'UTF-8');
    $email = htmlspecialchars($row['email'] ?? '', ENT_QUOTES | ENT_HTML5, 'UTF-8');
    echo "#{$lineNumber} {$name} <{$email}>";
}
```

### Generators — iterables preguiçosos (lazy)

```php
<?php

declare(strict_types=1);

/**
 * Generator: função que produz valores sob demanda com yield.
 * Usa memória constante — não carrega tudo de uma vez.
 *
 * @return \Generator<int, int, void, void>
 */
function fibonacci(): \Generator
{
    [$a, $b] = [0, 1];

    while (true) {
        yield $a;
        [$a, $b] = [$b, $a + $b];
    }
}

// ✅ Gera apenas os valores necessários — sequência infinita segura
$fib = fibonacci();

for ($i = 0; $i < 10; $i++) {
    echo $fib->current() . ' ';
    $fib->next();
}
// 0 1 1 2 3 5 8 13 21 34

// Generator com yield de array — lazy reading de arquivo grande
function readLargeFile(string $path): \Generator
{
    $handle = fopen($path, 'r');

    if ($handle === false) {
        throw new \RuntimeException("Arquivo não encontrado: {$path}");
    }

    try {
        while (!feof($handle)) {
            yield fgets($handle);
        }
    } finally {
        fclose($handle);
    }
}

// Processa linha a linha — memória constante, independente do tamanho do arquivo
foreach (readLargeFile(__DIR__ . '/big-log.txt') as $line) {
    // Processa uma linha por vez
    if (str_contains($line, 'ERROR')) {
        echo htmlspecialchars(trim($line), ENT_QUOTES | ENT_HTML5, 'UTF-8');
    }
}
```

---

## 67. PHP e MySQL — Introdução

**MySQL** é o banco de dados relacional mais usado com PHP. A forma correta e segura
de interagir com MySQL em PHP moderno é via **PDO** (PHP Data Objects) — uma interface
orientada a objetos que suporta múltiplos bancos de dados.

> ⚠️ **Nunca use as extensões `mysql_*`** — foram removidas no PHP 7.0.
> Use sempre **PDO** (recomendado) ou **MySQLi**.

### Conceitos fundamentais de banco de dados

```
Banco de dados → coleção de tabelas
Tabela         → linhas (registros) e colunas (campos)
SQL            → linguagem para consultar e manipular dados

Operações CRUD:
CREATE → INSERT INTO
READ   → SELECT
UPDATE → UPDATE SET
DELETE → DELETE FROM
```

### Conectando ao MySQL com PDO

```php
<?php

declare(strict_types=1);

/**
 * Cria e retorna uma conexão PDO configurada de forma segura.
 *
 * @throws \RuntimeException Se a conexão falhar
 */
function createConnection(
    string $host     = 'localhost',
    string $dbName   = 'my_app',
    string $username = 'root',
    string $password = '',
    int    $port     = 3306,
): \PDO {
    // DSN — Data Source Name
    $dsn = "mysql:host={$host};port={$port};dbname={$dbName};charset=utf8mb4";

    try {
        $pdo = new \PDO(
            dsn:      $dsn,
            username: $username,
            password: $password,
            options:  [
                // ✅ Erros como exceções — nunca silencioso
                \PDO::ATTR_ERRMODE            => \PDO::ERRMODE_EXCEPTION,
                // ✅ Retorna registros como array associativo por padrão
                \PDO::ATTR_DEFAULT_FETCH_MODE => \PDO::FETCH_ASSOC,
                // ✅ Desativa emulação de prepared statements — mais seguro
                \PDO::ATTR_EMULATE_PREPARES   => false,
                // ✅ Persistent connection — reutiliza conexões (produção)
                // \PDO::ATTR_PERSISTENT => true,
            ],
        );

        return $pdo;
    } catch (\PDOException $e) {
        // ⚠️ Log internamente — nunca exponha credenciais ou detalhes ao usuário
        error_log('DB connection failed: ' . $e->getMessage());

        throw new \RuntimeException(
            message:  'Falha ao conectar ao banco de dados. Tente novamente mais tarde.',
            code:     500,
            previous: $e,
        );
    }
}

// Uso
$pdo = createConnection(
    host:     'localhost',
    dbName:   'minha_loja',
    username: 'app_user',
    password: 'senha_segura',
);
```

### SELECT — lendo dados com Prepared Statements

```php
<?php

declare(strict_types=1);

// ✅ SEMPRE use Prepared Statements — previne SQL Injection
// NUNCA concatene variáveis em queries SQL!

// Buscar todos os usuários ativos
$stmt = $pdo->prepare('SELECT id, name, email, created_at FROM users WHERE active = :active ORDER BY name');
$stmt->execute(['active' => 1]);

$users = $stmt->fetchAll(); // Retorna todos os registros como array de arrays associativos

foreach ($users as $user) {
    $id    = (int)    $user['id'];
    $name  = htmlspecialchars((string) $user['name'],  ENT_QUOTES | ENT_HTML5, 'UTF-8');
    $email = htmlspecialchars((string) $user['email'], ENT_QUOTES | ENT_HTML5, 'UTF-8');

    echo "#{$id} {$name} <{$email}>";
}

// Buscar um único registro
$userId = 42;
$stmt   = $pdo->prepare('SELECT * FROM users WHERE id = :id LIMIT 1');
$stmt->execute(['id' => $userId]);

$user = $stmt->fetch(); // fetch() retorna um registro ou false

if ($user === false) {
    echo 'Usuário não encontrado.';
} else {
    echo $user['name'];
}
```

### INSERT — inserindo dados

```php
<?php

declare(strict_types=1);

function createUser(\PDO $pdo, string $name, string $email, string $password): int
{
    // ✅ Hash de senha com Argon2id — NUNCA armazene em texto plano
    $hashedPassword = password_hash($password, PASSWORD_ARGON2ID, [
        'memory_cost' => 65536,
        'time_cost'   => 4,
        'threads'     => 3,
    ]);

    $stmt = $pdo->prepare(
        'INSERT INTO users (name, email, password, created_at)
         VALUES (:name, :email, :password, NOW())'
    );

    $stmt->execute([
        'name'     => $name,
        'email'    => $email,
        'password' => $hashedPassword,
    ]);

    // Retorna o ID do registro inserido
    return (int) $pdo->lastInsertId();
}

try {
    $newUserId = createUser($pdo, 'Ana Silva', 'ana@example.com', 'senha_super_segura_123!');
    echo "Usuário criado com ID: {$newUserId}";
} catch (\PDOException $e) {
    // Erro de duplicidade (email único)
    if ($e->getCode() === '23000') {
        echo 'E-mail já cadastrado.';
    } else {
        error_log('DB insert error: ' . $e->getMessage());
        echo 'Erro ao criar usuário.';
    }
}
```

### UPDATE e DELETE

```php
<?php

declare(strict_types=1);

// ✅ UPDATE — atualiza registro específico
function updateUserEmail(\PDO $pdo, int $userId, string $newEmail): bool
{
    $validEmail = filter_var($newEmail, FILTER_VALIDATE_EMAIL);

    if ($validEmail === false) {
        throw new \InvalidArgumentException('E-mail inválido.');
    }

    $stmt = $pdo->prepare(
        'UPDATE users SET email = :email, updated_at = NOW() WHERE id = :id'
    );

    $stmt->execute(['email' => $validEmail, 'id' => $userId]);

    // rowCount() retorna o número de linhas afetadas
    return $stmt->rowCount() > 0;
}

// ✅ DELETE — remove registro
function deleteUser(\PDO $pdo, int $userId): bool
{
    $stmt = $pdo->prepare('DELETE FROM users WHERE id = :id');
    $stmt->execute(['id' => $userId]);

    return $stmt->rowCount() > 0;
}

// ✅ Soft delete — preferível ao DELETE real
function softDeleteUser(\PDO $pdo, int $userId): bool
{
    $stmt = $pdo->prepare(
        'UPDATE users SET deleted_at = NOW() WHERE id = :id AND deleted_at IS NULL'
    );
    $stmt->execute(['id' => $userId]);

    return $stmt->rowCount() > 0;
}
```

### Transações — operações atômicas

```php
<?php

declare(strict_types=1);

/**
 * Transfere saldo entre duas contas de forma atômica.
 * Se qualquer operação falhar, TUDO é revertido.
 */
function transferFunds(\PDO $pdo, int $fromId, int $toId, float $amount): void
{
    if ($amount <= 0.0) {
        throw new \InvalidArgumentException('Valor de transferência deve ser positivo.');
    }

    $pdo->beginTransaction(); // Inicia a transação

    try {
        // Debita a conta de origem
        $debit = $pdo->prepare(
            'UPDATE accounts SET balance = balance - :amount
             WHERE id = :id AND balance >= :amount'
        );
        $debit->execute(['amount' => $amount, 'id' => $fromId]);

        if ($debit->rowCount() === 0) {
            throw new \RuntimeException('Saldo insuficiente na conta de origem.');
        }

        // Credita a conta de destino
        $credit = $pdo->prepare(
            'UPDATE accounts SET balance = balance + :amount WHERE id = :id'
        );
        $credit->execute(['amount' => $amount, 'id' => $toId]);

        if ($credit->rowCount() === 0) {
            throw new \RuntimeException('Conta de destino não encontrada.');
        }

        $pdo->commit(); // ✅ Confirma TODAS as operações
        echo "Transferência de R$ {$amount} realizada com sucesso.";

    } catch (\Throwable $e) {
        $pdo->rollBack(); // ❌ Reverte TUDO em caso de erro
        error_log('Transfer failed: ' . $e->getMessage());
        throw new \RuntimeException('Falha na transferência: ' . $e->getMessage(), previous: $e);
    }
}
```

### Regras de ouro para banco de dados com PHP

| Regra | Razão |
|-------|-------|
| ✅ Use sempre Prepared Statements | Previne SQL Injection |
| ✅ PDO com `ERRMODE_EXCEPTION` | Erros como exceções, não silenciosos |
| ✅ `ATTR_EMULATE_PREPARES => false` | Statements reais, não emulados |
| ✅ `password_hash()` para senhas | Nunca armazene senhas em texto plano |
| ✅ Use transações para operações múltiplas | Garante atomicidade |
| ✅ `rowCount()` para verificar UPDATE/DELETE | Confirma que o registro foi afetado |
| ✅ `lastInsertId()` após INSERT | Obtém o ID gerado automaticamente |
| ❌ Nunca concatene variáveis em SQL | `"SELECT * WHERE id = {$id}"` → SQL Injection |
| ❌ Nunca exponha erros de DB ao usuário | Log interno, mensagem genérica ao cliente |
| ❌ Nunca use `mysql_*` | Removidas desde PHP 7.0 |

---

## 60. Classes Abstratas

Uma **classe abstrata** é um molde incompleto — define a estrutura e parte do comportamento,
mas delega a implementação de certos métodos às subclasses. Não pode ser instanciada diretamente.

### Quando usar classe abstrata vs interface

| | Classe Abstrata | Interface |
|--|-----------------|-----------|
| Pode ter implementação | ✅ Sim (métodos concretos) | ❌ Não (PHP < 8.4) |
| Pode ter propriedades | ✅ Sim | ✅ Apenas constantes |
| Herança múltipla | ❌ Uma classe pai apenas | ✅ Implementa N interfaces |
| Modificadores de acesso | `public`, `protected` | Apenas `public` |
| Uso ideal | Compartilhar código base + forçar contrato | Definir contrato puro |

### Exemplo — repositório com implementação base

```php
<?php

declare(strict_types=1);

/**
 * Repositório base abstrato.
 * Define o contrato (métodos abstratos) e compartilha lógica comum (métodos concretos).
 */
abstract class BaseRepository
{
    // ✅ Construtor protegido — só subclasses podem instanciar indiretamente
    protected function __construct(
        protected readonly \PDO $pdo,
    ) {}

    // ── Métodos abstratos — DEVEM ser implementados pelas subclasses ──────────

    /** Retorna o nome da tabela no banco. */
    abstract protected function getTableName(): string;

    /** Mapeia uma linha do banco para um objeto de domínio. */
    abstract protected function mapRowToEntity(array $row): object;

    // ── Métodos concretos — lógica compartilhada entre todos os repositórios ──

    /**
     * Busca todos os registros da tabela.
     *
     * @return object[]
     */
    public function findAll(): array
    {
        // ✅ Usa o método abstrato — polimorfismo sem saber a tabela concreta
        $table = $this->getTableName();
        $stmt  = $this->pdo->query("SELECT * FROM {$table}");

        return array_map(
            fn(array $row): object => $this->mapRowToEntity($row),
            $stmt->fetchAll()
        );
    }

    /**
     * Busca por ID.
     */
    public function findById(int $id): ?object
    {
        $table = $this->getTableName();
        $stmt  = $this->pdo->prepare("SELECT * FROM {$table} WHERE id = :id");
        $stmt->execute(['id' => $id]);

        $row = $stmt->fetch();

        return $row !== false ? $this->mapRowToEntity($row) : null;
    }

    /**
     * Conta o total de registros.
     */
    public function count(): int
    {
        $table = $this->getTableName();
        return (int) $this->pdo->query("SELECT COUNT(*) FROM {$table}")->fetchColumn();
    }
}

// ── Implementações concretas ─────────────────────────────────────────────────

final class User
{
    public function __construct(
        public readonly int    $id,
        public readonly string $name,
        public readonly string $email,
    ) {}
}

final class UserRepository extends BaseRepository
{
    public function __construct(\PDO $pdo)
    {
        parent::__construct($pdo);
    }

    #[\Override]
    protected function getTableName(): string
    {
        return 'users';
    }

    #[\Override]
    protected function mapRowToEntity(array $row): User
    {
        return new User(
            id:    (int)    $row['id'],
            name:  (string) $row['name'],
            email: (string) $row['email'],
        );
    }

    // Método específico deste repositório (não existe no pai)
    public function findByEmail(string $email): ?User
    {
        $stmt = $this->pdo->prepare(
            'SELECT * FROM users WHERE email = :email LIMIT 1'
        );
        $stmt->execute(['email' => $email]);

        $row = $stmt->fetch();

        return $row !== false ? $this->mapRowToEntity($row) : null;
    }
}
```

### Regras de implementação de métodos abstratos

```php
<?php

declare(strict_types=1);

abstract class ShippingCalculator
{
    // Método abstrato com argumento — subclasse DEVE ter o mesmo parâmetro obrigatório
    abstract protected function calculateRate(float $weightKg): float;

    // Método concreto que usa o método abstrato
    public function getShippingCost(float $weightKg, float $distanceKm): float
    {
        $rate = $this->calculateRate($weightKg); // Polimorfismo
        return round($rate * $distanceKm / 100, 2);
    }
}

final class SedexCalculator extends ShippingCalculator
{
    // ✅ Mesmo modificador ou menos restrito (protected → public é ok)
    // ✅ Pode adicionar parâmetros OPCIONAIS além dos obrigatórios do pai
    #[\Override]
    public function calculateRate(float $weightKg, string $priority = 'normal'): float
    {
        $base = match($priority) {
            'express' => 12.0,
            default   => 8.5,
        };

        return $base + ($weightKg * 1.5);
    }
}

final class PacCalculator extends ShippingCalculator
{
    #[\Override]
    protected function calculateRate(float $weightKg): float
    {
        return 4.0 + ($weightKg * 0.8); // Mais barato, mais lento
    }
}

$sedex = new SedexCalculator();
$pac   = new PacCalculator();

echo $sedex->getShippingCost(weightKg: 2.5, distanceKm: 300); // R$
echo $pac->getShippingCost(weightKg: 2.5, distanceKm: 300);

// ❌ Não pode instanciar classe abstrata diretamente
// $calc = new ShippingCalculator(); // Fatal error
```

---

## 61. Interfaces

Uma **interface** define um **contrato puro** — declara quais métodos uma classe deve
ter, sem nenhuma implementação. É a ferramenta central do **polimorfismo** em PHP.

### Definindo e implementando interfaces

```php
<?php

declare(strict_types=1);

/**
 * Contrato para qualquer classe que possa ser serializada para JSON.
 */
interface JsonSerializable
{
    public function toJson(): string;
    public function toArray(): array;
}

/**
 * Contrato para entidades com identidade (ID único).
 */
interface Identifiable
{
    public function getId(): int;
}

/**
 * Contrato para entidades auditáveis (data de criação/atualização).
 */
interface Auditable
{
    public function getCreatedAt(): \DateTimeImmutable;
    public function getUpdatedAt(): \DateTimeImmutable;
}

// ✅ Uma classe pode implementar MÚLTIPLAS interfaces (herança múltipla de contratos)
final class UserEntity implements JsonSerializable, Identifiable, Auditable
{
    public function __construct(
        private readonly int                $id,
        private readonly string             $name,
        private readonly string             $email,
        private readonly \DateTimeImmutable $createdAt,
        private readonly \DateTimeImmutable $updatedAt,
    ) {}

    #[\Override]
    public function getId(): int
    {
        return $this->id;
    }

    #[\Override]
    public function toArray(): array
    {
        return [
            'id'         => $this->id,
            'name'       => $this->name,
            'email'      => $this->email,
            'created_at' => $this->createdAt->format('Y-m-d H:i:s'),
            'updated_at' => $this->updatedAt->format('Y-m-d H:i:s'),
        ];
    }

    #[\Override]
    public function toJson(): string
    {
        return json_encode(
            $this->toArray(),
            JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE
        );
    }

    #[\Override]
    public function getCreatedAt(): \DateTimeImmutable { return $this->createdAt; }

    #[\Override]
    public function getUpdatedAt(): \DateTimeImmutable { return $this->updatedAt; }
}
```

### Polimorfismo — type hint de interface

```php
<?php

declare(strict_types=1);

interface Logger
{
    public function log(string $level, string $message, array $context = []): void;
}

// Diferentes implementações do mesmo contrato
final class FileLogger implements Logger
{
    public function __construct(private readonly string $logPath) {}

    #[\Override]
    public function log(string $level, string $message, array $context = []): void
    {
        $timestamp = (new \DateTimeImmutable())->format('Y-m-d H:i:s');
        $entry     = "[{$timestamp}] [{$level}] {$message}" . PHP_EOL;
        file_put_contents($this->logPath, $entry, FILE_APPEND | LOCK_EX);
    }
}

final class ConsoleLogger implements Logger
{
    #[\Override]
    public function log(string $level, string $message, array $context = []): void
    {
        echo "[{$level}] {$message}" . PHP_EOL;
    }
}

final class NullLogger implements Logger
{
    // ✅ NullObject pattern — descarta os logs (útil em testes)
    #[\Override]
    public function log(string $level, string $message, array $context = []): void {}
}

// ✅ Type hint de interface — aceita QUALQUER implementação de Logger
final class UserService
{
    public function __construct(
        private readonly Logger $logger, // Depende da abstração, não da implementação
    ) {}

    public function createUser(string $name, string $email): void
    {
        // Lógica de criação...
        $this->logger->log('INFO', "Usuário criado: {$name} ({$email})");
    }
}

// Injeção de dependência — troca a implementação sem mudar UserService
$service = new UserService(logger: new ConsoleLogger());
$service->createUser('Ana', 'ana@example.com');

// Em produção:
// $service = new UserService(new FileLogger('/var/log/app.log'));

// Em testes:
// $service = new UserService(new NullLogger());
```

### Interface vs Classe Abstrata — quando usar cada um

```php
<?php

declare(strict_types=1);

// ✅ Use INTERFACE quando:
// - Quer definir um contrato puro sem nenhuma implementação compartilhada
// - Uma classe precisa "ser" várias coisas ao mesmo tempo
// - Diferentes hierarquias de classe precisam compartilhar o mesmo contrato

interface Printable
{
    public function print(): void;
}

interface Exportable
{
    public function export(string $format): string;
}

// ✅ Use CLASSE ABSTRATA quando:
// - Quer compartilhar código/lógica entre as subclasses (métodos concretos)
// - Há um relacionamento "é-um" forte (ElectricCar é-um Vehicle)
// - Precisa de propriedades compartilhadas e estado interno

abstract class Document implements Printable, Exportable
{
    protected string $title = '';
    protected string $content = '';

    // Método concreto compartilhado — não precisa reimplementar em cada subclasse
    public function setContent(string $title, string $content): void
    {
        $this->title   = $title;
        $this->content = $content;
    }

    // Contrato da interface Printable — deve implementar nas subclasses
    abstract public function print(): void;

    // Implementação padrão de export (pode ser sobrescrita)
    #[\Override]
    public function export(string $format): string
    {
        return match($format) {
            'text' => "{$this->title}\n{$this->content}",
            'json' => json_encode(['title' => $this->title, 'content' => $this->content]),
            default => throw new \InvalidArgumentException("Formato desconhecido: {$format}"),
        };
    }
}
```

---

## 62. Traits

**Traits** são mecanismos de reuso horizontal de código — permitem compartilhar métodos
entre classes que não têm relação de herança. Resolvem o problema da herança múltipla
de forma segura.

### Trait básico

```php
<?php

declare(strict_types=1);

/**
 * Trait de timestamps — adiciona created_at e updated_at a qualquer entidade.
 */
trait HasTimestamps
{
    private \DateTimeImmutable $createdAt;
    private \DateTimeImmutable $updatedAt;

    public function initTimestamps(): void
    {
        $now = new \DateTimeImmutable();
        $this->createdAt = $now;
        $this->updatedAt = $now;
    }

    public function touch(): void
    {
        $this->updatedAt = new \DateTimeImmutable();
    }

    public function getCreatedAt(): \DateTimeImmutable { return $this->createdAt; }
    public function getUpdatedAt(): \DateTimeImmutable { return $this->updatedAt; }
}

/**
 * Trait de soft delete — marca registros como deletados sem remover do banco.
 */
trait SoftDeletable
{
    private ?\DateTimeImmutable $deletedAt = null;

    public function softDelete(): void
    {
        $this->deletedAt = new \DateTimeImmutable();
    }

    public function restore(): void
    {
        $this->deletedAt = null;
    }

    public function isDeleted(): bool
    {
        return $this->deletedAt !== null;
    }

    public function getDeletedAt(): ?\DateTimeImmutable
    {
        return $this->deletedAt;
    }
}

/**
 * Trait de serialização para array/JSON.
 */
trait Serializable
{
    public function toJson(): string
    {
        return json_encode(
            get_object_vars($this),
            JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE
        );
    }
}
```

### Usando múltiplos traits em uma classe

```php
<?php

declare(strict_types=1);

final class Article
{
    // ✅ Múltiplos traits com vírgula
    use HasTimestamps, SoftDeletable, Serializable;

    public function __construct(
        private readonly int    $id,
        private string          $title,
        private string          $body,
    ) {
        $this->initTimestamps(); // Método do trait HasTimestamps
    }

    public function updateTitle(string $newTitle): void
    {
        $this->title = $newTitle;
        $this->touch(); // Método do trait HasTimestamps — atualiza updatedAt
    }
}

$article = new Article(id: 1, title: 'PHP 8.5', body: 'Conteúdo...');
echo $article->getCreatedAt()->format('d/m/Y'); // Data de hoje
var_dump($article->isDeleted()); // bool(false)

$article->softDelete();
var_dump($article->isDeleted()); // bool(true)

$article->restore();
var_dump($article->isDeleted()); // bool(false)

echo $article->toJson(); // JSON com todas as propriedades públicas
```

### Trait com método abstrato — força implementação na classe

```php
<?php

declare(strict_types=1);

/**
 * Trait de validação — força a classe a implementar regras de validação.
 */
trait Validatable
{
    // Força a classe que usa o trait a implementar este método
    abstract protected function validationRules(): array;

    public function validate(): bool
    {
        $rules = $this->validationRules();

        foreach ($rules as $field => $rule) {
            $value = $this->{$field} ?? null;

            if ($rule === 'required' && empty($value)) {
                throw new \InvalidArgumentException("Campo obrigatório ausente: {$field}");
            }
        }

        return true;
    }
}

final class Order
{
    use Validatable;

    public function __construct(
        private readonly int    $id,
        private readonly string $customerName,
        private readonly float  $total,
    ) {}

    #[\Override]
    protected function validationRules(): array
    {
        return [
            'customerName' => 'required',
            'total'        => 'required',
        ];
    }
}

$order = new Order(id: 1, customerName: 'Ana', total: 299.90);
var_dump($order->validate()); // bool(true)
```

### Resolução de conflitos entre traits

```php
<?php

declare(strict_types=1);

trait A
{
    public function hello(): string
    {
        return 'Olá do Trait A';
    }
}

trait B
{
    public function hello(): string
    {
        return 'Olá do Trait B';
    }
}

class MyClass
{
    use A, B {
        A::hello insteadof B; // ✅ Usa hello() de A em vez de B
        B::hello as helloB;   // ✅ Cria alias para o hello() de B
    }
}

$obj = new MyClass();
echo $obj->hello();  // Olá do Trait A
echo $obj->helloB(); // Olá do Trait B
```

> ⚠️ **PHP 8.5:** `#[\Deprecated]` pode ser aplicado em traits e constantes.

---

## 63. Métodos Estáticos

Métodos `static` pertencem à **classe**, não a instâncias individuais. São acessados
via `ClassName::method()` sem necessidade de criar um objeto.

### Quando usar métodos estáticos

```
✅ Factory methods (instanciar com lógica)
✅ Funções utilitárias sem estado (helpers, formatters)
✅ Singleton e Registry patterns
❌ Lógica que depende de estado do objeto (use instância)
❌ Qualquer coisa que precise de injeção de dependência (dificulta testes)
```

### Factory method — criação com lógica

```php
<?php

declare(strict_types=1);

final class Money
{
    private function __construct(
        private readonly int    $amountCents, // Armazenado em centavos (evita float)
        private readonly string $currency,
    ) {}

    // ✅ Factory methods estáticos — nomes descritivos, lógica de criação
    public static function fromReais(float $reais, string $currency = 'BRL'): self
    {
        return new self(
            amountCents: (int) round($reais * 100),
            currency:    $currency,
        );
    }

    public static function fromCents(int $cents, string $currency = 'BRL'): self
    {
        return new self(amountCents: $cents, currency: $currency);
    }

    public static function zero(string $currency = 'BRL'): self
    {
        return new self(amountCents: 0, currency: $currency);
    }

    // Métodos de instância — operam no estado do objeto
    public function add(self $other): self
    {
        if ($this->currency !== $other->currency) {
            throw new \InvalidArgumentException('Moedas diferentes não podem ser somadas.');
        }

        return new self($this->amountCents + $other->amountCents, $this->currency);
    }

    public function format(): string
    {
        return $this->currency . ' ' . number_format($this->amountCents / 100, 2, ',', '.');
    }
}

$price    = Money::fromReais(299.90);
$shipping = Money::fromCents(1500); // R$ 15,00
$total    = $price->add($shipping);

echo $total->format(); // BRL 314,90
```

### Acesso entre métodos estáticos e de instância

```php
<?php

declare(strict_types=1);

final class MathHelper
{
    // Constante de classe — usada em métodos estáticos
    private const float PRECISION = 0.0001;

    // ✅ self:: — acessa a própria classe de dentro de métodos estáticos
    public static function isNearlyEqual(float $a, float $b): bool
    {
        return abs($a - $b) < self::PRECISION;
    }

    public static function clamp(float $value, float $min, float $max): float
    {
        return max($min, min($max, $value));
    }

    public static function lerp(float $start, float $end, float $t): float
    {
        return $start + ($end - $start) * self::clamp($t, 0.0, 1.0);
    }

    public static function percentage(float $part, float $total): float
    {
        if ($total === 0.0) {
            throw new \DivisionByZeroError('Total não pode ser zero.');
        }

        return round(($part / $total) * 100, 2);
    }
}

// Uso sem instanciar a classe
echo MathHelper::percentage(25.0, 200.0); // 12.5
echo MathHelper::lerp(0.0, 100.0, 0.3);   // 30
var_dump(MathHelper::isNearlyEqual(0.1 + 0.2, 0.3)); // bool(true) — trata imprecisão de float
```

### Chamando método estático do pai em herança

```php
<?php

declare(strict_types=1);

class BaseConfig
{
    protected static string $environment = 'production';

    protected static function getBaseUrl(): string
    {
        return 'https://api.example.com';
    }
}

final class AppConfig extends BaseConfig
{
    public static function getApiUrl(): string
    {
        // ✅ parent:: chama método estático da classe pai
        return parent::getBaseUrl() . '/v2';
    }

    public static function isDevelopment(): bool
    {
        return parent::$environment === 'development';
    }
}

echo AppConfig::getApiUrl(); // https://api.example.com/v2
```

---

## 64. Propriedades Estáticas

Propriedades `static` são **compartilhadas entre todas as instâncias** de uma classe.
Persistem durante toda a execução do script.

### Contador compartilhado — exemplo clássico

```php
<?php

declare(strict_types=1);

final class Connection
{
    // ✅ Propriedade estática — compartilhada entre todos os objetos Connection
    private static int $totalConnections = 0;
    private static int $activeConnections = 0;

    private readonly int $connectionId;

    public function __construct(
        private readonly string $dsn,
    ) {
        self::$totalConnections++;
        self::$activeConnections++;
        $this->connectionId = self::$totalConnections;
    }

    public function __destruct()
    {
        self::$activeConnections--;
    }

    // ✅ Métodos estáticos para ler estado compartilhado
    public static function getTotalConnections(): int  { return self::$totalConnections; }
    public static function getActiveConnections(): int { return self::$activeConnections; }

    public function getId(): int { return $this->connectionId; }
}

$conn1 = new Connection('mysql:host=localhost');
$conn2 = new Connection('mysql:host=localhost');
$conn3 = new Connection('mysql:host=localhost');

echo Connection::getTotalConnections();  // 3
echo Connection::getActiveConnections(); // 3

unset($conn2); // Destructor chamado
echo Connection::getActiveConnections(); // 2
```

### Singleton — instância única via propriedade estática

```php
<?php

declare(strict_types=1);

/**
 * Singleton de configuração — existe apenas uma instância durante toda a execução.
 *
 * ⚠️ Use Singleton com moderação — dificulta testes e cria acoplamento global.
 * ✅ Prefira Dependency Injection (DI) em projetos maiores.
 */
final class AppConfig
{
    private static ?self $instance = null;

    /** @var array<string, mixed> */
    private array $settings = [];

    // ✅ Constructor privado — impede new AppConfig() externo
    private function __construct() {}

    public static function getInstance(): self
    {
        // ✅ Null coalescing assignment — cria apenas se ainda não existe
        return self::$instance ??= new self();
    }

    public function set(string $key, mixed $value): void
    {
        $this->settings[$key] = $value;
    }

    public function get(string $key, mixed $default = null): mixed
    {
        return $this->settings[$key] ?? $default;
    }
}

// Primeira chamada — cria a instância
$config = AppConfig::getInstance();
$config->set('debug', true);
$config->set('timezone', 'America/Sao_Paulo');

// Segunda chamada — retorna a mesma instância
$same = AppConfig::getInstance();
var_dump($same->get('debug'));    // bool(true) — dados persistiram
var_dump($config === $same);      // bool(true) — é o mesmo objeto
```

### Propriedade estática em herança com static::

```php
<?php

declare(strict_types=1);

class Counter
{
    // ⚠️ self:: trava na classe onde está declarado
    // ✅ static:: usa late static binding — respeita a subclasse
    protected static int $count = 0;

    public static function increment(): void
    {
        static::$count++; // Incrementa o contador da classe chamada
    }

    public static function getCount(): int
    {
        return static::$count;
    }
}

class UserCounter extends Counter
{
    protected static int $count = 0; // Propriedade própria da subclasse
}

class ProductCounter extends Counter
{
    protected static int $count = 0;
}

UserCounter::increment();
UserCounter::increment();
ProductCounter::increment();

echo Counter::getCount();        // 0 — não afetado pelas subclasses
echo UserCounter::getCount();    // 2
echo ProductCounter::getCount(); // 1
```

---

## 65. Namespaces

**Namespaces** organizam o código em grupos lógicos, evitando colisões de nomes entre
classes, interfaces, funções e constantes — especialmente em projetos grandes ou ao
integrar bibliotecas de terceiros.

### Declarando namespace — PSR-4

```php
<?php

// ✅ namespace DEVE ser a primeira instrução (após <?php e docblock opcional)
// Convenção PSR-4: namespace espelha a estrutura de diretórios

declare(strict_types=1);

namespace App\Service\Payment;

// Imports — sempre após o namespace, antes do código
use App\Entity\Order;
use App\Repository\OrderRepository;
use App\Exception\PaymentException;
use DateTimeImmutable;
use InvalidArgumentException;

final class PaymentService
{
    public function __construct(
        private readonly OrderRepository $orderRepository,
    ) {}

    public function processPayment(int $orderId, float $amount): void
    {
        $order = $this->orderRepository->findById($orderId)
            ?? throw new PaymentException("Pedido #{$orderId} não encontrado.");

        if ($amount <= 0.0) {
            throw new InvalidArgumentException('Valor de pagamento deve ser positivo.');
        }

        // Processamento...
    }
}
```

### Estrutura de diretórios PSR-4

```
📂 src/
├── 📂 Controller/
│   └── 📄 UserController.php      → namespace App\Controller;
├── 📂 Entity/
│   ├── 📄 User.php                → namespace App\Entity;
│   └── 📄 Product.php             → namespace App\Entity;
├── 📂 Repository/
│   └── 📄 UserRepository.php      → namespace App\Repository;
├── 📂 Service/
│   ├── 📄 UserService.php         → namespace App\Service;
│   └── 📂 Payment/
│       └── 📄 PaymentService.php  → namespace App\Service\Payment;
└── 📂 Exception/
    └── 📄 DomainException.php     → namespace App\Exception;
```

### Usando classes de outros namespaces

```php
<?php

declare(strict_types=1);

namespace App\Controller;

// ── Formas de importar ───────────────────────────────────────────────────────

// Importação simples
use App\Entity\User;
use App\Service\UserService;

// Importação com alias — resolve colisão de nomes
use App\Entity\User as UserEntity;
use App\Dto\User as UserDto;

// Importação agrupada (PER-CS v3.0)
use App\Repository\{UserRepository, ProductRepository, OrderRepository};

// Importação de funções e constantes
use function App\Helper\{sanitizeString, formatCurrency};
use const App\Config\{APP_VERSION, API_BASE_URL};

// Classes do namespace global (PHP nativo) — prefixo \ ou importação explícita
use DateTimeImmutable;
use InvalidArgumentException;
// ou acesso direto: new \DateTimeImmutable()

final class UserController
{
    public function __construct(
        private readonly UserService    $userService,
        private readonly UserRepository $userRepository,
    ) {}

    public function show(int $id): array
    {
        $user = $this->userRepository->findById($id)
            ?? throw new \RuntimeException("Usuário #{$id} não encontrado.");

        return $user->toArray();
    }
}
```

### Namespace global e escape com \

```php
<?php

declare(strict_types=1);

namespace App\Util;

// Dentro de um namespace, PHP procura classes/funções no namespace atual primeiro
// Para usar classes PHP nativas, use \ ou importe explicitamente

final class DateHelper
{
    public function getCurrentDateTime(): \DateTimeImmutable // ✅ \ escapa para o namespace global
    {
        return new \DateTimeImmutable('now', new \DateTimeZone('America/Sao_Paulo'));
    }

    public function formatDate(\DateTimeImmutable $date): string
    {
        return $date->format('d/m/Y H:i');
    }
}

// Funções nativas também precisam de \  dentro de namespaces (ou importação)
function stringLength(string $s): int
{
    return \mb_strlen($s); // ✅ ou: use function mb_strlen;
}
```

---

## 66. Iterables e Iterator

Um **iterable** é qualquer valor que pode ser percorrido com `foreach`. Em PHP, isso
inclui arrays e objetos que implementam a interface `Iterator` ou `IteratorAggregate`.

### O tipo iterable

```php
<?php

declare(strict_types=1);

// ✅ iterable aceita tanto arrays quanto objetos Iterator
function processItems(iterable $items): void
{
    foreach ($items as $key => $item) {
        echo "{$key}: {$item}";
    }
}

// Funciona com array
processItems(['a', 'b', 'c']);

// Funciona com qualquer Iterator
processItems(new \ArrayIterator(['d', 'e', 'f']));

// ✅ Retorno iterable — flexível para o chamador
function getNumbers(int $start, int $end): iterable
{
    // Pode retornar array OU Generator (economiza memória para sequências grandes)
    for ($i = $start; $i <= $end; $i++) {
        yield $i; // Generator — produz valores sob demanda
    }
}

foreach (getNumbers(1, 1_000_000) as $n) {
    // Processa um número por vez sem carregar tudo na memória
    if ($n > 5) break;
    echo $n; // 1 2 3 4 5
}
```

### Implementando a interface Iterator

```php
<?php

declare(strict_types=1);

/**
 * Iterador de intervalo — gera números de $start a $end.
 * Demonstra como implementar Iterator do zero.
 */
final class RangeIterator implements \Iterator
{
    private int $current;

    public function __construct(
        private readonly int $start,
        private readonly int $end,
        private readonly int $step = 1,
    ) {
        $this->current = $start;
    }

    // Retorna o elemento atual
    public function current(): int
    {
        return $this->current;
    }

    // Retorna a chave atual
    public function key(): int
    {
        return ($this->current - $this->start) / $this->step;
    }

    // Avança para o próximo elemento
    public function next(): void
    {
        $this->current += $this->step;
    }

    // Reinicia o iterador
    public function rewind(): void
    {
        $this->current = $this->start;
    }

    // Verifica se a posição atual é válida
    public function valid(): bool
    {
        return $this->current <= $this->end;
    }
}

// Uso com foreach
$range = new RangeIterator(start: 0, end: 10, step: 2);

foreach ($range as $key => $value) {
    echo "{$key}: {$value}"; // 0: 0, 1: 2, 2: 4, 3: 6, 4: 8, 5: 10
}

// ✅ Pode reutilizar — rewind() é chamado automaticamente
foreach ($range as $value) {
    echo $value; // 0 2 4 6 8 10
}
```

### Generator — alternativa moderna e mais simples

```php
<?php

declare(strict_types=1);

// ✅ Generator com yield — evita implementar Iterator manualmente
// Ideal para sequências grandes ou de comprimento desconhecido
function fibonacci(): \Generator
{
    [$a, $b] = [0, 1];

    while (true) { // Sequência infinita — o caller controla quando parar
        yield $a;
        [$a, $b] = [$b, $a + $b];
    }
}

$fib = fibonacci();

for ($i = 0; $i < 10; $i++) {
    echo $fib->current(); // 0 1 1 2 3 5 8 13 21 34
    $fib->next();
}

// ✅ Leitura de arquivo linha por linha — sem carregar tudo na memória
function readFileLines(string $path): \Generator
{
    $handle = fopen($path, 'r')
        ?: throw new \RuntimeException("Falha ao abrir: {$path}");

    try {
        while (!feof($handle)) {
            $line = fgets($handle);

            if ($line !== false) {
                yield trim($line);
            }
        }
    } finally {
        fclose($handle);
    }
}

// Processa um arquivo de 10 GB linha por linha sem problema de memória
foreach (readFileLines('/data/huge-file.csv') as $lineNumber => $line) {
    if ($lineNumber === 0) continue; // Pula cabeçalho
    // Processa linha...
}
```

### IteratorAggregate — delegando a iteração

```php
<?php

declare(strict_types=1);

/**
 * Coleção de produtos com filtragem — implementa IteratorAggregate.
 * Mais simples que Iterator quando já temos uma estrutura iterável interna.
 */
final class ProductCollection implements \IteratorAggregate, \Countable
{
    /** @var array<int, array{name: string, price: float, stock: int}> */
    private array $products = [];

    public function add(string $name, float $price, int $stock): void
    {
        $this->products[] = compact('name', 'price', 'stock');
    }

    // Necessário para IteratorAggregate — retorna o iterador interno
    public function getIterator(): \ArrayIterator
    {
        return new \ArrayIterator($this->products);
    }

    // Necessário para Countable — permite count($collection)
    public function count(): int
    {
        return count($this->products);
    }

    // Método de filtragem
    public function inStock(): self
    {
        $filtered = new self();

        foreach ($this->products as $product) {
            if ($product['stock'] > 0) {
                $filtered->add($product['name'], $product['price'], $product['stock']);
            }
        }

        return $filtered;
    }
}

$catalog = new ProductCollection();
$catalog->add('Teclado',  350.0, 15);
$catalog->add('Mouse',     89.9,  0);
$catalog->add('Monitor', 1499.0,  8);

echo count($catalog); // 3

foreach ($catalog->inStock() as $product) {
    echo "{$product['name']}: R$ {$product['price']}";
}
// Teclado: R$ 350
// Monitor: R$ 1499
```

---

## 67. Banco de Dados com PDO — Introdução

**PDO** (PHP Data Objects) é a extensão nativa do PHP para acesso a bancos de dados.
Fornece uma interface **unificada** para MySQL, PostgreSQL, SQLite, SQL Server e outros,
com suporte a **prepared statements** — a única forma segura de executar queries com dados externos.

> 🔒 **Regra absoluta:** Nunca concatene dados do usuário em uma query SQL.
> Sempre use prepared statements com parâmetros vinculados.

### Por que PDO em vez de MySQLi?

| | PDO | MySQLi |
|--|-----|--------|
| Suporta múltiplos bancos | ✅ Sim (15+ drivers) | ❌ Apenas MySQL |
| API orientada a objetos | ✅ Sim | ✅ Sim |
| Prepared statements | ✅ Sim | ✅ Sim |
| Named parameters | ✅ `:name` | ❌ Apenas `?` |
| Padrão moderno | ✅ Recomendado | ⚠️ Legado |

### Conectando ao banco

```php
<?php

declare(strict_types=1);

/**
 * Cria e retorna uma conexão PDO configurada com as melhores práticas.
 *
 * @throws \PDOException Se a conexão falhar
 */
function createPdoConnection(
    string $host,
    string $database,
    string $username,
    string $password,
    int    $port = 3306,
): \PDO {
    $dsn = "mysql:host={$host};port={$port};dbname={$database};charset=utf8mb4";

    return new \PDO(
        dsn:      $dsn,
        username: $username,
        password: $password,
        options:  [
            // ✅ Lança PDOException em erros — nunca falha silenciosamente
            \PDO::ATTR_ERRMODE            => \PDO::ERRMODE_EXCEPTION,
            // ✅ Retorna resultados como array associativo por padrão
            \PDO::ATTR_DEFAULT_FETCH_MODE => \PDO::FETCH_ASSOC,
            // ✅ Desabilita prepared statements emulados — mais seguro
            \PDO::ATTR_EMULATE_PREPARES   => false,
            // ✅ Garante que inteiros retornem como int (não string)
            \PDO::ATTR_STRINGIFY_FETCHES  => false,
        ],
    );
}

// Credenciais nunca devem estar hard-coded — use variáveis de ambiente
$pdo = createPdoConnection(
    host:     $_ENV['DB_HOST']     ?? 'localhost',
    database: $_ENV['DB_NAME']     ?? 'my_app',
    username: $_ENV['DB_USER']     ?? 'root',
    password: $_ENV['DB_PASSWORD'] ?? '',
);
```

### SELECT com prepared statement

```php
<?php

declare(strict_types=1);

// ✅ Parâmetros nomeados — mais legível e ordem não importa
function findUserByEmail(\PDO $pdo, string $email): ?array
{
    // 1. Prepara a query — jamais concatene variáveis!
    $stmt = $pdo->prepare('SELECT id, name, email, role FROM users WHERE email = :email LIMIT 1');

    // 2. Executa com parâmetros — PDO escapa automaticamente
    $stmt->execute(['email' => $email]);

    // 3. Busca o resultado
    $row = $stmt->fetch(); // null ou array

    return $row !== false ? $row : null;
}

$user = findUserByEmail($pdo, 'ana@example.com');

if ($user !== null) {
    echo htmlspecialchars($user['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
} else {
    echo 'Usuário não encontrado.';
}

// ── fetchAll() — múltiplas linhas ───────────────────────────────────────────
function listUsersByRole(\PDO $pdo, string $role): array
{
    $stmt = $pdo->prepare('SELECT id, name, email FROM users WHERE role = :role ORDER BY name');
    $stmt->execute(['role' => $role]);

    return $stmt->fetchAll(); // array de arrays associativos
}

$admins = listUsersByRole($pdo, 'admin');

foreach ($admins as $admin) {
    echo htmlspecialchars($admin['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
```

### INSERT, UPDATE e DELETE

```php
<?php

declare(strict_types=1);

// ── INSERT ───────────────────────────────────────────────────────────────────
function createUser(\PDO $pdo, string $name, string $email, string $password): int
{
    // ✅ NUNCA armazene senha em texto plano
    $hash = password_hash($password, PASSWORD_ARGON2ID, [
        'memory_cost' => 65536,
        'time_cost'   => 4,
        'threads'     => 3,
    ]);

    $stmt = $pdo->prepare(
        'INSERT INTO users (name, email, password_hash, created_at) VALUES (:name, :email, :hash, NOW())'
    );

    $stmt->execute([
        'name'  => $name,
        'email' => $email,
        'hash'  => $hash,
    ]);

    // ✅ lastInsertId() retorna o ID gerado pelo AUTO_INCREMENT
    return (int) $pdo->lastInsertId();
}

$userId = createUser($pdo, 'Ana Silva', 'ana@example.com', 'senha_segura_123');
echo "Usuário criado com ID: {$userId}";

// ── UPDATE ───────────────────────────────────────────────────────────────────
function updateUserName(\PDO $pdo, int $userId, string $newName): bool
{
    $stmt = $pdo->prepare('UPDATE users SET name = :name, updated_at = NOW() WHERE id = :id');
    $stmt->execute(['name' => $newName, 'id' => $userId]);

    // rowCount() retorna o número de linhas afetadas
    return $stmt->rowCount() > 0;
}

$updated = updateUserName($pdo, $userId, 'Ana Costa');
var_dump($updated); // bool(true)

// ── DELETE ───────────────────────────────────────────────────────────────────
function deleteUser(\PDO $pdo, int $userId): bool
{
    $stmt = $pdo->prepare('DELETE FROM users WHERE id = :id');
    $stmt->execute(['id' => $userId]);

    return $stmt->rowCount() > 0;
}
```

### Transações — operações atômicas

```php
<?php

declare(strict_types=1);

/**
 * Transferência bancária — ambas as operações devem ter sucesso ou nenhuma.
 * Transações garantem atomicidade.
 */
function transferFunds(\PDO $pdo, int $fromId, int $toId, float $amount): void
{
    // ✅ Inicia a transação
    $pdo->beginTransaction();

    try {
        // Debita da conta origem
        $debit = $pdo->prepare('UPDATE accounts SET balance = balance - :amount WHERE id = :id AND balance >= :amount');
        $debit->execute(['amount' => $amount, 'id' => $fromId]);

        if ($debit->rowCount() === 0) {
            throw new \RuntimeException('Saldo insuficiente ou conta não encontrada.');
        }

        // Credita na conta destino
        $credit = $pdo->prepare('UPDATE accounts SET balance = balance + :amount WHERE id = :id');
        $credit->execute(['amount' => $amount, 'id' => $toId]);

        if ($credit->rowCount() === 0) {
            throw new \RuntimeException('Conta destino não encontrada.');
        }

        // ✅ Confirma a transação — todas as operações foram bem-sucedidas
        $pdo->commit();

    } catch (\Throwable $e) {
        // ✅ Reverte tudo se qualquer operação falhar
        $pdo->rollBack();
        throw new \RuntimeException(
            message:  'Transferência falhou: ' . $e->getMessage(),
            previous: $e,
        );
    }
}
```

### Checklist de segurança com PDO

| Regra | Razão |
|-------|-------|
| ✅ `ATTR_ERRMODE => ERRMODE_EXCEPTION` | Nunca falhar silenciosamente |
| ✅ `ATTR_EMULATE_PREPARES => false` | Prepared statements reais no driver |
| ✅ Sempre usar `:param` ou `?` | Previne SQL Injection |
| ✅ `password_hash(PASSWORD_ARGON2ID)` | Nunca armazene senhas em texto |
| ✅ `ATTR_DEFAULT_FETCH_MODE => FETCH_ASSOC` | Arrays associativos mais legíveis |
| ✅ `charset=utf8mb4` no DSN | Suporte completo a Unicode e emoji |
| ❌ Nunca concatenar `$_POST` na query | SQL Injection |
| ❌ Nunca exibir erros de PDO ao usuário | Vaza estrutura do banco |
| ❌ Nunca hard-code credenciais | Use variáveis de ambiente |

---

## 68. PDO — Conexão com MySQL

### Por que PDO e não MySQLi?

O W3Schools apresenta MySQLi e PDO como opções equivalentes. Na prática profissional,
**PDO é a escolha correta** para projetos novos:

| | PDO | MySQLi |
|--|-----|--------|
| Bancos suportados | 15+ (MySQL, PostgreSQL, SQLite, SQL Server...) | Apenas MySQL |
| Parâmetros nomeados | ✅ `:name` | ❌ Apenas `?` |
| Padrão moderno | ✅ | ⚠️ Legado |
| Portabilidade | ✅ Troca de banco = mudar DSN | ❌ Reescrever tudo |

> ✅ **Este guia usa exclusivamente PDO** — nunca MySQLi em código novo.

### Conexão PDO com todas as opções seguras

```php
<?php

declare(strict_types=1);

/**
 * Cria uma conexão PDO configurada com as melhores práticas de segurança.
 * Credenciais devem vir de variáveis de ambiente — nunca hard-coded.
 *
 * @throws \RuntimeException Se a conexão falhar
 */
function createConnection(): \PDO
{
    // ✅ Lê credenciais de variáveis de ambiente — nunca do código-fonte
    $host     = $_ENV['DB_HOST']     ?? 'localhost';
    $port     = (int) ($_ENV['DB_PORT'] ?? 3306);
    $database = $_ENV['DB_NAME']     ?? 'my_app';
    $username = $_ENV['DB_USER']     ?? 'root';
    $password = $_ENV['DB_PASSWORD'] ?? '';

    // DSN — Data Source Name: identifica o banco, host, porta e charset
    // charset=utf8mb4 suporta emoji e caracteres completos de Unicode
    $dsn = "mysql:host={$host};port={$port};dbname={$database};charset=utf8mb4";

    try {
        $pdo = new \PDO(
            dsn:      $dsn,
            username: $username,
            password: $password,
            options:  [
                // ✅ Lança PDOException em qualquer erro — nunca falha silenciosamente
                \PDO::ATTR_ERRMODE            => \PDO::ERRMODE_EXCEPTION,
                // ✅ Retorna arrays associativos por padrão (não stdClass)
                \PDO::ATTR_DEFAULT_FETCH_MODE => \PDO::FETCH_ASSOC,
                // ✅ Prepared statements reais no driver — mais seguro
                \PDO::ATTR_EMULATE_PREPARES   => false,
                // ✅ Inteiros e decimais retornam com tipo nativo (não string)
                \PDO::ATTR_STRINGIFY_FETCHES  => false,
                // ✅ Timeout de conexão em segundos
                \PDO::ATTR_TIMEOUT            => 5,
            ],
        );

        return $pdo;

    } catch (\PDOException $e) {
        // ✅ Log interno com detalhes, mensagem genérica ao exterior
        error_log('Falha de conexão PDO: ' . $e->getMessage());

        throw new \RuntimeException(
            message:  'Não foi possível conectar ao banco de dados.',
            code:     500,
            previous: $e,
        );
    }
}

// Uso
try {
    $pdo = createConnection();
    echo 'Conexão estabelecida com sucesso.';
} catch (\RuntimeException $e) {
    // Em produção: exiba mensagem genérica, nunca detalhes de conexão
    http_response_code(503);
    echo 'Serviço temporariamente indisponível.';
    exit;
}
```

### Singleton de conexão — uma conexão por requisição

```php
<?php

declare(strict_types=1);

/**
 * Gerencia uma única instância de PDO por requisição (lazy initialization).
 * Evita abrir múltiplas conexões desnecessariamente.
 */
final class Database
{
    private static ?\PDO $instance = null;

    // Constructor privado — use apenas Database::getInstance()
    private function __construct() {}

    public static function getInstance(): \PDO
    {
        if (self::$instance === null) {
            $dsn = sprintf(
                'mysql:host=%s;port=%d;dbname=%s;charset=utf8mb4',
                $_ENV['DB_HOST'] ?? 'localhost',
                (int) ($_ENV['DB_PORT'] ?? 3306),
                $_ENV['DB_NAME'] ?? 'my_app',
            );

            self::$instance = new \PDO(
                dsn:      $dsn,
                username: $_ENV['DB_USER']     ?? 'root',
                password: $_ENV['DB_PASSWORD'] ?? '',
                options:  [
                    \PDO::ATTR_ERRMODE            => \PDO::ERRMODE_EXCEPTION,
                    \PDO::ATTR_DEFAULT_FETCH_MODE => \PDO::FETCH_ASSOC,
                    \PDO::ATTR_EMULATE_PREPARES   => false,
                    \PDO::ATTR_STRINGIFY_FETCHES  => false,
                ],
            );
        }

        return self::$instance;
    }

    // Fecha a conexão explicitamente (raramente necessário)
    public static function close(): void
    {
        self::$instance = null; // PDO fecha ao perder todas as referências
    }
}

// Uso — obtém (ou cria) a conexão
$pdo = Database::getInstance();

// Segunda chamada retorna a mesma conexão
$samePdo = Database::getInstance();
var_dump($pdo === $samePdo); // bool(true)
```

### Verificando a conexão e versão do servidor

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

// Versão do servidor MySQL/MariaDB
$serverVersion = $pdo->getAttribute(\PDO::ATTR_SERVER_VERSION);
echo "Servidor: {$serverVersion}";

// Versão do driver PDO
$driverVersion = $pdo->getAttribute(\PDO::ATTR_CLIENT_VERSION);
echo "Driver: {$driverVersion}";

// Nome do driver (mysql, pgsql, sqlite...)
$driverName = $pdo->getAttribute(\PDO::ATTR_DRIVER_NAME);
echo "Driver: {$driverName}";

// ✅ Testa a conexão com uma query simples
$isAlive = $pdo->query('SELECT 1')->fetchColumn() === '1';
var_dump($isAlive); // bool(true) se conectado
```

---

## 69. PDO — Criando Banco e Tabelas

Na maioria dos projetos profissionais, banco de dados e tabelas são criados via
**migrations** (scripts versionados), não via PHP em runtime. Mas é importante entender
a sintaxe para automação e testes.

### Criando um banco de dados

```php
<?php

declare(strict_types=1);

/**
 * Cria um banco de dados se não existir.
 * Conecta sem selecionar banco (sem dbname no DSN).
 */
function createDatabase(string $dbName): void
{
    // ✅ Conecta sem dbname para poder criar o banco
    $pdo = new \PDO(
        dsn:      'mysql:host=localhost;charset=utf8mb4',
        username: $_ENV['DB_USER']     ?? 'root',
        password: $_ENV['DB_PASSWORD'] ?? '',
        options:  [\PDO::ATTR_ERRMODE => \PDO::ERRMODE_EXCEPTION],
    );

    // ✅ Valida o nome do banco — apenas letras, números e underscore
    if (!preg_match('/^[a-zA-Z0-9_]+$/', $dbName)) {
        throw new \InvalidArgumentException("Nome de banco inválido: {$dbName}");
    }

    // IF NOT EXISTS — seguro para re-executar sem erros
    $pdo->exec("CREATE DATABASE IF NOT EXISTS `{$dbName}` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci");

    echo "Banco '{$dbName}' criado (ou já existia).";
}

createDatabase('my_app');
```

### Criando tabelas — estrutura production-grade

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

/**
 * Cria a tabela de usuários com estrutura moderna.
 *
 * Boas práticas de schema:
 * - id BIGINT UNSIGNED AUTO_INCREMENT (suporta bilhões de registros)
 * - VARCHAR com limite real (não 255 por preguiça)
 * - UNIQUE em e-mail para garantir integridade
 * - created_at / updated_at para auditoria
 * - ENGINE=InnoDB para suporte a transações e FK
 * - CHARACTER SET utf8mb4 para Unicode completo (inclui emoji)
 */
function createUsersTable(\PDO $pdo): void
{
    $sql = <<<SQL
        CREATE TABLE IF NOT EXISTS users (
            id           BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
            name         VARCHAR(100)    NOT NULL,
            email        VARCHAR(150)    NOT NULL,
            password_hash VARCHAR(255)   NOT NULL,
            role         ENUM('admin', 'editor', 'viewer') NOT NULL DEFAULT 'viewer',
            active       TINYINT(1)      NOT NULL DEFAULT 1,
            created_at   TIMESTAMP       NOT NULL DEFAULT CURRENT_TIMESTAMP,
            updated_at   TIMESTAMP       NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
            PRIMARY KEY (id),
            UNIQUE KEY uq_users_email (email),
            INDEX idx_users_role (role),
            INDEX idx_users_active (active)
        ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci
    SQL;

    $pdo->exec($sql);
    echo "Tabela 'users' criada com sucesso.";
}

function createPostsTable(\PDO $pdo): void
{
    $sql = <<<SQL
        CREATE TABLE IF NOT EXISTS posts (
            id         BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
            user_id    BIGINT UNSIGNED NOT NULL,
            title      VARCHAR(200)    NOT NULL,
            slug       VARCHAR(220)    NOT NULL,
            body       TEXT            NOT NULL,
            published  TINYINT(1)      NOT NULL DEFAULT 0,
            created_at TIMESTAMP       NOT NULL DEFAULT CURRENT_TIMESTAMP,
            updated_at TIMESTAMP       NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
            PRIMARY KEY (id),
            UNIQUE KEY uq_posts_slug (slug),
            INDEX idx_posts_user_id (user_id),
            INDEX idx_posts_published (published),
            CONSTRAINT fk_posts_user_id
                FOREIGN KEY (user_id) REFERENCES users (id)
                ON DELETE CASCADE
                ON UPDATE CASCADE
        ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci
    SQL;

    $pdo->exec($sql);
    echo "Tabela 'posts' criada com sucesso.";
}

// Cria as tabelas em ordem (posts depende de users via FK)
try {
    createUsersTable($pdo);
    createPostsTable($pdo);
} catch (\PDOException $e) {
    error_log('Erro ao criar tabelas: ' . $e->getMessage());
    throw new \RuntimeException('Falha na migração do banco de dados.', previous: $e);
}
```

### Verificando se uma tabela existe

```php
<?php

declare(strict_types=1);

function tableExists(\PDO $pdo, string $tableName, string $database): bool
{
    $stmt = $pdo->prepare(
        "SELECT COUNT(*) FROM information_schema.tables
         WHERE table_schema = :db AND table_name = :table"
    );
    $stmt->execute(['db' => $database, 'table' => $tableName]);

    return (int) $stmt->fetchColumn() > 0;
}

$dbName = $_ENV['DB_NAME'] ?? 'my_app';

var_dump(tableExists($pdo, 'users', $dbName));  // bool(true)
var_dump(tableExists($pdo, 'orders', $dbName)); // bool(false)
```

---

## 70. PDO — INSERT e lastInsertId()

### INSERT simples com prepared statement

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

/**
 * Insere um novo usuário e retorna o ID gerado.
 *
 * @throws \RuntimeException Se o e-mail já existir (violação de UNIQUE)
 *
 * @return int ID do usuário inserido
 */
function insertUser(\PDO $pdo, string $name, string $email, string $password): int
{
    // ✅ SEMPRE hash antes de armazenar — nunca texto plano
    $hash = password_hash($password, PASSWORD_ARGON2ID, [
        'memory_cost' => 65536, // 64 MB
        'time_cost'   => 4,
        'threads'     => 3,
    ]);

    $stmt = $pdo->prepare(
        'INSERT INTO users (name, email, password_hash, role)
         VALUES (:name, :email, :hash, :role)'
    );

    try {
        $stmt->execute([
            'name'  => $name,
            'email' => $email,
            'hash'  => $hash,
            'role'  => 'viewer',
        ]);
    } catch (\PDOException $e) {
        // Código 23000 = violação de integridade (UNIQUE, FK, NOT NULL...)
        if ($e->getCode() === '23000') {
            throw new \RuntimeException("E-mail já cadastrado: {$email}");
        }

        throw $e; // Re-lança erros inesperados
    }

    // ✅ lastInsertId() retorna o AUTO_INCREMENT gerado
    return (int) $pdo->lastInsertId();
}

// Uso
try {
    $userId = insertUser($pdo, 'Ana Silva', 'ana@example.com', 'senha_segura_123');
    echo "Usuário criado com ID: {$userId}";
} catch (\RuntimeException $e) {
    echo 'Erro: ' . htmlspecialchars($e->getMessage(), ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
```

### INSERT com dados vindos de formulário — fluxo completo seguro

```php
<?php

declare(strict_types=1);

// Validação e sanitização dos dados do formulário
function processRegistration(\PDO $pdo, array $postData): array
{
    $errors = [];
    $data   = [];

    // Nome
    $name = trim($postData['name'] ?? '');
    if (mb_strlen($name) < 2 || mb_strlen($name) > 100) {
        $errors['name'] = 'Nome deve ter entre 2 e 100 caracteres.';
    } else {
        $data['name'] = $name;
    }

    // E-mail
    $email = filter_var(trim($postData['email'] ?? ''), FILTER_VALIDATE_EMAIL);
    if ($email === false) {
        $errors['email'] = 'Informe um e-mail válido.';
    } else {
        $data['email'] = strtolower($email);
    }

    // Senha
    $password = $postData['password'] ?? '';
    if (mb_strlen($password) < 8) {
        $errors['password'] = 'Senha deve ter ao menos 8 caracteres.';
    } else {
        $data['password'] = $password;
    }

    if (!empty($errors)) {
        return ['success' => false, 'errors' => $errors];
    }

    // ✅ Dados validados — persiste no banco
    try {
        $userId = insertUser($pdo, $data['name'], $data['email'], $data['password']);
        return ['success' => true, 'userId' => $userId];
    } catch (\RuntimeException $e) {
        return ['success' => false, 'errors' => ['email' => $e->getMessage()]];
    }
}

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $result = processRegistration($pdo, $_POST);

    if ($result['success']) {
        // ✅ Post/Redirect/Get — evita re-submissão ao recarregar
        header('Location: /perfil.php?id=' . $result['userId']);
        exit;
    }

    // Exibe erros
    foreach ($result['errors'] as $field => $message) {
        echo htmlspecialchars("{$field}: {$message}", ENT_QUOTES | ENT_HTML5, 'UTF-8');
    }
}
```

### UPDATE e DELETE com rowCount()

```php
<?php

declare(strict_types=1);

// UPDATE — atualiza e verifica se algo mudou
function updateUserEmail(\PDO $pdo, int $userId, string $newEmail): bool
{
    $email = filter_var($newEmail, FILTER_VALIDATE_EMAIL);

    if ($email === false) {
        throw new \InvalidArgumentException('E-mail inválido.');
    }

    $stmt = $pdo->prepare(
        'UPDATE users SET email = :email, updated_at = NOW() WHERE id = :id AND active = 1'
    );

    $stmt->execute(['email' => strtolower($email), 'id' => $userId]);

    // rowCount() — número de linhas afetadas (0 se nada mudou)
    return $stmt->rowCount() > 0;
}

// DELETE seguro — verifica que a linha pertence ao usuário correto
function deletePost(\PDO $pdo, int $postId, int $ownerId): bool
{
    // ✅ Sempre inclua a verificação de dono na query — autorização no banco
    $stmt = $pdo->prepare('DELETE FROM posts WHERE id = :post_id AND user_id = :owner_id');
    $stmt->execute(['post_id' => $postId, 'owner_id' => $ownerId]);

    return $stmt->rowCount() > 0;
}

var_dump(updateUserEmail($pdo, 1, 'novo@example.com')); // bool(true) ou false
var_dump(deletePost($pdo, 5, 1));                        // bool(true) se deletou
```

---

## 71. PDO — Inserindo Múltiplos Registros

Inserir múltiplos registros eficientemente requer atenção à segurança e à performance.

### Prepared statement reutilizado em loop — forma recomendada

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

/**
 * Insere múltiplos usuários reutilizando o mesmo prepared statement.
 *
 * Vantagens sobre múltiplos exec():
 * - Prepara a query apenas UMA vez — menor overhead no servidor
 * - Executa N vezes com diferentes parâmetros — eficiente
 * - Cada execução é individualmente segura contra SQL Injection
 *
 * @param array<array{name: string, email: string, role: string}> $users
 *
 * @return int Número de registros inseridos com sucesso
 */
function insertMultipleUsers(\PDO $pdo, array $users): int
{
    $stmt = $pdo->prepare(
        'INSERT INTO users (name, email, password_hash, role)
         VALUES (:name, :email, :hash, :role)'
    );

    $inserted = 0;

    // ✅ Transação — todos ou nenhum
    $pdo->beginTransaction();

    try {
        foreach ($users as $user) {
            // Valida cada usuário antes de inserir
            if (empty($user['name']) || empty($user['email'])) {
                continue; // Pula inválidos (ou lance exceção se preferir fail-fast)
            }

            $email = filter_var(trim($user['email']), FILTER_VALIDATE_EMAIL);

            if ($email === false) {
                continue;
            }

            // Senha temporária aleatória (deve ser trocada no primeiro login)
            $tempPassword = bin2hex(random_bytes(16));
            $hash = password_hash($tempPassword, PASSWORD_ARGON2ID);

            $stmt->execute([
                'name'  => trim($user['name']),
                'email' => strtolower($email),
                'hash'  => $hash,
                'role'  => $user['role'] ?? 'viewer',
            ]);

            $inserted++;
        }

        $pdo->commit();
        return $inserted;

    } catch (\Throwable $e) {
        $pdo->rollBack();
        throw new \RuntimeException(
            "Falha ao inserir usuários em lote: {$e->getMessage()}",
            previous: $e,
        );
    }
}

// Uso
$usersToImport = [
    ['name' => 'Ana Silva',   'email' => 'ana@example.com',   'role' => 'editor'],
    ['name' => 'Carlos Lima', 'email' => 'carlos@example.com', 'role' => 'viewer'],
    ['name' => 'Maria Souza', 'email' => 'maria@example.com',  'role' => 'admin'],
];

$count = insertMultipleUsers($pdo, $usersToImport);
echo "Inseridos: {$count} usuários.";
```

### INSERT em lote com VALUES múltiplos — alta performance

```php
<?php

declare(strict_types=1);

/**
 * Insere registros em lote usando VALUES múltiplos em uma única query.
 * Muito mais rápido que N inserts individuais para grandes volumes.
 *
 * ✅ Ainda usa prepared statements com parâmetros — seguro contra SQL Injection
 *
 * @param array<array{name: string, email: string}> $records
 */
function bulkInsertUsers(\PDO $pdo, array $records): int
{
    if (empty($records)) {
        return 0;
    }

    // Limita o tamanho do lote para evitar timeout e uso excessivo de memória
    $chunks = array_chunk($records, 500); // Máximo 500 por query
    $totalInserted = 0;

    $pdo->beginTransaction();

    try {
        foreach ($chunks as $chunk) {
            // Monta os placeholders: (:name0, :email0, :hash0), (:name1, :email1, :hash1), ...
            $placeholders = [];
            $bindings     = [];

            foreach ($chunk as $index => $record) {
                $email = filter_var(trim($record['email'] ?? ''), FILTER_VALIDATE_EMAIL);

                if ($email === false || empty($record['name'])) {
                    continue;
                }

                $placeholders[] = "(:name{$index}, :email{$index}, :hash{$index})";
                $bindings["name{$index}"]  = trim($record['name']);
                $bindings["email{$index}"] = strtolower($email);
                $bindings["hash{$index}"]  = password_hash(
                    bin2hex(random_bytes(16)),
                    PASSWORD_ARGON2ID
                );
            }

            if (empty($placeholders)) {
                continue;
            }

            $sql  = 'INSERT IGNORE INTO users (name, email, password_hash) VALUES '
                  . implode(', ', $placeholders);
            $stmt = $pdo->prepare($sql);
            $stmt->execute($bindings);
            $totalInserted += $stmt->rowCount();
        }

        $pdo->commit();
        return $totalInserted;

    } catch (\Throwable $e) {
        $pdo->rollBack();
        throw new \RuntimeException('Falha no bulk insert: ' . $e->getMessage(), previous: $e);
    }
}
```

### Upsert — INSERT ou UPDATE se já existir

```php
<?php

declare(strict_types=1);

/**
 * Insere ou atualiza (upsert) usando ON DUPLICATE KEY UPDATE.
 * Útil para sincronização de dados externos.
 */
function upsertUser(\PDO $pdo, string $name, string $email): int
{
    $stmt = $pdo->prepare(
        'INSERT INTO users (name, email, password_hash)
         VALUES (:name, :email, :hash)
         ON DUPLICATE KEY UPDATE
             name       = VALUES(name),
             updated_at = NOW()'
    );

    $stmt->execute([
        'name'  => $name,
        'email' => strtolower($email),
        'hash'  => password_hash(bin2hex(random_bytes(16)), PASSWORD_ARGON2ID),
    ]);

    // lastInsertId() retorna 0 em UPDATE, > 0 em INSERT
    $lastId = (int) $pdo->lastInsertId();
    return $lastId > 0 ? $lastId : 0;
}
```

---

## 72. PDO — Prepared Statements em Profundidade

Prepared statements são a **única forma segura** de executar queries com dados externos.
Eles separam a estrutura SQL dos dados, eliminando SQL Injection.

### Como funcionam os prepared statements

```
1. PREPARE  → O servidor MySQL analisa e compila a query template UMA VEZ
2. BIND     → Os parâmetros são enviados separadamente (protocolo binário)
3. EXECUTE  → O servidor substitui os parâmetros e executa com segurança
4. REPEAT   → A mesma query pode ser executada N vezes com dados diferentes
               sem re-compilação (ganho de performance)
```

### Parâmetros nomeados vs posicionais

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

// ── Parâmetros NOMEADOS — preferidos por clareza ─────────────────────────────
$stmt = $pdo->prepare(
    'SELECT * FROM users WHERE role = :role AND active = :active ORDER BY name'
);

// execute() com array associativo — mais legível
$stmt->execute(['role' => 'admin', 'active' => 1]);
$admins = $stmt->fetchAll();

// ── Parâmetros POSICIONAIS — mais verbosos, úteis em queries geradas ──────────
$stmt = $pdo->prepare(
    'SELECT * FROM users WHERE role = ? AND active = ? ORDER BY name'
);

// execute() com array indexado — ordem importa!
$stmt->execute(['admin', 1]);
$admins = $stmt->fetchAll();

// ── bindParam() vs bindValue() ────────────────────────────────────────────────

// bindParam() — vincula por REFERÊNCIA — valor lido na hora do execute()
$role   = 'admin';
$active = 1;

$stmt = $pdo->prepare(
    'SELECT * FROM users WHERE role = :role AND active = :active'
);
$stmt->bindParam(':role',   $role,   \PDO::PARAM_STR);
$stmt->bindParam(':active', $active, \PDO::PARAM_INT);

$role = 'editor'; // ✅ Muda ANTES do execute — bindParam captura a mudança
$stmt->execute();

// bindValue() — vincula o VALOR imediato — imutável após bind
$stmt->bindValue(':role',   'viewer', \PDO::PARAM_STR);
$stmt->bindValue(':active', 1,        \PDO::PARAM_INT);
// Mudar $role depois não afeta — valor já foi capturado
$stmt->execute();
```

### Tipos de parâmetros PDO

```php
<?php

declare(strict_types=1);

// PDO::PARAM_* informa o driver o tipo real do dado
// O driver usa essa informação para escapar corretamente

$types = [
    \PDO::PARAM_STR  => 'string (padrão)',
    \PDO::PARAM_INT  => 'integer',
    \PDO::PARAM_BOOL => 'boolean',
    \PDO::PARAM_NULL => 'NULL',
    \PDO::PARAM_LOB  => 'Large Object (BLOB)',
];

// Exemplo com tipo explícito — sempre preferível
$stmt = $pdo->prepare(
    'INSERT INTO posts (user_id, title, body, published)
     VALUES (:user_id, :title, :body, :published)'
);

$stmt->bindValue(':user_id',   42,             \PDO::PARAM_INT);
$stmt->bindValue(':title',     'Título do Post', \PDO::PARAM_STR);
$stmt->bindValue(':body',      'Conteúdo...',    \PDO::PARAM_STR);
$stmt->bindValue(':published', true,             \PDO::PARAM_BOOL);

$stmt->execute();

// ✅ Alternativa mais concisa — execute() infere tipos automaticamente
// (Aceitável para a maioria dos casos com PDO::ATTR_EMULATE_PREPARES = false)
$stmt = $pdo->prepare(
    'INSERT INTO posts (user_id, title, body, published)
     VALUES (:user_id, :title, :body, :published)'
);

$stmt->execute([
    'user_id'   => 42,
    'title'     => 'Título do Post',
    'body'      => 'Conteúdo...',
    'published' => 0,
]);
```

### SELECT com fetch() e fetchAll()

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

// ── fetchAll() — todos os resultados em memória ───────────────────────────────
function listActiveUsers(\PDO $pdo, string $role = 'viewer'): array
{
    $stmt = $pdo->prepare(
        'SELECT id, name, email, created_at
         FROM users
         WHERE active = 1 AND role = :role
         ORDER BY name
         LIMIT 100'
    );
    $stmt->execute(['role' => $role]);

    return $stmt->fetchAll(); // array de arrays associativos
}

// ── fetch() — uma linha por vez (eficiente para grandes resultados) ───────────
function streamLargeResult(\PDO $pdo): void
{
    $stmt = $pdo->prepare('SELECT id, name, email FROM users WHERE active = 1 ORDER BY id');
    $stmt->execute();

    while ($row = $stmt->fetch()) {
        // Processa uma linha por vez — sem carregar tudo na memória
        $name = htmlspecialchars($row['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
        echo "{$row['id']}: {$name}";
    }
}

// ── fetchColumn() — valor único (COUNT, SUM, valor escalar) ──────────────────
function countUsersByRole(\PDO $pdo, string $role): int
{
    $stmt = $pdo->prepare('SELECT COUNT(*) FROM users WHERE role = :role AND active = 1');
    $stmt->execute(['role' => $role]);

    return (int) $stmt->fetchColumn();
}

// ── FETCH_CLASS — mapeia resultado para objeto ────────────────────────────────
final class UserDto
{
    public int    $id;
    public string $name;
    public string $email;
    public string $createdAt;
}

function findUserDtos(\PDO $pdo): array
{
    $stmt = $pdo->prepare('SELECT id, name, email, created_at AS createdAt FROM users LIMIT 10');
    $stmt->execute();

    // ✅ Mapeia cada linha para um objeto UserDto automaticamente
    return $stmt->fetchAll(\PDO::FETCH_CLASS, UserDto::class);
}

$users = findUserDtos($pdo);

foreach ($users as $user) {
    echo "{$user->id}: {$user->name} ({$user->email})";
}
```

### Query builder simples — queries dinâmicas seguras

```php
<?php

declare(strict_types=1);

/**
 * Constrói queries dinâmicas com segurança usando prepared statements.
 * Útil para filtros de busca onde colunas e condições variam.
 */
final class UserQuery
{
    private array  $conditions = [];
    private array  $bindings   = [];
    private string $orderBy    = 'name ASC';
    private int    $limit      = 50;
    private int    $offset     = 0;

    public function whereRole(string $role): self
    {
        $clone = clone $this;
        $clone->conditions[]      = 'role = :role';
        $clone->bindings['role']  = $role;
        return $clone;
    }

    public function whereActive(bool $active = true): self
    {
        $clone = clone $this;
        $clone->conditions[]       = 'active = :active';
        $clone->bindings['active'] = (int) $active;
        return $clone;
    }

    public function search(string $term): self
    {
        $clone = clone $this;
        $clone->conditions[]      = '(name LIKE :search OR email LIKE :search)';
        $clone->bindings['search'] = '%' . $term . '%';
        return $clone;
    }

    public function orderBy(string $column, string $direction = 'ASC'): self
    {
        // ✅ Whitelist de colunas — nunca interpolação direta
        $allowedColumns    = ['name', 'email', 'created_at', 'role'];
        $allowedDirections = ['ASC', 'DESC'];

        if (!in_array($column, $allowedColumns, strict: true)) {
            throw new \InvalidArgumentException("Coluna inválida: {$column}");
        }

        if (!in_array(strtoupper($direction), $allowedDirections, strict: true)) {
            throw new \InvalidArgumentException("Direção inválida: {$direction}");
        }

        $clone          = clone $this;
        $clone->orderBy = "{$column} " . strtoupper($direction);
        return $clone;
    }

    public function paginate(int $limit, int $page = 1): self
    {
        $clone         = clone $this;
        $clone->limit  = max(1, min($limit, 100)); // Entre 1 e 100
        $clone->offset = ($page - 1) * $clone->limit;
        return $clone;
    }

    public function fetch(\PDO $pdo): array
    {
        $where = !empty($this->conditions)
            ? 'WHERE ' . implode(' AND ', $this->conditions)
            : '';

        $sql  = "SELECT id, name, email, role, created_at FROM users
                 {$where}
                 ORDER BY {$this->orderBy}
                 LIMIT {$this->limit} OFFSET {$this->offset}";

        $stmt = $pdo->prepare($sql);
        $stmt->execute($this->bindings);

        return $stmt->fetchAll();
    }

    public function count(\PDO $pdo): int
    {
        $where = !empty($this->conditions)
            ? 'WHERE ' . implode(' AND ', $this->conditions)
            : '';

        $sql  = "SELECT COUNT(*) FROM users {$where}";
        $stmt = $pdo->prepare($sql);
        $stmt->execute($this->bindings);

        return (int) $stmt->fetchColumn();
    }
}

// ── Uso com interface fluente ─────────────────────────────────────────────────
$query = (new UserQuery())
    ->whereActive()
    ->whereRole('editor')
    ->search('ana')
    ->orderBy('created_at', 'DESC')
    ->paginate(limit: 20, page: 2);

$users      = $query->fetch($pdo);
$totalCount = $query->count($pdo);

echo "Total: {$totalCount} | Exibindo: " . count($users);

foreach ($users as $user) {
    echo htmlspecialchars($user['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
```

### Resumo — boas práticas finais com PDO

```php
<?php

declare(strict_types=1);

// ✅ Checklist final de PDO seguro

// 1. Sempre use ERRMODE_EXCEPTION
// 2. Sempre use EMULATE_PREPARES = false
// 3. charset=utf8mb4 no DSN
// 4. NUNCA concatene dados do usuário em SQL — use :param ou ?
// 5. NUNCA exiba mensagens de PDOException ao usuário final
// 6. Use transações para operações que dependem umas das outras
// 7. Use fetchColumn() para valores escalares (COUNT, MAX, etc.)
// 8. Use FETCH_CLASS para mapear para objetos de domínio
// 9. Feche statements com $stmt = null quando não precisar mais
// 10. Use variáveis de ambiente para credenciais — nunca hard-coded

// Exemplo de query segura completa:
function safeQuery(\PDO $pdo, int $userId): ?array
{
    // Prepared statement com parâmetro nomeado
    $stmt = $pdo->prepare(
        'SELECT id, name, email, role
         FROM users
         WHERE id = :id AND active = 1
         LIMIT 1'
    );

    $stmt->execute(['id' => $userId]); // Tipo inferido corretamente

    $result = $stmt->fetch();

    $stmt = null; // Libera o statement

    return $result !== false ? $result : null;
}

$user = safeQuery($pdo, 1);

if ($user !== null) {
    // ✅ Escape sempre no output
    echo htmlspecialchars($user['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
} else {
    echo 'Usuário não encontrado.';
}
```

---

## 73. PDO — SELECT (Consultando Dados)

`SELECT` é a operação de leitura mais comum. Em PDO, usamos `prepare()` + `execute()`
para qualquer query com dados externos, e `query()` apenas para queries completamente
estáticas (sem parâmetros do usuário).

### SELECT básico — colunas específicas

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

/**
 * Lista todos os usuários ativos com colunas selecionadas.
 *
 * @return array<int, array{id: int, name: string, email: string, role: string}>
 */
function listUsers(\PDO $pdo): array
{
    // ✅ Query estática sem parâmetros — query() é adequado
    $stmt = $pdo->query(
        'SELECT id, name, email, role, created_at
         FROM users
         WHERE active = 1
         ORDER BY name ASC'
    );

    // fetchAll() carrega todos na memória — ok para listas pequenas/médias
    return $stmt->fetchAll();
}

$users = listUsers($pdo);

if (empty($users)) {
    echo 'Nenhum usuário encontrado.';
} else {
    echo 'Total: ' . count($users) . ' usuários';

    foreach ($users as $user) {
        // ✅ Sempre escape antes de exibir dados do banco no HTML
        $id    = (int)    $user['id'];
        $name  = htmlspecialchars((string) $user['name'],  ENT_QUOTES | ENT_HTML5, 'UTF-8');
        $email = htmlspecialchars((string) $user['email'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
        $role  = htmlspecialchars((string) $user['role'],  ENT_QUOTES | ENT_HTML5, 'UTF-8');

        echo "#{$id} {$name} ({$email}) — {$role}";
    }
}
```

### SELECT em tabela HTML — renderização segura

```php
<?php

declare(strict_types=1);

$pdo   = Database::getInstance();
$users = listUsers($pdo);

// Função auxiliar de escape — evita repetição
function e(string $value): string
{
    return htmlspecialchars($value, ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
?>

<?php if (empty($users)): ?>
    <p>Nenhum registro encontrado.</p>
<?php else: ?>
    <table>
        <thead>
            <tr>
                <th scope="col">ID</th>
                <th scope="col">Nome</th>
                <th scope="col">E-mail</th>
                <th scope="col">Papel</th>
                <th scope="col">Cadastrado em</th>
            </tr>
        </thead>
        <tbody>
            <?php foreach ($users as $user): ?>
                <tr>
                    <td><?= e((string) $user['id']) ?></td>
                    <td><?= e($user['name']) ?></td>
                    <td><?= e($user['email']) ?></td>
                    <td><?= e($user['role']) ?></td>
                    <td><?= e($user['created_at']) ?></td>
                </tr>
            <?php endforeach; ?>
        </tbody>
    </table>
<?php endif; ?>
```

### SELECT por ID — busca de registro único

```php
<?php

declare(strict_types=1);

/**
 * Busca um usuário pelo ID.
 * Retorna null se não encontrado ou se estiver inativo.
 *
 * @return array{id: int, name: string, email: string, role: string}|null
 */
function findUserById(\PDO $pdo, int $id): ?array
{
    $stmt = $pdo->prepare(
        'SELECT id, name, email, role, created_at
         FROM users
         WHERE id = :id AND active = 1
         LIMIT 1'
    );
    $stmt->execute(['id' => $id]);

    $row = $stmt->fetch();

    return $row !== false ? $row : null;
}

// Uso — com validação do parâmetro antes de consultar
$rawId = filter_input(INPUT_GET, 'id', FILTER_VALIDATE_INT, [
    'options' => ['min_range' => 1],
]);

if ($rawId === false || $rawId === null) {
    http_response_code(400);
    echo 'ID inválido.';
    exit;
}

$user = findUserById($pdo, $rawId);

if ($user === null) {
    http_response_code(404);
    echo 'Usuário não encontrado.';
    exit;
}

echo 'Nome: ' . htmlspecialchars($user['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
```

### SELECT com fetch() — streaming de grandes resultados

```php
<?php

declare(strict_types=1);

/**
 * Exporta todos os usuários para CSV sem carregar tudo na memória.
 * Ideal para exports de relatórios com milhares de registros.
 */
function exportUsersCsv(\PDO $pdo): void
{
    // Headers HTTP para download do arquivo
    header('Content-Type: text/csv; charset=UTF-8');
    header('Content-Disposition: attachment; filename="usuarios_' . date('Y-m-d') . '.csv"');

    // BOM UTF-8 para compatibilidade com Excel
    echo "\xEF\xBB\xBF";

    // Cabeçalho CSV
    echo "ID,Nome,E-mail,Papel,Cadastrado em\n";

    $stmt = $pdo->query(
        'SELECT id, name, email, role, created_at
         FROM users
         WHERE active = 1
         ORDER BY id'
    );

    // ✅ fetch() processa uma linha por vez — memória constante independente do volume
    while ($row = $stmt->fetch()) {
        echo implode(',', [
            $row['id'],
            '"' . str_replace('"', '""', $row['name'])  . '"', // Escapa aspas no CSV
            '"' . str_replace('"', '""', $row['email']) . '"',
            $row['role'],
            $row['created_at'],
        ]) . "\n";
    }
}
```

### fetchColumn() — valor escalar único

```php
<?php

declare(strict_types=1);

// COUNT — total de registros
function countUsers(\PDO $pdo, string $role = '%'): int
{
    $stmt = $pdo->prepare(
        'SELECT COUNT(*) FROM users WHERE role LIKE :role AND active = 1'
    );
    $stmt->execute(['role' => $role]);

    return (int) $stmt->fetchColumn();
}

echo 'Total de usuários: ' . countUsers($pdo);
echo 'Admins: '            . countUsers($pdo, 'admin');

// Verifica existência sem buscar dados desnecessários
function emailExists(\PDO $pdo, string $email): bool
{
    $stmt = $pdo->prepare(
        'SELECT COUNT(*) FROM users WHERE email = :email'
    );
    $stmt->execute(['email' => strtolower($email)]);

    return (int) $stmt->fetchColumn() > 0;
}

var_dump(emailExists($pdo, 'ana@example.com')); // bool(true) ou false
```

---

## 74. PDO — WHERE (Filtrando Dados)

A cláusula `WHERE` filtra registros. Com PDO, **todos os valores na condição
devem ser parâmetros vinculados** — nunca interpolados na string SQL.

### WHERE simples com parâmetro nomeado

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

/**
 * Busca usuários por papel (role).
 *
 * @return array<int, array<string, mixed>>
 */
function findUsersByRole(\PDO $pdo, string $role): array
{
    // ✅ :role é o placeholder — valor nunca toca a string SQL
    $stmt = $pdo->prepare(
        'SELECT id, name, email, created_at
         FROM users
         WHERE role = :role AND active = 1
         ORDER BY name'
    );
    $stmt->execute(['role' => $role]);

    return $stmt->fetchAll();
}

$editors = findUsersByRole($pdo, 'editor');
$admins  = findUsersByRole($pdo, 'admin');

// ❌ NUNCA faça isso — SQL Injection!
// $role  = $_GET['role'];
// $stmt  = $pdo->query("SELECT * FROM users WHERE role = '{$role}'");
```

### WHERE com múltiplas condições

```php
<?php

declare(strict_types=1);

/**
 * Busca usuários por intervalo de data de cadastro.
 */
function findUsersByDateRange(
    \PDO              $pdo,
    \DateTimeImmutable $from,
    \DateTimeImmutable $to,
): array {
    $stmt = $pdo->prepare(
        'SELECT id, name, email, role, created_at
         FROM users
         WHERE active = 1
           AND created_at BETWEEN :from AND :to
         ORDER BY created_at DESC'
    );

    $stmt->execute([
        'from' => $from->format('Y-m-d 00:00:00'),
        'to'   => $to->format('Y-m-d 23:59:59'),
    ]);

    return $stmt->fetchAll();
}

$tz   = new \DateTimeZone('America/Sao_Paulo');
$from = new \DateTimeImmutable('first day of this month', $tz);
$to   = new \DateTimeImmutable('last day of this month', $tz);

$thisMonthUsers = findUsersByDateRange($pdo, $from, $to);
echo 'Cadastros este mês: ' . count($thisMonthUsers);
```

### WHERE com IN — múltiplos valores

```php
<?php

declare(strict_types=1);

/**
 * Busca usuários por lista de IDs.
 * Abordagem segura com placeholders dinâmicos para cláusula IN.
 *
 * @param int[] $ids
 *
 * @return array<int, array<string, mixed>>
 */
function findUsersByIds(\PDO $pdo, array $ids): array
{
    if (empty($ids)) {
        return [];
    }

    // Valida e sanitiza cada ID
    $validIds = array_filter(
        array_map('intval', $ids),
        fn(int $id): bool => $id > 0
    );

    if (empty($validIds)) {
        return [];
    }

    // ✅ Cria placeholders dinâmicos: :id0, :id1, :id2, ...
    $placeholders = implode(
        ', ',
        array_map(fn(int $i): string => ":id{$i}", array_keys($validIds))
    );

    $stmt = $pdo->prepare(
        "SELECT id, name, email, role
         FROM users
         WHERE id IN ({$placeholders}) AND active = 1"
    );

    // Vincula cada ID com seu placeholder
    foreach (array_values($validIds) as $index => $id) {
        $stmt->bindValue(":id{$index}", $id, \PDO::PARAM_INT);
    }

    $stmt->execute();

    return $stmt->fetchAll();
}

$users = findUsersByIds($pdo, [1, 3, 5, 7, 9]);
echo 'Encontrados: ' . count($users);
```

### WHERE com LIKE — busca por texto

```php
<?php

declare(strict_types=1);

/**
 * Busca usuários por nome ou e-mail (busca full-text simples).
 * Escapa os caracteres especiais de LIKE antes de usar como parâmetro.
 */
function searchUsers(\PDO $pdo, string $term, int $limit = 20): array
{
    if (mb_strlen(trim($term)) < 2) {
        return []; // Termo muito curto — não busca
    }

    // ✅ Escapa caracteres especiais do LIKE: % e _ têm significado especial
    $escapedTerm = str_replace(['\\', '%', '_'], ['\\\\', '\\%', '\\_'], trim($term));
    $pattern     = "%{$escapedTerm}%";

    $stmt = $pdo->prepare(
        'SELECT id, name, email, role
         FROM users
         WHERE active = 1
           AND (name LIKE :pattern OR email LIKE :pattern)
         ORDER BY name
         LIMIT :limit'
    );

    // bindValue() necessário para LIMIT — PDO trata como string sem PARAM_INT
    $stmt->bindValue(':pattern', $pattern,  \PDO::PARAM_STR);
    $stmt->bindValue(':limit',   $limit,    \PDO::PARAM_INT);
    $stmt->execute();

    return $stmt->fetchAll();
}

// Lê o termo de busca do GET com sanitização
$searchTerm = filter_input(INPUT_GET, 'q', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
$results    = searchUsers($pdo, $searchTerm);

foreach ($results as $user) {
    echo htmlspecialchars($user['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
```

### WHERE com condições dinâmicas — busca por filtros variáveis

```php
<?php

declare(strict_types=1);

/**
 * Busca de usuários com filtros opcionais.
 * Monta a query dinamicamente apenas com as condições fornecidas.
 *
 * @param array{role?: string, active?: bool, search?: string} $filters
 *
 * @return array<int, array<string, mixed>>
 */
function filterUsers(\PDO $pdo, array $filters, int $limit = 50): array
{
    $conditions = ['1 = 1']; // Base sempre verdadeira — simplifica o implode
    $bindings   = [];

    if (isset($filters['role'])) {
        $conditions[]        = 'role = :role';
        $bindings['role']    = $filters['role'];
    }

    if (isset($filters['active'])) {
        $conditions[]        = 'active = :active';
        $bindings['active']  = (int) $filters['active'];
    }

    if (isset($filters['search']) && mb_strlen($filters['search']) >= 2) {
        $term                 = str_replace(['\\', '%', '_'], ['\\\\', '\\%', '\\_'], $filters['search']);
        $conditions[]         = '(name LIKE :search OR email LIKE :search)';
        $bindings['search']   = "%{$term}%";
    }

    $sql = 'SELECT id, name, email, role, created_at FROM users WHERE '
         . implode(' AND ', $conditions)
         . ' ORDER BY name LIMIT ' . max(1, min($limit, 100));

    $stmt = $pdo->prepare($sql);
    $stmt->execute($bindings);

    return $stmt->fetchAll();
}

// Filtros vindos da URL — ex: /users?role=admin&active=1&q=ana
$results = filterUsers($pdo, [
    'role'   => 'admin',
    'active' => true,
    'search' => 'ana',
]);

echo 'Resultados: ' . count($results);
```

---

## 75. PDO — ORDER BY, LIMIT e Paginação

`ORDER BY` define a ordem dos resultados. `LIMIT` e `OFFSET` permitem paginar
grandes conjuntos de dados de forma eficiente.

### ORDER BY com coluna da whitelist

```php
<?php

declare(strict_types=1);

/**
 * Lista usuários com ordenação dinâmica e segura.
 * A coluna de ordenação NUNCA vem diretamente do usuário sem whitelist.
 *
 * @return array<int, array<string, mixed>>
 */
function listUsersSorted(\PDO $pdo, string $sortColumn = 'name', string $direction = 'ASC'): array
{
    // ✅ Whitelist OBRIGATÓRIA — nunca interpole coluna ou direção diretamente
    $allowedColumns    = ['name', 'email', 'role', 'created_at'];
    $allowedDirections = ['ASC', 'DESC'];

    $column    = in_array($sortColumn, $allowedColumns, strict: true) ? $sortColumn : 'name';
    $direction = in_array(strtoupper($direction), $allowedDirections, strict: true)
        ? strtoupper($direction)
        : 'ASC';

    // ✅ Coluna e direção validadas — interpolação segura
    $stmt = $pdo->prepare(
        "SELECT id, name, email, role, created_at
         FROM users
         WHERE active = 1
         ORDER BY {$column} {$direction}"
    );
    $stmt->execute();

    return $stmt->fetchAll();
}

// Parâmetros de ordenação da URL — ex: /users?sort=email&dir=desc
$sort = filter_input(INPUT_GET, 'sort', FILTER_SANITIZE_SPECIAL_CHARS) ?? 'name';
$dir  = filter_input(INPUT_GET, 'dir',  FILTER_SANITIZE_SPECIAL_CHARS) ?? 'ASC';

$users = listUsersSorted($pdo, $sort, $dir);
```

### LIMIT e OFFSET — paginação simples

```php
<?php

declare(strict_types=1);

/**
 * Retorna uma página de usuários com metadados de paginação.
 *
 * @return array{
 *   data: array<int, array<string, mixed>>,
 *   total: int,
 *   page: int,
 *   perPage: int,
 *   totalPages: int,
 *   hasPrev: bool,
 *   hasNext: bool,
 * }
 */
function paginateUsers(\PDO $pdo, int $page = 1, int $perPage = 10): array
{
    // Garante valores válidos
    $page    = max(1, $page);
    $perPage = max(1, min($perPage, 100)); // Entre 1 e 100 por página
    $offset  = ($page - 1) * $perPage;

    // Conta o total para calcular o número de páginas
    $totalStmt = $pdo->query('SELECT COUNT(*) FROM users WHERE active = 1');
    $total     = (int) $totalStmt->fetchColumn();
    $totalPages = (int) ceil($total / $perPage);

    // ✅ LIMIT e OFFSET com bindValue PARAM_INT — PDO trataria como string sem isso
    $stmt = $pdo->prepare(
        'SELECT id, name, email, role, created_at
         FROM users
         WHERE active = 1
         ORDER BY name ASC
         LIMIT :limit OFFSET :offset'
    );
    $stmt->bindValue(':limit',  $perPage, \PDO::PARAM_INT);
    $stmt->bindValue(':offset', $offset,  \PDO::PARAM_INT);
    $stmt->execute();

    return [
        'data'       => $stmt->fetchAll(),
        'total'      => $total,
        'page'       => $page,
        'perPage'    => $perPage,
        'totalPages' => $totalPages,
        'hasPrev'    => $page > 1,
        'hasNext'    => $page < $totalPages,
    ];
}

// Lê a página da URL: /users?page=3
$currentPage = filter_input(INPUT_GET, 'page', FILTER_VALIDATE_INT, [
    'options' => ['default' => 1, 'min_range' => 1],
]) ?? 1;

$result = paginateUsers($pdo, page: $currentPage, perPage: 15);

echo "Página {$result['page']} de {$result['totalPages']} ({$result['total']} total)";

foreach ($result['data'] as $user) {
    echo htmlspecialchars($user['name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
```

### Renderizando controles de paginação

```php
<?php declare(strict_types=1); ?>

<?php if ($result['totalPages'] > 1): ?>
<nav aria-label="Paginação">
    <?php if ($result['hasPrev']): ?>
        <a href="?page=<?= $result['page'] - 1 ?>">← Anterior</a>
    <?php endif; ?>

    <?php for ($p = 1; $p <= $result['totalPages']; $p++): ?>
        <?php if ($p === $result['page']): ?>
            <strong><?= $p ?></strong>
        <?php else: ?>
            <a href="?page=<?= $p ?>"><?= $p ?></a>
        <?php endif; ?>
    <?php endfor; ?>

    <?php if ($result['hasNext']): ?>
        <a href="?page=<?= $result['page'] + 1 ?>">Próxima →</a>
    <?php endif; ?>
</nav>
<?php endif; ?>
```

### ORDER BY múltiplas colunas e LIMIT combinados

```php
<?php

declare(strict_types=1);

/**
 * Lista posts com ordenação por múltiplas colunas e paginação.
 */
function listPosts(\PDO $pdo, int $page = 1, int $perPage = 10, bool $onlyPublished = true): array
{
    $offset        = ($page - 1) * $perPage;
    $publishedCond = $onlyPublished ? 'AND published = 1' : '';

    $stmt = $pdo->prepare(
        "SELECT p.id, p.title, p.slug, p.created_at, u.name AS author_name
         FROM posts p
         INNER JOIN users u ON u.id = p.user_id
         WHERE u.active = 1 {$publishedCond}
         ORDER BY p.created_at DESC, p.id DESC
         LIMIT :limit OFFSET :offset"
    );

    $stmt->bindValue(':limit',  $perPage, \PDO::PARAM_INT);
    $stmt->bindValue(':offset', $offset,  \PDO::PARAM_INT);
    $stmt->execute();

    return $stmt->fetchAll();
}

$posts = listPosts($pdo, page: 1, perPage: 10);

foreach ($posts as $post) {
    $title  = htmlspecialchars($post['title'],       ENT_QUOTES | ENT_HTML5, 'UTF-8');
    $author = htmlspecialchars($post['author_name'], ENT_QUOTES | ENT_HTML5, 'UTF-8');
    echo "{$title} — por {$author}";
}
```

---

## 76. PDO — DELETE (Excluindo Dados)

`DELETE` remove registros. A cláusula `WHERE` é **obrigatória** — sem ela, toda a
tabela é apagada. Com PDO, sempre use prepared statements.

### DELETE simples por ID

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

/**
 * Exclui um usuário pelo ID.
 *
 * @return bool true se algum registro foi removido
 */
function deleteUser(\PDO $pdo, int $userId): bool
{
    $stmt = $pdo->prepare('DELETE FROM users WHERE id = :id');
    $stmt->execute(['id' => $userId]);

    // rowCount() = número de linhas afetadas
    return $stmt->rowCount() > 0;
}

$deleted = deleteUser($pdo, 3);
var_dump($deleted); // bool(true) se deletou, bool(false) se não encontrou
```

### DELETE com verificação de propriedade (autorização no banco)

```php
<?php

declare(strict_types=1);

/**
 * Deleta um post garantindo que pertence ao usuário autenticado.
 * A verificação de ownership na query previne acesso não autorizado
 * mesmo que o ID venha adulterado da requisição.
 */
function deleteUserPost(\PDO $pdo, int $postId, int $authenticatedUserId): bool
{
    // ✅ Dupla condição: ID do post E ID do dono — autorização no banco
    $stmt = $pdo->prepare(
        'DELETE FROM posts WHERE id = :post_id AND user_id = :owner_id'
    );

    $stmt->execute([
        'post_id'  => $postId,
        'owner_id' => $authenticatedUserId,
    ]);

    return $stmt->rowCount() > 0;
}

// Obtém IDs da requisição com validação estrita
$postId = filter_input(INPUT_POST, 'post_id', FILTER_VALIDATE_INT) ?? 0;
$userId = (int) ($_SESSION['user_id'] ?? 0); // ID do usuário autenticado

if ($postId <= 0 || $userId <= 0) {
    http_response_code(400);
    echo 'Dados inválidos.';
    exit;
}

$result = deleteUserPost($pdo, $postId, $userId);

if ($result) {
    // ✅ Post/Redirect/Get — evita re-submissão
    header('Location: /meus-posts.php?deleted=1');
    exit;
} else {
    http_response_code(404);
    echo 'Post não encontrado ou sem permissão.';
}
```

### Soft delete — marcar como deletado sem remover

```php
<?php

declare(strict_types=1);

/**
 * Soft delete — preserva o registro no banco mas o marca como inativo.
 * Preferível ao DELETE físico em sistemas que precisam de auditoria.
 */
function softDeleteUser(\PDO $pdo, int $userId): bool
{
    $stmt = $pdo->prepare(
        'UPDATE users
         SET active = 0, updated_at = NOW()
         WHERE id = :id AND active = 1'
    );
    $stmt->execute(['id' => $userId]);

    return $stmt->rowCount() > 0;
}

/**
 * Restaura um soft-deleted usuário.
 */
function restoreUser(\PDO $pdo, int $userId): bool
{
    $stmt = $pdo->prepare(
        'UPDATE users
         SET active = 1, updated_at = NOW()
         WHERE id = :id AND active = 0'
    );
    $stmt->execute(['id' => $userId]);

    return $stmt->rowCount() > 0;
}

/**
 * DELETE físico — apenas para limpeza de registros muito antigos.
 * Use com muita cautela e sempre com WHERE restrito.
 */
function purgeOldInactiveUsers(\PDO $pdo, int $daysInactive = 365): int
{
    $stmt = $pdo->prepare(
        'DELETE FROM users
         WHERE active = 0
           AND updated_at < NOW() - INTERVAL :days DAY'
    );
    $stmt->bindValue(':days', $daysInactive, \PDO::PARAM_INT);
    $stmt->execute();

    return $stmt->rowCount();
}

// Soft delete do usuário 5
var_dump(softDeleteUser($pdo, 5)); // bool(true)

// Purga usuários inativos há mais de 2 anos
$purged = purgeOldInactiveUsers($pdo, 730);
echo "Purged: {$purged} usuários antigos";
```

### DELETE em transação — múltiplos registros relacionados

```php
<?php

declare(strict_types=1);

/**
 * Remove um usuário e todos os seus posts de forma atômica.
 * Sem transação, um erro parcial deixaria dados órfãos.
 * (Na prática, use ON DELETE CASCADE na FK — mais robusto)
 */
function deleteUserWithPosts(\PDO $pdo, int $userId): void
{
    $pdo->beginTransaction();

    try {
        // 1. Remove os posts do usuário
        $deletePosts = $pdo->prepare('DELETE FROM posts WHERE user_id = :uid');
        $deletePosts->execute(['uid' => $userId]);
        $postsDeleted = $deletePosts->rowCount();

        // 2. Remove o próprio usuário
        $deleteUser = $pdo->prepare('DELETE FROM users WHERE id = :uid');
        $deleteUser->execute(['uid' => $userId]);

        if ($deleteUser->rowCount() === 0) {
            throw new \RuntimeException("Usuário #{$userId} não encontrado.");
        }

        $pdo->commit();

        echo "Usuário #{$userId} removido com {$postsDeleted} posts.";

    } catch (\Throwable $e) {
        $pdo->rollBack();
        throw new \RuntimeException(
            "Falha ao remover usuário #{$userId}: {$e->getMessage()}",
            previous: $e,
        );
    }
}
```

---

## 77. PDO — UPDATE (Atualizando Dados)

`UPDATE` modifica registros existentes. Assim como `DELETE`, exige `WHERE` —
sem ele, **todos os registros da tabela são atualizados**.

### UPDATE simples com prepared statement

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

/**
 * Atualiza o nome e e-mail de um usuário.
 *
 * @return bool true se algum registro foi modificado
 */
function updateUser(\PDO $pdo, int $userId, string $name, string $email): bool
{
    // Valida o e-mail antes de atualizar
    $validEmail = filter_var(strtolower(trim($email)), FILTER_VALIDATE_EMAIL);

    if ($validEmail === false) {
        throw new \InvalidArgumentException('E-mail inválido.');
    }

    if (mb_strlen(trim($name)) < 2) {
        throw new \InvalidArgumentException('Nome muito curto.');
    }

    $stmt = $pdo->prepare(
        'UPDATE users
         SET name = :name, email = :email, updated_at = NOW()
         WHERE id = :id AND active = 1'
    );

    $stmt->execute([
        'name'  => trim($name),
        'email' => $validEmail,
        'id'    => $userId,
    ]);

    return $stmt->rowCount() > 0;
}

var_dump(updateUser($pdo, 2, 'Maria Doe', 'maria.doe@example.com'));
```

### UPDATE com campos dinâmicos — atualização parcial

```php
<?php

declare(strict_types=1);

/**
 * Atualiza apenas os campos fornecidos (PATCH semântico).
 * Campos não incluídos no array $changes não são tocados.
 *
 * @param array<string, mixed> $changes Campos a atualizar: ['name' => '...', 'role' => '...']
 *
 * @throws \InvalidArgumentException Se $changes estiver vazio ou contiver campo inválido
 */
function patchUser(\PDO $pdo, int $userId, array $changes): bool
{
    if (empty($changes)) {
        throw new \InvalidArgumentException('Nenhum campo para atualizar.');
    }

    // ✅ Whitelist de colunas atualizáveis — nunca interpolação direta
    $allowedFields = ['name', 'email', 'role', 'active'];

    $setClauses = [];
    $bindings   = ['id' => $userId];

    foreach ($changes as $field => $value) {
        if (!in_array($field, $allowedFields, strict: true)) {
            throw new \InvalidArgumentException("Campo não permitido: {$field}");
        }

        $setClauses[]        = "{$field} = :{$field}";
        $bindings[$field]    = $value;
    }

    // Sempre atualiza updated_at
    $setClauses[] = 'updated_at = NOW()';

    $sql  = 'UPDATE users SET ' . implode(', ', $setClauses) . ' WHERE id = :id AND active = 1';
    $stmt = $pdo->prepare($sql);
    $stmt->execute($bindings);

    return $stmt->rowCount() > 0;
}

// Atualiza apenas o papel — sem tocar nos outros campos
var_dump(patchUser($pdo, 2, ['role' => 'editor']));

// Atualiza nome e e-mail ao mesmo tempo
var_dump(patchUser($pdo, 3, ['name' => 'Carlos Novo', 'email' => 'novo@example.com']));
```

### UPDATE com verificação pré-existência

```php
<?php

declare(strict_types=1);

/**
 * Altera a senha do usuário verificando a senha atual.
 *
 * @throws \RuntimeException Se a senha atual estiver incorreta
 */
function changePassword(
    \PDO   $pdo,
    int    $userId,
    string $currentPassword,
    string $newPassword,
): void {
    if (mb_strlen($newPassword) < 8) {
        throw new \InvalidArgumentException('Nova senha deve ter ao menos 8 caracteres.');
    }

    // 1. Busca o hash atual
    $stmt = $pdo->prepare('SELECT password_hash FROM users WHERE id = :id AND active = 1');
    $stmt->execute(['id' => $userId]);
    $row  = $stmt->fetch();

    if ($row === false) {
        throw new \RuntimeException('Usuário não encontrado.');
    }

    // 2. Verifica senha atual — timing-safe
    if (!password_verify($currentPassword, $row['password_hash'])) {
        throw new \RuntimeException('Senha atual incorreta.');
    }

    // 3. Gera novo hash — Argon2id
    $newHash = password_hash($newPassword, PASSWORD_ARGON2ID, [
        'memory_cost' => 65536,
        'time_cost'   => 4,
        'threads'     => 3,
    ]);

    // 4. Atualiza o hash e invalida sessões antigas (opcional)
    $update = $pdo->prepare(
        'UPDATE users
         SET password_hash = :hash, updated_at = NOW()
         WHERE id = :id'
    );
    $update->execute(['hash' => $newHash, 'id' => $userId]);

    // 5. Regenera o ID de sessão para invalidar sessões antigas
    session_regenerate_id(true);
}
```

### UPDATE em massa com transação

```php
<?php

declare(strict_types=1);

/**
 * Desativa em massa usuários que não logaram há N dias.
 *
 * @return int Número de usuários desativados
 */
function deactivateInactiveUsers(\PDO $pdo, int $inactiveDays = 180): int
{
    $stmt = $pdo->prepare(
        'UPDATE users
         SET active = 0, updated_at = NOW()
         WHERE active = 1
           AND updated_at < NOW() - INTERVAL :days DAY'
    );

    $stmt->bindValue(':days', $inactiveDays, \PDO::PARAM_INT);
    $stmt->execute();

    return $stmt->rowCount();
}

// Desativa usuários inativos há mais de 6 meses
$count = deactivateInactiveUsers($pdo, 180);
echo "Desativados: {$count} usuários inativos.";
```

### Quadro-resumo — operações CRUD com PDO

| Operação | SQL | Método PDO | Verifica resultado |
|----------|-----|------------|--------------------|
| Criar | `INSERT INTO` | `prepare()` + `execute()` | `lastInsertId()` |
| Ler um | `SELECT ... LIMIT 1` | `prepare()` + `fetch()` | `$row !== false` |
| Ler vários | `SELECT ...` | `prepare()` + `fetchAll()` | `count($rows) > 0` |
| Contar | `SELECT COUNT(*)` | `prepare()` + `fetchColumn()` | `(int) $result` |
| Atualizar | `UPDATE ... WHERE` | `prepare()` + `execute()` | `rowCount() > 0` |
| Deletar | `DELETE FROM ... WHERE` | `prepare()` + `execute()` | `rowCount() > 0` |
| Múltiplos | Qualquer | `beginTransaction()` + `commit()` | `rollBack()` em erro |

---

## 78. XML — Parsers e Tipos

**XML** (eXtensible Markup Language) é um formato universal para troca de dados entre
sistemas, bancos de dados e APIs. PHP possui suporte nativo a XML com três parsers distintos.

### Tipos de parsers XML

| Tipo | Carrega tudo na memória | Ideal para | Exemplos |
|------|------------------------|------------|----------|
| **Tree-based** | ✅ Sim (DOM completo) | Arquivos pequenos/médios com navegação complexa | SimpleXML, DOMDocument |
| **Event-based** | ❌ Não (streaming) | Arquivos grandes, performance crítica | XMLReader, Expat |

### Quando usar cada parser

```
✅ SimpleXML   → Leitura simples de XML pequeno/médio. API intuitiva.
✅ DOMDocument → Leitura e modificação de XML. Mais controle que SimpleXML.
✅ XMLReader   → Arquivos XML grandes (MB/GB). Streaming, baixo uso de memória.
✅ Expat       → Processamento evento por evento. Alta performance.
```

### Estrutura de um documento XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<bookstore>
    <book category="WEB">
        <title lang="pt-BR">Aprendendo PHP 8.5</title>
        <author>Ana Silva</author>
        <year>2025</year>
        <price>49.90</price>
    </book>
    <book category="PROGRAMMING">
        <title lang="en">Clean Code</title>
        <author>Robert C. Martin</author>
        <year>2008</year>
        <price>89.99</price>
    </book>
</bookstore>
```

---

## 79. XML — SimpleXML Parser

**SimpleXML** é o parser mais simples e direto do PHP. Converte XML em um objeto
PHP navegável com acesso intuitivo a elementos e atributos.

### Lendo XML de string

```php
<?php

declare(strict_types=1);

$xmlString = <<<XML
<?xml version="1.0" encoding="UTF-8"?>
<note>
    <to>Maria</to>
    <from>Carlos</from>
    <heading>Lembrete</heading>
    <body>Não esqueça a reunião amanhã!</body>
</note>
XML;

// ✅ Habilita erros internos para tratamento manual
libxml_use_internal_errors(true);

$xml = simplexml_load_string($xmlString);

if ($xml === false) {
    echo 'Falha ao carregar XML:';
    foreach (libxml_get_errors() as $error) {
        echo htmlspecialchars($error->message, ENT_QUOTES | ENT_HTML5, 'UTF-8');
    }
    libxml_clear_errors();
    exit;
}

// Acesso a elementos — notação de objeto
echo (string) $xml->to;      // Maria
echo (string) $xml->from;    // Carlos
echo (string) $xml->heading; // Lembrete
echo (string) $xml->body;    // Não esqueça a reunião amanhã!

// print_r() mostra a estrutura completa
// print_r($xml);
```

### Lendo XML de arquivo

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/books.xml';

if (!file_exists($filePath) || !is_readable($filePath)) {
    throw new \RuntimeException("Arquivo XML não encontrado: {$filePath}");
}

libxml_use_internal_errors(true);
$xml = simplexml_load_file($filePath);

if ($xml === false) {
    $errors = array_map(
        fn(\LibXMLError $e): string => trim($e->message),
        libxml_get_errors()
    );
    libxml_clear_errors();
    throw new \RuntimeException('XML inválido: ' . implode(', ', $errors));
}
```

### Acessando elementos e atributos

```php
<?php

declare(strict_types=1);

$xmlString = <<<XML
<?xml version="1.0" encoding="UTF-8"?>
<bookstore>
    <book category="WEB">
        <title lang="pt-BR">Aprendendo PHP 8.5</title>
        <author>Ana Silva</author>
        <year>2025</year>
        <price>49.90</price>
    </book>
    <book category="PROGRAMMING">
        <title lang="en">Clean Code</title>
        <author>Robert C. Martin</author>
        <year>2008</year>
        <price>89.99</price>
    </book>
</bookstore>
XML;

libxml_use_internal_errors(true);
$xml = simplexml_load_string($xmlString);

// Acesso por índice (base 0)
echo (string) $xml->book[0]->title;  // Aprendendo PHP 8.5
echo (string) $xml->book[1]->author; // Robert C. Martin

// Acessando atributos com ['nome_do_atributo']
echo (string) $xml->book[0]['category'];          // WEB
echo (string) $xml->book[1]->title['lang'];       // en

// Percorrendo todos os filhos com foreach
foreach ($xml->children() as $book) {
    $category = (string) $book['category'];
    $title    = (string) $book->title;
    $author   = (string) $book->author;
    $year     = (int)    $book->year;
    $price    = (float)  $book->price;
    $lang     = (string) $book->title['lang'];

    echo htmlspecialchars("{$title} ({$lang}) — {$author}, {$year} | R$ {$price}", ENT_QUOTES | ENT_HTML5, 'UTF-8');
}

// Percorrendo atributos de cada elemento
foreach ($xml->children() as $book) {
    echo (string) $book->title['lang'];
}
```

### Convertendo SimpleXML para array

```php
<?php

declare(strict_types=1);

/**
 * Converte um SimpleXMLElement para array PHP puro.
 * Útil para serialização JSON ou processamento posterior.
 */
function xmlToArray(\SimpleXMLElement $xml): array
{
    $array = [];

    foreach ($xml->children() as $key => $child) {
        $childArray = count($child->children()) > 0
            ? xmlToArray($child)
            : (string) $child;

        // Trata múltiplos elementos com o mesmo nome
        if (isset($array[$key])) {
            if (!is_array($array[$key]) || !isset($array[$key][0])) {
                $array[$key] = [$array[$key]];
            }
            $array[$key][] = $childArray;
        } else {
            $array[$key] = $childArray;
        }
    }

    return $array;
}

$data  = xmlToArray($xml);
$json  = json_encode($data, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE | JSON_THROW_ON_ERROR);
echo $json;
```

### XPath — consultas avançadas em XML

```php
<?php

declare(strict_types=1);

libxml_use_internal_errors(true);
$xml = simplexml_load_string($xmlString);

// XPath — linguagem de consulta para XML (similar ao SQL para bancos)
// Busca todos os livros da categoria WEB
$webBooks = $xml->xpath('//book[@category="WEB"]');

foreach ($webBooks as $book) {
    echo (string) $book->title;
}

// Busca títulos com lang="en"
$englishTitles = $xml->xpath('//title[@lang="en"]');

foreach ($englishTitles as $title) {
    echo (string) $title;
}

// Busca livros com preço menor que 50
$affordable = $xml->xpath('//book[price < 50]');
echo 'Livros acessíveis: ' . count($affordable);
```

---

## 80. XML — DOM Parser

**DOMDocument** é o parser de árvore completo do PHP. Permite leitura, criação,
modificação e validação de documentos XML com controle total sobre a estrutura.

### Lendo e percorrendo XML com DOMDocument

```php
<?php

declare(strict_types=1);

$filePath = __DIR__ . '/data/note.xml';

// Inicializa o parser DOM
$dom = new \DOMDocument();
$dom->preserveWhiteSpace = false; // ✅ Ignora nós de texto com espaços em branco

// Suprime warnings — usamos libxml para tratar erros
libxml_use_internal_errors(true);

$loaded = $dom->load($filePath);

if (!$loaded) {
    foreach (libxml_get_errors() as $error) {
        echo 'Erro XML: ' . htmlspecialchars(trim($error->message), ENT_QUOTES | ENT_HTML5, 'UTF-8');
    }
    libxml_clear_errors();
    exit;
}

// Acessa o elemento raiz
$root = $dom->documentElement;
echo 'Elemento raiz: ' . $root->nodeName; // note

// Percorre filhos ignorando nós de texto vazios
foreach ($root->childNodes as $node) {
    if ($node->nodeType === XML_ELEMENT_NODE) { // Apenas elementos, ignora texto/comentários
        $name  = $node->nodeName;
        $value = htmlspecialchars($node->nodeValue, ENT_QUOTES | ENT_HTML5, 'UTF-8');
        echo "{$name}: {$value}";
    }
}
```

### getElementsByTagName() — busca por nome de tag

```php
<?php

declare(strict_types=1);

libxml_use_internal_errors(true);

$dom = new \DOMDocument();
$dom->preserveWhiteSpace = false;
$dom->load(__DIR__ . '/data/books.xml');

// Busca todos os elementos <book>
$books = $dom->getElementsByTagName('book');

echo 'Total de livros: ' . $books->length;

foreach ($books as $book) {
    // Acessa atributo com getAttribute()
    $category = $book->getAttribute('category');

    // Busca elementos filhos dentro do book
    $title  = $book->getElementsByTagName('title')->item(0)?->nodeValue ?? '';
    $author = $book->getElementsByTagName('author')->item(0)?->nodeValue ?? '';
    $price  = (float) ($book->getElementsByTagName('price')->item(0)?->nodeValue ?? 0);

    // Atributo do elemento <title>
    $lang = $book->getElementsByTagName('title')->item(0)?->getAttribute('lang') ?? '';

    echo htmlspecialchars(
        "{$title} [{$lang}] ({$category}) — {$author} | R$ {$price}",
        ENT_QUOTES | ENT_HTML5, 'UTF-8'
    );
}
```

### Criando e modificando XML com DOMDocument

```php
<?php

declare(strict_types=1);

// ✅ Cria um documento XML do zero
$dom = new \DOMDocument('1.0', 'UTF-8');
$dom->formatOutput = true; // Indentação legível

// Elemento raiz
$root = $dom->createElement('catalog');
$dom->appendChild($root);

// Função auxiliar para criar nós com texto
function addTextElement(\DOMDocument $dom, \DOMElement $parent, string $tag, string $value): void
{
    $element = $dom->createElement($tag);
    $element->appendChild($dom->createTextNode($value));
    $parent->appendChild($element);
}

// Adiciona produtos
$products = [
    ['id' => '1', 'name' => 'Teclado Mecânico', 'price' => '350.00', 'category' => 'hardware'],
    ['id' => '2', 'name' => 'Mouse Gamer',       'price' => '189.90', 'category' => 'hardware'],
    ['id' => '3', 'name' => 'PHP 8.5 Guide',     'price' => '49.90',  'category' => 'book'],
];

foreach ($products as $productData) {
    $productEl = $dom->createElement('product');
    $productEl->setAttribute('id',       $productData['id']);
    $productEl->setAttribute('category', $productData['category']);
    $root->appendChild($productEl);

    addTextElement($dom, $productEl, 'name',  $productData['name']);
    addTextElement($dom, $productEl, 'price', $productData['price']);
}

// Salva como string ou arquivo
$xmlString = $dom->saveXML();
echo htmlspecialchars($xmlString, ENT_QUOTES | ENT_HTML5, 'UTF-8');

// Ou salva em arquivo
$dom->save(__DIR__ . '/data/catalog.xml');
```

### DOMDocument + XPath

```php
<?php

declare(strict_types=1);

libxml_use_internal_errors(true);

$dom = new \DOMDocument();
$dom->preserveWhiteSpace = false;
$dom->load(__DIR__ . '/data/books.xml');

$xpath = new \DOMXPath($dom);

// ✅ XPath com DOMXPath — consultas precisas
// Todos os títulos em inglês
$englishTitles = $xpath->query('//title[@lang="en"]');

foreach ($englishTitles as $node) {
    echo htmlspecialchars($node->nodeValue, ENT_QUOTES | ENT_HTML5, 'UTF-8');
}

// Livros com preço menor que 50
$cheapBooks = $xpath->query('//book[number(price) < 50]');
echo 'Livros baratos: ' . $cheapBooks->length;

// Avaliação de expressão — retorna valor escalar
$totalBooks = $xpath->evaluate('count(//book)');
echo 'Total: ' . (int) $totalBooks;
```

---

## 81. XML — Expat Parser (Event-based)

O **Expat Parser** processa XML por eventos — não carrega o documento inteiro na memória.
Ideal para arquivos XML grandes onde SimpleXML causaria problemas de performance.

### Como funciona o parser de eventos

```
Evento "start element" → PHP chama sua função de abertura de tag
Evento "character data" → PHP chama sua função de dados de texto
Evento "end element"   → PHP chama sua função de fechamento de tag
```

### Exemplo com XMLReader — alternativa moderna ao Expat

```php
<?php

declare(strict_types=1);

/**
 * XMLReader é a alternativa moderna ao Expat (xml_parser_create).
 * Streaming event-based — ideal para arquivos XML grandes.
 * API orientada a objetos, mais limpa que as funções xml_*
 */
function parseXmlWithReader(string $filePath): array
{
    $reader = new \XMLReader();

    if (!$reader->open($filePath)) {
        throw new \RuntimeException("Não foi possível abrir: {$filePath}");
    }

    $books       = [];
    $currentBook = [];
    $currentTag  = '';

    while ($reader->read()) {
        match($reader->nodeType) {
            // Tag de abertura
            \XMLReader::ELEMENT => (function() use ($reader, &$currentBook, &$currentTag, &$books): void {
                $currentTag = $reader->name;

                if ($currentTag === 'book') {
                    $currentBook = [
                        'category' => $reader->getAttribute('category') ?? '',
                    ];
                }
            })(),

            // Dado de texto
            \XMLReader::TEXT, \XMLReader::CDATA => (function() use ($reader, &$currentBook, $currentTag): void {
                $value = trim($reader->value);

                if (!empty($value) && !empty($currentBook) && in_array($currentTag, ['title', 'author', 'year', 'price'])) {
                    $currentBook[$currentTag] = $value;
                }
            })(),

            // Tag de fechamento
            \XMLReader::END_ELEMENT => (function() use ($reader, &$currentBook, &$books): void {
                if ($reader->name === 'book' && !empty($currentBook)) {
                    $books[]     = $currentBook;
                    $currentBook = [];
                }
            })(),

            default => null,
        };
    }

    $reader->close();
    return $books;
}

$books = parseXmlWithReader(__DIR__ . '/data/books.xml');

foreach ($books as $book) {
    $title  = htmlspecialchars($book['title']  ?? '', ENT_QUOTES | ENT_HTML5, 'UTF-8');
    $author = htmlspecialchars($book['author'] ?? '', ENT_QUOTES | ENT_HTML5, 'UTF-8');
    echo "{$title} — {$author}";
}
```

### Expat clássico — xml_parser_create() (legado)

```php
<?php

declare(strict_types=1);

// ✅ Mantido para referência — XMLReader é a forma moderna preferida

$currentTag  = '';
$currentData = [];

function handleStart(mixed $parser, string $elementName, array $attrs): void
{
    global $currentTag;
    $currentTag = strtolower($elementName);
}

function handleChar(mixed $parser, string $data): void
{
    global $currentTag, $currentData;
    $trimmed = trim($data);

    if (!empty($trimmed)) {
        $currentData[$currentTag] = ($currentData[$currentTag] ?? '') . $trimmed;
    }
}

function handleEnd(mixed $parser, string $elementName): void
{
    global $currentTag;
    $currentTag = '';
}

$stream = fopen(__DIR__ . '/data/note.xml', 'r');

if ($stream === false) {
    throw new \RuntimeException('Não foi possível abrir o arquivo XML.');
}

$parser = xml_parser_create('UTF-8');
xml_parser_set_option($parser, XML_OPTION_CASE_FOLDING, 0); // Preserva case
xml_set_element_handler($parser, 'handleStart', 'handleEnd');
xml_set_character_data_handler($parser, 'handleChar');

try {
    while ($data = fread($stream, 4096)) {
        if (!xml_parse($parser, $data, feof($stream))) {
            $errorCode = xml_get_error_code($parser);
            $errorMsg  = xml_error_string($errorCode);
            $line      = xml_get_current_line_number($parser);
            throw new \RuntimeException("XML Error [{$errorCode}]: {$errorMsg} na linha {$line}");
        }
    }
} finally {
    xml_parser_free($parser);
    fclose($stream);
}

// $currentData contém os dados coletados
foreach ($currentData as $tag => $value) {
    echo htmlspecialchars("{$tag}: {$value}", ENT_QUOTES | ENT_HTML5, 'UTF-8');
}
```

### Comparação dos parsers XML

| Parser | Memória | Velocidade | Modificação | Melhor Para |
|--------|---------|------------|-------------|-------------|
| SimpleXML | Alta (tudo em RAM) | Moderada | ❌ Limitada | Leitura simples, arquivos pequenos |
| DOMDocument | Alta (tudo em RAM) | Moderada | ✅ Completa | Leitura + escrita, navegação complexa |
| XMLReader | ✅ Baixa (streaming) | ✅ Alta | ❌ Não | Arquivos grandes, export, import |
| Expat | ✅ Baixa (streaming) | ✅ Alta | ❌ Não | Legado — prefira XMLReader |

---

## 82. AJAX com PHP — Introdução

**AJAX** (Asynchronous JavaScript and XML) permite que páginas web se comuniquem
com o servidor em segundo plano, atualizando partes do conteúdo sem recarregar a página.

### Fluxo AJAX com PHP

```
1. Evento do usuário (digitação, clique, mudança)
2. JavaScript cria XMLHttpRequest (ou usa fetch())
3. Requisição enviada ao servidor PHP (GET ou POST)
4. PHP processa e retorna dados (JSON, HTML, texto)
5. JavaScript recebe e atualiza o DOM dinamicamente
```

### Backend PHP para AJAX — boas práticas

```php
<?php

declare(strict_types=1);

// ✅ Endpoint PHP para requisições AJAX
// Sempre valide a origem da requisição

// Verifica se é uma requisição AJAX (via header X-Requested-With)
$isAjax = strtolower($_SERVER['HTTP_X_REQUESTED_WITH'] ?? '') === 'xmlhttprequest';

// ✅ Retorna apenas JSON para chamadas AJAX
header('Content-Type: application/json; charset=UTF-8');
header('X-Content-Type-Options: nosniff');

// Desativa exibição de erros em produção — use log
if (($_ENV['APP_ENV'] ?? 'production') === 'production') {
    ini_set('display_errors', '0');
    error_reporting(0);
}

/**
 * Retorna resposta JSON padronizada e encerra.
 *
 * @param mixed $data       Dados a serializar
 * @param int   $statusCode Código HTTP
 *
 * @return never
 */
function jsonResponse(mixed $data, int $statusCode = 200): never
{
    http_response_code($statusCode);
    echo json_encode($data, JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE);
    exit;
}

/**
 * Retorna resposta de erro JSON padronizada.
 *
 * @return never
 */
function jsonError(string $message, int $statusCode = 400): never
{
    jsonResponse(['error' => $message, 'success' => false], $statusCode);
}
```

### Autocomplete com AJAX — backend seguro

```php
<?php

// autocomplete.php — endpoint para sugestões de busca

declare(strict_types=1);

header('Content-Type: application/json; charset=UTF-8');
header('X-Content-Type-Options: nosniff');

// ✅ Valida o parâmetro de busca
$query = filter_input(INPUT_GET, 'q', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
$query = trim($query);

if (mb_strlen($query) < 2) {
    echo json_encode([], JSON_THROW_ON_ERROR);
    exit;
}

// Busca no banco via PDO (prepared statement)
try {
    $pdo = Database::getInstance();

    $term = '%' . str_replace(['\\', '%', '_'], ['\\\\', '\\%', '\\_'], $query) . '%';

    $stmt = $pdo->prepare(
        'SELECT id, name, email
         FROM users
         WHERE active = 1 AND (name LIKE :term OR email LIKE :term)
         ORDER BY name
         LIMIT 10'
    );
    $stmt->execute(['term' => $term]);

    $results = $stmt->fetchAll();

    // ✅ Retorna apenas os campos necessários — não exponha dados desnecessários
    $suggestions = array_map(
        fn(array $row): array => [
            'id'    => (int)    $row['id'],
            'label' => (string) $row['name'],
            'value' => (string) $row['email'],
        ],
        $results
    );

    echo json_encode($suggestions, JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE);

} catch (\Throwable $e) {
    error_log('Autocomplete error: ' . $e->getMessage());
    http_response_code(500);
    echo json_encode(['error' => 'Erro interno'], JSON_THROW_ON_ERROR);
}
```

Frontend correspondente (JavaScript moderno com `fetch()`):

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Autocomplete</title>
</head>
<body>

<label for="search">Buscar usuário:</label>
<input type="text" id="search" placeholder="Digite o nome..." autocomplete="off">
<ul id="suggestions" style="list-style:none; padding:0; border:1px solid #ccc; display:none;"></ul>

<script>
const searchInput   = document.getElementById('search');
const suggestionBox = document.getElementById('suggestions');
let debounceTimer;

searchInput.addEventListener('input', function () {
    const query = this.value.trim();
    clearTimeout(debounceTimer);

    if (query.length < 2) {
        suggestionBox.innerHTML = '';
        suggestionBox.style.display = 'none';
        return;
    }

    // ✅ Debounce — aguarda 300ms após parar de digitar
    debounceTimer = setTimeout(() => {
        // ✅ fetch() — API moderna para AJAX (substitui XMLHttpRequest)
        fetch(`autocomplete.php?q=${encodeURIComponent(query)}`, {
            headers: {
                'X-Requested-With': 'XMLHttpRequest', // Identifica como AJAX
                'Accept': 'application/json',
            }
        })
        .then(response => {
            if (!response.ok) throw new Error(`HTTP ${response.status}`);
            return response.json();
        })
        .then(data => {
            suggestionBox.innerHTML = '';

            if (data.length === 0) {
                suggestionBox.style.display = 'none';
                return;
            }

            data.forEach(item => {
                const li = document.createElement('li');
                li.style.cssText = 'padding:8px;cursor:pointer;';

                // ✅ textContent (não innerHTML) — previne XSS
                li.textContent = `${item.label} (${item.value})`;
                li.dataset.id  = item.id;

                li.addEventListener('click', () => {
                    searchInput.value = item.label;
                    suggestionBox.innerHTML = '';
                    suggestionBox.style.display = 'none';
                });

                suggestionBox.appendChild(li);
            });

            suggestionBox.style.display = 'block';
        })
        .catch(err => {
            console.error('Erro no autocomplete:', err);
        });
    }, 300);
});

// Fecha sugestões ao clicar fora
document.addEventListener('click', e => {
    if (!e.target.closest('#search, #suggestions')) {
        suggestionBox.style.display = 'none';
    }
});
</script>

</body>
</html>
```

---

## 83. AJAX com PHP — Autocomplete e Banco de Dados

### Endpoint de busca com PDO — production-grade

```php
<?php

// search.php — busca dinâmica com filtros e paginação via AJAX

declare(strict_types=1);

header('Content-Type: application/json; charset=UTF-8');
header('X-Content-Type-Options: nosniff');
header('Cache-Control: no-store'); // Não cacheia dados pessoais

// Parâmetros da requisição
$query  = filter_input(INPUT_GET, 'q',      FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
$role   = filter_input(INPUT_GET, 'role',   FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
$page   = filter_input(INPUT_GET, 'page',   FILTER_VALIDATE_INT, ['options' => ['default' => 1, 'min_range' => 1]]) ?? 1;
$perPage = 10;

try {
    $pdo = Database::getInstance();

    $conditions = ['active = 1'];
    $bindings   = [];

    if (mb_strlen(trim($query)) >= 2) {
        $term = '%' . str_replace(['\\', '%', '_'], ['\\\\', '\\%', '\\_'], trim($query)) . '%';
        $conditions[]      = '(name LIKE :term OR email LIKE :term)';
        $bindings['term']  = $term;
    }

    $allowedRoles = ['admin', 'editor', 'viewer'];

    if (!empty($role) && in_array($role, $allowedRoles, strict: true)) {
        $conditions[]       = 'role = :role';
        $bindings['role']   = $role;
    }

    $where  = 'WHERE ' . implode(' AND ', $conditions);
    $offset = ($page - 1) * $perPage;

    // Total para paginação
    $countStmt = $pdo->prepare("SELECT COUNT(*) FROM users {$where}");
    $countStmt->execute($bindings);
    $total = (int) $countStmt->fetchColumn();

    // Resultados paginados
    $dataStmt = $pdo->prepare(
        "SELECT id, name, email, role, created_at
         FROM users {$where}
         ORDER BY name ASC
         LIMIT :limit OFFSET :offset"
    );

    foreach ($bindings as $key => $value) {
        $dataStmt->bindValue(":{$key}", $value, \PDO::PARAM_STR);
    }

    $dataStmt->bindValue(':limit',  $perPage, \PDO::PARAM_INT);
    $dataStmt->bindValue(':offset', $offset,  \PDO::PARAM_INT);
    $dataStmt->execute();

    $users = $dataStmt->fetchAll();

    echo json_encode([
        'success'    => true,
        'data'       => $users,
        'total'      => $total,
        'page'       => $page,
        'perPage'    => $perPage,
        'totalPages' => (int) ceil($total / $perPage),
    ], JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE);

} catch (\Throwable $e) {
    error_log('Search endpoint error: ' . $e->getMessage());
    http_response_code(500);
    echo json_encode(['success' => false, 'error' => 'Erro interno'], JSON_THROW_ON_ERROR);
}
```

### Endpoint de votação/poll com arquivo de texto

```php
<?php

// poll.php — sistema de votação simples com arquivo de texto

declare(strict_types=1);

header('Content-Type: application/json; charset=UTF-8');

$pollFile = __DIR__ . '/data/poll_results.txt';

// Cria o arquivo se não existir
if (!file_exists($pollFile)) {
    file_put_contents($pollFile, '0||0', LOCK_EX);
}

$allowedVotes = [0, 1]; // 0 = Sim, 1 = Não
$vote = filter_input(INPUT_GET, 'vote', FILTER_VALIDATE_INT);

if ($vote === null || $vote === false || !in_array($vote, $allowedVotes, strict: true)) {
    http_response_code(400);
    echo json_encode(['error' => 'Voto inválido'], JSON_THROW_ON_ERROR);
    exit;
}

// Lê os votos atuais com lock
$content = file_get_contents($pollFile);
[$yes, $no] = array_map('intval', explode('||', $content . '||0'));

// Incrementa o voto correto
if ($vote === 0) {
    $yes++;
} else {
    $no++;
}

// Salva com lock exclusivo — previne race condition em alta concorrência
$result = file_put_contents($pollFile, "{$yes}||{$no}", LOCK_EX);

if ($result === false) {
    http_response_code(500);
    echo json_encode(['error' => 'Falha ao salvar voto'], JSON_THROW_ON_ERROR);
    exit;
}

$total   = $yes + $no;
$yesPct  = $total > 0 ? round(($yes / $total) * 100, 1) : 0.0;
$noPct   = $total > 0 ? round(($no  / $total) * 100, 1) : 0.0;

echo json_encode([
    'yes'     => $yes,
    'no'      => $no,
    'total'   => $total,
    'yesPct'  => $yesPct,
    'noPct'   => $noPct,
], JSON_THROW_ON_ERROR);
```

### Boas práticas de segurança em endpoints AJAX

```php
<?php

declare(strict_types=1);

// Checklist de segurança para endpoints AJAX:

// ✅ 1. Valide TODOS os parâmetros de entrada
$id = filter_input(INPUT_GET, 'id', FILTER_VALIDATE_INT) ?? 0;

// ✅ 2. Defina Content-Type correto
header('Content-Type: application/json; charset=UTF-8');

// ✅ 3. Nunca exponha detalhes de erro ao cliente
// Em desenvolvimento: json_encode(['error' => $e->getMessage()])
// Em produção:        json_encode(['error' => 'Erro interno'])

// ✅ 4. Verifique autenticação/autorização
$userId = (int) ($_SESSION['user_id'] ?? 0);
if ($userId === 0) {
    http_response_code(401);
    echo json_encode(['error' => 'Não autenticado']);
    exit;
}

// ✅ 5. Use CSRF token para requisições POST/PUT/DELETE
// (GET é considerado idempotente e seguro para leitura)

// ✅ 6. Rate limiting — evita abuso
// Implemente via Redis, APCu ou banco de dados

// ✅ 7. Sempre use PDO com prepared statements

// ✅ 8. Não use textContent = data (JS) — use textContent, não innerHTML com dados externos

// ✅ 9. Limite o tamanho dos dados retornados (LIMIT na SQL)

// ✅ 10. Log de erros internamente — nunca exiba ao usuário
```

---

## 84. Referência Rápida Final — Índice de Exemplos

Este capítulo consolida os principais tópicos cobertos neste guia com ponteiros
para os capítulos relevantes.

### Índice por tema — onde encontrar no documento

| Tema | Capítulo |
|------|----------|
| Introdução, instalação, sintaxe | 1–3 |
| Variáveis, tipos, echo, comentários | 4–8 |
| Strings e funções de string | 9–14 |
| Números, casting, matemática | 15–17 |
| Constantes e constantes mágicas | 18–19 |
| Operadores (aritméticos, lógicos, null coalescing) | 20 |
| if/else, match vs switch | 21–22 |
| while, do..while, for, foreach | 23 |
| Funções, callbacks, closures | 24, 51 |
| Arrays (indexed, associative, multidimensional) | 25, 27–28 |
| PHP 8.5 features exclusivas | 26 |
| Superglobais ($_GET, $_POST, $_SERVER...) | 29–34 |
| RegEx (preg_match, preg_replace...) | 35–36 |
| Formulários, validação, CSRF | 37–41 |
| Datas e horas (DateTimeImmutable) | 42 |
| Include e require | 43 |
| Arquivos (leitura, escrita, upload) | 44–46 |
| Cookies e Sessions | 47–48 |
| Filtros (filter_var, filter_input) | 49–50 |
| JSON (encode, decode, validate) | 52 |
| Exceções e tratamento de erros | 53 |
| POO: Classes, objetos, herança | 54–59 |
| Classes abstratas, interfaces, traits | 60–62 |
| Métodos e propriedades estáticos | 63–64 |
| Namespaces (PSR-4) | 65 |
| Iterables, Iterator, Generator | 66 |
| PDO — conexão e CRUD completo | 67–77 |
| XML (SimpleXML, DOM, Expat) | 78–81 |
| AJAX com PHP | 82–83 |

### Cheatsheet — funções mais usadas por categoria

```php
<?php

declare(strict_types=1);

// ── STRINGS ──────────────────────────────────────────────────────────────────
mb_strlen($s)                          // Comprimento em caracteres UTF-8
mb_strtolower($s)                      // Minúsculas com suporte Unicode
mb_substr($s, $start, $length)         // Fatia com suporte Unicode
str_contains($haystack, $needle)       // Contém substring? (PHP 8.0+)
str_starts_with($s, $prefix)           // Começa com? (PHP 8.0+)
str_ends_with($s, $suffix)             // Termina com? (PHP 8.0+)
str_replace($search, $replace, $s)     // Substitui texto
trim($s) / ltrim($s) / rtrim($s)       // Remove espaços
explode($sep, $s)                      // String → array
implode($sep, $arr)                    // Array → string
htmlspecialchars($s, ENT_QUOTES|ENT_HTML5, 'UTF-8') // Escape HTML (SEMPRE!)
sprintf('%05d', $n)                    // Formata string
number_format($n, 2, ',', '.')         // Formata número BR

// ── ARRAYS ───────────────────────────────────────────────────────────────────
array_first($arr)                      // 🆕 PHP 8.5: primeiro elemento
array_last($arr)                       // 🆕 PHP 8.5: último elemento
count($arr)                            // Número de elementos
array_filter($arr, $fn)                // Filtra
array_map($fn, $arr)                   // Transforma
array_reduce($arr, $fn, $initial)      // Reduz a valor escalar
array_column($arr, 'column')           // Extrai coluna de array 2D
usort($arr, fn($a, $b) => $a <=> $b)  // Ordena com comparador
in_array($val, $arr, strict: true)     // Verifica existência (strict!)
array_unique($arr)                     // Remove duplicatas
array_merge($a, $b) / [...$a, ...$b]  // Mescla arrays

// ── DATA/HORA ────────────────────────────────────────────────────────────────
new \DateTimeImmutable('now', new \DateTimeZone('America/Sao_Paulo'))
$dt->format('Y-m-d H:i:s')            // Formata
$dt->modify('+1 day')                  // Adiciona período (retorna novo objeto)
$dt->diff($other)                      // Diferença como DateInterval
\DateTimeImmutable::createFromFormat('d/m/Y', $str) // Parse de formato específico

// ── TIPOS E VALIDAÇÃO ─────────────────────────────────────────────────────────
filter_var($val, FILTER_VALIDATE_EMAIL)  // Valida e-mail
filter_var($val, FILTER_VALIDATE_URL)    // Valida URL
filter_var($val, FILTER_VALIDATE_INT)    // Valida inteiro
filter_input(INPUT_POST, 'field', ...)   // Lê e valida superglobal

// ── SEGURANÇA ─────────────────────────────────────────────────────────────────
password_hash($pass, PASSWORD_ARGON2ID)  // Hash seguro de senha
password_verify($pass, $hash)            // Verifica senha
random_bytes(32)                         // Bytes aleatórios seguros
bin2hex(random_bytes(32))               // Token CSRF / API key
hash_equals($known, $user)              // Comparação timing-safe
session_regenerate_id(true)             // Previne session fixation

// ── PDO ───────────────────────────────────────────────────────────────────────
$pdo->prepare($sql)                      // Prepara statement
$stmt->execute([':param' => $val])       // Executa com parâmetros
$stmt->fetch()                           // Uma linha
$stmt->fetchAll()                        // Todas as linhas
$stmt->fetchColumn()                     // Valor escalar (COUNT, etc.)
$stmt->rowCount()                        // Linhas afetadas (UPDATE/DELETE)
$pdo->lastInsertId()                     // ID do último INSERT
$pdo->beginTransaction()                 // Inicia transação
$pdo->commit() / $pdo->rollBack()        // Confirma / reverte

// ── JSON ──────────────────────────────────────────────────────────────────────
json_encode($data, JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE)
json_decode($json, associative: true, flags: JSON_THROW_ON_ERROR)
json_validate($json)                     // Valida sem decodificar (PHP 8.3+)

// ── OOP PHP 8.5 ──────────────────────────────────────────────────────────────
clone($obj, ['prop' => $newVal])         // Clone with (PHP 8.5)
array_first($arr)                        // PHP 8.5 — sem side effects
$val |> trim(...) |> strtolower(...)     // Pipe operator (PHP 8.5)
Closure::getCurrent()                    // Recursão em closures (PHP 8.5)
new Uri\Rfc3986\Uri($url)               // URI parsing (PHP 8.5)
```

### Padrões e anti-padrões — resumo de segurança

```
✅ SEMPRE                                    ❌ NUNCA
────────────────────────────────────────────────────────────────────────
declare(strict_types=1) em todo arquivo      Omitir strict_types
htmlspecialchars() ao exibir dados           Exibir dados sem escape
PDO + prepared statements                    Concatenar dados em SQL
password_hash(PASSWORD_ARGON2ID)             Armazenar senha em texto plano
filter_var() para validar inputs             Confiar em dados externos
random_bytes() para tokens                   rand() para segurança
hash_equals() para comparar tokens           == para comparar tokens
session_regenerate_id() após login           Manter mesmo session ID
HTTPS em formulários com dados sensíveis     Enviar senhas via GET
is_uploaded_file() em uploads                Mover arquivo sem verificar
realpath() para validar caminhos             Concatenar paths sem validar
array_first() / array_last() (PHP 8.5)       reset() / end() com side effects
match com UnhandledMatchError                switch sem default
DateTimeImmutable                            date() + mktime() para lógica
is_nan() antes de cast de NAN               Cast de NAN direto (PHP 8.5 ⚠️)
(bool), (int), (float), (string)             (boolean), (integer), (double) ⚠️
```

---

> **Fontes:** [php.net](https://www.php.net/) | [php-fig.org](https://www.php-fig.org/) |
> [W3Schools PHP Tutorial](https://www.w3schools.com/php/) (base, aprimorada para PHP 8.5)
>
> **Versão:** PHP 8.5 | **Estilo:** PER-CS v3.0 | **Última revisão:** Abril 2026

---

# PARTE 2 — TUTORIAL APROFUNDADO (Casos de Uso · Comparações · Armadilhas · Boas Práticas · Exemplos Reais)

---


1. [Variáveis e Tipos de Dados](#1-variáveis-e-tipos-de-dados)
2. [Strings e Manipulação de Texto](#2-strings-e-manipulação-de-texto)
3. [Números, Casting e Precisão](#3-números-casting-e-precisão)
4. [Constantes e Enums](#4-constantes-e-enums)
5. [Operadores](#5-operadores)
6. [Estruturas Condicionais — if, match e switch](#6-estruturas-condicionais--if-match-e-switch)
7. [Loops e Iteração](#7-loops-e-iteração)
8. [Funções e Closures](#8-funções-e-closures)
9. [Arrays — Fundamentos e Programação Funcional](#9-arrays--fundamentos-e-programação-funcional)
10. [Orientação a Objetos — Classes e Objetos](#10-orientação-a-objetos--classes-e-objetos)
11. [Herança, Interfaces e Traits](#11-herança-interfaces-e-traits)
12. [Exceções e Tratamento de Erros](#12-exceções-e-tratamento-de-erros)
13. [Superglobais e Formulários](#13-superglobais-e-formulários)
14. [Sessões e Cookies](#14-sessões-e-cookies)
15. [Filtros, Validação e Sanitização](#15-filtros-validação-e-sanitização)
16. [Arquivos e Sistema de Arquivos](#16-arquivos-e-sistema-de-arquivos)
17. [Banco de Dados com PDO](#17-banco-de-dados-com-pdo)
18. [JSON e APIs](#18-json-e-apis)
19. [Expressões Regulares](#19-expressões-regulares)
20. [PHP 8.5 — Features Exclusivas](#20-php-85--features-exclusivas)

---

## 1. Variáveis e Tipos de Dados

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── int: IDs, contadores, índices, quantidades ───────────────────────────────
$userId     = 42;          // ID do banco — sempre inteiro
$pageNumber = 3;           // Paginação
$quantity   = 150;         // Estoque
// ⚠️ NUNCA use int nem float para valores monetários!

// ── float: medidas físicas, coordenadas, taxas percentuais ──────────────────
$latitude     = -23.5505;   // Coordenada GPS
$longitude    = -46.6333;
$discountRate = 0.15;       // 15% de desconto — apenas taxa, não valor final

// ── string: texto, CPF, CEP, slugs, datas como texto ────────────────────────
$fullName   = 'Ana Silva';
$cpf        = '123.456.789-00';  // String! Zeros à esquerda importam
$slug       = 'php-8-5-lancado';
$isoDate    = '2025-04-07';      // Datas armazenadas como string ISO 8601

// ── bool: estados binários, flags, resultado de verificações ────────────────
$isActive      = true;
$hasPermission = false;
$isEmailSent   = false;

// ── null: ausência INTENCIONAL de valor ─────────────────────────────────────
$lastLoginAt   = null;  // Usuário nunca logou — diferente de "hoje"
$middleName    = null;  // Campo opcional não preenchido

// ── O PROBLEMA DO DINHEIRO — regra fundamental ───────────────────────────────
// Float em cálculos financeiros causa erro de precisão:
$price = 1.10;
$tax   = 0.10;
echo $price + $tax; // 1.2000000000000002 — NÃO é 1.20!

// ✅ Correto: armazene em centavos (inteiro), divida apenas no output
$priceCents = 110;  // R$ 1,10
$taxCents   = 10;   // R$ 0,10
$totalCents = $priceCents + $taxCents; // 120 — exato!
echo 'R$ ' . number_format($totalCents / 100, 2, ',', '.'); // R$ 1,20
```

### Comparações e Alternativas

```php
<?php

declare(strict_types=1);

// ── Verificação de tipo: qual função usar? ───────────────────────────────────

$value = 42;

// is_*(): diretas, booleanas — USE ESTAS
var_dump(is_int($value));      // bool(true) — preferida
var_dump(is_string($value));   // bool(false)
var_dump(is_float($value));    // bool(false)
var_dump(is_bool($value));     // bool(false)
var_dump(is_null($value));     // bool(false)
var_dump(is_array($value));    // bool(false)

// gettype(): retorna string — EVITE em condicionais (typo silencioso)
echo gettype($value);  // "integer" — string 'integer', não 'int'!
// if (gettype($x) === 'int') { } // ❌ Retorna 'integer', não 'int'!
// if (gettype($x) === 'integer') { } // ✅ Mas prefira is_int()

// get_debug_type(): PHP 8.0+ — nome completo incluindo namespace (melhor para debug)
class MyClass {}
$obj = new MyClass();
echo get_debug_type($obj);    // "MyClass"
echo get_debug_type(null);    // "null"
echo get_debug_type(42);      // "int" (não "integer"!)
echo get_debug_type([]);      // "array"
echo get_debug_type(3.14);    // "float"

// instanceof: para objetos — verificação de hierarquia
var_dump($obj instanceof MyClass); // bool(true)

// ── Comparação: == (frouxa) vs === (estrita) ──────────────────────────────────

// ❌ PHP 7 tinha "0" == false → true, "1" == true → true
// PHP 8 corrigiu: "1" == true ainda é true, "0" == false ainda é true
// ✅ Sempre use === para comparações seguras

var_dump(0   == false);  // true — perigoso!
var_dump(0   === false); // false — correto
var_dump("1" == true);   // true
var_dump("1" === true);  // false
var_dump(null == false); // true — null e false são "iguais" com ==
var_dump(null === false);// false
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Variável não inicializada (Notice/Warning em PHP 8)
function processData(bool $debug = false): void
{
    if ($debug) {
        $output = 'Modo debug ativo';
    }
    echo $output; // ⚠️ Warning: Undefined variable $output se $debug = false
}

// ✅ Sempre inicialize antes do if
function processDataFixed(bool $debug = false): void
{
    $output = ''; // Valor padrão
    if ($debug) {
        $output = 'Modo debug ativo';
    }
    echo $output; // Seguro
}

// ❌ ARMADILHA 2: Tipo muda ao longo da função (confusão de tipos)
$result = 0;
// ... mais código ...
$result = 'Erro ao processar'; // Muda de int para string — dificulta debugging
// ✅ Use nomes descritivos e tipos consistentes, ou use exceções para erros

// ❌ ARMADILHA 3: is_numeric() aceita formatos inesperados
var_dump(is_numeric('1e5'));   // bool(true) — notação científica é "numérica"
var_dump(is_numeric(' 42'));  // bool(true) — espaço à esquerda é aceito
// ✅ Para validar ID de banco, use filter_var:
$id = filter_var($_GET['id'] ?? '', FILTER_VALIDATE_INT, [
    'options' => ['min_range' => 1],
]);
// Retorna int válido ou false — muito mais preciso

// ❌ ARMADILHA 4: empty() com comportamentos surpreendentes
var_dump(empty(0));       // true — zero é "empty"!
var_dump(empty('0'));     // true — string "0" é "empty"!
var_dump(empty([]));      // true
var_dump(empty(null));    // true
var_dump(empty(false));   // true

// ✅ Seja específico:
$val = 0;
if ($val === null) { }    // Verifica só null
if ($val === []) { }      // Verifica só array vazio
if ($val === '') { }      // Verifica só string vazia
if ($val === 0) { }       // Verifica só zero — não confunde com false ou null

// ❌ ARMADILHA 5: Alterar tipo da mesma variável
$data = 42;
$data = ['erro' => 'não encontrado']; // Agora é array — confuso!
// ✅ Use variáveis diferentes com nomes descritivos:
$userId     = 42;
$userErrors = ['erro' => 'não encontrado'];
```

### Melhores Práticas

```php
<?php

declare(strict_types=1);

// ✅ 1. Nomes descritivos em camelCase — o nome deve comunicar o propósito
$u = 1;                     // ❌ O que é "u"?
$userId = 1;                // ✅ Claramente um ID de usuário
$isEmailVerified = false;   // ✅ bool óbvio pelo prefixo "is"
$hasPermission   = false;   // ✅ bool óbvio pelo prefixo "has"
$canEdit         = false;   // ✅ bool óbvio pelo prefixo "can"
$createdAt       = new \DateTimeImmutable(); // ✅ Sufixo "At" indica timestamp

// ✅ 2. Null coalescing — substitui isset() + ternário
// ❌ Verboso:
$name = isset($_GET['name']) ? $_GET['name'] : 'Visitante';
// ✅ Moderno:
$name = $_GET['name'] ?? 'Visitante';

// ✅ 3. Nullsafe operator para encadeamento de nullable
$city = $user?->getAddress()?->getCity() ?? 'Não informada';
// Se $user ou getAddress() forem null, retorna null (não lança erro)
// ?? 'Não informada' captura o null final

// ✅ 4. declare(strict_types=1) — SEMPRE, em todo arquivo
// Faz PHP verificar tipos em chamadas de função — evita bugs silenciosos

// ✅ 5. var_dump() para debug, nunca em produção
// Use logging estruturado em produção:
// error_log(json_encode(['context' => $data, 'level' => 'debug']));
```

### Exemplo do Mundo Real — Sistema de Cadastro de Produtos

```php
<?php

declare(strict_types=1);

/**
 * Representa um produto no catálogo de e-commerce.
 * Demonstra uso correto de tipos em PHP 8.5.
 */
final class Product
{
    // Preço em centavos (int) — evita imprecisão de float
    public function __construct(
        private readonly int    $id,
        private readonly string $name,
        private readonly string $sku,          // Código único — string mesmo sendo "número"
        private readonly int    $priceCents,   // ✅ Centavos, não reais!
        private readonly int    $stockQty,
        private readonly bool   $isActive    = true,
        private readonly ?string $description = null,  // Nullable — campo opcional
    ) {
        // Validações no construtor garantem invariantes
        if ($this->priceCents < 0) {
            throw new \InvalidArgumentException('Preço não pode ser negativo.');
        }
        if ($this->stockQty < 0) {
            throw new \InvalidArgumentException('Estoque não pode ser negativo.');
        }
        if (empty(trim($this->name))) {
            throw new \InvalidArgumentException('Nome do produto é obrigatório.');
        }
    }

    // Getters controlam o acesso
    public function getId(): int { return $this->id; }
    public function getName(): string { return $this->name; }
    public function getSku(): string { return $this->sku; }
    public function getPriceCents(): int { return $this->priceCents; }
    public function getStockQty(): int { return $this->stockQty; }
    public function isActive(): bool { return $this->isActive; }
    public function getDescription(): ?string { return $this->description; }

    // Formata o preço apenas no output — conversão ocorre só aqui
    public function getFormattedPrice(string $currency = 'R$'): string
    {
        return $currency . ' ' . number_format($this->priceCents / 100, 2, ',', '.');
    }

    public function hasStock(): bool
    {
        return $this->stockQty > 0;
    }

    // PHP 8.5: Clone With para modificar o preço sem violar readonly
    public function withDiscount(float $discountRate): self
    {
        if ($discountRate < 0.0 || $discountRate >= 1.0) {
            throw new \InvalidArgumentException('Taxa de desconto deve estar entre 0 e 1 (exclusive).');
        }

        $discountedPrice = (int) round($this->priceCents * (1.0 - $discountRate));
        return clone($this, ['priceCents' => $discountedPrice]);
    }
}

// ── Uso ──────────────────────────────────────────────────────────────────────
$keyboard = new Product(
    id:          1,
    name:        'Teclado Mecânico RGB',
    sku:         'TEC-001-RGB',
    priceCents:  35000,   // R$ 350,00
    stockQty:    15,
    description: 'Switch Red, layout ABNT2',
);

echo $keyboard->getFormattedPrice();  // R$ 350,00
var_dump($keyboard->hasStock());      // bool(true)

// Aplica 10% de desconto — objeto original intacto (imutável)
$saleKeyboard = $keyboard->withDiscount(0.10);
echo $saleKeyboard->getFormattedPrice(); // R$ 315,00
echo $keyboard->getFormattedPrice();     // R$ 350,00 — não mudou!
```

---

## 2. Strings e Manipulação de Texto

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Aspas simples vs duplas — quando usar cada uma ───────────────────────────

// Aspas SIMPLES: strings estáticas sem variáveis
// Mais rápidas (PHP não precisa analisar o conteúdo)
$sql       = 'SELECT id, name, email FROM users WHERE active = 1';
$cssClass  = 'btn btn-primary active';
$apiPath   = '/api/v2/users';

// Aspas DUPLAS: strings com variáveis ou sequências de escape
$greeting  = "Olá, {$userName}!";
$logLine   = "[{$timestamp}] {$level}: {$message}\n";
$tabSep    = "campo1\tcampo2\tcampo3\n"; // \t = tab, \n = nova linha

// ── Heredoc: blocos multiline COM variáveis ────────────────────────────────
// Útil para templates HTML, SQL complexo, mensagens longas
$emailBody = <<<HTML
    <h1>Bem-vindo, {$user->name}!</h1>
    <p>Seu cadastro foi confirmado.</p>
    <p>Acesse: <a href="{$loginUrl}">{$loginUrl}</a></p>
    HTML;

// ── Nowdoc: blocos multiline SEM interpolação (como aspas simples) ────────
// Útil para templates de código, SQL raw, strings com muitos $ e {}
$sqlTemplate = <<<'SQL'
    SELECT u.id, u.name, u.email
    FROM users u
    WHERE u.active = 1
      AND u.role = :role
    ORDER BY u.name ASC
    LIMIT :limit OFFSET :offset
    SQL;

// ── PHP 8.5 Pipe Operator — pipeline de transformação de strings ─────────
$rawInput = '  PHP 8.5 LANÇADO!  ';

$cleanSlug = $rawInput
    |> trim(...)
    |> mb_strtolower(...)
    |> (fn(string $s): string => preg_replace('/[^a-z0-9\s-]/u', '', $s) ?? '')
    |> (fn(string $s): string => preg_replace('/[\s]+/', '-', $s) ?? '');

echo $cleanSlug; // "php-85-lanado"
```

### Comparações e Alternativas

```php
<?php

declare(strict_types=1);

// ── Funções de byte vs funções multibyte ─────────────────────────────────────

$text = 'João'; // 4 caracteres, 5 bytes em UTF-8 (ã = 2 bytes)

// Funções de BYTE — incorretas para UTF-8
echo strlen($text);        // 5 — errado! (bytes, não chars)
echo substr($text, 0, 3);  // 'Jo' + metade do ã — quebra o caractere!
echo strtolower('JOÃO');    // 'joÃo' — não funciona com acentos

// Funções MULTIBYTE (mb_*) — corretas para UTF-8
echo mb_strlen($text);             // 4 — correto
echo mb_substr($text, 0, 3);       // 'Joã' — correto
echo mb_strtolower('JOÃO');        // 'joão' — correto
echo mb_strtoupper('joão');        // 'JOÃO' — correto

// ── str_contains vs strpos — modernidade e legibilidade ─────────────────────

$text = 'PHP 8.5 foi lançado em 2025';

// Antes (PHP < 8.0): strpos com !== false
if (strpos($text, 'PHP') !== false) { echo 'Contém PHP'; }

// Depois (PHP 8.0+): str_contains — mais legível e sem armadilha do !== false
if (str_contains($text, 'PHP')) { echo 'Contém PHP'; }    // ✅ Preferido
if (str_starts_with($text, 'PHP')) { echo 'Começa com PHP'; }
if (str_ends_with($text, '2025')) { echo 'Termina com 2025'; }

// ── sprintf vs concatenação — quando usar cada um ─────────────────────────

$name  = 'Ana';
$score = 9.75;
$rank  = 1;

// Concatenação: ok para 1-2 variáveis
$msg = 'Olá, ' . $name . '!';

// sprintf: melhor para templates com formatação complexa
$msg = sprintf('Classificação de %s: %dº lugar com %.2f pontos.', $name, $rank, $score);
// "Classificação de Ana: 1º lugar com 9.75 pontos."

// printf: imprime diretamente (sem retorno)
// fprintf: escreve em um file handle
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: strlen() com UTF-8 — produz contagem incorreta
$name = 'Ângela'; // 6 caracteres visíveis, 7 bytes
$limit = 5;
if (strlen($name) > $limit) {
    // Esta condição é avaliada com base em bytes, não caracteres!
    echo mb_substr($name, 0, $limit); // 'Ângel' — mas strlen deu 7, não 6!
}
// ✅ Use mb_strlen e mb_substr para texto em qualquer idioma:
if (mb_strlen($name) > $limit) {
    echo mb_substr($name, 0, $limit); // 'Ângel' — correto
}

// ❌ ARMADILHA 2: Concatenação em loops grandes (O(n²))
$parts = [];
$csv = '';
for ($i = 0; $i < 100000; $i++) {
    $csv .= "linha_{$i},";  // ❌ Cria nova string a cada iteração — muito lento!
}

// ✅ Acumule em array e una no final (O(n)):
$parts = [];
for ($i = 0; $i < 100000; $i++) {
    $parts[] = "linha_{$i}";
}
$csv = implode(',', $parts); // Uma única operação de join

// ❌ ARMADILHA 3: Interpolação ambígua sem chaves
$items = ['PHP', 'Python'];
$count = 3;
echo "Existem $count$items linguagens";   // Ambíguo — interpretado errado
echo "Tenho $items[0] preferido";          // Funciona mas é frágil
echo "Tenho {$items[0]} preferido";        // ✅ Sempre use chaves

// ❌ ARMADILHA 4: preg_replace retorna null em erro (PHP 8.5)
$result = preg_replace('/[invalid/', 'x', 'texto'); // Regex inválida
var_dump($result); // NULL — falha silenciosa!
// ✅ Verifique o retorno e use o operador null coalescing:
$result = preg_replace('/[a-z]+/', 'X', 'texto') ?? 'texto'; // Fallback seguro

// ❌ ARMADILHA 5: nl2br não escapa o HTML antes
$comment = '<script>alert("XSS")</script>' . "\n" . 'linha 2';
echo nl2br($comment); // ❌ Script executado! nl2br não escapa HTML

// ✅ Escape ANTES de nl2br:
echo nl2br(htmlspecialchars($comment, ENT_QUOTES | ENT_HTML5, 'UTF-8'));
// &lt;script&gt;alert("XSS")&lt;/script&gt;<br>\nlinha 2 — seguro
```

### Melhores Práticas

```php
<?php

declare(strict_types=1);

// ✅ 1. Configure mb_internal_encoding no início da aplicação
mb_internal_encoding('UTF-8');
mb_regex_encoding('UTF-8');

// ✅ 2. Use mb_* para qualquer texto que pode ter caracteres especiais
function truncate(string $text, int $maxChars, string $suffix = '…'): string
{
    if (mb_strlen($text) <= $maxChars) {
        return $text;
    }
    return mb_substr($text, 0, $maxChars - mb_strlen($suffix)) . $suffix;
}

echo truncate('PHP 8.5 foi lançado!', 10); // 'PHP 8.5 fo…'

// ✅ 3. Escape SEMPRE antes de exibir qualquer dado externo
function safeHtml(string $value): string
{
    return htmlspecialchars($value, ENT_QUOTES | ENT_HTML5, 'UTF-8');
}

// ✅ 4. sprintf para templates de mensagem (mais fácil de traduzir/manter)
function formatWelcome(string $name, int $points): string
{
    return sprintf('Bem-vindo, %s! Você tem %d pontos.', $name, $points);
}

// ✅ 5. Pipe operator (PHP 8.5) para pipelines de limpeza
function buildSlug(string $raw): string
{
    return $raw
        |> trim(...)
        |> mb_strtolower(...)
        |> (fn(string $s): string => preg_replace('/\s+/', '-', $s) ?? $s)
        |> (fn(string $s): string => preg_replace('/[^a-z0-9-]/u', '', $s) ?? $s)
        |> (fn(string $s): string => trim($s, '-'));
}

echo buildSlug('  PHP 8.5 Lançado! '); // 'php-85-lanado'
```

### Exemplo do Mundo Real — Gerador de E-mail de Boas-Vindas

```php
<?php

declare(strict_types=1);

/**
 * Gera o corpo de e-mail de boas-vindas de forma segura.
 * Demonstra: heredoc, escape, sprintf, mb_* e Pipe operator.
 */
final class WelcomeEmailBuilder
{
    public function __construct(
        private readonly string $siteUrl,
        private readonly string $siteName,
    ) {}

    public function build(string $userName, string $loginToken): string
    {
        // Sanitiza inputs antes de usar em HTML
        $safeName  = htmlspecialchars(trim($userName), ENT_QUOTES | ENT_HTML5, 'UTF-8');
        $safeUrl   = htmlspecialchars($this->siteUrl, ENT_QUOTES | ENT_HTML5, 'UTF-8');
        $safeSite  = htmlspecialchars($this->siteName, ENT_QUOTES | ENT_HTML5, 'UTF-8');

        // Token na URL deve ser URL-encoded (não HTML-encoded)
        $loginUrl  = $this->siteUrl . '/login?token=' . urlencode($loginToken);
        $safeLogin = htmlspecialchars($loginUrl, ENT_QUOTES | ENT_HTML5, 'UTF-8');

        // Expiração formatada
        $expiresAt = (new \DateTimeImmutable('+24 hours'))
            ->format('d/m/Y \à\s H:i');

        return <<<HTML
            <!DOCTYPE html>
            <html lang="pt-BR">
            <body>
                <h1>Bem-vindo ao {$safeSite}, {$safeName}!</h1>
                <p>Seu cadastro foi criado com sucesso.</p>
                <p>
                    <a href="{$safeLogin}">Ativar minha conta</a>
                </p>
                <p><small>Link válido até {$expiresAt}.</small></p>
            </body>
            </html>
            HTML;
    }

    /**
     * Gera o assunto do e-mail com nome do usuário truncado
     * para não ultrapassar 60 caracteres.
     */
    public function subject(string $userName): string
    {
        $prefix    = "Bem-vindo ao {$this->siteName}, ";
        $maxLength = 60;
        $available = $maxLength - mb_strlen($prefix) - 1; // -1 para '!'

        $truncatedName = $available > 0
            ? mb_substr($userName, 0, $available)
            : '';

        return sprintf('%s%s!', $prefix, $truncatedName);
    }
}

$builder = new WelcomeEmailBuilder(
    siteUrl:  'https://meusite.com.br',
    siteName: 'Meu E-commerce',
);

$html    = $builder->build('Maria da Silva', bin2hex(random_bytes(32)));
$subject = $builder->subject('Maria da Silva');

echo $subject; // "Bem-vindo ao Meu E-commerce, Maria da Silva!"
```

---

## 3. Números, Casting e Precisão

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Quando usar cada tipo numérico ───────────────────────────────────────────

// int: contadores, IDs, quantidades, timestamps Unix, bytes
$userId     = 42;
$timestamp  = time();           // Segundos desde 1970 — cabe em int de 64-bit
$fileSize   = filesize($path);  // Bytes — int
$priceCents = 9999;             // ✅ Dinheiro em centavos — int, não float!

// float: coordenadas, medidas físicas, percentuais (apenas taxa, não valor)
$lat    = -23.5505;
$weight = 72.5;    // kg
$rate   = 0.0875;  // Taxa de conversão — não valor final

// ── bcmath: para cálculos financeiros precisos ────────────────────────────────
// Use quando: resultado de divisão, juros compostos, cálculos multipassos
$principal  = '1000.00';
$rate       = '0.05';    // 5% ao mês
$months     = '12';

// Juros compostos: P * (1 + r)^n
$factor = bcpow(bcadd('1', $rate, 10), $months, 10);
$final  = bcmul($principal, $factor, 2);
echo "R$ {$final}"; // R$ 1795.85 — exato!

// ── Formatação de números para exibição ──────────────────────────────────────
$value = 1234567.89;

echo number_format($value, 2, ',', '.');    // "1.234.567,89" (BR)
echo number_format($value, 2, '.', ',');    // "1,234,567.89" (US)
echo number_format($value, 0, ',', '.');    // "1.234.568" (arredondado)

// Formatação de moeda
$cents = 123456; // R$ 1.234,56
echo 'R$ ' . number_format($cents / 100, 2, ',', '.'); // R$ 1.234,56
```

### Comparações e Alternativas

```php
<?php

declare(strict_types=1);

// ── Float vs BCMath vs GMP para cálculos ─────────────────────────────────────

// FLOAT: conveniente, mas impreciso para dinheiro
$a = 0.1;
$b = 0.2;
var_dump($a + $b === 0.3); // bool(false) — imprecisão binária!
var_dump($a + $b);          // float(0.30000000000000004)

// BCMATH: strings, precisão arbitrária, ideal para finanças
var_dump(bcadd('0.1', '0.2', 10) === '0.3000000000'); // bool(true)
// Desvantagem: trabalha com strings, sintaxe mais verbosa

// GMP: inteiros grandes (criptografia, big numbers)
$bigNum = gmp_init('12345678901234567890');
echo gmp_strval($bigNum); // "12345678901234567890" — exato

// INTEIROS EM CENTAVOS: a solução mais simples para dinheiro em PHP
// Vantagem: usa aritmética inteira nativa, simples, eficiente
// Desvantagem: requer divisão apenas no output (fácil de lembrar)

// ── Funções de arredondamento: qual usar? ─────────────────────────────────────
$value = 4.5;
echo round($value);    // 5  — arredonda para o mais próximo (padrão)
echo ceil($value);     // 5  — SEMPRE para cima
echo floor($value);    // 4  — SEMPRE para baixo
echo intval($value);   // 4  — trunca (igual ao floor para positivos)
echo (int) $value;     // 4  — cast — ⚠️ PHP 8.5 gera warning se há perda significativa

// PHP_ROUND_HALF_DOWN, PHP_ROUND_HALF_EVEN etc. para casos específicos
echo round(2.5, 0, PHP_ROUND_HALF_DOWN); // 2 — arredonda .5 para baixo
echo round(2.5, 0, PHP_ROUND_HALF_EVEN); // 2 — bancário (par mais próximo)
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Usar float para comparação
$price = 0.1 + 0.2; // 0.30000000000000004
if ($price === 0.3) {
    echo 'Igual'; // ❌ Nunca executa!
}

// ✅ Use epsilon para comparação de floats:
function floatEquals(float $a, float $b, float $eps = PHP_FLOAT_EPSILON): bool
{
    return abs($a - $b) < $eps;
}
var_dump(floatEquals(0.1 + 0.2, 0.3)); // bool(true)

// ❌ ARMADILHA 2: (int) trunca, não arredonda
echo (int) 4.9;    // 4 — perdeu 0.9!
echo (int) -4.9;   // -4 — trunca em direção ao zero (não -5)
// ✅ Use round() antes se precisar arredondar:
echo (int) round(4.9); // 5

// ❌ ARMADILHA 3: PHP 8.5 — cast float→int com perda gera warning
$pi = 3.14159;
$intPi = (int) $pi;  // ⚠️ Deprecated warning em PHP 8.5 se há perda significativa
// ✅ Use intval() — mais explícito sobre a intenção de truncar
$intPi = intval($pi); // Trunca intencionalmente — sem warning

// ❌ ARMADILHA 4: intval() com base automática (base 0)
echo intval('010');     // 10 (decimal)
echo intval('010', 0);  // 8  (octal! base 0 = auto-detect pelo prefixo)
echo intval('0x1A', 0); // 26 (hexadecimal)
// ✅ Sempre especifique a base explicitamente para inteiros de usuário:
echo intval($_GET['id'] ?? '0', 10); // Força base decimal

// ❌ ARMADILHA 5: (bool) com string 'false' retorna true
var_dump((bool) 'false'); // bool(true) — string não-vazia é true!
var_dump((bool) '0');     // bool(false) — única string falsy!
// ✅ Para converter string 'true'/'false' use filter_var:
var_dump(filter_var('false', FILTER_VALIDATE_BOOLEAN)); // bool(false)
var_dump(filter_var('true',  FILTER_VALIDATE_BOOLEAN)); // bool(true)
var_dump(filter_var('yes',   FILTER_VALIDATE_BOOLEAN)); // bool(true)
var_dump(filter_var('1',     FILTER_VALIDATE_BOOLEAN)); // bool(true)
var_dump(filter_var('on',    FILTER_VALIDATE_BOOLEAN)); // bool(true)
```

### Exemplo do Mundo Real — Calculadora de Parcelamento

```php
<?php

declare(strict_types=1);

/**
 * Calcula parcelas de compra com juros usando bcmath.
 * Demonstra uso correto de precisão em cálculos financeiros.
 */
final class InstallmentCalculator
{
    /**
     * Calcula o valor de cada parcela com juros compostos.
     *
     * @param int    $totalCents   Valor total em centavos
     * @param int    $installments Número de parcelas
     * @param float  $monthlyRate  Taxa mensal (ex: 0.0199 = 1,99%)
     *
     * @return int[] Array com o valor de cada parcela em centavos
     */
    public function calculate(int $totalCents, int $installments, float $monthlyRate): array
    {
        if ($totalCents <= 0) {
            throw new \InvalidArgumentException('Valor deve ser positivo.');
        }
        if ($installments < 1 || $installments > 72) {
            throw new \InvalidArgumentException('Parcelas devem ser entre 1 e 72.');
        }
        if ($monthlyRate < 0.0) {
            throw new \InvalidArgumentException('Taxa não pode ser negativa.');
        }

        // Sem juros (parcelamento sem acréscimo)
        if ($monthlyRate === 0.0) {
            $base      = intdiv($totalCents, $installments);
            $remainder = $totalCents % $installments;

            // Distribui o centavo restante na primeira parcela
            $result = array_fill(0, $installments, $base);
            $result[0] += $remainder;
            return $result;
        }

        // Com juros: usa bcmath para precisão
        $principal = (string) $totalCents;
        $rate      = number_format($monthlyRate, 10, '.', '');
        $n         = (string) $installments;

        // Fórmula PMT: P * r * (1+r)^n / ((1+r)^n - 1)
        $onePlusRate = bcadd('1', $rate, 15);
        $factor      = bcpow($onePlusRate, $n, 15);
        $numerator   = bcmul(bcmul($principal, $rate, 15), $factor, 15);
        $denominator = bcsub($factor, '1', 15);
        $pmt         = bcdiv($numerator, $denominator, 2);

        $installmentCents = (int) round((float) $pmt);

        return array_fill(0, $installments, $installmentCents);
    }

    public function formatTable(int $totalCents, int $installments, float $monthlyRate): string
    {
        $parcelas = $this->calculate($totalCents, $installments, $monthlyRate);
        $total    = array_sum($parcelas);

        $lines = ["Parcelamento em {$installments}x (taxa {$monthlyRate}% a.m.):"];
        $lines[] = str_repeat('-', 40);

        foreach ($parcelas as $i => $cents) {
            $lines[] = sprintf(
                'Parcela %02d/%02d: R$ %s',
                $i + 1,
                $installments,
                number_format($cents / 100, 2, ',', '.')
            );
        }

        $lines[] = str_repeat('-', 40);
        $lines[] = sprintf('Total: R$ %s', number_format($total / 100, 2, ',', '.'));

        return implode("\n", $lines);
    }
}

$calc = new InstallmentCalculator();

// R$ 1.000,00 em 12x sem juros
echo $calc->formatTable(100000, 12, 0.0);

// R$ 1.000,00 em 12x com 1,99% a.m.
echo $calc->formatTable(100000, 12, 0.0199);
```

---

## 4. Constantes e Enums

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── const: use para valores verdadeiramente fixos no escopo global ou de classe ──

// Configurações de aplicação — nunca mudam em runtime
const APP_VERSION    = '1.5.0';
const MAX_UPLOAD_MB  = 10;
const ITEMS_PER_PAGE = 20;

// Arrays de configuração
const ALLOWED_IMAGE_TYPES = ['image/jpeg', 'image/png', 'image/webp'];
const ALLOWED_ROLES       = ['admin', 'editor', 'viewer'];

// ── define(): use quando o valor é determinado em runtime ou em condicional ──

// O valor depende do ambiente — determinado em runtime
if (PHP_OS_FAMILY === 'Windows') {
    define('DIR_SEP', '\\');
} else {
    define('DIR_SEP', '/');
}

// O nome da constante é dinâmico (raro mas possível)
$envPrefix = strtoupper($_ENV['APP_ENV'] ?? 'PROD');
define("{$envPrefix}_MODE", true);

// ── Enum: use para conjuntos de valores relacionados (PHP 8.1+) ───────────────

// Substituição SUPERIOR a constantes agrupadas — tipado, exaustivo, com métodos
enum OrderStatus: string
{
    case Pending    = 'pending';
    case Confirmed  = 'confirmed';
    case Shipped    = 'shipped';
    case Delivered  = 'delivered';
    case Cancelled  = 'cancelled';
    case Refunded   = 'refunded';

    public function label(): string
    {
        return match($this) {
            self::Pending   => 'Aguardando pagamento',
            self::Confirmed => 'Pagamento confirmado',
            self::Shipped   => 'Enviado',
            self::Delivered => 'Entregue',
            self::Cancelled => 'Cancelado',
            self::Refunded  => 'Reembolsado',
        };
    }

    public function cssClass(): string
    {
        return match($this) {
            self::Pending   => 'badge-warning',
            self::Confirmed => 'badge-info',
            self::Shipped   => 'badge-primary',
            self::Delivered => 'badge-success',
            self::Cancelled => 'badge-danger',
            self::Refunded  => 'badge-secondary',
        };
    }

    /** Transições válidas de um status */
    public function canTransitionTo(self $next): bool
    {
        return match($this) {
            self::Pending   => in_array($next, [self::Confirmed, self::Cancelled], true),
            self::Confirmed => in_array($next, [self::Shipped, self::Cancelled], true),
            self::Shipped   => in_array($next, [self::Delivered], true),
            self::Delivered => in_array($next, [self::Refunded], true),
            default         => false,
        };
    }
}
```

### Comparações e Alternativas

```php
<?php

declare(strict_types=1);

// ── Por que Enum é superior a constantes agrupadas ────────────────────────────

// ❌ ANTES (constantes): sem type safety, sem validação
class OldOrderStatus
{
    const PENDING   = 'pending';
    const CONFIRMED = 'confirmed';
}

function updateStatus(string $status): void
{
    // PHP não valida se $status é um dos valores válidos!
    // Qualquer string passa sem erro
}

updateStatus('deletado');                   // ❌ Valor inválido — PHP aceita!
updateStatus(OldOrderStatus::PENDING);      // ✅ Mas não há garantia

// ✅ DEPOIS (Enum): type-safe, validado em compile time
function updateStatusModern(OrderStatus $status): void
{
    // PHP garante que $status é um OrderStatus válido
    // Impossível passar qualquer outra coisa
}

// updateStatusModern('deletado');           // ❌ TypeError em tempo de análise
updateStatusModern(OrderStatus::Pending);   // ✅

// Leitura de banco de dados (dados externos → Enum):
$dbValue = 'confirmed'; // Vem do banco
$status  = OrderStatus::tryFrom($dbValue) ?? OrderStatus::Pending;
// tryFrom retorna null se o valor não existir no Enum — nunca lança exceção

// ── Pure Enum vs Backed Enum ──────────────────────────────────────────────────

// Pure Enum: sem valor escalar — apenas para lógica interna
enum Direction
{
    case North;
    case South;
    case East;
    case West;
}

$dir = Direction::North;
// $dir->value; // ❌ Erro — pure enums não têm value

// Backed Enum: tem valor escalar (string ou int) — para banco/API/serialização
enum Color: string
{
    case Red   = '#FF0000';
    case Green = '#00FF00';
    case Blue  = '#0000FF';
}

echo Color::Red->value;               // '#FF0000'
echo Color::Red->name;                // 'Red'
$color = Color::from('#00FF00');      // Color::Green — lança ValueError se não encontrar
$color = Color::tryFrom('#FFFFFF');   // null — não existe no enum
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: const dentro de funções gera Fatal Error
function setup(): void
{
    const MY_CONST = 'value'; // ❌ Fatal Error: const declarations may not be nested
}
// ✅ define() funciona dentro de funções:
function setupFixed(): void
{
    define('MY_CONST', 'value'); // ✅
}

// ❌ ARMADILHA 2: Constantes de classe sem typed constants têm tipo errado
class Config
{
    const TIMEOUT = '30';  // string — mas deveria ser int!
    // ✅ PHP 8.3+: typed class constants
    const int MAX_RETRIES = 3;
    const string BASE_URL = 'https://api.example.com';
}

// ❌ ARMADILHA 3: Enum backed value deve ser único
enum Status: string
{
    case Active   = 'active';
    case Ativo    = 'active'; // ❌ Fatal Error: Duplicate value 'active'
}

// ❌ ARMADILHA 4: from() lança ValueError, tryFrom() retorna null
$input = 'invalido';
$status = OrderStatus::from($input);     // ❌ ValueError lançado!
$status = OrderStatus::tryFrom($input);  // ✅ Retorna null — seguro

// ❌ ARMADILHA 5: Enum não pode ser instanciado como classe
$s = new OrderStatus(); // ❌ Fatal Error — use OrderStatus::Pending

// ❌ ARMADILHA 6: Modificar constante após definição
define('MAX', 100);
define('MAX', 200); // ❌ Notice: Constant MAX already defined — não muda o valor
```

### Exemplo do Mundo Real — Sistema de Permissões com Enum

```php
<?php

declare(strict_types=1);

/**
 * Sistema de permissões baseado em Enum.
 * Demonstra Enum com métodos, comparações e uso em controle de acesso.
 */
enum UserRole: string
{
    case SuperAdmin = 'super_admin';
    case Admin      = 'admin';
    case Editor     = 'editor';
    case Author     = 'author';
    case Viewer     = 'viewer';
    case Guest      = 'guest';

    /** Nível hierárquico (maior = mais permissões) */
    public function level(): int
    {
        return match($this) {
            self::SuperAdmin => 100,
            self::Admin      => 80,
            self::Editor     => 60,
            self::Author     => 40,
            self::Viewer     => 20,
            self::Guest      => 0,
        };
    }

    public function hasPermission(string $action): bool
    {
        $permissions = match($this) {
            self::SuperAdmin => ['read', 'write', 'delete', 'manage_users', 'manage_settings'],
            self::Admin      => ['read', 'write', 'delete', 'manage_users'],
            self::Editor     => ['read', 'write', 'delete'],
            self::Author     => ['read', 'write'],
            self::Viewer     => ['read'],
            self::Guest      => [],
        };

        return in_array($action, $permissions, strict: true);
    }

    public function isAtLeast(self $minimumRole): bool
    {
        return $this->level() >= $minimumRole->level();
    }

    public function label(): string
    {
        return match($this) {
            self::SuperAdmin => 'Super Administrador',
            self::Admin      => 'Administrador',
            self::Editor     => 'Editor',
            self::Author     => 'Autor',
            self::Viewer     => 'Leitor',
            self::Guest      => 'Visitante',
        };
    }
}

// Middleware de autorização
function requirePermission(UserRole $userRole, string $action): void
{
    if (!$userRole->hasPermission($action)) {
        http_response_code(403);
        echo json_encode([
            'error' => "Permissão negada: ação '{$action}' requer papel superior ao seu ({$userRole->label()}).",
        ]);
        exit;
    }
}

// Uso
$currentUserRole = UserRole::tryFrom($_SESSION['user_role'] ?? '') ?? UserRole::Guest;

requirePermission($currentUserRole, 'write');   // Permite para Author, Editor, Admin, SuperAdmin
requirePermission($currentUserRole, 'delete');  // Permite apenas para Editor+

// Verificação hierárquica
if ($currentUserRole->isAtLeast(UserRole::Admin)) {
    echo 'Painel administrativo visível';
}

// Listagem para formulário de criação de usuário
$availableRoles = array_filter(
    UserRole::cases(),
    fn(UserRole $role): bool => $role->level() < $currentUserRole->level()
);
```

---

## 5. Operadores

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Spaceship <=> — ordenação multi-critério ─────────────────────────────────
$employees = [
    ['name' => 'Carlos', 'dept' => 'TI',  'salary' => 8500.0, 'years' => 3],
    ['name' => 'Ana',    'dept' => 'RH',  'salary' => 6200.0, 'years' => 7],
    ['name' => 'Maria',  'dept' => 'TI',  'salary' => 9100.0, 'years' => 5],
    ['name' => 'Bruno',  'dept' => 'TI',  'salary' => 8500.0, 'years' => 1],
];

// Ordenação: dept ASC → salary DESC → years DESC (o mais sênior primeiro no empate)
usort($employees, function (array $a, array $b): int {
    return $a['dept']    <=> $b['dept']     // 1º: dept crescente
        ?: $b['salary']  <=> $a['salary']   // 2º: salary decrescente (invertido!)
        ?: $b['years']   <=> $a['years'];   // 3º: years decrescente
});
// Resultado: [Ana/RH, Maria/TI/9100, Carlos/TI/8500/3y, Bruno/TI/8500/1y]

// ── Null coalescing ?? e ??= — acesso seguro a dados externos ────────────────

// Leitura de configuração com fallback em cadeia
$timeout = $_ENV['DB_TIMEOUT'] ?? $config['timeout'] ?? 30;

// Inicialização lazy com ??=
$cache ??= []; // Inicializa apenas se for null
$cache['key'] ??= expensiveComputation(); // Computa apenas se não existir

// ── Operador nullsafe ?-> — encadeamento sem null checks ─────────────────────

// ❌ Antes: verificação manual tediosa
$city = null;
if ($user !== null) {
    $address = $user->getAddress();
    if ($address !== null) {
        $city = $address->getCity();
    }
}

// ✅ Com nullsafe:
$city = $user?->getAddress()?->getCity(); // null se qualquer parte for null

// ── Operador ternário e Elvis ─────────────────────────────────────────────────

$role = $user['role'] ?? 'guest';

// ?: (Elvis) — substitui o valor se for falsy (null, 0, '', false, [])
$displayName = $user['nickname'] ?: $user['name']; // Usa name se nickname for vazio

// vs ?? — substitui apenas se for null (0 e '' passam!)
$displayName = $user['nickname'] ?? $user['name']; // Usa name apenas se nickname for null
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: and/or têm precedência menor que = (assignment!)
$result = true and false;   // $result é TRUE! (= tem prioridade sobre and)
// Equivale a: ($result = true) and false;
$result = true && false;    // $result é FALSE — correto
// ✅ Sempre use && e || em vez de and e or em expressões de atribuição

// ❌ ARMADILHA 2: == com tipos diferentes — resultados surpreendentes
var_dump(0   == 'php');   // true em PHP 7! (false no PHP 8 — corrigido)
var_dump(0   == '');      // true em PHP 7! (false no PHP 8 — corrigido)
var_dump(100 == '1e2');   // true — notação científica!
var_dump('1' == '01');    // true — comparação numérica de strings!
// ✅ Sempre use === para comparações seguras

// ❌ ARMADILHA 3: Incremento de string (deprecated PHP 8.3)
$s = 'z';
$s++; // 'aa' — comportamento de incremento de string legado
// ✅ Use chr(ord($s) + 1) para manipulação explícita de caracteres

// ❌ ARMADILHA 4: Precedência do operador ternário (resolvida no PHP 8)
// PHP 7: $a ? $b : $c ? $d : $e era ($a ? $b : $c) ? $d : $e (confuso)
// PHP 8: aninhamento de ternários sem parênteses gera erro
// ✅ Sempre use parênteses explícitos em ternários aninhados:
$value = $a ? ($b ? 'b' : 'a') : 'nenhum';

// ❌ ARMADILHA 5: Divisão inteira com / retorna float
var_dump(10 / 3);      // float(3.3333...)
var_dump(intdiv(10, 3)); // int(3) — divisão inteira real

// ❌ ARMADILHA 6: Null coalescing não funciona com undefined array keys de objeto
class Config { public array $settings = []; }
$c = new Config();
// $val = $c->settings['key'] ?? 'default'; // ✅ Funciona
// $val = $c->unknownProp ?? 'default';     // ✅ Funciona com nullsafe
// $val = $c?->settings['key'] ?? 'default'; // ✅ Encadeia nullsafe + ??
```

---

## 6. Estruturas Condicionais — if, match e switch

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Quando usar if ────────────────────────────────────────────────────────────
// Use if para: condições complexas, múltiplos statements por ramo, ranges

$age = 25;

// Condição com range — match não cobre isso de forma natural
if ($age < 13) {
    $category = 'Criança';
} elseif ($age < 18) {
    $category = 'Adolescente';
} elseif ($age < 65) {
    $category = 'Adulto';
} else {
    $category = 'Idoso';
}

// ── Quando usar match ─────────────────────────────────────────────────────────
// Use match para: valores discretos, retorno de valor, comparação estrita

// ✅ match — retorna valor, compara com ===, lança UnhandledMatchError se sem default
$httpMethod = 'POST';
$action = match($httpMethod) {
    'GET'    => 'read',
    'POST'   => 'create',
    'PUT'    => 'replace',
    'PATCH'  => 'update',
    'DELETE' => 'delete',
    'HEAD', 'OPTIONS' => 'metadata', // Múltiplos valores no mesmo ramo
    default  => throw new \InvalidArgumentException("Método HTTP inválido: {$httpMethod}"),
};

// ✅ match com condições booleanas (match(true))
$score = 87;
$grade = match(true) {
    $score >= 90 => 'A',
    $score >= 80 => 'B',
    $score >= 70 => 'C',
    $score >= 60 => 'D',
    default      => 'F',
};

// ── Quando usar switch ────────────────────────────────────────────────────────
// Use switch para: código legado, múltiplos statements com fall-through intencional
// Na maioria dos casos novos, prefira match

// ✅ switch com fall-through intencional (raro, mas válido)
switch ($dayOfWeek) {
    case 1: // Segunda
    case 2: // Terça
    case 3: // Quarta
    case 4: // Quinta
    case 5: // Sexta
        echo 'Dia útil';
        break;
    case 6: // Sábado
    case 0: // Domingo
        echo 'Final de semana';
        break;
    default:
        echo 'Dia inválido';
}
```

### Comparações e Alternativas — match vs switch

```php
<?php

declare(strict_types=1);

$status = 1;

// switch: comparação FROUXA (==), sem retorno, break manual, sem erro se sem match
switch ($status) {
    case '1':   // ✅ Combina com int 1 por causa do ==
        echo 'Ativo';
        break;
}

// match: comparação ESTRITA (===), retorna valor, break automático, erro se sem match
$label = match($status) {
    1  => 'Ativo',     // Só combina com int 1 (===)
    '1'=> 'Texto 1',   // Distinto do caso acima!
    default => '?',
};

// ── Tabela de diferenças ──────────────────────────────────────────────────────

// CARACTERÍSTICA          | switch          | match
// ───────────────────────────────────────────────────
// Tipo de comparação      | == (frouxa)     | === (estrita)
// Retorna valor           | ❌ Não          | ✅ Sim
// Break automático        | ❌ Manual       | ✅ Sim
// Fall-through            | ✅ Possível     | ❌ Impossível
// Sem match + sem default | Continua        | UnhandledMatchError
// Múltiplos valores/ramo  | Casos empilhados| Vírgula: 1, 2, 3 =>
// Permite expressão       | ❌ Não          | ✅ Sim (default => throw)
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: match sem default lança UnhandledMatchError
$input = 'invalido';
try {
    $result = match($input) {
        'ok'   => 'Sucesso',
        'erro' => 'Falha',
        // Sem default — qualquer outro valor lança exceção!
    };
} catch (\UnhandledMatchError $e) {
    $result = 'Desconhecido'; // ✅ Trate ou adicione default
}

// ❌ ARMADILHA 2: switch sem break — fall-through acidental
$color = 'red';
switch ($color) {
    case 'red':
        echo 'Vermelho';
        // ❌ Esqueceu o break! Executa o próximo caso também!
    case 'blue':
        echo 'Azul'; // Executado mesmo com $color = 'red'!
        break;
}

// ❌ ARMADILHA 3: empty() em condicionais — comportamento surpreendente
$count = 0;
if (empty($count)) {
    echo 'Vazio'; // ❌ Executa — zero é "empty"! Mas pode ser um count válido
}
// ✅ Seja específico:
if ($count === null) { echo 'Não definido'; }
if ($count === 0) { echo 'Nenhum registro'; }

// ❌ ARMADILHA 4: Comparar com null usando ==
$value = 0;
if ($value == null) {
    echo 'Nulo'; // ❌ Executa — 0 == null é true com comparação frouxa!
}
if ($value === null) {
    echo 'Nulo'; // ✅ Não executa — 0 !== null
}

// ❌ ARMADILHA 5: if sem chaves em código de produção
if ($isValid)
    doSomething();   // Ok hoje
    doSomethingElse(); // ❌ SEMPRE executa — não está no if!

// ✅ Sempre use chaves, mesmo para uma linha:
if ($isValid) {
    doSomething();
}
```

---

## 7. Loops e Iteração

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Guia de escolha do loop ───────────────────────────────────────────────────

// foreach: PADRÃO — use para arrays, objetos iteráveis, Generator
$products = ['Teclado', 'Mouse', 'Monitor'];
foreach ($products as $index => $product) {
    echo "{$index}: {$product}"; // Índice e valor
}

// for: quando você controla o índice com lógica complexa
// Casos: algoritmos que precisam de dois ponteiros, acesso por posição específica
for ($left = 0, $right = count($products) - 1; $left < $right; $left++, $right--) {
    // Algoritmo two-pointer (ex: verificar palíndromo)
}

// while: quando a condição de parada não é um contador previsível
$fileHandle = fopen('data.csv', 'r');
while (($line = fgets($fileHandle)) !== false) {
    // Lê enquanto houver linhas
}
fclose($fileHandle);

// do...while: o bloco DEVE executar pelo menos uma vez
do {
    $input = readline('Digite um número positivo: ');
    $num   = (int) $input;
} while ($num <= 0); // Repete até input válido

// Generator com yield: para conjuntos grandes sem carregar tudo na memória
function readCsvRows(string $path): \Generator
{
    $handle = fopen($path, 'r') ?: throw new \RuntimeException("Arquivo não encontrado: {$path}");

    try {
        fgetcsv($handle); // Pula cabeçalho
        while (($row = fgetcsv($handle)) !== false) {
            yield $row; // Produz uma linha por vez
        }
    } finally {
        fclose($handle); // Sempre fecha, mesmo com exceção
    }
}

// Processa arquivo de 1 GB com uso constante de memória
foreach (readCsvRows('/data/huge-file.csv') as $i => $row) {
    processRow($row);
}
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Modificar array no foreach sem referência (sem efeito)
$prices = [10.0, 20.0, 30.0];

foreach ($prices as $price) {
    $price *= 1.1; // ❌ Modifica a cópia local — original NÃO muda!
}
var_dump($prices); // Ainda [10, 20, 30]

// ✅ Use referência ou array_map:
foreach ($prices as &$price) {
    $price *= 1.1; // ✅ Modifica o original
}
unset($price); // ✅ OBRIGATÓRIO — remove a referência ao último elemento

// ❌ ARMADILHA 2: Esquecer unset() após foreach por referência
$items = [1, 2, 3];
foreach ($items as &$item) {
    $item *= 2; // [2, 4, 6]
}
// SEM unset($item):
$item = 99; // $items[2] (último elemento) vira 99!
var_dump($items); // [2, 4, 99] — surpresa!

// ✅ Array map é mais seguro que referência:
$prices = array_map(fn(float $p): float => $p * 1.1, $prices);

// ❌ ARMADILHA 3: count() chamado a cada iteração no for
$bigArr = range(1, 100000);
for ($i = 0; $i < count($bigArr); $i++) { } // count() chamado 100.001 vezes!

// ✅ Cache o count fora do loop:
$len = count($bigArr);
for ($i = 0; $i < $len; $i++) { } // count() chamado 1 vez

// ❌ ARMADILHA 4: break sem número em loops aninhados
for ($i = 0; $i < 5; $i++) {
    for ($j = 0; $j < 5; $j++) {
        if ($j === 2) break; // Quebra apenas o loop INTERNO ($j)!
    }
    echo $i; // 0 1 2 3 4 — loop externo continua
}

// ✅ Use break 2 para sair de dois níveis:
for ($i = 0; $i < 5; $i++) {
    for ($j = 0; $j < 5; $j++) {
        if ($j === 2) break 2; // Sai de ambos os loops
    }
    echo $i; // Nunca executado após break 2
}

// ❌ ARMADILHA 5: Loop infinito silencioso
$i = 0;
while ($i < 10) {
    processItem($i);
    // Esqueceu $i++ — loop infinito sem warning!
}
// ✅ Sempre revise que a condição de parada é atingida
```

---

## 8. Funções e Closures

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Funções nomeadas: lógica reutilizável com nome descritivo ─────────────────
function formatCurrency(int $cents, string $currency = 'BRL'): string
{
    return match($currency) {
        'BRL' => 'R$ ' . number_format($cents / 100, 2, ',', '.'),
        'USD' => '$ ' . number_format($cents / 100, 2, '.', ','),
        default => throw new \InvalidArgumentException("Moeda desconhecida: {$currency}"),
    };
}

// ── Closures anônimas: lógica de uso único, captura do escopo ─────────────────
$discountRate = 0.10;

$applyDiscount = function(int $priceCents) use ($discountRate): int {
    return (int) round($priceCents * (1 - $discountRate));
};

$discountedPrice = $applyDiscount(10000); // R$ 100,00 → R$ 90,00

// ── Arrow functions: closures concisas que capturam automaticamente ────────────
$taxRate   = 0.12;
$addTax    = fn(int $cents): int => (int) round($cents * (1 + $taxRate));
$prices    = [1000, 2500, 5000];
$withTax   = array_map($addTax, $prices); // [1120, 2800, 5600]

// ── FCC — First-Class Callable Syntax (PHP 8.1+) ─────────────────────────────
// Converte qualquer callable em Closure — mais seguro que string
$cleaners = [
    trim(...),          // FCC de função nativa
    strtolower(...),    // FCC de função nativa
    htmlspecialchars(...), // FCC de função nativa
];

$clean = array_reduce(
    $cleaners,
    fn(string $carry, callable $fn): string => $fn($carry),
    '  <B>PHP 8.5</B>  '
);
// Resultado: "&lt;b&gt;php 8.5&lt;/b&gt;"

// ── PHP 8.5: Closure::getCurrent() — recursão em closure anônima ─────────────
$factorial = function(int $n): int {
    if ($n <= 1) return 1;
    return $n * (Closure::getCurrent())($n - 1); // Referência à própria closure
};
echo $factorial(5); // 120
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Captura por referência acidental em closure
$multiplier = 3;
$triple = fn(int $n): int => $n * $multiplier; // Arrow: captura por VALOR

$multiplier = 10; // Muda o externo
echo $triple(5);  // 15 — capturou o valor 3 no momento da definição

// Com closure anônima e use() sem &:
$double = function(int $n) use ($multiplier): int {
    return $n * $multiplier; // Capturou $multiplier no momento do use()
};
$multiplier = 100;
echo $double(5); // 50 — ainda usa o valor capturado (10)

// ❌ ARMADILHA 2: Passar nome de função como string — sem verificação de typo
$result = array_map('strtolwer', $items); // typo em "strtolower"!
// PHP só detecta o erro em runtime (quando array_map tentar chamar a função)

// ✅ Use FCC — erros de typo detectados em análise estática:
$result = array_map(strtolower(...), $items); // ❌ Detectado imediatamente

// ❌ ARMADILHA 3: Parâmetro variádico no meio da lista
function invalid(string $first, ...$rest, string $last): void {} // Fatal Error!
// ✅ Variádico SEMPRE é o último:
function valid(string $first, string $last, string ...$middle): void {}

// ❌ ARMADILHA 4: Retornar null implicitamente quando tipo declara string
function getName(int $id): string
{
    if ($id === 0) {
        return; // ❌ TypeError! Retorna null implicitamente
    }
    return 'Ana';
}
// ✅ Declare ?string ou lance exceção:
function getNameFixed(int $id): ?string
{
    return $id === 0 ? null : 'Ana';
}

// ❌ ARMADILHA 5: never não pode ter return
function fail(string $msg): never
{
    // throw new \RuntimeException($msg); // ✅ Correto para never
    return; // ❌ Fatal Error — never não pode retornar nada, nem void
}
```

---

## 9. Arrays — Fundamentos e Programação Funcional

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── array_filter + array_map + array_reduce: a trindade funcional ────────────

$orders = [
    ['id' => 1, 'total' => 150.0,  'status' => 'completed', 'items' => 3],
    ['id' => 2, 'total' => 89.90,  'status' => 'pending',   'items' => 1],
    ['id' => 3, 'total' => 320.0,  'status' => 'completed', 'items' => 5],
    ['id' => 4, 'total' => 45.0,   'status' => 'cancelled', 'items' => 1],
    ['id' => 5, 'total' => 200.0,  'status' => 'completed', 'items' => 2],
];

// 1. Filtra pedidos concluídos
$completed = array_values(array_filter(
    $orders,
    fn(array $o): bool => $o['status'] === 'completed'
));

// 2. Transforma: extrai apenas o total de cada pedido
$totals = array_map(fn(array $o): float => $o['total'], $completed);

// 3. Agrega: soma todos os totais
$revenue = array_reduce($totals, fn(float $sum, float $t): float => $sum + $t, 0.0);

echo "Receita: R$ " . number_format($revenue, 2, ',', '.'); // R$ 670,00

// ✅ PHP 8.5: Pipeline com Pipe Operator — legível como linguagem natural
$avgTicket = $orders
    |> (fn(array $arr): array  => array_filter($arr, fn($o) => $o['status'] === 'completed'))
    |> (fn(array $arr): array  => array_column($arr, 'total'))
    |> (fn(array $arr): float  => array_sum($arr) / max(count($arr), 1));

echo "Ticket médio: R$ " . number_format($avgTicket, 2, ',', '.'); // R$ 223,33

// ── array_column: o atalho mais subestimado do PHP ───────────────────────────
// Extrai uma "coluna" e pode reindexar por outra coluna

$users = [
    ['id' => 1, 'name' => 'Ana',    'email' => 'ana@x.com',    'role' => 'admin'],
    ['id' => 2, 'name' => 'Carlos', 'email' => 'carlos@x.com', 'role' => 'editor'],
    ['id' => 3, 'name' => 'Maria',  'email' => 'maria@x.com',  'role' => 'viewer'],
];

$names     = array_column($users, 'name');          // ['Ana', 'Carlos', 'Maria']
$byId      = array_column($users, null, 'id');       // Indexado por ID — lookup O(1)!
$emailById = array_column($users, 'email', 'id');   // [1 => 'ana@x.com', ...]

// Antes era necessário loop para indexar por ID:
echo $byId[2]['name'];     // 'Carlos' — acesso direto sem loop
echo $emailById[3];        // 'maria@x.com'

// ── PHP 8.5: array_first() e array_last() ────────────────────────────────────
$scores = [85, 92, 78, 95, 88];
$empty  = [];

echo array_first($scores); // 85
echo array_last($scores);  // 88
var_dump(array_first($empty)); // NULL — seguro, sem erro

// ❌ LEGACY: reset() e end() têm side effects no ponteiro interno
// $first = reset($scores); // Move o ponteiro interno!
// $last  = end($scores);   // Move o ponteiro interno!
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: array_filter cria buracos nos índices
$numbers = [0, 1, 2, 3, 4, 5];
$nonZero = array_filter($numbers); // Remove 0 (falsy), mas mantém chaves!
var_dump(array_keys($nonZero)); // [1, 2, 3, 4, 5] — chave 0 sumiu!

// Isso causa erro se o código espera índice começando em 0:
echo $nonZero[0]; // ⚠️ Undefined offset 0!

// ✅ Sempre re-indexe após filter se precisar de índices sequenciais:
$nonZero = array_values(array_filter($numbers));
var_dump(array_keys($nonZero)); // [0, 1, 2, 3, 4]

// ❌ ARMADILHA 2: in_array() sem strict — comparação frouxa perigosa
var_dump(in_array('1', [1, 2, 3]));       // true  — string '1' == int 1!
var_dump(in_array('php', [0, 1, 2]));     // true  — 'php' == 0 (conversão PHP 7)!
var_dump(in_array('1', [1, 2, 3], true)); // false — string !== int
// ✅ SEMPRE use o terceiro parâmetro true (strict mode):
var_dump(in_array(1, [1, 2, 3], strict: true)); // true — correto

// ❌ ARMADILHA 3: array_search retorna false OU a chave (incluindo 0)
$arr = ['zero', 'um', 'dois'];
$key = array_search('zero', $arr); // Retorna 0 (int) — mas 0 é falsy!

if ($key) { echo 'encontrou'; }         // ❌ 0 é falsy — não executa!
if ($key !== false) { echo 'encontrou'; } // ✅ Usa !== false, não !$key

// ❌ ARMADILHA 4: sort() em associativo perde as chaves
$ages = ['Pedro' => 35, 'Ana' => 28, 'Zé' => 42];
sort($ages); // ❌ Perde as chaves! Vira [0 => 28, 1 => 35, 2 => 42]
// ✅ Para associativos, use asort() (preserva chaves):
asort($ages); // ['Ana' => 28, 'Pedro' => 35, 'Zé' => 42]

// ❌ ARMADILHA 5: array_splice modifica o array original (side effect!)
$items = ['A', 'B', 'C', 'D'];
$removed = array_splice($items, 1, 2); // ❌ Modifica $items in-place!
// $items agora é ['A', 'D']! E retorna ['B', 'C']

// ✅ Se quiser extrair sem modificar, use array_slice:
$slice = array_slice($items, 1, 2); // Retorna ['B', 'C'], $items intacto
```

### Exemplo do Mundo Real — Relatório de Vendas

```php
<?php

declare(strict_types=1);

/**
 * Gera relatório de vendas a partir de array de pedidos.
 * Demonstra: filter, map, reduce, column, groupBy e PHP 8.5 features.
 */
final class SalesReport
{
    /** @param array<int, array{id: int, seller: string, total: float, category: string, date: string}> $orders */
    public function __construct(private readonly array $orders) {}

    /** Total de receita de pedidos concluídos */
    public function totalRevenue(): float
    {
        return $this->orders
            |> (fn(array $arr): array => array_filter($arr, fn($o) => $o['status'] === 'completed'))
            |> (fn(array $arr): array => array_column($arr, 'total'))
            |> array_sum(...);
    }

    /** Agrupa pedidos por vendedor com totais */
    public function bySeller(): array
    {
        $result = [];
        foreach ($this->orders as $order) {
            $seller = $order['seller'];
            $result[$seller] ??= ['orders' => 0, 'revenue' => 0.0, 'seller' => $seller];
            $result[$seller]['orders']++;
            $result[$seller]['revenue'] += $order['total'];
        }

        // Ordena por receita decrescente
        usort($result, fn(array $a, array $b): int => $b['revenue'] <=> $a['revenue']);

        return array_values($result);
    }

    /** Top N categorias por receita */
    public function topCategories(int $limit = 5): array
    {
        $byCategory = [];
        foreach ($this->orders as $order) {
            $cat = $order['category'];
            $byCategory[$cat] = ($byCategory[$cat] ?? 0.0) + $order['total'];
        }

        arsort($byCategory); // Ordena por valor (receita) decrescente
        return array_slice($byCategory, 0, $limit, preserve_keys: true);
    }

    /** Melhor e pior dia de vendas */
    public function extremeDays(): array
    {
        $byDate = [];
        foreach ($this->orders as $order) {
            $date = $order['date'];
            $byDate[$date] = ($byDate[$date] ?? 0.0) + $order['total'];
        }

        return [
            'best'  => ['date' => array_key_first($byDate), 'revenue' => array_first(array_values($byDate))],
            'worst' => ['date' => array_key_last($byDate),  'revenue' => array_last(array_values($byDate))],
        ];
    }
}
```

---

## 10. Orientação a Objetos — Classes e Objetos

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Por que usar OOP? — comparação procedural vs orientado a objetos ──────────

// ❌ Abordagem procedural: funções soltas, estado global, difícil de testar
$userName    = 'Ana';
$userEmail   = 'ana@example.com';
$userBalance = 1000;

function getUserBalance(int $userId): int { /* ... */ }
function debitUser(int $userId, int $amount): void { /* ... */ }
function creditUser(int $userId, int $amount): void { /* ... */ }
// Problema: sem encapsulamento — qualquer parte do código pode modificar $userBalance!
// Sem tipo: o que é "userId"? string? int? Como a função valida?

// ✅ Abordagem OOP: encapsulado, coeso, testável
final class BankAccount
{
    private int $balanceCents;

    public function __construct(
        private readonly int    $id,
        private readonly string $owner,
        int                     $initialBalanceCents = 0,
    ) {
        if ($initialBalanceCents < 0) {
            throw new \InvalidArgumentException('Saldo inicial não pode ser negativo.');
        }
        $this->balanceCents = $initialBalanceCents;
    }

    public function getBalanceCents(): int { return $this->balanceCents; }
    public function getOwner(): string { return $this->owner; }

    public function debit(int $amountCents): void
    {
        if ($amountCents <= 0) {
            throw new \InvalidArgumentException('Valor de débito deve ser positivo.');
        }
        if ($amountCents > $this->balanceCents) {
            throw new \RuntimeException('Saldo insuficiente.');
        }
        $this->balanceCents -= $amountCents;
    }

    public function credit(int $amountCents): void
    {
        if ($amountCents <= 0) {
            throw new \InvalidArgumentException('Valor de crédito deve ser positivo.');
        }
        $this->balanceCents += $amountCents;
    }

    public function getFormattedBalance(): string
    {
        return 'R$ ' . number_format($this->balanceCents / 100, 2, ',', '.');
    }
}

$account = new BankAccount(id: 1, owner: 'Ana', initialBalanceCents: 100000);
$account->credit(50000);  // +R$500
$account->debit(25000);   // -R$250
echo $account->getFormattedBalance(); // R$ 1.250,00
```

### Armadilhas Comuns de OOP

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: God Object — classe que faz tudo
final class UserManager
{
    public function validateEmail(string $email): bool { /* ... */ }
    public function saveToDatabase(array $data): void { /* ... */ }
    public function sendWelcomeEmail(string $email): void { /* ... */ }
    public function generateReport(): string { /* ... */ }
    public function hashPassword(string $pass): string { /* ... */ }
    // 50 métodos... — impossível de testar, manter e entender
}

// ✅ Single Responsibility: cada classe tem uma responsabilidade
final class EmailValidator { public function validate(string $email): bool { /* ... */ } }
final class UserRepository { public function save(array $data): int { /* ... */ } }
final class WelcomeEmailSender { public function send(string $email): void { /* ... */ } }
final class PasswordHasher { public function hash(string $pass): string { /* ... */ } }

// ❌ ARMADILHA 2: Herança para reuso de código sem relação semântica
class Database
{
    protected function query(string $sql): array { /* ... */ }
}

class UserService extends Database
{
    // ❌ "UserService É UM Database?" — Não! Herança errada!
    public function getUser(int $id): array
    {
        return $this->query("SELECT * FROM users WHERE id = {$id}");
    }
}

// ✅ Use composição (injeção de dependência):
final class UserService
{
    public function __construct(
        private readonly \PDO $pdo, // Injeta a dependência
    ) {}

    public function getUser(int $id): ?array
    {
        $stmt = $this->pdo->prepare('SELECT * FROM users WHERE id = :id');
        $stmt->execute(['id' => $id]);
        $row = $stmt->fetch();
        return $row !== false ? $row : null;
    }
}

// ❌ ARMADILHA 3: Propriedades públicas sem controle
class Order
{
    public float $total = 0.0; // ❌ Qualquer um pode setar $order->total = -99!
}

// ✅ Propriedades readonly ou com setter validado:
final class Order
{
    private float $totalCents = 0.0;

    public function addItem(int $priceCents, int $qty): void
    {
        if ($priceCents <= 0 || $qty <= 0) {
            throw new \InvalidArgumentException('Preço e quantidade devem ser positivos.');
        }
        $this->totalCents += $priceCents * $qty;
    }

    public function getTotal(): float
    {
        return $this->totalCents / 100;
    }
}

// ❌ ARMADILHA 4: __toString que lança exceção (deprecado PHP 8.5 como comportamento)
class Product
{
    public function __toString(): string
    {
        throw new \RuntimeException('Não pode converter para string'); // ❌ Deprecado!
        // ✅ Nunca lance exceção em __toString — retorne string sempre
    }
}
```

---

## 11. Herança, Interfaces e Traits

### Quando Usar Cada Um

```php
<?php

declare(strict_types=1);

// ── Herança: relação "É UM" — compartilha implementação ──────────────────────
// Use quando: há uma hierarquia natural, comportamento base compartilhado

abstract class Vehicle
{
    public function __construct(
        public readonly string $brand,
        public readonly string $model,
        public readonly int    $year,
    ) {}

    abstract public function fuelType(): string;
    abstract public function rangeKm(): int;

    // Comportamento compartilhado por todos os veículos
    public function describe(): string
    {
        return "{$this->year} {$this->brand} {$this->model} ({$this->fuelType()})";
    }
}

final class ElectricCar extends Vehicle
{
    public function __construct(
        string $brand, string $model, int $year,
        private readonly int $batteryKwh,
    ) {
        parent::__construct($brand, $model, $year);
    }

    public function fuelType(): string { return 'Elétrico'; }
    public function rangeKm(): int { return $this->batteryKwh * 6; } // ~6km/kWh
}

// ── Interface: contrato — "PODE FAZER" — sem implementação ───────────────────
// Use quando: diferentes hierarquias precisam do mesmo contrato

interface Exportable
{
    public function toArray(): array;
    public function toJson(): string;
    public function toCsv(): string;
}

interface Cacheable
{
    public function getCacheKey(): string;
    public function getCacheTtl(): int;
}

// Uma classe pode implementar múltiplas interfaces (herança múltipla de contrato)
final class UserReport implements Exportable, Cacheable
{
    public function __construct(private readonly array $data) {}

    public function toArray(): array { return $this->data; }
    public function toJson(): string { return json_encode($this->data, JSON_THROW_ON_ERROR); }
    public function toCsv(): string { /* ... */ return ''; }

    public function getCacheKey(): string { return 'user_report_' . date('Y-m-d'); }
    public function getCacheTtl(): int { return 3600; }
}

// ── Trait: reuso horizontal — "TEM" — sem herança ────────────────────────────
// Use quando: código comum entre classes sem hierarquia relacionada

trait HasTimestamps
{
    private \DateTimeImmutable $createdAt;
    private \DateTimeImmutable $updatedAt;

    public function initTimestamps(): void
    {
        $now = new \DateTimeImmutable();
        $this->createdAt = $now;
        $this->updatedAt = $now;
    }

    public function touch(): void
    {
        $this->updatedAt = new \DateTimeImmutable();
    }

    public function getCreatedAt(): \DateTimeImmutable { return $this->createdAt; }
    public function getUpdatedAt(): \DateTimeImmutable { return $this->updatedAt; }
}

trait SoftDeletable
{
    private ?\DateTimeImmutable $deletedAt = null;

    public function softDelete(): void { $this->deletedAt = new \DateTimeImmutable(); }
    public function restore(): void { $this->deletedAt = null; }
    public function isDeleted(): bool { return $this->deletedAt !== null; }
}

// Qualquer entidade pode usar os traits — sem herança forçada
final class Article { use HasTimestamps, SoftDeletable; }
final class Comment { use HasTimestamps; }
final class Category { use HasTimestamps, SoftDeletable; }
```

---

## 12. Exceções e Tratamento de Erros

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Quando lançar exceção vs retornar null/false ──────────────────────────────

// Retorne null: quando "não encontrado" é um resultado NORMAL esperado
function findUserByEmail(\PDO $pdo, string $email): ?array
{
    $stmt = $pdo->prepare('SELECT * FROM users WHERE email = :email LIMIT 1');
    $stmt->execute(['email' => $email]);
    $row = $stmt->fetch();
    return $row !== false ? $row : null; // null = não encontrado (normal)
}

// Lance exceção: quando uma pré-condição ou invariante é violada
function findUserById(\PDO $pdo, int $id): array
{
    if ($id <= 0) {
        throw new \InvalidArgumentException("ID deve ser positivo: {$id}");
    }

    $stmt = $pdo->prepare('SELECT * FROM users WHERE id = :id LIMIT 1');
    $stmt->execute(['id' => $id]);
    $row = $stmt->fetch();

    if ($row === false) {
        throw new \RuntimeException("Usuário #{$id} não encontrado."); // Inesperado neste contexto
    }

    return $row;
}

// ── Hierarquia de exceções customizadas ─────────────────────────────────────
class DomainException extends \RuntimeException {} // Base para o domínio

class UserNotFoundException extends DomainException
{
    public function __construct(int $userId, ?\Throwable $previous = null)
    {
        parent::__construct("Usuário #{$userId} não encontrado.", 404, $previous);
    }
}

class InsufficientFundsException extends DomainException
{
    public function __construct(
        public readonly int $requestedCents,
        public readonly int $availableCents,
        ?\Throwable $previous = null,
    ) {
        parent::__construct(
            sprintf(
                'Saldo insuficiente. Solicitado: R$ %s, disponível: R$ %s.',
                number_format($requestedCents / 100, 2, ',', '.'),
                number_format($availableCents / 100, 2, ',', '.'),
            ),
            422,
            $previous,
        );
    }
}

// ── try/catch/finally — padrões de uso ──────────────────────────────────────
function transfer(\PDO $pdo, int $fromId, int $toId, int $amountCents): void
{
    $pdo->beginTransaction();

    try {
        $from = findUserById($pdo, $fromId);
        $to   = findUserById($pdo, $toId);

        if ($from['balance_cents'] < $amountCents) {
            throw new InsufficientFundsException($amountCents, $from['balance_cents']);
        }

        // Operações de banco...
        $pdo->commit();

    } catch (InsufficientFundsException $e) {
        $pdo->rollBack();
        throw $e; // Re-lança para o controller tratar

    } catch (\Throwable $e) {
        $pdo->rollBack();
        throw new \RuntimeException('Transferência falhou: ' . $e->getMessage(), previous: $e);

    } finally {
        // finally SEMPRE executa — independente de exceção ou return
        // Use para liberar recursos, fechar conexões, fazer limpeza
        error_log("Transfer {$fromId}→{$toId} finalized");
    }
}
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: catch genérico esconde bugs importantes
try {
    risky();
} catch (\Throwable $e) {
    // ❌ Silencia TypeError, ParseError, TUDO — bugs passam despercebidos!
    echo 'Erro';
}

// ✅ Catch específico, re-lance o que não sabe tratar:
try {
    risky();
} catch (DomainException $e) {
    handleDomainError($e); // Trata o que conhece
} catch (\Throwable $e) {
    error_log($e->getMessage()); // Log interno
    throw $e; // Re-lança — deixa o handler de topo decidir
}

// ❌ ARMADILHA 2: Exception chaining sem previous — perde o contexto
try {
    $pdo->query($sql);
} catch (\PDOException $e) {
    error_log($e->getMessage());
    throw new \RuntimeException('Falha no banco'); // ❌ Perda do erro original!
}

// ✅ Sempre passe a exceção anterior com previous:
try {
    $pdo->query($sql);
} catch (\PDOException $e) {
    throw new \RuntimeException('Falha no banco.', previous: $e); // ✅ Contexto preservado
}

// ❌ ARMADILHA 3: finally com return sobrescreve o return do try/catch
function riskyOp(): string
{
    try {
        return 'sucesso';
    } catch (\Exception $e) {
        return 'erro';
    } finally {
        return 'finally'; // ❌ SEMPRE retorna 'finally', sobrescreve tudo!
    }
}
// ✅ finally é apenas para limpeza — nunca para retorno de valor

// ❌ ARMADILHA 4: Usar exceção para controle de fluxo normal
function findProduct(int $id): ?array
{
    throw new NotFoundException("Produto {$id}"); // ❌ "Não encontrado" é fluxo normal!
}
// ✅ Retorne null para ausência esperada, lance exceção para erros inesperados:
function findProductFixed(int $id): ?array
{
    return $db->find($id) ?: null; // null = não encontrou (ok)
}
```

---

## 13. Superglobais e Formulários

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Quando usar cada superglobal ─────────────────────────────────────────────

// $_GET: dados de busca, filtros, paginação — operações de LEITURA
// Visível na URL, pode ser favoritado, sem limite prático para URLs normais
$page      = filter_input(INPUT_GET, 'page', FILTER_VALIDATE_INT, ['options' => ['default' => 1, 'min_range' => 1]]) ?? 1;
$search    = filter_input(INPUT_GET, 'q',    FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
$sortBy    = filter_input(INPUT_GET, 'sort', FILTER_SANITIZE_SPECIAL_CHARS) ?? 'name';

// ✅ Whitelist de valores permitidos para sort (NUNCA interpole diretamente em SQL):
$allowedSorts = ['name', 'price', 'date', 'popularity'];
$sortBy = in_array($sortBy, $allowedSorts, strict: true) ? $sortBy : 'name';

// $_POST: criação, atualização, deleção — operações de ESCRITA
// Dados no body HTTP, não visível na URL, sem limite prático de tamanho
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // ✅ Valide token CSRF PRIMEIRO
    $submittedToken = $_POST['csrf_token'] ?? '';
    if (!hash_equals($_SESSION['csrf_token'] ?? '', $submittedToken)) {
        http_response_code(403);
        exit('Requisição inválida.');
    }

    // ✅ Depois valide e processe os dados
    $name  = filter_input(INPUT_POST, 'name',  FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
    $email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);
}

// $_SERVER: informações do servidor e requisição
// ⚠️ Muitos valores podem ser forjados pelo cliente — use só para leitura/log
$method    = $_SERVER['REQUEST_METHOD'];           // Confiável
$isHttps   = !empty($_SERVER['HTTPS']) && $_SERVER['HTTPS'] !== 'off'; // Confiável
$userAgent = $_SERVER['HTTP_USER_AGENT'] ?? '';   // ⚠️ Pode ser forjado
$clientIp  = $_SERVER['REMOTE_ADDR']     ?? '';   // ⚠️ Pode ser forjado via proxy
```

### Armadilhas de Formulários

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: PHP_SELF sem escape — XSS via URL
// URL: /form.php/"><script>alert(1)</script>
echo '<form action="' . $_SERVER['PHP_SELF'] . '">'; // ❌ XSS!

// ✅ Sempre escape PHP_SELF:
echo '<form action="' . htmlspecialchars($_SERVER['PHP_SELF'], ENT_QUOTES | ENT_HTML5, 'UTF-8') . '">';

// ❌ ARMADILHA 2: Usar $_REQUEST — ambíguo e inseguro
$name = $_REQUEST['name']; // ❌ Pode vir de GET, POST ou COOKIE — sem clareza
// ✅ Sempre use a superglobal específica:
$name = $_POST['name'] ?? ''; // Explícito: espero POST

// ❌ ARMADILHA 3: Não verificar REQUEST_METHOD antes de processar
$name = $_POST['name'] ?? ''; // ❌ Processa mesmo em GET (name seria vazio)
echo "Olá, {$name}"; // ❌ Pode exibir vazio ou processar dados inválidos

// ✅ Sempre verifique o método antes:
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $name = filter_input(INPUT_POST, 'name', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';
    // Processa
}

// ❌ ARMADILHA 4: Re-submissão de formulário ao recarregar (F5)
// ✅ Use o padrão Post/Redirect/Get (PRG):
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // Processa...
    header('Location: /sucesso.php?id=' . $newId);
    exit; // ✅ Redireciona após POST — F5 não re-submete
}

// ❌ ARMADILHA 5: Exibir dados de formulário sem escape
$name = $_POST['name'];
echo "Olá, {$name}!"; // ❌ XSS se name contiver <script>
// ✅ Sempre escape ao exibir:
echo 'Olá, ' . htmlspecialchars($name, ENT_QUOTES | ENT_HTML5, 'UTF-8') . '!';
```

---

## 14. Sessões e Cookies

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Sessão: dados no servidor, ID no cliente via cookie ──────────────────────
// Use para: dados de autenticação, carrinho, preferências de sessão

// SEMPRE configure antes de session_start():
ini_set('session.cookie_httponly',  '1'); // ✅ JS não acessa o cookie
ini_set('session.cookie_secure',    '1'); // ✅ Apenas HTTPS
ini_set('session.cookie_samesite',  'Strict'); // ✅ Previne CSRF
ini_set('session.use_strict_mode',  '1'); // ✅ Rejeita IDs externos
ini_set('session.gc_maxlifetime',   '1800'); // 30 min de inatividade
session_start();

// ── Cookie: dados no browser, enviados em toda requisição ────────────────────
// Use para: preferências de longo prazo, "lembrar-me" (com token, não dados!)

// ✅ Preferência de tema — pode ficar 1 ano no browser
setcookie(
    name:     'ui_theme',
    value:    'dark',
    expires:  time() + (86400 * 365),
    path:     '/',
    secure:   true,
    httponly: false, // JS pode ler para aplicar o tema imediatamente
);

// ✅ "Lembrar-me" — NUNCA armazene userId/role no cookie!
// Armazene um token aleatório, valide-o no banco:
$rememberToken = bin2hex(random_bytes(32)); // 64 chars hex
$tokenHash     = hash('sha256', $rememberToken); // Salve o HASH no banco
// INSERT INTO remember_tokens (user_id, token_hash, expires_at) ...

setcookie(
    name:     'remember_token',
    value:    $rememberToken, // Token raw no cookie
    expires:  time() + (86400 * 30),
    path:     '/',
    secure:   true,
    httponly: true, // JS não precisa ler
);

// ── Sistema completo de login seguro ─────────────────────────────────────────
function performLogin(\PDO $pdo, string $email, string $password): bool
{
    $stmt = $pdo->prepare('SELECT id, name, password_hash, role FROM users WHERE email = :email AND active = 1');
    $stmt->execute(['email' => strtolower(trim($email))]);
    $user = $stmt->fetch();

    // ✅ password_verify é timing-safe — previne timing attacks
    if ($user === false || !password_verify($password, $user['password_hash'])) {
        return false; // Mesma mensagem para email errado e senha errada
    }

    // ✅ Regenera o ID ANTES de escrever dados de autenticação — previne session fixation
    session_regenerate_id(true);

    $_SESSION['user_id']       = (int)    $user['id'];
    $_SESSION['user_name']     = (string) $user['name'];
    $_SESSION['user_role']     = (string) $user['role'];
    $_SESSION['login_time']    = time();
    $_SESSION['last_activity'] = time();

    return true;
}
```

### Armadilhas de Sessão e Cookie

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: session_start() após qualquer output
echo 'Olá'; // Qualquer output, incluindo BOM ou espaços antes de <?php
session_start(); // ❌ Warning: Cannot send session cookie - headers already sent

// ✅ Sempre session_start() antes de qualquer output HTML

// ❌ ARMADILHA 2: Não regenerar o ID após login — session fixation
// Fluxo do ataque:
// 1. Atacante visita /login.php → obtém PHPSESSID=xyz
// 2. Envia link com PHPSESSID=xyz para a vítima (ex: via parâmetro na URL)
// 3. Vítima loga com ID xyz — sessão xyz agora está autenticada
// 4. Atacante usa xyz — está autenticado como a vítima!
// ✅ session_regenerate_id(true) imediatamente após login!

// ❌ ARMADILHA 3: Logout incompleto — dados do servidor removidos, cookie ainda existe
session_destroy(); // ❌ Remove dados do servidor, mas PHPSESSID ainda está no browser!

// ✅ Logout completo em 3 etapas:
session_unset();                // 1. Remove todas as variáveis
session_destroy();              // 2. Destroi a sessão no servidor
setcookie(                      // 3. Remove o cookie do browser
    name:    session_name(),
    value:   '',
    expires: time() - 3600,
    path:    '/',
);

// ❌ ARMADILHA 4: Armazenar dados sensíveis em cookies
setcookie('user_role', 'admin');  // ❌ Usuário pode editar o cookie e se tornar admin!
setcookie('user_id', '1');        // ❌ Usuário pode se passar por outro usuário!
// ✅ Armazene apenas em $_SESSION (no servidor):
$_SESSION['user_role'] = 'admin'; // ✅ O cliente só tem o PHPSESSID

// ❌ ARMADILHA 5: Cookie sem secure em HTTPS
setcookie('auth_token', $token); // ❌ Cookie enviado em HTTP e HTTPS
// ✅ secure: true garante envio apenas via HTTPS:
setcookie('auth_token', $token, secure: true, httponly: true);
```

---

## 15. Filtros, Validação e Sanitização

### Estratégia de Validação em 4 Camadas

```php
<?php

declare(strict_types=1);

// ── CAMADA 1: HTML5 — conforto do usuário, NÃO segurança ─────────────────────
// <input type="email" required maxlength="150">
// Facilmente bypassado com curl/Postman — nunca confie nisso sozinho

// ── CAMADA 2: Sanitização PHP — limpa o dado ─────────────────────────────────
// Remove/substitui caracteres inválidos, normaliza formato
$rawEmail = $_POST['email'] ?? '';
$cleanEmail = strtolower(trim($rawEmail));

// ── CAMADA 3: Validação PHP — verifica o formato ─────────────────────────────
$validEmail = filter_var($cleanEmail, FILTER_VALIDATE_EMAIL);
if ($validEmail === false) {
    $errors['email'] = 'Formato de e-mail inválido.';
}

// ── CAMADA 4: Banco de dados — última defesa ──────────────────────────────────
// UNIQUE KEY evita duplicatas mesmo se a validação PHP falhar
// NOT NULL evita nulos inesperados
// FK previne referências inválidas

// ── Diferença crucial: Sanitize vs Validate ───────────────────────────────────

// SANITIZE: MODIFICA o dado (remove/substitui caracteres)
$dirty   = 'user (at) example.com';
$cleaned = filter_var($dirty, FILTER_SANITIZE_EMAIL); // 'userexample.com' — modificado!
// ⚠️ O resultado de sanitize pode ainda ser inválido!

// VALIDATE: NÃO modifica, verifica se é válido
$isValid = filter_var($cleaned, FILTER_VALIDATE_EMAIL); // false — não é um email válido

// ✅ Regra: sempre sanitize primeiro, depois validate, use apenas o validado

// ── Exemplos de uso correto ───────────────────────────────────────────────────
function validateUserInput(array $post): array
{
    $errors = [];
    $clean  = [];

    // E-mail
    $email = filter_var(strtolower(trim($post['email'] ?? '')), FILTER_VALIDATE_EMAIL);
    if ($email === false) {
        $errors['email'] = 'E-mail inválido.';
    } else {
        $clean['email'] = $email;
    }

    // Inteiro com range
    $age = filter_var($post['age'] ?? '', FILTER_VALIDATE_INT, [
        'options' => ['min_range' => 1, 'max_range' => 120],
    ]);
    if ($age === false) {
        $errors['age'] = 'Idade deve ser entre 1 e 120.';
    } else {
        $clean['age'] = $age;
    }

    // URL (com verificação adicional do protocolo)
    $url = filter_var(trim($post['website'] ?? ''), FILTER_VALIDATE_URL);
    if ($url !== false) {
        $scheme = parse_url($url, PHP_URL_SCHEME);
        if (!in_array($scheme, ['http', 'https'], strict: true)) {
            $url = false;
        }
    }
    if ($url === false && !empty(trim($post['website'] ?? ''))) {
        $errors['website'] = 'URL inválida. Use http:// ou https://';
    } else {
        $clean['website'] = $url ?: null;
    }

    return ['errors' => $errors, 'data' => $clean, 'valid' => empty($errors)];
}
```

### Armadilhas de Filtros

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: FILTER_VALIDATE_INT retorna false OU int (incluindo 0!)
$val = filter_var(0, FILTER_VALIDATE_INT);
if (!$val) {
    echo 'Inválido'; // ❌ Executa! 0 é falsy, mas é um int válido!
}
// ✅ Sempre compare com !== false:
if ($val === false) {
    echo 'Inválido';
}

// ❌ ARMADILHA 2: FILTER_SANITIZE_STRING foi REMOVIDO no PHP 8.1!
$clean = filter_var($input, FILTER_SANITIZE_STRING); // ❌ PHP 8.1+ lança aviso/erro
// ✅ Alternativas:
$clean = htmlspecialchars($input, ENT_QUOTES | ENT_HTML5, 'UTF-8'); // Para output HTML
$clean = strip_tags($input); // Para remover tags completamente

// ❌ ARMADILHA 3: FILTER_VALIDATE_URL aceita javascript: e outros protocolos perigosos
$url = 'javascript:alert(1)';
$valid = filter_var($url, FILTER_VALIDATE_URL); // ❌ Retorna a URL — "válida"!
// ✅ Sempre verifique o protocolo:
if ($valid && in_array(parse_url($valid, PHP_URL_SCHEME), ['http', 'https'], true)) {
    // URL segura
}

// ❌ ARMADILHA 4: Validar e-mail sem normalizar — duplicatas no banco
$email1 = 'Ana@Example.COM';   // "Válido" pelo filter_var
$email2 = 'ana@example.com';   // "Válido" pelo filter_var
// Ambos são o mesmo endereço mas parecem diferentes para o banco!
// ✅ Sempre strtolower() antes de armazenar:
$normalized = strtolower(filter_var($email1, FILTER_VALIDATE_EMAIL));

// ❌ ARMADILHA 5: Confiar apenas em filter_var para CPF/CNPJ/CEP
// filter_var não valida o algoritmo de CPF — apenas o formato
// ✅ Use preg_match para formato + algoritmo de validação:
function isValidCpf(string $cpf): bool
{
    $digits = preg_replace('/\D/', '', $cpf); // Remove não-dígitos
    if (strlen($digits) !== 11 || preg_match('/(\d)\1{10}/', $digits)) {
        return false; // 11 dígitos, sem sequência repetida (111.111.111-11)
    }
    // Algoritmo de validação do dígito verificador...
    return true;
}
```

---

## 16. Arquivos e Sistema de Arquivos

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Quando usar cada função de leitura ───────────────────────────────────────

// file_get_contents(): lê TUDO de uma vez — ideal para arquivos pequenos (<10 MB)
$config = file_get_contents(__DIR__ . '/config.json');
$data   = json_decode($config, associative: true, flags: JSON_THROW_ON_ERROR);

// file(): lê linha por linha em array — ideal para processamento de linhas
$lines = file('/data/names.txt', FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);
foreach ($lines as $line) {
    processName(trim($line));
}

// fopen() + fgets(): streaming — ideal para arquivos grandes
function processLargeFile(string $path, callable $callback): int
{
    $handle = fopen($path, 'r')
        ?: throw new \RuntimeException("Não foi possível abrir: {$path}");

    $processed = 0;

    try {
        while (!feof($handle)) {
            $line = fgets($handle);
            if ($line !== false) {
                $callback(trim($line));
                $processed++;
            }
        }
    } finally {
        fclose($handle); // ✅ Sempre fecha, mesmo com exceção
    }

    return $processed;
}

// Generator com yield: streaming elegante para arquivos gigantes
function readLines(string $path): \Generator
{
    $handle = fopen($path, 'r')
        ?: throw new \RuntimeException("Arquivo não encontrado: {$path}");

    try {
        while (!feof($handle)) {
            $line = fgets($handle);
            if ($line !== false) {
                yield trim($line);
            }
        }
    } finally {
        fclose($handle);
    }
}

// Processa arquivo de 2 GB com memória constante (~1-2 MB)
foreach (readLines('/data/huge-log.txt') as $lineNumber => $line) {
    if (str_contains($line, 'ERROR')) {
        logError($lineNumber, $line);
    }
}
```

### Armadilhas de Arquivos

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Path traversal — usuário acessa arquivos do sistema
$filename = $_GET['file']; // ?file=../../../../etc/passwd
readfile('/uploads/' . $filename); // ❌ Lê arquivos fora do diretório!

// ✅ Sempre use realpath() + verificação de diretório:
$allowedDir = realpath('/var/www/uploads');
$requested  = realpath('/var/www/uploads/' . basename($_GET['file'] ?? ''));

if ($requested === false || !str_starts_with($requested, $allowedDir . DIRECTORY_SEPARATOR)) {
    http_response_code(403);
    exit('Acesso negado.');
}
readfile($requested);

// ❌ ARMADILHA 2: fwrite() sem verificar permissões
$bytes = fwrite($handle, $data);
// $bytes pode ser false (permissão negada) ou int menor que strlen($data) (disco cheio)!
// ✅ Verifique o retorno:
$bytes = fwrite($handle, $data);
if ($bytes === false || $bytes < strlen($data)) {
    throw new \RuntimeException('Falha ao escrever no arquivo. Verifique permissões e espaço em disco.');
}

// ❌ ARMADILHA 3: file_put_contents() sem LOCK_EX em ambiente concorrente
file_put_contents('/data/counter.txt', $newValue); // ❌ Race condition!
// Dois processos simultâneos podem corromper o arquivo

// ✅ Use LOCK_EX para escrita atômica:
file_put_contents('/data/counter.txt', $newValue, LOCK_EX);

// ❌ ARMADILHA 4: Não fechar arquivos — resource leak
$handle = fopen('file.txt', 'r');
// ... código que pode lançar exceção ...
fclose($handle); // ❌ Pode não ser chamado se houver exceção!

// ✅ Use try/finally:
$handle = fopen('file.txt', 'r') ?: throw new \RuntimeException('Não abriu');
try {
    // trabalha com $handle
} finally {
    fclose($handle); // ✅ Sempre executado
}

// ❌ ARMADILHA 5: Usar nomes de arquivo do usuário diretamente
$name = $_FILES['upload']['name']; // 'photo.jpg' — ou '../../../hack.php'!
move_uploaded_file($tmp, '/uploads/' . $name); // ❌ Path traversal + extensão maliciosa

// ✅ Gere um nome seguro:
$ext  = strtolower(pathinfo($name, PATHINFO_EXTENSION));
$safe = date('Ymd_His') . '_' . bin2hex(random_bytes(8)) . '.' . $ext;
move_uploaded_file($tmp, '/uploads/' . $safe);
```

---

## 17. Banco de Dados com PDO

### O Problema N+1 — O Inimigo da Performance

```php
<?php

declare(strict_types=1);

$pdo = Database::getInstance();

// ❌ PROBLEMA N+1 — Uma query para listar + N queries para cada item
$posts = $pdo->query('SELECT id, title, user_id FROM posts WHERE published = 1')->fetchAll();

foreach ($posts as $post) {
    // ❌ Uma query POR POST para buscar o autor — mata a performance!
    $authorStmt = $pdo->prepare('SELECT name FROM users WHERE id = :id');
    $authorStmt->execute(['id' => $post['user_id']]);
    $authorName = $authorStmt->fetchColumn();

    echo "{$post['title']} por {$authorName}";
}
// 100 posts = 1 + 100 = 101 queries!

// ✅ SOLUÇÃO: JOIN — tudo em uma única query
$stmt = $pdo->prepare(
    'SELECT p.id, p.title, p.created_at, u.name AS author_name
     FROM posts p
     INNER JOIN users u ON u.id = p.user_id
     WHERE p.published = 1
     ORDER BY p.created_at DESC
     LIMIT :limit OFFSET :offset'
);
$stmt->bindValue(':limit',  20, \PDO::PARAM_INT);
$stmt->bindValue(':offset', 0,  \PDO::PARAM_INT);
$stmt->execute();

foreach ($stmt->fetchAll() as $post) {
    echo "{$post['title']} por {$post['author_name']}";
}
// 1 query — independente de quantos posts houver!

// ── Casos de uso das funções de fetch ─────────────────────────────────────────

// fetch(): uma linha por vez — streaming de resultados grandes
$stmt = $pdo->query('SELECT id, name FROM users');
while ($row = $stmt->fetch()) {
    processUser($row); // Processa uma linha por vez — baixo uso de memória
}

// fetchAll(): todas de uma vez — para listas pequenas/médias (<10k linhas)
$users = $pdo->query('SELECT id, name, email FROM users LIMIT 100')->fetchAll();

// fetchColumn(): valor escalar único — COUNT, SUM, MAX, etc.
$total = $pdo->query('SELECT COUNT(*) FROM users WHERE active = 1')->fetchColumn();
echo "Total: {$total}";

// FETCH_CLASS: mapeia resultado direto para objeto
final class UserDto
{
    public int $id;
    public string $name;
    public string $email;
}

$stmt  = $pdo->query('SELECT id, name, email FROM users LIMIT 10');
$users = $stmt->fetchAll(\PDO::FETCH_CLASS, UserDto::class);
// Cada linha vira um UserDto com propriedades populadas!
```

### Armadilhas de PDO

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: LIMIT/OFFSET como string — erro em drivers estritos
$page    = 2;
$perPage = 10;
$offset  = ($page - 1) * $perPage;

$stmt = $pdo->prepare('SELECT * FROM users LIMIT :limit OFFSET :offset');
$stmt->execute(['limit' => $perPage, 'offset' => $offset]); // ❌ Trata como string!

// ✅ Use bindValue com PARAM_INT:
$stmt->bindValue(':limit',  $perPage, \PDO::PARAM_INT);
$stmt->bindValue(':offset', $offset,  \PDO::PARAM_INT);
$stmt->execute();

// ❌ ARMADILHA 2: IN() com array — SQL Injection em soluções "espirituosas"
$ids = [1, 2, 3];
$pdo->query("SELECT * FROM users WHERE id IN (" . implode(',', $ids) . ")"); // ❌!
// Se $ids vier do usuário: [1, "2 OR 1=1"] — SQL Injection!

// ✅ Placeholders dinâmicos para IN():
$placeholders = implode(',', array_fill(0, count($ids), '?'));
$stmt = $pdo->prepare("SELECT * FROM users WHERE id IN ({$placeholders})");
$stmt->execute($ids); // PDO escapa cada valor

// ❌ ARMADILHA 3: rowCount() com SELECT não é confiável em todos os drivers
$stmt = $pdo->query('SELECT * FROM users');
echo $stmt->rowCount(); // Pode retornar -1 ou 0 em alguns drivers!
// ✅ Use count() no resultado:
$users = $stmt->fetchAll();
echo count($users);

// ❌ ARMADILHA 4: Mostrar erros de PDO ao usuário
try {
    $stmt = $pdo->prepare($sql);
    $stmt->execute($params);
} catch (\PDOException $e) {
    echo $e->getMessage(); // ❌ Expõe estrutura do banco ao usuário!
}
// ✅ Log interno + mensagem genérica ao usuário:
} catch (\PDOException $e) {
    error_log('DB Error: ' . $e->getMessage());
    http_response_code(500);
    echo json_encode(['error' => 'Erro interno. Tente novamente.']);
}

// ❌ ARMADILHA 5: Credenciais hard-coded no código
$pdo = new \PDO('mysql:host=localhost;dbname=myapp', 'root', 'senha123'); // ❌ Git expõe!
// ✅ Use variáveis de ambiente:
$pdo = new \PDO(
    dsn:      sprintf('mysql:host=%s;dbname=%s;charset=utf8mb4', $_ENV['DB_HOST'], $_ENV['DB_NAME']),
    username: $_ENV['DB_USER'],
    password: $_ENV['DB_PASSWORD'],
);
```

---

## 18. JSON e APIs

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── json_encode: PHP → JSON ──────────────────────────────────────────────────

// Dados básicos
$data = [
    'id'      => 1,
    'name'    => 'Ana Silva',
    'email'   => 'ana@example.com',
    'balance' => 1250.00,
    'active'  => true,
    'tags'    => ['php', 'backend'],
];

// ❌ Sem flags — problema com acentos e URLs
echo json_encode($data);
// {"name":"Ana Silva","email":"ana@example.com","balance":1250}
// URL com \/ é problemático no frontend

// ✅ Com flags corretas para API em português
echo json_encode($data,
    JSON_THROW_ON_ERROR |       // Lança JsonException em erro
    JSON_UNESCAPED_UNICODE |    // Mantém ã, é, ç sem escape
    JSON_UNESCAPED_SLASHES |    // Mantém / sem escape
    JSON_PRETTY_PRINT           // Indentação legível (apenas em dev/debug)
);

// ── json_decode: JSON → PHP ───────────────────────────────────────────────────

$jsonString = '{"id":1,"name":"Ana","role":"admin","active":true}';

// ✅ Como array associativo (preferido — mais seguro e tipável)
$data = json_decode($jsonString, associative: true, flags: JSON_THROW_ON_ERROR);
echo $data['name'];   // 'Ana'
echo $data['role'];   // 'admin'

// Como objeto stdClass (acesso com ->)
$obj = json_decode($jsonString, associative: false, flags: JSON_THROW_ON_ERROR);
echo $obj->name;      // 'Ana'

// ── json_validate (PHP 8.3+) — verifica sem decodificar ──────────────────────
$rawBody = file_get_contents('php://input');

if (!json_validate($rawBody)) {
    http_response_code(400);
    echo json_encode(['error' => 'JSON inválido no corpo da requisição']);
    exit;
}

$payload = json_decode($rawBody, associative: true, flags: JSON_THROW_ON_ERROR);
```

### Armadilhas de JSON

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: json_decode retorna null silenciosamente em PHP 7
$result = json_decode('{"invalido": }'); // null — sem erro!
if ($result === null) {
    // Pode ser null válido ou JSON inválido — ambíguo!
}
// ✅ Use JSON_THROW_ON_ERROR — exceção em qualquer erro:
try {
    $result = json_decode('{"invalido": }', true, 512, JSON_THROW_ON_ERROR);
} catch (\JsonException $e) {
    // JSON definitivamente inválido
}

// ❌ ARMADILHA 2: json_encode falha silenciosamente com UTF-8 inválido
$data = ['text' => "\xB1\x31"]; // String UTF-8 inválida
$json = json_encode($data);      // false — falha silenciosa!
var_dump($json);                 // bool(false)
// ✅ Use JSON_THROW_ON_ERROR:
try {
    $json = json_encode($data, JSON_THROW_ON_ERROR);
} catch (\JsonException $e) {
    echo 'Falha: ' . $e->getMessage(); // 'Malformed UTF-8 characters...'
}

// ❌ ARMADILHA 3: Float precision no JSON
$data = ['price' => 9.99];
echo json_encode($data); // {"price":9.99} — ok neste caso
$data = ['price' => 1.1 + 2.2];
echo json_encode($data); // {"price":3.3000000000000003} — imprecisão!
// ✅ Armazene preços em centavos (int) — sem imprecisão:
$data = ['price_cents' => 330];
echo json_encode($data); // {"price_cents":330} — exato

// ❌ ARMADILHA 4: Exposição de dados sensíveis na resposta JSON
$user = $pdo->fetch();
echo json_encode($user); // ❌ Pode incluir password_hash, tokens, dados internos!
// ✅ Selecione apenas os campos necessários:
echo json_encode([
    'id'    => $user['id'],
    'name'  => $user['name'],
    'email' => $user['email'],
    // Jamais inclua: password_hash, internal_notes, etc.
]);
```

---

## 19. Expressões Regulares

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Quando usar regex vs funções de string ────────────────────────────────────

// Funções de string: SEMPRE prefira quando possível (mais rápido, mais legível)
str_contains($text, 'PHP');          // ✅ vs /PHP/
str_starts_with($text, 'https://');  // ✅ vs /^https:\/\//
str_replace(' ', '-', $text);        // ✅ vs preg_replace('/ /', '-', $text)

// Regex: use quando o padrão é complexo ou variável
// Validação de CPF formato 000.000.000-00
preg_match('/^\d{3}\.\d{3}\.\d{3}-\d{2}$/', $cpf);

// Extração de todos os e-mails de um texto
preg_match_all('/[\w.+-]+@[\w-]+\.[a-z]{2,}/i', $text, $emails);

// Substituição com lógica (callback)
preg_replace_callback('/\{\{(\w+)\}\}/', fn($m) => $data[$m[1]] ?? '', $template);

// ── Padrões comuns e corretos ─────────────────────────────────────────────────

// ✅ E-mail (simplificado — use filter_var para validação real)
$emailPattern = '/^[\w._%+\-]+@[\w.\-]+\.[a-zA-Z]{2,}$/u';

// ✅ CPF: 000.000.000-00
$cpfPattern = '/^\d{3}\.\d{3}\.\d{3}-\d{2}$/';

// ✅ CEP brasileiro: 00000-000
$cepPattern = '/^\d{5}-\d{3}$/';

// ✅ Telefone BR: (11) 98765-4321 ou (11) 3456-7890
$phonePattern = '/^\(\d{2}\)\s\d{4,5}-\d{4}$/';

// ✅ Slug (URL amigável)
$slugPattern = '/^[a-z0-9-]+$/';

// ✅ Data ISO 8601: 2025-04-07
$datePattern = '/^\d{4}-(0[1-9]|1[0-2])-(0[1-9]|[12]\d|3[01])$/';

// ✅ Versão semântica: 1.2.3
$semverPattern = '/^\d+\.\d+\.\d+(-[\w.]+)?(\+[\w.]+)?$/';
```

### Armadilhas de Regex

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: preg_replace retorna null em erro (regex inválida)
$result = preg_replace('/[invalid/', 'x', 'texto'); // Regex inválida!
var_dump($result); // NULL em PHP 8.x — falha silenciosa!
// ✅ Sempre verifique o retorno ou use try/catch:
$result = preg_replace('/[a-z]+/', 'X', 'texto') ?? 'texto'; // Fallback

// ❌ ARMADILHA 2: preg_match_all retorna número de matches, não bool
$count = preg_match_all('/\d+/', 'abc123def456', $matches);
// $count = 2 (int) — não bool!
if ($count) { } // ✅ $count > 0 é truthy — ok neste caso
if ($count === false) { } // Erro na regex — diferente de 0 matches!

// ❌ ARMADILHA 3: . não captura \n por padrão
$html = "<p>\nConteúdo\n</p>";
preg_match('/<p>(.*)<\/p>/', $html, $m); // ❌ Não captura — . não inclui \n!
// ✅ Use flag s (dotall) para incluir \n:
preg_match('/<p>(.*)<\/p>/s', $html, $m); // ✅ Captura todo o conteúdo

// ❌ ARMADILHA 4: Regex sem flag u para UTF-8
$text = 'PHP é incrível!';
preg_match('/^[\w\s]+$/u', $text); // Sem /u: \w não inclui ê, é, ç etc.
// ✅ Use /u para texto em qualquer idioma com caracteres especiais

// ❌ ARMADILHA 5: ReDoS — regex com backtracking catastrófico
// Padrão vulnerável: /^(a+)+$/ com input 'aaaaaaaaaaaaaaab'
// Pode travar o servidor por segundos ou minutos!
// ✅ Evite grupos aninhados com quantificadores:
// /^a+$/ em vez de /^(a+)+$/

// ❌ ARMADILHA 6: Usar regex para parsear HTML/XML — impossível de forma segura
preg_match('/<a href="(.+?)"/', $html, $m); // ❌ Frágil — HTML não é linguagem regular
// ✅ Use DOMDocument ou SimpleXML para parsear HTML/XML:
$dom = new \DOMDocument();
$dom->loadHTML($html);
$links = $dom->getElementsByTagName('a');
foreach ($links as $link) {
    echo $link->getAttribute('href');
}
```

---

## 20. PHP 8.5 — Features Exclusivas

### Pipe Operator |> — Quando e Como Usar

```php
<?php

declare(strict_types=1);

// ── O que o pipe operator resolve ────────────────────────────────────────────

// ❌ Problema: funções aninhadas — lidas de dentro para fora (confuso)
$result = array_sum(
    array_map(
        fn(float $p): float => round($p * 1.1, 2),
        array_filter(
            $prices,
            fn(float $p): bool => $p > 10.0
        )
    )
);
// Para entender: precisa ler do centro para as bordas

// ✅ Solução: pipe operator — lido da esquerda para direita (natural)
$result = $prices
    |> (fn(array $arr): array => array_filter($arr, fn(float $p): bool => $p > 10.0))
    |> (fn(array $arr): array => array_map(fn(float $p): float => round($p * 1.1, 2), $arr))
    |> array_sum(...);

// ── REGRAS CRÍTICAS do pipe operator ─────────────────────────────────────────

// REGRA 1: Funções com 1 argumento — use FCC (First-Class Callable)
$result = '  PHP 8.5  '
    |> trim(...)          // ✅ FCC: trim() recebe 1 argumento
    |> strtolower(...)    // ✅ FCC: strtolower() recebe 1 argumento
    |> strlen(...);       // ✅ FCC: strlen() recebe 1 argumento

// REGRA 2: Funções com múltiplos argumentos — OBRIGATÓRIO usar closure
// ❌ Errado:
// $slug = $text |> str_replace(' ', '-', ...); // TypeError! Pipe passa como 1º arg
// str_replace espera (search, replace, subject) — subject seria o 3º, não o 1º!

// ✅ Correto — closure reordena os argumentos:
$slug = '  PHP 8.5 lançado!  '
    |> trim(...)
    |> mb_strtolower(...)
    |> (fn(string $s): string => str_replace(' ', '-', $s))    // ✅
    |> (fn(string $s): string => preg_replace('/[^a-z0-9-]/', '', $s) ?? $s); // ✅

// REGRA 3: Arrow functions no pipe PRECISAM de parênteses
$data = $input
    |> (fn($x): mixed => transform($x))  // ✅ Parênteses obrigatórios!
    |> finalize(...);

// ❌ Errado:
// $data = $input |> fn($x) => transform($x) |> finalize(...);
// PHP interpreta como: fn($x) => (transform($x) |> finalize(...)) — captura o |> !

// REGRA 4: Funções by-reference NÃO funcionam no pipe
// ❌ sort() modifica o array por referência — não pode ser usado no pipe
// $sorted = $arr |> sort(...); // Error!
// ✅ Use rsort, usort, ou envolva em closure que retorna:
$sorted = $arr |> (fn(array $a): array => (usort($a, fn($x, $y) => $x <=> $y)) ? $a : $a);
// Melhor: chame sort() diretamente e não force no pipe quando não fizer sentido

// ── Casos de uso ideais do pipe operator ─────────────────────────────────────

// 1. Sanitização de input
function sanitizeSearchQuery(string $raw): string
{
    return $raw
        |> trim(...)
        |> mb_strtolower(...)
        |> (fn(string $s): string => preg_replace('/\s+/', ' ', $s) ?? $s)
        |> (fn(string $s): string => strip_tags($s));
}

// 2. Pipeline de dados
function processScores(array $rawScores): array
{
    return $rawScores
        |> (fn(array $s): array => array_filter($s, fn(int $score): bool => $score >= 0))
        |> (fn(array $s): array => array_map(fn(int $score): float => $score / 10, $s))
        |> (fn(array $s): array => array_values($s)); // Re-indexa
}

// 3. Formatação de output
function formatProductName(string $raw): string
{
    return $raw
        |> trim(...)
        |> (fn(string $s): string => preg_replace('/\s+/', ' ', $s) ?? $s)
        |> (fn(string $s): string => mb_convert_case($s, MB_CASE_TITLE, 'UTF-8'));
}
```

### Clone With — Imutabilidade Elegante

```php
<?php

declare(strict_types=1);

// ── O problema: modificar objetos readonly ────────────────────────────────────

// readonly garante imutabilidade após construção — ótimo para value objects
// Mas como criar variações? Antes era necessário um novo construtor para cada caso

// ❌ Solução ingênua: múltiplos factory methods com todos os parâmetros
final class Money
{
    public function __construct(
        public readonly int    $amountCents,
        public readonly string $currency,
        public readonly string $description = '',
    ) {}

    // ❌ Verboso: precisa copiar todos os campos manualmente
    public function withAmountOld(int $newCents): self
    {
        return new self($newCents, $this->currency, $this->description);
    }
}

// ✅ PHP 8.5: Clone With — conciso e explícito
final class MoneyV2
{
    public function __construct(
        public readonly int    $amountCents,
        public readonly string $currency,
        public readonly string $description = '',
    ) {}

    public function add(int $cents): self
    {
        return clone($this, ['amountCents' => $this->amountCents + $cents]);
    }

    public function subtract(int $cents): self
    {
        if ($cents > $this->amountCents) {
            throw new \RuntimeException('Valor a subtrair maior que o total.');
        }
        return clone($this, ['amountCents' => $this->amountCents - $cents]);
    }

    public function convert(string $newCurrency, float $rate): self
    {
        return clone($this, [
            'amountCents' => (int) round($this->amountCents * $rate),
            'currency'    => $newCurrency,
        ]);
    }

    public function withDescription(string $desc): self
    {
        return clone($this, ['description' => $desc]);
    }

    public function format(): string
    {
        return match($this->currency) {
            'BRL' => 'R$ ' . number_format($this->amountCents / 100, 2, ',', '.'),
            'USD' => '$ ' . number_format($this->amountCents / 100, 2),
            default => "{$this->currency} " . number_format($this->amountCents / 100, 2),
        };
    }
}

// Interface fluente imutável — cada operação retorna novo objeto
$price     = new MoneyV2(10000, 'BRL', 'Produto A');  // R$ 100,00
$withTax   = $price->add(1200);     // R$ 112,00
$discounted = $withTax->subtract(500); // R$ 107,00
$inUsd     = $price->convert('USD', 0.19); // $ 19,00

// Originais intactos!
echo $price->format();      // R$ 100,00
echo $withTax->format();    // R$ 112,00
echo $discounted->format(); // R$ 107,00
echo $inUsd->format();      // $ 19,00
```

### #[\NoDiscard] — Prevenindo Erros Silenciosos

```php
<?php

declare(strict_types=1);

// ── O problema: retornos ignorados acidentalmente ─────────────────────────────

// Em PHP, você pode ignorar qualquer valor de retorno silenciosamente
// Isso causa bugs difíceis de detectar

// ❌ Sem NoDiscard: erro silencioso
$stmt = $pdo->prepare('INSERT INTO logs (message) VALUES (?)');
$stmt->execute(['Login realizado']); // ✅ Correto
$pdo->prepare('INSERT INTO users (email) VALUES (?)'); // ❌ Retorno ignorado!
// Nenhum aviso — o insert nunca ocorreu, mas ninguém sabe

// ✅ Com #[\NoDiscard]: PHP avisa quando o retorno é ignorado
final class UserRepository
{
    #[\NoDiscard('O ID do usuário criado deve ser armazenado para uso posterior')]
    public function create(string $name, string $email): int
    {
        $stmt = $this->pdo->prepare('INSERT INTO users (name, email) VALUES (:name, :email)');
        $stmt->execute(['name' => $name, 'email' => $email]);
        return (int) $this->pdo->lastInsertId();
    }

    #[\NoDiscard]
    public function update(int $id, array $data): bool
    {
        // ...
        return $affected > 0; // True se atualizou, false se não encontrou
    }
}

$repo = new UserRepository($pdo);

// ✅ Captura o ID — sem warning
$userId = $repo->create('Ana', 'ana@x.com');
echo "Criado com ID: {$userId}";

// ⚠️ Warning: Return value of create() should not be discarded
$repo->create('Carlos', 'carlos@x.com'); // ❌ Esqueceu de capturar o ID

// Para ignorar INTENCIONALMENTE, use (void):
(void) $repo->create('Maria', 'maria@x.com'); // ✅ Suprime o warning explicitamente
```

### array_first() e array_last() — Acesso Seguro ao PHP 8.5

```php
<?php

declare(strict_types=1);

// ── O problema com reset() e end() ──────────────────────────────────────────

$scores = [85, 92, 78, 95, 88];

// ❌ LEGADO: reset() e end() têm side effects no ponteiro interno
$first = reset($scores); // Move o ponteiro para o início!
$last  = end($scores);   // Move o ponteiro para o final!
// Isso pode interferir com foreach subsequente ou outras operações

// Além disso: em array vazio retornam false (não null), causando bugs:
$empty = [];
var_dump(reset($empty)); // bool(false) — falsy, pode confundir com "não encontrado"
var_dump(end($empty));   // bool(false)

// ✅ PHP 8.5: array_first() e array_last() — sem side effects
$first = array_first($scores); // 85 — sem modificar o ponteiro
$last  = array_last($scores);  // 88 — sem modificar o ponteiro

// Array vazio retorna null — semanticamente correto
var_dump(array_first($empty)); // NULL — explícito e seguro
var_dump(array_last($empty));  // NULL

// ── Uso com verificação de null ────────────────────────────────────────────
function getTopScorer(array $students): ?string
{
    usort($students, fn(array $a, array $b): int => $b['score'] <=> $a['score']);

    $top = array_first($students);
    return $top !== null ? $top['name'] : null;
}

$students = [
    ['name' => 'Ana',    'score' => 95],
    ['name' => 'Carlos', 'score' => 82],
    ['name' => 'Maria',  'score' => 78],
];

$topScorer = getTopScorer($students);
echo $topScorer ?? 'Nenhum aluno cadastrado'; // 'Ana'

$noStudents = getTopScorer([]);
echo $noStudents ?? 'Nenhum aluno cadastrado'; // 'Nenhum aluno cadastrado'
```

---

> **Guia produzido seguindo as instruções do sistema-instructions-php85.md e php-fig-psr.md**
>
> **Versão:** PHP 8.5 | **Estilo:** PER-CS v3.0 | **Última revisão:** Abril 2026
>
> **Fontes:** [php.net](https://www.php.net/) | [php-fig.org](https://www.php-fig.org/) |
> [OWASP Top 10](https://owasp.org/Top10/)

---

# PARTE 3 — GUIA DE CONTEXTO, ARMADILHAS E BOAS PRÁTICAS AVANÇADAS

---

---

## Sumário

1. [Variáveis e Tipos](#1-variáveis-e-tipos)
2. [Strings](#2-strings)
3. [Números e Casting](#3-números-e-casting)
4. [Constantes e Enums](#4-constantes-e-enums)
5. [Operadores](#5-operadores)
6. [Estruturas Condicionais — if e match](#6-estruturas-condicionais--if-e-match)
7. [Loops](#7-loops)
8. [Funções](#8-funções)
9. [Arrays](#9-arrays)
10. [Cookies e Sessões](#10-cookies-e-sessões)
11. [Filtros e Validação](#11-filtros-e-validação)
12. [Orientação a Objetos](#12-orientação-a-objetos)
13. [Exceções e Erros](#13-exceções-e-erros)
14. [Banco de Dados com PDO](#14-banco-de-dados-com-pdo)
15. [AJAX e APIs JSON](#15-ajax-e-apis-json)
16. [Segurança — Guia Consolidado](#16-segurança--guia-consolidado)
17. [PHP 8.5 — Features Exclusivas em Profundidade](#17-php-85--features-exclusivas-em-profundidade)
18. [Performance e Boas Práticas Gerais](#18-performance-e-boas-práticas-gerais)

---

## 1. Variáveis e Tipos

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Quando usar cada tipo ────────────────────────────────────────────────────

// int: IDs, contadores, índices — NUNCA para dinheiro!
$userId    = 42;
$pageCount = 150;
$quantity  = 3;

// float: medidas físicas, coordenadas, percentuais
// ⚠️ NUNCA para valores monetários — use inteiros em centavos!
$latitude  = -23.5505;
$discountRate = 0.15; // 15%

// string: qualquer texto — nomes, CPF, CEP, slugs
$userName  = 'Ana Silva';
$cpf       = '123.456.789-00'; // Armazenado como string — zeros à esquerda importam
$slug      = 'php-8-5-lancado';

// bool: estados binários, flags, resultados de verificação
$isActive      = true;
$hasPermission = false;
$isVerified    = false;

// null: ausência intencional de valor
$lastLoginDate = null; // Usuário nunca logou — diferente de "hoje"
$middleName    = null; // Campo opcional não preenchido

// ── O PROBLEMA DO DINHEIRO ────────────────────────────────────────────────────
// Nunca: $price = 9.99; (float perde precisão em cálculos)
// Correto: armazene em centavos como inteiro
$priceInCents = 999; // R$ 9,99
$taxInCents   = 18;  // R$ 0,18
$totalCents   = $priceInCents + $taxInCents; // 1017 = R$ 10,17

// Exibição: divide por 100 apenas no output
echo 'R$ ' . number_format($totalCents / 100, 2, ',', '.'); // R$ 10,17
```

### Comparações e Alternativas

```php
<?php

declare(strict_types=1);

// ── PHP loosely typed vs strictly typed ──────────────────────────────────────

// SEM strict_types (comportamento legado — imprevisível)
// "5" + 3 → 8 (PHP converte "5" para int silenciosamente)
// 0 == "foo" → true em PHP 7 (!!!), false em PHP 8+ (corrigido)
// [] == false → true

// COM strict_types=1 (comportamento previsível — use sempre)
// "5" + 3 → TypeError em funções com type hint int
// Strings não são comparadas loosely com inteiros

// ── Verificação de tipo: is_* vs gettype() vs instanceof ──────────────────────
$value = 42;

// is_*(): funções de verificação — preferidas
var_dump(is_int($value));    // bool(true)
var_dump(is_string($value)); // bool(false)
var_dump(is_numeric('42'));  // bool(true) — string numérica

// gettype(): retorna string com o nome do tipo — evite em comparações
echo gettype($value); // "integer"

// instanceof: para objetos
// var_dump($obj instanceof MyClass);

// get_debug_type(): mais preciso, PHP 8.0+ — nome completo de classe
class Foo {}
$obj = new Foo();
echo get_debug_type($obj);    // "Foo"
echo get_debug_type(null);    // "null"
echo get_debug_type(42);      // "int"
echo get_debug_type([]);      // "array"
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Comparação com == em vez de ===
// Em PHP 8+, "0" == false ainda é true — use === sempre
$userInput = '0';
if ($userInput == false) {
    echo 'Armadilha! String "0" é igual a false com =='; // Executa!
}
if ($userInput === false) {
    echo 'Não executa — corretamente';
}

// ❌ ARMADILHA 2: Variáveis não inicializadas
function processData(bool $debug = false): void
{
    if ($debug) {
        $output = 'Modo debug';
    }
    // Se $debug for false, $output não existe — Warning em PHP 8+
    // echo $output; // ⚠️ Warning: Undefined variable
}

// ✅ Sempre inicialize variáveis
function processDataFixed(bool $debug = false): void
{
    $output = ''; // Inicializa com valor padrão

    if ($debug) {
        $output = 'Modo debug';
    }

    echo $output;
}

// ❌ ARMADILHA 3: Modificar tipo da mesma variável
$result = 0;
$result = 'erro'; // Muda de int para string — confuso e difícil de debugar
// ✅ Use nomes diferentes ou tipos consistentes

// ❌ ARMADILHA 4: is_numeric() aceita notação científica
var_dump(is_numeric('1e5'));  // bool(true) — mas não é um inteiro normal!
var_dump(is_numeric('0x1A')); // bool(false) no PHP 7+ (era true antes)
// ✅ Para validar ID inteiro, use filter_var com FILTER_VALIDATE_INT
```

### Melhores Práticas

```php
<?php

declare(strict_types=1);

// ✅ 1. Nomes descritivos em camelCase
$userId         = 1;
$orderTotal     = 9999;
$isEmailVerified = true;
$createdAt      = new \DateTimeImmutable();

// ✅ 2. Tipos declarados em funções e properties
final class Order
{
    public function __construct(
        private readonly int   $id,
        private readonly float $total,      // OK aqui — não é cálculo monetário
        private readonly bool  $isPaid = false,
    ) {}
}

// ✅ 3. Null coalescing em vez de isset() + ternário
$name = $_GET['name'] ?? 'Visitante'; // Limpo
// ❌ Evite: $name = isset($_GET['name']) ? $_GET['name'] : 'Visitante';

// ✅ 4. Nullsafe operator para encadeamento com nullable
$city = $user?->getAddress()?->getCity() ?? 'Não informado';

// ✅ 5. Readonly para valores imutáveis
$pi = 3.14159; // ❌ Pode ser reatribuída acidentalmente
// ✅ Use constante ou readonly property na classe
```

---

## 2. Strings

### Casos de Uso Práticos

```php
<?php

declare(strict_types=1);

// ── Quando usar aspas simples vs duplas ──────────────────────────────────────

// Aspas simples: strings estáticas, sem variáveis, SQL, paths, HTML
$sql     = 'SELECT id, name FROM users WHERE active = 1';
$path    = '/var/www/html/uploads/';
$cssClass = 'btn btn-primary active';

// Aspas duplas: quando há variáveis ou sequências de escape
$greeting = "Olá, {$userName}! Bem-vindo ao {$siteName}.";
$logEntry  = "[{$timestamp}] [{$level}] {$message}\n";

// ── Heredoc: blocos de texto multiline com variáveis ─────────────────────────
$html = <<<HTML
    <article>
        <h2>{$post->title}</h2>
        <p class="meta">Por {$post->author} em {$post->date}</p>
        <div class="body">{$post->body}</div>
    </article>
    HTML;

// ── Nowdoc: como heredoc mas SEM interpolação (como aspas simples) ────────────
$template = <<<'TEMPLATE'
    SELECT *
    FROM {table_name}
    WHERE id = :id
    TEMPLATE;

// ── Pipeline de transformação com Pipe Operator (PHP 8.5) ────────────────────
$slug = '  Título: PHP 8.5 Lançado!  '
    |> trim(...)
    |> strtolower(...)
    |> (fn(string $s): string => preg_replace('/[^a-z0-9\s-]/', '', $s))
    |> (fn(string $s): string => preg_replace('/[\s-]+/', '-', $s));
// resultado: "ttulo-php-85-lanado"
```

### Armadilhas Comuns

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: strlen() com UTF-8
$name = 'João'; // 4 caracteres, mas 5 bytes em UTF-8 (ã ocupa 2 bytes)
echo strlen($name);    // 5 — errado para contagem de caracteres!
echo mb_strlen($name); // 4 — correto

// ❌ ARMADILHA 2: substr() com UTF-8
$str = 'Olá!';
echo substr($str, 0, 2);    // Pode quebrar no meio de um caractere multibyte
echo mb_substr($str, 0, 2); // 'Ol' — correto

// ❌ ARMADILHA 3: strtolower() com acentos
echo strtolower('JOÃO');    // 'joÃo' — não funciona com caracteres especiais
echo mb_strtolower('JOÃO'); // 'joão' — correto

// ❌ ARMADILHA 4: Interpolação sem chaves em casos complexos
$items = ['PHP', 'Python'];
echo "Linguagem: $items[0]";   // Funciona, mas é ambíguo
echo "Linguagem: {$items[0]}"; // ✅ Sempre use chaves para clareza

// ❌ ARMADILHA 5: Concatenação em loop (ineficiente)
$result = '';
for ($i = 0; $i < 10000; $i++) {
    $result .= 'item '; // Cria uma nova string a cada iteração — O(n²)
}
// ✅ Use array + implode para concatenações em massa
$parts = [];
for ($i = 0; $i < 10000; $i++) {
    $parts[] = 'item';
}
$result = implode(' ', $parts); // Muito mais eficiente

// ❌ ARMADILHA 6: sprintf() vs concatenação para formatação complexa
// Concatenação longa é difícil de ler:
$msg = 'Usuário ' . $name . ' (#' . $id . ') fez login às ' . $time . '.';

// ✅ sprintf() para templates complexos:
$msg = sprintf('Usuário %s (#%d) fez login às %s.', $name, $id, $time);
```

### Melhores Práticas

```php
<?php

declare(strict_types=1);

// ✅ 1. Sempre use mb_* para texto com caracteres especiais
function truncateText(string $text, int $maxLength, string $suffix = '…'): string
{
    if (mb_strlen($text) <= $maxLength) {
        return $text;
    }

    return mb_substr($text, 0, $maxLength - mb_strlen($suffix)) . $suffix;
}

// ✅ 2. Pipe operator para pipelines de limpeza (PHP 8.5)
function normalizeSlug(string $raw): string
{
    return $raw
        |> trim(...)
        |> mb_strtolower(...)
        |> (fn(string $s): string => preg_replace('/\s+/', '-', $s) ?? $s)
        |> (fn(string $s): string => preg_replace('/[^a-z0-9-]/', '', $s) ?? $s);
}

// ✅ 3. Constantes para delimitadores e separadores
const CSV_SEPARATOR = ';';
const PATH_SEPARATOR_UNIX = '/';

// ✅ 4. Validação antes de manipulação
function parseEmail(string $raw): string
{
    $clean = filter_var(strtolower(trim($raw)), FILTER_SANITIZE_EMAIL);
    $valid = filter_var($clean, FILTER_VALIDATE_EMAIL);

    if ($valid === false) {
        throw new \InvalidArgumentException("E-mail inválido: {$raw}");
    }

    return $valid;
}
```

---

## 3. Números e Casting

### O Problema do Ponto Flutuante

```php
<?php

declare(strict_types=1);

// ❌ O maior erro com float: usar para dinheiro
$price    = 1.10;
$tax      = 0.10;
$total    = $price + $tax;
echo $total; // 1.2000000000000002 — não é 1.20!

// Por quê? Floats são representados em binário, e muitas frações decimais
// não têm representação exata em binário (como 1/3 não tem em decimal).

// ✅ Solução 1: Armazenar em centavos (inteiros)
$priceC = 110; // R$ 1,10
$taxC   = 10;  // R$ 0,10
$totalC = $priceC + $taxC; // 120 = R$ 1,20 (exato!)

// Exibição
echo 'R$ ' . number_format($totalC / 100, 2, ',', '.'); // R$ 1,20

// ✅ Solução 2: bcmath para cálculos científicos/financeiros complexos
$a = '1.10';
$b = '0.10';
echo bcadd($a, $b, 2);   // '1.20' (string — exato!)
echo bcmul('1.10', '3', 2); // '3.30'

// ── PHP_FLOAT_EPSILON — comparação segura de floats ──────────────────────────
function floatsAreEqual(float $a, float $b, float $epsilon = PHP_FLOAT_EPSILON): bool
{
    return abs($a - $b) < $epsilon;
}

var_dump(floatsAreEqual(0.1 + 0.2, 0.3)); // bool(true)
var_dump(0.1 + 0.2 === 0.3);               // bool(false) — nunca compare floats com ===
```

### Armadilhas de Casting

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: (int) trunca, não arredonda
echo (int) 4.9;  // 4 — perdeu 0.9!
echo (int) -4.9; // -4 — trunca em direção ao zero

// ✅ Use round(), ceil() ou floor() antes do cast quando necessário
echo (int) round(4.9);   // 5
echo (int) round(-4.9);  // -5

// ❌ ARMADILHA 2: PHP 8.5 — cast float→int com perda de dados gera warning
$pi = 3.14159;
$intPi = (int) $pi; // ⚠️ Warning se a parte decimal for significativa em PHP 8.5
// ✅ Use intval() com verificação explícita
$intPi = intval($pi); // Mais explícito sobre a intenção de truncar

// ❌ ARMADILHA 3: intval() com base 0 tem comportamento especial
echo intval('010');    // 10 — interpreta como decimal
echo intval('010', 0); // 8  — interpreta como octal (base 0 = auto-detect)!
echo intval('0x1A', 0); // 26 — interpreta como hex
// ✅ Sempre especifique a base explicitamente
echo intval('010', 10); // 10 — decimal

// ❌ ARMADILHA 4: (bool) com strings
var_dump((bool) 'false'); // bool(true) — string não-vazia é true!
var_dump((bool) '0');     // bool(false) — a única string falsy
var_dump((bool) '');      // bool(false)
// ✅ Para strings booleanas, use filter_var
$val = filter_var('false', FILTER_VALIDATE_BOOLEAN); // bool(false)
$val = filter_var('true',  FILTER_VALIDATE_BOOLEAN); // bool(true)
$val = filter_var('yes',   FILTER_VALIDATE_BOOLEAN); // bool(true)
$val = filter_var('no',    FILTER_VALIDATE_BOOLEAN); // bool(false)
```

---

## 4. Constantes e Enums

### Por que Enum supera constantes agrupadas

```php
<?php

declare(strict_types=1);

// ── ANTES (constantes soltas — PHP < 8.1) ────────────────────────────────────

// ❌ Problemas com constantes agrupadas:
class OldStatus
{
    const ACTIVE   = 'active';
    const INACTIVE = 'inactive';
    const PENDING  = 'pending';
}

function processUser(string $status): void
{
    // ❌ PHP não valida se 'qualquer_string' é um status válido
    // ❌ Nenhum type hint garante que $status é um dos três valores
    // ❌ Sem IDE autocompletion específico para os valores
    if ($status === OldStatus::ACTIVE) {
        // ...
    }
}

// Pode ser chamado com qualquer string — sem segurança de tipo:
processUser('deletado');    // ❌ Valor inválido — PHP não reclamará!
processUser(OldStatus::ACTIVE); // ✅

// ── DEPOIS (Enum — PHP 8.1+) ──────────────────────────────────────────────────

// ✅ Vantagens do Enum:
// 1. Type-safe: apenas valores válidos do enum são aceitos
// 2. Exaustividade: match() sem default lança erro se um caso não for tratado
// 3. Métodos: pode ter comportamento associado
// 4. Serialização: backed enums têm valor escalar para banco/API
// 5. from() e tryFrom(): conversão segura de strings/ints externos

enum UserStatus: string
{
    case Active   = 'active';
    case Inactive = 'inactive';
    case Pending  = 'pending';

    public function label(): string
    {
        return match($this) {
            self::Active   => 'Ativo',
            self::Inactive => 'Inativo',
            self::Pending  => 'Pendente de aprovação',
        };
    }

    public function canLogin(): bool
    {
        return $this === self::Active;
    }

    public function cssClass(): string
    {
        return match($this) {
            self::Active   => 'badge-success',
            self::Inactive => 'badge-secondary',
            self::Pending  => 'badge-warning',
        };
    }
}

function processUser(UserStatus $status): void
{
    // ✅ PHP garante que $status é um UserStatus válido — impossível passar lixo
    if ($status->canLogin()) {
        echo "Usuário pode fazer login.";
    }
}

// ❌ processUser('deletado'); → TypeError em tempo de compilação
// ✅ processUser(UserStatus::Active);

// Lendo do banco de dados:
$dbValue = 'active'; // Vem do banco
$status  = UserStatus::tryFrom($dbValue) ?? UserStatus::Pending; // Seguro!

// Listando todos os casos:
foreach (UserStatus::cases() as $case) {
    echo "{$case->value}: {$case->label()}";
}
```

### Armadilhas Comuns com Constantes

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: define() vs const — escopo diferente
function setup(): void
{
    define('APP_NAME', 'Meu App'); // ✅ Funciona dentro de funções
    // const SITE = 'x'; // ❌ Fatal Error — const não pode estar em função
}
setup();
echo APP_NAME; // 'Meu App'

// ❌ ARMADILHA 2: Constantes de classe sem typed class constant podem ter tipo errado
class Config
{
    const TIMEOUT = '30'; // string! Deveria ser int

    // ✅ PHP 8.3+: typed class constants
    const int MAX_RETRIES = 3;
    const string BASE_URL = 'https://api.example.com';
}

// ❌ ARMADILHA 3: Constantes de enum backed não são simples strings
$val = UserStatus::Active; // UserStatus, não 'active'
$val->value; // 'active' — precisa de ->value para o escalar
```

---

## 5. Operadores

### O Operador Spaceship `<=>` — Casos de Uso Reais

```php
<?php

declare(strict_types=1);

// O spaceship operator <=> é a joia oculta do PHP 7+
// Retorna: -1 (menor), 0 (igual), 1 (maior)

// ── Ordenação customizada com usort() ────────────────────────────────────────

$employees = [
    ['name' => 'Carlos', 'dept' => 'TI',  'salary' => 8500.0, 'seniority' => 3],
    ['name' => 'Ana',    'dept' => 'RH',  'salary' => 6200.0, 'seniority' => 7],
    ['name' => 'Maria',  'dept' => 'TI',  'salary' => 9100.0, 'seniority' => 5],
    ['name' => 'Bruno',  'dept' => 'TI',  'salary' => 8500.0, 'seniority' => 1],
];

// ✅ Ordenação multi-critério: dept ASC, salary DESC, seniority DESC
usort($employees, function (array $a, array $b): int {
    return $a['dept']   <=> $b['dept']      // 1º critério: dept
        ?: $b['salary'] <=> $a['salary']    // 2º critério: salary desc (invertido)
        ?: $b['seniority'] <=> $a['seniority']; // 3º critério: seniority desc
});

// ── Comparação de objetos ─────────────────────────────────────────────────────
// O spaceship funciona com qualquer tipo que suporte comparação

$dates = [
    new \DateTimeImmutable('2025-06-15'),
    new \DateTimeImmutable('2025-01-01'),
    new \DateTimeImmutable('2025-12-31'),
];

usort($dates, fn(\DateTimeImmutable $a, \DateTimeImmutable $b): int => $a <=> $b);
// Ordena do mais antigo para o mais recente
```

### Armadilhas com Operadores

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: and/or têm precedência MENOR que = (assignment)
$result = true and false; // $result é TRUE! (= tem precedência sobre and)
// Equivale a: ($result = true) and false;

$result = true && false; // $result é FALSE — correto!
// ✅ Use sempre && e || em vez de and e or em expressões de atribuição

// ❌ ARMADILHA 2: Concatenação com + em vez de .
// $name = "Olá" + " Mundo"; // TypeError — + é aritmético, . é concatenação
$name = "Olá" . " Mundo"; // ✅

// ❌ ARMADILHA 3: Incremento em strings — comportamento legado
$s = 'z';
$s++; // 'aa' — comportamento de incremento de string (deprecated em PHP 8.3)
// ✅ Use intval() ou chr(ord($s) + 1) para manipulação de caracteres

// ❌ ARMADILHA 4: Null coalescing vs Elvis
$value = null;
echo $value ?? 'default';  // 'default' — ?? verifica null (não falsy!)
echo $value ?: 'default';  // 'default' — ?: verifica falsy (0, '', false, null)

$value = 0;
echo $value ?? 'default';  // 0   — ?? só substitui null
echo $value ?: 'default';  // 'default' — 0 é falsy!

// ❌ ARMADILHA 5: Precedência do Pipe Operator (PHP 8.5)
$result = 5 + 3 |> (fn(int $n): int => $n * 2); // (5 + 3) * 2 = 16
// Pipe tem precedência MENOR que aritmética — isso é esperado e correto
// Mas pode surpreender: ternários REQUEREM parênteses no callable
```

---

## 6. Estruturas Condicionais — if e match

### match vs switch — Quando Usar Cada Um

```php
<?php

declare(strict_types=1);

// ── Use match quando: ─────────────────────────────────────────────────────────
// 1. Você precisa do valor retornado
// 2. Comparação estrita (===) é desejada
// 3. Cada caso é uma expressão simples
// 4. Você quer erro se nenhum caso combinar

$httpCode = 404;

// ✅ match para mapeamento de valores
$message = match($httpCode) {
    200, 201, 204 => 'Sucesso',
    301, 302      => 'Redirecionamento',
    400           => 'Requisição inválida',
    401           => 'Não autorizado',
    403           => 'Acesso negado',
    404           => 'Não encontrado',
    500, 503      => 'Erro interno',
    default       => "Código {$httpCode} desconhecido",
};

// ── Use switch quando: ────────────────────────────────────────────────────────
// 1. Múltiplas ações complexas por caso (vários statements)
// 2. Fall-through intencional (raro — muito propenso a bugs)
// 3. Compatibilidade com código legado

// ── Armadilha crítica do match: sem default lança UnhandledMatchError ─────────
$status = 'deletado'; // Valor inesperado

try {
    $label = match($status) {
        'active'   => 'Ativo',
        'inactive' => 'Inativo',
        // Sem default — lança UnhandledMatchError se $status for 'deletado'!
    };
} catch (\UnhandledMatchError $e) {
    // ✅ Capture ou sempre adicione default
    $label = 'Status desconhecido';
}

// ✅ Melhor prática: sempre inclua default ou lance exceção explícita
$label = match($status) {
    'active'   => 'Ativo',
    'inactive' => 'Inativo',
    default    => throw new \InvalidArgumentException("Status inválido: {$status}"),
};

// ── match com condições complexas ────────────────────────────────────────────
$age = 25;
$category = match(true) {
    $age < 13           => 'Criança',
    $age < 18           => 'Adolescente',
    $age < 65           => 'Adulto',
    default             => 'Idoso',
};
```

### Armadilhas de Condicionais

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Yoda conditions desnecessárias
// if (42 === $id) { } — legado defensivo desnecessário com strict_types

// ✅ Com strict_types, a ordem natural é preferível:
if ($id === 42) { }

// ❌ ARMADILHA 2: Negação dupla confusa
if (!empty($users) && !$isAdmin) { }
// ✅ Extraia para variável com nome descritivo
$hasUsers     = !empty($users);
$isRegularUser = !$isAdmin;
if ($hasUsers && $isRegularUser) { }

// ❌ ARMADILHA 3: empty() com comportamento surpreendente
$zero  = 0;
$false = false;
$empty = '';
$null  = null;
$arr   = [];

// Tudo abaixo retorna true com empty():
var_dump(empty($zero));  // true — 0 é "empty"!
var_dump(empty($false)); // true
var_dump(empty($empty)); // true
var_dump(empty($null));  // true
var_dump(empty($arr));   // true

// ✅ Seja específico na verificação:
if ($zero === 0) { }      // Verifica especificamente zero
if ($arr === []) { }      // Verifica array vazio
if ($null === null) { }   // Verifica null
if ($str === '') { }      // Verifica string vazia

// ❌ ARMADILHA 4: Short-circuit não garante execução completa
function hasPermission(): bool
{
    echo 'verificando...';
    return false;
}

$result = false && hasPermission(); // hasPermission() NUNCA é chamada!
// ✅ Útil para performance, mas cuidado com side effects
```

---

## 7. Loops

### Escolhendo o Loop Correto

```php
<?php

declare(strict_types=1);

// ── Guia de escolha ───────────────────────────────────────────────────────────

// foreach: para percorrer arrays e objetos iteráveis — USE NA MAIORIA DOS CASOS
$products = ['Teclado', 'Mouse', 'Monitor'];
foreach ($products as $i => $product) { }

// for: quando você precisa do índice com lógica complexa de iteração
for ($i = 0, $j = count($arr) - 1; $i < $j; $i++, $j--) {
    // Algoritmos que operam de ambas as extremidades
}

// while: quando a condição de parada não é baseada em um contador previsível
while ($line = fgets($fileHandle)) {
    // Lê arquivo linha por linha até EOF
}

// do...while: quando o bloco DEVE executar pelo menos uma vez
do {
    $userInput = readline('Digite um número (0 para sair): ');
} while ($userInput !== '0');

// ── Performance: count() no for ───────────────────────────────────────────────
$bigArray = range(1, 100000);

// ❌ Lento: count() é chamado a cada iteração
for ($i = 0; $i < count($bigArray); $i++) { }

// ✅ Rápido: count() chamado apenas uma vez
for ($i = 0, $len = count($bigArray); $i < $len; $i++) { }

// ✅ Ou ainda melhor — use foreach que não tem esse problema
foreach ($bigArray as $item) { }
```

### Armadilhas Clássicas de Loops

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Modificar array durante foreach sem referência
$prices = [10.0, 20.0, 30.0];

foreach ($prices as $price) {
    $price *= 1.1; // Modifica a cópia local — original NÃO muda!
}

var_dump($prices); // Ainda [10, 20, 30]

// ✅ Para modificar: use referência ou array_map
foreach ($prices as &$price) {
    $price *= 1.1;
}
unset($price); // ✅ OBRIGATÓRIO — remove a referência!

// OU (preferível por ser mais explícito):
$prices = array_map(fn(float $p): float => $p * 1.1, $prices);

// ❌ ARMADILHA 2: Esquecer unset() após foreach por referência
$items = [1, 2, 3, 4, 5];
foreach ($items as &$item) {
    $item *= 2;
}
// SEM unset($item):
$item = 99;          // $items[4] vira 99! (pois $item ainda aponta para último)
var_dump($items);    // [2, 4, 6, 8, 99] — surpresa!

// ❌ ARMADILHA 3: break e continue com loops aninhados
for ($i = 0; $i < 3; $i++) {
    for ($j = 0; $j < 3; $j++) {
        if ($j === 1) {
            break; // Quebra apenas o loop INTERNO ($j), não o externo ($i)
        }
    }
}

// ✅ Para quebrar loops externos, use break N ou return
for ($i = 0; $i < 3; $i++) {
    for ($j = 0; $j < 3; $j++) {
        if ($j === 1) {
            break 2; // Quebra 2 níveis de loop
        }
    }
}

// ❌ ARMADILHA 4: Loop infinito silencioso
$i = 0;
while ($i < 10) {
    echo $i;
    // Esqueceu $i++ — loop infinito!
}
```

---

## 8. Funções

### Funções de Primeira Classe — PHP 8.1+

```php
<?php

declare(strict_types=1);

// FCC — First-Class Callable Syntax: converte qualquer callable em Closure
// ✅ Mais seguro que passar nome como string — erros detectados em análise

// Antes (PHP < 8.1): nomes como strings — sem verificação de typo
$result = array_map('strrev', ['PHP', 'SQL', 'API']); // Pode ter typo silencioso

// Depois (PHP 8.1+): FCC — closure real, verificada
$result = array_map(strrev(...), ['PHP', 'SQL', 'API']); // ✅

// FCC com métodos
$formatter = new \NumberFormatter('pt_BR', \NumberFormatter::CURRENCY);
$format    = $formatter->format(...); // Closure do método de instância

// Casos de uso:
$pipeline = [
    trim(...),
    strtolower(...),
    htmlspecialchars(...),
];

$cleanInput = array_reduce(
    $pipeline,
    fn(string $carry, callable $fn): string => $fn($carry),
    '  <script>alert("XSS")</script>  '
);

// ── Funções com retorno imutável vs mutante ────────────────────────────────────

// ❌ Função mutante (modifica o argumento por referência)
function addPrefix(string &$str, string $prefix): void
{
    $str = $prefix . $str;
}

$name = 'PHP';
addPrefix($name, 'Linguagem: ');
echo $name; // 'Linguagem: PHP' — efeito colateral invisível para o caller

// ✅ Função pura (retorna novo valor, não modifica)
function withPrefix(string $str, string $prefix): string
{
    return $prefix . $str;
}

$name = 'PHP';
$titled = withPrefix($name, 'Linguagem: ');
echo $name;   // 'PHP' — original intacto
echo $titled; // 'Linguagem: PHP'
```

### Armadilhas de Funções

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Valor padrão mutável (array ou objeto)
// Em PHP isso NÃO é um problema como em Python, mas é confuso
function addToList(array $list = []): array
{
    $list[] = 'item'; // ✅ Em PHP, arrays são copiados — não há problema
    return $list;
}

// ❌ ARMADILHA 2: Parâmetro variádico no meio da lista
function invalid(int $a, ...$rest, int $b): void {} // Fatal Error
// ✅ Variádico SEMPRE deve ser o último parâmetro:
function valid(int $a, int $b, int ...$rest): void {}

// ❌ ARMADILHA 3: Closure captura variável por referência por acidente
$multiplier = 2;
$double = fn(int $n): int => $n * $multiplier; // Arrow function captura por VALOR

$multiplier = 10; // Muda o externo
echo $double(5);  // 10 (não 50!) — arrow function capturou o valor original 2

// Mas com closure anônima:
$double2 = function(int $n) use ($multiplier): int {
    return $n * $multiplier; // Capturou $multiplier quando foi definida
};
$multiplier = 100;
echo $double2(5); // 50 — ainda o valor no momento do use()

// Para capturar por referência (raro):
$counter = 0;
$increment = function() use (&$counter): void {
    $counter++; // Modifica o $counter externo
};
$increment();
echo $counter; // 1

// ❌ ARMADILHA 4: Funções dentro de loops criam closures por loop
$funcs = [];
for ($i = 0; $i < 3; $i++) {
    // ⚠️ Arrow function captura $i por valor — correto
    $funcs[] = fn(): int => $i;
}
// Cada closure captura um valor diferente de $i
echo $funcs[0](); // 0
echo $funcs[1](); // 1
echo $funcs[2](); // 2 — correto com arrow functions!

// Mas com closures anônimas e use():
for ($i = 0; $i < 3; $i++) {
    $funcs[] = function() use ($i): int { return $i; }; // ✅ Também correto
    // $funcs[] = function() use (&$i): int { return $i; }; // ❌ Todos retornariam 3!
}
```

---

## 9. Arrays

### Quando Usar Cada Função de Array

```php
<?php

declare(strict_types=1);

// ── array_map vs array_filter vs array_reduce: a trindade funcional ──────────

$orders = [
    ['id' => 1, 'total' => 150.0,  'status' => 'completed'],
    ['id' => 2, 'total' => 89.90,  'status' => 'pending'],
    ['id' => 3, 'total' => 320.0,  'status' => 'completed'],
    ['id' => 4, 'total' => 45.0,   'status' => 'cancelled'],
    ['id' => 5, 'total' => 200.0,  'status' => 'completed'],
];

// array_filter: selecione um subconjunto (mesmo formato, menos elementos)
$completed = array_filter(
    $orders,
    fn(array $o): bool => $o['status'] === 'completed'
);
// Preserva chaves! Use array_values() se precisar de índices sequenciais

// array_map: transforme (mesmo número de elementos, formato diferente)
$totals = array_map(
    fn(array $o): float => $o['total'],
    $orders
);
// [150.0, 89.90, 320.0, 45.0, 200.0]

// array_reduce: agregue em um único valor
$totalRevenue = array_reduce(
    $completed,
    fn(float $sum, array $o): float => $sum + $o['total'],
    0.0
);
// 670.0 (soma dos completed)

// ✅ PHP 8.5: Pipeline com Pipe Operator — legível como linguagem natural
$averageCompletedOrder = $orders
    |> (fn(array $arr): array => array_filter($arr, fn($o) => $o['status'] === 'completed'))
    |> (fn(array $arr): array => array_column($arr, 'total'))
    |> (fn(array $arr): float => array_sum($arr) / max(count($arr), 1));

echo round($averageCompletedOrder, 2); // 223.33

// ── array_column: extrai "coluna" de array 2D ─────────────────────────────────
// Extremamente útil para preparar dados para templates e APIs

$names    = array_column($orders, 'id');     // [1, 2, 3, 4, 5]
$byId     = array_column($orders, null, 'id'); // Array indexado por ID — lookup O(1)!

// Antes era necessário um loop:
$lookup = [];
foreach ($orders as $order) {
    $lookup[$order['id']] = $order;
}
// ✅ array_column faz isso em uma linha
$lookup = array_column($orders, null, 'id');
echo $lookup[3]['total']; // 320.0 — acesso direto por ID
```

### Armadilhas de Arrays

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: array_filter preserva chaves (cria "buracos")
$numbers = [0, 1, 2, 3, 4, 5];
$nonZero = array_filter($numbers); // Remove 0 (falsy)
var_dump(array_keys($nonZero)); // [1, 2, 3, 4, 5] — chave 0 sumiu!

// ✅ Re-indexe se necessário:
$nonZero = array_values(array_filter($numbers));
var_dump(array_keys($nonZero)); // [0, 1, 2, 3, 4]

// ❌ ARMADILHA 2: in_array() sem strict=true
var_dump(in_array('1', [1, 2, 3]));           // true  — comparação frouxa!
var_dump(in_array('1', [1, 2, 3], true));     // false — strict: string !== int
var_dump(in_array(1,   [1, 2, 3], true));     // true  — correto
// ✅ SEMPRE use o terceiro parâmetro true!

// ❌ ARMADILHA 3: array_search retorna false OU a chave (incluindo 0!)
$arr = ['zero', 'um', 'dois'];
$key = array_search('zero', $arr); // Retorna 0 (int) — mas 0 == false!

if ($key) { echo 'encontrou'; } // ❌ Não executa — 0 é falsy!
if ($key !== false) { echo 'encontrou'; } // ✅ Usa !== false, não !$key

// ❌ ARMADILHA 4: Ordenar arrays associativos com sort() perde as chaves
$prices = ['banana' => 1.50, 'maçã' => 2.00, 'laranja' => 0.90];
sort($prices); // ❌ Perde as chaves! Vira [0 => 0.90, 1 => 1.50, 2 => 2.00]
// ✅ Para associativos, use asort() (mantém chaves):
asort($prices); // ['laranja' => 0.90, 'banana' => 1.50, 'maçã' => 2.00]

// ❌ ARMADILHA 5: PHP 8.5 — array_first()/array_last() retornam null em vazio
$empty = [];
var_dump(array_first($empty)); // NULL — não lança erro
// ✅ Verifique antes de usar o valor:
$first = array_first($empty);
if ($first !== null) {
    // Use $first
}
```

---

## 10. Cookies e Sessões

### Sessões — Ciclo de Vida e Segurança

```php
<?php

declare(strict_types=1);

// ── O ciclo completo seguro de autenticação com sessão ───────────────────────

// PASSO 1: Configuração (antes de qualquer output)
ini_set('session.cookie_httponly',  '1'); // Inacessível a JavaScript
ini_set('session.cookie_secure',    '1'); // Apenas HTTPS
ini_set('session.cookie_samesite',  'Strict'); // Previne CSRF via cookie
ini_set('session.use_strict_mode',  '1'); // Rejeita IDs externos
ini_set('session.gc_maxlifetime',   '1800'); // 30 min

// PASSO 2: Início
session_start();

// PASSO 3: Login bem-sucedido
function authenticate(\PDO $pdo, string $email, string $password): ?array
{
    $stmt = $pdo->prepare('SELECT id, name, password_hash, role FROM users WHERE email = :email AND active = 1');
    $stmt->execute(['email' => strtolower(trim($email))]);
    $user = $stmt->fetch();

    if ($user === false || !password_verify($password, $user['password_hash'])) {
        return null; // ✅ Mesma mensagem para email ou senha errada — sem brecha de enumeração
    }

    return $user;
}

// PASSO 4: Armazenar na sessão
function startUserSession(array $user): void
{
    // ✅ session_regenerate_id() SEMPRE após login — previne session fixation
    session_regenerate_id(true);

    // Armazene apenas o mínimo necessário
    $_SESSION['user_id']      = (int)    $user['id'];
    $_SESSION['user_name']    = (string) $user['name'];
    $_SESSION['user_role']    = (string) $user['role'];
    $_SESSION['login_time']   = time();
    $_SESSION['last_activity'] = time();
    // ✅ Não armazene password_hash, email completo, dados sensíveis desnecessários
}

// PASSO 5: Verificação em cada página protegida
function requireAuth(int $timeoutSeconds = 1800): void
{
    if (!isset($_SESSION['user_id'])) {
        header('Location: /login.php');
        exit;
    }

    // Timeout por inatividade
    if (time() - (int) $_SESSION['last_activity'] > $timeoutSeconds) {
        session_unset();
        session_destroy();
        header('Location: /login.php?timeout=1');
        exit;
    }

    $_SESSION['last_activity'] = time();
}

// ── Cookies: casos de uso legítimos ──────────────────────────────────────────

// ✅ Cookie de preferência (não sensível) — pode ter longa duração
setcookie(
    name:     'ui_theme',
    value:    'dark',
    expires:  time() + (86400 * 365), // 1 ano
    path:     '/',
    secure:   true,
    httponly: false, // JavaScript pode ler — para aplicar o tema imediatamente
);

// ✅ Cookie "lembrar-me" (token de segurança, não dados de usuário)
// NUNCA armazene userId ou role direto no cookie — use tokens
$rememberToken = bin2hex(random_bytes(32));
// Armazene o hash do token no banco, o token em si no cookie
$tokenHash = hash('sha256', $rememberToken);
// INSERT INTO remember_tokens (user_id, token_hash, expires_at) VALUES (...)
setcookie(
    name:     'remember_token',
    value:    $rememberToken,
    expires:  time() + (86400 * 30), // 30 dias
    path:     '/',
    secure:   true,
    httponly: true, // Não precisa de JS
);
```

### Armadilhas de Sessão e Cookie

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: session_start() após output
echo 'Olá!';
session_start(); // ❌ Warning: Cannot send session cookie - headers already sent

// ✅ session_start() deve ser chamado antes de qualquer output

// ❌ ARMADILHA 2: Confiar no cookie PHPSESSID do cliente
// session.use_strict_mode = 1 previne que o PHP aceite IDs externos
// Sem isso: um atacante pode forçar um session ID known

// ❌ ARMADILHA 3: Não regenerar o ID após login (session fixation)
// Fluxo sem regeneração:
// 1. Atacante visita /login.php e obtém PHPSESSID=xyz
// 2. Atacante envia link com ?PHPSESSID=xyz para a vítima
// 3. Vítima loga — sessão xyz agora está autenticada
// 4. Atacante usa PHPSESSID=xyz — está autenticado como vítima!
// ✅ SEMPRE: session_regenerate_id(true) no login!

// ❌ ARMADILHA 4: Armazenar dados sensíveis em cookies
setcookie('user_role', 'admin'); // ❌ Qualquer um pode editar o cookie!
// ✅ Armazene na sessão (servidor) — o cookie apenas transporta o ID

// ❌ ARMADILHA 5: Logout incompleto
session_destroy(); // ❌ Dados do servidor removidos, mas cookie PHPSESSID ainda existe!
// ✅ Logout completo:
session_unset();   // 1. Remove dados
session_destroy(); // 2. Destroi no servidor
setcookie(session_name(), '', time() - 3600, '/'); // 3. Remove o cookie
```

---

## 11. Filtros e Validação

### Estratégia de Validação em Camadas

```php
<?php

declare(strict_types=1);

// ── As 4 camadas de validação ────────────────────────────────────────────────

// CAMADA 1: Frontend (HTML5 atributos) — conforto do usuário, NÃO segurança
// <input type="email" required maxlength="150">
// Facilmente bypassado — nunca confie nisso sozinho

// CAMADA 2: Sanitização (PHP) — limpa o dado antes de validar
// Remove caracteres ilegais, normaliza formato
$rawEmail = $_POST['email'] ?? '';
$cleanEmail = strtolower(trim($rawEmail));
// Não valida — apenas limpa

// CAMADA 3: Validação (PHP) — verifica formato e regras de negócio
$validEmail = filter_var($cleanEmail, FILTER_VALIDATE_EMAIL);
if ($validEmail === false) {
    throw new \InvalidArgumentException('E-mail inválido.');
}

// CAMADA 4: Banco de dados (constraints) — última linha de defesa
// UNIQUE KEY no banco previne duplicatas mesmo se a validação PHP falhar
// NOT NULL previne nulos inesperados
// FK previne referências inválidas

// ── Validação vs Sanitização — diferença crucial ──────────────────────────────

// SANITIZE: modifica o dado (remove chars ilegais)
$dirtyEmail = 'user (at) example.com';
$sanitized  = filter_var($dirtyEmail, FILTER_SANITIZE_EMAIL);
echo $sanitized; // 'userexample.com' — dado modificado, pode ainda ser inválido!

// VALIDATE: verifica sem modificar
$valid = filter_var($sanitized, FILTER_VALIDATE_EMAIL);
var_dump($valid); // false — não é um email válido

// ✅ Regra: sanitize primeiro, validate depois, use o valor validado
$email = filter_var(
    strtolower(trim($_POST['email'] ?? '')),
    FILTER_VALIDATE_EMAIL
);

if ($email === false) {
    echo 'E-mail inválido';
} else {
    // $email é garantidamente um e-mail válido e limpo
    storeEmail($email);
}
```

### Armadilhas de Validação

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: FILTER_VALIDATE_INT retorna false OU int (incluindo 0)
$val = filter_var(0, FILTER_VALIDATE_INT); // Retorna 0 (int), não false!
if (!$val) {
    echo 'Inválido'; // ❌ Executa — 0 é falsy!
}
// ✅ SEMPRE compare com !== false
if ($val === false) {
    echo 'Inválido';
} else {
    echo "Válido: {$val}"; // 0 é um inteiro válido
}

// ❌ ARMADILHA 2: Validar e-mail sem normalizar para lowercase
$email1 = 'Ana@Example.COM';
$email2 = 'ana@example.com';
// Ambos são "válidos" pelo filter_var, mas referem-se ao mesmo endereço
// Se não normalizar, pode duplicar no banco!
// ✅ Sempre strtolower() antes de armazenar:
$normalized = strtolower(filter_var($email1, FILTER_VALIDATE_EMAIL));

// ❌ ARMADILHA 3: FILTER_SANITIZE_STRING foi removido no PHP 8.1!
// $clean = filter_var($input, FILTER_SANITIZE_STRING); // ❌ PHP 8.1+
// ✅ Alternativas:
$clean = htmlspecialchars($input, ENT_QUOTES | ENT_HTML5, 'UTF-8'); // Para output HTML
$clean = strip_tags($input); // Para remover tags completamente

// ❌ ARMADILHA 4: Validar URL aceita qualquer protocolo (incluindo javascript:)
$url = 'javascript:alert(1)';
$valid = filter_var($url, FILTER_VALIDATE_URL); // ❌ Retorna a URL — é "válida"!
// ✅ Sempre verifique o protocolo após validar:
if ($valid && in_array(parse_url($valid, PHP_URL_SCHEME), ['http', 'https'], true)) {
    // URL segura
}
```

---

## 12. Orientação a Objetos

### SOLID na Prática com PHP 8.5

```php
<?php

declare(strict_types=1);

// ── S — Single Responsibility Principle ──────────────────────────────────────

// ❌ Classe com múltiplas responsabilidades:
class UserManager
{
    public function validateEmail(string $email): bool { /* ... */ }
    public function saveToDatabase(array $data): void { /* ... */ }
    public function sendWelcomeEmail(string $email): void { /* ... */ }
    public function generatePdfReport(): string { /* ... */ }
}
// Uma classe que valida, persiste, envia email E gera PDF é impossível de testar!

// ✅ Uma responsabilidade por classe:
final class UserValidator { /* apenas validação */ }
final class UserRepository { /* apenas persistência */ }
final class WelcomeEmailSender { /* apenas email */ }
final class UserReportGenerator { /* apenas relatório */ }

// ── D — Dependency Inversion (Injeção de Dependência) ────────────────────────

// ❌ Acoplamento rígido:
final class OrderService
{
    public function create(array $data): void
    {
        $mailer = new SmtpMailer(); // ❌ Instância concreta — impossível mockar em testes
        $mailer->send($data['email'], 'Pedido criado!');
    }
}

// ✅ Depende de abstração (interface), não de implementação:
interface MailerInterface
{
    public function send(string $to, string $subject, string $body): void;
}

final class OrderService
{
    public function __construct(
        private readonly MailerInterface $mailer, // Injeta a dependência
    ) {}

    public function create(array $data): void
    {
        // Em produção: usa SmtpMailer
        // Em testes: usa FakeMailer ou NullMailer
        $this->mailer->send($data['email'], 'Pedido criado!', '...');
    }
}
```

### Armadilhas de OOP

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Herança para reuso de código (herança por conveniência)
class Animal
{
    public function breathe(): void { echo 'Respirando'; }
}

class Car extends Animal
{
    // ❌ Car estende Animal apenas para usar breathe() — sem relação semântica!
    // "Um carro É UM animal?" — Não!
}

// ✅ Use composição ou trait para reuso sem herança:
trait Loggable
{
    public function log(string $message): void
    {
        file_put_contents('/var/log/app.log', $message . PHP_EOL, FILE_APPEND);
    }
}

final class Order
{
    use Loggable; // Composição por trait
}

// ❌ ARMADILHA 2: God Object — classe que sabe de tudo
final class Application
{
    public function getUser(): array { }
    public function saveProduct(): void { }
    public function sendEmail(): void { }
    public function generateReport(): string { }
    public function connectDatabase(): void { }
    // 100 métodos... — viola SRP completamente
}

// ❌ ARMADILHA 3: Mutabilidade desnecessária
class Config
{
    public string $dbHost = 'localhost'; // ❌ Pode ser alterado em qualquer lugar!
    public int    $dbPort = 3306;
}

// ✅ Use readonly para dados imutáveis:
final class Config
{
    public function __construct(
        public readonly string $dbHost = 'localhost',
        public readonly int    $dbPort = 3306,
    ) {}
}

// ❌ ARMADILHA 4: Retornar null de factory methods
final class UserFactory
{
    public static function create(array $data): ?User // ❌ Quem verifica o null?
    {
        if (empty($data['name'])) {
            return null;
        }
        return new User($data);
    }
}

// ✅ Lance exceção — não retorne null de factories:
final class UserFactory
{
    public static function create(array $data): User
    {
        if (empty($data['name'])) {
            throw new \InvalidArgumentException('Nome é obrigatório para criar usuário.');
        }
        return new User($data);
    }
}
```

---

## 13. Exceções e Erros

### Hierarquia e Estratégia de Tratamento

```php
<?php

declare(strict_types=1);

// ── Hierarquia PHP: Throwable → Error | Exception ────────────────────────────

// Error (erros de engine — geralmente fatais):
// ├── TypeError        → tipo errado passado para função com type hint
// ├── ValueError       → valor correto mas fora do range aceito
// ├── ArithmeticError
// │   └── DivisionByZeroError
// ├── ParseError       → erro de sintaxe PHP
// └── AssertionError

// Exception (exceções de aplicação — esperadas e tratáveis):
// ├── RuntimeException → falha em tempo de execução (IO, rede, banco)
// │   ├── OutOfRangeException
// │   └── OverflowException / UnderflowException
// ├── LogicException   → erro de programação (invariantes violadas)
// │   ├── InvalidArgumentException  → argumento com formato/valor inválido
// │   ├── OutOfBoundsException      → índice inválido
// │   └── UnexpectedValueException  → valor inesperado em operação
// └── JsonException    → erro de JSON

// ── Estratégia: Use o tipo mais específico possível ───────────────────────────

function findUser(int $id): array
{
    if ($id <= 0) {
        throw new \InvalidArgumentException("ID deve ser positivo: {$id}");
        // ✅ InvalidArgumentException = problema com o argumento
    }

    $user = $db->findById($id);

    if ($user === null) {
        throw new \RuntimeException("Usuário #{$id} não encontrado.");
        // ✅ RuntimeException = condição que pode acontecer em produção
    }

    return $user;
}

// ── Quando criar exceções customizadas ───────────────────────────────────────

// ✅ Crie exceções de domínio para erros específicos do negócio:
class InsufficientFundsException extends \RuntimeException
{
    public function __construct(
        public readonly float $requested,
        public readonly float $available,
        \Throwable $previous = null,
    ) {
        parent::__construct(
            "Saldo insuficiente. Solicitado: R$ {$requested}, disponível: R$ {$available}.",
            code: 422,
            previous: $previous,
        );
    }
}

// Isso permite catch específico:
try {
    withdrawFunds($account, 500.0);
} catch (InsufficientFundsException $e) {
    // Tratamento específico para saldo insuficiente
    echo "Saldo: R$ {$e->available}, solicitado: R$ {$e->requested}";
} catch (\RuntimeException $e) {
    // Outros erros de runtime
    error_log($e->getMessage());
}
```

### Armadilhas de Tratamento de Erros

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: catch genérico suprimindo erros importantes
try {
    riskyOperation();
} catch (\Throwable $e) {
    // Silencia TUDO — bugs de TypeError, ParseError, tudo passa silenciosamente!
}

// ✅ Catch específico, re-lance o que não sabe tratar:
try {
    riskyOperation();
} catch (DomainException $e) {
    // Trato somente o que sei tratar
    handleDomainError($e);
} catch (\RuntimeException $e) {
    error_log($e->getMessage());
    throw $e; // Re-lança para camada superior
}
// Ou capture \Throwable apenas no controller/middleware de topo

// ❌ ARMADILHA 2: Usar exceções para controle de fluxo normal
function findById(int $id): ?User
{
    throw new NotFoundException("User {$id}"); // ❌ "Não encontrado" é fluxo normal!
}

// ✅ Retorne null para "não encontrado" — exceção para erro inesperado
function findById(int $id): ?User
{
    return $db->find($id) ?: null; // null = não encontrou (ok)
}

// ❌ ARMADILHA 3: Logar E re-lançar sem encadeamento
try {
    doSomething();
} catch (\RuntimeException $e) {
    error_log($e->getMessage()); // Log aqui
    throw new \RuntimeException('Falhou'); // ❌ Perde o contexto original!
}

// ✅ Use exception chaining com previous:
try {
    doSomething();
} catch (\RuntimeException $e) {
    throw new \RuntimeException('Contexto da operação falhou.', previous: $e); // ✅
}

// ❌ ARMADILHA 4: finally com return sobrescreve o return do try/catch
function riskyOp(): string
{
    try {
        return 'sucesso';
    } catch (\Exception $e) {
        return 'erro';
    } finally {
        return 'finally'; // ❌ SEMPRE retorna 'finally', sobrescreve tudo!
    }
}

// ✅ finally apenas para limpeza, nunca para retorno de valor:
function riskyOpFixed(): string
{
    $handle = fopen('file.txt', 'r');
    try {
        return processFile($handle);
    } finally {
        fclose($handle); // ✅ Limpeza — não tem return
    }
}
```

---

## 14. Banco de Dados com PDO

### N+1 Query — O Inimigo da Performance

```php
<?php

declare(strict_types=1);

// ❌ PROBLEMA N+1: Uma query para listar + N queries para cada item
$posts = $pdo->query('SELECT id, title, user_id FROM posts WHERE published = 1')->fetchAll();

foreach ($posts as $post) {
    // ❌ Para cada post, faz UMA query para buscar o autor!
    $author = $pdo->prepare('SELECT name FROM users WHERE id = :id');
    $author->execute(['id' => $post['user_id']]);
    $authorName = $author->fetchColumn();

    echo "{$post['title']} por {$authorName}";
}
// Se há 100 posts: 1 + 100 = 101 queries! Performance terrível.

// ✅ SOLUÇÃO: JOIN em uma única query
$stmt = $pdo->prepare(
    'SELECT p.id, p.title, u.name AS author_name
     FROM posts p
     INNER JOIN users u ON u.id = p.user_id
     WHERE p.published = 1
     ORDER BY p.created_at DESC'
);
$stmt->execute();
$posts = $stmt->fetchAll();
// Uma única query — independente de quantos posts houver!

foreach ($posts as $post) {
    echo "{$post['title']} por {$post['author_name']}";
}

// ── Quando usar lazy loading (N+1 aceitável) ─────────────────────────────────
// Apenas quando você raramente precisa dos dados relacionados.
// Para UMA entidade: OK buscar o autor separado
// Para uma LISTA: sempre use JOIN
```

### Armadilhas de PDO

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: LIMIT/OFFSET sem PARAM_INT causa erros
$page    = 2;
$perPage = 10;
$offset  = ($page - 1) * $perPage;

// ❌ execute() com LIMIT como string causa erro em alguns drivers
$stmt = $pdo->prepare('SELECT * FROM users LIMIT :limit OFFSET :offset');
$stmt->execute(['limit' => $perPage, 'offset' => $offset]); // Pode falhar!

// ✅ Sempre bindValue com PARAM_INT para LIMIT/OFFSET:
$stmt->bindValue(':limit',  $perPage, \PDO::PARAM_INT);
$stmt->bindValue(':offset', $offset,  \PDO::PARAM_INT);
$stmt->execute();

// ❌ ARMADILHA 2: IN() com array — SQL Injection em "soluções" comuns
$ids = [1, 2, 3];
// $pdo->query("SELECT * FROM users WHERE id IN (".implode(',', $ids).")"); // ❌!

// ✅ Placeholders dinâmicos para IN():
$placeholders = implode(',', array_fill(0, count($ids), '?'));
$stmt = $pdo->prepare("SELECT * FROM users WHERE id IN ({$placeholders})");
$stmt->execute($ids);

// ❌ ARMADILHA 3: rowCount() com SELECT não é confiável
$stmt = $pdo->query('SELECT * FROM users');
echo $stmt->rowCount(); // Pode retornar 0 em alguns drivers para SELECT!
// ✅ Use count() no resultado ou SELECT COUNT(*):
echo count($stmt->fetchAll());
// OU
$count = $pdo->query('SELECT COUNT(*) FROM users')->fetchColumn();

// ❌ ARMADILHA 4: Não fechar statements causa memory leaks em loops longos
for ($i = 0; $i < 10000; $i++) {
    $stmt = $pdo->prepare('SELECT * FROM users WHERE id = ?');
    $stmt->execute([$i]);
    $result = $stmt->fetch();
    // $stmt não é fechado — acumula recursos!
}

// ✅ Feche ou reutilize statements:
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = ?'); // Prepara UMA VEZ
for ($i = 0; $i < 10000; $i++) {
    $stmt->execute([$i]); // Executa N vezes
    $result = $stmt->fetch();
    $stmt->closeCursor(); // ✅ Libera recursos do cursor
}
$stmt = null; // ✅ Libera o statement ao final
```

---

## 15. AJAX e APIs JSON

### Design de API RESTful com PHP

```php
<?php

declare(strict_types=1);

// ── Princípios REST para endpoints PHP ───────────────────────────────────────

// GET    /api/users          → listar usuários
// GET    /api/users/42       → buscar usuário 42
// POST   /api/users          → criar usuário
// PUT    /api/users/42       → substituir usuário 42 (todos os campos)
// PATCH  /api/users/42       → atualizar parcialmente usuário 42
// DELETE /api/users/42       → deletar usuário 42

// ── Estrutura de resposta padronizada ────────────────────────────────────────
function apiSuccess(mixed $data, string $message = '', int $code = 200): never
{
    http_response_code($code);
    header('Content-Type: application/json; charset=UTF-8');

    echo json_encode([
        'success' => true,
        'message' => $message,
        'data'    => $data,
    ], JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES);
    exit;
}

function apiError(string $message, int $code = 400, array $errors = []): never
{
    http_response_code($code);
    header('Content-Type: application/json; charset=UTF-8');

    echo json_encode([
        'success' => false,
        'message' => $message,
        'errors'  => $errors,
    ], JSON_THROW_ON_ERROR | JSON_UNESCAPED_UNICODE);
    exit;
}

// ── Roteamento básico sem framework ──────────────────────────────────────────
$method = $_SERVER['REQUEST_METHOD'];
$path   = parse_url($_SERVER['REQUEST_URI'], PHP_URL_PATH);

// Remove prefixo de API
$path   = str_replace('/api', '', $path);
$parts  = explode('/', trim($path, '/'));

// GET /users/42 → $parts = ['users', '42']
$resource = $parts[0] ?? '';
$id       = isset($parts[1]) && is_numeric($parts[1]) ? (int) $parts[1] : null;

match("{$method} {$resource}") {
    'GET users'    => $id ? getUser($id) : listUsers(),
    'POST users'   => createUser(),
    'PUT users'    => $id ? updateUser($id) : apiError('ID obrigatório', 400),
    'DELETE users' => $id ? deleteUser($id) : apiError('ID obrigatório', 400),
    default        => apiError('Endpoint não encontrado', 404),
};
```

### Armadilhas de AJAX e JSON

```php
<?php

declare(strict_types=1);

// ❌ ARMADILHA 1: Exibir erros PHP no output JSON
// Se ini_set('display_errors', '1'), um Warning PHP pode corromper o JSON:
// Warning: ... in file.php on line 42
// {"data": "ok"} ← JSON inválido por causa do Warning antes!

// ✅ Sempre em APIs:
ini_set('display_errors', '0');
error_reporting(E_ALL);
ini_set('log_errors', '1'); // Log em arquivo, não em output

// ❌ ARMADILHA 2: json_encode com caracteres especiais sem flag
$data = ['nome' => 'João', 'url' => 'https://example.com/path'];
echo json_encode($data);
// {"nome":"Jo\u00e3o","url":"https:\/\/example.com\/path"}
// URL com \/ é difícil de usar no frontend

// ✅ Use as flags corretas:
echo json_encode($data, JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES);
// {"nome":"João","url":"https://example.com/path"}

// ❌ ARMADILHA 3: json_decode retorna null silenciosamente em JSON inválido
$result = json_decode('{"invalido": }'); // null — sem erro!
if ($result === null && json_last_error() !== JSON_ERROR_NONE) {
    // Nunca foi verificado...
}

// ✅ Sempre use JSON_THROW_ON_ERROR:
try {
    $result = json_decode('{"invalido": }', associative: true, flags: JSON_THROW_ON_ERROR);
} catch (\JsonException $e) {
    apiError('JSON inválido no corpo da requisição', 400);
}

// ❌ ARMADILHA 4: CORS não configurado — requisições bloqueadas no browser
// (Para APIs públicas ou cross-origin)
// ✅ Configure os headers CORS adequados:
header('Access-Control-Allow-Origin: https://trusted-frontend.com');
header('Access-Control-Allow-Methods: GET, POST, PUT, DELETE, OPTIONS');
header('Access-Control-Allow-Headers: Content-Type, Authorization, X-Requested-With');

if ($_SERVER['REQUEST_METHOD'] === 'OPTIONS') {
    // Preflight request
    http_response_code(204);
    exit;
}

// ❌ ARMADILHA 5: XSS via innerHTML no JavaScript (frontend)
// fetch('/api/users').then(r => r.json()).then(data => {
//   document.getElementById('name').innerHTML = data.name; // ❌ XSS se data.name contiver HTML!
// });

// ✅ Use textContent no JavaScript (nunca innerHTML com dados externos):
// document.getElementById('name').textContent = data.name; // ✅
```

---

## 16. Segurança — Guia Consolidado

### As 10 Vulnerabilidades Mais Críticas (OWASP Top 10 para PHP)

```php
<?php

declare(strict_types=1);

// ── 1. SQL INJECTION ─────────────────────────────────────────────────────────

// ❌ Vulnerável:
$userId = $_GET['id'];
$query  = "SELECT * FROM users WHERE id = {$userId}"; // ?id=1 OR 1=1
// Destruiria o banco com: ?id=1; DROP TABLE users; --

// ✅ Seguro: prepared statement
$stmt = $pdo->prepare('SELECT * FROM users WHERE id = :id');
$stmt->execute(['id' => (int) $_GET['id']]);

// ── 2. XSS (Cross-Site Scripting) ────────────────────────────────────────────

// ❌ Vulnerável:
echo $_POST['comment']; // Exibe <script>alert('XSS')</script> diretamente!

// ✅ Seguro: escape antes de exibir
echo htmlspecialchars($_POST['comment'], ENT_QUOTES | ENT_HTML5, 'UTF-8');

// ── 3. CSRF (Cross-Site Request Forgery) ─────────────────────────────────────

// ❌ Vulnerável: formulário sem token
// <form method="POST" action="/delete-account">
//   <button>Deletar conta</button>
// </form>
// Atacante pode incorporar esse form em outro site e forçar o POST da vítima

// ✅ Seguro: token CSRF em todo POST
$_SESSION['csrf'] ??= bin2hex(random_bytes(32));
// No form: <input type="hidden" name="csrf" value="<?= $_SESSION['csrf'] ?>">
// Na validação:
if (!hash_equals($_SESSION['csrf'], $_POST['csrf'] ?? '')) {
    http_response_code(403);
    exit('CSRF inválido');
}

// ── 4. PATH TRAVERSAL ────────────────────────────────────────────────────────

// ❌ Vulnerável:
$file = $_GET['file']; // ?file=../../etc/passwd
readfile('/uploads/' . $file); // Lê arquivos do sistema!

// ✅ Seguro: realpath + verificação de diretório
$allowedDir = realpath('/uploads');
$realPath   = realpath('/uploads/' . basename($_GET['file']));

if ($realPath === false || !str_starts_with($realPath, $allowedDir . '/')) {
    http_response_code(403);
    exit('Acesso negado');
}
readfile($realPath);

// ── 5. BROKEN AUTHENTICATION ────────────────────────────────────────────────

// ❌ Vulnerável:
$password = md5($_POST['password']); // md5 é quebrado em segundos!
// Sem rate limiting, sem bloqueio por tentativas

// ✅ Seguro:
$hash = password_hash($pass, PASSWORD_ARGON2ID, [
    'memory_cost' => 65536,
    'time_cost' => 4,
    'threads' => 3,
]);

// Rate limiting de login:
$attempts = $_SESSION['login_attempts'] ?? 0;
if ($attempts >= 5) {
    http_response_code(429);
    exit('Muitas tentativas. Aguarde.');
}
```

### Matriz de Segurança — Referência Rápida

```
Ação                    | Risco                | Prevenção
────────────────────────────────────────────────────────────────────────────────
Exibir dado do usuário  | XSS                  | htmlspecialchars() SEMPRE
Query com dado externo  | SQL Injection         | PDO prepared statements SEMPRE
Formulário POST         | CSRF                  | Token + hash_equals()
Upload de arquivo       | RCE, Path Traversal   | Whitelist + finfo + realpath
Armazenar senha         | Credential Stuffing   | password_hash(ARGON2ID)
Verificar senha         | Timing Attack         | password_verify() (timing-safe)
Token CSRF/API          | Brute Force           | random_bytes(32) = 256 bits
Comparar tokens         | Timing Attack         | hash_equals()
Caminho de arquivo      | Path Traversal        | realpath() + str_starts_with()
Sessão após login       | Session Fixation      | session_regenerate_id(true)
Cookie de sessão        | XSS, Hijacking        | httponly=true, secure=true
Input numérico          | Type Juggling         | filter_var + FILTER_VALIDATE_INT
Redirect após POST      | Open Redirect         | Whitelist de URLs destino
```

---

## 17. PHP 8.5 — Features Exclusivas em Profundidade

### Pipe Operator — Quando e Como Usar

```php
<?php

declare(strict_types=1);

// ── Quando o pipe operator AJUDA ─────────────────────────────────────────────

// Caso 1: Pipeline de transformação de dados
// ❌ Antes — leitura de dentro para fora (confuso com muitos passos)
$result = array_sum(
    array_map(
        fn(float $p): float => $p * 1.1,
        array_filter(
            $prices,
            fn(float $p): bool => $p > 10.0
        )
    )
);

// ✅ Com pipe — leitura natural da esquerda para direita
$result = $prices
    |> (fn(array $arr): array => array_filter($arr, fn(float $p): bool => $p > 10.0))
    |> (fn(array $arr): array => array_map(fn(float $p): float => $p * 1.1, $arr))
    |> array_sum(...);

// Caso 2: Sanitização de input
$cleanName = $_POST['name'] ?? ''
    |> trim(...)
    |> (fn(string $s): string => mb_strtolower($s))
    |> (fn(string $s): string => ucwords($s));

// ── Quando o pipe operator NÃO ajuda ─────────────────────────────────────────

// ❌ Para lógica condicional (use if/match):
$value = $input |> (fn($v) => $v > 0 ? doThis($v) : doThat($v)); // Confuso

// ❌ Para funções com efeitos colaterais (dificulta debugging):
$result = $data
    |> saveToDB(...)     // Efeito colateral! Debugging difícil no meio do pipe
    |> sendEmail(...);

// ── Regras críticas do pipe ────────────────────────────────────────────────────

// REGRA 1: Arrow functions DEVEM ter parênteses no pipe
$wrong = $data |> fn($x) => transform($x) |> finalize(...); // ❌ Bug: captura |>
$right = $data |> (fn($x): mixed => transform($x)) |> finalize(...); // ✅

// REGRA 2: Funções multi-argumento precisam de closure
// ❌ Errado — str_replace espera (search, replace, subject) mas pipe passa como 1º
// $slug = $text |> str_replace(' ', '-', ...); // TypeError!
// ✅ Correto — closure reordena os argumentos
$slug = $text |> (fn(string $s): string => str_replace(' ', '-', $s));

// REGRA 3: Funções by-reference não funcionam no pipe
// ❌ $val = $arr |> sort(...); // Erro — sort() usa referência
// ✅ Chame diretamente: sort($arr);
```

### Clone With — Imutabilidade Prática

```php
<?php

declare(strict_types=1);

// O Clone With é a solução para o "problema readonly" — como criar variações
// de objetos imutáveis sem violar readonly ou criar construtores complexos

final class ApiConfig
{
    public function __construct(
        public readonly string $baseUrl,
        public readonly string $apiKey,
        public readonly int    $timeout = 30,
        public readonly int    $retries = 3,
        public readonly array  $headers = [],
    ) {}

    // ✅ Métodos "wither" — criam nova instância com campo alterado
    public function withTimeout(int $seconds): self
    {
        return clone($this, ['timeout' => $seconds]);
    }

    public function withRetries(int $count): self
    {
        return clone($this, ['retries' => $count]);
    }

    public function withHeader(string $name, string $value): self
    {
        return clone($this, ['headers' => [...$this->headers, $name => $value]]);
    }
}

// ✅ Interface fluente para configuração imutável
$config = new ApiConfig(
    baseUrl: 'https://api.example.com',
    apiKey:  $_ENV['API_KEY'],
);

$prodConfig = $config
    ->withTimeout(10)
    ->withRetries(5)
    ->withHeader('X-App-Version', '1.0.0')
    ->withHeader('Accept', 'application/json');

// $config original permanece intacto!
echo $config->timeout;     // 30
echo $prodConfig->timeout; // 10
```

---

## 18. Performance e Boas Práticas Gerais

### Otimizações de Alto Impacto

```php
<?php

declare(strict_types=1);

// ── 1. OpCache — a otimização mais importante ─────────────────────────────────
// Configure no php.ini (impacto: 5-10x de performance)
// opcache.enable=1
// opcache.memory_consumption=256
// opcache.max_accelerated_files=20000
// opcache.validate_timestamps=0  ← em produção (requer reload para mudanças)

// ── 2. Evite include/require em loops ────────────────────────────────────────

// ❌ Inclui o arquivo a cada iteração
foreach ($items as $item) {
    include 'template.php'; // Lê do disco em cada loop!
}

// ✅ Capture o template uma vez
ob_start();
foreach ($items as $item) {
    include 'template.php';
}
$output = ob_get_clean();

// ── 3. Lazy loading — carregue apenas o que precisa ──────────────────────────

// ❌ Busca tudo do banco mesmo que use apenas 3 campos
$users = $pdo->query('SELECT * FROM users')->fetchAll(); // Traz 50 colunas

// ✅ Selecione apenas o necessário
$users = $pdo->query('SELECT id, name, email FROM users')->fetchAll(); // 3 colunas

// ── 4. Cache de queries lentas ────────────────────────────────────────────────

function getCachedStats(\PDO $pdo): array
{
    $cacheKey  = 'dashboard_stats';
    $cacheFile = "/tmp/cache_{$cacheKey}.json";
    $ttl       = 300; // 5 minutos

    // Cache hit?
    if (file_exists($cacheFile) && (time() - filemtime($cacheFile)) < $ttl) {
        return json_decode(file_get_contents($cacheFile), true);
    }

    // Cache miss — busca do banco (operação lenta)
    $stats = [
        'total_users'  => $pdo->query('SELECT COUNT(*) FROM users')->fetchColumn(),
        'total_orders' => $pdo->query('SELECT COUNT(*) FROM orders')->fetchColumn(),
        'revenue'      => $pdo->query('SELECT SUM(total) FROM orders WHERE status = "completed"')->fetchColumn(),
    ];

    // Salva cache
    file_put_contents($cacheFile, json_encode($stats), LOCK_EX);

    return $stats;
}

// ── 5. Autoloader eficiente — PSR-4 ──────────────────────────────────────────

// O autoloader carrega classes sob demanda (lazy) — apenas quando usadas
// Composer implementa PSR-4 com um mapa pré-compilado para máxima performance
// composer dump-autoload --optimize

// Sem Composer — autoloader manual simples:
spl_autoload_register(function (string $class): void {
    $file = __DIR__ . '/src/' . str_replace('\\', '/', $class) . '.php';

    if (file_exists($file)) {
        require $file;
    }
});
```

### Checklist Final de Código PHP 8.5

```
✅ ESTRUTURA
□ declare(strict_types=1) em todo arquivo
□ Namespace correto (PSR-4) espelhando diretório
□ Imports organizados: classes → funções → constantes
□ Sem tag de fechamento ?> em arquivos puramente PHP

✅ TIPAGEM
□ Type hints em todos os parâmetros
□ Return type em todas as funções/métodos
□ Property types em todas as propriedades de classe
□ Nullable (?Type) apenas quando null é semanticamente válido
□ Union types (int|string) em vez de mixed quando possível

✅ CLASSES E OOP
□ final class quando herança não é necessária
□ readonly properties para dados imutáveis após construção
□ Constructor Property Promotion para propriedades simples
□ #[\Override] em métodos que sobrescrevem o pai
□ #[\NoDiscard] em métodos cujo retorno é crítico

✅ SEGURANÇA
□ htmlspecialchars() em TODO output de dados externos
□ PDO prepared statements em TODA query com dados externos
□ password_hash(PASSWORD_ARGON2ID) para senhas
□ random_bytes(32) para tokens (não rand() ou uniqid())
□ hash_equals() para comparação de tokens
□ session_regenerate_id(true) após login
□ Token CSRF em todo formulário POST

✅ PHP 8.5 FEATURES
□ Pipe operator |> para pipelines de transformação
□ array_first()/array_last() no lugar de reset()/end()
□ clone($obj, [...]) para modificar objetos readonly
□ Uri\Rfc3986\Uri no lugar de parse_url()
□ match em vez de switch (quando retorna valor)
□ Enums em vez de constantes agrupadas
□ Named arguments para clareza em funções com muitos parâmetros

✅ PERFORMANCE
□ OpCache habilitado em produção
□ Queries SQL com apenas as colunas necessárias (não SELECT *)
□ LIMIT em todas as queries que podem retornar muitos resultados
□ Índices no banco para colunas usadas em WHERE/ORDER BY/JOIN
□ array_column() para lookups em arrays 2D (O(1) após preparação)
□ Generator/yield para processar conjuntos grandes sem carregar na memória
```

---

> **Este documento é o complemento do Tutorial PHP 8.5 — Guia Completo e Moderno.**
> Use ambos juntos: o tutorial como referência de sintaxe e este como guia de contexto.
>
> **Versão:** PHP 8.5 | **Estilo:** PER-CS v3.0 | **Abril 2026**
