---
data_documento: "2026-02-20"
contexto: "rag"
tecnologia: "php 8.5"
modelo_ia: "claude-opus-4-6"
tags: ["rag", "php8.5", "claude-opus-4-6", "php-syntax"]
---

# Documentação RAG: PHP 8.5 e Claude Opus 4.6

---

# 📘 Manual PHP 8.5 — Fundamentos da Linguagem

> **Referência oficial:** <https://www.php.net/releases/8.5/>
> Este manual utiliza a sintaxe moderna do **PHP 8.5** como padrão.
> Todos os exemplos seguem `declare(strict_types=1)` e tipagem rigorosa.

---

## Sumário

### Parte I — Fundamentos da Linguagem

1. [PHP Syntax](#1-php-syntax)
2. [PHP Comments](#2-php-comments)
3. [PHP Variables](#3-php-variables)
4. [PHP Echo / Print](#4-php-echo--print)
5. [PHP Data Types](#5-php-data-types)
6. [PHP Strings](#6-php-strings)
7. [PHP Numbers](#7-php-numbers)
8. [PHP Casting](#8-php-casting)
9. [PHP Math](#9-php-math)
10. [PHP Constants](#10-php-constants)
11. [PHP Magic Constants](#11-php-magic-constants)
12. [PHP Operators](#12-php-operators)
13. [PHP If...Else...Elseif](#13-php-ifelseelseif)
14. [PHP Switch](#14-php-switch)
15. [PHP Match](#15-php-match)
16. [PHP Loops](#16-php-loops)
17. [PHP Functions](#17-php-functions)
18. [PHP Arrays](#18-php-arrays)
19. [PHP Superglobals](#19-php-superglobals)
20. [PHP RegEx](#20-php-regex)
21. [PHP RegEx Functions](#21-php-regex-functions)

### Parte II — Manipulação de Dados

22. [Datas e Horas](#22-datas-e-horas)
23. [Arquivos e Diretórios](#23-arquivos-e-diretórios)
24. [JSON e Serialização](#24-json-e-serialização)

### Parte III — Orientação a Objetos

25. [Classes e Objetos](#25-classes-e-objetos)
26. [Encapsulamento](#26-encapsulamento)
27. [Herança e Polimorfismo](#27-herança-e-polimorfismo)
28. [Interfaces e Traits](#28-interfaces-e-traits)
29. [OOP Avançado](#29-oop-avançado)

### Parte IV — PHP Moderno: Recursos 8.0 a 8.5

30. [Recursos do PHP 8.0–8.4](#30-recursos-do-php-80–84)
31. [Novidades do PHP 8.5](#31-novidades-do-php-85)
32. [Sistema de Tipos Avançado](#32-sistema-de-tipos-avançado)

### Parte V — Projetos Práticos

33. [Formulários e Validação](#33-formulários-e-validação)
34. [Sessões e Cookies](#34-sessões-e-cookies)
35. [Banco de Dados com PDO](#35-banco-de-dados-com-pdo)
36. [Segurança](#36-segurança)
37. [Projeto Final — Sistema Completo](#37-projeto-final--sistema-completo)

### Parte VI — Tópicos Avançados Complementares

38. [Iterables e Iteradores](#38-iterables-e-iteradores)
39. [Namespaces Avançado](#39-namespaces-avançado)
40. [OOP — Properties e Methods Estáticos](#40-oop--properties-e-methods-estáticos)
41. [OOP — Traits Avançado](#41-oop--traits-avançado)
42. [OOP — Interfaces Avançado](#42-oop--interfaces-avançado)
43. [OOP — Abstract Classes Avançado](#43-oop--abstract-classes-avançado)
44. [OOP — Class Constants](#44-oop--class-constants)
45. [OOP — Access Modifiers Detalhado](#45-oop--access-modifiers-detalhado)
46. [Regular Expressions Completo](#46-regular-expressions-completo)
47. [Validação de Forms — E-mail e URL](#47-validação-de-forms--e-mail-e-url)
48. [cURL — Requisições HTTP](#48-curl--requisições-http)
49. [PDO — PHP Data Objects (Completo)](#49-pdo--php-data-objects-completo)
50. [PHP e JSON — Guia Completo](#50-php-e-json--guia-completo)
51. [Extensão URI Nativa — PHP 8.5](#51-extensão-uri-nativa--php-85)
52. [Novidades do PHP 8.5 — Guia Completo](#52-novidades-do-php-85--guia-completo)
53. [Segurança em PHP 8.5 — Guia de Melhores Práticas](#53-segurança-em-php-85--guia-de-melhores-práticas)
54. [Autenticação 2FA com Gemini 3 Flash — Login Inteligente](#54-autenticação-2fa-com-gemini-3-flash--login-inteligente)
55. [Operador Pipe — Guia Prático Avançado](#55-operador-pipe--guia-prático-avançado)
56. [Validação de Senhas e Autoloading Moderno](#56-validação-de-senhas-e-autoloading-moderno)
57. [Property Hooks — Guia Completo](#57-property-hooks--guia-completo)
58. [Visibilidade Assimétrica — Controle Granular de Acesso](#58-visibilidade-assimétrica--controle-granular-de-acesso)
59. [PHP 8.5 por Nível — Exemplos Práticos](#59-php-85-por-nível--exemplos-práticos)
60. [Visibilidade Assimétrica — Aprofundamento e Herança](#60-visibilidade-assimétrica--aprofundamento-e-herança)
61. [Visibilidade Assimétrica na Herança](#61-visibilidade-assimétrica-na-herança)
62. [Módulo Prático 1 — Fundamentos do PHP 8.5 Moderno](#62-módulo-prático-1--fundamentos-do-php-85-moderno)
63. [Módulo Prático 2 — Orientação a Objetos Moderna](#63-módulo-prático-2--orientação-a-objetos-moderna)
64. [Service Locator Pattern e Union Types](#64-service-locator-pattern-e-union-types)
65. [Superglobais e Segurança de Input](#65-superglobais-e-segurança-de-input)
66. [Expressões Regulares (PCRE) — Guia Completo](#66-expressões-regulares-pcre--guia-completo)
67. [Namespaces e Autoloading PSR-4 Detalhado](#67-namespaces-e-autoloading-psr-4-detalhado)
68. [Orientação a Objetos — Fundamentos no PHP 8.5](#68-orientação-a-objetos--fundamentos-no-php-85)
69. [Clone With e Value Objects — Imutabilidade no PHP 8.5](#69-clone-with-e-value-objects--imutabilidade-no-php-85)
70. [Projeto Prático — Sistema de Logística com PSR-4](#70-projeto-prático--sistema-de-logística-com-psr-4)
71. [Value Objects com Validação — Fail Fast](#71-value-objects-com-validação--fail-fast)
72. [Value Object Dedicado — Classe ZipCode](#72-value-object-dedicado--classe-zipcode)
73. [Persistência de Value Objects com PDO — Repository Pattern](#73-persistência-de-value-objects-com-pdo--repository-pattern)
74. [Sistema de Login Profissional — PHP 8.5](#74-sistema-de-login-profissional--php-85)
75. [Rehash de Senhas com Argon2id](#75-rehash-de-senhas-com-argon2id)
76. [Proteção contra Session Hijacking](#76-proteção-contra-session-hijacking)
77. [Argon2i vs Argon2id — Comparativo Técnico](#77-argon2i-vs-argon2id--comparativo-técnico)
78. [Pipe Operator para Sanitização de Inputs](#78-pipe-operator-para-sanitização-de-inputs)
79. [Value Objects para Dados Brasileiros (CPF, RG, CEP)](#79-value-objects-para-dados-brasileiros-cpf-rg-cep)
80. [Validação de Titularidade de CPF — grapheme_levenshtein](#80-validação-de-titularidade-de-cpf--grapheme_levenshtein)
81. [Criptografia de Dados Sensíveis (LGPD) — Sodium](#81-criptografia-de-dados-sensíveis-lgpd--sodium)
82. [Criptografia com Sodium — CryptoService e Blind Indexing](#82-criptografia-com-sodium--cryptoservice-e-blind-indexing)
83. [Busca de CEP via API — ViaCEP com cURL](#83-busca-de-cep-via-api--viacep-com-curl)
84. [Pipe Operator com PDO — Buscas Dinâmicas](#84-pipe-operator-com-pdo--buscas-dinâmicas)
85. [Validação de NIS e CPF Mascarado](#85-validação-de-nis-e-cpf-mascarado)
86. [NIS (PIS/PASEP) e CPF Mascarado](#86-nis-pispasep-e-cpf-mascarado)
87. [Escalabilidade MySQL — Do Monólito ao Sharding](#87-escalabilidade-mysql--do-monólito-ao-sharding)
88. [Validação de CNPJ e Documentos com Pipe Operator](#88-validação-de-cnpj-e-documentos-com-pipe-operator)
89. [Armazenamento Seguro de NIS (LGPD)](#89-armazenamento-seguro-de-nis-lgpd)
90. [Cliente de API de Titularidade com cURL Persistente](#90-cliente-de-api-de-titularidade-com-curl-persistente)
91. [Criptografia Simétrica vs Blind Indexing](#91-criptografia-simétrica-vs-blind-indexing)
92. [Gerenciamento de .env com PHP Puro](#92-gerenciamento-de-env-com-php-puro)
93. [Ecossistema cURL — Categorias de Funções](#93-ecossistema-curl--categorias-de-funções)
94. [Pipe Operator com cURL — Processamento de Respostas](#94-pipe-operator-com-curl--processamento-de-respostas)
95. [ApiClient — GET e POST com cURL](#95-apiclient--get-e-post-com-curl)
96. [#[\\NoDiscard] para Integrações de Rede](#96-nodiscard-para-integrações-de-rede)
97. [Biblioteca de Segurança do Zero — PHP 8.5 Puro](#97-biblioteca-de-segurança-do-zero--php-85-puro)

---

## 1. PHP Syntax

A sintaxe do PHP é a base de tudo. Todo código PHP **deve** estar dentro das tags `<?php`. O PHP é uma linguagem de script do lado do servidor, o que significa que o código é executado no servidor web antes de enviar o resultado (geralmente HTML) ao navegador do usuário.

No PHP moderno, **sempre** começamos com `declare(strict_types=1)` para garantir tipagem rigorosa. Essa diretiva instrui o PHP a **rejeitar** conversões automáticas de tipo. Por exemplo, sem ela, o PHP aceitaria passar a string `"42"` onde um `int` é esperado; com `strict_types=1`, isso gera um `TypeError`, forçando você a escrever código mais seguro e previsível desde o início.

### Estrutura básica de um arquivo PHP

Todo arquivo PHP começa com a tag de abertura `<?php`. Essa tag indica ao interpretador PHP onde o código executável começa. Tudo que estiver fora das tags PHP é tratado como texto literal (HTML, por exemplo).

```php
<?php
// Estrutura mínima de um arquivo PHP 8.5
declare(strict_types=1);

// Seu código começa aqui
echo 'Olá, PHP 8.5!';
```

### Esqueleto completo (com namespace)

Em projetos reais, todo arquivo de classe segue esta estrutura. O **namespace** (`namespace App\Service`) funciona como um "endereço" para sua classe dentro do projeto — ele evita conflitos de nomes quando duas bibliotecas diferentes possuem classes com o mesmo nome. O padrão **PSR-4** define que a estrutura de diretórios deve espelhar o namespace: a classe `App\Service\ExampleService` ficaria no arquivo `src/Service/ExampleService.php`.

A palavra-chave `final` impede que outras classes herdem desta, o que é uma boa prática para classes que não foram projetadas para extensão. O tipo de retorno `void` indica que o método `execute()` não retorna nenhum valor.

```php
<?php

declare(strict_types=1);

namespace App\Service;

/**
 * Descrição breve da classe.
 */
final class ExampleService
{
    public function execute(): void
    {
        // Implementação
    }
}
```

> **Ordem obrigatória:** Em todo arquivo PHP, a sequência deve ser: (1) `<?php`, (2) `declare(strict_types=1)`, (3) `namespace`, (4) `use` (importações), (5) definição da classe. Alterar essa ordem gera erros de sintaxe.

### Tags PHP — o que usar e o que evitar

| Tag     | Uso                        | Recomendação                           |
| ------- | -------------------------- | -------------------------------------- |
| `<?php` | Abertura padrão            | ✅ **Sempre use**                       |
| `?>`    | Fechamento                 | ❌ **Omita** em arquivos somente PHP    |
| `<?=`   | Short echo (`<?= $var ?>`) | ⚠️ Apenas em templates HTML             |
| `<?`    | Short open tag             | ❌ **Nunca use** — depende de `php.ini` |

> **Por que omitir `?>`?** Qualquer espaço em branco ou linha vazia após `?>` seria enviado como saída HTTP, causando erros como "headers already sent".

### Regras fundamentais

- Todo comando termina com **ponto e vírgula** `;`
- PHP é **case-sensitive** para variáveis: `$nome` ≠ `$Nome`
- Palavras-chave (`if`, `echo`, `class`) **não** são case-sensitive, mas a convenção é minúscula
- Use **4 espaços** de indentação (padrão PSR-12 / PER-CS)
- Em arquivos **somente PHP**, omita a tag de fechamento `?>`
- Primeiro caractere do arquivo deve ser `<?php` — sem espaços antes

```php
<?php
declare(strict_types=1);

// Boas práticas: sem tag de fechamento no final
// Isso evita o erro "headers already sent"

$greeting = 'Bem-vindo ao PHP 8.5!';
echo $greeting;
```

### ⚠️ Exercício

Crie um arquivo `index.php` que exiba seu nome completo na tela.

---

## 2. PHP Comments

Comentários são trechos de texto ignorados pelo interpretador PHP. Servem para **documentar** seu código e torná-lo legível para outros desenvolvedores (e para você no futuro!). Em equipes profissionais, o código é lido muito mais vezes do que é escrito — por isso, comentários bem colocados economizam horas de trabalho.

O PHP oferece três estilos de comentários, cada um com um propósito diferente:

### Tipos de comentários

```php
<?php
declare(strict_types=1);

// Comentário de linha única — use para explicações curtas
// Tudo que vem após as duas barras até o final da linha é ignorado.

// ⚠️ O estilo # também funciona, mas EVITE no PHP moderno:
// No PHP 8.0+, #[...] é a sintaxe de Attributes, então usar # para
// comentários pode gerar confusão visual. Prefira sempre //

/*
 * Comentário de múltiplas linhas (bloco)
 * Use para explicações mais longas que ocupam várias linhas,
 * ou para desabilitar blocos de código temporariamente durante
 * a depuração. Tudo entre /* e */ é ignorado.
 */

/**
 * PHPDoc — comentário de documentação (note os dois asteriscos **).
 * Usado para documentar funções, classes e métodos.
 * IDEs como VS Code e PhpStorm leem essas anotações para
 * autocompletar parâmetros e validar tipos automaticamente.
 *
 * @param string $name Nome do usuário
 * @return string Saudação formatada
 */
function greetUser(string $name): string
{
    return "Olá, {$name}!";
}
```

### Tags PHPDoc mais usadas

| Tag | Uso | Exemplo |
| :--- | :--- | :--- |
| `@param` | Documenta um parâmetro da função | `@param int $id ID do usuário` |
| `@return` | Documenta o tipo de retorno | `@return string Nome formatado` |
| `@throws` | Indica exceções que podem ser lançadas | `@throws \InvalidArgumentException` |
| `@var` | Documenta o tipo de uma propriedade | `@var string $name` |
| `@deprecated` | Marca como obsoleto (não usar mais) | `@deprecated Use newMethod()` |
| `@see` | Referencia outra classe ou método | `@see UserService::find()` |

### Boas práticas

- Use `//` para comentários curtos inline
- Use `/** */` (PHPDoc) para documentar funções e classes
- Escreva comentários que expliquem o **porquê**, não o **quê** — se o código já diz claramente o que faz, o comentário deve explicar a razão da decisão
- Mantenha comentários atualizados com o código — um comentário desatualizado é pior que nenhum comentário, pois induz ao erro
- Nunca comente código "para guardar" — use o controle de versão (Git) para isso

```php
<?php
declare(strict_types=1);

// ❌ Comentário ruim — apenas repete o código
$tax = $price * 0.15; // Multiplica preço por 0.15

// ✅ Comentário bom — explica a razão
$tax = $price * 0.15; // Alíquota de ISS para serviços da categoria

// ❌ Código comentado "para guardar" — use Git para isso
// $oldTax = $price * 0.10; // versão antiga
```

### ⚠️ Exercício

Documente uma função `calculateArea()` usando PHPDoc com `@param` e `@return`.

---

## 3. PHP Variables

Variáveis são espaços nomeados na memória que armazenam valores durante a execução do programa. No PHP, toda variável começa com o símbolo `$` (cifrão), seguido do nome. O PHP é uma linguagem **dinamicamente tipada** — você não precisa declarar o tipo da variável antes de usá-la; o tipo é determinado automaticamente pelo valor atribuído. Porém, com `declare(strict_types=1)`, o PHP passa a ser rigoroso na verificação de tipos em chamadas de função.

### Regras de nomeação

- Começa com `$` seguido de **letra** ou `_` (nunca número: `$1nome` é inválido)
- Pode conter letras, números e `_` (após o primeiro caractere)
- São **case-sensitive**: `$age` ≠ `$Age` ≠ `$AGE` — são três variáveis diferentes
- Use **camelCase** por convenção (padrão PSR-12): `$firstName`, `$totalPrice`
- Escolha nomes **descritivos**: `$userName` é melhor que `$u` ou `$x`

```php
<?php
declare(strict_types=1);

// Declaração e atribuição de variáveis
// O operador = (atribuição) armazena o valor da direita na variável da esquerda
$userName = 'Maria Silva';       // string — texto entre aspas
$userAge = 28;                    // int — número inteiro
$accountBalance = 1_500.75;       // float — o underline é separador visual (PHP 7.4+)
$isActive = true;                 // bool — verdadeiro ou falso

// Exibindo valores com interpolação (aspas duplas obrigatórias)
// {$variavel} dentro de aspas duplas é substituído pelo valor da variável
echo "Nome: {$userName}" . PHP_EOL;           // PHP_EOL = quebra de linha
echo "Idade: {$userAge}" . PHP_EOL;           // do sistema operacional
echo "Saldo: R$ {$accountBalance}" . PHP_EOL; // (\n no Linux, \r\n no Windows)
```

### Variáveis tipadas (em propriedades de classe)

No PHP moderno, podemos declarar o **tipo** de uma variável quando ela é propriedade de uma classe:

```php
<?php
declare(strict_types=1);

final class Product
{
    // ✅ PHP 8.5: propriedades tipadas + readonly
    public function __construct(
        public readonly string $name,
        public readonly float $price,
        public readonly int $stock,
    ) {}
}

$product = new Product('Teclado Mecânico', 299.90, 50);
echo "Produto: {$product->name} — R$ {$product->price}" . PHP_EOL;
```

> **Nota:** Variáveis locais (`$name`, `$price`) não possuem declaração de tipo no PHP — apenas parâmetros de função e propriedades de classe são tipados.

### Variáveis por referência

Por padrão, quando você atribui uma variável a outra (`$b = $a`), o PHP cria uma **cópia** independente do valor. Alterar `$b` não afeta `$a`. Porém, usando o operador `&` (referência), ambas as variáveis passam a apontar para o **mesmo espaço de memória** — qualquer alteração em uma reflete na outra.

```php
<?php
declare(strict_types=1);

// Cópia (comportamento padrão)
$a = 100;
$b = $a;     // $b recebe uma CÓPIA do valor de $a
$b = 999;
echo $a;     // Saída: 100 — $a não foi afetado

// Referência (com &)
$originalValue = 100;
$referenceValue = &$originalValue; // & cria um APELIDO para o mesmo valor

$referenceValue = 200;
echo $originalValue; // Saída: 200 — ambas apontam para o mesmo dado na memória
```

> **Quando usar referências?** Na prática, raramente. O PHP moderno (8.5) favorece a **imutabilidade** (dados que não mudam). Referências são úteis em funções que precisam modificar o valor original, como `sort($array)` que ordena o array no local.

### Escopo de variáveis

O **escopo** define onde uma variável pode ser acessada. No PHP, funções criam um escopo **isolado** — variáveis de fora não são visíveis dentro de funções, e vice-versa. Isso é diferente de linguagens como JavaScript, onde funções herdam o escopo externo.

```php
<?php
declare(strict_types=1);

$globalMessage = 'Sou global'; // Escopo global

function showMessage(): void
{
    // $globalMessage NÃO está acessível aqui (escopo isolado)
    // Tentar usar $globalMessage geraria Warning: Undefined variable
    $localMessage = 'Sou local'; // Escopo local — só existe dentro desta função
    echo $localMessage . PHP_EOL;
}

showMessage();
// $localMessage NÃO está acessível aqui — morreu com a função
```

> **Evite `global`:** Existe a palavra-chave `global $variavel` para importar variáveis globais dentro de funções, mas seu uso é **fortemente desencorajado** no PHP moderno. Em vez disso, passe valores como **parâmetros** da função — isso torna o código mais previsível e testável.

### Verificando a existência de variáveis

Antes de usar uma variável, é boa prática verificar se ela existe e tem valor. O PHP oferece duas funções essenciais para isso:

```php
<?php
declare(strict_types=1);

$name = 'Carlos';
$emptyValue = '';
// $undeclared não foi definida

// isset() — verifica se a variável existe E não é null
var_dump(isset($name));       // true — existe e tem valor
var_dump(isset($undeclared)); // false — não existe

// empty() — verifica se o valor é "vazio" (0, '', null, false, [])
var_dump(empty($emptyValue)); // true — string vazia é considerada empty
var_dump(empty($name));       // false — 'Carlos' não é vazio
```

### Destruindo variáveis

`unset()` remove uma variável da memória. Após chamar `unset()`, a variável deixa de existir — qualquer tentativa de acessá-la gerará um Warning.

```php
<?php
declare(strict_types=1);

$temporaryData = 'Dados temporários';
echo $temporaryData . PHP_EOL;

unset($temporaryData); // Remove a variável da memória
// echo $temporaryData; // ❌ Warning: Undefined variable $temporaryData

// Dica: isset() retorna false após unset()
var_dump(isset($temporaryData)); // false
```

### ⚠️ Exercício

Crie variáveis para armazenar dados de um produto (nome, preço, quantidade em estoque) e exiba-os formatados.

---

## 4. PHP Echo / Print

No PHP, `echo` e `print` são os comandos fundamentais para enviar dados ao navegador do usuário (ou ao terminal, se executado via CLI). Quando o PHP é usado para gerar páginas web, o resultado de `echo` é literalmente o HTML que o navegador recebe e renderiza. Tudo que você "ecoa" se torna parte da resposta HTTP.

Apesar de `echo` e `print` parecerem idênticos, existem diferenças sutis entre eles. Na prática, **use `echo` para tudo** — é a convenção da comunidade PHP e a mais eficiente.

### Diferenças principais

| Característica  | `echo`                   | `print`                   |
| --------------- | ------------------------ | ------------------------- |
| Retorna valor?  | ❌ Não                    | ✅ Sim (sempre `1`)        |
| Múltiplos args? | ✅ Sim (com `,`)          | ❌ Não                     |
| Velocidade      | Ligeiramente mais rápido | Ligeiramente mais lento   |
| Uso comum       | Saída geral              | Quando precisa do retorno |

> **Nota técnica:** Nem `echo` nem `print` são funções — são **construções da linguagem** (*language constructs*). Por isso, os parênteses são opcionais. Diferente de funções, eles não podem ser passados como *callbacks*.

### Aspas simples vs aspas duplas

Esta é uma das distinções mais importantes do PHP. Aspas simples (`'...'`) tratam o conteúdo como texto literal — nenhuma variável é substituída. Aspas duplas (`"..."`) permitem **interpolação**: o PHP substitui `{$variavel}` pelo valor real da variável. Além disso, aspas duplas processam sequências de escape como `\n` (nova linha) e `\t` (tab), enquanto aspas simples só reconhecem `\'` e `\\`.

### Exemplos práticos

```php
<?php
declare(strict_types=1);

// echo — forma mais comum de saída
echo 'Olá, mundo!' . PHP_EOL;
echo 'Linha 1', ' — ', 'Linha 2', PHP_EOL; // Múltiplos argumentos separados por vírgula

// print — retorna 1, pode ser usado em expressões condicionais
$result = print 'Texto exibido' . PHP_EOL;
echo "print retornou: {$result}" . PHP_EOL; // Saída: 1

// Interpolação de variáveis (aspas duplas obrigatórias)
$language = 'PHP 8.5';
echo "Estou aprendendo {$language}!" . PHP_EOL;
// As chaves {} são opcionais para variáveis simples, mas OBRIGATÓRIAS
// para expressões complexas como {$obj->prop} ou {$arr['key']}

// Concatenação com ponto (.)
// O operador . junta duas strings em uma só
echo 'Versão: ' . $language . PHP_EOL;

// Sintaxe com parênteses (funciona, mas não é necessário)
echo('Com parênteses' . PHP_EOL);
print('Também funciona' . PHP_EOL);
```

### HTML com echo

Como o PHP gera páginas web, é muito comum usar `echo` para emitir tags HTML diretamente. Quando o servidor processa o arquivo PHP, o `echo` envia o HTML gerado ao navegador, que o renderiza visualmente:

```php
<?php
declare(strict_types=1);

$pageTitle = 'Minha Página';
$userName = 'Carlos';

// O PHP gera este HTML e envia ao navegador:
// <h1>Minha Página</h1>
// <p>Bem-vindo, Carlos!</p>
echo "<h1>{$pageTitle}</h1>";
echo "<p>Bem-vindo, {$userName}!</p>";
```

> **Dica:** Em templates HTML, prefira o short echo `<?= $var ?>` em vez de `<?php echo $var; ?>`. É mais limpo e legível. O `<?=` é habilitado por padrão desde o PHP 5.4.

### Saída para depuração — `var_dump()` e `print_r()`

Além de `echo`, o PHP oferece funções específicas para **inspecionar** o conteúdo de variáveis durante o desenvolvimento:

```php
<?php
declare(strict_types=1);

$scores = [85, 92, 78, 95];
$userName = 'Ana';
$isAdmin = false;

// var_dump() — mostra tipo + valor (ideal para depuração)
var_dump($scores);
// array(4) { [0]=> int(85) [1]=> int(92) [2]=> int(78) [3]=> int(95) }

var_dump($userName); // string(3) "Ana"
var_dump($isAdmin);  // bool(false)

// print_r() — saída legível de arrays e objetos
print_r($scores);
// Array ( [0] => 85 [1] => 92 [2] => 78 [3] => 95 )
```

| Função       | Mostra tipo? | Uso ideal                                    |
| ------------ | ------------ | -------------------------------------------- |
| `echo`       | ❌            | Saída para o usuário final                   |
| `print_r()`  | ❌            | Visualizar arrays de forma legível           |
| `var_dump()` | ✅            | Depuração detalhada (tipo + tamanho + valor) |

> **Dica:** Use `var_dump()` sempre que precisar entender **o que** uma variável contém e **qual** o seu tipo. É a ferramenta de depuração mais importante do PHP.

### ⚠️ Exercício

Use `echo` para montar uma tabela HTML simples com 3 linhas mostrando nome, idade e cidade.

---

## 5. PHP Data Types

O **sistema de tipos** é o coração de qualquer linguagem de programação. Ele define quais categorias de dados o PHP consegue manipular e como eles se comportam. O PHP 8.5 suporta **tipagem rigorosa** quando você declara `strict_types=1`: isso significa que se uma função espera um `int` e você passa um `float`, o PHP **rejeitará** a chamada com um `TypeError`, em vez de converter silenciosamente.

O PHP possui três categorias de tipos: **escalares** (valores simples e unitários), **compostos** (que contêm múltiplos valores) e **especiais** (para situações específicas).

### Tipos escalares

Os tipos escalares representam um único valor. São os "blocos de construção" básicos de qualquer programa:

```php
<?php
declare(strict_types=1);

// String — texto entre aspas (simples ou duplas)
// É o tipo mais usado para nomes, mensagens, HTML, JSON, etc.
$name = 'Ana Beatriz';

// Integer — número inteiro (sem parte decimal)
// Suporta diversas notações: decimal, hexadecimal, octal e binária
$age = 32;
$hexColor = 0xFF5733;       // Hexadecimal (prefixo 0x) — usado para cores, IDs
$binaryFlag = 0b1010;       // Binário (prefixo 0b) — usado em flags, permissões
$bigNumber = 1_000_000;     // Separador visual _ (PHP 7.4+) — apenas legibilidade

// Float (também chamado double) — número decimal
// Usado para preços, medidas, coordenadas
$price = 29.99;
$scientificValue = 2.5e3;   // Notação científica: 2.5 × 10³ = 2500.0

// Boolean — verdadeiro ou falso
// Fundamental para condicionais (if/else), controle de fluxo
$isLoggedIn = true;
$hasPermission = false;
```

### Tipos compostos

Tipos compostos armazenam **múltiplos valores** ou representam estruturas mais complexas:

```php
<?php
declare(strict_types=1);

// Array — coleção ordenada de valores (o tipo mais versátil do PHP)
// Arrays podem armazenar qualquer tipo e são usados para listas, mapas, filas, etc.
$colors = ['vermelho', 'azul', 'verde'];

// Object — instância de uma classe (um "molde" com dados + comportamento)
// Classes encapsulam dados (propriedades) e ações (métodos) em uma unidade
final class Product
{
    // Constructor Property Promotion (PHP 8.0+)
    // Cria as propriedades e atribui valores automaticamente no construtor
    public function __construct(
        public readonly string $name,   // readonly = não pode ser alterado depois
        public readonly float $price,
    ) {}
}

// Named arguments (PHP 8.0+): name: e price: tornam a chamada explícita
$item = new Product(name: 'Notebook', price: 3_499.90);
echo "Produto: {$item->name} — R$ {$item->price}" . PHP_EOL;
```

> **callable e iterable:** O PHP possui dois tipos compostos especiais: `callable` (qualquer coisa que possa ser chamada como função — closures, nomes de função, métodos) e `iterable` (qualquer coisa que possa ser percorrida com `foreach` — arrays e objetos que implementam `Traversable`).

### Tipos especiais

```php
<?php
declare(strict_types=1);

// NULL — representa a AUSÊNCIA intencional de valor
// Diferente de 0, '', false ou [] — null significa "nada foi atribuído"
$middleName = null;

// Verificação de tipo
var_dump($middleName);          // NULL
var_dump(is_null($middleName)); // bool(true)
var_dump($middleName === null); // bool(true) — forma preferida de verificar
```

> **`void` vs `never`:** O tipo `void` indica que uma função **não retorna valor** (mas encerra normalmente). O tipo `never` (PHP 8.1+) indica que a função **nunca retorna** — ela sempre lança exceção ou chama `exit()`. Use `void` para funções que fazem algo e terminam; use `never` para funções que interrompem a execução.

### Union Types e Intersection Types

A partir do PHP 8.0, você pode declarar que um parâmetro aceita **mais de um tipo**. Isso é especialmente útil para funções que lidam com dados de fontes externas (APIs, formulários) onde o formato pode variar:

```php
<?php
declare(strict_types=1);

// Union type (|) — aceita mais de um tipo
// O parâmetro $id pode ser int OU string, nada mais
function formatId(int|string $id): string
{
    return "ID: {$id}";
}

echo formatId(42) . PHP_EOL;        // "ID: 42"
echo formatId('ABC-123') . PHP_EOL; // "ID: ABC-123"
// formatId(3.14);  // ❌ TypeError: float não é int nem string

// Nullable (?) — atalho para union com null
// ?int é o mesmo que int|null
function findUser(?int $id): ?string
{
    if ($id === null) {
        return null; // Retorno null é permitido pelo ?string
    }
    return "Usuário #{$id}";
}
```

> **Intersection Types (`&`)** obrigam o valor a implementar **todos** os tipos listados simultaneamente: `Countable&Iterator` exige que o objeto implemente ambas as interfaces. São menos comuns, mas poderosos para garantir contratos.

### Never return type (PHP 8.1+)

O tipo `never` é usado em funções que **jamais retornam ao código chamador**. Elas sempre terminam com uma exceção, `exit()` ou um loop infinito. Isso permite que o PHP e as IDEs entendam que qualquer código após a chamada dessa função é **inalcançável**:

```php
<?php
declare(strict_types=1);

// never — função que NUNCA retorna normalmente
function throwError(string $message): never
{
    throw new \RuntimeException($message);
    // Qualquer código aqui é inalcançável e a IDE alertará
}

// Uso prático: após chamar throwError(), o PHP sabe que
// o código seguinte nunca será executado
function processPayment(float $amount): void
{
    if ($amount <= 0) {
        throwError('Valor do pagamento deve ser positivo');
        // Nenhum return necessário aqui — o PHP sabe que throwError() nunca retorna
    }
    // ... processar pagamento
}
```

### Enums (PHP 8.1+)

Enums (enumerações) são tipos que representam um **conjunto fixo de valores possíveis**. Antes dos enums, desenvolvedores usavam constantes ou strings "mágicas" (como `'pendente'`, `'ativo'`), o que gerava erros difíceis de detectar. Com enums, o PHP garante em tempo de compilação que apenas valores válidos sejam usados.

Existem dois tipos: **Pure Enums** (sem valor associado) e **Backed Enums** (com um valor `string` ou `int` por trás, ideal para salvar no banco de dados):

```php
<?php
declare(strict_types=1);

// Backed Enum — cada caso tem um valor string associado
// O `: string` após o nome indica que é um backed enum com valores string
enum OrderStatus: string
{
    case Pending = 'pendente';
    case Processing = 'processando';
    case Delivered = 'entregue';
    case Cancelled = 'cancelado';
}

$status = OrderStatus::Pending;
echo "Status: {$status->value}" . PHP_EOL; // pendente

// Converter de string para enum (útil ao ler do banco de dados)
$fromDb = OrderStatus::from('entregue'); // OrderStatus::Delivered
// OrderStatus::from('invalido'); // ❌ ValueError — valor não existe

// tryFrom() retorna null em vez de lançar exceção
$safe = OrderStatus::tryFrom('invalido'); // null
```

### Tabela resumo de tipos

| Categoria    | Tipos                                     | Exemplo                         |
| ------------ | ----------------------------------------- | ------------------------------- |
| Escalares    | `string`, `int`, `float`, `bool`          | `'texto'`, `42`, `3.14`, `true` |
| Compostos    | `array`, `object`, `callable`, `iterable` | `[1, 2]`, `new Foo()`           |
| Especiais    | `null`, `never`, `void`, `mixed`          | `null`, sem retorno             |
| Union        | `int\|string`, `?int`                     | Aceita múltiplos tipos          |
| Intersection | `Countable&Iterator`                      | Deve implementar ambos          |

### ⚠️ Exercício

Crie um enum `PaymentMethod` com os casos: Pix, CreditCard, BankSlip. Cada um com um valor string descritivo.

---

## 6. PHP Strings

Strings são sequências de caracteres — o tipo de dado mais usado na programação web. No PHP, praticamente tudo começa e termina como string: o HTML enviado ao navegador, os dados de formulários recebidos, as consultas SQL, os JSONs de APIs, os caminhos de arquivo. Dominar strings é essencial.

O PHP oferece **quatro formas** de definir strings, cada uma com comportamento diferente:

### Tipos de strings

```php
<?php
declare(strict_types=1);

$name = 'Carlos';

// 1. Aspas simples ('...') — LITERAL, sem interpolação
// É a forma mais rápida: o PHP não precisa analisar o conteúdo
$simpleString = 'Olá, $name';         // Saída literal: Olá, $name
// Sequências de escape: apenas \' (apóstrofo) e \\ (barra invertida)

// 2. Aspas duplas ("...") — com INTERPOLAÇÃO
// O PHP analisa o conteúdo, substituindo variáveis e escape sequences
$doubleString = "Olá, {$name}";       // Saída: Olá, Carlos
// Sequências de escape: \n (nova linha), \t (tab), \r, \\ e mais

// 3. Heredoc (<<<IDENTIFICADOR) — como aspas duplas, para textos longos
// Perfeito para HTML, SQL, JSON que ocupam múltiplas linhas
$heredocString = <<<HTML
    <div class="card">
        <h2>{$name}</h2>
    </div>
HTML;

// 4. Nowdoc (<<<'IDENTIFICADOR') — como aspas simples, para blocos literais
// Note as aspas simples ao redor do identificador
$nowdocString = <<<'TEXT'
    Isso é texto literal: $name não será interpretado.
    Útil para regex complexos ou templates que não precisam de variáveis.
TEXT;
```

> **Quando usar qual?** Prefira aspas simples (`'...'`) quando não precisa de interpolação — é mais rápido e deixa claro que não há variáveis. Use aspas duplas (`"..."`) quando precisa incluir variáveis. Use Heredoc/Nowdoc para blocos de texto grandes como HTML ou SQL.

### Funções de string essenciais

O PHP possui mais de 100 funções para manipular strings. Abaixo estão as que você usará **todos os dias**. Uma distinção fundamental: funções que começam com `mb_` (multibyte) lidam corretamente com caracteres acentuados e especiais (UTF-8), enquanto as funções padrão tratam cada byte como um caractere — o que causa problemas com `é`, `ã`, `ç`, emojis, etc.

```php
<?php
declare(strict_types=1);

$text = '  PHP 8.5 é fantástico!  ';

// --- Tamanho ---
echo strlen($text) . PHP_EOL;    // 29 (conta BYTES — 'é' e 'á' ocupam 2 bytes cada)
echo mb_strlen($text) . PHP_EOL; // 27 (conta CARACTERES — o correto para UTF-8)
// ⚠️ Sempre use mb_strlen() para texto em português!

// --- Remover espaços ---
echo trim($text) . PHP_EOL;      // 'PHP 8.5 é fantástico!' (remove espaços das bordas)
echo ltrim($text) . PHP_EOL;     // Remove apenas da esquerda (left)
echo rtrim($text) . PHP_EOL;     // Remove apenas da direita (right)

// --- Maiúsculas e minúsculas ---
echo strtoupper('hello') . PHP_EOL;      // HELLO
echo strtolower('WORLD') . PHP_EOL;      // world
echo mb_strtoupper('café') . PHP_EOL;    // CAFÉ (mb_ respeita acentos)
// strtoupper('café') poderia falhar dependendo do locale do sistema

// --- Busca (PHP 8.0+) ---
// Antes do PHP 8.0, era necessário usar strpos() !== false (confuso e propenso a bugs)
echo str_contains('PHP 8.5', '8.5') ? 'Sim' : 'Não';      // Sim
echo PHP_EOL;
echo str_starts_with('PHP 8.5', 'PHP') ? 'Sim' : 'Não';   // Sim
echo PHP_EOL;
echo str_ends_with('foto.jpg', '.jpg') ? 'Sim' : 'Não';   // Sim
echo PHP_EOL;

// --- Substituição ---
echo str_replace('8.5', '9.0', 'PHP 8.5') . PHP_EOL; // PHP 9.0

// --- Substring (extrair pedaço) ---
echo substr('Fundamentos', 0, 5) . PHP_EOL; // Funda (do índice 0, pegue 5 caracteres)

// --- Dividir e juntar ---
// explode() = divide string em array usando um separador
$parts = explode(',', 'a,b,c,d');           // ['a', 'b', 'c', 'd']
// implode() = junta array em string usando um separador (operação inversa)
echo implode(' | ', $parts) . PHP_EOL;      // a | b | c | d
```

### Pipe Operator com strings (PHP 8.5)

O **Pipe Operator** (`|>`) é uma das adições mais elegantes do PHP 8.5. Ele permite encadear transformações de dados da esquerda para a direita, como uma "esteira de produção". O resultado de cada etapa é automaticamente passado como primeiro argumento da próxima função. Compare as duas abordagens:

```php
<?php
declare(strict_types=1);

// ❌ LEGADO - PHP < 8.5 — chamadas aninhadas (leia de DENTRO para FORA)
// A ordem de leitura é inversa à ordem de execução:
// $result = strtoupper(trim("  olá mundo  "));
// 1° executa trim(), 2° executa strtoupper() — mas você lê ao contrário

// ✅ MODERNO - PHP 8.5 — pipe operator |> (leia de CIMA para BAIXO)
// A ordem de leitura = ordem de execução:
$result = "  olá mundo  "   // 1° define o valor inicial
    |> trim(...)            // 2° remove espaços → "olá mundo"
    |> strtoupper(...);     // 3° converte para maiúsculo → "OLÁ MUNDO"

echo $result . PHP_EOL; // OLÁ MUNDO

// Os (...) são a sintaxe First-Class Callable (PHP 8.1+):
// trim(...) é equivalente a Closure::fromCallable('trim')
// Isso transforma a função em um valor passável
```

### ⚠️ Exercício

Crie uma função que receba um nome completo e retorne as iniciais em maiúsculo (ex: "ana maria" → "A.M.").

---

## 7. PHP Numbers

O PHP trabalha com dois tipos numéricos principais: **inteiros** (`int`) e **números de ponto flutuante** (`float`). Entender as diferenças entre eles é crucial, especialmente ao lidar com valores financeiros — onde a escolha errada pode causar centavos perdidos em milhares de transações.

### Inteiros (int)

Inteiros são números sem parte decimal. O PHP aceita inteiros em quatro notações diferentes, todas representando o mesmo conceito mas em bases numéricas distintas:

```php
<?php
declare(strict_types=1);

// Todas representam o número 255, apenas em bases diferentes:
$decimal = 255;               // Base 10 (padrão, o que usamos no dia a dia)
$octal = 0377;                // Base 8 (prefixo 0) — usado em permissões Unix
$hexadecimal = 0xFF;          // Base 16 (prefixo 0x) — usado em cores, endereços
$binary = 0b11111111;         // Base 2 (prefixo 0b) — usado em flags e bitmasks
$formatted = 1_000_000;       // Separador visual _ (PHP 7.4+) — não altera o valor

// Limites do sistema (dependem se é 32 ou 64 bits)
echo PHP_INT_MAX . PHP_EOL;   // 9223372036854775807 (em 64 bits)
echo PHP_INT_MIN . PHP_EOL;   // -9223372036854775808
echo PHP_INT_SIZE . PHP_EOL;  // 8 (bytes) = 64 bits
// Se ultrapassar PHP_INT_MAX, o PHP converte automaticamente para float!
```

### Ponto flutuante (float)

Floats representam números decimais, mas internamente são armazenados em formato binário (IEEE 754). Isso causa um problema famoso: **nem todo número decimal pode ser representado com exatidão**. O número `0.1` em binário é uma dízima periódica infinita — assim como `1/3` (0.333...) em decimal.

```php
<?php
declare(strict_types=1);

$price = 19.99;
$scientific = 2.5e3;      // Notação científica: 2.5 × 10³ = 2500.0
$negative = -1.5E-2;      // -0.015

echo PHP_FLOAT_MAX . PHP_EOL; // Maior float suportado (~1.8e308)
echo PHP_FLOAT_MIN . PHP_EOL; // Menor float positivo (~2.2e-308)

// ⚠️ A ARMADILHA CLÁSSICA: comparação de floats
$a = 0.1 + 0.2;  // NÃO é exatamente 0.3!
$b = 0.3;
echo var_export($a, true) . PHP_EOL; // 0.30000000000000004 (surpresa!)

// ❌ NUNCA compare floats diretamente — pode falhar!
// if ($a === $b) — retorna false mesmo que sejam "iguais"!

// ✅ Use comparação com tolerância (epsilon)
$epsilon = 0.00001;
if (abs($a - $b) < $epsilon) {
    echo 'São iguais (dentro da tolerância)' . PHP_EOL;
}
```

> **⚠️ CRÍTICO — Floats e dinheiro:** **NUNCA** use `float` para valores monetários. O arredondamento binário pode causar diferenças de centavos que se acumulam. Para dinheiro, use **inteiros representando centavos** (R$ 19,99 = `1999`) ou a extensão `bcmath` para aritmética de precisão arbitrária: `bcadd('0.1', '0.2', 2)` retorna `'0.30'` exato.

### Verificação de tipo numérico

Quando você recebe dados de formulários HTML, tudo chega como **string**. Antes de usar esses valores em cálculos, você precisa verificar se realmente contêm números. O PHP oferece várias funções para isso:

```php
<?php
declare(strict_types=1);

$values = [42, 3.14, '100', '12abc', NAN, INF];

foreach ($values as $value) {
    $type = gettype($value);
    $isNumeric = is_numeric($value) ? 'sim' : 'não';
    echo "Valor: {$value} | Tipo: {$type} | Numérico: {$isNumeric}" . PHP_EOL;
}
// Saída:
// Valor: 42      | Tipo: integer | Numérico: sim
// Valor: 3.14    | Tipo: double  | Numérico: sim
// Valor: 100     | Tipo: string  | Numérico: sim  ← string numérica!
// Valor: 12abc   | Tipo: string  | Numérico: não  ← não é puramente numérica
// Valor: NAN     | Tipo: double  | Numérico: não  ← Not A Number
// Valor: INF     | Tipo: double  | Numérico: sim  ← Infinito é considerado numérico
```

> **`NAN` e `INF`:** `NAN` (Not A Number) é o resultado de operações matemáticas inválidas como `0/0` ou `sqrt(-1)`. `INF` (Infinity) surge de divisões como `1/0`. Ambos são do tipo `float`. Para verificar: `is_nan($val)` e `is_infinite($val)`.

### Formatação para exibição

Números brutos como `1234567.891` são difíceis de ler. A função `number_format()` é essencial para exibir valores ao usuário de forma legível, especialmente em contextos de preços e relatórios. Note que **ela retorna uma string** — o resultado formatado não deve ser usado em cálculos matemáticos:

```php
<?php
declare(strict_types=1);

$price = 1234567.891;

// number_format(número, casas decimais, separador decimal, separador de milhar)
echo number_format($price, 2, ',', '.') . PHP_EOL; // 1.234.567,89 (formato BR)
echo number_format($price, 2, '.', ',') . PHP_EOL; // 1,234,567.89 (formato US)

// Divisão inteira — intdiv() descarta a parte decimal
echo intdiv(10, 3) . PHP_EOL; // 3 (não arredonda, apenas descarta)
// Operador % (módulo) — retorna o RESTO da divisão
echo 10 % 3 . PHP_EOL;        // 1 (porque 10 = 3×3 + 1)
// Módulo é muito usado para verificar par/ímpar: $n % 2 === 0
```

### ⚠️ Exercício

Crie uma função `calculateInstallments()` que receba um valor total e número de parcelas, retornando o valor de cada parcela formatado com 2 casas decimais.

---

## 8. PHP Casting

**Type casting** (conversão de tipo) é o ato de transformar um valor de um tipo para outro. No PHP, isso pode acontecer de duas formas: **implicitamente** (o PHP converte automaticamente, chamado *coercion*) ou **explicitamente** (você força a conversão).

Com `declare(strict_types=1)`, o PHP **desabilita a coerção implícita** em chamadas de função, tornando o casting explícito uma habilidade essencial — você precisa converter os dados antes de passá-los.

### Formas de casting

Existem duas formas principais de converter tipos: o operador de casting `(tipo)` (mais comum e direto) e as funções de conversão (`intval()`, etc.):

```php
<?php
declare(strict_types=1);

$stringNumber = '42';

// Casting explícito com operador (tipo)
// A sintaxe é: (tipo_desejado) valor
$asInt = (int) $stringNumber;      // 42 (inteiro)
$asFloat = (float) $stringNumber;  // 42.0 (ponto flutuante)
$asBool = (bool) $stringNumber;    // true ('42' não é vazio)
$asString = (string) 42;           // '42' (string)
$asArray = (array) 'texto';        // ['texto'] (array com 1 elemento)

echo gettype($asInt) . PHP_EOL;     // integer
echo gettype($asFloat) . PHP_EOL;   // double (nome interno do float)
echo gettype($asBool) . PHP_EOL;    // boolean

// Funções de conversão — alternativa mais legível em expressões complexas
$converted = intval('99');     // Equivalente a (int) '99'
$converted2 = floatval('3.14'); // Equivalente a (float) '3.14'
$converted3 = strval(100);      // Equivalente a (string) 100
$converted4 = boolval(1);       // Equivalente a (bool) 1
```

> **`(tipo)` vs `intval()`: quando usar qual?** São equivalentes na maioria dos casos. `(int)` é mais conciso; `intval()` aceita um segundo parâmetro para especificar a base numérica: `intval('FF', 16)` retorna `255`.

> **⚠️ PHP 8.5 — Deprecações de casting:**
> Os aliases `(boolean)`, `(integer)`, `(double)` e `(binary)` estão **deprecados**.
> Use sempre: `(bool)`, `(int)`, `(float)`, `(string)`.

### Conversões importantes

Existem regras específicas que o PHP segue ao converter entre tipos. Conhecer essas regras evita bugs sutis — especialmente a lista de valores **falsy** (que são convertidos para `false`), que é pergunta frequente em entrevistas e causa de bugs em produção:

```php
<?php
declare(strict_types=1);

// --- String para número ---
// O PHP lê do início da string até encontrar um caractere não-numérico
echo (int) '10abc' . PHP_EOL;     // 10 (para no 'a' — ignora o resto)
echo (int) 'abc' . PHP_EOL;       // 0 (nenhum dígito no início)
echo (int) '' . PHP_EOL;          // 0 (string vazia)
echo (float) '3.14xyz' . PHP_EOL; // 3.14

// --- Para boolean: valores "falsy" ---
// MEMORIZE esta lista — são os ÚNICOS valores que se tornam false:
var_dump((bool) 0);               // false — zero inteiro
var_dump((bool) 0.0);             // false — zero float
var_dump((bool) '');               // false — string vazia
var_dump((bool) '0');              // false — string "0" (PEGADINHA!)
var_dump((bool) []);               // false — array vazio
var_dump((bool) null);             // false — null

// TUDO o mais é true — inclusive valores que parecem "falsos":
var_dump((bool) 1);                // true
var_dump((bool) -1);               // true — números negativos!
var_dump((bool) 'false');          // true — a string 'false' NÃO é false!
var_dump((bool) 'qualquer texto'); // true
var_dump((bool) [1, 2]);           // true — array com elementos
var_dump((bool) ' ');              // true — string com espaço NÃO é vazia!

// ⚠️ PHP 8.5: casting de NAN agora emite Warning
// var_dump((int) NAN);  // Warning + resultado indeterminado
```

> **A pegadinha do `'0'`:** A string `'0'` ser `false` é uma particularidade do PHP que não existe em quase nenhuma outra linguagem. Tenha cuidado ao usar `if ($value)` para validar dados de formulários — o usuário pode digitar "0" (zero) e seu código tratar como se nada fosse digitado.

### settype() — altera o tipo da variável

Diferente do casting com `(tipo)`, que **cria um novo valor** sem alterar o original, `settype()` **modifica a variável existente** diretamente. Na prática, o casting com `(tipo)` é muito mais usado porque é mais previsível e funcional (não gera efeitos colaterais):

```php
<?php
declare(strict_types=1);

$value = '3.14';
echo gettype($value) . PHP_EOL;  // string (antes)

settype($value, 'float');        // Modifica a variável IN-PLACE
echo gettype($value) . PHP_EOL;  // double (depois — a variável mudou de tipo!)
echo $value . PHP_EOL;           // 3.14

// Comparação: casting vs settype
$original = '42';
$casted = (int) $original;       // $casted é 42 (int), $original continua '42' (string)
settype($original, 'integer');   // $original agora é 42 (int) — o original foi alterado!
```

> **Preferência:** No PHP moderno, **prefira casting explícito** `(int) $valor` sobre `settype()`. O casting é mais claro, não altera variáveis existentes e funciona melhor com `readonly` e imutabilidade.

### ⚠️ Exercício

Crie uma função que receba um valor `mixed` e retorne uma string descrevendo seu tipo e o resultado de converter para `int`, `float`, `bool` e `string`.

---

## 9. PHP Math

O PHP oferece um conjunto abrangente de funções matemáticas nativas, desde operações básicas (arredondamento, valor absoluto) até funções avançadas (logaritmos, trigonometria). Essas funções são essenciais para cálculos financeiros, processamento de dados, jogos, gráficos e qualquer aplicação que manipule números.

### Funções essenciais

As funções abaixo cobrem as operações matemáticas mais comuns no dia a dia de um desenvolvedor PHP:

```php
<?php
declare(strict_types=1);

// --- Arredondamento ---
// round() arredonda usando regra "metade para cima" por padrão
echo round(4.567, 2) . PHP_EOL;     // 4.57 (2 casas decimais)
echo round(2.5) . PHP_EOL;          // 3 (0.5 arredonda para cima)
// ceil() sempre arredonda para CIMA (ceiling = teto)
echo ceil(4.1) . PHP_EOL;           // 5
// floor() sempre arredonda para BAIXO (floor = chão)
echo floor(4.9) . PHP_EOL;          // 4

// ⚠️ Quando usar qual?
// round() → exibir preços ao usuário (R$ 19,99)
// ceil()  → calcular número de páginas (17 itens ÷ 5 por página = ceil(3.4) = 4 páginas)
// floor() → calcular idade (data de nascimento → anos completos)

// --- Valor absoluto ---
// abs() remove o sinal negativo, retornando a distância do zero
echo abs(-15) . PHP_EOL;            // 15
echo abs(15) . PHP_EOL;             // 15 (positivo permanece igual)

// --- Máximo e mínimo ---
// Aceitam múltiplos argumentos ou um array
echo max(10, 20, 5, 30) . PHP_EOL;  // 30
echo min(10, 20, 5, 30) . PHP_EOL;  // 5
echo max([85, 92, 78, 95]) . PHP_EOL; // 95 (também aceita arrays)

// --- Potência e raiz ---
// ✅ O operador ** é a forma moderna (PHP 5.6+), preferível a pow()
echo 2 ** 8 . PHP_EOL;              // 256 (2 elevado à 8ª potência)
echo 2 ** 0.5 . PHP_EOL;            // 1.414... (raiz quadrada via expoente)
echo sqrt(144) . PHP_EOL;           // 12 (raiz quadrada — equivalente a 144 ** 0.5)

// --- Módulo (resto da divisão) ---
// % funciona com inteiros; fmod() funciona com floats
echo 10 % 3 . PHP_EOL;              // 1 (porque 10 = 3×3 + 1)
echo fmod(10.5, 3.2) . PHP_EOL;     // 0.9 (resto com decimais)

// --- Logaritmo ---
echo log(M_E) . PHP_EOL;            // 1 (logaritmo natural, base e)
echo log10(1000) . PHP_EOL;         // 3 (logaritmo base 10: 10³ = 1000)
echo log(8, 2) . PHP_EOL;           // 3 (logaritmo base 2: 2³ = 8)

// --- Constantes matemáticas pré-definidas ---
echo M_PI . PHP_EOL;                // 3.14159265358979... (π)
echo M_E . PHP_EOL;                 // 2.71828182845905... (número de Euler)
echo M_SQRT2 . PHP_EOL;             // 1.41421356237310... (√2)
```

### Números aleatórios

A geração de números aleatórios é fundamental para tokens de sessão, códigos de verificação, senhas temporárias e qualquer funcionalidade de segurança. O PHP oferece duas gerações: a **insegura** (previsível, `rand()` e `mt_rand()`) e a **segura** (criptograficamente imprevisível, `random_int()` e `random_bytes()`). Em aplicações web, **sempre use as funções seguras**:

```php
<?php
declare(strict_types=1);

// ✅ random_int() — gera inteiro criptograficamente seguro
// Usa /dev/urandom (Linux) ou CryptGenRandom (Windows) como fonte de entropia
echo random_int(1, 100) . PHP_EOL;            // Número entre 1 e 100
echo random_int(100000, 999999) . PHP_EOL;    // Código de verificação de 6 dígitos

// ❌ NUNCA use rand() ou mt_rand() para segurança — são previsíveis!
// rand(1, 100);     // ❌ Inseguro — resultado pode ser adivinhado
// mt_rand(1, 100);  // ❌ Inseguro — algoritmo Mersenne Twister é previsível

// ✅ random_bytes() — gera bytes aleatórios seguros (ideal para tokens)
// bin2hex() converte bytes binários para string hexadecimal legível
$token = bin2hex(random_bytes(16)); // 16 bytes = 32 caracteres hex
echo "Token: {$token}" . PHP_EOL;   // Ex: "a3f8b2c4d5e6f7a8b9c0d1e2f3a4b5c6"

// Uso prático: gerar senha temporária de 8 caracteres
$tempPassword = bin2hex(random_bytes(4)); // 4 bytes = 8 caracteres hex
echo "Senha temporária: {$tempPassword}" . PHP_EOL;
```

### Exemplo prático — calculadora de IMC

Este exemplo combina várias funções matemáticas e conceitos modernos do PHP. Observe o uso de `round()` para limitar casas decimais, `**` para potência, `match(true)` para classificação por faixas, e Named Arguments para clareza:

```php
<?php
declare(strict_types=1);

// Calcula o IMC: peso (kg) ÷ altura² (m)
function calculateBmi(float $weightKg, float $heightM): float
{
    if ($heightM <= 0.0) {
        throw new InvalidArgumentException('Altura deve ser maior que zero.');
    }
    // $heightM ** 2 = altura ao quadrado
    // round(..., 2) = limita a 2 casas decimais
    return round($weightKg / ($heightM ** 2), 2);
}

// Classifica usando match(true) — compara cada condição sequencialmente
// match(true) é a alternativa moderna ao if/elseif/else para classificações
function classifyBmi(float $bmi): string
{
    return match (true) {
        $bmi < 18.5 => 'Abaixo do peso',
        $bmi < 25.0 => 'Peso normal',      // 18.5 até 24.9
        $bmi < 30.0 => 'Sobrepeso',         // 25.0 até 29.9
        default     => 'Obesidade',          // 30.0+
    };
}

// Named Arguments (weightKg: e heightM:) tornam a chamada autoexplicativa
$bmi = calculateBmi(weightKg: 75.0, heightM: 1.75);
$classification = classifyBmi($bmi);
echo "IMC: {$bmi} — Classificação: {$classification}" . PHP_EOL;
// Saída: IMC: 24.49 — Classificação: Peso normal
```

### ⚠️ Exercício

Crie uma função que calcule a área de um círculo usando `M_PI` e valide que o raio é positivo.

---

## 10. PHP Constants

Constantes são valores que **não podem ser alterados** após serem definidos. Diferente de variáveis (que podem mudar a qualquer momento), constantes representam valores que permanecem fixos durante toda a execução do programa. São essenciais para: configurações (nome da aplicação, versão), limites (máximo de tentativas de login), e valores de referência (códigos HTTP, alíquotas de impostos).

Por convenção, constantes são escritas em **UPPER_SNAKE_CASE**: `MAX_LOGIN_ATTEMPTS`, `DATABASE_HOST`. Isso as diferencia visualmente das variáveis (`$maxAttempts`).

### Definindo constantes

O PHP oferece duas formas de definir constantes: `const` e `define()`. Ambas criam valores imutáveis, mas possuem diferenças importantes:

```php
<?php
declare(strict_types=1);

// ✅ const — definição em tempo de compilação
// Mais rápido, pode ser usado dentro de classes e no escopo global
// O valor deve ser uma expressão constante (literais, operações entre constantes)
const APP_NAME = 'Minha Aplicação';
const APP_VERSION = '2.1.0';
const MAX_LOGIN_ATTEMPTS = 5;

echo APP_NAME . ' v' . APP_VERSION . PHP_EOL;

// define() — definição em tempo de execução
// Permite definição condicional e valores calculados dinamicamente
define('DATABASE_HOST', 'localhost');
define('DATABASE_PORT', 3306);

echo DATABASE_HOST . ':' . DATABASE_PORT . PHP_EOL;
```

| Característica | `const` | `define()` |
| :--- | :--- | :--- |
| Quando é criada | Compilação | Execução |
| Dentro de `if`/loops | ❌ Não permite | ✅ Permite |
| Dentro de classes | ✅ Sim | ❌ Não |
| Aceita expressões | Apenas constantes | Qualquer valor |
| Velocidade | Mais rápido | Mais lento |

> **Regra prática:** Use `const` por padrão. Use `define()` apenas quando precisar definir constantes condicionalmente (dentro de `if`) ou com valores dinâmicos.

### Constantes em classes

Constantes de classe são acessadas com `NomeDaClasse::CONSTANTE` (sem `$`). A partir do PHP 8.3, constantes de classe podem ser **tipadas**, adicionando segurança extra. Você também pode controlar a visibilidade (`public`, `protected`, `private`):

```php
<?php
declare(strict_types=1);

final class HttpStatus
{
    // Constantes de classe — acessíveis de qualquer lugar com NomeDaClasse::CONSTANTE
    // A parte `int` após `const` é tipagem de constantes (PHP 8.3+)
    public const int OK = 200;
    public const int CREATED = 201;
    public const int NOT_FOUND = 404;
    public const int SERVER_ERROR = 500;

    // Constante tipada como string (PHP 8.3+)
    public const string DEFAULT_MESSAGE = 'OK';

    // ⚠️ Constantes privadas só são visíveis dentro da própria classe
    private const int MAX_RETRIES = 3;
}

// Acesso externo via :: (operador de resolução de escopo)
echo HttpStatus::OK . PHP_EOL;            // 200
echo HttpStatus::NOT_FOUND . PHP_EOL;     // 404
// echo HttpStatus::MAX_RETRIES;          // ❌ Error: constante privada
```

> **Constantes tipadas (PHP 8.3+):** Antes do PHP 8.3, `public const OK = 200` aceitava qualquer tipo de valor. Com tipagem, `public const int OK = 200` garante que o valor seja sempre inteiro — o PHP rejeita atribuições incompatíveis em tempo de compilação.

### Constantes em Enums

Enums (introduzidos no PHP 8.1) também podem conter constantes. Isso é útil para definir valores padrão ou aliases para casos específicos. A constante `DEFAULT` abaixo aponta para um caso existente do enum, criando um "atalho" reutilizável:

```php
<?php
declare(strict_types=1);

enum Color: string
{
    case Red = '#FF0000';
    case Green = '#00FF00';
    case Blue = '#0000FF';

    // Constante tipada dentro do enum — aponta para um caso existente
    // `self::Blue` referencia o próprio enum
    public const Color DEFAULT = self::Blue;
}

echo Color::DEFAULT->value . PHP_EOL; // #0000FF
echo Color::Red->value . PHP_EOL;     // #FF0000

// ⚠️ A constante DEFAULT é do tipo Color (o próprio enum),
// então possui ->value e todos os métodos do enum
```

### ⚠️ Exercício

Crie uma classe `Config` com constantes para conexão ao banco de dados (host, porta, nome, charset).

---

## 11. PHP Magic Constants

Diferente das constantes normais (que têm valor fixo), as **constantes mágicas** são valores especiais que **mudam automaticamente** dependendo de **onde** são usadas no código. O nome "mágica" vem exatamente disso: o mesmo `__LINE__` escrito na linha 10 retorna `10`, mas escrito na linha 50 retorna `50` — o PHP resolve o valor em tempo de compilação.

Todas as constantes mágicas seguem o padrão `__NOME__` (dois underscores antes e depois). O PHP possui **8 constantes mágicas**. Elas são especialmente úteis para depuração, logging e autoloaders.

### Lista completa

```php
<?php
declare(strict_types=1);

// __LINE__ — número da linha atual no arquivo
// Muda conforme a posição no código — essencial para logs de erro
echo 'Linha: ' . __LINE__ . PHP_EOL;  // Ex: 6 (depende da posição)

// __FILE__ — caminho absoluto completo do arquivo atual
// Inclui diretório + nome: "/var/www/app/index.php"
echo 'Arquivo: ' . __FILE__ . PHP_EOL;

// __DIR__ — diretório do arquivo (sem o nome do arquivo)
// ✅ Equivale a dirname(__FILE__), mas mais legível
// ✅ Muito usado para incluir arquivos de forma confiável
echo 'Diretório: ' . __DIR__ . PHP_EOL;

// __FUNCTION__ — nome da função onde está sendo usado
// Fora de qualquer função, retorna string vazia
function myTestFunction(): void
{
    echo 'Função: ' . __FUNCTION__ . PHP_EOL;  // "myTestFunction"
}
myTestFunction();

// __CLASS__ — nome completo da classe (com namespace)
final class MyExampleClass
{
    public function showClass(): void
    {
        echo 'Classe: ' . __CLASS__ . PHP_EOL;  // "MyExampleClass"
    }
}
(new MyExampleClass())->showClass();

// __METHOD__ — nome completo: "NomeDaClasse::nomeDoMetodo"
// Diferente de __FUNCTION__, inclui o nome da classe
final class AnotherClass
{
    public function showMethod(): void
    {
        echo 'Método: ' . __METHOD__ . PHP_EOL; // "AnotherClass::showMethod"
    }
}
(new AnotherClass())->showMethod();

// __NAMESPACE__ — namespace atual do arquivo
// Retorna string vazia se não houver namespace declarado
namespace App\Models;
echo __NAMESPACE__ . PHP_EOL;  // "App\Models"

// __TRAIT__ — nome do trait atual (análogo a __CLASS__ para traits)
trait Loggable
{
    public function traitName(): string
    {
        return __TRAIT__;  // "App\Models\Loggable"
    }
}
```

> **`__CLASS__` vs `::class`:** A sintaxe `NomeDaClasse::class` (sem underscores) retorna o nome completo da classe como string, e pode ser usada **fora** da classe. `__CLASS__` só funciona **dentro** da classe. No PHP moderno, prefira `::class` quando possível:
> `$className = HttpStatus::class; // "HttpStatus"`

### Tabela de referência

| Constante       | Valor                       |
| --------------- | --------------------------- |
| `__LINE__`      | Número da linha atual       |
| `__FILE__`      | Caminho completo do arquivo |
| `__DIR__`       | Diretório do arquivo        |
| `__FUNCTION__`  | Nome da função              |
| `__CLASS__`     | Nome da classe (FQN)        |
| `__METHOD__`    | `Classe::método`            |
| `__NAMESPACE__` | Namespace atual             |
| `__TRAIT__`     | Nome do trait               |

### Uso prático — autoloader com `__DIR__`

O uso mais importante de `__DIR__` é em autoloaders e includes. Como `__DIR__` sempre retorna o diretório **do arquivo onde está escrito** (não do arquivo que o chamou), ele garante que os caminhos funcionem independentemente de onde o script é executado:

```php
<?php
declare(strict_types=1);

// ✅ CORRETO — caminho relativo ao arquivo atual (funciona sempre)
require_once __DIR__ . '/config/database.php';
require_once __DIR__ . '/../vendor/autoload.php';

// ❌ ERRADO — caminho relativo ao diretório de trabalho (pode falhar)
// require_once 'config/database.php';  // Depende de onde o PHP foi executado
```

### Uso prático — log de debug

Combinar constantes mágicas cria logs extremamente informativos que apontam exatamente onde o problema ocorreu:

```php
<?php
declare(strict_types=1);

function debugLog(string $message): void
{
    $timestamp = date('Y-m-d H:i:s');
    // Usando constantes mágicas para identificar o local exato
    error_log(sprintf(
        "[%s] %s — em %s:%d",
        $timestamp,
        $message,
        __FILE__,   // Qual arquivo
        __LINE__    // Qual linha
    ));
    // Saída: [2026-02-21 00:35:00] Erro de conexão — em /var/www/app.php:12
}

// ⚠️ Atenção: __FILE__ e __LINE__ dentro de debugLog() apontam para
// o arquivo/linha DA FUNÇÃO, não de onde ela foi chamada.
// Para capturar o local da chamada, use debug_backtrace():
function smartLog(string $message): void
{
    $caller = debug_backtrace(DEBUG_BACKTRACE_IGNORE_ARGS, 1)[0];
    error_log(sprintf(
        "[%s] %s — chamado de %s:%d",
        date('Y-m-d H:i:s'),
        $message,
        $caller['file'],
        $caller['line']
    ));
}

smartLog('Erro detectado aqui');
// Saída: [2026-02-21 00:35:00] Erro detectado aqui — chamado de /var/www/index.php:45
```

### ⚠️ Exercício

Crie uma função `logError()` que registre automaticamente o arquivo, linha e função de onde foi chamada.

---

## 12. PHP Operators

Operadores são símbolos que realizam operações sobre valores e variáveis. O PHP possui operadores aritméticos, de comparação, lógicos, de atribuição, e operadores especiais como o null coalescing (`??`) e o pipe (`|>`). Entender a **precedência** (qual operador é avaliado primeiro) é fundamental para evitar bugs — na dúvida, sempre use parênteses para deixar a intenção explícita.

### Aritméticos

Os operadores aritméticos funcionam como na matemática. A divisão `/` sempre retorna `float` quando o resultado não é inteiro:

```php
<?php
declare(strict_types=1);

$a = 10;
$b = 3;

echo $a + $b . PHP_EOL;   // 13 — soma
echo $a - $b . PHP_EOL;   // 7  — subtração
echo $a * $b . PHP_EOL;   // 30 — multiplicação
echo $a / $b . PHP_EOL;   // 3.333... — divisão (retorna float se não for exato)
echo $a % $b . PHP_EOL;   // 1  — módulo (resto da divisão: 10 = 3×3 + 1)
echo $a ** $b . PHP_EOL;  // 1000 — exponenciação (10³)

// ⚠️ Divisão por zero lança DivisionByZeroError no PHP 8+
// echo 10 / 0;  // DivisionByZeroError
```

### Comparação

A diferença entre `==` (comparação solta) e `===` (comparação estrita) é uma das maiores fontes de bugs em PHP. A comparação solta converte os tipos antes de comparar, causando resultados inesperados. **Sempre use `===`**:

```php
<?php
declare(strict_types=1);

// ❌ == (comparação solta) — converte tipos, resultados surpreendentes!
var_dump(0 == 'abc');    // false (PHP 8+, mas era true no PHP 7!)
var_dump(1 == '1');      // true  — string '1' vira inteiro 1
var_dump('' == false);   // true  — string vazia vira false
var_dump(null == false); // true  — null vira false

// ✅ === (comparação estrita) — compara valor E tipo, sem surpresas
var_dump(1 === '1');     // false — int !== string
var_dump(1 === 1);       // true  — mesmo valor E mesmo tipo
var_dump('' === false);  // false — string !== bool

// <=> Spaceship operator (retorna -1, 0 ou 1)
// Muito usado com usort() para ordenação personalizada
echo 1 <=> 2 . PHP_EOL;   // -1 (esquerdo MENOR que direito)
echo 2 <=> 2 . PHP_EOL;   // 0  (iguais)
echo 3 <=> 2 . PHP_EOL;   // 1  (esquerdo MAIOR que direito)

// Exemplo prático: ordenar array de números decrescente
$numbers = [3, 1, 4, 1, 5, 9];
usort($numbers, fn(int $a, int $b): int => $b <=> $a);
// Resultado: [9, 5, 4, 3, 1, 1]
```

### Null Coalescing e Null Safe

Estes operadores foram introduzidos para lidar com valores `null` de forma elegante, substituindo verificações verbosas com `isset()` e `!== null`:

```php
<?php
declare(strict_types=1);

// ?? — null coalescing: retorna o lado esquerdo se NÃO for null,
// caso contrário retorna o lado direito (valor padrão)
$userName = $_GET['name'] ?? 'Visitante';
echo $userName . PHP_EOL;
// ✅ Equivale a: isset($_GET['name']) ? $_GET['name'] : 'Visitante'

// Encadeamento: tenta cada opção da esquerda para a direita
$color = $config['color'] ?? $default['color'] ?? 'azul';

// ??= — null coalescing assignment: atribui SOMENTE se o valor atual for null
$config = [];
$config['theme'] ??= 'dark';  // Define 'dark' porque $config['theme'] é null
echo $config['theme'] . PHP_EOL; // dark
$config['theme'] ??= 'light'; // NÃO altera porque já não é null
echo $config['theme'] . PHP_EOL; // dark (mantém o valor anterior)

// ?-> — null safe operator (PHP 8.0+)
// Propagation de null: se o objeto for null, toda a cadeia retorna null
// ao invés de lançar erro "Call to a member function on null"
final class Address
{
    public function __construct(
        public readonly ?string $city = null,
    ) {}
}

final class User
{
    public function __construct(
        public readonly ?Address $address = null,
    ) {}
}

$user = new User(address: null);

// ❌ Sem null safe — verboso e propenso a erro
// $city = $user->address !== null ? $user->address->city : null;

// ✅ Com null safe — se address for null, retorna null (sem erro)
echo $user->address?->city ?? 'Cidade não informada';
echo PHP_EOL;
```

### Pipe Operator (PHP 8.5)

O operador pipe `|>` é uma das novidades mais aguardadas do PHP 8.5. Ele transforma chamadas de função aninhadas (lidas de dentro para fora) em uma sequência linear (lida de cima para baixo), tornando o código muito mais legível:

```php
<?php
declare(strict_types=1);

$text = '  php 8.5 é incrível!  ';

// ❌ LEGADO — funções aninhadas: leia de DENTRO para FORA
// $result = ucwords(trim($text));
// Ordem real: 1) trim, 2) ucwords — mas lemos ao contrário

// ✅ Pipe operator — leitura natural da esquerda para a direita
// O resultado de cada linha é passado como argumento da próxima
$result = $text
    |> trim(...)       // 1° Remove espaços: "php 8.5 é incrível!"
    |> ucwords(...);   // 2° Capitaliza: "Php 8.5 É Incrível!"

echo $result . PHP_EOL; // Php 8.5 É Incrível!

// A sintaxe (...) é a First-Class Callable Syntax (PHP 8.1)
// trim(...) transforma a função trim em um valor callable
```

### Lógicos

Operadores lógicos combinam condições booleanas. O PHP usa **avaliação de curto-circuito**: se o resultado já for determinado pelo primeiro operando, o segundo **não é avaliado** — isso é útil para evitar erros:

```php
<?php
declare(strict_types=1);

$isAdult = true;
$hasTicket = false;

// && (AND) — true somente se AMBOS forem true
var_dump($isAdult && $hasTicket);   // false (hasTicket é false)

// || (OR) — true se PELO MENOS UM for true
var_dump($isAdult || $hasTicket);   // true (isAdult é true)

// ! (NOT) — inverte o valor booleano
var_dump(!$hasTicket);              // true (inverte false)

// ⚠️ Curto-circuito: o segundo operando NÃO é avaliado se desnecessário
// Útil para evitar erros:
$user = null;
// Se $user for null, a segunda parte NÃO é avaliada (evita erro)
if ($user !== null && $user->isActive()) {
    echo 'Usuário ativo';
}
```

### ⚠️ Exercício

Use o operador `<=>` (spaceship) junto com `usort()` para ordenar um array de produtos por preço.

### Atribuição composta

```php
<?php
declare(strict_types=1);

$total = 100;

$total += 50;   // $total = $total + 50  → 150
$total -= 20;   // $total = $total - 20  → 130
$total *= 2;    // $total = $total * 2   → 260
$total /= 4;    // $total = $total / 4   → 65.0
$total %= 10;   // $total = $total % 10  → 5
$total **= 3;   // $total = $total ** 3  → 125

$text = 'PHP';
$text .= ' 8.5'; // Concatenação: 'PHP 8.5'
```

### Spread Operator `...`

O operador `...` (three dots / spread) tem dois usos diferentes dependendo do contexto: na **definição** de função ele **coleta** argumentos (variadic), e na **chamada** ele **expande** arrays em argumentos individuais:

```php
<?php
declare(strict_types=1);

// 1. Spread em arrays — mescla arrays de forma limpa
$base = [1, 2, 3];
$extended = [0, ...$base, 4, 5]; // [0, 1, 2, 3, 4, 5]

// 2. Na DEFINIÇÃO: coleta argumentos variáveis (variadic)
// int ...$numbers aceita 0 ou mais inteiros como array
function sum(int ...$numbers): int
{
    return array_sum($numbers);
}

echo sum(1, 2, 3, 4, 5) . PHP_EOL; // 15
echo sum() . PHP_EOL;               // 0 (nenhum argumento é válido)

// 3. Na CHAMADA: expande um array em argumentos individuais
$args = [10, 20, 30];
echo sum(...$args) . PHP_EOL; // 60 (equivale a sum(10, 20, 30))
```

> **Dica de precedência:** Na dúvida, use parênteses para tornar a intenção explícita. `$a + $b * $c` é `$a + ($b * $c)`, não `($a + $b) * $c`.

---

## 13. PHP If...Else...Elseif

Estruturas condicionais controlam o **fluxo de execução** do programa, decidindo quais blocos de código serão executados com base em condições booleanas. O `if` é a estrutura mais fundamental — todas as outras (ternário, `match`, `switch`) são variações para casos específicos.

A ordem dos `elseif` importa: o PHP avalia de cima para baixo e **executa apenas o primeiro bloco** cuja condição for `true`. Os demais são ignorados.

### Sintaxe básica

```php
<?php
declare(strict_types=1);

$temperature = 32;

// O PHP avalia cada condição sequencialmente:
// 1. 32 >= 35? Não → pula
// 2. 32 >= 25? Sim → executa este bloco e ignora o resto
if ($temperature >= 35) {
    echo 'Está muito quente!' . PHP_EOL;
} elseif ($temperature >= 25) {
    echo 'Temperatura agradável.' . PHP_EOL;  // ✅ Executado
} elseif ($temperature >= 15) {
    echo 'Está fresco.' . PHP_EOL;
} else {
    // else é o "fallback" — executado quando NENHUMA condição anterior é true
    echo 'Está frio!' . PHP_EOL;
}
```

### Operador ternário

O ternário é um `if/else` condensado em uma única linha. A sintaxe é: `condição ? valor_se_true : valor_se_false`. Use para atribuições simples — para lógica complexa, prefira `if/else` convencional:

```php
<?php
declare(strict_types=1);

$age = 20;

// Ternário simples — equivale a if ($age >= 18) { 'Adulto' } else { 'Menor' }
$category = $age >= 18 ? 'Adulto' : 'Menor de idade';
echo $category . PHP_EOL;  // Adulto

// ❌ EVITE ternários aninhados — ilegíveis
// $result = $a > $b ? 'maior' : ($a < $b ? 'menor' : 'igual');

// ?: — Elvis operator (ternário curto)
// Retorna o lado esquerdo se truthy, senão o lado direito
$displayName = '' ?: 'Nome padrão';  // 'Nome padrão' (string vazia é falsy)
echo $displayName . PHP_EOL;

// ⚠️ ?: vs ?? — diferença sutil:
// ?: testa se é truthy (0, '', [] são falsy)
// ?? testa apenas se é null (0, '' NÃO são null)
echo 0 ?: 'fallback' . PHP_EOL;   // 'fallback' (0 é falsy)
echo 0 ?? 'fallback' . PHP_EOL;   // 0 (0 não é null)
```

### Exemplo prático — validação

```php
<?php
declare(strict_types=1);

function validateAge(int $age): string
{
    if ($age < 0 || $age > 150) {
        throw new InvalidArgumentException(
            "Idade inválida: {$age}. Deve estar entre 0 e 150."
        );
    }

    if ($age < 12) {
        return 'Criança';
    } elseif ($age < 18) {
        return 'Adolescente';
    } elseif ($age < 60) {
        return 'Adulto';
    } else {
        return 'Idoso';
    }
}

try {
    echo validateAge(25) . PHP_EOL;   // Adulto
    echo validateAge(8) . PHP_EOL;    // Criança
    echo validateAge(-1) . PHP_EOL;   // Exceção!
} catch (InvalidArgumentException $e) {
    echo "Erro: {$e->getMessage()}" . PHP_EOL;
}
```

### ⚠️ Exercício

Crie uma função que receba uma nota (0-100) e retorne o conceito: A (90+), B (80+), C (70+), D (60+), F (abaixo de 60).

> **Dica — Early Return:** Sempre que possível, valide e retorne cedo para reduzir aninhamento:
>
> ```php
> // ❌ Aninhado demais
> function process(int $value): string {
>     if ($value > 0) {
>         if ($value < 100) {
>             return 'Válido';
>         }
>     }
>     return 'Inválido';
> }
>
> // ✅ Early return — limpo e legível
> function process(int $value): string {
>     if ($value <= 0 || $value >= 100) {
>         return 'Inválido';
>     }
>     return 'Válido';
> }
> ```

---

## 14. PHP Switch

O `switch` compara uma expressão contra múltiplos valores possíveis. Ele é equivalente a uma série de `if/elseif` comparando a mesma variável. Porém, possui **duas armadilhas** que todo iniciante deve conhecer:

1. Usa comparação **solta** (`==`) — pode causar comparações inesperadas
2. Requer `break` explícito — sem ele, a execução "cai" para o próximo case (fall-through)

> ⚠️ **Recomendação PHP moderno:** Para a maioria dos casos, prefira `match` (PHP 8.0+) que usa `===`, não precisa de `break`, e retorna valores.

> ⚠️ **PHP 8.5 — Deprecação:** Terminar `case` com ponto e vírgula (`;`) ao invés de dois pontos (`:`) está **deprecado**. Sempre use `:` após `case`.

```php
<?php
declare(strict_types=1);

$dayOfWeek = 3;

switch ($dayOfWeek) {
    case 1:
        echo 'Segunda-feira' . PHP_EOL;
        break;  // ⚠️ OBRIGATÓRIO — sem break, executa o case seguinte!
    case 2:
        echo 'Terça-feira' . PHP_EOL;
        break;
    case 3:
        echo 'Quarta-feira' . PHP_EOL;
        break;
    case 4:
        echo 'Quinta-feira' . PHP_EOL;
        break;
    case 5:
        echo 'Sexta-feira' . PHP_EOL;
        break;
    case 6:
    case 7:
        // Fall-through intencional: 6 e 7 executam o MESMO bloco
        echo 'Fim de semana!' . PHP_EOL;
        break;
    default:
        // default é executado se NENHUM case corresponder
        echo 'Dia inválido' . PHP_EOL;
        break;
}
```

### Quando usar switch vs match

Use `switch` quando precisa executar **blocos de código** com múltiplas instruções e efeitos colaterais. Use `match` quando quer simplesmente **mapear um valor para outro**:

```php
<?php
declare(strict_types=1);

// Switch — útil quando precisa executar BLOCOS de código
// (múltiplas instruções, chamadas a funções, efeitos colaterais)
$action = 'save';

switch ($action) {
    case 'save':
        // Validar dados...
        // Salvar no banco...
        // Registrar log...
        echo 'Dados salvos com sucesso!' . PHP_EOL;
        break;

    case 'delete':
        // Confirmar exclusão...
        // Remover registro...
        echo 'Registro removido!' . PHP_EOL;
        break;

    default:
        echo 'Ação desconhecida.' . PHP_EOL;
}

// ✅ O mesmo código com match — quando o resultado é um simples valor:
// $message = match ($action) {
//     'save'   => 'Dados salvos com sucesso!',
//     'delete' => 'Registro removido!',
//     default  => 'Ação desconhecida.',
// };
```

---

## 15. PHP Match

A expressão `match` (PHP 8.0+) é a **alternativa moderna e segura** ao `switch`. Ela resolve todas as armadilhas do `switch`: usa comparação estrita (`===`), não precisa de `break`, e **retorna um valor** — o que a torna ideal para atribuições e expressões.

A diferença mais importante é que `match` **lança erro** (`UnhandledMatchError`) se nenhum braço corresponder e não houver `default`. Isso evita bugs silenciosos que passam despercebidos com `switch`.

### Diferenças: match vs switch

| Característica       | `match`                 | `switch`     |
| -------------------- | ----------------------- | ------------ |
| Comparação           | Estrita (`===`)         | Solta (`==`) |
| Retorna valor?       | ✅ Sim                   | ❌ Não        |
| Precisa de break?    | ❌ Não                   | ✅ Sim        |
| Sem match gera erro? | ✅ `UnhandledMatchError` | ❌ Silencioso |

### Sintaxe básica

A sintaxe é `match (expressão) { valor => resultado, ... }`. Cada braço usa `=>` (seta) e termina com vírgula. O resultado inteiro é uma **expressão** — pode ser atribuída a uma variável:

```php
<?php
declare(strict_types=1);

$statusCode = 404;

// ✅ match — atribui o resultado diretamente a $message
$message = match ($statusCode) {
    200     => 'OK',
    201     => 'Criado',
    301     => 'Redirecionado permanentemente',
    400     => 'Requisição inválida',
    401     => 'Não autorizado',
    403     => 'Proibido',
    404     => 'Não encontrado',
    500     => 'Erro interno do servidor',
    default => 'Status desconhecido',
};

echo "HTTP {$statusCode}: {$message}" . PHP_EOL;
// Saída: HTTP 404: Não encontrado

// ⚠️ Sem default e sem correspondência = UnhandledMatchError
// match (999) { 200 => 'OK' };  // ❌ UnhandledMatchError!
```

### Match com múltiplos valores

```php
<?php
declare(strict_types=1);

$extension = 'jpg';

$fileType = match ($extension) {
    'jpg', 'jpeg', 'png', 'gif', 'webp' => 'Imagem',
    'mp4', 'avi', 'mkv', 'mov'          => 'Vídeo',
    'mp3', 'wav', 'flac', 'ogg'         => 'Áudio',
    'pdf', 'doc', 'docx', 'txt'         => 'Documento',
    default                              => 'Desconhecido',
};

echo "Tipo: {$fileType}" . PHP_EOL; // Imagem
```

### Match sem argumento (match(true))

Quando você precisa comparar **faixas de valores** (ao invés de valores exatos), use `match(true)`. Neste padrão, cada braço contém uma **expressão booleana** — o PHP executa o primeiro que for `true`:

```php
<?php
declare(strict_types=1);

$score = 85;

// match(true) — cada braço é uma condição booleana
// O PHP avalia de cima para baixo e retorna o PRIMEIRO que for true
$grade = match (true) {
    $score >= 90 => 'A — Excelente',       // 85 >= 90? Não
    $score >= 80 => 'B — Muito bom',       // 85 >= 80? Sim ✅
    $score >= 70 => 'C — Bom',             // Não avaliado
    $score >= 60 => 'D — Regular',         // Não avaliado
    default      => 'F — Insuficiente',    // Não avaliado
};

echo "Nota {$score}: {$grade}" . PHP_EOL;
// Saída: Nota 85: B — Muito bom

// ⚠️ A ordem dos braços importa! Se colocasse >= 60 primeiro,
// TODOS os valores acima de 60 cairiam nesse braço.
```

### ⚠️ Exercício

Use `match` para criar um conversor de moedas simples que suporte BRL, USD, EUR e GBP.

---

## 16. PHP Loops

Loops repetem um bloco de código enquanto uma condição for verdadeira. O PHP oferece **quatro tipos** de loops, cada um ideal para uma situação:

- `while` — quando não sabe quantas vezes repetir
- `do...while` — quando precisa executar pelo menos uma vez
- `for` — quando sabe exatamente quantas vezes repetir
- `foreach` — quando precisa percorrer arrays ou objetos (o mais usado)

### while

O `while` verifica a condição **antes** de cada execução. Se a condição já for falsa na primeira verificação, o bloco **nunca** executa:

```php
<?php
declare(strict_types=1);

// while — verifica a condição ANTES de executar
// Se $counter já fosse > 5, o bloco nunca executaria
$counter = 1;

while ($counter <= 5) {
    echo "Contagem: {$counter}" . PHP_EOL;
    $counter++;  // ⚠️ Sem isso, loop infinito!
}
```

### do...while

Diferente do `while`, o `do...while` executa o bloco **primeiro** e só depois verifica a condição. Isso garante que o bloco rode **pelo menos uma vez** — ideal para menus e leitura de entrada do usuário:

```php
<?php
declare(strict_types=1);

// do...while — executa pelo menos UMA vez, depois verifica
// Perfeito para menus e validação de entrada
$input = '';

do {
    $input = readline('Digite "sair" para encerrar: ');
    echo "Você digitou: {$input}" . PHP_EOL;
} while ($input !== 'sair');
// Mesmo se o usuário digitar "sair" na primeira vez,
// o bloco já terá executado uma vez
```

### for

O `for` tem três partes: `for (inicialização; condição; incremento)`. Use quando sabe exatamente quantas iterações precisa:

```php
<?php
declare(strict_types=1);

// for — 3 partes: ini; condição; incremento
// 1. $i = 0     → executado UMA vez no início
// 2. $i < 10    → verificado ANTES de cada iteração
// 3. $i++       → executado APÓS cada iteração
for ($i = 0; $i < 10; $i++) {
    echo "Iteração {$i}" . PHP_EOL;
}

// Contagem regressiva
for ($i = 10; $i > 0; $i--) {
    echo "{$i}..." . PHP_EOL;
}
echo 'Lançamento!' . PHP_EOL;

// ⚠️ Evite chamar funções na condição (recalculada a cada iteração):
// ❌ for ($i = 0; $i < count($array); $i++) — count() chamado N vezes
// ✅ $length = count($array); for ($i = 0; $i < $length; $i++) — count() 1 vez
```

### foreach

O `foreach` é o loop **mais usado** no PHP. Ele percorre automaticamente cada elemento de um array ou objeto iterável. Diferente do `for`, não precisa de contador manual:

```php
<?php
declare(strict_types=1);

// foreach — percorre cada elemento automaticamente
// A variável $fruit recebe uma CÓPIA de cada elemento
$fruits = ['Maçã', 'Banana', 'Laranja', 'Uva'];

foreach ($fruits as $fruit) {
    echo "Fruta: {$fruit}" . PHP_EOL;
}

// Com chave => valor — acessa tanto o índice/chave quanto o valor
$prices = ['Café' => 5.50, 'Pão' => 3.00, 'Leite' => 7.90];

foreach ($prices as $product => $price) {
    echo "{$product}: R$ " . number_format($price, 2, ',', '.') . PHP_EOL;
}
// Café: R$ 5,50
// Pão: R$ 3,00
// Leite: R$ 7,90
```

### break e continue

Dois comandos controlam o fluxo dentro de loops: `break` sai do loop imediatamente, `continue` pula para a próxima iteração. Ambos aceitam um número para atuar em loops aninhados (ex: `break 2` sai de 2 loops):

```php
<?php
declare(strict_types=1);

// break — sai do loop IMEDIATAMENTE
for ($i = 0; $i < 100; $i++) {
    if ($i === 5) {
        break; // Para no 5 — não executa o echo para 5
    }
    echo $i . PHP_EOL;  // Saída: 0, 1, 2, 3, 4
}

// continue — PULA para a próxima iteração (não executa o restante)
for ($i = 0; $i < 10; $i++) {
    if ($i % 2 === 0) {
        continue; // Pula os pares — vai direto para $i++
    }
    echo "Ímpar: {$i}" . PHP_EOL;  // Saída: 1, 3, 5, 7, 9
}
```

### foreach com desestruturação

A desestruturação permite "desempacotar" arrays dentro do `foreach`, extraindo valores diretamente em variáveis nomeadas. Isso evita acessos repetidos como `$student['nome']`:

```php
<?php
declare(strict_types=1);

// Desestruturação de arrays associativos dentro do foreach
// Ao invés de: foreach ($students as $student) { $student['nome']... }
// Extrai diretamente: 'nome' => $name, 'nota' => $grade
$students = [
    ['nome' => 'Ana', 'nota' => 9.5],
    ['nome' => 'Carlos', 'nota' => 7.2],
    ['nome' => 'Maria', 'nota' => 8.8],
];

foreach ($students as ['nome' => $name, 'nota' => $grade]) {
    $status = $grade >= 7.0 ? '✅ Aprovado' : '❌ Reprovado';
    echo "{$name}: {$grade} — {$status}" . PHP_EOL;
}
// Ana: 9.5 — ✅ Aprovado
// Carlos: 7.2 — ✅ Aprovado
// Maria: 8.8 — ✅ Aprovado
```

### PHP 8.5: `array_first()` e `array_last()`

```php
<?php
declare(strict_types=1);

$queue = ['urgente', 'normal', 'baixa'];

// ✅ PHP 8.5 — funções nativas
echo array_first($queue) . PHP_EOL; // urgente
echo array_last($queue) . PHP_EOL;  // baixa

// LEGADO — antes do PHP 8.5
// $first = reset($queue);  // modifica o ponteiro interno!
// $last = end($queue);     // modifica o ponteiro interno!
```

### ⚠️ Exercício

Use `foreach` para percorrer um array de alunos com notas e exiba apenas os aprovados (nota >= 7).

---

## 17. PHP Functions

Funções são blocos de código reutilizáveis que recebem entradas (parâmetros), processam dados e retornam um resultado. Elas são fundamentais para organizar o código, evitar repetição e facilitar testes. No PHP moderno, **sempre** declare tipos nos parâmetros e no retorno — isso, combinado com `declare(strict_types=1)`, garante que erros de tipo sejam detectados imediatamente.

### Declaração básica

```php
<?php
declare(strict_types=1);

// Função com tipos explícitos no parâmetro e retorno
// float $price → aceita apenas float
// : float      → retorna apenas float
function calculateDiscount(float $price, float $percentage): float
{
    if ($percentage < 0 || $percentage > 100) {
        throw new InvalidArgumentException('Percentual deve estar entre 0 e 100.');
    }
    return round($price * (1 - $percentage / 100), 2);
}

echo calculateDiscount(100.00, 15.0) . PHP_EOL; // 85.00
// calculateDiscount('cem', 15.0); // ❌ TypeError com strict_types=1
```

### Named arguments (PHP 8.0+)

Argumentos nomeados permitem passar parâmetros **em qualquer ordem**, referenciando-os pelo nome. Isso torna chamadas de função com muitos parâmetros (especialmente os opcionais) muito mais legíveis:

```php
<?php
declare(strict_types=1);

// trailing comma após o último parâmetro é válida no PHP 8.0+
function createUser(
    string $name,
    string $email,
    int $age = 18,        // Valor padrão: 18 se não informado
    bool $isAdmin = false, // Valor padrão: false se não informado
): array
{
    return compact('name', 'email', 'age', 'isAdmin');
}

// ✅ Com named arguments — ordem livre, autoexplicativo
// Pulamos $age (usa o padrão 18) e definimos apenas $isAdmin
$user = createUser(
    email: 'ana@email.com',
    name: 'Ana Silva',
    isAdmin: true,
);

print_r($user);
// Array ( [name] => Ana Silva [email] => ana@email.com [age] => 18 [isAdmin] => 1 )
```

### Arrow functions (fn)

Arrow functions são funções anônimas **de uma única expressão**. Diferente da closure tradicional (`function() use (...)`), elas capturam variáveis do escopo externo **automaticamente** (por valor). Muito usadas com `array_map`, `array_filter` e `usort`:

```php
<?php
declare(strict_types=1);

// Arrow function — captura $multiplier automaticamente (sem `use`)
$multiplier = 3;
$multiply = fn(int $value): int => $value * $multiplier;

echo $multiply(5) . PHP_EOL; // 15

// Comum com array_map/array_filter
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// array_filter: mantém apenas os que retornam true
$evens = array_filter($numbers, fn(int $n): bool => $n % 2 === 0);
// array_map: transforma CADA elemento
$doubled = array_map(fn(int $n): int => $n * 2, $numbers);

print_r($evens);   // [2, 4, 6, 8, 10]
print_r($doubled); // [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```

### First-class callable syntax (PHP 8.1+)

```php
<?php
declare(strict_types=1);

// Referência a funções como valores com (...)
$numbers = [3, 1, 4, 1, 5, 9];

// LEGADO - PHP < 8.1 — string com nome da função
// usort($numbers, 'compareFunction');

// ✅ MODERNO — first-class callable
usort($numbers, strcmp(...)); // Não funciona com tipos mistos aqui

// Exemplo prático com pipe operator (PHP 8.5)
$text = '  hello world  ';
$result = $text
    |> trim(...)
    |> strtoupper(...)
    |> strrev(...);

echo $result . PHP_EOL; // DLROW OLLEH
```

### Tipos de retorno especiais

```php
<?php
declare(strict_types=1);

// void — não retorna nada
function logMessage(string $message): void
{
    echo "[LOG] {$message}" . PHP_EOL;
}

// never — nunca retorna (lança exceção ou termina execução)
function throwError(string $message): never
{
    throw new RuntimeException($message);
}

// Union types no retorno
function divide(float $a, float $b): float|false
{
    if ($b === 0.0) {
        return false;
    }
    return $a / $b;
}
```

### #[\NoDiscard] (PHP 8.5)

```php
<?php
declare(strict_types=1);

// PHP 8.5: avisa se o valor de retorno for ignorado
#[\NoDiscard('O resultado da validação deve ser verificado')]
function validateInput(string $input): bool
{
    return mb_strlen($input) >= 3;
}

// ✅ Correto — usa o retorno
if (validateInput('ab')) {
    echo 'Válido' . PHP_EOL;
}

// ⚠️ PHP 8.5 emitirá Warning se o retorno for ignorado:
// validateInput('ab'); // Warning: The return value ... should not be discarded
```

### ⚠️ Exercício

Crie uma função `formatCurrency()` que receba um valor float e retorne uma string formatada em reais (ex: R$ 1.234,56).

---

## 18. PHP Arrays

Arrays são a estrutura de dados mais **versátil** do PHP. Diferente de linguagens como Java ou C#, arrays em PHP combinam listas (indexadas por inteiro) e mapas/dicionários (indexados por strings) em uma única estrutura. Podem funcionar como listas, filas, pilhas e tabelas hash. Arrays são **ordenados** — mantêm a ordem de inserção.

### Criação de arrays

```php
<?php
declare(strict_types=1);

// Array indexado (lista) — chaves são inteiros automáticos: 0, 1, 2
$colors = ['vermelho', 'azul', 'verde'];
echo $colors[0] . PHP_EOL;  // vermelho

// Array associativo (mapa chave => valor) — chaves são strings
$student = [
    'name' => 'Carlos Souza',
    'age' => 22,
    'course' => 'Engenharia',
];
echo $student['name'] . PHP_EOL;  // Carlos Souza

// Array multidimensional — array de arrays
// Acesso: $matrix[linha][coluna]
$matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
];

echo $matrix[1][2] . PHP_EOL; // 6 (linha 1, coluna 2)
```

### array_first() e array_last() (PHP 8.5)

```php
<?php
declare(strict_types=1);

$fruits = ['Maçã', 'Banana', 'Laranja', 'Uva'];

// LEGADO - PHP < 8.5
// $first = reset($fruits);     // Modifica o ponteiro interno!
// $last = end($fruits);        // Modifica o ponteiro interno!
// $first = $fruits[0];         // Falha se o array for vazio

// ✅ MODERNO - PHP 8.5 — funções dedicadas, seguras e sem efeitos colaterais
$first = array_first($fruits);
$last = array_last($fruits);

echo "Primeiro: {$first}" . PHP_EOL; // Maçã
echo "Último: {$last}" . PHP_EOL;    // Uva

// Retorna null para arrays vazios (sem erro!)
$emptyArray = [];
$result = array_first($emptyArray); // null
var_dump($result);
```

### Funções essenciais de array

O PHP oferece mais de **80 funções** para manipular arrays. Estas são as mais usadas no dia a dia. Note que `sort()` modifica o array original (mutação), enquanto `array_filter`, `array_map` e `array_reduce` **retornam novos arrays** sem alterar o original:

```php
<?php
declare(strict_types=1);

$numbers = [5, 3, 8, 1, 9, 2, 7];

// Ordenação (⚠️ modifica o array original!)
sort($numbers);           // [1, 2, 3, 5, 7, 8, 9]
rsort($numbers);          // [9, 8, 7, 5, 3, 2, 1]

// Busca — ✅ sempre use strict: true para evitar surpresas com ==
$found = in_array(5, $numbers, strict: true);  // true/false
$key = array_search(5, $numbers, strict: true); // índice ou false

// Filtrar — mantém apenas os que satisfazem a condição
$bigNumbers = array_filter(
    $numbers,
    fn(int $n): bool => $n > 5,
);

// Transformar — aplica função a CADA elemento
$squared = array_map(
    fn(int $n): int => $n ** 2,
    $numbers,
);

// Reduzir — condensa o array em um único valor
// $carry acumula o resultado, começando em 0
$sum = array_reduce(
    $numbers,
    fn(int $carry, int $n): int => $carry + $n,
    0,  // valor inicial do $carry
);

echo "Soma: {$sum}" . PHP_EOL;
```

### Spread operator e destructuring

```php
<?php
declare(strict_types=1);

// Spread operator — desempacotar arrays
$base = [1, 2, 3];
$extended = [0, ...$base, 4, 5]; // [0, 1, 2, 3, 4, 5]

// Funciona em argumentos de funções
function sumAll(int ...$numbers): int
{
    return array_sum($numbers);
}
echo sumAll(...$extended) . PHP_EOL; // 15

// Destructuring com list() ou []
$coordinates = [23.5505, -46.6333];
[$latitude, $longitude] = $coordinates;
echo "Lat: {$latitude}, Lng: {$longitude}" . PHP_EOL;

// Destructuring associativo
$person = ['name' => 'Maria', 'age' => 30, 'city' => 'São Paulo'];
['name' => $name, 'city' => $city] = $person;
echo "{$name} mora em {$city}" . PHP_EOL;
```

### ⚠️ Exercício

Crie um array de produtos com nome e preço. Use `array_filter` para filtrar os acima de R$ 50 e `array_map` para aplicar 10% de desconto.

---

## 19. PHP Superglobals

Superglobais são variáveis predefinidas pelo PHP, acessíveis em **qualquer escopo** (dentro de funções, classes, arquivos includos) sem precisar de `global` ou parâmetros. Elas contêm dados sobre a requisição HTTP, ambiente do servidor e estado da sessão.

> ⚠️ **SEGURANÇA:** Superglobais como `$_GET`, `$_POST` e `$_COOKIE` contêm dados enviados pelo usuário. **NUNCA confie neles diretamente** — sempre valide e sanitize antes de usar.

### Lista das superglobais

| Superglobal | Descrição                            |
| ----------- | ------------------------------------ |
| `$_GET`     | Dados da URL (query string)          |
| `$_POST`    | Dados enviados via formulário POST   |
| `$_REQUEST` | Combinação de GET, POST e COOKIE     |
| `$_SERVER`  | Informações do servidor e requisição |
| `$_SESSION` | Dados da sessão do usuário           |
| `$_COOKIE`  | Cookies recebidos                    |
| `$_FILES`   | Arquivos enviados via upload         |
| `$_ENV`     | Variáveis de ambiente                |
| `$GLOBALS`  | Todas as variáveis globais           |

### $_GET e $_POST com segurança

```php
<?php
declare(strict_types=1);

// ⚠️ SEGURANÇA: NUNCA confie em dados do usuário!
// Sempre valide e sanitize

// Recebendo dados GET com validação
$page = filter_input(INPUT_GET, 'page', FILTER_VALIDATE_INT) ?: 1;

// Recebendo dados POST com sanitização
$userName = filter_input(INPUT_POST, 'name', FILTER_SANITIZE_SPECIAL_CHARS) ?? '';

// Escapar para exibição HTML (previne XSS)
echo htmlspecialchars($userName, ENT_QUOTES, 'UTF-8');
```

### $_SERVER

```php
<?php
declare(strict_types=1);

// Informações úteis do servidor
echo $_SERVER['REQUEST_METHOD'] . PHP_EOL;  // GET, POST, etc.
echo $_SERVER['REQUEST_URI'] . PHP_EOL;     // URL requisitada
echo $_SERVER['HTTP_HOST'] . PHP_EOL;       // Domínio
echo $_SERVER['REMOTE_ADDR'] . PHP_EOL;     // IP do cliente
echo $_SERVER['HTTP_USER_AGENT'] . PHP_EOL; // Navegador
echo $_SERVER['DOCUMENT_ROOT'] . PHP_EOL;   // Raiz do servidor
```

### $_SESSION — gestão segura

```php
<?php
declare(strict_types=1);

// Configuração segura ANTES de iniciar a sessão
ini_set('session.cookie_httponly', '1');   // Impede acesso via JavaScript
ini_set('session.cookie_secure', '1');     // Apenas HTTPS
ini_set('session.use_strict_mode', '1');   // Rejeita IDs desconhecidos

session_start();

// Armazenar dados na sessão
$_SESSION['user_id'] = 42;
$_SESSION['user_name'] = 'Ana';

// Após login, SEMPRE regenere o ID da sessão (previne Session Fixation)
session_regenerate_id(delete_old_session: true);

// Verificar se existe
if (isset($_SESSION['user_id'])) {
    echo "Usuário logado: {$_SESSION['user_name']}" . PHP_EOL;
}

// Destruir sessão (logout)
function destroySession(): void
{
    $_SESSION = [];
    if (ini_get('session.use_cookies')) {
        $params = session_get_cookie_params();
        setcookie(
            session_name(),
            '',
            time() - 42000,
            $params['path'],
            $params['domain'],
            $params['secure'],
            $params['httponly'],
        );
    }
    session_destroy();
}
```

### ⚠️ Exercício

Crie um formulário de login simples com `$_POST` e `$_SESSION` que valide credenciais e mantenha o estado de autenticação.

---

## 20. PHP RegEx

Expressões regulares (RegEx) são **padrões de texto** usados para buscar, validar e manipular strings. São extremamente poderosas, mas podem ser difíceis de ler. O PHP usa a biblioteca **PCRE2** (Perl Compatible Regular Expressions), uma das implementações mais completas disponíveis.

Use regex quando funções simples como `str_contains()`, `str_starts_with()` ou `filter_var()` não forem suficientes. Para validações comuns (email, URL, IP), prefira `filter_var()` que é mais seguro e legível.

### Sintaxe básica de padrões

```
/padrão/modificadores
```

### Metacaracteres principais

| Caractere | Significado                      | Exemplo                     |
| --------- | -------------------------------- | --------------------------- |
| `.`       | Qualquer caractere (exceto `\n`) | `/.at/` → cat, bat          |
| `^`       | Início da string                 | `/^PHP/` → "PHP é legal"    |
| `$`       | Fim da string                    | `/legal$/` → "PHP é legal"  |
| `*`       | Zero ou mais repetições          | `/ab*c/` → ac, abc, abbc    |
| `+`       | Uma ou mais repetições           | `/ab+c/` → abc, abbc        |
| `?`       | Zero ou uma repetição            | `/colou?r/` → color, colour |
| `\d`      | Dígito (0-9)                     | `/\d{3}/` → 123             |
| `\w`      | Caractere de palavra             | `/\w+/` → abc_123           |
| `\s`      | Espaço em branco                 | `/\s+/` → espaço, tab       |
| `[abc]`   | Qualquer um dos caracteres       | `/[aeiou]/` → vogais        |
| `(...)`   | Grupo de captura                 | `/(php)/i` → PHP            |
| `{n,m}`   | Entre n e m repetições           | `/\d{2,4}/` → 12, 123, 1234 |

### Modificadores

| Mod. | Nome             | Descrição                    |
| ---- | ---------------- | ---------------------------- |
| `i`  | Case-insensitive | Ignora maiúsculas/minúsculas |
| `m`  | Multiline        | `^` e `$` por linha          |
| `s`  | Dotall           | `.` inclui `\n`              |
| `u`  | Unicode          | Suporte a UTF-8              |

### Exemplos de validação

```php
<?php
declare(strict_types=1);

// Validar email simples
$email = 'usuario@exemplo.com';
$isValidEmail = preg_match('/^[\w.+-]+@[\w-]+\.[\w.]+$/u', $email) === 1;
echo "Email válido: " . ($isValidEmail ? 'Sim' : 'Não') . PHP_EOL;

// ✅ Preferível: use filter_var() para validação de email
$isValidEmail2 = filter_var($email, FILTER_VALIDATE_EMAIL) !== false;
echo "Email válido (filter_var): " . ($isValidEmail2 ? 'Sim' : 'Não') . PHP_EOL;

// Validar CPF (formato)
$cpf = '123.456.789-00';
$isValidCpf = preg_match('/^\d{3}\.\d{3}\.\d{3}-\d{2}$/', $cpf) === 1;
echo "CPF formato válido: " . ($isValidCpf ? 'Sim' : 'Não') . PHP_EOL;

// Validar telefone brasileiro
$phone = '(11) 99999-8888';
$isValidPhone = preg_match('/^\(\d{2}\)\s?\d{4,5}-\d{4}$/', $phone) === 1;
echo "Telefone válido: " . ($isValidPhone ? 'Sim' : 'Não') . PHP_EOL;

// Validar senha forte
$password = 'Senh@F0rte!';
$isStrongPassword = preg_match(
    '/^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[\W_]).{8,}$/',
    $password,
) === 1;
echo "Senha forte: " . ($isStrongPassword ? 'Sim' : 'Não') . PHP_EOL;
```

### ⚠️ Exercício

Crie uma função que valide um CEP brasileiro no formato `12345-678` usando regex.

---

## 21. PHP RegEx Functions

O PHP oferece um conjunto completo de funções para trabalhar com expressões regulares. Todas começam com o prefixo `preg_` (Perl Regular Expression). As quatro principais são:

- `preg_match()` — busca a **primeira** correspondência
- `preg_match_all()` — busca **todas** as correspondências
- `preg_replace()` — **substitui** com base em padrão
- `preg_split()` — **divide** string por padrão

### preg_match() — primeira correspondência

Retorna `1` se encontrou, `0` se não, e `false` em caso de erro. O terceiro parâmetro `$matches` recebe os resultados: `[0]` é o match completo, `[1]` em diante são os **grupos de captura** `()`:

```php
<?php
declare(strict_types=1);

$text = 'O PHP 8.5 foi lançado em 2025';

// (\d+\.\d+) é um grupo de captura — captura a versão
if (preg_match('/PHP\s(\d+\.\d+)/', $text, $matches)) {
    echo "Versão encontrada: {$matches[1]}" . PHP_EOL; // 8.5
    echo "Match completo: {$matches[0]}" . PHP_EOL;    // PHP 8.5
}

// Named groups — grupos nomeados com (?P<nome>...) tornam o código mais legível
if (preg_match('/(?P<language>PHP)\s(?P<version>\d+\.\d+)/', $text, $matches)) {
    echo "Linguagem: {$matches['language']}" . PHP_EOL; // PHP
    echo "Versão: {$matches['version']}" . PHP_EOL;     // 8.5
}
```

### preg_match_all() — todas as correspondências

```php
<?php
declare(strict_types=1);

$html = '<a href="https://php.net">PHP</a> e <a href="https://laravel.com">Laravel</a>';

// Extrair todos os URLs
$count = preg_match_all('/href="([^"]+)"/', $html, $matches);
echo "URLs encontradas: {$count}" . PHP_EOL;

foreach ($matches[1] as $url) {
    echo "URL: {$url}" . PHP_EOL;
}
// URL: https://php.net
// URL: https://laravel.com
```

### preg_replace() — substituição

```php
<?php
declare(strict_types=1);

// Substituição simples
$phone = '11999998888';
$formatted = preg_replace('/(\d{2})(\d{5})(\d{4})/', '($1) $2-$3', $phone);
echo $formatted . PHP_EOL; // (11) 99999-8888

// Substituição com callback
$text = 'preço: 100 reais e 50 centavos';
$result = preg_replace_callback(
    '/\d+/',
    fn(array $matches): string => (string) ((int) $matches[0] * 2),
    $text,
);
echo $result . PHP_EOL; // preço: 200 reais e 100 centavos
```

### preg_split() — dividir por padrão

```php
<?php
declare(strict_types=1);

// Dividir por múltiplos separadores
$text = 'PHP,JavaScript;Python|TypeScript Go';
$languages = preg_split('/[,;|\s]+/', $text);

foreach ($languages as $language) {
    echo "- {$language}" . PHP_EOL;
}
```

### Tratamento de erros em regex

```php
<?php
declare(strict_types=1);

// Sempre verifique erros de regex
$result = @preg_match('/padrão(inválido/', 'texto');

if ($result === false) {
    $error = match (preg_last_error()) {
        PREG_NO_ERROR             => 'Sem erro',
        PREG_INTERNAL_ERROR       => 'Erro interno',
        PREG_BACKTRACK_LIMIT_ERROR => 'Limite de backtrack excedido',
        PREG_RECURSION_LIMIT_ERROR => 'Limite de recursão excedido',
        PREG_BAD_UTF8_ERROR       => 'UTF-8 inválido',
        default                   => 'Erro desconhecido',
    };
    echo "Erro de regex: {$error}" . PHP_EOL;
}
```

### Exemplo prático — extrator de dados

```php
<?php
declare(strict_types=1);

/**
 * Extrai todos os endereços de email de um texto
 *
 * @param string $text Texto para buscar emails
 * @return array<string> Lista de emails encontrados
 */
function extractEmails(string $text): array
{
    preg_match_all(
        '/[\w.+-]+@[\w-]+\.[\w.]+/u',
        $text,
        $matches,
    );
    return $matches[0];
}

$document = 'Contatos: ana@email.com, joao.silva@empresa.com.br e suporte@site.org';
$emails = extractEmails($document);

foreach ($emails as $email) {
    echo "✉️ {$email}" . PHP_EOL;
}
```

### ⚠️ Exercício

Crie uma função `sanitizeHtml()` que use `preg_replace()` para remover todas as tags HTML de um texto, mantendo apenas o conteúdo.

---

# Parte II: Manipulação de Dados

---

## 22. Datas e Horas

Manipular datas e horas é uma das tarefas mais comuns — e mais traiçoeiras — no desenvolvimento web. Cálculos de prazos, fusos horários, horário de verão e formatação para diferentes locais são fontes constantes de bugs sutis.

O PHP oferece classes robustas para trabalhar com datas: `DateTime` (mutável) e `DateTimeImmutable` (imutável). No PHP moderno, **prefira sempre `DateTimeImmutable`** para evitar bugs por mutação acidental. Neste capítulo, você aprenderá desde a formatação básica até cálculos avançados com fusos horários e formatação internacionalizada.

### 22.1 Obtendo data e hora atual

A função `time()` retorna o **timestamp Unix** — o número de segundos decorridos desde 1º de janeiro de 1970 (UTC). Já a função `date()` converte esse timestamp em uma string legível usando **símbolos de formatação**. Essa dupla é a base para qualquer operação com datas no PHP:

```php
<?php

declare(strict_types=1);

// Timestamp Unix — segundos desde 01/01/1970 00:00:00 UTC
$timestamp = time();
echo $timestamp . PHP_EOL; // Ex: 1739138400

// Função date() — formata timestamp como string legível
echo date('Y-m-d') . PHP_EOL;       // 2026-02-09 (ISO 8601)
echo date('d/m/Y') . PHP_EOL;       // 09/02/2026 (formato BR)
echo date('H:i:s') . PHP_EOL;       // 14:30:45
echo date('Y-m-d H:i:s') . PHP_EOL; // 2026-02-09 14:30:45

// Componentes individuais
echo date('Y') . PHP_EOL; // 2026 — ano (4 dígitos)
echo date('m') . PHP_EOL; // 02   — mês (com zero à esquerda)
echo date('d') . PHP_EOL; // 09   — dia (com zero à esquerda)
echo date('H') . PHP_EOL; // 14   — hora (formato 24h)
echo date('i') . PHP_EOL; // 30   — minutos
echo date('s') . PHP_EOL; // 45   — segundos
echo date('N') . PHP_EOL; // 7    — dia da semana (1=seg, 7=dom)
```

### 22.2 Tabela de formatação

A tabela abaixo reúne os **símbolos de formatação** mais utilizados com `date()` e `DateTimeImmutable::format()`. Memorize os mais comuns (`Y`, `m`, `d`, `H`, `i`, `s`) — você os usará constantemente:

| Símbolo | Descrição                    | Exemplo    |
| ------- | ---------------------------- | ---------- |
| `Y`     | Ano (4 dígitos)              | 2026       |
| `y`     | Ano (2 dígitos)              | 26         |
| `m`     | Mês (com zero)               | 02         |
| `n`     | Mês (sem zero)               | 2          |
| `M`     | Mês abreviado                | Feb        |
| `F`     | Mês completo                 | February   |
| `d`     | Dia (com zero)               | 09         |
| `j`     | Dia (sem zero)               | 9          |
| `D`     | Dia da semana (abreviado)    | Mon        |
| `l`     | Dia da semana (completo)     | Monday     |
| `N`     | Dia da semana (1=seg, 7=dom) | 1          |
| `H`     | Hora 24h (com zero)          | 14         |
| `h`     | Hora 12h (com zero)          | 02         |
| `i`     | Minutos (com zero)           | 30         |
| `s`     | Segundos (com zero)          | 45         |
| `A`     | AM/PM maiúsculo              | PM         |
| `U`     | Timestamp Unix               | 1739138400 |

### 22.3 DateTimeImmutable — a abordagem moderna

`DateTimeImmutable` é a classe recomendada para manipulação de datas no PHP moderno. A principal vantagem é que **toda modificação retorna um novo objeto**, mantendo o original intacto. Isso elimina uma classe inteira de bugs causados por mutação acidental — especialmente quando datas são passadas entre funções ou armazenadas em variáveis compartilhadas.

Você pode criar instâncias com a data atual, com strings descritivas (como `'2026-12-25'` ou `'+1 week'`), e usar métodos como `modify()`, `add()` e `sub()` para cálculos:

```php
<?php

declare(strict_types=1);

// ✅ RECOMENDADO: DateTimeImmutable — nunca modifica o objeto original
$now = new DateTimeImmutable();
echo $now->format('d/m/Y H:i:s') . PHP_EOL;

// Criar com data específica
$christmas = new DateTimeImmutable('2026-12-25');
echo $christmas->format('d/m/Y') . PHP_EOL; // 25/12/2026

// Criar com hora específica
$meeting = new DateTimeImmutable('2026-02-10 15:30:00');
echo $meeting->format('d/m/Y \à\s H:i') . PHP_EOL; // 10/02/2026 às 15:30

// Modificar retorna NOVO objeto (original intacto!)
$today = new DateTimeImmutable('2026-02-09');
$tomorrow = $today->modify('+1 day');
$nextMonth = $today->modify('+1 month');
$nextYear = $today->modify('+1 year');

echo $today->format('d/m/Y') . PHP_EOL;       // 09/02/2026 (original!)
echo $tomorrow->format('d/m/Y') . PHP_EOL;    // 10/02/2026
echo $nextMonth->format('d/m/Y') . PHP_EOL;   // 09/03/2026
echo $nextYear->format('d/m/Y') . PHP_EOL;    // 09/02/2027

// Usando DateInterval para modificações precisas
$date = new DateTimeImmutable('2026-02-09');
$plusSevenDays = $date->add(new DateInterval('P7D'));      // +7 dias
$minusOneMonth = $date->sub(new DateInterval('P1M'));      // -1 mês
$plusOneHour = $date->add(new DateInterval('PT1H'));       // +1 hora
$complexDate = $date->add(new DateInterval('P1Y2M3DT4H')); // +1 ano, 2 meses, 3 dias, 4 horas

echo $plusSevenDays->format('d/m/Y') . PHP_EOL;  // 16/02/2026
echo $minusOneMonth->format('d/m/Y') . PHP_EOL;  // 09/01/2026
```

### 22.4 Por que evitar DateTime (mutável)?

A classe `DateTime` é **mutável**: quando você chama `modify()`, o próprio objeto é alterado. Isso gera bugs extremamente sutis, pois em PHP, objetos são passados **por referência** — ou seja, atribuir `$date2 = $date1` não cria uma cópia, mas sim duas variáveis apontando para o **mesmo** objeto. Veja o problema:

```php
<?php

declare(strict_types=1);

// ⚠️ PROBLEMA com DateTime (mutável) — bug sutil
$date1 = new DateTime('2026-02-09');
$date2 = $date1; // Parece uma cópia, mas é REFERÊNCIA ao mesmo objeto!
$date2->modify('+1 day');

echo $date1->format('d/m/Y') . PHP_EOL; // 10/02/2026 — MUDOU sem querer!
echo $date2->format('d/m/Y') . PHP_EOL; // 10/02/2026

// ✅ SOLUÇÃO com DateTimeImmutable — previsível e seguro
$date1 = new DateTimeImmutable('2026-02-09');
$date2 = $date1->modify('+1 day'); // Cria NOVO objeto

echo $date1->format('d/m/Y') . PHP_EOL; // 09/02/2026 — intacto ✅
echo $date2->format('d/m/Y') . PHP_EOL; // 10/02/2026 — novo objeto
```

### 22.5 Cálculos com datas

O método `diff()` retorna um objeto `DateInterval` com a diferença entre duas datas, decomposta em anos, meses, dias e horas. A propriedade `->days` fornece o total absoluto de dias. Cálculos comuns incluem idade, prazos em dias úteis e verificação de fins de semana:

```php
<?php

declare(strict_types=1);

// Diferença entre datas com DateInterval
$startDate = new DateTimeImmutable('2026-01-01');
$endDate = new DateTimeImmutable('2026-12-31');

$difference = $startDate->diff($endDate);

echo $difference->days . ' dias totais' . PHP_EOL;     // 364
echo $difference->m . ' meses' . PHP_EOL;               // 11
echo $difference->format('%y anos, %m meses e %d dias') . PHP_EOL;

// Calcular idade — função prática
function calculateAge(string $birthDate): int
{
    $birth = new DateTimeImmutable($birthDate);
    $today = new DateTimeImmutable();

    return $birth->diff($today)->y;
}

echo 'Idade: ' . calculateAge('1998-05-15') . ' anos' . PHP_EOL;

// Verificar se é final de semana
function isWeekend(DateTimeImmutable $date): bool
{
    // format('N') retorna 1=segunda ... 7=domingo
    return (int) $date->format('N') >= 6;
}

$today = new DateTimeImmutable();
echo isWeekend($today) ? 'Final de semana! 🎉' : 'Dia útil 💼';
echo PHP_EOL;

// Adicionar dias úteis (pula fins de semana)
function addBusinessDays(DateTimeImmutable $date, int $days): DateTimeImmutable
{
    $result = $date;
    $added = 0;

    while ($added < $days) {
        $result = $result->modify('+1 day');

        if (!isWeekend($result)) {
            $added++;
        }
    }

    return $result;
}

$deadline = addBusinessDays(new DateTimeImmutable('2026-02-09'), 5);
echo 'Prazo: ' . $deadline->format('d/m/Y') . PHP_EOL;
```

### 22.6 Fusos horários

Fusos horários são essenciais em aplicações que atendem usuários em diferentes regiões. O PHP usa a base de dados **IANA** (como `America/Sao_Paulo`, `Asia/Tokyo`) para gerenciar fusos e horário de verão automaticamente. A função `date_default_timezone_set()` define o fuso padrão do script, enquanto `DateTimeZone` permite conversões entre fusos:

```php
<?php

declare(strict_types=1);

// Definir fuso horário padrão do script
date_default_timezone_set('America/Sao_Paulo');

// DateTimeImmutable com fuso horário específico
$sp = new DateTimeImmutable('now', new DateTimeZone('America/Sao_Paulo'));
$ny = new DateTimeImmutable('now', new DateTimeZone('America/New_York'));
$tokyo = new DateTimeImmutable('now', new DateTimeZone('Asia/Tokyo'));
$london = new DateTimeImmutable('now', new DateTimeZone('Europe/London'));

echo 'São Paulo: ' . $sp->format('H:i (P)') . PHP_EOL;
echo 'Nova York: ' . $ny->format('H:i (P)') . PHP_EOL;
echo 'Tóquio:    ' . $tokyo->format('H:i (P)') . PHP_EOL;
echo 'Londres:   ' . $london->format('H:i (P)') . PHP_EOL;

// Converter entre fusos — o instante no tempo é o mesmo,
// apenas a representação muda
$spTime = new DateTimeImmutable(
    '2026-02-09 15:00:00',
    new DateTimeZone('America/Sao_Paulo'),
);

$londonTime = $spTime->setTimezone(new DateTimeZone('Europe/London'));
echo 'SP: ' . $spTime->format('H:i') . PHP_EOL;       // 15:00
echo 'Londres: ' . $londonTime->format('H:i') . PHP_EOL; // 18:00
```

### 22.7 Formatação localizada com IntlDateFormatter

A classe `IntlDateFormatter` (parte da extensão `intl`) formata datas em **qualquer idioma** sem tradução manual. Ela utiliza os dados do ICU (International Components for Unicode) para gerar nomes de meses e dias da semana automaticamente em português, inglês, japonês ou qualquer outro idioma suportado:

```php
<?php

declare(strict_types=1);

// IntlDateFormatter — datas em português brasileiro nativo
$date = new DateTimeImmutable('2026-02-09 15:30:00');

// Formato completo em pt-BR
$fullFormatter = new IntlDateFormatter(
    locale: 'pt_BR',
    dateType: IntlDateFormatter::FULL,
    timeType: IntlDateFormatter::SHORT,
    timezone: 'America/Sao_Paulo',
);
echo $fullFormatter->format($date) . PHP_EOL;
// segunda-feira, 9 de fevereiro de 2026 15:30

// Formato curto
$shortFormatter = new IntlDateFormatter(
    locale: 'pt_BR',
    dateType: IntlDateFormatter::SHORT,
    timeType: IntlDateFormatter::NONE,
);
echo $shortFormatter->format($date) . PHP_EOL; // 09/02/2026

// Padrão customizado
$customFormatter = new IntlDateFormatter(
    locale: 'pt_BR',
    dateType: IntlDateFormatter::NONE,
    timeType: IntlDateFormatter::NONE,
    pattern: "EEEE, d 'de' MMMM 'de' yyyy",
);
echo $customFormatter->format($date) . PHP_EOL;
// segunda-feira, 9 de fevereiro de 2026
```

### 📝 Exercícios do Capítulo 22

1. Calcule quantos dias faltam para o próximo Natal usando `DateTimeImmutable`
2. Crie uma função `getDayNamePtBr()` que retorne o nome do dia da semana em português
3. Calcule quantas semanas completas existem entre duas datas
4. Verifique se uma data é feriado nacional (use array com feriados fixos do Brasil)
5. Crie um calendário simples que exiba os dias de um mês em formato de grade

---

## 23. Arquivos e Diretórios

Trabalhar com o sistema de arquivos é essencial para logs, uploads, configurações, cache e integrações com sistemas externos. O PHP oferece funções completas que vão desde leitura simples até manipulação de diretórios recursivos.

**Segurança é fundamental** — nunca confie em nomes de arquivos vindos do usuário. Sempre valide, sanitize e use caminhos absolutos controlados pelo servidor.

### 23.1 Leitura de arquivos

O PHP oferece três abordagens principais para leitura: `file_get_contents()` carrega o arquivo inteiro como string (ideal para arquivos pequenos), `file()` retorna um array com uma linha por elemento, e `fopen()`/`fgets()` lê linha a linha sem carregar tudo na memória (ideal para arquivos grandes):

```php
<?php

declare(strict_types=1);

// file_get_contents() — lê o arquivo INTEIRO como string
// ✅ Ideal para arquivos pequenos/médios
$content = file_get_contents('config.txt');
echo $content;

// Verificar se o arquivo existe ANTES de ler
if (!file_exists('config.txt')) {
    throw new RuntimeException('Arquivo config.txt não encontrado.');
}

// file() — lê como array (uma linha por elemento)
$lines = file('log.txt', FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);

foreach ($lines as $lineNumber => $line) {
    echo "Linha {$lineNumber}: {$line}" . PHP_EOL;
}

// fopen/fgets — leitura linha a linha (econômico para arquivos grandes)
// ✅ Não carrega o arquivo inteiro na memória
$handle = fopen('largefile.txt', 'r');

if ($handle !== false) {
    while (($line = fgets($handle)) !== false) {
        // Processa uma linha por vez — eficiente em memória
        echo trim($line) . PHP_EOL;
    }

    fclose($handle); // ⚠️ Sempre feche o arquivo!
}

// fread() — lê quantidade específica de bytes
$handle = fopen('binary.dat', 'r');
$header = fread($handle, 128); // Primeiros 128 bytes
fclose($handle);
```

### 23.2 Escrita de arquivos

A escrita segue a mesma lógica: `file_put_contents()` para operações simples e `fopen()`/`fwrite()` para controle fino. A flag `FILE_APPEND` adiciona ao final sem sobrescrever, e `LOCK_EX` previne conflitos em ambientes concorrentes:

```php
<?php

declare(strict_types=1);

// file_put_contents() — escreve de uma vez (sobrescreve)
file_put_contents('output.txt', 'Novo conteúdo');

// Adicionar ao final (append) sem sobrescrever
file_put_contents('output.txt', "\nLinha adicional", FILE_APPEND);

// fopen/fwrite — escrita com controle fino
$handle = fopen('report.txt', 'w'); // 'w' cria ou sobrescreve

if ($handle !== false) {
    fwrite($handle, "Relatório gerado em " . date('Y-m-d H:i:s') . "\n");
    fwrite($handle, "=================================\n");
    fwrite($handle, "Total de itens processados: 42\n");
    fclose($handle);
}

// Modos de abertura de arquivos:
// 'r'  — Leitura apenas (ponteiro no início)
// 'w'  — Escrita apenas (cria/sobrescreve, ponteiro no início)
// 'a'  — Append (cria se não existe, ponteiro no final)
// 'r+' — Leitura e escrita (ponteiro no início)
// 'w+' — Leitura e escrita (cria/sobrescreve)
// 'a+' — Leitura e append

// Exemplo prático: Logger simples
function writeLog(string $level, string $message): void
{
    $timestamp = date('Y-m-d H:i:s');
    $entry = "[{$timestamp}] [{$level}] {$message}" . PHP_EOL;

    file_put_contents('app.log', $entry, FILE_APPEND | LOCK_EX);
    // LOCK_EX evita conflitos em escrita simultânea
}

writeLog('INFO', 'Aplicação iniciada');
writeLog('WARNING', 'Memória acima de 80%');
writeLog('ERROR', 'Falha na conexão com banco de dados');
```

### 23.3 Informações sobre arquivos

Antes de operar sobre arquivos, é boa prática verificar sua existência, tipo e permissões. Funções como `file_exists()`, `is_file()`, `is_readable()` e `pathinfo()` fornecem essas informações de forma segura:

```php
<?php

declare(strict_types=1);

$filepath = 'documento.pdf';

// Verificações booleanas
var_dump(file_exists($filepath));   // Existe?
var_dump(is_file($filepath));       // É um arquivo?
var_dump(is_dir($filepath));        // É um diretório?
var_dump(is_readable($filepath));   // Pode ler?
var_dump(is_writable($filepath));   // Pode escrever?

// Informações detalhadas
echo filesize($filepath) . ' bytes' . PHP_EOL; // Tamanho

// Data de última modificação
$modified = filemtime($filepath);
$modifiedDate = new DateTimeImmutable('@' . $modified);
echo 'Modificado em: ' . $modifiedDate->format('d/m/Y H:i:s') . PHP_EOL;

// Decompor caminho com pathinfo()
$info = pathinfo('/var/www/html/uploads/foto.jpg');
echo $info['dirname'] . PHP_EOL;    // /var/www/html/uploads
echo $info['basename'] . PHP_EOL;   // foto.jpg
echo $info['extension'] . PHP_EOL;  // jpg
echo $info['filename'] . PHP_EOL;   // foto

// Atalho para pegar apenas a extensão
function getExtension(string $filepath): string
{
    return strtolower(pathinfo($filepath, PATHINFO_EXTENSION));
}

echo getExtension('Relatorio_Final.PDF') . PHP_EOL; // pdf
```

### 23.4 Manipulação de arquivos e diretórios

Além de ler e escrever, frequentemente precisamos copiar, mover, renomear e deletar arquivos, além de criar e listar diretórios. A função `rename()` serve tanto para renomear quanto para mover, e `mkdir()` com `recursive: true` cria toda a hierarquia de uma vez:

```php
<?php

declare(strict_types=1);

// Copiar arquivo
if (copy('original.txt', 'backup/original_backup.txt')) {
    echo 'Arquivo copiado com sucesso' . PHP_EOL;
}

// Renomear / mover arquivo (mesma função)
rename('antigo.txt', 'novo.txt');             // Renomear
rename('arquivo.txt', 'pasta/arquivo.txt');   // Mover

// Deletar arquivo com verificação
if (file_exists('temporario.txt')) {
    unlink('temporario.txt');
    echo 'Arquivo removido' . PHP_EOL;
}

// Criar diretório (com recursão para subpastas)
mkdir('storage/uploads/images', recursive: true);

// Remover diretório vazio
rmdir('pasta_vazia');

// Listar conteúdo de um diretório
$items = scandir('.');

foreach ($items as $item) {
    if ($item === '.' || $item === '..') {
        continue;
    }

    $type = is_dir($item) ? '📁' : '📄';
    echo "{$type} {$item}" . PHP_EOL;
}

// Listar recursivamente todos os arquivos
function listFilesRecursive(string $directory): array
{
    $result = [];
    $items = scandir($directory);

    foreach ($items as $item) {
        if ($item === '.' || $item === '..') {
            continue;
        }

        $path = $directory . DIRECTORY_SEPARATOR . $item;

        if (is_dir($path)) {
            $result = [...$result, ...listFilesRecursive($path)];
        } else {
            $result[] = $path;
        }
    }

    return $result;
}

$allFiles = listFilesRecursive('.');
print_r($allFiles);
```

### 23.5 Upload seguro de arquivos

⚠️ Upload de arquivos é um dos **pontos mais críticos de segurança** em aplicações web. Nunca confie no nome original do arquivo, na extensão informada pelo navegador, nem no Content-Type do request. Sempre valide o tipo MIME real com `finfo_file()`, gere nomes aleatórios e use `move_uploaded_file()` (que verifica se o arquivo realmente veio de um upload HTTP):

```php
<?php

declare(strict_types=1);

// Formulário HTML necessário (em arquivo separado):
// <form method="POST" enctype="multipart/form-data">
//     <input type="file" name="upload">
//     <button type="submit">Enviar</button>
// </form>

if ($_SERVER['REQUEST_METHOD'] === 'POST' && isset($_FILES['upload'])) {
    $file = $_FILES['upload'];

    // 1. Verificar se houve erro no upload
    if ($file['error'] !== UPLOAD_ERR_OK) {
        $errorMessages = [
            UPLOAD_ERR_INI_SIZE   => 'Arquivo excede o limite do servidor',
            UPLOAD_ERR_FORM_SIZE  => 'Arquivo excede o limite do formulário',
            UPLOAD_ERR_PARTIAL    => 'Upload incompleto',
            UPLOAD_ERR_NO_FILE    => 'Nenhum arquivo enviado',
            UPLOAD_ERR_NO_TMP_DIR => 'Pasta temporária não encontrada',
            UPLOAD_ERR_CANT_WRITE => 'Falha ao gravar arquivo',
        ];

        $message = $errorMessages[$file['error']] ?? 'Erro desconhecido';
        throw new RuntimeException("Erro no upload: {$message}");
    }

    // 2. Validar tamanho (máximo 5MB)
    $maxSize = 5 * 1024 * 1024;
    if ($file['size'] > $maxSize) {
        throw new RuntimeException('Arquivo excede 5MB');
    }

    // 3. Validar tipo REAL do arquivo (não confie na extensão!)
    $finfo = finfo_open(FILEINFO_MIME_TYPE);
    $mimeType = finfo_file($finfo, $file['tmp_name']);
    finfo_close($finfo);

    $allowedTypes = ['image/jpeg', 'image/png', 'image/webp', 'application/pdf'];
    if (!in_array($mimeType, $allowedTypes, true)) {
        throw new RuntimeException("Tipo {$mimeType} não permitido");
    }

    // 4. Gerar nome seguro e único (NUNCA use o nome original!)
    $extension = match ($mimeType) {
        'image/jpeg' => 'jpg',
        'image/png'  => 'png',
        'image/webp' => 'webp',
        'application/pdf' => 'pdf',
        default => throw new RuntimeException('Tipo não mapeado'),
    };

    $safeName = bin2hex(random_bytes(16)) . '.' . $extension;
    $destination = 'uploads/' . $safeName;

    // 5. Mover para destino final
    if (!move_uploaded_file($file['tmp_name'], $destination)) {
        throw new RuntimeException('Falha ao mover arquivo');
    }

    echo "Upload realizado: {$safeName}" . PHP_EOL;
}
```

### 23.6 Trabalhando com CSV

CSV (Comma-Separated Values) é um formato popular para importação/exportação de dados entre sistemas. O PHP oferece `fgetcsv()` e `fputcsv()` que lidam automaticamente com aspas, escapes e separadores. A técnica de combinar `fgetcsv()` com `array_combine()` transforma cada linha em um array associativo usando o cabeçalho como chaves:

```php
<?php

declare(strict_types=1);

// Ler arquivo CSV linha a linha
$handle = fopen('dados.csv', 'r');

if ($handle !== false) {
    // Pular cabeçalho
    $headers = fgetcsv($handle);

    while (($row = fgetcsv($handle)) !== false) {
        // Combinar cabeçalhos com valores
        $record = array_combine($headers, $row);
        echo $record['nome'] . ' — R$ ' . $record['preco'] . PHP_EOL;
    }

    fclose($handle);
}

// Escrever arquivo CSV
$products = [
    ['Nome', 'Preço', 'Estoque'],
    ['Notebook', '2500.00', '10'],
    ['Mouse', '50.00', '100'],
    ['Teclado', '120.00', '45'],
];

$handle = fopen('products.csv', 'w');

foreach ($products as $row) {
    fputcsv($handle, $row);
}

fclose($handle);

// Função utilitária: ler CSV completo como array associativo
function readCsvFile(string $filepath, string $separator = ','): array
{
    if (!file_exists($filepath)) {
        throw new RuntimeException("Arquivo não encontrado: {$filepath}");
    }

    $result = [];
    $handle = fopen($filepath, 'r');
    $headers = fgetcsv($handle, separator: $separator);

    while (($row = fgetcsv($handle, separator: $separator)) !== false) {
        if (count($row) === count($headers)) {
            $result[] = array_combine($headers, $row);
        }
    }

    fclose($handle);
    return $result;
}

$users = readCsvFile('usuarios.csv');
// [['nome' => 'João', 'idade' => '25', 'cidade' => 'São Paulo'], ...]
```

### 📝 Exercícios do Capítulo 23

1. Crie um contador de visitas que salve o total em um arquivo `.txt`
2. Leia um arquivo de texto e exiba: total de linhas, palavras e caracteres
3. Implemente um sistema de log com níveis (INFO, WARNING, ERROR) e rotação diária
4. Faça backup de todos os arquivos `.txt` de um diretório para uma pasta `backup/`
5. Leia um CSV de produtos e calcule a média de preços e o produto mais caro

---

## 24. JSON e Serialização

JSON (JavaScript Object Notation) é o formato padrão para troca de dados em APIs modernas, configurações e persistência leve. É leve, legível por humanos e suportado nativamente por praticamente todas as linguagens. O PHP oferece suporte nativo completo para codificação e decodificação, com flags poderosas para controlar o comportamento.

### 24.1 Codificando para JSON (encode)

`json_encode()` converte arrays e objetos PHP em strings JSON. Use a flag `JSON_THROW_ON_ERROR` para erros explícitos (em vez de retornos `false` silenciosos), `JSON_UNESCAPED_UNICODE` para preservar acentos, e `JSON_PRETTY_PRINT` para saída legível:

```php
<?php

declare(strict_types=1);

// Array associativo → JSON
$user = [
    'nome' => 'João Silva',
    'idade' => 25,
    'email' => 'joao@example.com',
    'ativo' => true,
    'hobbies' => ['programação', 'música', 'esportes'],
];

// JSON compacto (ideal para transmissão)
$json = json_encode($user);
echo $json . PHP_EOL;
// {"nome":"Jo\u00e3o Silva","idade":25,"email":"joao@example.com",...}

// JSON formatado (ideal para debug e arquivos de config)
$jsonPretty = json_encode($user, JSON_PRETTY_PRINT);
echo $jsonPretty . PHP_EOL;

// Flags mais usadas — podem ser combinadas com |
$jsonBr = json_encode($user,
    JSON_PRETTY_PRINT          // Indentação legível
    | JSON_UNESCAPED_UNICODE   // ✅ Mantém acentos: "João" em vez de "Jo\u00e3o"
    | JSON_UNESCAPED_SLASHES   // ✅ Mantém barras: "/" em vez de "\/"
    | JSON_THROW_ON_ERROR      // ✅ Lança JsonException em vez de retornar false
);
echo $jsonBr . PHP_EOL;
```

### 24.2 Decodificando JSON (decode)

`json_decode()` faz o caminho inverso: converte strings JSON em estruturas PHP. O parâmetro `associative: true` retorna arrays associativos (recomendado na maioria dos casos), enquanto `false` retorna objetos `stdClass`. A partir do PHP 8.3, `json_validate()` permite verificar se uma string é JSON válido **sem decodificá-la** — mais rápido quando você só precisa validar:

```php
<?php

declare(strict_types=1);

$json = '{"nome":"João","idade":25,"email":"joao@example.com"}';

// Decodificar como array associativo (recomendado na maioria dos casos)
$array = json_decode($json, associative: true, flags: JSON_THROW_ON_ERROR);
echo $array['nome'] . PHP_EOL;  // João
echo $array['idade'] . PHP_EOL; // 25

// Decodificar como objeto stdClass
$object = json_decode($json, flags: JSON_THROW_ON_ERROR);
echo $object->nome . PHP_EOL;   // João
echo $object->idade . PHP_EOL;  // 25

// ✅ Tratamento de erros moderno com try/catch
try {
    $invalidJson = '{"nome": "João"';  // JSON malformado
    $result = json_decode($invalidJson, true, flags: JSON_THROW_ON_ERROR);
} catch (JsonException $e) {
    echo 'Erro ao decodificar JSON: ' . $e->getMessage() . PHP_EOL;
    // Erro ao decodificar JSON: Syntax error
}

// ✅ PHP 8.3+: json_validate() — verifica sem decodificar (mais rápido)
$testJson = '{"key": "value"}';
if (json_validate($testJson)) {
    echo 'JSON válido!' . PHP_EOL;
}
```

### 24.3 JSON com arquivos — persistência local

Arquivos JSON funcionam como um "banco de dados" leve para aplicações simples, prototipação e configurações. A combinação de `file_get_contents()` + `json_decode()` para leitura e `json_encode()` + `file_put_contents()` para escrita é um padrão poderoso. O exemplo abaixo inclui uma classe `JsonStorage` reutilizável com operações CRUD completas:

```php
<?php

declare(strict_types=1);

// Salvar dados em arquivo JSON
$products = [
    ['id' => 1, 'nome' => 'Notebook', 'preco' => 2500.00],
    ['id' => 2, 'nome' => 'Mouse', 'preco' => 50.00],
    ['id' => 3, 'nome' => 'Teclado', 'preco' => 120.00],
];

file_put_contents(
    'products.json',
    json_encode($products, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE),
);

// Ler dados de arquivo JSON
$json = file_get_contents('products.json');
$products = json_decode($json, true, flags: JSON_THROW_ON_ERROR);

foreach ($products as $product) {
    echo "{$product['nome']}: R$ " . number_format($product['preco'], 2, ',', '.') . PHP_EOL;
}

// Classe utilitária para JSON como "banco de dados" simples
class JsonStorage
{
    public function __construct(
        private readonly string $filepath,
    ) {
        if (!file_exists($this->filepath)) {
            file_put_contents($this->filepath, '[]');
        }
    }

    public function readAll(): array
    {
        $json = file_get_contents($this->filepath);
        return json_decode($json, true, flags: JSON_THROW_ON_ERROR);
    }

    public function save(array $data): void
    {
        $json = json_encode(
            $data,
            JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE | JSON_THROW_ON_ERROR,
        );
        file_put_contents($this->filepath, $json, LOCK_EX);
    }

    public function append(array $item): void
    {
        $data = $this->readAll();
        $item['id'] = count($data) > 0
            ? max(array_column($data, 'id')) + 1
            : 1;
        $data[] = $item;
        $this->save($data);
    }

    public function findById(int $id): ?array
    {
        $data = $this->readAll();

        foreach ($data as $item) {
            if ($item['id'] === $id) {
                return $item;
            }
        }

        return null;
    }

    public function deleteById(int $id): bool
    {
        $data = $this->readAll();
        $filtered = array_filter($data, fn(array $item): bool => $item['id'] !== $id);

        if (count($filtered) === count($data)) {
            return false; // Não encontrou o ID
        }

        $this->save(array_values($filtered));
        return true;
    }
}

// Uso
$db = new JsonStorage('tasks.json');
$db->append(['titulo' => 'Estudar PHP 8.5', 'concluida' => false]);
$db->append(['titulo' => 'Criar projeto', 'concluida' => false]);

$tasks = $db->readAll();
print_r($tasks);
```

### 24.4 API REST simples com JSON

Com o servidor embutido do PHP (`php -S localhost:8000`), você pode criar APIs REST rapidamente para testes e prototipação. O exemplo abaixo usa `match` para rotear métodos HTTP e a classe `JsonStorage` criada anteriormente como backend:

```php
<?php

declare(strict_types=1);

// API REST básica usando arquivos JSON como storage
// Rode com: php -S localhost:8000 api.php

header('Content-Type: application/json; charset=utf-8');

$method = $_SERVER['REQUEST_METHOD'];
$storage = new JsonStorage('api_data.json'); // Classe do exemplo anterior

try {
    $response = match ($method) {
        'GET' => json_encode($storage->readAll()),

        'POST' => (function () use ($storage): string {
            $input = json_decode(
                file_get_contents('php://input'),
                true,
                flags: JSON_THROW_ON_ERROR,
            );
            $storage->append($input);
            http_response_code(201); // Created
            return json_encode(['success' => true, 'data' => $input]);
        })(),

        'DELETE' => (function () use ($storage): string {
            $id = filter_input(INPUT_GET, 'id', FILTER_VALIDATE_INT);
            if ($id === null || $id === false) {
                http_response_code(400);
                return json_encode(['error' => 'ID inválido']);
            }
            $storage->deleteById($id);
            return json_encode(['success' => true]);
        })(),

        default => (function (): string {
            http_response_code(405); // Method Not Allowed
            return json_encode(['error' => 'Método não suportado']);
        })(),
    };

    echo $response;
} catch (JsonException $e) {
    http_response_code(400);
    echo json_encode(['error' => 'JSON inválido: ' . $e->getMessage()]);
}
```

### 📝 Exercícios do Capítulo 24

1. Crie um sistema de configurações que salve/carregue de um arquivo `config.json`
2. Implemente CRUD completo (Create, Read, Update, Delete) com `JsonStorage`
3. Crie uma função que valide se uma string é JSON válido e retorne o motivo do erro
4. Implemente cache com TTL (tempo de expiração) usando arquivos JSON
5. Crie uma API REST que gerencie uma lista de tarefas (to-do list)

---

# Parte III: Orientação a Objetos

---

## 25. Classes e Objetos

A Programação Orientada a Objetos (OOP) é o paradigma dominante no desenvolvimento PHP profissional. Em vez de funções e variáveis soltas, você organiza o código em **classes** (moldes que definem estrutura e comportamento) e **objetos** (instâncias concretas criadas a partir desses moldes). Frameworks como Laravel, Symfony e até o próprio WordPress moderno são inteiramente baseados em OOP.

Neste capítulo, você aprenderá a criar classes, usar construtores modernos com *property promotion*, implementar lógica de negócio, e entender as palavras-chave `$this`, `self` e `parent`.

### 25.1 Criando sua primeira classe

Uma classe define **propriedades** (dados/estado) e **métodos** (comportamentos/ações). A palavra-chave `$this` dentro de um método refere-se à instância atual do objeto. Cada objeto criado com `new` é independente — alterar um não afeta outros:

```php
<?php

declare(strict_types=1);

// Classe: molde que define propriedades e comportamentos
class Person
{
    // Propriedades (atributos) — definem o ESTADO do objeto
    public string $name;
    public int $age;

    // Método (função da classe) — define o COMPORTAMENTO
    public function introduce(): string
    {
        // $this refere-se à instância atual do objeto
        return "Olá, meu nome é {$this->name} e tenho {$this->age} anos.";
    }

    public function isAdult(): bool
    {
        return $this->age >= 18;
    }
}

// Instanciar (criar) objetos a partir da classe
$person1 = new Person();
$person1->name = 'João';
$person1->age = 25;

$person2 = new Person();
$person2->name = 'Maria';
$person2->age = 30;

echo $person1->introduce() . PHP_EOL;
// Olá, meu nome é João e tenho 25 anos.

echo $person2->introduce() . PHP_EOL;
// Olá, meu nome é Maria e tenho 30 anos.

// Cada objeto é independente — alterar um não afeta o outro
echo $person1->isAdult() ? 'Maior de idade' : 'Menor de idade';
```

### 25.2 Construtor e inicialização

O **construtor** (`__construct`) é executado automaticamente ao criar um objeto com `new`. No PHP 8.0+, o *Constructor Property Promotion* elimina a necessidade de declarar propriedades separadamente e atribuí-las manualmente — reduzindo o boilerplate drasticamente:

```php
<?php

declare(strict_types=1);

// Construtor CLÁSSICO — PHP < 8.0
class ProductClassic
{
    public string $name;
    public float $price;
    public int $stock;

    public function __construct(string $name, float $price, int $stock = 0)
    {
        $this->name = $name;
        $this->price = $price;
        $this->stock = $stock;
    }
}

// ✅ Constructor Property Promotion — PHP 8.0+
// Combina declaração + atribuição em uma linha
class Product
{
    public function __construct(
        public string $name,
        public float $price,
        public int $stock = 0,
    ) {}

    public function getDescription(): string
    {
        $formatted = number_format($this->price, 2, ',', '.');
        return "{$this->name} — R$ {$formatted}";
    }

    public function isAvailable(): bool
    {
        return $this->stock > 0;
    }
}

// Criar objetos com o construtor
$notebook = new Product('Notebook Dell', 2500.00, 10);
$mouse = new Product('Mouse Gamer', 89.90);

echo $notebook->getDescription() . PHP_EOL;
// Notebook Dell — R$ 2.500,00

echo $mouse->isAvailable() ? 'Disponível' : 'Indisponível';
// Indisponível (stock = 0)
```

### 25.3 Métodos com lógica de negócio

Métodos não são apenas getters e setters — eles encapsulam **regras de negócio** que protegem a integridade dos dados. O exemplo abaixo mostra uma conta bancária onde operações como saque e transferência lançam exceções claras quando as regras são violadas:

```php
<?php

declare(strict_types=1);

class BankAccount
{
    public function __construct(
        private readonly string $holder,
        private float $balance = 0.0,
    ) {}

    public function deposit(float $amount): void
    {
        if ($amount <= 0) {
            throw new InvalidArgumentException('Valor de depósito deve ser positivo.');
        }

        $this->balance += $amount;
    }

    public function withdraw(float $amount): void
    {
        if ($amount <= 0) {
            throw new InvalidArgumentException('Valor de saque deve ser positivo.');
        }

        if ($amount > $this->balance) {
            throw new RuntimeException('Saldo insuficiente.');
        }

        $this->balance -= $amount;
    }

    public function transferTo(BankAccount $destination, float $amount): void
    {
        $this->withdraw($amount);       // Lança exceção se não tiver saldo
        $destination->deposit($amount);
    }

    public function getBalance(): float
    {
        return $this->balance;
    }

    public function getStatement(): string
    {
        $formatted = number_format($this->balance, 2, ',', '.');
        return "Titular: {$this->holder} | Saldo: R$ {$formatted}";
    }
}

// Uso
$account1 = new BankAccount('João', 1000.00);
$account2 = new BankAccount('Maria', 500.00);

$account1->deposit(200.00);
echo $account1->getStatement() . PHP_EOL;
// Titular: João | Saldo: R$ 1.200,00

$account1->transferTo($account2, 300.00);
echo $account1->getStatement() . PHP_EOL; // R$ 900,00
echo $account2->getStatement() . PHP_EOL; // R$ 800,00

// Tratamento de erro
try {
    $account1->withdraw(5000.00);
} catch (RuntimeException $e) {
    echo 'Erro: ' . $e->getMessage() . PHP_EOL; // Saldo insuficiente.
}
```

### 25.4 Propriedades e métodos estáticos

Membros **estáticos** (`static`) pertencem à **classe**, não a uma instância específica. São acessados via `NomeClasse::` (sem `new`). Use-os para utilitários puros e contadores compartilhados — mas com moderação, pois dificultam testes:

```php
<?php

declare(strict_types=1);

class MathHelper
{
    // Constante da classe — acessível sem instanciar
    public const PI = 3.14159265358979;

    // Propriedade estática — compartilhada entre TODAS as instâncias
    private static int $callCount = 0;

    // Método estático — chamável sem new
    public static function add(float $a, float $b): float
    {
        self::$callCount++;
        return $a + $b;
    }

    public static function circleArea(float $radius): float
    {
        if ($radius < 0) {
            throw new InvalidArgumentException('Raio deve ser positivo.');
        }

        self::$callCount++;
        return self::PI * ($radius ** 2);
    }

    public static function getCallCount(): int
    {
        return self::$callCount;
    }
}

// Usar sem criar objeto — acesso via NomeClasse::
echo MathHelper::add(5, 3) . PHP_EOL;          // 8
echo MathHelper::circleArea(10) . PHP_EOL;      // 314.159...
echo MathHelper::PI . PHP_EOL;                  // 3.14159...
echo MathHelper::getCallCount() . PHP_EOL;      // 2

// Contagem de instâncias — padrão útil
class User
{
    private static int $instanceCount = 0;

    public function __construct(
        public readonly string $name,
    ) {
        self::$instanceCount++;
    }

    public static function getInstanceCount(): int
    {
        return self::$instanceCount;
    }
}

$u1 = new User('Ana');
$u2 = new User('Bruno');
$u3 = new User('Carlos');

echo User::getInstanceCount() . ' usuários criados' . PHP_EOL; // 3
```

### 25.5 Palavras-chave: $this, self e parent

Essas três palavras-chave referenciam diferentes contextos dentro de uma classe: `$this` aponta para a **instância atual**, `self` para a **classe onde o código está escrito**, e `parent` para a **classe pai** (superclasse). Entender essa distinção é fundamental para herança:

```php
<?php

declare(strict_types=1);

// $this → instância atual (propriedades e métodos de instância)
// self  → classe atual (constantes, propriedades/métodos estáticos)
// parent → classe pai (ao sobrescrever métodos)

class Animal
{
    public function __construct(
        protected string $name,
    ) {}

    public function makeSound(): string
    {
        return 'Som genérico';
    }

    public static function kingdom(): string
    {
        return 'Animalia';
    }
}

class Dog extends Animal
{
    public function makeSound(): string
    {
        // parent:: chama o método da classe pai
        return parent::makeSound() . ' → Au au!';
    }

    public function present(): string
    {
        // $this para instância, self para classe atual
        return "Sou {$this->name}, um " . self::kingdom();
    }
}

$rex = new Dog('Rex');
echo $rex->makeSound() . PHP_EOL;  // Som genérico → Au au!
echo $rex->present() . PHP_EOL;    // Sou Rex, um Animalia
```

### 📝 Exercícios do Capítulo 25

1. Crie uma classe `Rectangle` com `width` e `height` e métodos para área e perímetro
2. Implemente uma classe `ShoppingCart` com métodos para adicionar, remover e calcular total
3. Crie uma classe `Calculator` com métodos estáticos para as 4 operações
4. Implemente uma classe `User` com validação de email no construtor
5. Faça uma classe `Counter` que registre quantas instâncias foram criadas (use `static`)

---

## 26. Encapsulamento

Encapsulamento é o princípio de **esconder detalhes internos** e expor apenas uma interface controlada. Em vez de permitir que qualquer código externo manipule diretamente as propriedades de um objeto, você define o que é público, o que é protegido (para subclasses) e o que é privado (uso interno apenas).

Esse controle previne estados inválidos, facilita refatorações futuras (a interface pública não muda mesmo se a implementação interna mudar) e torna o código mais previsível.

### 26.1 Modificadores de acesso (visibilidade)

O PHP possui três modificadores: `public` (qualquer código acessa), `protected` (classe e subclasses) e `private` (apenas a própria classe). A regra geral é: **comece sempre com `private`** e abra o acesso conforme a necessidade:

```php
<?php

declare(strict_types=1);

class UserAccount
{
    // public — acessível de QUALQUER lugar
    public string $displayName;

    // protected — acessível na classe e em SUBCLASSES
    protected string $email;

    // private — acessível APENAS dentro da própria classe
    private string $passwordHash;

    public function __construct(
        string $displayName,
        string $email,
        string $password,
    ) {
        $this->displayName = $displayName;
        $this->email = $email;
        $this->passwordHash = password_hash($password, PASSWORD_ARGON2ID);
    }

    // Método público — interface controlada para acessar dados privados
    public function verifyPassword(string $password): bool
    {
        return password_verify($password, $this->passwordHash);
    }

    // Método privado — uso interno apenas
    private function generateToken(): string
    {
        return bin2hex(random_bytes(32));
    }

    public function createSession(): string
    {
        // Método público pode usar métodos privados internamente
        return $this->generateToken();
    }
}

$user = new UserAccount('João', 'joao@example.com', 'senha123');

echo $user->displayName . PHP_EOL;    // ✅ OK (public)
// echo $user->email;                  // ❌ ERRO (protected)
// echo $user->passwordHash;           // ❌ ERRO (private)
echo $user->verifyPassword('senha123') ? 'OK' : 'Falha'; // ✅ OK
// echo $user->generateToken();        // ❌ ERRO (private)
echo $user->createSession() . PHP_EOL; // ✅ OK (public)
```

### 26.2 Getters e Setters com validação

Getters e setters são métodos que **controlam o acesso** a propriedades privadas. O setter valida o valor antes de atribuí-lo, garantindo que o objeto nunca entre em estado inválido. No construtor, use os setters para que a validação se aplique desde a criação:

```php
<?php

declare(strict_types=1);

class Product
{
    private string $name;
    private float $price;
    private int $stock;

    public function __construct(string $name, float $price, int $stock)
    {
        // Validação via setters mesmo no construtor
        $this->setName($name);
        $this->setPrice($price);
        $this->setStock($stock);
    }

    // Getter — retorna o valor
    public function getName(): string
    {
        return $this->name;
    }

    // Setter — valida ANTES de atribuir
    public function setName(string $name): void
    {
        $trimmed = trim($name);

        if (mb_strlen($trimmed) < 3) {
            throw new InvalidArgumentException(
                'Nome do produto deve ter pelo menos 3 caracteres.',
            );
        }

        $this->name = $trimmed;
    }

    public function getPrice(): float
    {
        return $this->price;
    }

    public function setPrice(float $price): void
    {
        if ($price < 0) {
            throw new InvalidArgumentException('Preço não pode ser negativo.');
        }

        $this->price = $price;
    }

    public function getStock(): int
    {
        return $this->stock;
    }

    public function setStock(int $stock): void
    {
        if ($stock < 0) {
            throw new InvalidArgumentException('Estoque não pode ser negativo.');
        }

        $this->stock = $stock;
    }

    // Método de negócio que usa validação interna
    public function sell(int $quantity): void
    {
        if ($quantity <= 0) {
            throw new InvalidArgumentException('Quantidade deve ser positiva.');
        }

        if ($quantity > $this->stock) {
            throw new RuntimeException(
                "Estoque insuficiente. Disponível: {$this->stock}",
            );
        }

        $this->stock -= $quantity;
    }

    public function getFormattedPrice(): string
    {
        return 'R$ ' . number_format($this->price, 2, ',', '.');
    }
}

$product = new Product('Notebook Dell', 2500.00, 10);
echo $product->getName() . PHP_EOL;           // Notebook Dell
echo $product->getFormattedPrice() . PHP_EOL;  // R$ 2.500,00

$product->sell(3);
echo $product->getStock() . PHP_EOL; // 7

// Validação em ação
try {
    $product->setPrice(-100);
} catch (InvalidArgumentException $e) {
    echo 'Erro: ' . $e->getMessage() . PHP_EOL;
    // Erro: Preço não pode ser negativo.
}
```

### 26.3 Readonly Properties (PHP 8.1+)

Propriedades `readonly` podem ser atribuídas **uma única vez** (geralmente no construtor) e nunca mais modificadas. São perfeitas para dados que não devem mudar após a criação, como IDs, timestamps e documentos. No PHP 8.2+, `readonly class` torna **todas** as propriedades imutáveis automaticamente:

```php
<?php

declare(strict_types=1);

// readonly — propriedade que pode ser atribuída APENAS UMA VEZ (no construtor)
class Invoice
{
    public function __construct(
        public readonly int $id,
        public readonly string $customerEmail,
        public readonly float $total,
        public readonly DateTimeImmutable $createdAt = new DateTimeImmutable(),
    ) {}

    public function getFormattedTotal(): string
    {
        return 'R$ ' . number_format($this->total, 2, ',', '.');
    }
}

$invoice = new Invoice(
    id: 1001,
    customerEmail: 'cliente@email.com',
    total: 2599.90,
);

echo $invoice->id . PHP_EOL;                // 1001 — leitura OK
echo $invoice->getFormattedTotal() . PHP_EOL; // R$ 2.599,90

// $invoice->id = 2;        // ❌ ERRO: Cannot modify readonly property
// $invoice->total = 0;     // ❌ ERRO: Cannot modify readonly property

// Readonly Class (PHP 8.2+) — TODAS as propriedades são readonly automaticamente
readonly class Address
{
    public function __construct(
        public string $street,
        public string $city,
        public string $state,
        public string $zipCode,
    ) {}

    public function getFullAddress(): string
    {
        return "{$this->street}, {$this->city} - {$this->state}, {$this->zipCode}";
    }
}

$address = new Address('Rua Augusta, 100', 'São Paulo', 'SP', '01310-100');
echo $address->getFullAddress() . PHP_EOL;
// Rua Augusta, 100, São Paulo - SP, 01310-100
// Nenhuma propriedade pode ser modificada após criação
```

### 26.4 Property Hooks (PHP 8.4+)

Property Hooks são uma das maiores novidades do PHP 8.4: permitem definir lógica de `get` e `set` **diretamente na declaração da propriedade**, eliminando a necessidade de getters/setters separados. Propriedades virtuais (sem armazenamento próprio) podem ser calculadas a partir de outras:

```php
<?php

declare(strict_types=1);

// Property Hooks substituem getters/setters com sintaxe integrada à propriedade
class Temperature
{
    // Hook get — transforma valor ao ler
    public float $celsius {
        get => $this->celsius;
        set {
            if ($value < -273.15) {
                throw new InvalidArgumentException(
                    'Temperatura não pode ser menor que zero absoluto (-273.15°C).',
                );
            }
            $this->celsius = round($value, 2);
        }
    }

    // Propriedade virtual — calculada a partir de outra
    public float $fahrenheit {
        get => round($this->celsius * 9 / 5 + 32, 2);
        set => $this->celsius = ($value - 32) * 5 / 9;
    }

    public float $kelvin {
        get => round($this->celsius + 273.15, 2);
        set => $this->celsius = $value - 273.15;
    }

    public function __construct(float $celsius)
    {
        $this->celsius = $celsius;
    }
}

$temp = new Temperature(25.0);
echo "Celsius: {$temp->celsius}" . PHP_EOL;       // 25.0
echo "Fahrenheit: {$temp->fahrenheit}" . PHP_EOL;  // 77.0
echo "Kelvin: {$temp->kelvin}" . PHP_EOL;          // 298.15

// Setar via Fahrenheit — converte automaticamente para Celsius
$temp->fahrenheit = 100.0;
echo "Celsius: {$temp->celsius}" . PHP_EOL; // 37.78

// Outro exemplo: formatação automática
class UserProfile
{
    public string $email {
        set => strtolower(trim($value)); // Normaliza automaticamente
    }

    public string $phone {
        // Armazena apenas dígitos, exibe formatado
        set => preg_replace('/\D/', '', $value);
        get => preg_replace(
            '/(\d{2})(\d{4,5})(\d{4})/',
            '($1) $2-$3',
            $this->phone,
        );
    }

    public function __construct(string $email, string $phone)
    {
        $this->email = $email;
        $this->phone = $phone;
    }
}

$profile = new UserProfile('  JOAO@Email.COM  ', '(11) 98765-4321');
echo $profile->email . PHP_EOL; // joao@email.com (normalizado)
echo $profile->phone . PHP_EOL; // (11) 98765-4321 (formatado)
```

### 📝 Exercícios do Capítulo 26

1. Crie uma classe `Person` com propriedades privadas nome/idade e getters/setters com validação
2. Implemente uma classe `BankAccount` que **nunca** permita saldo negativo
3. Crie uma classe readonly `CpfDocument` que valide o formato no construtor
4. Use property hooks para criar uma classe `Money` que formate automaticamente valores
5. Implemente `UserProfile` com hook que normalize email para minúsculas ao setar

---

## 27. Herança e Polimorfismo

Herança permite que uma classe **filho** herde propriedades e métodos de uma classe **pai**, reutilizando código sem duplicação. Polimorfismo ("muitas formas") permite que objetos de classes diferentes respondam à **mesma interface** de maneiras distintas — você pode tratar um `Dog`, um `Cat` e um `Bird` todos como `Animal`, e cada um executa seu comportamento específico.

### 27.1 Herança básica (extends)

Use `extends` para criar uma classe filha. A filha herda tudo que é `public` ou `protected` do pai, e pode **sobrescrever** (override) métodos para customizar comportamento. O construtor do pai pode ser chamado explicitamente com `parent::__construct()`:

```php
<?php

declare(strict_types=1);

// Classe base (superclasse / classe pai)
class Vehicle
{
    public function __construct(
        protected string $brand,
        protected string $model,
        protected int $year,
    ) {}

    public function getDescription(): string
    {
        return "{$this->brand} {$this->model} ({$this->year})";
    }

    public function start(): string
    {
        return '🔑 Veículo ligado';
    }
}

// extends — herda TODAS as propriedades e métodos da classe pai
class Car extends Vehicle
{
    public function __construct(
        string $brand,
        string $model,
        int $year,
        private int $doors,
    ) {
        // parent::__construct() chama o construtor da classe pai
        parent::__construct($brand, $model, $year);
    }

    public function getDoors(): int
    {
        return $this->doors;
    }

    // Override — sobrescreve o método da classe pai
    public function start(): string
    {
        return parent::start() . ' — Motor do carro ligado 🚗';
    }
}

class Motorcycle extends Vehicle
{
    public function __construct(
        string $brand,
        string $model,
        int $year,
        private int $engineCC,
    ) {
        parent::__construct($brand, $model, $year);
    }

    public function getEngineCC(): int
    {
        return $this->engineCC;
    }

    public function start(): string
    {
        return parent::start() . ' — Motor da moto ligado 🏍️';
    }
}

// Uso — cada classe herda getDescription() e sobrescreve start()
$car = new Car('Toyota', 'Corolla', 2024, 4);
echo $car->getDescription() . PHP_EOL;  // Toyota Corolla (2024)
echo $car->start() . PHP_EOL;           // 🔑 Veículo ligado — Motor do carro ligado 🚗
echo $car->getDoors() . PHP_EOL;        // 4

$motorcycle = new Motorcycle('Honda', 'CB 500', 2024, 500);
echo $motorcycle->start() . PHP_EOL;          // 🔑 Veículo ligado — Motor da moto ligado 🏍️
echo $motorcycle->getEngineCC() . ' cc' . PHP_EOL; // 500 cc
```

### 27.2 Classes abstratas (abstract)

Classes abstratas são **moldes incompletos** que não podem ser instanciados diretamente. Elas definem métodos abstratos (sem corpo) que **obrigam** as subclasses a fornecer uma implementação. Use quando você quer garantir uma estrutura comum, mas cada subclasse deve ter comportamento específico:

```php
<?php

declare(strict_types=1);

// abstract — classe que NÃO pode ser instanciada diretamente
// Serve como "modelo parcial" que subclasses devem completar
abstract class Shape
{
    // Métodos abstratos — DEVEM ser implementados pelas subclasses
    abstract public function calculateArea(): float;
    abstract public function calculatePerimeter(): float;

    // Métodos concretos — herdados automaticamente
    public function getInfo(): string
    {
        return sprintf(
            'Área: %.2f | Perímetro: %.2f',
            $this->calculateArea(),
            $this->calculatePerimeter(),
        );
    }
}

class Rectangle extends Shape
{
    public function __construct(
        private float $width,
        private float $height,
    ) {}

    public function calculateArea(): float
    {
        return $this->width * $this->height;
    }

    public function calculatePerimeter(): float
    {
        return 2 * ($this->width + $this->height);
    }
}

class Circle extends Shape
{
    public function __construct(
        private float $radius,
    ) {}

    public function calculateArea(): float
    {
        return M_PI * ($this->radius ** 2);
    }

    public function calculatePerimeter(): float
    {
        return 2 * M_PI * $this->radius;
    }
}

class Triangle extends Shape
{
    public function __construct(
        private float $sideA,
        private float $sideB,
        private float $sideC,
    ) {
        // Validação: desigualdade triangular
        if ($sideA + $sideB <= $sideC
            || $sideA + $sideC <= $sideB
            || $sideB + $sideC <= $sideA
        ) {
            throw new InvalidArgumentException('Lados não formam um triângulo válido.');
        }
    }

    public function calculateArea(): float
    {
        // Fórmula de Heron
        $s = ($this->sideA + $this->sideB + $this->sideC) / 2;
        return sqrt($s * ($s - $this->sideA) * ($s - $this->sideB) * ($s - $this->sideC));
    }

    public function calculatePerimeter(): float
    {
        return $this->sideA + $this->sideB + $this->sideC;
    }
}

// $shape = new Shape();  // ❌ ERRO: Cannot instantiate abstract class

$rect = new Rectangle(5, 10);
echo $rect->getInfo() . PHP_EOL;    // Área: 50.00 | Perímetro: 30.00

$circle = new Circle(5);
echo $circle->getInfo() . PHP_EOL;  // Área: 78.54 | Perímetro: 31.42

$triangle = new Triangle(3, 4, 5);
echo $triangle->getInfo() . PHP_EOL; // Área: 6.00 | Perímetro: 12.00
```

### 27.3 Polimorfismo em ação

O poder real do polimorfismo aparece quando você trabalha com **coleções de objetos de tipos diferentes**, todos tipados pela classe pai ou interface. O código que os processa não precisa saber o tipo específico — cada objeto sabe como executar seus próprios métodos:

```php
<?php

declare(strict_types=1);

// Polimorfismo: objetos de classes diferentes respondem
// à MESMA interface de formas DIFERENTES

abstract class PaymentMethod
{
    public function __construct(
        protected float $amount,
    ) {}

    abstract public function process(): string;
    abstract public function getReceipt(): string;
}

class PixPayment extends PaymentMethod
{
    public function __construct(
        float $amount,
        private string $pixKey,
    ) {
        parent::__construct($amount);
    }

    public function process(): string
    {
        return "💚 Pix de R$ " . number_format($this->amount, 2, ',', '.') .
            " enviado para {$this->pixKey}";
    }

    public function getReceipt(): string
    {
        return "Comprovante Pix — Chave: {$this->pixKey}";
    }
}

class CreditCardPayment extends PaymentMethod
{
    public function __construct(
        float $amount,
        private string $lastFourDigits,
        private int $installments = 1,
    ) {
        parent::__construct($amount);
    }

    public function process(): string
    {
        $installmentValue = $this->amount / $this->installments;
        return "💳 Cartão final {$this->lastFourDigits} — {$this->installments}x de R$ " .
            number_format($installmentValue, 2, ',', '.');
    }

    public function getReceipt(): string
    {
        return "Comprovante Cartão — Final: {$this->lastFourDigits}";
    }
}

class BoletoPayment extends PaymentMethod
{
    public function process(): string
    {
        return "📄 Boleto gerado no valor de R$ " .
            number_format($this->amount, 2, ',', '.');
    }

    public function getReceipt(): string
    {
        $barCode = str_repeat(str_pad((string) random_int(0, 9), 1), 44);
        return "Comprovante Boleto — Código: {$barCode}";
    }
}

// Função que aceita QUALQUER PaymentMethod — polimorfismo!
function processPayment(PaymentMethod $payment): void
{
    echo $payment->process() . PHP_EOL;
    echo $payment->getReceipt() . PHP_EOL;
    echo str_repeat('─', 50) . PHP_EOL;
}

// Array de pagamentos mistos — cada um sabe como se processar
$payments = [
    new PixPayment(150.00, 'joao@email.com'),
    new CreditCardPayment(899.90, '4321', installments: 3),
    new BoletoPayment(250.00),
];

foreach ($payments as $payment) {
    processPayment($payment); // Cada objeto responde de forma diferente!
}
```

### 27.4 Final — prevenir herança e override

`final` impede que uma classe seja estendida ou que um método seja sobrescrito. Use quando a implementação não deve ser alterada por subclasses — comum em classes de segurança, logs e configurações críticas:

```php
<?php

declare(strict_types=1);

// final method — NÃO pode ser sobrescrito por subclasses
class User
{
    public function __construct(
        private readonly int $id,
        private string $name,
    ) {}

    // Método sensível — ninguém pode alterar o comportamento
    final public function getId(): int
    {
        return $this->id;
    }

    // Método aberto — subclasses podem sobrescrever
    public function getDisplayName(): string
    {
        return $this->name;
    }
}

class Admin extends User
{
    // public function getId(): int { }  // ❌ ERRO: Cannot override final method

    public function getDisplayName(): string // ✅ OK — não é final
    {
        return '👑 ' . parent::getDisplayName();
    }
}

// final class — NÃO pode ser herdada (nenhuma subclasse permitida)
final class SecurityToken
{
    public function __construct(
        public readonly string $value,
        public readonly DateTimeImmutable $expiresAt,
    ) {}

    public function isExpired(): bool
    {
        return new DateTimeImmutable() > $this->expiresAt;
    }
}

// class CustomToken extends SecurityToken { }  // ❌ ERRO: Cannot inherit from final class
```

### 📝 Exercícios do Capítulo 27

1. Crie uma hierarquia `Animal` → `Dog`, `Cat`, `Bird` com métodos `speak()` e `move()` diferentes
2. Implemente classes abstratas para formas geométricas 3D (`Cube`, `Sphere`, `Cylinder`) com cálculo de volume
3. Crie um sistema de pagamento polimórfico que calcule taxas diferentes por método
4. Use `final` para proteger métodos sensíveis em uma classe `Authentication`
5. Implemente um mini-sistema de notificações (`EmailNotification`, `SmsNotification`, `PushNotification`)

---

## 28. Interfaces e Traits

Interfaces definem **contratos** — métodos que uma classe **deve** implementar, sem ditar como. Traits oferecem **reutilização horizontal** de código, permitindo compartilhar métodos entre classes que não têm relação de herança. Juntos, eles resolvem limitações da herança simples do PHP.

### 28.1 Interfaces — contratos obrigatórios

Uma interface declara assinaturas de métodos sem implementação. Qualquer classe que implemente a interface **deve** fornecer todos os métodos. Uma classe pode implementar **múltiplas** interfaces (ao contrário da herança, limitada a um pai). Use interfaces para definir capacidades ("o que o objeto faz"), não hierarquias ("o que o objeto é"):

```php
<?php

declare(strict_types=1);

// Interface: define APENAS assinaturas de métodos (contrato)
// Qualquer classe que implementar DEVE fornecer todos os métodos
interface AuthenticatableInterface
{
    // Verifica credenciais — retorna true se válidas
    public function authenticate(string $password): bool;

    // Retorna lista de permissões do usuário
    public function getPermissions(): array;
}

interface NotifiableInterface
{
    // Envia notificação para o usuário
    public function sendNotification(string $message): void;
}

// Uma classe pode implementar MÚLTIPLAS interfaces
// Isso é como "herança múltipla" segura no PHP
class User implements AuthenticatableInterface, NotifiableInterface
{
    public function __construct(
        private readonly string $name,
        private readonly string $passwordHash,
        private readonly array $permissions = [],
    ) {}

    // Implementação OBRIGATÓRIA de AuthenticatableInterface
    public function authenticate(string $password): bool
    {
        return password_verify($password, $this->passwordHash);
    }

    public function getPermissions(): array
    {
        return $this->permissions;
    }

    // Implementação OBRIGATÓRIA de NotifiableInterface
    public function sendNotification(string $message): void
    {
        // Simulação de envio de email
        echo "📧 Enviando para {$this->name}: {$message}" . PHP_EOL;
    }
}

// ✅ Type hint com interface — aceita QUALQUER objeto que implemente o contrato
// Isso é polimorfismo via interface (mais flexível que herança)
function performLogin(AuthenticatableInterface $entity, string $password): bool
{
    if ($entity->authenticate($password)) {
        $permissions = $entity->getPermissions();
        echo 'Login realizado! Permissões: ' . implode(', ', $permissions) . PHP_EOL;
        return true;
    }

    echo 'Falha no login.' . PHP_EOL;
    return false;
}

// Uso
$user = new User(
    name: 'João',
    passwordHash: password_hash('senha123', PASSWORD_ARGON2ID),
    permissions: ['read', 'write'],
);

performLogin($user, 'senha123');
// Login realizado! Permissões: read, write

// ✅ Qualquer outra classe que implemente AuthenticatableInterface também funciona
class ApiClient implements AuthenticatableInterface
{
    public function __construct(
        private readonly string $apiKey,
    ) {}

    public function authenticate(string $password): bool
    {
        return hash_equals($this->apiKey, $password);
    }

    public function getPermissions(): array
    {
        return ['api.read'];
    }
}

$api = new ApiClient(apiKey: 'chave-secreta-123');
performLogin($api, 'chave-secreta-123'); // Funciona! Mesmo contrato, implementação diferente
```

### 28.2 Traits — reutilização de código

Traits permitem **compartilhar métodos** entre classes não relacionadas por herança. Pense neles como "copiar e colar inteligente" — o código do trait é inserido na classe que o usa. Uma classe pode usar múltiplos traits:

```php
<?php

declare(strict_types=1);

// Trait: bloco de código reutilizável que pode ser "colado" em várias classes
// Resolve o problema de PHP não ter herança múltipla

trait TimestampableTrait
{
    // Propriedades com tipo e valor padrão
    private ?DateTimeImmutable $createdAt = null;
    private ?DateTimeImmutable $updatedAt = null;

    // Registra data/hora da criação
    public function recordCreation(): void
    {
        $this->createdAt = new DateTimeImmutable();
    }

    // Registra data/hora da última atualização
    public function recordUpdate(): void
    {
        $this->updatedAt = new DateTimeImmutable();
    }

    public function getCreatedAt(): ?DateTimeImmutable
    {
        return $this->createdAt;
    }

    public function getUpdatedAt(): ?DateTimeImmutable
    {
        return $this->updatedAt;
    }

    // Retorna datas formatadas para exibição
    public function getTimestampInfo(): string
    {
        $created = $this->createdAt?->format('d/m/Y H:i:s') ?? 'N/A';
        $updated = $this->updatedAt?->format('d/m/Y H:i:s') ?? 'N/A';
        return "Criado: {$created} | Atualizado: {$updated}";
    }
}

trait ValidatableTrait
{
    // Armazena erros de validação por campo
    protected array $errors = [];

    // Método abstrato — a classe que usar este trait DEVE implementar
    abstract protected function validate(): bool;

    // Executa validação e retorna resultado
    public function isValid(): bool
    {
        $this->errors = [];  // Limpa erros anteriores
        return $this->validate();
    }

    public function getErrors(): array
    {
        return $this->errors;
    }

    // Adiciona erro de validação para um campo específico
    protected function addError(string $field, string $message): void
    {
        $this->errors[$field][] = $message;
    }

    // Verifica se um campo específico tem erros
    public function hasError(string $field): bool
    {
        return isset($this->errors[$field]);
    }
}

// Classe que usa MÚLTIPLOS traits — composição poderosa
class User
{
    use TimestampableTrait, ValidatableTrait;

    public function __construct(
        private string $name,
        private string $email,
    ) {
        // Registra data de criação automaticamente
        $this->recordCreation();
    }

    // Atualiza dados e registra timestamp
    public function update(string $name, string $email): void
    {
        $this->name = $name;
        $this->email = $email;
        $this->recordUpdate();
    }

    // Implementação obrigatória do método abstrato do trait
    protected function validate(): bool
    {
        $valid = true;

        if (mb_strlen($this->name) < 3) {
            $this->addError('name', 'Nome deve ter pelo menos 3 caracteres.');
            $valid = false;
        }

        if (!filter_var($this->email, FILTER_VALIDATE_EMAIL)) {
            $this->addError('email', 'Email inválido.');
            $valid = false;
        }

        return $valid;
    }

    public function getName(): string
    {
        return $this->name;
    }
}

// Uso
$user = new User('João', 'joao@example.com');

if ($user->isValid()) {
    echo "✅ Usuário válido!" . PHP_EOL;
    echo $user->getTimestampInfo() . PHP_EOL;
    // Criado: 09/02/2026 15:30:00 | Atualizado: N/A
} else {
    echo "❌ Erros encontrados:" . PHP_EOL;
    print_r($user->getErrors());
}

// Testar validação com dados inválidos
$invalid = new User('AB', 'email-invalido');
if (!$invalid->isValid()) {
    print_r($invalid->getErrors());
    // ['name' => ['Nome deve ter...'], 'email' => ['Email inválido.']]
}
```

### 28.3 Resolvendo conflitos entre Traits

Quando dois traits definem métodos com o mesmo nome, ocorre um conflito. O PHP exige resolução explícita com `insteadof` (para escolher qual usar) e `as` (para criar um alias alternativo):

```php
<?php

declare(strict_types=1);

// Quando dois traits têm métodos com o MESMO nome, ocorre conflito
// O PHP exige que você resolva explicitamente

trait LoggerTrait
{
    public function log(string $message): string
    {
        return "[LOG] {$message}";
    }

    public function uniqueFromLogger(): string
    {
        return 'Método exclusivo de LoggerTrait';
    }
}

trait AuditorTrait
{
    public function log(string $message): string
    {
        return "[AUDIT] {$message}";
    }
}

class AppService
{
    use LoggerTrait, AuditorTrait {
        // Resolver conflito: usar o log() de LoggerTrait
        LoggerTrait::log insteadof AuditorTrait;

        // Criar alias para acessar o log() de AuditorTrait
        AuditorTrait::log as auditLog;
    }
}

$service = new AppService();
echo $service->log('Evento registrado') . PHP_EOL;
// [LOG] Evento registrado

echo $service->auditLog('Ação auditada') . PHP_EOL;
// [AUDIT] Ação auditada

echo $service->uniqueFromLogger() . PHP_EOL;
// Método exclusivo de LoggerTrait

// ✅ Alterar visibilidade via alias
trait HelperTrait
{
    public function internalHelper(): string
    {
        return 'Resultado interno';
    }
}

class MyService
{
    use HelperTrait {
        // Renomear e tornar privado
        internalHelper as private privateHelper;
    }

    public function process(): string
    {
        // Pode usar internamente
        return $this->privateHelper() . ' processado';
    }
}

$myService = new MyService();
echo $myService->process() . PHP_EOL; // Resultado interno processado
// echo $myService->privateHelper(); // ❌ ERRO: método é private
```

### 28.4 Exemplo prático completo

O exemplo abaixo combina interfaces, traits e classes abstratas em um cenário realista de sistema de notificações, demonstrando como cada ferramenta resolve uma necessidade diferente:

```php
<?php

declare(strict_types=1);

// ── Trait para auditoria (log de ações) ──

trait LoggableTrait
{
    private array $logs = [];

    protected function log(string $action, string $detail = ''): void
    {
        $this->logs[] = [
            'timestamp' => new DateTimeImmutable(),
            'action' => $action,
            'detail' => $detail,
        ];
    }

    public function getLogs(): array
    {
        return $this->logs;
    }

    // Retorna logs formatados para debug
    public function getFormattedLogs(): string
    {
        $output = '';

        foreach ($this->logs as $entry) {
            $time = $entry['timestamp']->format('H:i:s');
            $output .= "[{$time}] {$entry['action']}";
            if ($entry['detail'] !== '') {
                $output .= " — {$entry['detail']}";
            }
            $output .= PHP_EOL;
        }

        return $output;
    }
}

// ── Trait para serialização JSON ──

trait JsonSerializableTrait
{
    // Converte objeto para JSON formatado
    public function toJson(): string
    {
        return json_encode(
            $this->toArray(),
            JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE | JSON_THROW_ON_ERROR,
        );
    }

    // Cada classe define quais campos expor
    abstract protected function toArray(): array;
}

// ── Interface de repositório (contrato para persistência) ──

interface RepositoryInterface
{
    public function save(mixed $entity): void;
    public function find(int $id): mixed;
    public function delete(int $id): bool;
    public function findAll(): array;
}

// ── Classe de domínio usando traits ──

class Product
{
    use LoggableTrait, JsonSerializableTrait;

    public function __construct(
        private readonly int $id,
        private string $name,
        private float $price,
    ) {
        $this->log('create', "Produto criado: {$name}");
    }

    public function updatePrice(float $newPrice): void
    {
        $oldPrice = $this->price;
        $this->price = $newPrice;
        $this->log(
            'price_update',
            "Preço alterado de R$ {$oldPrice} para R$ {$newPrice}",
        );
    }

    // Implementação do método abstrato do JsonSerializableTrait
    protected function toArray(): array
    {
        return [
            'id' => $this->id,
            'name' => $this->name,
            'price' => $this->price,
        ];
    }

    public function getId(): int
    {
        return $this->id;
    }

    public function getName(): string
    {
        return $this->name;
    }
}

// Uso completo
$product = new Product(id: 1, name: 'Notebook', price: 2500.00);
$product->updatePrice(2800.00);

// JSON do produto
echo $product->toJson() . PHP_EOL;
// {
//     "id": 1,
//     "name": "Notebook",
//     "price": 2800
// }

// Logs de auditoria
echo $product->getFormattedLogs();
// [15:30:00] create — Produto criado: Notebook
// [15:30:00] price_update — Preço alterado de R$ 2500 para R$ 2800
```

### 📝 Exercícios do Capítulo 28

1. Crie `PayableInterface` com métodos `processPayment()` e `validatePayment()`
2. Implemente um trait `SluggableTrait` que gere URLs amigáveis a partir de títulos
3. Crie um trait `SoftDeletableTrait` para exclusão lógica (marca `deletedAt` sem remover)
4. Implemente sistema de e-commerce com interfaces: `CartInterface`, `ProductInterface`, `PaymentInterface`
5. Resolva conflitos entre dois traits que possuem métodos `format()` com comportamentos diferentes

---

## 29. OOP Avançado

Este capítulo cobre recursos avançados de OOP que elevam seu código ao nível profissional: **Enums** para valores finitos e tipados, **métodos mágicos** para comportamentos interceptados, e **namespaces** com autoloading PSR-4 para organização em projetos de grande escala.

### 29.1 Enums (PHP 8.1+)

Enums (enumerações) representam um **conjunto fixo e finito** de valores possíveis. São type-safe (o compilador garante que apenas valores válidos são usados) e substituem constantes soltas ou strings mágicas. *Backed Enums* associam cada caso a um valor escalar (string ou int) para persistência:

```php
<?php

declare(strict_types=1);

// Enum pura — sem valor associado (ideal para estados simples)
enum Priority
{
    case LOW;
    case MEDIUM;
    case HIGH;
    case CRITICAL;
}

// ✅ Backed Enum — com valor string/int (ideal para persistência em banco)
enum OrderStatus: string
{
    case PENDING = 'pending';
    case PAID = 'paid';
    case SHIPPED = 'shipped';
    case DELIVERED = 'delivered';
    case CANCELLED = 'cancelled';

    // Enums podem ter métodos!
    public function label(): string
    {
        return match ($this) {
            self::PENDING => 'Aguardando Pagamento',
            self::PAID => 'Pagamento Confirmado',
            self::SHIPPED => 'Em Transporte',
            self::DELIVERED => 'Entregue',
            self::CANCELLED => 'Cancelado',
        };
    }

    // Lógica de negócio dentro do enum
    public function canModify(): bool
    {
        return match ($this) {
            self::PENDING, self::PAID => true,
            default => false,
        };
    }

    // Verificar transição válida de status
    public function canTransitionTo(self $newStatus): bool
    {
        return match ($this) {
            self::PENDING => in_array($newStatus, [self::PAID, self::CANCELLED]),
            self::PAID => in_array($newStatus, [self::SHIPPED, self::CANCELLED]),
            self::SHIPPED => $newStatus === self::DELIVERED,
            self::DELIVERED, self::CANCELLED => false,
        };
    }
}

class Order
{
    public function __construct(
        private readonly int $id,
        private OrderStatus $status = OrderStatus::PENDING,
    ) {}

    public function updateStatus(OrderStatus $newStatus): void
    {
        // Validação de transição usando lógica do enum
        if (!$this->status->canTransitionTo($newStatus)) {
            throw new RuntimeException(
                "Transição inválida: {$this->status->label()} → {$newStatus->label()}",
            );
        }

        $this->status = $newStatus;
    }

    public function getStatus(): OrderStatus
    {
        return $this->status;
    }
}

// Uso
$order = new Order(id: 1);
echo $order->getStatus()->label() . PHP_EOL; // Aguardando Pagamento

$order->updateStatus(OrderStatus::PAID);
echo $order->getStatus()->value . PHP_EOL; // paid

// Iterar sobre todos os cases do enum
foreach (OrderStatus::cases() as $status) {
    echo "{$status->name}: {$status->label()}" . PHP_EOL;
}

// Criar enum a partir de valor do banco de dados
$fromDb = OrderStatus::from('shipped');      // Lança ValueError se inválido
$safe = OrderStatus::tryFrom('invalido');     // Retorna null se inválido
var_dump($safe); // NULL
```

### 29.2 Métodos Mágicos

Métodos mágicos (prefixados com `__`) são interceptadores chamados automaticamente pelo PHP em situações específicas: ao criar um objeto (`__construct`), ao convertê-lo para string (`__toString`), ao serializá-lo (`__serialize`), ou ao acessar propriedades inexistentes (`__get`/`__set`). Use com moderação — preferível em frameworks e libraries:

```php
<?php

declare(strict_types=1);

class DynamicEntity
{
    // Armazena propriedades dinâmicas internamente
    private array $data = [];

    // __construct — inicializa o objeto
    public function __construct(array $initialData = [])
    {
        $this->data = $initialData;
    }

    // __get — chamado ao acessar propriedade inexistente
    public function __get(string $name): mixed
    {
        return $this->data[$name] ?? null;
    }

    // __set — chamado ao atribuir valor a propriedade inexistente
    public function __set(string $name, mixed $value): void
    {
        $this->data[$name] = $value;
    }

    // __isset — chamado por isset() e empty()
    public function __isset(string $name): bool
    {
        return isset($this->data[$name]);
    }

    // __unset — chamado por unset()
    public function __unset(string $name): void
    {
        unset($this->data[$name]);
    }

    // __toString — converte o objeto para string
    public function __toString(): string
    {
        return json_encode(
            $this->data,
            JSON_UNESCAPED_UNICODE | JSON_THROW_ON_ERROR,
        );
    }

    // __invoke — permite usar o objeto como função: $obj('arg')
    public function __invoke(string $message): string
    {
        return "Entidade diz: {$message}";
    }

    // __clone — executado quando o objeto é clonado com clone
    public function __clone(): void
    {
        // Remover ID do clone para evitar duplicatas
        unset($this->data['id']);
    }

    // __debugInfo — controla o que var_dump() exibe
    public function __debugInfo(): array
    {
        return [
            'data_count' => count($this->data),
            'keys' => array_keys($this->data),
        ];
    }
}

// Uso dos métodos mágicos
$entity = new DynamicEntity(['name' => 'João', 'age' => 25]);

// __get
echo $entity->name . PHP_EOL;           // João

// __set
$entity->email = 'joao@example.com';

// __isset
echo isset($entity->email) ? 'Sim' : 'Não'; // Sim

// __toString
echo $entity . PHP_EOL;
// {"name":"João","age":25,"email":"joao@example.com"}

// __invoke
echo $entity('Olá!') . PHP_EOL;         // Entidade diz: Olá!

// __clone
$clone = clone $entity;
var_dump($clone->id);                    // NULL (removido no __clone)
```

### 29.3 Namespaces e Autoloading

Namespaces organizam classes em **espaços hierarquícos**, evitando conflitos de nomes em projetos grandes. Combinados com autoloading, eliminam a necessidade de `require`/`include` manual — as classes são carregadas automaticamente quando usadas pela primeira vez:

```php
<?php

declare(strict_types=1);

// ── Arquivo: src/Model/User.php ──
namespace App\Model;

class User
{
    public function __construct(
        public readonly int $id,
        public string $name,
        public string $email,
    ) {}
}

// ── Arquivo: src/Service/UserService.php ──
namespace App\Service;

// Importar classes de outros namespaces com 'use'
use App\Model\User;
use App\Repository\UserRepository;

class UserService
{
    public function __construct(
        private readonly UserRepository $repository,
    ) {}

    public function create(string $name, string $email): User
    {
        $user = new User(id: 0, name: $name, email: $email);
        $this->repository->save($user);
        return $user;
    }
}

// ── Arquivo: src/Controller/UserController.php ──
namespace App\Controller;

// Alias para evitar conflito de nomes
use App\Model\User as UserModel;
use App\Service\UserService;

class UserController
{
    public function __construct(
        private readonly UserService $service,
    ) {}

    public function store(array $data): UserModel
    {
        return $this->service->create(
            name: $data['name'],
            email: $data['email'],
        );
    }
}
```

### 29.4 Autoloading PSR-4

O padrão **PSR-4** mapeia namespaces a diretórios de forma previsível: o namespace `App\Model\User` corresponde ao arquivo `src/Model/User.php`. O Composer implementa isso automaticamente, mas entender o mecanismo é fundamental:

```php
<?php

declare(strict_types=1);

// ── Arquivo: autoload.php ──
// Autoloader PSR-4 manual (sem Composer)
// Mapeia: App\Model\User → src/Model/User.php

spl_autoload_register(function (string $className): void {
    // Prefixo do namespace base
    $prefix = 'App\\';
    $baseDir = __DIR__ . '/src/';

    // Verificar se a classe usa nosso prefixo
    if (!str_starts_with($className, $prefix)) {
        return; // Não é nossa classe, pular
    }

    // Remover prefixo e converter separadores de namespace para /
    $relativeClass = substr($className, strlen($prefix));
    $file = $baseDir . str_replace('\\', '/', $relativeClass) . '.php';

    // Carregar o arquivo se existir
    if (file_exists($file)) {
        require $file;
    }
});

// Agora pode usar classes sem require manual!
// O autoloader carrega automaticamente quando a classe é referenciada
$user = new App\Model\User(id: 1, name: 'João', email: 'joao@example.com');
$service = new App\Service\UserService(/* ... */);

// ✅ Em projetos reais, use o autoloader do Composer:
// composer.json → { "autoload": { "psr-4": { "App\\": "src/" } } }
// Depois rode: composer dump-autoload
// E inclua: require 'vendor/autoload.php';
```

### 📝 Exercícios do Capítulo 29

1. Crie enums para dias da semana (`Weekday`) e meses (`Month`) com métodos de label em pt-BR
2. Implemente `__get` e `__set` com validação de tipos usando `match`
3. Organize um mini-projeto com namespaces PSR-4: `App\Model`, `App\Service`, `App\Controller`
4. Crie autoloader personalizado com suporte a múltiplos prefixos de namespace
5. Use backed enums com `from()` e `tryFrom()` para converter valores do banco de dados

---

# Parte IV: PHP Moderno — Recursos 8.0 a 8.5

---

## 30. Recursos do PHP 8.0–8.4

Antes de mergulharmos no PHP 8.5, é essencial dominar os recursos revolucionários introduzidos nas versões 8.0 a 8.4. Cada versão trouxe mudanças que transformaram a maneira de escrever PHP moderno.

### 30.1 Named Arguments (PHP 8.0)

Named arguments permitem passar valores para uma função especificando o **nome do parâmetro**, em vez de depender da ordem posicional. Isso torna chamadas com muitos parâmetros (ou com valores padrão intermediários) muito mais legíveis:
```php
<?php

declare(strict_types=1);

// Função com vários parâmetros opcionais
function createUser(
    string $name,
    string $email,
    int $age = 18,
    bool $active = true,
    string $country = 'Brasil',
    string $role = 'user',
): array {
    return compact('name', 'email', 'age', 'active', 'country', 'role');
}

// LEGACY CODE - PHP < 8.0
// Para pular parâmetros opcionais, era preciso repetir os valores padrão:
// $user = createUser("João", "joao@ex.com", 25, true, "Brasil", "admin");

// ✅ PHP 8.0+: named arguments — ordem livre, pula opcionais
$user = createUser(
    email: 'maria@example.com',
    name: 'Maria',
    role: 'admin',
    age: 30,
);
// 'country' e 'active' usam os valores padrão automaticamente

// ✅ Misturar posicionais com nomeados (posicionais primeiro)
$user2 = createUser(
    'Pedro',                      // posicional: $name
    'pedro@example.com',          // posicional: $email
    country: 'Argentina',         // nomeado: pula $age, $active
);

// ✅ Muito útil com funções nativas
$data = array_slice(
    array: [1, 2, 3, 4, 5],
    offset: 1,
    length: 3,
    preserve_keys: true,
);
```

### 30.2 Match Expression (PHP 8.0)

`match` é a evolução do `switch`: usa comparação estrita (`===`), retorna valores diretamente, e lança exceção se nenhum caso corresponder. Elimina os bugs causados por `break` esquecido:
```php
<?php

declare(strict_types=1);

// ✅ match: expressão mais segura e concisa que switch
// Diferenças do switch: comparação estrita (===), retorna valor, sem break
$statusCode = 404;

$message = match ($statusCode) {
    200 => 'OK',
    201 => 'Criado com sucesso',
    400 => 'Requisição inválida',
    401 => 'Não autorizado',
    403 => 'Acesso proibido',
    404 => 'Recurso não encontrado',
    500 => 'Erro interno do servidor',
    default => 'Código desconhecido',
};

echo $message . PHP_EOL; // Recurso não encontrado

// ✅ match com expressão booleana (padrão avançado)
$age = 20;

$category = match (true) {
    $age < 13 => 'Criança',
    $age < 18 => 'Adolescente',
    $age < 60 => 'Adulto',
    $age < 80 => 'Idoso',
    default => 'Centenário',
};

echo $category . PHP_EOL; // Adulto

// ✅ Múltiplos valores no mesmo braço
$dayName = 'saturday';

$dayType = match ($dayName) {
    'monday', 'tuesday', 'wednesday', 'thursday', 'friday' => 'Dia útil',
    'saturday', 'sunday' => 'Final de semana',
};

echo $dayType . PHP_EOL; // Final de semana

// ⚠️ match lança UnhandledMatchError se nenhum braço corresponder
// e não houver 'default'. Isso é INTENCIONAL — evita bugs silenciosos
```

### 30.3 Nullsafe Operator (PHP 8.0)

O operador `?->` encadeia chamadas de métodos em objetos que podem ser `null`, retornando `null` imediatamente se qualquer etapa da cadeia for nula — eliminando cascatas de `if` para verificação de nulidade:
```php
<?php

declare(strict_types=1);

class User
{
    public function __construct(
        public readonly string $name,
        public readonly ?Address $address = null,
    ) {}
}

class Address
{
    public function __construct(
        public readonly ?City $city = null,
    ) {}
}

class City
{
    public function __construct(
        public readonly string $name,
    ) {}

    public function getFormattedName(): string
    {
        return mb_strtoupper($this->name);
    }
}

// LEGACY CODE - PHP < 8.0
// Verificação manual aninhada (verbosa e frágil):
// $cityName = null;
// if ($user->address !== null) {
//     if ($user->address->city !== null) {
//         $cityName = $user->address->city->getFormattedName();
//     }
// }

// ✅ PHP 8.0+: nullsafe operator (?->)
// Se QUALQUER elo da cadeia for null, toda a expressão retorna null
$user = new User('João');
$cityName = $user->address?->city?->getFormattedName();
var_dump($cityName); // NULL (address é null, cadeia para aqui)

// Com valor padrão via ??
$user2 = new User('Maria', new Address(new City('São Paulo')));
$displayCity = $user2->address?->city?->name ?? 'Não informada';
echo $displayCity . PHP_EOL; // São Paulo
```

### 30.4 Readonly Properties (PHP 8.1)

Propriedades `readonly` só podem ser inicializadas uma vez (no construtor) e nunca mais modificadas. Perfeitas para Value Objects e DTOs onde imutabilidade é desejada:
```php
<?php

declare(strict_types=1);

class Product
{
    public function __construct(
        // readonly: só pode ser atribuído UMA VEZ (no construtor)
        public readonly int $id,
        public readonly string $name,
        public readonly string $sku,
        // Propriedades NÃO readonly podem ser modificadas
        public float $price,
        public int $stock = 0,
    ) {}
}

$product = new Product(
    id: 1,
    name: 'Notebook',
    sku: 'NB-001',
    price: 2500.00,
    stock: 50,
);

echo $product->id . PHP_EOL;    // 1
$product->price = 2800.00;       // ✅ OK: price não é readonly
$product->stock = 45;            // ✅ OK: stock não é readonly

// $product->id = 2;             // ❌ ERRO: Cannot modify readonly property
// $product->name = "Mouse";     // ❌ ERRO: Cannot modify readonly property
```

### 30.5 Readonly Classes (PHP 8.2)

No PHP 8.2, `readonly class` declara que **todas** as propriedades são automaticamente `readonly`. Isso elimina repetição e garante imutabilidade total:
```php
<?php

declare(strict_types=1);

// readonly class: TODAS as propriedades são readonly automaticamente
// Ideal para Value Objects e DTOs (Data Transfer Objects)
readonly class Configuration
{
    public function __construct(
        public string $appName,
        public string $version,
        public bool $debugMode,
        public string $databaseHost,
        public int $databasePort,
    ) {}

    // Métodos normais funcionam — apenas propriedades não podem mudar
    public function getDsn(): string
    {
        return "mysql:host={$this->databaseHost};port={$this->databasePort}";
    }
}

$config = new Configuration(
    appName: 'Minha Aplicação',
    version: '2.0.0',
    debugMode: false,
    databaseHost: 'localhost',
    databasePort: 3306,
);

echo $config->getDsn() . PHP_EOL;
// mysql:host=localhost;port=3306

// Nenhuma propriedade pode ser modificada após criação
// $config->appName = "Outra";     // ❌ ERRO
// $config->debugMode = true;      // ❌ ERRO
```

### 30.6 Property Hooks (PHP 8.4)

Property Hooks permitem definir lógica de `get` e `set` **diretamente na propriedade**, substituindo getters/setters tradicionais com sintaxe integrada à linguagem:
```php
<?php

declare(strict_types=1);

class User
{
    // Hook 'get': transforma o valor ao ler a propriedade
    public string $fullName {
        get => mb_convert_case($this->fullName, MB_CASE_TITLE);
    }

    // Hook 'set': valida/transforma antes de armazenar
    public string $email {
        set {
            if (!filter_var($value, FILTER_VALIDATE_EMAIL)) {
                throw new InvalidArgumentException('Email inválido.');
            }
            $this->email = mb_strtolower($value);
        }
    }

    // Ambos hooks: propriedade virtual baseada em outra
    private float $salaryAmount;

    public float $salary {
        get => $this->salaryAmount;
        set {
            if ($value < 0) {
                throw new InvalidArgumentException('Salário não pode ser negativo.');
            }
            $this->salaryAmount = round($value, 2);
        }
    }

    public function __construct(
        string $fullName,
        string $email,
        float $salary,
    ) {
        $this->fullName = $fullName;
        $this->email = $email;
        $this->salary = $salary;
    }
}

$user = new User('joão silva', 'JOAO@Example.COM', 5000.00);
echo $user->fullName . PHP_EOL;  // João Silva (hook get: title case)
echo $user->email . PHP_EOL;     // joao@example.com (hook set: lowercase)
echo $user->salary . PHP_EOL;    // 5000.00

// $user->email = 'invalido';    // ❌ InvalidArgumentException: Email inválido.
// $user->salary = -100;         // ❌ InvalidArgumentException: Salário não pode ser negativo.
```

### 📝 Exercícios do Capítulo 30

1. Refatore código `switch` existente para usar `match` com comparação estrita
2. Use nullsafe operator para encadear 3+ objetos nullable sem `if` aninhados
3. Crie um `readonly class Money` com propriedades `amount` e `currency`
4. Implemente property hooks para normalizar CEP (formato `xxxxx-xxx`) e telefone
5. Use named arguments para simplificar chamadas a `setcookie()` e `array_slice()`

---

## 31. Novidades do PHP 8.5

O PHP 8.5 traz recursos que tornam o código mais legível, seguro e expressivo. Estes são os recursos que diferenciam o PHP moderno das versões anteriores.

### 31.1 Pipe Operator (`|>`)

O pipe operator transforma chamadas aninhadas como `strtolower(trim(strip_tags($input)))` em uma **sequência legível** da esquerda para a direita. O resultado de cada expressão é passado como argumento para a próxima função:
```php
<?php

declare(strict_types=1);

// ✅ NOVO NO PHP 8.5!
// O pipe operator passa o resultado de uma expressão como PRIMEIRO argumento
// da próxima função — leitura natural da esquerda para a direita

// LEGACY CODE - PHP < 8.5
// Chamadas aninhadas (leitura de dentro para fora — confuso):
// $result = array_unique(array_map('strtolower', array_map('trim', $values)));

// ✅ PHP 8.5: pipe operator — leitura fluente
$values = ['  PHP  ', ' javascript ', '  PHP  ', ' python '];

$result = $values
    |> array_map(trim(...), ...)        // Remove espaços
    |> array_map(strtolower(...), ...)  // Tudo minúsculo
    |> array_unique(...);               // Remove duplicatas

print_r($result); // ['php', 'javascript', 'python']

// ── Exemplo: processamento de texto ──
function processText(string $text): string
{
    return $text
        |> trim(...)
        |> strtolower(...)
        |> ucfirst(...);
}

echo processText('  OLÁ MUNDO  ') . PHP_EOL; // Olá mundo

// ── Exemplo: gerador de slug para URLs ──
function removeAccents(string $text): string
{
    return iconv('UTF-8', 'ASCII//TRANSLIT', $text);
}

function createSlug(string $text): string
{
    return $text
        |> trim(...)
        |> mb_strtolower(...)
        |> removeAccents(...)
        |> preg_replace('/[^a-z0-9]+/', '-', ...)
        |> trim(..., '-');
}

echo createSlug('Título do Artigo!') . PHP_EOL;
// titulo-do-artigo

// ── Exemplo: pipeline de validação ──
function sanitizeInput(string $input): string
{
    return $input
        |> trim(...)
        |> strip_tags(...)
        |> htmlspecialchars(..., ENT_QUOTES, 'UTF-8');
}
```

### 31.2 `array_first()` e `array_last()`

Essas novas funções retornam o primeiro ou último elemento de um array (ou `null` se vazio), sem modificar o array original e sem os problemas de `reset()`/`end()` que alteram o ponteiro interno:
```php
<?php

declare(strict_types=1);

// ✅ NOVO NO PHP 8.5!
// Funções dedicadas para acessar primeiro/último elemento de forma segura

$products = [
    ['id' => 1, 'name' => 'Notebook', 'price' => 2500],
    ['id' => 2, 'name' => 'Mouse',    'price' => 50],
    ['id' => 3, 'name' => 'Teclado',  'price' => 150],
];

// LEGACY CODE - PHP < 8.5
// Abordagens antigas (todas com armadilhas):
// $first = reset($products);              // Efeito colateral: move ponteiro interno
// $first = $products[0] ?? null;          // Falha com arrays associativos
// $last = end($products);                 // Efeito colateral: move ponteiro
// $last = $products[count($products)-1];  // Falha com arrays vazios

// ✅ PHP 8.5: limpo, seguro, sem efeitos colaterais
$first = array_first($products);
$last = array_last($products);

echo $first['name'] . PHP_EOL; // Notebook
echo $last['name'] . PHP_EOL;  // Teclado

// Retorna null para arrays vazios (sem erro!)
$empty = [];
$result = array_first($empty);
var_dump($result); // NULL

// ✅ Funciona com arrays associativos também
$config = [
    'database' => 'mysql',
    'cache' => 'redis',
    'queue' => 'rabbitmq',
];

echo array_first($config) . PHP_EOL; // mysql
echo array_last($config) . PHP_EOL;  // rabbitmq

// Uso prático: buscar resultados
function getLatestLog(): ?string
{
    $logs = file('app.log', FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);
    return $logs !== false ? array_last($logs) : null;
}
```

### 31.3 Clone with

O `clone with` permite clonar objetos `readonly` modificando propriedades específicas — essencial para Value Objects imutáveis onde você precisa criar variações sem alterar o original:
```php
<?php

declare(strict_types=1);

// ✅ NOVO NO PHP 8.5!
// Clona objeto e modifica propriedades em um único passo
// Especialmente útil com readonly classes (onde não dá para mudar depois)

readonly class User
{
    public function __construct(
        public int $id,
        public string $name,
        public string $email,
        public int $age,
    ) {}
}

$user = new User(id: 1, name: 'João', email: 'joao@example.com', age: 25);

// LEGACY CODE - PHP < 8.5
// Com readonly, era impossível "clonar e modificar":
// $updated = clone $user;
// $updated->age = 26;  // ❌ ERRO: Cannot modify readonly property

// ✅ PHP 8.5: clone with — cria cópia com propriedades alteradas
$updated = clone $user with { age: 26 };

echo $user->age . PHP_EOL;     // 25 (original intacto)
echo $updated->age . PHP_EOL;  // 26 (clone modificado)

// Múltiplas propriedades de uma vez
$modified = clone $user with {
    name: 'João Silva',
    email: 'joao.silva@example.com',
    age: 26,
};

// ── Padrão Builder imutável com clone with ──
readonly class ProductBuilder
{
    private function __construct(
        private string $name = '',
        private float $price = 0.0,
        private int $stock = 0,
        private string $category = '',
    ) {}

    public static function create(): self
    {
        return new self();
    }

    public function withName(string $name): self
    {
        // Cada chamada retorna uma NOVA instância
        return clone $this with { name: $name };
    }

    public function withPrice(float $price): self
    {
        return clone $this with { price: $price };
    }

    public function withStock(int $stock): self
    {
        return clone $this with { stock: $stock };
    }

    public function withCategory(string $category): self
    {
        return clone $this with { category: $category };
    }

    public function build(): array
    {
        return [
            'name' => $this->name,
            'price' => $this->price,
            'stock' => $this->stock,
            'category' => $this->category,
        ];
    }
}

// Uso fluente — cada passo é imutável
$product = ProductBuilder::create()
    ->withName('Notebook')
    ->withPrice(2500.00)
    ->withStock(10)
    ->withCategory('Eletrônicos')
    ->build();

print_r($product);
```

### 31.4 Atributo `#[\NoDiscard]`

O atributo `#[\NoDiscard]` emite um aviso quando o valor de retorno de uma função é ignorado. Perfeito para operações críticas cujo resultado nunca deve ser descartado, como validações e transações:
```php
<?php

declare(strict_types=1);

// ✅ NOVO NO PHP 8.5!
// Marca métodos cujo valor de retorno NÃO DEVE ser ignorado
// Previne bugs onde o desenvolvedor esquece de verificar o resultado

class PaymentGateway
{
    // ⚠️ O resultado DEVE ser verificado — ignorar pode causar bugs graves
    #[\NoDiscard("O resultado do pagamento deve ser verificado")]
    public function processPayment(float $amount): PaymentResult
    {
        // Simulação de processamento
        $success = $amount <= 10000.00;
        return new PaymentResult(
            success: $success,
            transactionId: $success ? 'TXN' . random_int(1000, 9999) : '',
            message: $success ? 'Pagamento aprovado' : 'Limite excedido',
        );
    }

    #[\NoDiscard]
    public function validateCard(string $cardNumber): bool
    {
        // Validação básica: 16 dígitos
        return (bool) preg_match('/^\d{16}$/', $cardNumber);
    }
}

readonly class PaymentResult
{
    public function __construct(
        public bool $success,
        public string $transactionId,
        public string $message,
    ) {}
}

$gateway = new PaymentGateway();

// ❌ Warning em tempo de compilação/análise estática:
// "O resultado do pagamento deve ser verificado"
// $gateway->processPayment(100.00);  // Resultado descartado!

// ✅ Forma correta: sempre verificar o resultado
$result = $gateway->processPayment(100.00);

if (!$result->success) {
    throw new RuntimeException("Pagamento falhou: {$result->message}");
}

echo "✅ {$result->message} — Transação: {$result->transactionId}" . PHP_EOL;

// ✅ Também aceito: usar diretamente em condição
if ($gateway->validateCard('1234567890123456')) {
    echo 'Cartão válido!' . PHP_EOL;
}

// ══════════════════════════════════════
// (void) cast — descarte intencional
// ══════════════════════════════════════

// Se você SABE que não precisa do retorno, use (void) para silenciar o aviso:
(void) $gateway->processPayment(0.01); // ✅ Sem warning — descarte explícito

// ── Funções standalone ──

#[\NoDiscard]
function getPhpVersion(): string
{
    return 'PHP 8.5';
}

// ❌ Warning: The return value of function getPhpVersion() should
// either be used or intentionally ignored by casting it as (void)
// getPhpVersion();

// ✅ Correto: usar o valor
$version = getPhpVersion();
echo $version . PHP_EOL;

// ✅ Correto: descarte intencional com (void)
(void) getPhpVersion();

// ── Quando usar #[\NoDiscard]? ──
// ✅ Métodos que retornam status de operação (pagamento, validação)
// ✅ Funções puras cujo resultado é o único propósito
// ✅ Operações que retornam erros (em vez de lançar exceções)
// ❌ NÃO use em setters, loggers ou side-effect functions
```

### 31.5 Extensão URI Nativa

O PHP 8.5 traz suporte nativo para manipulação de URIs com as classes `Uri\Rfc3986\Uri` e `Uri\WhatWg\Url`, eliminando a necessidade de `parse_url()` e manipulação manual de strings:
```php
<?php

declare(strict_types=1);

// ✅ NOVO NO PHP 8.5!
// Parsing e manipulação de URIs com validação RFC 3986

use Uri\Rfc3986\Uri;

// LEGACY CODE - PHP < 8.5
// parse_url() retorna array associativo — sem validação, sem OOP:
// $parts = parse_url('https://example.com/path?q=1');
// $scheme = $parts['scheme'] ?? null;  // Pode falhar silenciosamente

// ✅ PHP 8.5: classe URI com validação automática
$uri = new Uri('https://user:pass@example.com:8080/api/v1?page=1&limit=10#results');

echo $uri->getScheme() . PHP_EOL;    // https
echo $uri->getUserInfo() . PHP_EOL;  // user:pass
echo $uri->getHost() . PHP_EOL;      // example.com
echo $uri->getPort() . PHP_EOL;      // 8080
echo $uri->getPath() . PHP_EOL;      // /api/v1
echo $uri->getQuery() . PHP_EOL;     // page=1&limit=10
echo $uri->getFragment() . PHP_EOL;  // results

// ✅ Manipulação imutável — métodos with*() retornam NOVA instância
$newUri = $uri
    ->withHost('api.example.com')
    ->withPath('/v2/users')
    ->withQuery('active=true');

echo (string) $newUri . PHP_EOL;
// https://user:pass@api.example.com:8080/v2/users?active=true#results

// ✅ Validação automática — URIs inválidas lançam exceção
try {
    $invalid = new Uri('http://domínio inválido.com');
} catch (InvalidArgumentException $e) {
    echo "URI inválida: {$e->getMessage()}" . PHP_EOL;
}

// ── Uso prático: construtor de URL para API ──
function buildApiUrl(string $endpoint, array $params = []): string
{
    $base = new Uri('https://api.example.com/v1');

    $uri = $base->withPath($base->getPath() . '/' . ltrim($endpoint, '/'));

    if (!empty($params)) {
        $uri = $uri->withQuery(http_build_query($params));
    }

    return (string) $uri;
}

echo buildApiUrl('users', ['page' => 1, 'limit' => 10]) . PHP_EOL;
// https://api.example.com/v1/users?page=1&limit=10

echo buildApiUrl('products/search', ['q' => 'notebook']) . PHP_EOL;
// https://api.example.com/v1/products/search?q=notebook
```

### 31.6 Closures em expressões constantes

No PHP 8.5, closures podem ser usadas em contextos de expressões constantes (como valores padrão de parâmetros e propriedades), permitindo callbacks configurados em tempo de definição:
```php
<?php

declare(strict_types=1);

// ✅ NOVO NO PHP 8.5!
// Closures podem ser usadas como valores de constantes de classe

class Calculator
{
    // Operações definidas como constantes — imutáveis e reutilizáveis
    public const DOUBLE = fn(int|float $x): int|float => $x * 2;
    public const TRIPLE = fn(int|float $x): int|float => $x * 3;
    public const SQUARE = fn(int|float $x): int|float => $x ** 2;

    // Mapa de operações
    public const OPERATIONS = [
        'double' => self::DOUBLE,
        'triple' => self::TRIPLE,
        'square' => self::SQUARE,
    ];

    // Aplicar operação por nome
    public static function apply(string $operation, int|float $value): int|float
    {
        $fn = self::OPERATIONS[$operation]
            ?? throw new InvalidArgumentException("Operação desconhecida: {$operation}");

        return $fn($value);
    }
}

// Uso direto das constantes
$double = Calculator::DOUBLE;
echo $double(5) . PHP_EOL; // 10

// Uso via mapa de operações
echo Calculator::apply('square', 7) . PHP_EOL; // 49

// ── Exemplo prático: validadores como constantes ──
class Validators
{
    public const EMAIL = fn(string $v): bool =>
        filter_var($v, FILTER_VALIDATE_EMAIL) !== false;

    public const CPF = fn(string $v): bool =>
        (bool) preg_match('/^\d{3}\.\d{3}\.\d{3}-\d{2}$/', $v);

    public const PHONE = fn(string $v): bool =>
        (bool) preg_match('/^\(\d{2}\) \d{4,5}-\d{4}$/', $v);

    public static function validate(string $type, string $value): bool
    {
        return match ($type) {
            'email' => (self::EMAIL)($value),
            'cpf' => (self::CPF)($value),
            'phone' => (self::PHONE)($value),
            default => throw new InvalidArgumentException("Validador '{$type}' não existe."),
        };
    }
}

echo Validators::validate('email', 'teste@example.com') ? 'Válido' : 'Inválido';
// Válido

echo PHP_EOL;

echo Validators::validate('cpf', '123.456.789-00') ? 'Válido' : 'Inválido';
// Válido
```

### 📝 Exercícios do Capítulo 31

1. Refatore código com chamadas aninhadas (`strtolower(trim(strip_tags(...)))`) usando pipe operator
2. Use `array_first()` e `array_last()` para acessar resultados de queries com segurança
3. Crie value objects imutáveis (`Money`, `Email`, `Address`) usando `readonly class` + `clone with`
4. Adicione `#[\NoDiscard]` em métodos que retornam status de operações críticas
5. Construa um serviço de URLs que usa a extensão URI nativa para montar endpoints de API

---

## 32. Sistema de Tipos Avançado

O PHP moderno possui um sistema de tipos robusto. Dominar union types, intersection types, `mixed` e `never` é essencial para escrever código seguro e expressivo.

### 32.1 Union Types (PHP 8.0+)

Union types permitem que um parâmetro, retorno ou propriedade aceite **múltiplos tipos**, separados por `|`. Isso substitui `@param mixed` por tipoóes explícitas e verificáveis pelo engine:
```php
<?php

declare(strict_types=1);

// Union type: parâmetro aceita MÚLTIPLOS tipos (separados por |)
function processValue(int|float|string $value): int|float
{
    // Cada tipo requer tratamento adequado
    if (is_string($value)) {
        // Para strings, tenta converter para inteiro
        return (int) $value;
    }

    // Para numéricos, dobra o valor
    return $value * 2;
}

echo processValue(5) . PHP_EOL;       // 10
echo processValue(5.5) . PHP_EOL;     // 11.0
echo processValue('10') . PHP_EOL;    // 10

// ✅ Union types em propriedades — útil para configurações flexíveis
readonly class DatabaseConfig
{
    public function __construct(
        // Porta pode ser int (3306) ou string ("3306")
        public int|string $port,
        // Debug pode ser bool (true) ou int (1/0) para compatibilidade
        public bool|int $debug,
        // Timeout em segundos (int) ou como float para precisão
        public int|float $timeout = 30,
    ) {}
}

$config = new DatabaseConfig(port: 3306, debug: true);
$config2 = new DatabaseConfig(port: '3306', debug: 1, timeout: 30.5);
```

### 32.2 Intersection Types (PHP 8.1+)

Intersection types (com `&`) exigem que um valor implemente **todos** os tipos listados simultaneamente. Use quando precisa garantir que um objeto cumpre múltiplas interfaces:
```php
<?php

declare(strict_types=1);

// Intersection type: parâmetro DEVE implementar TODAS as interfaces (separadas por &)
// Garante que o objeto satisfaz múltiplos contratos simultaneamente

interface AuthenticatableInterface
{
    public function authenticate(): bool;
}

interface TraceableInterface
{
    public function getAuditLogs(): array;
}

interface SerializableEntityInterface
{
    public function toArray(): array;
}

// A função exige que o objeto implemente AMBAS interfaces
function processSecureEntity(AuthenticatableInterface&TraceableInterface $entity): void
{
    if ($entity->authenticate()) {
        $logs = $entity->getAuditLogs();
        echo 'Entidade autenticada. Total de logs: ' . count($logs) . PHP_EOL;
    }
}

// Classe que satisfaz a intersection
class AdminUser implements AuthenticatableInterface, TraceableInterface, SerializableEntityInterface
{
    public function authenticate(): bool
    {
        return true;
    }

    public function getAuditLogs(): array
    {
        return ['login em 2026-02-09', 'ação administrativa em 2026-02-09'];
    }

    public function toArray(): array
    {
        return ['role' => 'admin'];
    }
}

$admin = new AdminUser();
processSecureEntity($admin); // ✅ Funciona: implementa ambas interfaces

// ❌ Classe que implementa apenas uma interface NÃO funciona
// class BasicUser implements AuthenticatableInterface { ... }
// processSecureEntity(new BasicUser()); // TypeError!
```

### 32.3 O tipo `mixed`

`mixed` é o tipo que aceita **qualquer valor** (`int|float|string|bool|array|object|null`). Use quando realmente não há restrição de tipo — mas prefira union types específicos sempre que possível:
```php
<?php

declare(strict_types=1);

// mixed: aceita QUALQUER tipo (int, float, string, array, object, null, bool, etc.)
// Use quando realmente precisa aceitar qualquer coisa (evite quando possível)
function inspect(mixed $value): string
{
    return match (true) {
        is_int($value) => "Inteiro: {$value}",
        is_float($value) => "Float: {$value}",
        is_string($value) => 'String: "' . $value . '"',
        is_bool($value) => 'Boolean: ' . ($value ? 'true' : 'false'),
        is_array($value) => 'Array com ' . count($value) . ' elemento(s)',
        is_object($value) => 'Objeto: ' . $value::class,
        is_null($value) => 'Null',
        default => 'Tipo desconhecido',
    };
}

// mixed aceita literalmente qualquer tipo
echo inspect(42) . PHP_EOL;             // Inteiro: 42
echo inspect(3.14) . PHP_EOL;           // Float: 3.14
echo inspect('texto') . PHP_EOL;        // String: "texto"
echo inspect([1, 2, 3]) . PHP_EOL;      // Array com 3 elemento(s)
echo inspect(null) . PHP_EOL;           // Null
echo inspect(new stdClass()) . PHP_EOL; // Objeto: stdClass

// ⚠️ CUIDADO: mixed !== sem tipo. Declarar mixed é EXPLÍCITO —
// mostra que a decisão de aceitar qualquer tipo foi intencional.
// Já a ausência de tipos pode ser descuido ou código legado.
```

### 32.4 O tipo `never`

`never` indica que uma função **nunca retorna normalmente**: ela sempre lança uma exceção, chama `exit`, ou entra em loop infinito. O análise estática usa isso para detectar código inalcançável:
```php
<?php

declare(strict_types=1);

// never: indica que a função NUNCA retorna normalmente
// Ela SEMPRE lança exceção, executa exit(), ou entra em loop infinito
// Útil para análise estática: código após uma chamada never é inalcançável

function abort(string $message, int $code = 500): never
{
    throw new RuntimeException("[Erro {$code}] {$message}");
}

function redirect(string $url): never
{
    header("Location: {$url}");
    exit;
}

function fatalError(string $message): never
{
    // Loga o erro antes de encerrar
    error_log("[FATAL] {$message}");
    exit(1);
}

// ✅ Uso prático: validação que aborta execução
function processOrder(mixed $orderId): int
{
    if (!is_int($orderId) || $orderId <= 0) {
        // abort() tem retorno never — o PHP sabe que código abaixo nunca executa
        abort('ID do pedido deve ser um inteiro positivo.', 400);
    }

    // Este código é alcançado SOMENTE se $orderId for válido
    // Análise estática deduz que $orderId é int e > 0 aqui
    return $orderId * 2;
}
```

### 📝 Exercícios do Capítulo 32

1. Crie função com union type que aceita `int|string` como ID e normaliza para `int`
2. Use intersection type para exigir que um objeto implemente `Countable&Iterator`
3. Implemente função `inspect()` com `mixed` que retorna informações detalhadas do tipo
4. Use `never` em funções de error handler e redirect do seu framework
5. Combine union types com nullable: `?int|string` vs `int|string|null`

---

# Parte V: Projetos Práticos

---

## 33. Formulários e Validação

Formulários são o principal canal de entrada de dados do usuário em aplicações web. Processar e **validar** esses dados corretamente é essencial para segurança e integridade — nunca confie em dados vindos do cliente.

### 33.1 Processamento de formulário básico

O fluxo básico envolve: exibir o formulário HTML, receber os dados via `$_POST`, sanitizar a entrada, validar os campos, e processar ou retornar erros:
```php
<?php

declare(strict_types=1);

// ── HTML do formulário (formulario.html) ──
/*
<!DOCTYPE html>
<html lang="pt-BR">
<body>
    <form method="POST" action="process.php">
        <input type="text" name="name" required>
        <input type="email" name="email" required>
        <input type="number" name="age" min="18" max="120">
        <button type="submit">Enviar</button>
    </form>
</body>
</html>
*/

// ── Processamento no servidor (process.php) ──

// Verificar se é requisição POST — jamais processe GET como ação
if ($_SERVER['REQUEST_METHOD'] !== 'POST') {
    http_response_code(405);
    exit('Método não permitido.');
}

// Obter dados do formulário com valores padrão seguros
$name = trim($_POST['name'] ?? '');
$email = trim($_POST['email'] ?? '');
$age = (int) ($_POST['age'] ?? 0);

// Validação manual — abordagem mais simples
$errors = [];

if (mb_strlen($name) < 3) {
    $errors['name'] = 'Nome deve ter pelo menos 3 caracteres.';
}

if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
    $errors['email'] = 'Email inválido.';
}

if ($age < 18 || $age > 120) {
    $errors['age'] = 'Idade deve estar entre 18 e 120 anos.';
}

// Exibir resultado
if (!empty($errors)) {
    // Mostrar erros — em produção, retorne JSON ou re-renderize o formulário
    foreach ($errors as $field => $message) {
        echo "❌ {$field}: {$message}" . PHP_EOL;
    }
} else {
    // ✅ Todos os dados validados — seguro para processar
    echo "✅ Dados válidos!" . PHP_EOL;
    echo "Nome: " . htmlspecialchars($name, ENT_QUOTES, 'UTF-8') . PHP_EOL;
    echo "Email: " . htmlspecialchars($email, ENT_QUOTES, 'UTF-8') . PHP_EOL;
    echo "Idade: {$age}" . PHP_EOL;
}
```

### 33.2 Classe Validator reutilizável

Uma classe `Validator` centraliza todas as regras de validação em um único lugar, tornando o código reutilizável e testável. Cada regra é um método que adiciona erros a uma lista interna:
```php
<?php

declare(strict_types=1);

class Validator
{
    // Erros agrupados por campo
    private array $errors = [];

    // Valida dados contra regras. Retorna true se TODOS os dados forem válidos
    public function validate(array $data, array $rules): bool
    {
        $this->errors = [];

        foreach ($rules as $field => $fieldRules) {
            $value = $data[$field] ?? null;

            // Aplicar cada regra ao campo
            foreach ($fieldRules as $rule) {
                $this->applyRule($field, $value, $rule);
            }
        }

        return empty($this->errors);
    }

    // Aplica uma regra individual ao valor do campo
    private function applyRule(string $field, mixed $value, string $rule): void
    {
        [$ruleName, $parameter] = $this->parseRule($rule);

        $valid = match ($ruleName) {
            'required' => $value !== null && $value !== '',
            'email' => filter_var($value, FILTER_VALIDATE_EMAIL) !== false,
            'min' => is_string($value) && mb_strlen($value) >= (int) $parameter,
            'max' => is_string($value) && mb_strlen($value) <= (int) $parameter,
            'numeric' => is_numeric($value),
            'integer' => filter_var($value, FILTER_VALIDATE_INT) !== false,
            'url' => filter_var($value, FILTER_VALIDATE_URL) !== false,
            'between' => $this->checkBetween($value, $parameter),
            default => true,
        };

        if (!$valid) {
            $this->errors[$field][] = $this->getMessage($ruleName, $field, $parameter);
        }
    }

    // Separa nome da regra e parâmetro: "min:3" → ["min", "3"]
    private function parseRule(string $rule): array
    {
        if (str_contains($rule, ':')) {
            return explode(':', $rule, 2);
        }

        return [$rule, null];
    }

    // Verifica se valor está entre min e max: "between:18,120"
    private function checkBetween(mixed $value, ?string $parameter): bool
    {
        if ($parameter === null || !is_numeric($value)) {
            return false;
        }

        [$min, $max] = explode(',', $parameter);
        return (float) $value >= (float) $min && (float) $value <= (float) $max;
    }

    // Mensagens de erro em português
    private function getMessage(string $rule, string $field, ?string $parameter): string
    {
        return match ($rule) {
            'required' => "O campo '{$field}' é obrigatório.",
            'email' => "O campo '{$field}' deve ser um email válido.",
            'min' => "O campo '{$field}' deve ter no mínimo {$parameter} caracteres.",
            'max' => "O campo '{$field}' deve ter no máximo {$parameter} caracteres.",
            'numeric' => "O campo '{$field}' deve ser numérico.",
            'integer' => "O campo '{$field}' deve ser um número inteiro.",
            'url' => "O campo '{$field}' deve ser uma URL válida.",
            'between' => "O campo '{$field}' deve estar entre {$parameter}.",
            default => "O campo '{$field}' é inválido.",
        };
    }

    public function getErrors(): array
    {
        return $this->errors;
    }

    public function hasErrors(): bool
    {
        return !empty($this->errors);
    }
}

// Uso
$validator = new Validator();

$data = [
    'name' => 'João',
    'email' => 'joao@example.com',
    'age' => '25',
    'password' => '123',  // Muito curta!
];

$rules = [
    'name' => ['required', 'min:3', 'max:100'],
    'email' => ['required', 'email'],
    'age' => ['required', 'integer'],
    'password' => ['required', 'min:8'],
];

if ($validator->validate($data, $rules)) {
    echo '✅ Todos os dados são válidos!' . PHP_EOL;
} else {
    echo '❌ Erros de validação:' . PHP_EOL;
    foreach ($validator->getErrors() as $field => $messages) {
        foreach ($messages as $message) {
            echo "  - {$message}" . PHP_EOL;
        }
    }
    // ❌ Erros de validação:
    //   - O campo 'password' deve ter no mínimo 8 caracteres.
}
```

### 33.3 Proteção CSRF

CSRF (Cross-Site Request Forgery) engana o navegador do usuário para enviar requisições indesejadas. A defesa é um **token único** por sessão/formulário que o atacante não consegue adivinhar:
```php
<?php

declare(strict_types=1);

session_start();

// Classe para proteção contra Cross-Site Request Forgery
class CsrfProtection
{
    private const TOKEN_KEY = 'csrf_token';

    // Gera ou recupera token da sessão
    public static function generateToken(): string
    {
        if (!isset($_SESSION[self::TOKEN_KEY])) {
            // Token criptograficamente seguro com 32 bytes (64 hex chars)
            $_SESSION[self::TOKEN_KEY] = bin2hex(random_bytes(32));
        }

        return $_SESSION[self::TOKEN_KEY];
    }

    // Valida token recebido contra o da sessão (timing-safe)
    public static function validateToken(string $token): bool
    {
        if (!isset($_SESSION[self::TOKEN_KEY])) {
            return false;
        }

        // hash_equals() previne ataques de timing — compara em tempo constante
        return hash_equals($_SESSION[self::TOKEN_KEY], $token);
    }

    // Gera campo hidden HTML com o token
    public static function inputField(): string
    {
        $token = self::generateToken();
        return sprintf(
            '<input type="hidden" name="csrf_token" value="%s">',
            htmlspecialchars($token, ENT_QUOTES, 'UTF-8'),
        );
    }

    // Regenera token após uso bem-sucedido (one-time token)
    public static function regenerate(): void
    {
        unset($_SESSION[self::TOKEN_KEY]);
    }
}

// ── No formulário HTML ──
/*
<form method="POST" action="process.php">
    <?= CsrfProtection::inputField() ?>
    <input type="text" name="name">
    <button type="submit">Enviar</button>
</form>
*/

// ── No processamento ──
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $token = $_POST['csrf_token'] ?? '';

    if (!CsrfProtection::validateToken($token)) {
        http_response_code(403);
        exit('⛔ Token CSRF inválido! Possível tentativa de ataque.');
    }

    // Token válido — regenerar para próxima requisição
    CsrfProtection::regenerate();

    // Processar formulário com segurança...
    echo '✅ Formulário processado com segurança.' . PHP_EOL;
}
```

### 📝 Exercícios do Capítulo 33

1. Crie formulário de cadastro completo com validação de nome, email, CPF e senha forte
2. Implemente regra personalizada de validação de CPF no `Validator`
3. Adicione proteção CSRF a todos os formulários do seu projeto
4. Crie validador de senha forte (mínimo 8 chars, maiúsculas, números, caracteres especiais)
5. Faça formulário de upload com validação de tipo MIME e tamanho máximo

---

## 34. Sessões e Cookies

Sessões armazenam dados do usuário **no servidor** entre requisições (identificados por um cookie de sessão). Cookies armazenam dados **no navegador** do cliente. Juntos, permitem autenticação, preferências persistentes e carrinhos de compra.

### 34.1 Trabalhando com sessões

`session_start()` inicia ou retoma uma sessão. Os dados ficam em `$_SESSION` e persistem até o fechamento do navegador ou destruição explícita:
```php
<?php

declare(strict_types=1);

// session_start() DEVE ser chamado antes de qualquer output HTML
session_start();

// ── Armazenar dados na sessão ──
$_SESSION['user_id'] = 123;
$_SESSION['user_name'] = 'João Silva';
$_SESSION['user_email'] = 'joao@example.com';

// ── Ler dados ──
$name = $_SESSION['user_name'] ?? 'Visitante';
echo "Olá, {$name}!" . PHP_EOL;

// ── Verificar se existe ──
function isLoggedIn(): bool
{
    return isset($_SESSION['user_id']);
}

if (isLoggedIn()) {
    echo 'Usuário autenticado.' . PHP_EOL;
} else {
    echo 'Usuário não autenticado.' . PHP_EOL;
}

// ── Destruir sessão (logout completo) ──
function destroySession(): void
{
    // 1. Limpar todos os dados
    $_SESSION = [];

    // 2. Destruir cookie de sessão
    if (ini_get('session.use_cookies')) {
        $params = session_get_cookie_params();
        setcookie(
            name: session_name(),
            value: '',
            expires_or_options: time() - 42000,
            path: $params['path'],
            domain: $params['domain'],
            secure: $params['secure'],
            httponly: $params['httponly'],
        );
    }

    // 3. Destruir a sessão no servidor
    session_destroy();
}
```

### 34.2 Sistema de autenticação

Um sistema completo de autenticação combina sessões, hash de senhas e proteção contra ataques. A classe `Auth` encapsula toda a lógica de login, logout, verificação e timeout:
```php
<?php

declare(strict_types=1);

session_start();

class Auth
{
    private const SESSION_USER_KEY = 'authenticated_user';

    // Registra usuário na sessão (login)
    public static function login(int $userId, array $userData): void
    {
        // ⚠️ CRÍTICO: regenerar ID da sessão após autenticação
        // Previne Session Fixation Attack
        session_regenerate_id(delete_old_session: true);

        $_SESSION[self::SESSION_USER_KEY] = [
            'id' => $userId,
            'name' => $userData['name'],
            'email' => $userData['email'],
            'logged_at' => time(),
        ];
    }

    // Remove usuário da sessão (logout)
    public static function logout(): void
    {
        unset($_SESSION[self::SESSION_USER_KEY]);
        session_regenerate_id(delete_old_session: true);
    }

    // Verifica se há usuário autenticado
    public static function isLoggedIn(): bool
    {
        return isset($_SESSION[self::SESSION_USER_KEY]);
    }

    // Retorna dados do usuário autenticado
    public static function getUser(): ?array
    {
        return $_SESSION[self::SESSION_USER_KEY] ?? null;
    }

    // Retorna ID do usuário autenticado
    public static function getUserId(): ?int
    {
        return $_SESSION[self::SESSION_USER_KEY]['id'] ?? null;
    }

    // Protege página — redireciona se não logado
    public static function requireLogin(string $redirectUrl = '/login.php'): void
    {
        if (!self::isLoggedIn()) {
            header("Location: {$redirectUrl}");
            exit;
        }
    }

    // Verifica timeout de sessão por inatividade
    public static function checkTimeout(int $maxIdleSeconds = 1800): void
    {
        if (!self::isLoggedIn()) {
            return;
        }

        $loggedAt = $_SESSION[self::SESSION_USER_KEY]['logged_at'] ?? 0;

        if ((time() - $loggedAt) > $maxIdleSeconds) {
            self::logout();
            header('Location: /login.php?reason=timeout');
            exit;
        }

        // Resetar timer a cada verificação
        $_SESSION[self::SESSION_USER_KEY]['logged_at'] = time();
    }
}

// ── Página de login (login.php) ──
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $email = trim($_POST['email'] ?? '');
    $password = $_POST['password'] ?? '';

    // Simulação de busca no banco de dados
    $storedUser = [
        'id' => 1,
        'name' => 'João Silva',
        'email' => 'joao@example.com',
        'password_hash' => password_hash('senha123', PASSWORD_ARGON2ID),
    ];

    // Verificar credenciais
    if ($email === $storedUser['email']
        && password_verify($password, $storedUser['password_hash'])
    ) {
        Auth::login($storedUser['id'], $storedUser);
        header('Location: /dashboard.php');
        exit;
    }

    echo '❌ Email ou senha incorretos.' . PHP_EOL;
}

// ── Página protegida (dashboard.php) ──
// Auth::requireLogin();
// Auth::checkTimeout(1800); // 30 minutos de inatividade
//
// $user = Auth::getUser();
// echo "Bem-vindo, {$user['name']}!";
```

### 34.3 Cookies seguros

Cookies devem ser configurados com flags de segurança: `HttpOnly` (inacessível via JavaScript), `Secure` (apenas HTTPS), e `SameSite` (proteção CSRF). A classe `Cookie` abstrai essas boas práticas:
```php
<?php

declare(strict_types=1);

// Classe para gerenciamento seguro de cookies
class Cookie
{
    // Criar cookie com opções de segurança
    public static function set(
        string $name,
        string $value,
        int $expirationDays = 30,
        bool $httpOnly = true,
        bool $secure = true,
        string $sameSite = 'Lax',
    ): void {
        setcookie(
            name: $name,
            value: $value,
            expires_or_options: [
                'expires' => time() + ($expirationDays * 86400),
                'path' => '/',
                'domain' => '',
                'secure' => $secure,      // Apenas HTTPS
                'httponly' => $httpOnly,   // Inacessível via JavaScript
                'samesite' => $sameSite,  // Proteção CSRF
            ],
        );
    }

    // Obter valor do cookie com padrão seguro
    public static function get(string $name, string $default = ''): string
    {
        return $_COOKIE[$name] ?? $default;
    }

    // Verificar se cookie existe
    public static function exists(string $name): bool
    {
        return isset($_COOKIE[$name]);
    }

    // Deletar cookie
    public static function delete(string $name): void
    {
        setcookie(
            name: $name,
            value: '',
            expires_or_options: time() - 3600,
            path: '/',
        );
        unset($_COOKIE[$name]);
    }
}

// Uso
Cookie::set(name: 'theme', value: 'dark', expirationDays: 365);
Cookie::set(name: 'language', value: 'pt-BR', expirationDays: 365);

// Ler preferências do usuário
$theme = Cookie::get('theme', 'light');
$language = Cookie::get('language', 'en-US');

echo "Tema: {$theme}" . PHP_EOL;      // dark
echo "Idioma: {$language}" . PHP_EOL;  // pt-BR

// Verificar existência
if (Cookie::exists('last_visit')) {
    echo 'Última visita: ' . Cookie::get('last_visit') . PHP_EOL;
}

// Remover cookie
Cookie::delete('old_cookie');
```

### 📝 Exercícios do Capítulo 34

1. Implemente sistema completo de login/logout com sessões
2. Crie funcionalidade "lembrar-me" usando cookies seguros + token no banco
3. Faça carrinho de compras usando `$_SESSION` com métodos `addItem()`, `removeItem()`, `getTotal()`
4. Implemente timeout de sessão por inatividade (30 minutos)
5. Crie sistema de preferências do usuário (tema, idioma) persistido com cookies

---

## 35. Banco de Dados com PDO

PDO (PHP Data Objects) é a interface unificada para acesso a bancos de dados. Suporta prepared statements que previnem SQL injection por design, e funciona com MySQL, PostgreSQL, SQLite e outros.

### 35.1 Conexão e configuração

A conexão PDO usa um DSN (Data Source Name) que identifica o driver, host e banco. Configure para lançar exceções em erros e retornar dados como arrays associativos:
```php
<?php

declare(strict_types=1);

// Classe Singleton para conexão com banco de dados
// Garante apenas UMA conexão por requisição (eficiente)
class Database
{
    private static ?PDO $connection = null;

    // Impedir instanciação direta
    private function __construct() {}

    public static function connect(): PDO
    {
        if (self::$connection === null) {
            $host = 'localhost';
            $dbName = 'my_database';
            $username = 'user';
            $password = 'secret';

            $dsn = "mysql:host={$host};dbname={$dbName};charset=utf8mb4";

            self::$connection = new PDO(
                dsn: $dsn,
                username: $username,
                password: $password,
                options: [
                    // Lançar exceção em vez de silenciar erros
                    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
                    // Retornar arrays associativos por padrão
                    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
                    // Usar prepared statements nativos (mais seguro)
                    PDO::ATTR_EMULATE_PREPARES => false,
                ],
            );
        }

        return self::$connection;
    }
}

// Uso: uma única conexão compartilhada
$pdo = Database::connect();
```

### 35.2 CRUD completo com Repository

O padrão Repository encapsula toda a lógica de acesso a dados, mantendo o resto da aplicação desacoplado do banco. Cada entidade tem seu próprio Repository:
```php
<?php

declare(strict_types=1);

// Repository: encapsula toda lógica de acesso a dados
class UserRepository
{
    public function __construct(
        private readonly PDO $pdo,
    ) {}

    // ── CREATE ──
    public function create(array $data): int
    {
        $sql = "INSERT INTO users (name, email, password_hash, created_at)
                VALUES (:name, :email, :password_hash, NOW())";

        $stmt = $this->pdo->prepare($sql);

        $stmt->execute([
            'name' => $data['name'],
            'email' => $data['email'],
            'password_hash' => password_hash($data['password'], PASSWORD_ARGON2ID),
        ]);

        return (int) $this->pdo->lastInsertId();
    }

    // ── READ (um registro por ID) ──
    public function findById(int $id): ?array
    {
        $sql = "SELECT * FROM users WHERE id = :id";

        $stmt = $this->pdo->prepare($sql);
        $stmt->execute(['id' => $id]);

        $result = $stmt->fetch();
        return $result !== false ? $result : null;
    }

    // ── READ (todos os registros) ──
    public function findAll(): array
    {
        $sql = "SELECT * FROM users ORDER BY name ASC";
        $stmt = $this->pdo->query($sql);
        return $stmt->fetchAll();
    }

    // ── READ (por email) ──
    public function findByEmail(string $email): ?array
    {
        $sql = "SELECT * FROM users WHERE email = :email";

        $stmt = $this->pdo->prepare($sql);
        $stmt->execute(['email' => $email]);

        $result = $stmt->fetch();
        return $result !== false ? $result : null;
    }

    // ── UPDATE ──
    public function update(int $id, array $data): bool
    {
        $sql = "UPDATE users
                SET name = :name, email = :email, updated_at = NOW()
                WHERE id = :id";

        $stmt = $this->pdo->prepare($sql);

        return $stmt->execute([
            'id' => $id,
            'name' => $data['name'],
            'email' => $data['email'],
        ]);
    }

    // ── DELETE ──
    public function delete(int $id): bool
    {
        $sql = "DELETE FROM users WHERE id = :id";
        $stmt = $this->pdo->prepare($sql);
        return $stmt->execute(['id' => $id]);
    }

    // ── PAGINAÇÃO ──
    public function paginate(int $page = 1, int $perPage = 10): array
    {
        $offset = ($page - 1) * $perPage;

        $sql = "SELECT * FROM users ORDER BY id DESC LIMIT :limit OFFSET :offset";

        $stmt = $this->pdo->prepare($sql);
        // bindValue com tipo explícito para LIMIT/OFFSET (obrigatório!)
        $stmt->bindValue(':limit', $perPage, PDO::PARAM_INT);
        $stmt->bindValue(':offset', $offset, PDO::PARAM_INT);
        $stmt->execute();

        return $stmt->fetchAll();
    }

    // ── CONTAGEM ──
    public function count(): int
    {
        $sql = "SELECT COUNT(*) FROM users";
        $stmt = $this->pdo->query($sql);
        return (int) $stmt->fetchColumn();
    }
}

// Uso completo
$pdo = Database::connect();
$repo = new UserRepository($pdo);

// Criar
$id = $repo->create([
    'name' => 'João Silva',
    'email' => 'joao@example.com',
    'password' => 'senhaForte123!',
]);
echo "Usuário criado com ID: {$id}" . PHP_EOL;

// Buscar
$user = $repo->findById($id);
echo "Nome: {$user['name']}" . PHP_EOL;

// Atualizar
$repo->update($id, [
    'name' => 'João Silva Santos',
    'email' => 'joao.santos@example.com',
]);

// Listar com paginação
$users = $repo->paginate(page: 1, perPage: 10);
$total = $repo->count();
echo "Exibindo " . count($users) . " de {$total} usuários." . PHP_EOL;

// Deletar
$repo->delete($id);
```

### 35.3 Transações

Transações garantem que múltiplas operações no banco sejam executadas **atomicamente** — ou todas succedem, ou todas são revertidas. Essenciais para integridade de dados:
```php
<?php

declare(strict_types=1);

class OrderService
{
    public function __construct(
        private readonly PDO $pdo,
    ) {}

    // Transação: garante que TODAS as operações são atômicas
    // Se qualquer uma falhar, NENHUMA é persistida (rollback)
    public function createOrder(int $userId, array $items): int
    {
        try {
            // 1. Iniciar transação
            $this->pdo->beginTransaction();

            // 2. Inserir pedido
            $sql = "INSERT INTO orders (user_id, total, status, created_at)
                    VALUES (:user_id, :total, 'pending', NOW())";

            $stmt = $this->pdo->prepare($sql);
            $total = array_sum(array_column($items, 'price'));

            $stmt->execute([
                'user_id' => $userId,
                'total' => $total,
            ]);

            $orderId = (int) $this->pdo->lastInsertId();

            // 3. Inserir itens do pedido
            $sql = "INSERT INTO order_items (order_id, product_id, quantity, price)
                    VALUES (:order_id, :product_id, :quantity, :price)";

            $stmt = $this->pdo->prepare($sql);

            foreach ($items as $item) {
                $stmt->execute([
                    'order_id' => $orderId,
                    'product_id' => $item['product_id'],
                    'quantity' => $item['quantity'],
                    'price' => $item['price'],
                ]);

                // 4. Atualizar estoque
                $this->updateStock($item['product_id'], $item['quantity']);
            }

            // 5. Confirmar: TODAS as operações foram bem-sucedidas
            $this->pdo->commit();

            return $orderId;
        } catch (Exception $e) {
            // ⚠️ Reverter TUDO se qualquer operação falhar
            $this->pdo->rollBack();

            throw new RuntimeException(
                "Erro ao criar pedido: {$e->getMessage()}",
                previous: $e,
            );
        }
    }

    private function updateStock(int $productId, int $quantity): void
    {
        $sql = "UPDATE products
                SET stock = stock - :quantity
                WHERE id = :id AND stock >= :quantity";

        $stmt = $this->pdo->prepare($sql);

        $stmt->execute([
            'id' => $productId,
            'quantity' => $quantity,
        ]);

        // Se nenhuma linha foi afetada, estoque insuficiente
        if ($stmt->rowCount() === 0) {
            throw new RuntimeException(
                "Estoque insuficiente para o produto ID {$productId}.",
            );
        }
    }
}
```

### 📝 Exercícios do Capítulo 35

1. Crie `ProductRepository` com CRUD completo e busca por categoria
2. Implemente paginação com contagem total e cálculo de páginas
3. Faça sistema de relacionamento (User hasMany Orders, Order hasMany Items)
4. Implemente soft delete (coluna `deleted_at` em vez de remover o registro)
5. Crie relatório SQL com `GROUP BY`, `SUM()` e `COUNT()` para vendas por mês

---

## 36. Segurança

Segurança não é opcional — é **obrigatória** desde o primeiro `echo`. Esta seção cobre as vulnerabilidades mais comuns e como preveni-las.

### 36.1 Prevenção de SQL Injection

SQL Injection acontece quando dados do usuário são inseridos diretamente em queries SQL. A defesa é **sempre** usar prepared statements com parâmetros nomeados — nunca concatene variáveis em SQL:
```php
<?php

declare(strict_types=1);

// ❌ NUNCA FAÇA ISSO — vulnerável a SQL Injection
function findUserUnsafe(string $email): ?array
{
    $pdo = Database::connect();

    // PERIGO: input do usuário concatenado diretamente no SQL!
    // Atacante pode enviar: ' OR '1'='1' --
    // Resultado: SELECT * FROM users WHERE email = '' OR '1'='1' --'
    // Isso retorna TODOS os usuários!
    $sql = "SELECT * FROM users WHERE email = '{$email}'";

    return $pdo->query($sql)->fetch() ?: null;
}

// ✅ SEMPRE USE PREPARED STATEMENTS — 100% seguro contra SQL Injection
function findUserSafe(string $email): ?array
{
    $pdo = Database::connect();

    // Parâmetros são enviados SEPARADAMENTE do SQL
    // O banco de dados trata eles como DADOS, nunca como código SQL
    $sql = "SELECT * FROM users WHERE email = :email";
    $stmt = $pdo->prepare($sql);
    $stmt->execute(['email' => $email]);

    $result = $stmt->fetch();
    return $result !== false ? $result : null;
}
```

### 36.2 Prevenção de XSS (Cross-Site Scripting)

XSS permite que atacantes injetem JavaScript malicioso em páginas vistas por outros usuários. A defesa é **escapar toda saída** com `htmlspecialchars()` — nunca exiba dados do usuário sem tratamento:
```php
<?php

declare(strict_types=1);

// ❌ NUNCA exiba input do usuário sem escapar
// Atacante pode injetar: <script>document.cookie</script>
// $name = $_GET['name'];
// echo "Olá, $name!";  // PERIGO: executa JavaScript no navegador do visitante!

// ✅ SEMPRE escape output com htmlspecialchars
$name = $_GET['name'] ?? 'Visitante';
echo 'Olá, ' . htmlspecialchars($name, ENT_QUOTES, 'UTF-8') . '!' . PHP_EOL;

// ✅ Helper function para tornar o escape mais ergonômico
function e(string $text): string
{
    return htmlspecialchars($text, ENT_QUOTES, 'UTF-8');
}

// Uso conciso
echo "Olá, " . e($name) . "!" . PHP_EOL;

// ✅ Em templates PHP
/*
<h1><?= e($title) ?></h1>
<p>Autor: <?= e($author) ?></p>
<a href="<?= e($url) ?>">Link</a>
*/
```

### 36.3 Senhas seguras

Nunca armazene senhas em texto puro. Use `password_hash()` com `PASSWORD_ARGON2ID` (o algoritmo mais seguro disponível) e `password_verify()` para comparação. O PHP gera o salt automaticamente:
```php
<?php

declare(strict_types=1);

class PasswordService
{
    // Hash de senha com Argon2ID (mais seguro que bcrypt)
    public function hash(string $password): string
    {
        return password_hash($password, PASSWORD_ARGON2ID, [
            'memory_cost' => 65536,  // 64MB de RAM
            'time_cost' => 4,        // 4 iterações
            'threads' => 3,          // 3 threads paralelas
        ]);
    }

    // Verificar senha contra hash armazenado
    public function verify(string $password, string $hash): bool
    {
        return password_verify($password, $hash);
    }

    // Verificar se hash precisa ser atualizado (algoritmo/custo mudou)
    public function needsRehash(string $hash): bool
    {
        return password_needs_rehash($hash, PASSWORD_ARGON2ID, [
            'memory_cost' => 65536,
            'time_cost' => 4,
            'threads' => 3,
        ]);
    }

    // Validar força da senha — retorna array de erros (vazio = forte)
    public function validateStrength(string $password): array
    {
        $errors = [];

        if (mb_strlen($password) < 8) {
            $errors[] = 'Senha deve ter pelo menos 8 caracteres.';
        }

        if (!preg_match('/[A-Z]/', $password)) {
            $errors[] = 'Senha deve conter pelo menos uma letra maiúscula.';
        }

        if (!preg_match('/[a-z]/', $password)) {
            $errors[] = 'Senha deve conter pelo menos uma letra minúscula.';
        }

        if (!preg_match('/[0-9]/', $password)) {
            $errors[] = 'Senha deve conter pelo menos um número.';
        }

        if (!preg_match('/[^A-Za-z0-9]/', $password)) {
            $errors[] = 'Senha deve conter pelo menos um caractere especial.';
        }

        return $errors;
    }
}

// ── Uso no cadastro ──
$passwordService = new PasswordService();
$inputPassword = $_POST['password'] ?? '';

$strengthErrors = $passwordService->validateStrength($inputPassword);

if (!empty($strengthErrors)) {
    foreach ($strengthErrors as $error) {
        echo "❌ {$error}" . PHP_EOL;
    }
} else {
    $hash = $passwordService->hash($inputPassword);
    // Salvar $hash no banco de dados
    echo '✅ Senha válida e hash gerado.' . PHP_EOL;
}

// ── Uso no login ──
$inputPassword = $_POST['password'] ?? '';
$storedHash = '...'; // Recuperado do banco

if ($passwordService->verify($inputPassword, $storedHash)) {
    echo '✅ Autenticação bem-sucedida!' . PHP_EOL;

    // Verificar se hash precisa ser atualizado
    if ($passwordService->needsRehash($storedHash)) {
        $newHash = $passwordService->hash($inputPassword);
        // Atualizar hash no banco (transparente para o usuário)
    }
} else {
    echo '❌ Credenciais inválidas.' . PHP_EOL;
}
```

### 36.4 Rate Limiting

Rate limiting protege sua aplicação contra ataques de força bruta e abuso. Limite o número de requisições por IP ou por usuário em uma janela de tempo:
```php
<?php

declare(strict_types=1);

// Proteção contra ataques de força bruta
// Limita número de tentativas por IP/ação em janela de tempo
class RateLimiter
{
    private readonly string $storageDir;

    public function __construct(string $storageDir = 'storage/rate_limit')
    {
        $this->storageDir = $storageDir;

        if (!is_dir($this->storageDir)) {
            mkdir($this->storageDir, 0755, true);
        }
    }

    // Verifica se ação é permitida (dentro do limite)
    public function allow(
        string $identifier,
        int $maxAttempts = 5,
        int $timeWindowSeconds = 60,
    ): bool {
        $file = $this->getFile($identifier);
        $attempts = $this->readAttempts($file);

        // Remover tentativas expiradas
        $now = time();
        $validAttempts = array_filter(
            $attempts,
            fn(int $timestamp): bool => ($now - $timestamp) < $timeWindowSeconds,
        );

        // Verificar se excedeu o limite
        if (count($validAttempts) >= $maxAttempts) {
            return false;
        }

        // Registrar nova tentativa
        $validAttempts[] = $now;
        $this->saveAttempts($file, $validAttempts);

        return true;
    }

    // Retorna segundos restantes até o desbloqueio
    public function getRetryAfter(string $identifier, int $timeWindowSeconds = 60): int
    {
        $file = $this->getFile($identifier);
        $attempts = $this->readAttempts($file);

        if (empty($attempts)) {
            return 0;
        }

        $oldestAttempt = min($attempts);
        $retryAfter = $timeWindowSeconds - (time() - $oldestAttempt);

        return max(0, $retryAfter);
    }

    private function getFile(string $identifier): string
    {
        return $this->storageDir . '/' . md5($identifier) . '.json';
    }

    private function readAttempts(string $file): array
    {
        if (!file_exists($file)) {
            return [];
        }

        $json = file_get_contents($file);
        return json_decode($json, true) ?? [];
    }

    private function saveAttempts(string $file, array $attempts): void
    {
        file_put_contents(
            $file,
            json_encode(array_values($attempts), JSON_THROW_ON_ERROR),
        );
    }
}

// Uso em formulário de login
$limiter = new RateLimiter();
$clientIp = $_SERVER['REMOTE_ADDR'] ?? '0.0.0.0';

// 5 tentativas em 5 minutos por IP
if (!$limiter->allow("login:{$clientIp}", maxAttempts: 5, timeWindowSeconds: 300)) {
    $retryAfter = $limiter->getRetryAfter("login:{$clientIp}", 300);
    http_response_code(429);
    exit("⛔ Muitas tentativas de login. Tente novamente em {$retryAfter} segundos.");
}

// Processar login normalmente...
echo '✅ Tentativa de login permitida.' . PHP_EOL;
```

### 📝 Exercícios do Capítulo 36

1. Implemente validação completa de entrada com sanitização e escape
2. Crie sistema de token temporário para redefinição de senha (com expiração)
3. Adicione rate limiting na API com resposta adequada (`429 Too Many Requests`)
4. Faça sistema de auditoria que registra todas as ações do usuário com timestamp
5. Implemente autenticação de dois fatores (2FA) simples usando TOTP

---

## 37. Projeto Final — Sistema Completo

Este capítulo reúne **tudo** que você aprendeu em um projeto real: um sistema CRUD com autenticação, validação, banco de dados PDO e segurança. A estrutura segue boas práticas de organização com separação entre código público, classes, configuração e templates.

### 37.1 Estrutura do projeto

O projeto segue uma organização profissional: `public/` contém os arquivos acessíveis pela web (entry points), `src/` contém as classes da aplicação, `config/` as configurações, e `templates/` as views:
```text
projeto/
├── public/                     # Arquivos acessíveis pela web
│   ├── index.php               # Página inicial (entry point)
│   ├── login.php               # Formulário e processamento de login
│   ├── logout.php              # Encerrar sessão
│   ├── products/
│   │   ├── index.php           # Listagem com paginação
│   │   ├── create.php          # Formulário de criação
│   │   ├── edit.php            # Formulário de edição
│   │   └── delete.php          # Confirmação e exclusão
│   └── assets/
│       └── style.css           # Estilos CSS
├── src/                        # Código-fonte (não acessível pela web)
│   ├── Database.php            # Conexão PDO Singleton
│   ├── Auth.php                # Autenticação e autorização
│   ├── Validator.php           # Validação reutilizável
│   ├── CsrfProtection.php     # Proteção CSRF
│   ├── Repository/
│   │   ├── UserRepository.php
│   │   └── ProductRepository.php
│   └── Service/
│       ├── AuthService.php
│       └── ProductService.php
├── views/                      # Templates HTML
│   ├── header.php
│   ├── footer.php
│   └── dashboard.php
├── config/
│   └── database.php            # Configurações de conexão
└── autoload.php                # PSR-4 autoloader
```

### 37.2 Autoloader

O autoloader carrega classes automaticamente quando são referenciadas pela primeira vez, eliminando a necessidade de `require` manual. A função `spl_autoload_register()` mapeia nomes de classe para caminhos de arquivo:
```php
<?php
// autoload.php

declare(strict_types=1);

spl_autoload_register(function (string $className): void {
    $file = __DIR__ . '/src/' . str_replace('\\', '/', $className) . '.php';

    if (file_exists($file)) {
        require $file;
    }
});
```

### 37.3 Configuração do banco

Separe as credenciais do banco em um arquivo de configuração fora do diretório público. Este arquivo retorna um array associativo que é consumido pela classe `Database`:
```php
<?php
// config/database.php

declare(strict_types=1);

// Retorna array com configurações — NÃO versione credenciais reais!
return [
    'host' => 'localhost',
    'database' => 'my_system',
    'username' => 'root',
    'password' => '',
    'charset' => 'utf8mb4',
];
```

### 37.4 Classe Database

A classe `Database` implementa o padrão Singleton para manter uma única conexão PDO durante toda a requisição, evitando múltiplas conexões desnecessárias:
```php
<?php
// src/Database.php

declare(strict_types=1);

class Database
{
    private static ?PDO $connection = null;

    public static function connect(): PDO
    {
        if (self::$connection === null) {
            $config = require __DIR__ . '/../config/database.php';

            $dsn = sprintf(
                'mysql:host=%s;dbname=%s;charset=%s',
                $config['host'],
                $config['database'],
                $config['charset'],
            );

            self::$connection = new PDO(
                dsn: $dsn,
                username: $config['username'],
                password: $config['password'],
                options: [
                    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
                    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
                    PDO::ATTR_EMULATE_PREPARES => false,
                ],
            );
        }

        return self::$connection;
    }
}
```

### 37.5 Página inicial

A página inicial (`index.php`) é o entry point da aplicação. Ela carrega o autoloader, inicia a sessão, verifica autenticação e exibe o conteúdo:
```php
<?php
// public/index.php

declare(strict_types=1);

require __DIR__ . '/../autoload.php';

session_start();

// Proteger página — redireciona para login se não autenticado
Auth::requireLogin();

$user = Auth::getUser();

// Renderizar dashboard
require __DIR__ . '/../views/header.php';
require __DIR__ . '/../views/dashboard.php';
require __DIR__ . '/../views/footer.php';
```

### 📝 Checklist do Projeto Final

Construa um sistema completo de gerenciamento de produtos aplicando **tudo** o que aprendeu:

1. ✅ **Autenticação** — Login/logout com sessões seguras e `session_regenerate_id()`
2. ✅ **CRUD de Produtos** — Criar, ler, atualizar, deletar usando `ProductRepository`
3. ✅ **Validação** — Classe `Validator` com regras reutilizáveis
4. ✅ **Proteção CSRF** — Token em todos os formulários POST
5. ✅ **Paginação** — Listagem com `LIMIT`/`OFFSET` e links de navegação
6. ✅ **Upload de Imagem** — Validação de tipo MIME e tamanho
7. ✅ **Busca e Filtros** — `WHERE` dinâmico com prepared statements
8. ✅ **Sessões Seguras** — Timeout por inatividade, flags de cookie seguras
9. ✅ **Prepared Statements** — Zero concatenação de SQL
10. ✅ **Escape de Output** — `htmlspecialchars()` em toda exibição de dados

---

## 🎉 Conclusão

Parabéns! Você completou o guia completo de **PHP 8.5 Moderno: Do Zero à Maestria**! 🚀

### O que você aprendeu

| Parte                | Conteúdo                                                                              |
| -------------------- | ------------------------------------------------------------------------------------- |
| **I — Fundamentos**  | Variáveis, tipos, operadores, controle de fluxo, arrays, funções, strings             |
| **II — Dados**       | Datas/horas com `DateTimeImmutable`, arquivos, JSON, serialização                     |
| **III — OOP**        | Classes, encapsulamento, herança, polimorfismo, interfaces, traits, enums, namespaces |
| **IV — PHP Moderno** | Recursos 8.0–8.4, PHP 8.5 (pipe, clone with, `#[\NoDiscard]`, URI), sistema de tipos  |
| **V — Projetos**     | Formulários, validação, CSRF, sessões, cookies, PDO, segurança, projeto completo      |

### Próximos passos na sua jornada

1. 📚 **Pratique:** Construa projetos reais — a prática é a melhor professora
2. 🔒 **Segurança:** Aprofunde-se no OWASP Top 10 e proteja suas aplicações
3. 🧪 **Testes:** Aprenda PHPUnit e Pest PHP para código confiável
4. 🚀 **Frameworks:** Explore Laravel ou Symfony e entenda como eles funcionam por dentro
5. 📊 **Performance:** Estude OPcache, profiling com Xdebug e estratégias de cache
6. 🔍 **Análise Estática:** Use PHPStan ou Psalm para encontrar bugs antes de executar
7. 🐳 **DevOps:** Docker, CI/CD e deploy automatizado

> **Lembre-se:** Sempre use `declare(strict_types=1)`, tipagem completa, prepared statements e siga as boas práticas de segurança. O código que você escreve hoje será mantido amanhã! 🔒

**Continue programando e evoluindo! 💻🚀**

---

# Parte VI: Tópicos Avançados Complementares

---

## 38. Iterables e Iteradores

Iterables e Iteradores permitem percorrer coleções de dados de forma eficiente, especialmente quando o conjunto é grande demais para caber na memória. Generators são a forma mais simples de criar iteradores sob demanda.

### 38.1 O que são Iterables?

O tipo `iterable` aceita qualquer valor que pode ser percorrido com `foreach`: arrays e objetos que implementam `Traversable`. Use este type hint quando sua função deve aceitar ambos:
```php
<?php

declare(strict_types=1);

// Iterable: qualquer valor que pode ser iterado com foreach
// Inclui arrays e objetos que implementam Traversable

function processIterable(iterable $items): void
{
    foreach ($items as $item) {
        echo $item . PHP_EOL;
    }
}

// ✅ Funciona com arrays
$numbers = [1, 2, 3, 4, 5];
processIterable($numbers);

// ✅ Funciona com Generator
function generateNumbers(int $max): Generator
{
    for ($i = 1; $i <= $max; $i++) {
        yield $i; // Retorna um valor por vez, sem carregar tudo na memória
    }
}

processIterable(generateNumbers(5));

// ✅ Type hint iterable aceita tanto array quanto Traversable
function getData(bool $useGenerator): iterable
{
    if ($useGenerator) {
        return generateNumbers(3);
    }

    return [1, 2, 3];
}
```

### 38.2 Generators

Generators criam iteradores usando `yield` — cada chamada produz um valor e **pausa** a execução até o próximo pedido. Perfeitos para processar arquivos grandes, streams e sequências infinitas sem consumir memória:
```php
<?php

declare(strict_types=1);

// Generator: cria iterador sob demanda — NÃO carrega tudo em memória
// Ideal para processar arquivos grandes, resultados de queries enormes, etc.
function readLargeFile(string $filePath): Generator
{
    $handle = fopen($filePath, 'r');

    if ($handle === false) {
        throw new RuntimeException("Erro ao abrir: {$filePath}");
    }

    try {
        while (($line = fgets($handle)) !== false) {
            yield $line; // Retorna uma linha por vez
        }
    } finally {
        fclose($handle);
    }
}

// Uso: processa linha por linha sem carregar tudo na memória
foreach (readLargeFile('access.log') as $line) {
    echo $line;
}

// ── Generator com chave e valor ──
function generateKeyValuePairs(): Generator
{
    yield 'one' => 1;
    yield 'two' => 2;
    yield 'three' => 3;
}

foreach (generateKeyValuePairs() as $key => $value) {
    echo "{$key}: {$value}" . PHP_EOL;
}

// ── Generator com send() — comunicação bidirecional ──
function counter(): Generator
{
    $i = 0;

    while (true) {
        $reset = yield $i;

        if ($reset === true) {
            $i = 0;
        } else {
            $i++;
        }
    }
}

$gen = counter();
echo $gen->current() . PHP_EOL; // 0
$gen->next();
echo $gen->current() . PHP_EOL; // 1
$gen->send(true);               // Reset
echo $gen->current() . PHP_EOL; // 0

// ── Generator infinito: Fibonacci ──
function fibonacci(): Generator
{
    [$a, $b] = [0, 1];

    while (true) {
        yield $a;
        [$a, $b] = [$b, $a + $b];
    }
}

// Pegar apenas os 10 primeiros
$fib = fibonacci();

for ($i = 0; $i < 10; $i++) {
    echo $fib->current() . ' ';
    $fib->next();
}
// 0 1 1 2 3 5 8 13 21 34
```

### 38.3 Iterator Interface

A interface `Iterator` dá **controle total** sobre a iteração, exigindo 5 métodos: `current()`, `key()`, `next()`, `rewind()` e `valid()`. Use quando precisa de lógica customizada de navegação:
```php
<?php

declare(strict_types=1);

// Implementar Iterator: controle total sobre a iteração
class CustomIterator implements Iterator
{
    private int $position = 0;

    public function __construct(
        private readonly array $items,
    ) {}

    public function current(): mixed
    {
        return $this->items[$this->position];
    }

    public function key(): int
    {
        return $this->position;
    }

    public function next(): void
    {
        $this->position++;
    }

    public function rewind(): void
    {
        $this->position = 0;
    }

    public function valid(): bool
    {
        return isset($this->items[$this->position]);
    }
}

$iterator = new CustomIterator([10, 20, 30, 40, 50]);

foreach ($iterator as $value) {
    echo $value . PHP_EOL;
}

// ── Exemplo prático: iterador de intervalo numérico ──
class RangeIterator implements Iterator
{
    private int|float $current;

    public function __construct(
        private readonly int|float $start,
        private readonly int|float $end,
        private readonly int|float $step = 1,
    ) {
        $this->current = $start;
    }

    public function current(): int|float
    {
        return $this->current;
    }

    public function key(): int|float
    {
        return $this->current;
    }

    public function next(): void
    {
        $this->current += $this->step;
    }

    public function rewind(): void
    {
        $this->current = $this->start;
    }

    public function valid(): bool
    {
        return $this->step > 0
            ? $this->current <= $this->end
            : $this->current >= $this->end;
    }
}

// Iterar de 1 a 10 pulando de 2 em 2
$range = new RangeIterator(start: 1, end: 10, step: 2);

foreach ($range as $number) {
    echo "{$number} "; // 1 3 5 7 9
}
```

### 38.4 IteratorAggregate Interface

`IteratorAggregate` é mais simples que `Iterator`: exige apenas o método `getIterator()` que retorna um `Traversable`. Ideal para coleções que delegam a iteração a um `ArrayIterator` interno:
```php
<?php

declare(strict_types=1);

// IteratorAggregate: delega iteração para outro objeto (mais simples que Iterator)
class Collection implements IteratorAggregate, Countable
{
    private array $items = [];

    public function add(mixed $item): void
    {
        $this->items[] = $item;
    }

    public function count(): int
    {
        return count($this->items);
    }

    // Único método obrigatório: retornar um Traversable
    public function getIterator(): Traversable
    {
        return new ArrayIterator($this->items);
    }
}

$collection = new Collection();
$collection->add('Item 1');
$collection->add('Item 2');
$collection->add('Item 3');

echo "Total: {$collection->count()}" . PHP_EOL;

foreach ($collection as $item) {
    echo $item . PHP_EOL;
}

// ── Coleção com filtro integrado ──
class FilteredCollection implements IteratorAggregate
{
    public function __construct(
        private readonly array $items,
        private readonly ?Closure $filter = null,
    ) {}

    public function getIterator(): Traversable
    {
        $items = $this->items;

        if ($this->filter !== null) {
            $items = array_filter($items, $this->filter);
        }

        return new ArrayIterator($items);
    }
}

// Apenas números pares
$evenNumbers = new FilteredCollection(
    items: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    filter: fn(int $n): bool => $n % 2 === 0,
);

foreach ($evenNumbers as $number) {
    echo "{$number} "; // 2 4 6 8 10
}
```

### 38.5 Exemplo prático: Paginação com Iterator

Este exemplo demonstra um iterador de paginação que divide dados em páginas e permite percorrê-las com `foreach`, carregando apenas uma página por vez:
```php
<?php

declare(strict_types=1);

class PaginatorIterator implements Iterator
{
    private int $currentPage = 1;
    private array $currentPageData = [];

    public function __construct(
        private readonly array $allData,
        private readonly int $itemsPerPage,
    ) {
        $this->loadPage();
    }

    private function loadPage(): void
    {
        $offset = ($this->currentPage - 1) * $this->itemsPerPage;

        $this->currentPageData = array_slice(
            $this->allData,
            $offset,
            $this->itemsPerPage,
        );
    }

    public function current(): array
    {
        return $this->currentPageData;
    }

    public function key(): int
    {
        return $this->currentPage;
    }

    public function next(): void
    {
        $this->currentPage++;
        $this->loadPage();
    }

    public function rewind(): void
    {
        $this->currentPage = 1;
        $this->loadPage();
    }

    public function valid(): bool
    {
        return !empty($this->currentPageData);
    }

    public function getTotalPages(): int
    {
        return (int) ceil(count($this->allData) / $this->itemsPerPage);
    }
}

// Uso
$data = range(1, 100);
$paginator = new PaginatorIterator(allData: $data, itemsPerPage: 10);

foreach ($paginator as $pageNumber => $pageItems) {
    echo "Página {$pageNumber}: " . implode(', ', $pageItems) . PHP_EOL;
}

echo "Total de páginas: {$paginator->getTotalPages()}" . PHP_EOL;
```

### 📝 Exercícios do Capítulo 38

1. Crie generator que lê CSV linha por linha e retorna arrays associativos
2. Implemente `Iterator` para percorrer nós de uma árvore binária
3. Faça `IteratorAggregate` para coleção que mantém itens automaticamente ordenados
4. Crie generator infinito de números Fibonacci e use `for` com `break` para limitar
5. Implemente paginação customizada com `Iterator` que busca dados do banco sob demanda

---

## 39. Namespaces Avançado

Namespaces organizam código em espaços hierárquicos, evitando conflitos de nomes em projetos grandes. Combinados com PSR-4, permitem autoloading automático — cada arquivo corresponde a uma única classe.

### 39.1 Declaração e organização

Declare o namespace no topo do arquivo com `namespace`. Classes no mesmo diretório lógico compartilham o namespace, e sub-namespaces correspondem a subdiretórios:
```php
<?php

declare(strict_types=1);

// Namespace simples — organiza classes logicamente
namespace App\Model;

class User
{
    public function __construct(
        public readonly string $name,
        public readonly string $email,
    ) {}
}
```

```php
<?php

declare(strict_types=1);

// Múltiplas classes podem compartilhar o mesmo namespace
namespace App\Service;

class UserService
{
    public function create(array $data): void
    {
        // Lógica de criação de usuário
    }
}

class EmailService
{
    public function send(string $to, string $subject, string $body): void
    {
        // Lógica de envio de email
    }
}
```

```php
<?php

declare(strict_types=1);

// Sub-namespaces para organização ainda mais granular
namespace App\Service\Email;

class SmtpService
{
    // Implementação SMTP direta
}

class MailgunService
{
    // Implementação via API Mailgun
}
```

### 39.2 Importação e aliases

`use` importa classes para o contexto atual, evitando nomes longos. Grouped imports agrupam múltiplas classes do mesmo namespace, e aliases (`as`) resolvem conflitos de nomes:
```php
<?php

declare(strict_types=1);

namespace App\Controller;

// Importar classe específica
use App\Model\User;
use App\Service\UserService;

// Importar múltiplas classes do mesmo namespace
use App\Repository\{
    UserRepository,
    ProductRepository,
    OrderRepository,
};

// ✅ Aliases: resolve conflitos de nome entre namespaces diferentes
use App\Model\User as UserModel;
use App\DTO\User as UserDTO;

class UserController
{
    public function __construct(
        private readonly UserService $service,
        private readonly UserRepository $repository,
    ) {}

    public function create(array $data): UserModel
    {
        // Converter DTO para Model
        $dto = new UserDTO($data);

        return $this->service->createFromDto($dto);
    }
}
```

### 39.3 Namespace global

Dentro de um namespace, classes, funções e constantes do PHP precisam de `\` (backslash) para acessar o namespace global. Sem isso, o PHP busca no namespace atual:
```php
<?php

declare(strict_types=1);

namespace App\Util;

// ⚠️ Dentro de um namespace, classes globais precisam de \ (backslash)
class DateHelper
{
    public function now(): \DateTimeImmutable
    {
        // \ antes de DateTimeImmutable acessa a classe global
        return new \DateTimeImmutable();
    }

    public function format(\DateTimeInterface $date): string
    {
        return $date->format('d/m/Y');
    }
}

// Funções globais também precisam de \ dentro de namespaces
function calculateSquareRoot(float $value): float
{
    return \sqrt($value); // Função sqrt() do namespace global
}

// Constantes globais: mesma regra
class Config
{
    public function getPhpVersion(): string
    {
        return \PHP_VERSION;
    }
}
```

### 39.4 Autoloading com PSR-4

PSR-4 mapeia prefixos de namespace a diretórios de forma previsível. O autoloader registrado com `spl_autoload_register()` converte o nome da classe em caminho de arquivo automaticamente:
```php
<?php
// autoload.php

declare(strict_types=1);

/**
 * PSR-4 Autoloader completo
 *
 * Estrutura de diretórios:
 *
 * projeto/
 * ├── src/
 * │   ├── Model/
 * │   │   └── User.php       (namespace App\Model)
 * │   ├── Service/
 * │   │   └── UserService.php (namespace App\Service)
 * │   └── Repository/
 * │       └── UserRepository.php (namespace App\Repository)
 * └── autoload.php
 */

spl_autoload_register(function (string $className): void {
    // Mapa de prefixos → diretórios base
    $prefixMap = [
        'App\\' => __DIR__ . '/src/',
    ];

    foreach ($prefixMap as $prefix => $baseDir) {
        $prefixLength = strlen($prefix);

        // Verificar se a classe usa este prefixo
        if (strncmp($prefix, $className, $prefixLength) !== 0) {
            continue;
        }

        // Obter o nome relativo da classe (sem o prefixo)
        $relativeClass = substr($className, $prefixLength);

        // Converter namespace separators em directory separators
        $file = $baseDir . str_replace('\\', '/', $relativeClass) . '.php';

        if (file_exists($file)) {
            require $file;
            return;
        }
    }
});

// ✅ Agora pode usar classes sem require manual!
// $user = new App\Model\User(name: 'João', email: 'joao@ex.com');
```

### 39.5 Funções e constantes em namespaces

Além de classes, funções e constantes também podem viver em namespaces. Para importá-las, use `use function` e `use const` respectivamente:
```php
<?php

declare(strict_types=1);

namespace App\Helpers;

// Funções podem viver em namespaces
function formatCurrency(float $value): string
{
    return 'R$ ' . number_format($value, 2, ',', '.');
}

function cleanCpf(string $cpf): string
{
    return preg_replace('/[^0-9]/', '', $cpf);
}

// Constantes em namespace
const APP_VERSION = '2.0.0';
const ENVIRONMENT = 'production';
```

```php
<?php

declare(strict_types=1);

namespace App\Controller;

// ✅ Importar FUNÇÕES com 'use function'
use function App\Helpers\formatCurrency;
use function App\Helpers\cleanCpf;

// ✅ Importar CONSTANTES com 'use const'
use const App\Helpers\APP_VERSION;

class ProductController
{
    public function displayPrice(float $price): string
    {
        return formatCurrency($price); // R$ 1.234,56
    }

    public function getVersion(): string
    {
        return APP_VERSION; // 2.0.0
    }
}
```

### 39.6 Organização de projeto real

Em projetos reais, a estrutura de diretórios espelha os namespaces: cada classe em seu próprio arquivo, cada namespace em seu diretório correspondente:
```php
<?php

declare(strict_types=1);

/**
 * Estrutura recomendada (PSR-4 compliant):
 *
 * projeto/
 * ├── src/
 * │   ├── Controller/
 * │   │   ├── UserController.php
 * │   │   └── ProductController.php
 * │   ├── Model/
 * │   │   ├── User.php
 * │   │   └── Product.php
 * │   ├── Repository/
 * │   │   ├── UserRepository.php
 * │   │   └── ProductRepository.php
 * │   ├── Service/
 * │   │   ├── AuthService.php
 * │   │   └── EmailService.php
 * │   ├── Validator/
 * │   │   └── Validator.php
 * │   ├── Exception/
 * │   │   ├── ValidationException.php
 * │   │   └── NotFoundException.php
 * │   └── Helpers/
 * │       └── StringHelper.php
 * ├── config/
 * │   └── database.php
 * ├── public/
 * │   └── index.php
 * ├── composer.json          ← PSR-4 autoload config
 * └── vendor/                ← Composer autoloader
 */

// Cada arquivo = uma classe, namespace = caminho do diretório
// src/Controller/UserController.php:
namespace App\Controller;

use App\Service\AuthService;
use App\Repository\UserRepository;
use App\Validator\Validator;

class UserController
{
    public function __construct(
        private readonly AuthService $auth,
        private readonly UserRepository $repository,
        private readonly Validator $validator,
    ) {}
}
```

### 📝 Exercícios do Capítulo 39

1. Organize projeto existente seguindo PSR-4 com autoloader customizado
2. Crie helpers com funções em namespace e importe com `use function`
3. Resolva conflitos de nomes entre 3+ classes homônimas usando aliases
4. Estruture aplicação MVC completa com namespaces (`Controller`, `Model`, `View`)
5. Migre autoloader customizado para `composer.json` com mapa PSR-4

---

## 40. OOP — Properties e Methods Estáticos

Membros estáticos pertencem à **classe**, não ao objeto. São acessíveis via `NomeDaClasse::` sem precisar criar uma instância. Use para utilitários puros, factories, singletons e caches.

### 40.1 Static Properties

Propriedades estáticas são compartilhadas por **todas** as instâncias da classe. Qualquer modificação é visível globalmente. Acesse com `self::$prop` internamente ou `Classe::$prop` externamente:
```php
<?php

declare(strict_types=1);

class Counter
{
    // Propriedade estática: compartilhada por TODAS as instâncias
    // Existe na CLASSE, não no objeto
    private static int $count = 0;

    public function __construct()
    {
        self::$count++;
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

echo Counter::getCount() . PHP_EOL; // 0

$obj1 = new Counter();
$obj2 = new Counter();
$obj3 = new Counter();

echo Counter::getCount() . PHP_EOL; // 3

Counter::reset();
echo Counter::getCount() . PHP_EOL; // 0
```

### 40.2 Static Methods

Métodos estáticos não têm acesso a `$this` (não há instância). Ideais para funções utilitárias puras que não dependem de estado do objeto:
```php
<?php

declare(strict_types=1);

// Métodos estáticos: chamados na CLASSE, não no objeto
// NÃO têm acesso a $this (não há instância)
class MathHelper
{
    public static function add(float $a, float $b): float
    {
        return $a + $b;
    }

    public static function multiply(float $a, float $b): float
    {
        return $a * $b;
    }

    public static function factorial(int $n): int
    {
        if ($n <= 1) {
            return 1;
        }

        // Pode chamar outro método estático com self::
        return $n * self::factorial($n - 1);
    }

    public static function clamp(float $value, float $min, float $max): float
    {
        return max($min, min($max, $value));
    }
}

// Uso sem criar objeto — ideal para funções utilitárias puras
echo MathHelper::add(5, 3) . PHP_EOL;       // 8
echo MathHelper::multiply(4, 7) . PHP_EOL;  // 28
echo MathHelper::factorial(5) . PHP_EOL;     // 120
echo MathHelper::clamp(150, 0, 100) . PHP_EOL; // 100
```

### 40.3 Late Static Binding (`static::`)

`self::` sempre resolve para a classe onde o método foi **definido**. `static::` resolve para a classe que **chamou** o método (late binding). Essencial para factory methods em hierarquias:
```php
<?php

declare(strict_types=1);

class Animal
{
    protected static string $type = 'Generic Animal';

    // self:: refere à classe onde o método foi DEFINIDO
    public static function getTypeSelf(): string
    {
        return self::$type;
    }

    // static:: refere à classe que CHAMOU o método (late binding)
    public static function getTypeStatic(): string
    {
        return static::$type;
    }

    // ✅ Uso prático: factory method
    public static function create(): static
    {
        return new static(); // Cria instância da classe que chamou
    }
}

class Dog extends Animal
{
    protected static string $type = 'Dog';
}

class Cat extends Animal
{
    protected static string $type = 'Cat';
}

// self:: sempre resolve para Animal (onde foi definido)
echo Dog::getTypeSelf() . PHP_EOL;    // Generic Animal
echo Cat::getTypeSelf() . PHP_EOL;    // Generic Animal

// static:: resolve para a classe que chamou (polimorfismo estático)
echo Dog::getTypeStatic() . PHP_EOL;  // Dog
echo Cat::getTypeStatic() . PHP_EOL;  // Cat

// Factory method com static:: cria a subclasse correta
$dog = Dog::create();
var_dump($dog instanceof Dog); // true
```

### 40.4 Singleton Pattern

Singleton garante **uma única instância** de uma classe durante toda a execução. Construtor privado impede `new`, clone privado impede `clone`. Use com moderação — dificulta testes:
```php
<?php

declare(strict_types=1);

// Singleton: garante UMA ÚNICA instância de uma classe
// ⚠️ Use com moderação — dificulta testes e acopla código
class AppConfig
{
    private static ?self $instance = null;
    private array $settings = [];

    // Construtor PRIVADO: impede new AppConfig()
    private function __construct() {}

    // Clone PRIVADO: impede clone $config
    private function __clone() {}

    // Wakeup lança exceção: impede unserialize()
    public function __wakeup(): never
    {
        throw new RuntimeException('Singleton não pode ser deserializado.');
    }

    // Único ponto de acesso à instância
    public static function getInstance(): self
    {
        if (self::$instance === null) {
            self::$instance = new self();
        }

        return self::$instance;
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

$config1 = AppConfig::getInstance();
$config2 = AppConfig::getInstance();

$config1->set('app_name', 'Meu Sistema');
echo $config2->get('app_name') . PHP_EOL; // Meu Sistema

var_dump($config1 === $config2); // true (mesma instância)

// new AppConfig();  // ❌ ERRO: construtor privado
// clone $config1;   // ❌ ERRO: clone privado
```

### 40.5 Factory Pattern com static

O Factory Pattern encapsula a lógica de criação de objetos em métodos estáticos, permitindo trocar implementações sem alterar o código cliente:
```php
<?php

declare(strict_types=1);

interface LoggerInterface
{
    public function log(string $message): void;
}

class FileLogger implements LoggerInterface
{
    public function __construct(
        private readonly string $filePath,
    ) {}

    public function log(string $message): void
    {
        file_put_contents(
            $this->filePath,
            date('[Y-m-d H:i:s] ') . $message . PHP_EOL,
            FILE_APPEND,
        );
    }
}

class DatabaseLogger implements LoggerInterface
{
    public function __construct(
        private readonly PDO $pdo,
    ) {}

    public function log(string $message): void
    {
        $stmt = $this->pdo->prepare(
            "INSERT INTO logs (message, created_at) VALUES (:message, NOW())",
        );
        $stmt->execute(['message' => $message]);
    }
}

// Factory com métodos estáticos — encapsula lógica de criação
class LoggerFactory
{
    public static function createFileLogger(string $path): LoggerInterface
    {
        return new FileLogger($path);
    }

    public static function createDatabaseLogger(PDO $pdo): LoggerInterface
    {
        return new DatabaseLogger($pdo);
    }

    public static function create(string $type, mixed $config): LoggerInterface
    {
        return match ($type) {
            'file' => self::createFileLogger($config),
            'database' => self::createDatabaseLogger($config),
            default => throw new InvalidArgumentException(
                "Tipo de logger desconhecido: {$type}",
            ),
        };
    }
}

// Uso
$logger = LoggerFactory::create('file', 'app.log');
$logger->log('Aplicação iniciada.');
```

### 40.6 Cache em memória com static

Propriedades estáticas persistem durante toda a requisição HTTP, tornando-as ideais para cache em memória. O método `remember()` busca do cache ou executa um callback e armazena o resultado:
```php
<?php

declare(strict_types=1);

class MemoryCache
{
    private static array $data = [];

    public static function set(string $key, mixed $value, int $ttl = 3600): void
    {
        self::$data[$key] = [
            'value' => $value,
            'expiresAt' => time() + $ttl,
        ];
    }

    public static function get(string $key): mixed
    {
        if (!isset(self::$data[$key])) {
            return null;
        }

        $item = self::$data[$key];

        // Verificar se expirou
        if (time() > $item['expiresAt']) {
            unset(self::$data[$key]);
            return null;
        }

        return $item['value'];
    }

    public static function has(string $key): bool
    {
        return self::get($key) !== null;
    }

    public static function delete(string $key): void
    {
        unset(self::$data[$key]);
    }

    public static function clear(): void
    {
        self::$data = [];
    }

    // ✅ remember(): busca do cache ou executa callback e armazena
    public static function remember(string $key, callable $callback, int $ttl = 3600): mixed
    {
        if (self::has($key)) {
            return self::get($key);
        }

        $value = $callback();
        self::set($key, $value, $ttl);

        return $value;
    }
}

// Uso direto
MemoryCache::set('user:1', ['name' => 'João', 'email' => 'joao@example.com']);
$user = MemoryCache::get('user:1');

// Uso com callback — evita recalcular dados caros
$products = MemoryCache::remember('products:featured', function (): array {
    // Simulação de consulta pesada ao banco
    return [
        ['id' => 1, 'name' => 'Notebook'],
        ['id' => 2, 'name' => 'Mouse'],
    ];
}, ttl: 3600);
```

### 📝 Exercícios do Capítulo 40

1. Implemente Singleton para gerenciar configurações da aplicação com `load()` de arquivo
2. Crie Factory estática para diferentes tipos de notificação (Email, SMS, Push)
3. Faça `MemoryCache` com suporte a tags para invalidação em grupo
4. Implemente contador de instâncias por classe usando static property
5. Use late static binding em hierarquia onde `create()` retorna a subclasse correta

---

## 41. OOP — Traits Avançado

Traits avançados permitem composição sofisticada de comportamento: métodos abstratos que forçam contratos, resolução de conflitos entre traits, traits compostos, e controle de visibilidade na importação.

### 41.1 Traits com properties e methods

Traits podem conter propriedades e métodos completos. Combinar múltiplos traits em uma classe é como "montar" funcionalidades de forma modular:
```php
<?php

declare(strict_types=1);

// ── Trait Timestampable: rastreia criação e atualização ──
trait TimestampableTrait
{
    protected ?string $createdAt = null;
    protected ?string $updatedAt = null;

    public function markAsCreated(): void
    {
        $this->createdAt = date('Y-m-d H:i:s');
    }

    public function markAsUpdated(): void
    {
        $this->updatedAt = date('Y-m-d H:i:s');
    }

    public function getCreatedAt(): ?string
    {
        return $this->createdAt;
    }

    public function getUpdatedAt(): ?string
    {
        return $this->updatedAt;
    }
}

// ── Trait SoftDeletable: exclusão lógica (sem remover do banco) ──
trait SoftDeletableTrait
{
    protected ?string $deletedAt = null;

    public function softDelete(): void
    {
        $this->deletedAt = date('Y-m-d H:i:s');
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

// ── Classe usando múltiplos traits ──
class User
{
    use TimestampableTrait, SoftDeletableTrait;

    public function __construct(
        public string $name,
        public string $email,
    ) {
        $this->markAsCreated();
    }

    public function update(string $name, string $email): void
    {
        $this->name = $name;
        $this->email = $email;
        $this->markAsUpdated();
    }
}

// Uso
$user = new User('João', 'joao@example.com');
echo $user->getCreatedAt() . PHP_EOL; // 2026-02-10 08:30:00

$user->update('João Silva', 'joao.silva@example.com');
echo $user->getUpdatedAt() . PHP_EOL; // 2026-02-10 08:31:00

$user->softDelete();
echo $user->isDeleted() ? 'Deletado' : 'Ativo'; // Deletado

$user->restore();
echo $user->isDeleted() ? 'Deletado' : 'Ativo'; // Ativo
```

### 41.2 Traits com abstract methods

Traits podem declarar métodos `abstract`, exigindo que a classe que usa o trait forneça a implementação. Isso cria um **contrato** entre o trait e a classe:
```php
<?php

declare(strict_types=1);

// Trait pode exigir que a classe implemente métodos específicos
trait ValidatableTrait
{
    protected array $errors = [];

    // ⚠️ Método abstrato: a classe DEVE implementar
    abstract protected function validationRules(): array;

    public function validate(): bool
    {
        $this->errors = [];
        $rules = $this->validationRules();

        foreach ($rules as $field => $fieldRules) {
            $value = $this->{$field} ?? null;

            foreach ($fieldRules as $rule) {
                $errorMessage = $this->applyRule($field, $value, $rule);

                if ($errorMessage !== null) {
                    $this->errors[$field][] = $errorMessage;
                }
            }
        }

        return empty($this->errors);
    }

    private function applyRule(string $field, mixed $value, string $rule): ?string
    {
        return match ($rule) {
            'required' => empty($value) ? "O campo {$field} é obrigatório." : null,
            'email' => filter_var($value, FILTER_VALIDATE_EMAIL) === false
                ? "O campo {$field} deve ser um email válido." : null,
            'min:3' => strlen((string) $value) < 3
                ? "O campo {$field} deve ter no mínimo 3 caracteres." : null,
            default => null,
        };
    }

    public function getErrors(): array
    {
        return $this->errors;
    }

    public function isValid(): bool
    {
        return empty($this->errors);
    }
}

class ContactForm
{
    use ValidatableTrait;

    public function __construct(
        public string $name,
        public string $email,
        public string $message,
    ) {}

    // ✅ Obrigatório: definir regras de validação
    protected function validationRules(): array
    {
        return [
            'name' => ['required', 'min:3'],
            'email' => ['required', 'email'],
            'message' => ['required'],
        ];
    }
}

// Uso
$form = new ContactForm(name: '', email: 'invalido', message: '');

if (!$form->validate()) {
    foreach ($form->getErrors() as $field => $messages) {
        foreach ($messages as $msg) {
            echo "❌ {$msg}" . PHP_EOL;
        }
    }
}
```

### 41.3 Resolução de conflitos

Quando dois traits definem métodos com o mesmo nome, o PHP exige resolução explícita. Use `insteadof` para escolher qual usar e `as` para criar aliases:
```php
<?php

declare(strict_types=1);

// Quando dois traits têm métodos com o MESMO nome → conflito!
trait FileLoggerTrait
{
    public function log(string $message): void
    {
        echo "[FILE] {$message}" . PHP_EOL;
    }

    public function process(): void
    {
        $this->log('Processing via FileLogger...');
    }
}

trait AuditLoggerTrait
{
    public function log(string $message): void
    {
        echo "[AUDIT] {$message}" . PHP_EOL;
    }

    public function process(): void
    {
        $this->log('Processing via AuditLogger...');
    }
}

class Service
{
    use FileLoggerTrait, AuditLoggerTrait {
        // Resolver conflito: usar log() de FileLoggerTrait
        FileLoggerTrait::log insteadof AuditLoggerTrait;

        // Criar alias para log() de AuditLoggerTrait
        AuditLoggerTrait::log as auditLog;

        // Usar process() de FileLoggerTrait
        FileLoggerTrait::process insteadof AuditLoggerTrait;
    }

    public function execute(): void
    {
        $this->log('Normal log message');    // FileLoggerTrait::log
        $this->auditLog('Audit message');    // AuditLoggerTrait::log
        $this->process();                     // FileLoggerTrait::process
    }
}

$service = new Service();
$service->execute();
// [FILE] Normal log message
// [AUDIT] Audit message
// [FILE] Processing via FileLogger...
```

### 41.4 Traits compostos (trait usando trait)

Um trait pode usar outro trait, criando composição hierárquica. A classe que usa o trait composto ganha todos os métodos da cadeia:
```php
<?php

declare(strict_types=1);

// Um trait pode usar OUTRO trait — composição hierárquica
trait LoggableTrait
{
    protected function log(string $message): void
    {
        echo "[LOG] {$message}" . PHP_EOL;
    }
}

trait TrackableTrait
{
    use LoggableTrait; // ← Trait composto!

    protected array $operations = [];

    protected function track(string $operation): void
    {
        $this->operations[] = [
            'operation' => $operation,
            'timestamp' => time(),
        ];

        $this->log("Operação rastreada: {$operation}");
    }

    public function getHistory(): array
    {
        return $this->operations;
    }
}

class BankAccount
{
    use TrackableTrait; // Ganha LoggableTrait + TrackableTrait

    private float $balance = 0;

    public function deposit(float $amount): void
    {
        $this->balance += $amount;
        $this->track("Depósito de R$ {$amount}");
    }

    public function withdraw(float $amount): void
    {
        if ($amount > $this->balance) {
            throw new RuntimeException('Saldo insuficiente.');
        }

        $this->balance -= $amount;
        $this->track("Saque de R$ {$amount}");
    }

    public function getBalance(): float
    {
        return $this->balance;
    }
}

$account = new BankAccount();
$account->deposit(1000);
$account->withdraw(200);

echo "Saldo: R$ {$account->getBalance()}" . PHP_EOL; // R$ 800

print_r($account->getHistory());
// [
//   ['operation' => 'Depósito de R$ 1000', 'timestamp' => ...],
//   ['operation' => 'Saque de R$ 200', 'timestamp' => ...],
// ]
```

### 41.5 Traits com visibility overrides

Ao importar um trait, você pode alterar a visibilidade dos métodos com `as private`, `as protected` ou `as public`. Útil para restringir acesso a métodos que devem ser apenas internos:
```php
<?php

declare(strict_types=1);

trait HelloTrait
{
    public function sayHello(): string
    {
        return 'Hello from trait!';
    }
}

class PublicGreeter
{
    use HelloTrait; // sayHello() permanece public
}

class PrivateGreeter
{
    use HelloTrait {
        // ✅ Alterar visibilidade ao importar
        sayHello as private;
    }

    public function greet(): string
    {
        return $this->sayHello(); // Acessível internamente
    }
}

$public = new PublicGreeter();
echo $public->sayHello() . PHP_EOL; // ✅ Funciona

$private = new PrivateGreeter();
echo $private->greet() . PHP_EOL;   // ✅ Funciona via proxy
// $private->sayHello();             // ❌ ERRO: método privado
```

### 41.6 Exemplo prático: trait Sluggable

Este trait gera URLs amigáveis (slugs) a partir de texto, removendo acentos e caracteres especiais. Reutilizável em qualquer entidade com título:
```php
<?php

declare(strict_types=1);

// Trait reutilizável para gerar URLs amigáveis (slugs)
trait SluggableTrait
{
    protected string $slug = '';

    public function generateSlug(string $text): string
    {
        $slug = mb_strtolower($text);

        // Substituir caracteres acentuados
        $replacements = [
            'á' => 'a', 'é' => 'e', 'í' => 'i', 'ó' => 'o', 'ú' => 'u',
            'ã' => 'a', 'õ' => 'o', 'ç' => 'c', 'â' => 'a', 'ê' => 'e',
            'î' => 'i', 'ô' => 'o', 'û' => 'u', 'ü' => 'u',
        ];
        $slug = strtr($slug, $replacements);

        // Manter apenas letras, números e hífens
        $slug = preg_replace('/[^a-z0-9\s-]/', '', $slug);
        $slug = preg_replace('/[\s-]+/', '-', $slug);
        $slug = trim($slug, '-');

        $this->slug = $slug;

        return $slug;
    }

    public function getSlug(): string
    {
        return $this->slug;
    }
}

class BlogPost
{
    use SluggableTrait;

    public function __construct(
        public readonly string $title,
        public readonly string $content,
    ) {
        $this->generateSlug($title);
    }
}

$post = new BlogPost(
    title: 'Programação em PHP é Fácil!',
    content: 'Conteúdo do post...',
);

echo $post->getSlug() . PHP_EOL;
// programacao-em-php-e-facil
```

### 📝 Exercícios do Capítulo 41

1. Crie trait `CacheableTrait` que armazena resultados de métodos em cache automático
2. Implemente trait `SearchableTrait` com filtros dinâmicos e ordenação
3. Faça trait `ExportableTrait` para exportar dados em JSON, CSV e XML
4. Crie trait `EventEmitterTrait` para sistema de eventos pub/sub
5. Resolva conflitos complexos entre 3+ traits com `insteadof` e `as`

---

## 42. OOP — Interfaces Avançado

Interfaces avançadas vão além de contratos simples: o Interface Segregation Principle (ISP) mantém interfaces pequenas e específicas, interfaces fluentes permitem encadeamento elegante, e o Strategy Pattern troca algoritmos em runtime.

### 42.1 Interface Segregation Principle (ISP)

O ISP diz: **nenhuma classe deve ser forçada a implementar métodos que não usa**. Divida interfaces grandes em interfaces pequenas e específicas:
```php
<?php

declare(strict_types=1);

// ❌ Interface "gorda" — obriga implementar métodos desnecessários
interface FatWorkerInterface
{
    public function work(): void;
    public function eat(): void;
    public function sleep(): void;
    public function code(): void;
}

// ✅ Interfaces segregadas — pequenas e específicas
interface WorkableInterface
{
    public function work(): void;
}

interface FeedableInterface
{
    public function eat(): void;
}

interface SleepableInterface
{
    public function sleep(): void;
}

interface CodableInterface
{
    public function code(): void;
}

// Classes implementam APENAS o que precisam
class Developer implements WorkableInterface, CodableInterface, FeedableInterface
{
    public function work(): void
    {
        echo 'Desenvolvedor trabalhando...' . PHP_EOL;
    }

    public function code(): void
    {
        echo 'Escrevendo PHP 8.5...' . PHP_EOL;
    }

    public function eat(): void
    {
        echo 'Pausa para café ☕' . PHP_EOL;
    }
}

class Robot implements WorkableInterface
{
    public function work(): void
    {
        echo 'Robô trabalhando 24/7 🤖' . PHP_EOL;
    }

    // ✅ Robô NÃO come, NÃO dorme, NÃO programa
    // Com ISP, não é obrigado a implementar esses métodos!
}
```

### 42.2 Interfaces com constantes

Interfaces podem definir constantes públicas, úteis para enumerar estados ou configurações. No PHP 8.1+, prefira Enums para este propósito:
```php
<?php

declare(strict_types=1);

// ✅ Interfaces podem definir constantes — ideal para enumeração de estados
// (Para PHP 8.1+, considere Enums como alternativa moderna)
interface OrderStatusInterface
{
    public const PENDING    = 'pending';
    public const PROCESSING = 'processing';
    public const SHIPPED    = 'shipped';
    public const DELIVERED  = 'delivered';
    public const CANCELLED  = 'cancelled';

    public function getStatus(): string;
    public function updateStatus(string $newStatus): void;
}

class Order implements OrderStatusInterface
{
    private string $status = self::PENDING;

    public function getStatus(): string
    {
        return $this->status;
    }

    public function updateStatus(string $newStatus): void
    {
        $validStatuses = [
            self::PENDING,
            self::PROCESSING,
            self::SHIPPED,
            self::DELIVERED,
            self::CANCELLED,
        ];

        if (!in_array($newStatus, $validStatuses, strict: true)) {
            throw new InvalidArgumentException(
                "Status inválido: {$newStatus}",
            );
        }

        $this->status = $newStatus;
    }
}

$order = new Order();
$order->updateStatus(OrderStatusInterface::PROCESSING);
echo $order->getStatus() . PHP_EOL; // processing
```

### 42.3 Interfaces fluentes (fluent interface)

Interfaces fluentes definem métodos que retornam `static` (a própria instância), permitindo encadeamento elegante como `$query->select()->from()->where()`:
```php
<?php

declare(strict_types=1);

// Interface fluente: cada método retorna $this (self)
// Permite encadeamento elegante: $obj->a()->b()->c()
interface QueryBuilderInterface
{
    public function select(array $columns): static;
    public function from(string $table): static;
    public function where(string $condition, mixed $value): static;
    public function orderBy(string $column, string $direction = 'ASC'): static;
    public function limit(int $limit): static;
    public function toSql(): string;
}

class QueryBuilder implements QueryBuilderInterface
{
    private array $columns = ['*'];
    private string $table = '';
    private array $conditions = [];
    private array $bindings = [];
    private ?string $orderClause = null;
    private ?int $limitValue = null;

    public function select(array $columns): static
    {
        $this->columns = $columns;
        return $this;
    }

    public function from(string $table): static
    {
        $this->table = $table;
        return $this;
    }

    public function where(string $condition, mixed $value): static
    {
        $this->conditions[] = $condition;
        $this->bindings[] = $value;
        return $this;
    }

    public function orderBy(string $column, string $direction = 'ASC'): static
    {
        $this->orderClause = "{$column} {$direction}";
        return $this;
    }

    public function limit(int $limit): static
    {
        $this->limitValue = $limit;
        return $this;
    }

    public function toSql(): string
    {
        $sql = 'SELECT ' . implode(', ', $this->columns);
        $sql .= " FROM {$this->table}";

        if (!empty($this->conditions)) {
            $sql .= ' WHERE ' . implode(' AND ', $this->conditions);
        }

        if ($this->orderClause !== null) {
            $sql .= " ORDER BY {$this->orderClause}";
        }

        if ($this->limitValue !== null) {
            $sql .= " LIMIT {$this->limitValue}";
        }

        return $sql;
    }

    public function getBindings(): array
    {
        return $this->bindings;
    }
}

// ✅ Uso fluente — leitura natural como SQL
$query = (new QueryBuilder())
    ->select(['id', 'name', 'email'])
    ->from('users')
    ->where('active = ?', 1)
    ->where('role = ?', 'admin')
    ->orderBy('name', 'ASC')
    ->limit(10);

echo $query->toSql() . PHP_EOL;
// SELECT id, name, email FROM users WHERE active = ? AND role = ? ORDER BY name ASC LIMIT 10
```

### 42.4 Contratos de repositório

Interfaces segregadas para repositórios separam responsabilidades: CRUD básico, busca e paginação. Cada classe implementa apenas as interfaces que precisa:
```php
<?php

declare(strict_types=1);

// ✅ Contratos bem segregados — cada interface tem responsabilidade única

interface RepositoryInterface
{
    public function find(int $id): ?array;
    public function findAll(): array;
    public function create(array $data): int;
    public function update(int $id, array $data): bool;
    public function delete(int $id): bool;
}

interface SearchableRepositoryInterface
{
    public function search(array $criteria): array;
    public function searchByField(string $field, mixed $value): array;
}

interface PaginatableRepositoryInterface
{
    public function paginate(int $page, int $perPage): array;
    public function count(): int;
}

// ✅ Implementa apenas as interfaces necessárias
class UserRepository implements
    RepositoryInterface,
    SearchableRepositoryInterface,
    PaginatableRepositoryInterface
{
    public function __construct(
        private readonly PDO $pdo,
    ) {}

    public function find(int $id): ?array
    {
        $stmt = $this->pdo->prepare('SELECT * FROM users WHERE id = :id');
        $stmt->execute(['id' => $id]);
        $result = $stmt->fetch(PDO::FETCH_ASSOC);

        return $result ?: null;
    }

    public function findAll(): array
    {
        return $this->pdo
            ->query('SELECT * FROM users')
            ->fetchAll(PDO::FETCH_ASSOC);
    }

    public function create(array $data): int
    {
        $stmt = $this->pdo->prepare(
            'INSERT INTO users (name, email) VALUES (:name, :email)',
        );
        $stmt->execute([
            'name' => $data['name'],
            'email' => $data['email'],
        ]);

        return (int) $this->pdo->lastInsertId();
    }

    public function update(int $id, array $data): bool
    {
        $stmt = $this->pdo->prepare(
            'UPDATE users SET name = :name, email = :email WHERE id = :id',
        );

        return $stmt->execute([
            'name' => $data['name'],
            'email' => $data['email'],
            'id' => $id,
        ]);
    }

    public function delete(int $id): bool
    {
        $stmt = $this->pdo->prepare('DELETE FROM users WHERE id = :id');

        return $stmt->execute(['id' => $id]);
    }

    public function search(array $criteria): array
    {
        $conditions = [];
        $bindings = [];

        foreach ($criteria as $field => $value) {
            $conditions[] = "{$field} LIKE :{$field}";
            $bindings[$field] = "%{$value}%";
        }

        $sql = 'SELECT * FROM users';

        if (!empty($conditions)) {
            $sql .= ' WHERE ' . implode(' AND ', $conditions);
        }

        $stmt = $this->pdo->prepare($sql);
        $stmt->execute($bindings);

        return $stmt->fetchAll(PDO::FETCH_ASSOC);
    }

    public function searchByField(string $field, mixed $value): array
    {
        // ⚠️ $field é validado internamente — nunca vem do usuário
        $allowed = ['name', 'email', 'status'];

        if (!in_array($field, $allowed, strict: true)) {
            throw new InvalidArgumentException("Campo não permitido: {$field}");
        }

        $stmt = $this->pdo->prepare("SELECT * FROM users WHERE {$field} = :value");
        $stmt->execute(['value' => $value]);

        return $stmt->fetchAll(PDO::FETCH_ASSOC);
    }

    public function paginate(int $page, int $perPage): array
    {
        $offset = ($page - 1) * $perPage;

        $stmt = $this->pdo->prepare(
            'SELECT * FROM users ORDER BY id LIMIT :limit OFFSET :offset',
        );
        $stmt->bindValue('limit', $perPage, PDO::PARAM_INT);
        $stmt->bindValue('offset', $offset, PDO::PARAM_INT);
        $stmt->execute();

        return [
            'data' => $stmt->fetchAll(PDO::FETCH_ASSOC),
            'page' => $page,
            'perPage' => $perPage,
            'total' => $this->count(),
        ];
    }

    public function count(): int
    {
        return (int) $this->pdo
            ->query('SELECT COUNT(*) FROM users')
            ->fetchColumn();
    }
}
```

### 42.5 Strategy Pattern com interfaces

O Strategy Pattern define uma família de algoritmos intercambiáveis por trás de uma interface comum. O contexto usa a interface, e você pode trocar a estratégia em runtime:
```php
<?php

declare(strict_types=1);

// ✅ Strategy: trocar algoritmos em runtime via interface
interface PaymentStrategyInterface
{
    public function pay(float $amount): array;
    public function getName(): string;
}

class CreditCardPayment implements PaymentStrategyInterface
{
    public function __construct(
        private readonly string $cardNumber,
        private readonly string $expiryDate,
    ) {}

    public function pay(float $amount): array
    {
        // Lógica de pagamento com cartão
        return [
            'method' => $this->getName(),
            'amount' => $amount,
            'status' => 'approved',
            'card_last4' => substr($this->cardNumber, -4),
        ];
    }

    public function getName(): string
    {
        return 'Cartão de Crédito';
    }
}

class PixPayment implements PaymentStrategyInterface
{
    public function __construct(
        private readonly string $pixKey,
    ) {}

    public function pay(float $amount): array
    {
        return [
            'method' => $this->getName(),
            'amount' => $amount,
            'status' => 'pending',
            'pix_key' => $this->pixKey,
            'qr_code' => 'data:image/png;base64,...',
        ];
    }

    public function getName(): string
    {
        return 'PIX';
    }
}

class BoletoPayment implements PaymentStrategyInterface
{
    public function pay(float $amount): array
    {
        return [
            'method' => $this->getName(),
            'amount' => $amount,
            'status' => 'pending',
            'boleto_url' => 'https://banco.com/boleto/123',
            'due_date' => date('Y-m-d', strtotime('+3 days')),
        ];
    }

    public function getName(): string
    {
        return 'Boleto';
    }
}

// Contexto que usa a Strategy
class PaymentProcessor
{
    public function __construct(
        private PaymentStrategyInterface $strategy,
    ) {}

    public function setStrategy(PaymentStrategyInterface $strategy): void
    {
        $this->strategy = $strategy;
    }

    public function processPayment(float $amount): array
    {
        echo "Processando pagamento via {$this->strategy->getName()}..." . PHP_EOL;

        return $this->strategy->pay($amount);
    }
}

// Uso — trocar estratégia em runtime
$processor = new PaymentProcessor(
    new CreditCardPayment('4111111111111111', '12/28'),
);

$result = $processor->processPayment(299.90);
print_r($result);

// Mudar para PIX
$processor->setStrategy(new PixPayment('joao@email.com'));
$result = $processor->processPayment(199.90);
print_r($result);
```

### 📝 Exercícios do Capítulo 42

1. Crie interfaces segregadas para sistema de notificações (Email, SMS, Push, InApp)
2. Implemente Repository pattern completo com interfaces + testes
3. Faça interface fluente para `EmailBuilder` com `to()`, `subject()`, `body()`, `send()`
4. Crie Strategy pattern para diferentes algoritmos de ordenação
5. Implemente Observer pattern com `ObservableInterface` e `ObserverInterface`

---

## 43. OOP — Abstract Classes Avançado

Classes abstratas combinam contrato (métodos abstratos) com código reutilizável (métodos concretos). São a escolha ideal quando subclasses compartilham lógica significativa mas diferem em pontos específicos.

### 43.1 Classes abstratas com métodos concretos

Uma classe abstrata pode ter métodos abstratos (que subclasses **devem** implementar) e métodos concretos (que são **herdados** automaticamente). Isso evita duplicação:
```php
<?php

declare(strict_types=1);

// Classe abstrata: NÃO pode ser instanciada, serve de "molde"
// Pode ter métodos abstratos (sem corpo) E concretos (com corpo)
abstract class Shape
{
    public function __construct(
        protected string $color,
    ) {}

    // ── Métodos ABSTRATOS: subclasses DEVEM implementar ──
    abstract public function calculateArea(): float;
    abstract public function calculatePerimeter(): float;

    // ── Métodos CONCRETOS: já implementados, herdados ──
    public function getColor(): string
    {
        return $this->color;
    }

    public function setColor(string $color): void
    {
        $this->color = $color;
    }

    public function displayInfo(): string
    {
        return sprintf(
            '%s — Cor: %s, Área: %.2f, Perímetro: %.2f',
            static::class,
            $this->color,
            $this->calculateArea(),
            $this->calculatePerimeter(),
        );
    }

    // ── Template Method: esqueleto final + hook sobrescrevível ──
    final public function render(): string
    {
        $html = "<div style='color: {$this->color}'>";
        $html .= $this->renderContent();
        $html .= '</div>';

        return $html;
    }

    protected function renderContent(): string
    {
        return $this->displayInfo();
    }
}

class Rectangle extends Shape
{
    public function __construct(
        string $color,
        private readonly float $width,
        private readonly float $height,
    ) {
        parent::__construct($color);
    }

    public function calculateArea(): float
    {
        return $this->width * $this->height;
    }

    public function calculatePerimeter(): float
    {
        return 2 * ($this->width + $this->height);
    }
}

class Circle extends Shape
{
    public function __construct(
        string $color,
        private readonly float $radius,
    ) {
        parent::__construct($color);
    }

    public function calculateArea(): float
    {
        return M_PI * ($this->radius ** 2);
    }

    public function calculatePerimeter(): float
    {
        return 2 * M_PI * $this->radius;
    }
}

// Uso
$rectangle = new Rectangle(color: 'blue', width: 5, height: 10);
echo $rectangle->displayInfo() . PHP_EOL;
// Rectangle — Cor: blue, Área: 50.00, Perímetro: 30.00

$circle = new Circle(color: 'red', radius: 5);
echo $circle->displayInfo() . PHP_EOL;
// Circle — Cor: red, Área: 78.54, Perímetro: 31.42

// new Shape('green');  // ❌ ERRO: classe abstrata não pode ser instanciada
```

### 43.2 Template Method Pattern

O Template Method define o **esqueleto de um algoritmo** na classe abstrata, delegando passos específicos para as subclasses. O método principal é `final` para impedir alteração do fluxo:
```php
<?php

declare(strict_types=1);

// Template Method: a classe abstrata define o ESQUELETO do algoritmo,
// e as subclasses implementam os passos específicos.
abstract class PaymentProcessor
{
    // ✅ final: nenhuma subclasse pode alterar o fluxo geral
    final public function process(float $amount): array
    {
        // 1. Validar
        if (!$this->validate($amount)) {
            return ['success' => false, 'error' => 'Valor inválido.'];
        }

        // 2. Preparar dados
        $transactionData = $this->prepareTransaction($amount);

        // 3. Executar (cada subclasse implementa)
        $result = $this->executePayment($transactionData);

        // 4. Registrar
        $this->logTransaction($result);

        return $result;
    }

    // Hook com implementação padrão (pode ser sobrescrito)
    protected function validate(float $amount): bool
    {
        return $amount > 0;
    }

    protected function prepareTransaction(float $amount): array
    {
        return [
            'amount' => $amount,
            'timestamp' => time(),
            'gateway' => static::class,
        ];
    }

    protected function logTransaction(array $result): void
    {
        $status = $result['success'] ? 'SUCCESS' : 'FAILED';
        error_log("Transaction: {$status} — " . json_encode($result));
    }

    // ⚠️ Abstrato: CADA gateway implementa sua lógica
    abstract protected function executePayment(array $data): array;
}

class CreditCardProcessor extends PaymentProcessor
{
    protected function executePayment(array $data): array
    {
        return [
            'success' => true,
            'transaction_id' => 'CC_' . uniqid(),
            'amount' => $data['amount'],
        ];
    }
}

class PixProcessor extends PaymentProcessor
{
    // Sobrescreve validação: PIX tem valor mínimo de R$ 1
    protected function validate(float $amount): bool
    {
        return parent::validate($amount) && $amount >= 1.0;
    }

    protected function executePayment(array $data): array
    {
        return [
            'success' => true,
            'transaction_id' => 'PIX_' . uniqid(),
            'amount' => $data['amount'],
            'qr_code' => 'data:image/png;base64,...',
        ];
    }
}

// Uso — o fluxo geral é IDÊNTICO, só a execução muda
$cardProcessor = new CreditCardProcessor();
$result = $cardProcessor->process(100.00);

$pixProcessor = new PixProcessor();
$result = $pixProcessor->process(50.00);
```

### 43.3 Abstract Classes vs Interfaces

Interfaces definem contratos puros (o quê), classes abstratas oferecem implementação parcial (como em parte). Uma classe pode estender **uma** abstrata e implementar **várias** interfaces:
```php
<?php

declare(strict_types=1);

// ── Interface: apenas CONTRATO (o quê fazer) ──
interface PayableInterface
{
    public function charge(float $amount): bool;
    public function getFee(): float;
}

// ── Abstract Class: contrato + implementação parcial (como fazer em parte) ──
abstract class BaseProcessor
{
    protected array $logs = [];

    // Método concreto: reutilizado por TODAS as subclasses
    public function addLog(string $message): void
    {
        $this->logs[] = [
            'timestamp' => date('Y-m-d H:i:s'),
            'message' => $message,
        ];
    }

    public function getLogs(): array
    {
        return $this->logs;
    }

    // Método abstrato: cada subclasse implementa
    abstract public function process(float $amount): bool;
}

// ✅ Classe pode estender UMA abstrata E implementar VÁRIAS interfaces
class BoletoProcessor extends BaseProcessor implements PayableInterface
{
    public function process(float $amount): bool
    {
        $this->addLog("Processando boleto: R$ {$amount}");

        return true;
    }

    public function charge(float $amount): bool
    {
        return $this->process($amount);
    }

    public function getFee(): float
    {
        return 2.50; // Taxa fixa do boleto
    }
}

// ┌──────────────────────────────────────────────────┐
// │ Quando usar cada um:                             │
// │ • Interface: contrato puro, sem código            │
// │ • Abstract: código compartilhado entre subclasses │
// │ • Ambos: contrato público + base de código        │
// └──────────────────────────────────────────────────┘
```

### 43.4 Hierarquia de classes abstratas

Classes abstratas podem estender outras abstratas, criando hierarquias em camadas onde cada nível adiciona requisitos e funcionalidades:
```php
<?php

declare(strict_types=1);

// Abstratas podem estender outras abstratas — hierarquia em camadas
abstract class Vehicle
{
    public function __construct(
        protected readonly string $make,
        protected readonly string $model,
    ) {}

    abstract public function start(): string;

    public function getDescription(): string
    {
        return "{$this->make} {$this->model}";
    }
}

abstract class MotorizedVehicle extends Vehicle
{
    public function __construct(
        string $make,
        string $model,
        protected readonly int $engineCC,
    ) {
        parent::__construct($make, $model);
    }

    abstract public function accelerate(): string;

    public function getHorsePower(): int
    {
        return (int) ($this->engineCC * 0.1); // Estimativa simplificada
    }
}

class Car extends MotorizedVehicle
{
    public function start(): string
    {
        return "Carro ligado: motor {$this->engineCC}cc 🚗";
    }

    public function accelerate(): string
    {
        return "Acelerando com {$this->getHorsePower()} CV";
    }
}

class Motorcycle extends MotorizedVehicle
{
    public function start(): string
    {
        return "Moto ligada: motor {$this->engineCC}cc 🏍️";
    }

    public function accelerate(): string
    {
        return "Moto acelerando com {$this->getHorsePower()} CV";
    }
}

// Uso
$car = new Car('Toyota', 'Corolla', 2000);
echo $car->start() . PHP_EOL;      // Carro ligado: motor 2000cc 🚗
echo $car->accelerate() . PHP_EOL; // Acelerando com 200 CV

$motorcycle = new Motorcycle('Honda', 'CB 500', 500);
echo $motorcycle->start() . PHP_EOL;       // Moto ligada: motor 500cc 🏍️
echo $motorcycle->getDescription() . PHP_EOL; // Honda CB 500
```

### 📝 Exercícios do Capítulo 43

1. Crie hierarquia abstrata para diferentes tipos de relatório (PDF, CSV, HTML)
2. Implemente Template Method para processamento de pedidos (validar → calcular → finalizar)
3. Faça classe abstrata `NotificationSender` com subclasses `EmailSender`, `SmsSender`, `PushSender`
4. Crie base abstrata `Validator` com subclasses para CPF, email e telefone
5. Compare abstract class + interface combinadas num sistema de pagamento

---

## 44. OOP — Class Constants

Constantes de classe armazenam valores imutáveis que pertencem à classe, não a instâncias. Desde PHP 8.3, podem ter **tipo explícito**. São ideais para configurações, limites e valores que nunca mudam em runtime.

### 44.1 Constantes de classe básicas

Constantes são declaradas com `const` e acessadas via `Classe::CONSTANTE`. Suportam os modificadores `public`, `protected` e `private` para controlar visibilidade:
```php
<?php

declare(strict_types=1);

class DatabaseConfig
{
    // Constantes públicas — acessíveis de qualquer lugar
    public const HOST = 'localhost';
    public const PORT = 3306;
    public const CHARSET = 'utf8mb4';

    // Constantes privadas — apenas dentro da classe
    private const USERNAME = 'root';
    private const PASSWORD = 'secret';

    public static function connect(): PDO
    {
        $dsn = sprintf(
            'mysql:host=%s;port=%d;charset=%s',
            self::HOST,
            self::PORT,
            self::CHARSET,
        );

        return new PDO($dsn, self::USERNAME, self::PASSWORD);
    }
}

// ✅ Constantes públicas
echo DatabaseConfig::HOST . PHP_EOL;    // localhost
echo DatabaseConfig::PORT . PHP_EOL;    // 3306

// DatabaseConfig::USERNAME;  // ❌ ERRO: constante privada
```

### 44.2 Constantes tipadas (PHP 8.3+)

A partir do PHP 8.3, constantes podem especificar o tipo explicitamente (`string`, `int`, `float`, `bool`, `array`), prevenindo erros de tipo em tempo de compilação:
```php
<?php

declare(strict_types=1);

class AppSettings
{
    // ✅ PHP 8.3+: constantes podem ter tipo explícito
    public const string APP_NAME = 'Meu Sistema';
    public const string VERSION = '2.0.0';
    public const int MAX_UPLOAD_SIZE = 5_242_880; // 5 MB em bytes
    public const float TAX_RATE = 0.15;
    public const bool DEBUG = false;
    public const array SUPPORTED_LANGUAGES = ['pt-BR', 'en-US', 'es-ES'];

    public static function isLanguageSupported(string $language): bool
    {
        return in_array($language, self::SUPPORTED_LANGUAGES, strict: true);
    }
}

echo AppSettings::APP_NAME . PHP_EOL;        // Meu Sistema
echo AppSettings::MAX_UPLOAD_SIZE . PHP_EOL;  // 5242880

var_dump(AppSettings::isLanguageSupported('pt-BR')); // true
var_dump(AppSettings::isLanguageSupported('fr-FR')); // false
```

### 44.3 Constantes em Enums

Enums podem ter constantes que agrupam `cases` logicamente, facilitando verificações como "este status é editável?" ou "é um estado final?":
```php
<?php

declare(strict_types=1);

enum OrderStatus: string
{
    case Pending    = 'pending';
    case Approved   = 'approved';
    case Shipped    = 'shipped';
    case Delivered  = 'delivered';
    case Cancelled  = 'cancelled';

    // ✅ Enums podem ter constantes que agrupam cases
    public const array EDITABLE_STATES = [
        self::Pending,
        self::Approved,
    ];

    public const array FINAL_STATES = [
        self::Delivered,
        self::Cancelled,
    ];

    public function canEdit(): bool
    {
        return in_array($this, self::EDITABLE_STATES, strict: true);
    }

    public function isFinal(): bool
    {
        return in_array($this, self::FINAL_STATES, strict: true);
    }

    public function label(): string
    {
        return match ($this) {
            self::Pending   => 'Pendente',
            self::Approved  => 'Aprovado',
            self::Shipped   => 'Enviado',
            self::Delivered => 'Entregue',
            self::Cancelled => 'Cancelado',
        };
    }
}

$status = OrderStatus::Pending;
echo $status->label() . PHP_EOL;   // Pendente
echo $status->canEdit() ? 'Pode editar' : 'Bloqueado'; // Pode editar
```

### 44.4 Constantes herdadas e late static binding

Constantes são herdáveis e sobrescrevíveis. A diferença entre `self::` e `static::` é crucial: `self` resolve na classe onde foi definido, `static` resolve na classe que chamou (late binding):
```php
<?php

declare(strict_types=1);

class Animal
{
    public const string TYPE = 'Generic Animal';
    protected const string HABITAT = 'Terrestrial';

    // self:: resolve para Animal (onde foi definido)
    public static function getTypeSelf(): string
    {
        return self::TYPE;
    }

    // static:: resolve para a classe que CHAMOU (late binding)
    public static function getTypeStatic(): string
    {
        return static::TYPE;
    }

    public static function getHabitat(): string
    {
        return static::HABITAT;
    }
}

class Dog extends Animal
{
    public const string TYPE = 'Dog';
    protected const string HABITAT = 'Domestic';
}

class Fish extends Animal
{
    public const string TYPE = 'Fish';
    protected const string HABITAT = 'Aquatic';
}

echo Animal::TYPE . PHP_EOL; // Generic Animal
echo Dog::TYPE . PHP_EOL;    // Dog
echo Fish::TYPE . PHP_EOL;   // Fish

// self:: vs static::
echo Dog::getTypeSelf() . PHP_EOL;    // Generic Animal (self)
echo Dog::getTypeStatic() . PHP_EOL;  // Dog (static)

echo Fish::getHabitat() . PHP_EOL;    // Aquatic
```

### 44.5 Constantes mágicas

PHP oferece constantes mágicas predefinidas que mudam conforme o contexto de execução (`__CLASS__`, `__METHOD__`, `__FILE__`, `__LINE__`, etc.). Úteis para logging e debugging:
```php
<?php

declare(strict_types=1);

// PHP tem constantes mágicas predefinidas — mudam conforme o contexto
class DebugHelper
{
    public function displayContext(): void
    {
        echo '__CLASS__:     ' . __CLASS__ . PHP_EOL;     // Nome da classe
        echo '__METHOD__:    ' . __METHOD__ . PHP_EOL;    // Classe::método
        echo '__FUNCTION__:  ' . __FUNCTION__ . PHP_EOL;  // Nome da função
        echo '__FILE__:      ' . __FILE__ . PHP_EOL;      // Caminho do arquivo
        echo '__DIR__:       ' . __DIR__ . PHP_EOL;       // Diretório do arquivo
        echo '__LINE__:      ' . __LINE__ . PHP_EOL;      // Linha atual
        echo '__NAMESPACE__: ' . __NAMESPACE__ . PHP_EOL;  // Namespace atual
    }

    public function logWithContext(string $message): void
    {
        echo sprintf(
            '[%s] [%s] %s',
            date('Y-m-d H:i:s'),
            __METHOD__,
            $message,
        ) . PHP_EOL;
    }
}

$debug = new DebugHelper();
$debug->logWithContext('Sistema iniciado.');
// [2026-02-10 08:30:00] [DebugHelper::logWithContext] Sistema iniciado.
```

### 44.6 Uso prático: configuração centralizada

Constantes de classe centralizam configurações que seriam variáveis de ambiente em produção. Métodos estáticos auxiliares tornam o consumo ergonômico:
```php
<?php

declare(strict_types=1);

class AppConfig
{
    // ── Ambiente ──
    public const string ENVIRONMENT = 'production';

    // ── Banco de dados ──
    public const string DB_HOST = 'localhost';
    public const int DB_PORT = 3306;
    public const string DB_NAME = 'app_db';

    // ── Upload ──
    public const int MAX_FILE_SIZE = 5 * 1024 * 1024; // 5 MB
    public const array ALLOWED_EXTENSIONS = ['jpg', 'png', 'webp', 'pdf'];

    // ── Cache e paginação ──
    public const int CACHE_TTL = 3600;
    public const int ITEMS_PER_PAGE = 20;

    // ── API ──
    public const string API_VERSION = 'v2';
    public const int RATE_LIMIT_PER_MINUTE = 100;

    public static function isProduction(): bool
    {
        return self::ENVIRONMENT === 'production';
    }

    public static function getDatabaseDsn(): string
    {
        return sprintf(
            'mysql:host=%s;port=%d;dbname=%s;charset=utf8mb4',
            self::DB_HOST,
            self::DB_PORT,
            self::DB_NAME,
        );
    }

    public static function isExtensionAllowed(string $extension): bool
    {
        return in_array(
            strtolower($extension),
            self::ALLOWED_EXTENSIONS,
            strict: true,
        );
    }
}

// Uso centralizado em todo o projeto
if (AppConfig::isProduction()) {
    ini_set('display_errors', '0');
}

echo AppConfig::getDatabaseDsn() . PHP_EOL;
echo AppConfig::isExtensionAllowed('jpg') ? 'Permitido' : 'Bloqueado';
```

### 📝 Exercícios do Capítulo 44

1. Crie classe de configuração com constantes tipadas para sistema de e-commerce
2. Implemente sistema de permissões (RBAC) com constantes bitmask (`ADMIN = 1`, `EDITOR = 2`, etc.)
3. Faça enum `PaymentMethod` com constantes que agrupam métodos por categoria
4. Use constantes mágicas para criar logger com contexto automático
5. Crie hierarquia de classes com constantes herdadas e sobrescritas

---

## 45. OOP — Access Modifiers Detalhado

Modificadores de acesso controlam **quem pode ler e escrever** propriedades e métodos. PHP 8.4 introduz visibilidade assimétrica (`public private(set)`), e `readonly` garante imutabilidade pós-construção.

### 45.1 Public, Protected, Private

Os três níveis de visibilidade formam a base do encapsulamento: `public` (acesso livre), `protected` (classe + subclasses), `private` (apenas a própria classe):
```php
<?php

declare(strict_types=1);

class Vehicle
{
    // public: acessível de QUALQUER lugar
    public string $make;

    // protected: acessível na classe E nas subclasses
    protected string $model;

    // private: acessível APENAS na própria classe
    private string $chassisNumber;

    public function __construct(string $make, string $model, string $chassisNumber)
    {
        $this->make = $make;
        $this->model = $model;
        $this->chassisNumber = $chassisNumber;
    }

    // Método público — acessível de fora
    public function getDescription(): string
    {
        return "{$this->make} {$this->model} — Chassi: {$this->chassisNumber}";
    }

    // Método protegido — acessível nas subclasses
    protected function getModel(): string
    {
        return $this->model;
    }

    // Método privado — acessível APENAS aqui
    private function getChassisNumber(): string
    {
        return $this->chassisNumber;
    }
}

class Car extends Vehicle
{
    public function displayInfo(): string
    {
        $info = "Marca: {$this->make}" . PHP_EOL;      // ✅ public
        $info .= "Modelo: {$this->getModel()}" . PHP_EOL; // ✅ protected

        // $this->chassisNumber;     // ❌ ERRO: private do pai
        // $this->getChassisNumber(); // ❌ ERRO: private do pai

        return $info;
    }
}

$car = new Car('Toyota', 'Corolla', 'ABC123');

echo $car->make . PHP_EOL;          // ✅ public
echo $car->getDescription() . PHP_EOL; // ✅ método público

// $car->model;          // ❌ protected
// $car->chassisNumber;  // ❌ private
// $car->getModel();     // ❌ protected
```

### 45.2 Constructor Property Promotion com visibility

PHP 8.0+ permite declarar e inicializar propriedades diretamente nos parâmetros do construtor. Cada parâmetro com modificador de visibilidade se torna uma propriedade:
```php
<?php

declare(strict_types=1);

// PHP 8.0+: declarar e atribuir propriedades direto no construtor
class User
{
    public function __construct(
        public readonly int $id,          // Público e imutável
        public string $name,               // Público e mutável
        protected string $email,           // Protegido
        private string $passwordHash,      // Privado
    ) {}

    public function getEmail(): string
    {
        return $this->email;
    }

    public function verifyPassword(string $password): bool
    {
        return password_verify($password, $this->passwordHash);
    }
}

$user = new User(
    id: 1,
    name: 'João',
    email: 'joao@example.com',
    passwordHash: password_hash('secret123', PASSWORD_ARGON2ID),
);

echo $user->id . PHP_EOL;     // ✅ public readonly
echo $user->name . PHP_EOL;   // ✅ public

// $user->email;           // ❌ protected
// $user->passwordHash;    // ❌ private

echo $user->getEmail() . PHP_EOL;                   // ✅
echo $user->verifyPassword('secret123') ? '✅' : '❌'; // ✅
```

### 45.3 Readonly Properties (PHP 8.1+)

Propriedades `readonly` só podem ser atribuídas **uma vez** (no construtor). PHP 8.2+ permite `readonly class`, tornando todas as propriedades imutáveis:
```php
<?php

declare(strict_types=1);

class Product
{
    public function __construct(
        public readonly int $id,        // Imutável após construção
        public readonly string $sku,     // Imutável
        public string $name,             // Mutável
        public float $price,             // Mutável
    ) {}
}

$product = new Product(
    id: 1,
    sku: 'PROD-001',
    name: 'Notebook',
    price: 2500.00,
);

// ✅ Pode modificar propriedades NÃO readonly
$product->name = 'Notebook Dell';
$product->price = 2800.00;

// ❌ NÃO pode modificar readonly
// $product->id = 2;        // ERRO: Cannot modify readonly property
// $product->sku = 'PROD-002'; // ERRO

// ✅ PHP 8.2+: Readonly classes (TODAS as properties são readonly)
readonly class Money
{
    public function __construct(
        public float $amount,
        public string $currency,
    ) {}
}

$price = new Money(amount: 99.90, currency: 'BRL');
echo "R$ {$price->amount}" . PHP_EOL;
// $price->amount = 199.90; // ❌ ERRO
```

### 45.4 Asymmetric Visibility (PHP 8.4+)

PHP 8.4 permite visibilidades diferentes para leitura e escrita. Por exemplo, `public private(set)` significa leitura pública mas escrita apenas dentro da classe:
```php
<?php

declare(strict_types=1);

// PHP 8.4+: leitura e escrita com visibilidades DIFERENTES
class BankAccount
{
    // Leitura pública, escrita privada
    public private(set) float $balance = 0.0;

    // Leitura pública, escrita protegida
    public protected(set) string $status = 'active';

    public function deposit(float $amount): void
    {
        if ($amount <= 0) {
            throw new InvalidArgumentException('Valor deve ser positivo.');
        }

        $this->balance += $amount; // ✅ Escrita dentro da classe
    }

    public function withdraw(float $amount): bool
    {
        if ($amount <= 0 || $amount > $this->balance) {
            return false;
        }

        $this->balance -= $amount;

        return true;
    }
}

$account = new BankAccount();

// ✅ Leitura pública
echo $account->balance . PHP_EOL; // 0.0

// ✅ Modificação via métodos
$account->deposit(1000);
echo $account->balance . PHP_EOL; // 1000.0

// ❌ Escrita direta bloqueada: set é private
// $account->balance = 5000; // ERRO
```

### 45.5 Visibilidade de constantes

Constantes de classe também suportam `public`, `protected` e `private`. Isso protege chaves secretas e tokens internos de acesso externo:
```php
<?php

declare(strict_types=1);

class SecurityConfig
{
    // Constante pública — acessível de fora
    public const string APP_NAME = 'Meu Sistema';

    // Constante protegida — acessível em subclasses
    protected const string SECRET_KEY = 'sk_live_abc123';

    // Constante privada — apenas nesta classe
    private const string INTERNAL_TOKEN = 'internal_xyz789';

    public static function getVersion(): string
    {
        return '2.1.0'; // Pode acessar qualquer constante aqui
    }
}

class ExtendedConfig extends SecurityConfig
{
    public static function getKey(): string
    {
        return self::SECRET_KEY; // ✅ protected do pai
    }

    public static function getToken(): string
    {
        // return self::INTERNAL_TOKEN; // ❌ private do pai
        return 'N/A';
    }
}

echo SecurityConfig::APP_NAME . PHP_EOL; // ✅
// echo SecurityConfig::SECRET_KEY;       // ❌ protected
// echo SecurityConfig::INTERNAL_TOKEN;   // ❌ private

echo ExtendedConfig::getKey() . PHP_EOL; // ✅ via método
```

### 45.6 Visibilidade em Traits

Traits respeitam os mesmos modificadores de visibilidade. Métodos `private` no trait ficam inacessíveis mesmo para a classe que o usa — apenas outros métodos do próprio trait podem chamá-los:
```php
<?php

declare(strict_types=1);

trait AuditableTrait
{
    protected array $auditLog = [];

    // Método privado: só acessível dentro do TRAIT
    private function addAuditEntry(string $action): void
    {
        $this->auditLog[] = [
            'action' => $action,
            'timestamp' => date('Y-m-d H:i:s'),
        ];
    }

    // Método protegido: acessível na classe que usa o trait + subclasses
    protected function audit(string $action): void
    {
        $this->addAuditEntry($action);
    }

    // Método público: acessível de qualquer lugar
    public function getAuditLog(): array
    {
        return $this->auditLog;
    }
}

class OrderService
{
    use AuditableTrait;

    public function createOrder(array $data): void
    {
        // Lógica de criação...
        $this->audit('order_created'); // ✅ protected

        // $this->addAuditEntry('test'); // ❌ private do trait
    }
}

$service = new OrderService();
$service->createOrder(['item' => 'Notebook']);

print_r($service->getAuditLog()); // ✅ public
```

### 📝 Exercícios do Capítulo 45

1. Crie classe com todos os níveis de visibilidade e teste cada um
2. Implemente value object `Money` com `readonly` class
3. Use asymmetric visibility para propriedade `score` (leitura pública, escrita privada)
4. Controle acesso a constantes sensíveis em hierarquia de configuração
5. Crie trait `AuditableTrait` com métodos privados, protegidos e públicos

---

## 46. Regular Expressions Completo

Expressões regulares (regex) são padrões para busca, validação e transformação de texto. PHP usa PCRE (Perl Compatible Regular Expressions) via funções `preg_*`. Dominá-las permite validar CPFs, extrair emails, mascarar dados e muito mais.

### 46.1 Sintaxe básica

Um padrão regex é delimitado por `/` e suporta modificadores (`i` = case-insensitive, `m` = multiline). Metacaracteres como `.`, `^`, `$`, `*`, `+` e `?` controlam o matching:
```php
<?php

declare(strict_types=1);

// Metacaracteres fundamentais:
// .  → Qualquer caractere (exceto \n)    ^  → Início da string
// $  → Fim da string                     *  → 0 ou mais repetições
// +  → 1 ou mais repetições              ?  → 0 ou 1 (opcional)
// [] → Classe de caracteres              () → Grupo de captura
// |  → OU lógico                         \  → Escape

// Exemplos básicos
$text = 'PHP 8.5 é incrível!';

var_dump(preg_match('/php/i', $text));      // 1 (i = case-insensitive)
var_dump(preg_match('/^PHP/', $text));       // 1 (começa com PHP)
var_dump(preg_match('/!$/', $text));         // 1 (termina com !)
var_dump(preg_match('/PHP.*8/', $text));     // 1 (PHP + qualquer coisa + 8)
var_dump(preg_match('/Python/', $text));     // 0 (não encontrado)
```

### 46.2 Classes de caracteres

Classes de caracteres `[...]` definem conjuntos permitidos. Classes predefinidas como `\d`, `\w` e `\s` são atalhos para padrões comuns. O `^` dentro de `[]` nega a classe:
```php
<?php

declare(strict_types=1);

// Classes predefinidas:
// \d → Dígito [0-9]          \D → Não dígito [^0-9]
// \w → Word [a-zA-Z0-9_]     \W → Não word
// \s → Whitespace [ \t\n\r]  \S → Não whitespace

// Apenas dígitos
var_dump(preg_match('/^\d+$/', '12345'));   // 1 ✅
var_dump(preg_match('/^\d+$/', '123a5'));   // 0 ❌

// Alfanumérico
var_dump(preg_match('/^\w+$/', 'user_123')); // 1 ✅

// Classe customizada: apenas letras
var_dump(preg_match('/^[a-zA-Z]+$/', 'abc'));    // 1 ✅
var_dump(preg_match('/^[a-zA-Z]+$/', 'abc123')); // 0 ❌

// Negação com ^ dentro de []
var_dump(preg_match('/^[^0-9]+$/', 'abc'));  // 1 ✅ (nenhum dígito)
var_dump(preg_match('/^[^0-9]+$/', 'abc1')); // 0 ❌
```

### 46.3 Quantificadores

Quantificadores controlam **quantas vezes** um padrão pode repetir: `{n}` exatamente n vezes, `{n,m}` entre n e m. São essenciais para validar formatos brasileiros (CEP, CPF, CNPJ, telefone):
```php
<?php

declare(strict_types=1);

// {n}   → Exatamente n vezes
// {n,}  → n ou mais vezes
// {n,m} → Entre n e m vezes

// CEP brasileiro: 12345-678
$cepPattern = '/^\d{5}-\d{3}$/';
var_dump(preg_match($cepPattern, '01310-100')); // 1 ✅

// CPF: 123.456.789-00
$cpfPattern = '/^\d{3}\.\d{3}\.\d{3}-\d{2}$/';
var_dump(preg_match($cpfPattern, '123.456.789-00')); // 1 ✅

// Telefone BR: (11) 98765-4321 ou (11) 3456-7890
$phonePattern = '/^\(\d{2}\) \d{4,5}-\d{4}$/';
var_dump(preg_match($phonePattern, '(11) 98765-4321')); // 1 ✅
var_dump(preg_match($phonePattern, '(11) 3456-7890'));   // 1 ✅

// CNPJ: 12.345.678/0001-90
$cnpjPattern = '/^\d{2}\.\d{3}\.\d{3}\/\d{4}-\d{2}$/';
var_dump(preg_match($cnpjPattern, '12.345.678/0001-90')); // 1 ✅
```

### 46.4 Grupos e capturas

Grupos `()` capturam partes do match para uso posterior. Grupos nomeados `(?<nome>...)` tornam o código mais legível. Grupos não-capturantes `(?:...)` agrupam sem capturar:
```php
<?php

declare(strict_types=1);

// ── Grupos de captura () ──
$text = 'João Silva tem 25 anos';
$pattern = '/(\w+) (\w+) tem (\d+) anos/';

preg_match($pattern, $text, $matches);
// $matches[0] = 'João Silva tem 25 anos' (match completo)
// $matches[1] = 'João'                   (grupo 1)
// $matches[2] = 'Silva'                  (grupo 2)
// $matches[3] = '25'                     (grupo 3)

// ── Grupos NOMEADOS (?<name>...) — muito mais legível ──
$pattern = '/(?<firstName>\w+) (?<lastName>\w+) tem (?<age>\d+) anos/';

preg_match($pattern, $text, $matches);
echo $matches['firstName'] . PHP_EOL; // João
echo $matches['lastName'] . PHP_EOL;  // Silva
echo $matches['age'] . PHP_EOL;       // 25

// ── Grupos NÃO-capturantes (?:...) — agrupam sem capturar ──
$pattern = '/(?:Sr\.|Sra\.) (?<name>\w+)/';

preg_match($pattern, 'Sr. Silva', $matches);
echo $matches['name'] . PHP_EOL; // Silva
// Não há $matches[1] para o prefixo — não foi capturado
```

### 46.5 Validações práticas

Esta classe `InputValidator` consolida as validações mais comuns em projetos brasileiros: email, CPF, CNPJ, telefone, senha forte, cartão de crédito, data e placa Mercosul:
```php
<?php

declare(strict_types=1);

class InputValidator
{
    public static function isEmail(string $email): bool
    {
        $pattern = '/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/';

        return preg_match($pattern, $email) === 1;
    }

    public static function isUrl(string $url): bool
    {
        $pattern = '/^https?:\/\/(www\.)?[a-zA-Z0-9-]+(\.[a-zA-Z]{2,})+/';

        return preg_match($pattern, $url) === 1;
    }

    public static function isCpf(string $cpf): bool
    {
        return preg_match('/^\d{3}\.\d{3}\.\d{3}-\d{2}$/', $cpf) === 1;
    }

    public static function isCnpj(string $cnpj): bool
    {
        return preg_match('/^\d{2}\.\d{3}\.\d{3}\/\d{4}-\d{2}$/', $cnpj) === 1;
    }

    public static function isPhone(string $phone): bool
    {
        return preg_match('/^\(\d{2}\) \d{4,5}-\d{4}$/', $phone) === 1;
    }

    public static function isStrongPassword(string $password): bool
    {
        // Mínimo 8 chars + maiúscula + minúscula + número + especial
        if (strlen($password) < 8) {
            return false;
        }

        $hasUppercase = preg_match('/[A-Z]/', $password) === 1;
        $hasLowercase = preg_match('/[a-z]/', $password) === 1;
        $hasDigit     = preg_match('/[0-9]/', $password) === 1;
        $hasSpecial   = preg_match('/[^A-Za-z0-9]/', $password) === 1;

        return $hasUppercase && $hasLowercase && $hasDigit && $hasSpecial;
    }

    public static function isCreditCard(string $number): bool
    {
        // Remove espaços e hífens, verifica 13-19 dígitos
        $cleaned = preg_replace('/[\s-]/', '', $number);

        return preg_match('/^\d{13,19}$/', $cleaned) === 1;
    }

    public static function isBrazilianDate(string $date): bool
    {
        // dd/mm/yyyy
        return preg_match(
            '/^(0[1-9]|[12]\d|3[01])\/(0[1-9]|1[0-2])\/\d{4}$/',
            $date,
        ) === 1;
    }

    public static function isLicensePlate(string $plate): bool
    {
        // Mercosul: ABC1D23 ou ABC-1D23
        return preg_match(
            '/^[A-Z]{3}-?\d[A-Z]\d{2}$/',
            strtoupper($plate),
        ) === 1;
    }
}

// Testes
echo InputValidator::isEmail('joao@example.com') ? '✅' : '❌';     // ✅
echo InputValidator::isCpf('123.456.789-00') ? '✅' : '❌';         // ✅
echo InputValidator::isPhone('(11) 98765-4321') ? '✅' : '❌';      // ✅
echo InputValidator::isStrongPassword('Senha@123') ? '✅' : '❌';   // ✅
echo InputValidator::isCnpj('12.345.678/0001-90') ? '✅' : '❌';   // ✅
echo InputValidator::isLicensePlate('ABC1D23') ? '✅' : '❌';       // ✅
```

### 46.6 Funções de Regex avançadas

Além de `preg_match`, PHP oferece `preg_match_all` (todas ocorrências), `preg_replace` (substituir), `preg_replace_callback` (substituir com lógica), `preg_split` (dividir) e `preg_grep` (filtrar arrays):
```php
<?php

declare(strict_types=1);

// ── preg_match_all: encontrar TODAS as ocorrências ──
$text = 'Suportamos PHP 8.5, PHP 8.4 e PHP 8.3';
preg_match_all('/PHP \d\.\d/', $text, $matches);
print_r($matches[0]);
// ['PHP 8.5', 'PHP 8.4', 'PHP 8.3']

// ── preg_replace: substituir com regex ──
$text = 'João Silva, Maria Santos, Pedro Lima';
$anonymized = preg_replace('/(\w+) (\w+)/', '$1 ***', $text);
echo $anonymized . PHP_EOL;
// João ***, Maria ***, Pedro ***

// ── preg_replace_callback: substituir com lógica customizada ──
$text = 'Preços: 100, 200, 300';
$doubled = preg_replace_callback(
    '/\d+/',
    fn(array $match): string => (string) ((int) $match[0] * 2),
    $text,
);
echo $doubled . PHP_EOL; // Preços: 200, 400, 600

// ── preg_split: dividir com regex ──
$text = 'maçã;banana,laranja|uva';
$fruits = preg_split('/[;,|]/', $text);
print_r($fruits);
// ['maçã', 'banana', 'laranja', 'uva']

// ── preg_grep: filtrar array com regex ──
$languages = ['PHP', 'JavaScript', 'Python', 'Ruby', 'Perl'];
$startsWithP = preg_grep('/^P/', $languages);
print_r($startsWithP);
// [0 => 'PHP', 2 => 'Python', 4 => 'Perl']

// ── Extrair todos os emails de um texto ──
$text = 'Contato: joao@ex.com ou maria@empresa.org. Suporte: help@site.com';
preg_match_all('/[\w.+-]+@[\w-]+\.[\w.]+/', $text, $emails);
print_r($emails[0]);
// ['joao@ex.com', 'maria@empresa.org', 'help@site.com']
```

### 46.7 Lookahead e Lookbehind

Lookahead (`(?=...)`) e lookbehind (`(?<=...)`) verificam contexto **sem consumir** caracteres. Negativos (`(?!...)`, `(?<!...)`) verificam ausência. Ideais para mascarar dados e extrair valores condicionais:
```php
<?php

declare(strict_types=1);

// Lookahead e Lookbehind: verificam contexto SEM capturar

// ── Positive Lookahead (?=...) → seguido por ──
// Encontrar "PHP" apenas se seguido de versão
$pattern = '/PHP(?= \d)/';
var_dump(preg_match($pattern, 'PHP 8.5'));    // 1 ✅
var_dump(preg_match($pattern, 'PHP rocks'));  // 0 ❌

// ── Negative Lookahead (?!...) → NÃO seguido por ──
// Dígitos que NÃO são seguidos de ponto
$pattern = '/\d+(?!\.)/';
preg_match($pattern, '3.14', $m);
echo $m[0] . PHP_EOL; // 14 (o 3 é seguido de ponto, então não matcha)

// ── Positive Lookbehind (?<=...) → precedido por ──
// Extrair valor após "R$"
$pattern = '/(?<=R\$ )\d+[.,]\d{2}/';
preg_match($pattern, 'Preço: R$ 99,90', $m);
echo $m[0] . PHP_EOL; // 99,90

// ── Negative Lookbehind (?<!...) → NÃO precedido por ──
// Números que NÃO são precedidos de "-" (positivos)
$pattern = '/(?<!-)\b\d+\b/';
preg_match_all($pattern, 'Valores: 50, -30, 100, -10', $m);
print_r($m[0]); // ['50', '30', '100', '10']
// ⚠️ Nota: o \b (word boundary) ajuda a delimitar números inteiros

// ── Exemplo prático: mascarar cartão de crédito ──
function maskCreditCard(string $number): string
{
    $cleaned = preg_replace('/[\s-]/', '', $number);

    return preg_replace(
        '/^(\d{4})\d+(\d{4})$/',
        '$1 **** **** $2',
        $cleaned,
    );
}

echo maskCreditCard('4111 1111 1111 1111') . PHP_EOL;
// 4111 **** **** 1111

// ── Exemplo prático: extrair hashtags ──
function extractHashtags(string $text): array
{
    preg_match_all('/#(\w+)/', $text, $matches);

    return $matches[1];
}

$hashtags = extractHashtags('Aprendendo #PHP #programação com #PHP85');
print_r($hashtags); // ['PHP', 'programação', 'PHP85']
```

### 📝 Exercícios do Capítulo 46

1. Valide CNPJ com regex (formato + dígitos verificadores)
2. Extraia todos os emails de um texto longo e remova duplicatas
3. Crie validador de senha com requisitos configuráveis (min/max, classes de chars)
4. Mascare parcialmente números de cartão, CPF e telefone (`****1234`)
5. Faça parser simples de Markdown: `**bold**` → `<strong>bold</strong>`, `*italic*` → `<em>italic</em>`

---

## 47. Validação de Forms — E-mail e URL

Validação de email e URL é essencial em qualquer formulário. PHP oferece `filter_var()` com filtros built-in, mas validação completa exige verificação de DNS, limites RFC e sanitização adequada.

### 47.1 Validação de e-mail com filter_var

`filter_var($email, FILTER_VALIDATE_EMAIL)` valida o formato básico. Para produção, combine com normalização (trim + lowercase), limites RFC 5321 (máx 254 chars, parte local máx 64) e verificação DNS:
```php
<?php

declare(strict_types=1);

class EmailValidator
{
    // Validação simples com filter_var (built-in do PHP)
    public static function isValid(string $email): bool
    {
        return filter_var($email, FILTER_VALIDATE_EMAIL) !== false;
    }

    // Validar + normalizar (trim, lowercase)
    public static function validateAndNormalize(string $email): ?string
    {
        $email = trim($email);
        $email = strtolower($email);

        if (filter_var($email, FILTER_VALIDATE_EMAIL) === false) {
            return null;
        }

        return $email;
    }

    // Sanitizar: remove caracteres ilegais
    public static function sanitize(string $email): string
    {
        return filter_var($email, FILTER_SANITIZE_EMAIL);
    }

    // Validação COMPLETA: formato + comprimento + DNS
    public static function validateFull(string $email): array
    {
        $result = [
            'valid' => false,
            'email' => null,
            'errors' => [],
        ];

        $email = trim($email);

        if ($email === '') {
            $result['errors'][] = 'Email não pode estar vazio.';
            return $result;
        }

        $cleanedEmail = self::sanitize($email);

        if (!self::isValid($cleanedEmail)) {
            $result['errors'][] = 'Formato de email inválido.';
            return $result;
        }

        // RFC 5321: máximo 254 caracteres no total
        if (strlen($cleanedEmail) > 254) {
            $result['errors'][] = 'Email muito longo (máx 254 caracteres).';
            return $result;
        }

        [$localPart, $domain] = explode('@', $cleanedEmail);

        // RFC 5321: parte local máx 64 caracteres
        if (strlen($localPart) > 64) {
            $result['errors'][] = 'Parte local muito longa (máx 64 caracteres).';
            return $result;
        }

        // Verificar se o domínio existe (registro MX ou A)
        if (!self::validateDns($domain)) {
            $result['errors'][] = 'Domínio não encontrado no DNS.';
            return $result;
        }

        $result['valid'] = true;
        $result['email'] = strtolower($cleanedEmail);

        return $result;
    }

    // Verificar registro DNS do domínio
    private static function validateDns(string $domain): bool
    {
        return checkdnsrr($domain, 'MX') || checkdnsrr($domain, 'A');
    }
}

// Testes
$emails = [
    'joao@example.com',          // ✅ Válido
    'JOAO@EXAMPLE.COM',          // ✅ Normalizado para minúsculas
    'joao.silva@empresa.com.br', // ✅ Subdomínio válido
    'joao+newsletter@ex.com',    // ✅ Tag válida
    'invalid@',                  // ❌ Sem domínio
    '@example.com',              // ❌ Sem parte local
    'not-an-email',              // ❌ Formato inválido
];

foreach ($emails as $email) {
    $result = EmailValidator::validateFull($email);

    if ($result['valid']) {
        echo "✅ {$email} → {$result['email']}" . PHP_EOL;
    } else {
        echo "❌ {$email} → " . implode(', ', $result['errors']) . PHP_EOL;
    }
}
```

### 47.2 Validação de e-mail com Regex

Regex permite validação customizada e funcionalidades extras como extração de domínio e mascaramento parcial. Use uma regex básica para validação geral ou a RFC 5322 simplificada para conformidade estrita:
```php
<?php

declare(strict_types=1);

class EmailRegexValidator
{
    // Regex básica para email
    private const string PATTERN_BASIC =
        '/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/';

    // RFC 5322 simplificada
    private const string PATTERN_RFC =
        '/^[a-zA-Z0-9!#$%&\'*+\/=?^_`{|}~-]+(?:\.[a-zA-Z0-9!#$%&\'*+\/=?^_`{|}~-]+)*'
        . '@(?:[a-zA-Z0-9](?:[a-zA-Z0-9-]*[a-zA-Z0-9])?\.)+[a-zA-Z0-9](?:[a-zA-Z0-9-]*[a-zA-Z0-9])?$/';

    public static function isValidBasic(string $email): bool
    {
        return preg_match(self::PATTERN_BASIC, $email) === 1;
    }

    public static function isValidRfc(string $email): bool
    {
        return preg_match(self::PATTERN_RFC, $email) === 1;
    }

    public static function extractDomain(string $email): ?string
    {
        if (!self::isValidBasic($email)) {
            return null;
        }

        return explode('@', $email)[1];
    }

    public static function extractLocalPart(string $email): ?string
    {
        if (!self::isValidBasic($email)) {
            return null;
        }

        return explode('@', $email)[0];
    }

    // Mascarar email: joao.silva@ex.com → joa*******@ex.com
    public static function mask(string $email): string
    {
        if (!self::isValidBasic($email)) {
            return '***';
        }

        [$localPart, $domain] = explode('@', $email);

        $localLength = strlen($localPart);
        $showCount = (int) ceil($localLength / 3);

        $masked = substr($localPart, 0, $showCount)
                . str_repeat('*', $localLength - $showCount)
                . '@'
                . $domain;

        return $masked;
    }
}

// Testes
echo EmailRegexValidator::mask('joao.silva@example.com') . PHP_EOL;
// joa*******@example.com

echo EmailRegexValidator::extractDomain('joao@example.com') . PHP_EOL;
// example.com
```

### 47.3 Validação de URL

`filter_var($url, FILTER_VALIDATE_URL)` valida o formato básico. Validação completa inclui verificar o scheme (http/https), decompor com `parse_url()`, normalizar, e opcionalmente testar acessibilidade:
```php
<?php

declare(strict_types=1);

class UrlValidator
{
    // Validação básica com filter_var
    public static function isValid(string $url): bool
    {
        return filter_var($url, FILTER_VALIDATE_URL) !== false;
    }

    // Sanitizar URL
    public static function sanitize(string $url): string
    {
        return filter_var($url, FILTER_SANITIZE_URL);
    }

    // Validar apenas HTTP/HTTPS
    public static function isValidHttp(string $url): bool
    {
        if (!self::isValid($url)) {
            return false;
        }

        $scheme = parse_url($url, PHP_URL_SCHEME);

        return in_array($scheme, ['http', 'https'], strict: true);
    }

    // Validação completa com decomposição
    public static function validateFull(string $url): array
    {
        $result = [
            'valid' => false,
            'url' => null,
            'components' => [],
            'errors' => [],
        ];

        $url = trim($url);

        if ($url === '') {
            $result['errors'][] = 'URL não pode estar vazia.';
            return $result;
        }

        if (!self::isValid($url)) {
            $result['errors'][] = 'Formato de URL inválido.';
            return $result;
        }

        $components = parse_url($url);

        if ($components === false) {
            $result['errors'][] = 'URL malformada.';
            return $result;
        }

        if (!isset($components['scheme'])) {
            $result['errors'][] = 'Esquema (http/https) é obrigatório.';
            return $result;
        }

        if (!in_array($components['scheme'], ['http', 'https'], strict: true)) {
            $result['errors'][] = 'Apenas http e https são permitidos.';
            return $result;
        }

        if (!isset($components['host'])) {
            $result['errors'][] = 'Host é obrigatório.';
            return $result;
        }

        if (strlen($url) > 2048) {
            $result['errors'][] = 'URL muito longa (máx 2048 caracteres).';
            return $result;
        }

        $result['valid'] = true;
        $result['url'] = $url;
        $result['components'] = $components;

        return $result;
    }

    // Normalizar URL (adicionar scheme, lowercase host)
    public static function normalize(string $url): ?string
    {
        $url = trim($url);

        // Adicionar http:// se não tiver scheme
        if (!preg_match('/^https?:\/\//i', $url)) {
            $url = 'http://' . $url;
        }

        if (!self::isValid($url)) {
            return null;
        }

        $components = parse_url($url);

        $scheme   = strtolower($components['scheme']);
        $host     = strtolower($components['host']);
        $path     = $components['path'] ?? '/';
        $query    = isset($components['query']) ? '?' . $components['query'] : '';
        $fragment = isset($components['fragment']) ? '#' . $components['fragment'] : '';

        return "{$scheme}://{$host}{$path}{$query}{$fragment}";
    }

    // Extrair domínio
    public static function extractDomain(string $url): ?string
    {
        if (!self::isValid($url)) {
            return null;
        }

        return parse_url($url, PHP_URL_HOST);
    }

    // Verificar se URL responde (HEAD request leve)
    public static function isAccessible(string $url): bool
    {
        if (!self::isValidHttp($url)) {
            return false;
        }

        $headers = @get_headers($url);

        if ($headers === false) {
            return false;
        }

        // Status 2xx ou 3xx = acessível
        return preg_match('/HTTP\/[\d.]+\s+[23]\d\d/', $headers[0]) === 1;
    }
}

// Testes
$urls = [
    'https://example.com',        // ✅
    'http://example.com/path',    // ✅
    'example.com',                // ❌ Sem scheme
    'ftp://example.com',          // ❌ Scheme não HTTP
    'not-a-url',                  // ❌
];

foreach ($urls as $url) {
    $result = UrlValidator::validateFull($url);

    if ($result['valid']) {
        echo "✅ {$url} → Host: {$result['components']['host']}" . PHP_EOL;
    } else {
        echo "❌ {$url} → " . implode(', ', $result['errors']) . PHP_EOL;
    }
}

// Normalização
echo UrlValidator::normalize('example.com') . PHP_EOL;
// http://example.com/

echo UrlValidator::normalize('HTTPS://EXAMPLE.COM/Path') . PHP_EOL;
// https://example.com/Path
```

### 47.4 Formulário completo de contato

Este exemplo integra `EmailValidator` e `UrlValidator` num formulário de contato real, com validação de todos os campos, sanitização de saída e tratamento de erros:
```php
<?php

declare(strict_types=1);

class ContactFormValidator
{
    private array $errors = [];

    public function validate(array $data): bool
    {
        $this->errors = [];

        // ── Nome (obrigatório, 3-100 chars) ──
        if (empty($data['name'])) {
            $this->errors['name'] = 'Nome é obrigatório.';
        } elseif (strlen($data['name']) < 3) {
            $this->errors['name'] = 'Nome deve ter pelo menos 3 caracteres.';
        } elseif (strlen($data['name']) > 100) {
            $this->errors['name'] = 'Nome muito longo (máx 100 caracteres).';
        }

        // ── Email (obrigatório, validação completa) ──
        if (empty($data['email'])) {
            $this->errors['email'] = 'Email é obrigatório.';
        } else {
            $emailResult = EmailValidator::validateFull($data['email']);

            if (!$emailResult['valid']) {
                $this->errors['email'] = implode(', ', $emailResult['errors']);
            }
        }

        // ── Telefone (opcional, formato BR) ──
        if (!empty($data['phone'])) {
            $phonePattern = '/^\(\d{2}\) \d{4,5}-\d{4}$/';

            if (preg_match($phonePattern, $data['phone']) !== 1) {
                $this->errors['phone'] = 'Formato inválido. Use (11) 98765-4321.';
            }
        }

        // ── Website (opcional, deve ser HTTP/HTTPS) ──
        if (!empty($data['website'])) {
            if (!UrlValidator::isValidHttp($data['website'])) {
                $this->errors['website'] = 'URL inválida.';
            }
        }

        // ── Assunto (obrigatório, mín 5 chars) ──
        if (empty($data['subject'])) {
            $this->errors['subject'] = 'Assunto é obrigatório.';
        } elseif (strlen($data['subject']) < 5) {
            $this->errors['subject'] = 'Assunto muito curto (mín 5 caracteres).';
        }

        // ── Mensagem (obrigatória, 20-1000 chars) ──
        if (empty($data['message'])) {
            $this->errors['message'] = 'Mensagem é obrigatória.';
        } elseif (strlen($data['message']) < 20) {
            $this->errors['message'] = 'Mensagem muito curta (mín 20 caracteres).';
        } elseif (strlen($data['message']) > 1000) {
            $this->errors['message'] = 'Mensagem muito longa (máx 1000 caracteres).';
        }

        return $this->errors === [];
    }

    public function getErrors(): array
    {
        return $this->errors;
    }
}

// ── Processar formulário ──
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $validator = new ContactFormValidator();

    if ($validator->validate($_POST)) {
        // Sanitizar antes de usar
        $safeData = [
            'name'    => htmlspecialchars($_POST['name'], ENT_QUOTES, 'UTF-8'),
            'email'   => filter_var($_POST['email'], FILTER_SANITIZE_EMAIL),
            'phone'   => $_POST['phone'] ?? '',
            'website' => filter_var($_POST['website'] ?? '', FILTER_SANITIZE_URL),
            'subject' => htmlspecialchars($_POST['subject'], ENT_QUOTES, 'UTF-8'),
            'message' => htmlspecialchars($_POST['message'], ENT_QUOTES, 'UTF-8'),
        ];

        echo 'Formulário válido! ' . json_encode($safeData, JSON_PRETTY_PRINT);
    } else {
        echo "Erros de validação:" . PHP_EOL;
        print_r($validator->getErrors());
    }
}
```

### 📝 Exercícios do Capítulo 47

1. Implemente validação de CNPJ com verificação de dígitos verificadores
2. Crie validador de domínio de email com whitelist/blacklist configurável
3. Faça `UrlValidator::extractQueryParams()` que retorna array de parâmetros
4. Valide URLs permitindo apenas domínios específicos (ex.: apenas `.gov.br`)
5. Crie formulário de cadastro completo com validação de CPF, data de nascimento e CEP

---

## 48. cURL — Requisições HTTP

cURL é a biblioteca do PHP para fazer requisições HTTP programáticas — consumir APIs REST, baixar arquivos, enviar dados e autenticar. Combinado com `json_decode`, é a base para integração entre sistemas.

### 48.1 GET Request básico

O GET é o verbo HTTP mais simples: busca dados sem alterar estado. `curl_init()` inicializa o handle, `CURLOPT_RETURNTRANSFER` retorna o corpo como string, e `curl_getinfo()` obtém metadados:
```php
<?php

declare(strict_types=1);

class HttpClient
{
    // GET simples — retorna o corpo ou false
    public static function get(string $url): string|false
    {
        $ch = curl_init();

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);

        $response = curl_exec($ch);
        curl_close($ch);

        return $response;
    }

    // GET com informações detalhadas de resposta
    public static function getDetailed(string $url): array
    {
        $ch = curl_init();

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
        curl_setopt($ch, CURLOPT_TIMEOUT, 30);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        $error    = curl_error($ch);

        curl_close($ch);

        return [
            'success'   => $response !== false && $httpCode < 400,
            'http_code' => $httpCode,
            'body'      => $response,
            'error'     => $error,
        ];
    }
}

// Uso simples
$response = HttpClient::get('https://api.example.com/users');

if ($response !== false) {
    $data = json_decode($response, associative: true);
    print_r($data);
}

// Uso detalhado com checagem de erro
$result = HttpClient::getDetailed('https://api.example.com/users');

if ($result['success']) {
    $data = json_decode($result['body'], associative: true);
    echo "Recebidos " . count($data) . " usuários." . PHP_EOL;
} else {
    echo "Erro HTTP {$result['http_code']}: {$result['error']}" . PHP_EOL;
}
```

### 48.2 POST Request com JSON

POST envia dados ao servidor para criar recursos. O corpo pode ser JSON (`application/json`) ou form-data (`application/x-www-form-urlencoded`). Defina `CURLOPT_POST` e `CURLOPT_POSTFIELDS`:
```php
<?php

declare(strict_types=1);

class HttpClient
{
    // POST com corpo JSON
    public static function postJson(string $url, array $data): array
    {
        $ch = curl_init();
        $jsonBody = json_encode($data);

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_POST, true);
        curl_setopt($ch, CURLOPT_POSTFIELDS, $jsonBody);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_HTTPHEADER, [
            'Content-Type: application/json',
            'Content-Length: ' . strlen($jsonBody),
        ]);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        curl_close($ch);

        return [
            'http_code' => $httpCode,
            'body'      => json_decode($response, associative: true),
        ];
    }

    // POST com form-data (application/x-www-form-urlencoded)
    public static function postForm(string $url, array $data): array
    {
        $ch = curl_init();

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_POST, true);
        curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($data));
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        curl_close($ch);

        return [
            'http_code' => $httpCode,
            'body'      => $response,
        ];
    }
}

// POST JSON → criar recurso
$result = HttpClient::postJson('https://api.example.com/users', [
    'name'  => 'João Silva',
    'email' => 'joao@example.com',
    'age'   => 25,
]);

if ($result['http_code'] === 201) {
    echo "Usuário criado!" . PHP_EOL;
    print_r($result['body']);
}

// POST Form → login
$result = HttpClient::postForm('https://api.example.com/login', [
    'username' => 'joao',
    'password' => 'secret123',
]);
```

### 48.3 Headers e autenticação

Headers customizados (`CURLOPT_HTTPHEADER`) permitem enviar tokens de autenticação, Accept types e API keys. Bearer Token (OAuth/JWT) e Basic Auth são os esquemas mais comuns:
```php
<?php

declare(strict_types=1);

class HttpClient
{
    // GET com headers customizados
    public static function getWithHeaders(string $url, array $headers): array
    {
        $ch = curl_init();

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        curl_close($ch);

        return [
            'http_code' => $httpCode,
            'body'      => $response,
        ];
    }

    // GET com Bearer Token (OAuth 2.0, JWT)
    public static function getWithBearerToken(string $url, string $token): array
    {
        return self::getWithHeaders($url, [
            "Authorization: Bearer {$token}",
            'Accept: application/json',
        ]);
    }

    // GET com Basic Auth (usuário:senha em base64)
    public static function getWithBasicAuth(
        string $url,
        string $username,
        string $password,
    ): array {
        $ch = curl_init();

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_USERPWD, "{$username}:{$password}");

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        curl_close($ch);

        return [
            'http_code' => $httpCode,
            'body'      => $response,
        ];
    }
}

// Bearer Token
$token = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...';
$result = HttpClient::getWithBearerToken(
    'https://api.example.com/me',
    $token,
);

// Basic Auth
$result = HttpClient::getWithBasicAuth(
    'https://api.example.com/admin',
    'admin',
    'superSecretPass',
);
```

### 48.4 Upload de arquivos

`CURLFile` encapsula arquivos para upload via `multipart/form-data`. Suporta arquivo único ou múltiplo, com detecção automática de MIME type:
```php
<?php

declare(strict_types=1);

class HttpClient
{
    // Upload de arquivo único
    public static function uploadFile(string $url, string $filePath): array
    {
        if (!file_exists($filePath)) {
            throw new InvalidArgumentException("Arquivo não encontrado: {$filePath}");
        }

        $ch = curl_init();

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_POST, true);
        curl_setopt($ch, CURLOPT_POSTFIELDS, [
            'file' => new CURLFile($filePath),
        ]);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        curl_close($ch);

        return [
            'http_code' => $httpCode,
            'body'      => $response,
        ];
    }

    // Upload de múltiplos arquivos
    public static function uploadMultiple(string $url, array $files): array
    {
        $ch = curl_init();

        $postData = [];
        foreach ($files as $fieldName => $path) {
            if (file_exists($path)) {
                $postData[$fieldName] = new CURLFile($path);
            }
        }

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_POST, true);
        curl_setopt($ch, CURLOPT_POSTFIELDS, $postData);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        curl_close($ch);

        return [
            'http_code' => $httpCode,
            'body'      => $response,
        ];
    }
}

// Upload único
$result = HttpClient::uploadFile(
    'https://api.example.com/upload',
    '/path/to/photo.jpg',
);

// Upload múltiplo
$result = HttpClient::uploadMultiple(
    'https://api.example.com/upload',
    [
        'photo1'   => '/path/to/photo1.jpg',
        'photo2'   => '/path/to/photo2.jpg',
        'document' => '/path/to/report.pdf',
    ],
);
```

### 48.5 Download de arquivos

Para downloads, use `CURLOPT_FILE` para streaming direto ao disco (eficiente para arquivos grandes) ou `CURLOPT_RETURNTRANSFER` para obter o conteúdo em memória (arquivos pequenos):
```php
<?php

declare(strict_types=1);

class HttpClient
{
    // Download para string (arquivos pequenos)
    public static function download(string $url): string|false
    {
        $ch = curl_init();

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);

        $content = curl_exec($ch);
        curl_close($ch);

        return $content;
    }

    // Download direto para arquivo (streaming — eficiente para arquivos grandes)
    public static function downloadToFile(string $url, string $destination): bool
    {
        $ch = curl_init();
        $fp = fopen($destination, 'wb');

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_FILE, $fp);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);

        $success = curl_exec($ch);

        curl_close($ch);
        fclose($fp);

        return $success !== false && file_exists($destination);
    }

    // Download com barra de progresso (CLI)
    public static function downloadWithProgress(string $url, string $destination): bool
    {
        $ch = curl_init();
        $fp = fopen($destination, 'wb');

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_FILE, $fp);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
        curl_setopt($ch, CURLOPT_NOPROGRESS, false);
        curl_setopt($ch, CURLOPT_PROGRESSFUNCTION, function (
            $resource,
            int $totalSize,
            int $downloaded,
            int $uploadTotal,
            int $uploaded,
        ): void {
            if ($totalSize > 0) {
                $percent = ($downloaded / $totalSize) * 100;
                echo "\rDownload: " . number_format($percent, 1) . '%';
            }
        });

        $success = curl_exec($ch);

        curl_close($ch);
        fclose($fp);

        echo PHP_EOL; // Quebra linha após o progresso

        return $success !== false && file_exists($destination);
    }
}

// Download para variável
$content = HttpClient::download('https://example.com/data.json');

if ($content !== false) {
    file_put_contents('local_data.json', $content);
}

// Download direto para arquivo (eficiente)
HttpClient::downloadToFile(
    'https://example.com/image.jpg',
    'local_image.jpg',
);

// Download com progresso no terminal
HttpClient::downloadWithProgress(
    'https://example.com/large_file.zip',
    'large_file.zip',
);
```

### 48.6 Cliente HTTP completo (classe reutilizável)

Esta classe encapsula todos os verbos HTTP (GET, POST, PUT, DELETE) com fluent interface, base URL configurável, headers customizados e timeout. O padrão para clientes HTTP em projetos reais:
```php
<?php

declare(strict_types=1);

// Cliente HTTP reutilizável com fluent interface
class FullHttpClient
{
    private array $headers = [];
    private int $timeout = 30;

    public function __construct(
        private readonly ?string $baseUrl = null,
    ) {}

    public function setHeader(string $name, string $value): self
    {
        $this->headers[] = "{$name}: {$value}";

        return $this;
    }

    public function setTimeout(int $seconds): self
    {
        $this->timeout = $seconds;

        return $this;
    }

    // ── Verbos HTTP ──

    public function get(string $endpoint, array $params = []): array
    {
        $url = $this->buildUrl($endpoint, $params);
        $ch  = $this->initCurl($url);

        return $this->execute($ch);
    }

    public function post(string $endpoint, array $data): array
    {
        $url = $this->buildUrl($endpoint);
        $ch  = $this->initCurl($url);

        curl_setopt($ch, CURLOPT_POST, true);
        curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));

        return $this->execute($ch);
    }

    public function put(string $endpoint, array $data): array
    {
        $url = $this->buildUrl($endpoint);
        $ch  = $this->initCurl($url);

        curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'PUT');
        curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));

        return $this->execute($ch);
    }

    public function delete(string $endpoint): array
    {
        $url = $this->buildUrl($endpoint);
        $ch  = $this->initCurl($url);

        curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'DELETE');

        return $this->execute($ch);
    }

    // ── Métodos internos ──

    private function buildUrl(string $endpoint, array $params = []): string
    {
        $url = $this->baseUrl !== null
            ? rtrim($this->baseUrl, '/') . '/' . ltrim($endpoint, '/')
            : $endpoint;

        if ($params !== []) {
            $url .= '?' . http_build_query($params);
        }

        return $url;
    }

    private function initCurl(string $url): \CurlHandle
    {
        $ch = curl_init();

        curl_setopt($ch, CURLOPT_URL, $url);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
        curl_setopt($ch, CURLOPT_TIMEOUT, $this->timeout);
        curl_setopt($ch, CURLOPT_HTTPHEADER, $this->headers);

        return $ch;
    }

    private function execute(\CurlHandle $ch): array
    {
        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        $error    = curl_error($ch);

        curl_close($ch);

        return [
            'success'   => $response !== false && $httpCode < 400,
            'http_code' => $httpCode,
            'body'      => json_decode($response, associative: true) ?? $response,
            'error'     => $error,
        ];
    }
}

// ── Uso: CRUD completo com fluent interface ──
$client = new FullHttpClient(baseUrl: 'https://api.example.com');

$client
    ->setHeader('Authorization', 'Bearer TOKEN_HERE')
    ->setHeader('Accept', 'application/json')
    ->setHeader('Content-Type', 'application/json')
    ->setTimeout(60);

// GET com query params
$result = $client->get('/users', ['page' => 1, 'limit' => 10]);

if ($result['success']) {
    print_r($result['body']);
}

// POST — criar
$result = $client->post('/users', [
    'name'  => 'João Silva',
    'email' => 'joao@example.com',
]);

// PUT — atualizar
$result = $client->put('/users/1', [
    'name' => 'João Silva Atualizado',
]);

// DELETE — remover
$result = $client->delete('/users/1');

if ($result['success']) {
    echo 'Usuário removido com sucesso!' . PHP_EOL;
}
```

### 48.7 cURL Share Handles Persistentes (PHP 8.5)

Diferente de `curl_share_init()`, handles criados com `curl_share_init_persistent()` **não são destruídos ao final da requisição PHP**. Se um handle persistente com o mesmo conjunto de opções for encontrado, ele será reutilizado — evitando o custo de inicializar o cURL a cada requisição.

```php
<?php

declare(strict_types=1);

// ══════════════════════════════════════
// Antes do PHP 8.5 — curl_share_init()
// ══════════════════════════════════════

// O share handle é criado e destruído a cada requisição PHP
$sh = curl_share_init();
curl_share_setopt($sh, CURLSHOPT_SHARE, CURL_LOCK_DATA_DNS);
curl_share_setopt($sh, CURLSHOPT_SHARE, CURL_LOCK_DATA_CONNECT);

$ch = curl_init('https://php.net/');
curl_setopt($ch, CURLOPT_SHARE, $sh);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_exec($ch);

curl_close($ch);
curl_share_close($sh); // Destruído — próxima requisição recomeça do zero

// ══════════════════════════════════════
// PHP 8.5 — curl_share_init_persistent()
// ══════════════════════════════════════

// O share handle PERSISTE entre requisições ao mesmo SAPI!
// DNS e conexões são reutilizados automaticamente
$sh = curl_share_init_persistent([
    CURL_LOCK_DATA_DNS,
    CURL_LOCK_DATA_CONNECT,
]);

$ch = curl_init('https://php.net/');
curl_setopt($ch, CURLOPT_SHARE, $sh);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

// Pode reutilizar a conexão de uma requisição anterior!
curl_exec($ch);
curl_close($ch);

// ⚠️ NÃO chame curl_share_close() em handles persistentes!
// O PHP gerencia o ciclo de vida automaticamente.

// ══════════════════════════════════════
// Opções disponíveis para compartilhamento
// ══════════════════════════════════════

// CURL_LOCK_DATA_DNS      → Cache de resolução DNS entre requests
// CURL_LOCK_DATA_CONNECT  → Reutilização de conexões TCP/TLS
// CURL_LOCK_DATA_COOKIE   → Compartilhamento de cookies
// CURL_LOCK_DATA_SSL_SESSION → Reutilização de sessões SSL/TLS

// Exemplo com todas as opções
$sh = curl_share_init_persistent([
    CURL_LOCK_DATA_DNS,
    CURL_LOCK_DATA_CONNECT,
    CURL_LOCK_DATA_SSL_SESSION,
]);

// ══════════════════════════════════════
// Classe helper com persistent share
// ══════════════════════════════════════

class PersistentCurlClient
{
    private \CurlShareHandle $shareHandle;

    public function __construct()
    {
        // Inicializar handle persistente — reutilizado entre requests SAPI
        $this->shareHandle = curl_share_init_persistent([
            CURL_LOCK_DATA_DNS,
            CURL_LOCK_DATA_CONNECT,
            CURL_LOCK_DATA_SSL_SESSION,
        ]);
    }

    public function get(string $url, array $headers = []): string|false
    {
        $ch = curl_init($url);

        curl_setopt_array($ch, [
            CURLOPT_SHARE          => $this->shareHandle,
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_FOLLOWLOCATION => true,
            CURLOPT_HTTPHEADER     => $headers,
            CURLOPT_TIMEOUT        => 30,
        ]);

        $response = curl_exec($ch);
        curl_close($ch);

        return $response;
    }

    public function getMultiple(array $urls): array
    {
        $results = [];

        foreach ($urls as $url) {
            $results[$url] = $this->get($url);
        }

        return $results;
    }
}

// Uso — conexões DNS/TCP persistem entre chamadas
$client   = new PersistentCurlClient();
$response = $client->get('https://api.example.com/data');

// Chamadas subsequentes reutilizam DNS e conexões!
$pages = $client->getMultiple([
    'https://api.example.com/users',
    'https://api.example.com/products',
    'https://api.example.com/orders',
]);
```

### 📝 Exercícios do Capítulo 48

1. Crie cliente HTTP completo para consumir API REST com paginação automática
2. Implemente cache local de requisições (salvar resposta em arquivo com TTL)
3. Adicione sistema de retry com backoff exponencial para falhas 5xx
4. Faça web scraper simples com cURL que respeita `robots.txt`
5. Implemente cliente para API GraphQL usando `FullHttpClient`
6. Use `curl_share_init_persistent()` para benchmark de performance vs `curl_share_init()`

---

## Conclusão dos Tópicos Avançados

Parabéns! 🎉 Você dominou todos os tópicos avançados de PHP 8.5 Moderno!

### O que você aprendeu nesta seção:

| Parte   | Capítulos | Temas                                                                 |
| ------- | --------- | --------------------------------------------------------------------- |
| **VI**  | 24-28     | Iterables, Namespaces, Static, Traits, Interfaces                     |
| **VII** | 29-34     | Abstract Classes, Constants, Access Modifiers, Regex, Validação, cURL |

### Resumo das habilidades adquiridas:

✅ **Iterables:** Generators, Iterator, IteratorAggregate
✅ **Namespaces:** PSR-4, autoloading, aliases
✅ **Static:** Late static binding, Singleton, Factory
✅ **Traits:** Composição, conflitos, abstract methods
✅ **Interfaces:** ISP, fluent interface, Strategy
✅ **Abstract Classes:** Template Method, hierarquias
✅ **Constants:** Tipadas (8.3+), em enums, visibilidade
✅ **Access Modifiers:** Readonly (8.1+), Asymmetric (8.4+)
✅ **Regex:** Validações, lookahead/lookbehind, extração
✅ **Validação:** Email, URL, formulários completos
✅ **cURL:** GET, POST, auth, upload, download, cliente HTTP

---

## 49. PDO — PHP Data Objects (Completo)

PDO é a interface unificada do PHP para acessar **qualquer** banco de dados relacional. Suporta prepared statements (proteção contra SQL Injection), transações ACID, múltiplos fetch modes e 12+ drivers. Este capítulo cobre cada método em detalhes.

### Índice do Capítulo

1. Introdução ao PDO
2. `PDO::__construct` — Conexão
3. `PDO::connect` — Conexão alternativa (PHP 8.4+)
4. `getAttribute` e `setAttribute`
5. `getAvailableDrivers`
6. `PDO::prepare` — Prepared Statements
7. `PDO::query` — Queries diretas
8. `PDO::exec` — Execução direta
9. `PDO::quote` — Escapar strings
10. `PDO::lastInsertId`
11. `errorCode` e `errorInfo`
12. Transações (`beginTransaction`, `commit`, `rollBack`)
13. `PDO::inTransaction`
14. Projeto prático completo

---

### 49.1 Introdução ao PDO

PDO (PHP Data Objects) é a extensão padrão do PHP para acesso a **qualquer** banco de dados relacional através de uma interface unificada e orientada a objetos.

```php
<?php

declare(strict_types=1);

/**
 * Por que usar PDO?
 *
 * ✅ Funciona com 12+ bancos (MySQL, PostgreSQL, SQLite, Oracle, SQL Server…)
 * ✅ Prepared Statements nativos → proteção contra SQL Injection
 * ✅ Orientado a objetos (sem funções procedurais como mysqli_*)
 * ✅ Tratamento de erros robusto com exceções (PDOException)
 * ✅ Transações ACID (beginTransaction, commit, rollBack)
 * ✅ Melhor performance com prepared statements reutilizáveis
 * ✅ Suporte a múltiplos fetch modes (ASSOC, OBJ, CLASS, etc.)
 *
 * Bancos suportados:
 * ┌────────────────────┬─────────────────────────────────────┐
 * │ Driver             │ DSN Prefix                           │
 * ├────────────────────┼─────────────────────────────────────┤
 * │ MySQL / MariaDB    │ mysql:                               │
 * │ PostgreSQL         │ pgsql:                               │
 * │ SQLite             │ sqlite:                              │
 * │ Oracle             │ oci:                                 │
 * │ SQL Server         │ sqlsrv:                              │
 * │ Firebird           │ firebird:                            │
 * │ ODBC               │ odbc:                                │
 * │ IBM DB2            │ ibm:                                 │
 * └────────────────────┴─────────────────────────────────────┘
 */
```

---

### 49.2 PDO::__construct — Conexão

O construtor cria uma conexão com o banco de dados.

```php
<?php

declare(strict_types=1);

/**
 * Sintaxe:
 * new PDO(string $dsn, ?string $username = null, ?string $password = null, ?array $options = null)
 *
 * DSN (Data Source Name) = string de conexão específica do driver.
 * Formato: "driver:param1=valor1;param2=valor2"
 */

// ── MySQL ──
try {
    $pdo = new PDO(
        dsn:      'mysql:host=localhost;dbname=my_database;charset=utf8mb4',
        username: 'root',
        password: 'secret',
    );

    echo 'Conectado ao MySQL com sucesso!' . PHP_EOL;
} catch (PDOException $e) {
    die('Erro na conexão: ' . $e->getMessage());
}

// ── PostgreSQL ──
$pdo = new PDO(
    'pgsql:host=localhost;port=5432;dbname=my_database',
    'postgres',
    'secret',
);

// ── SQLite (arquivo local) ──
$pdo = new PDO('sqlite:/path/to/database.db');

// ── SQLite (em memória — ótimo para testes) ──
$pdo = new PDO('sqlite::memory:');

// ── Com opções recomendadas (SEMPRE configure!) ──
$options = [
    // Lançar exceções em vez de warnings silenciosos
    PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,

    // Arrays associativos por padrão (sem índices numéricos redundantes)
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,

    // Prepared statements nativos do driver (não emulados pelo PHP)
    PDO::ATTR_EMULATE_PREPARES   => false,

    // Sem conexão persistente (evita problemas de estado)
    PDO::ATTR_PERSISTENT         => false,
];

$pdo = new PDO(
    'mysql:host=localhost;dbname=app;charset=utf8mb4',
    'root',
    'secret',
    $options,
);
```

#### Classe de Conexão Reutilizável (Singleton)

```php
<?php

declare(strict_types=1);

/**
 * Singleton de conexão PDO.
 *
 * Garante uma única instância por request,
 * com configuração centralizada e segura.
 */
final class Database
{
    private static ?PDO $instance = null;

    // Construtor privado → impede new Database()
    private function __construct() {}

    public static function getConnection(): PDO
    {
        if (self::$instance === null) {
            // Em produção, use variáveis de ambiente ou .env
            $host     = $_ENV['DB_HOST']    ?? 'localhost';
            $port     = $_ENV['DB_PORT']    ?? '3306';
            $dbname   = $_ENV['DB_NAME']    ?? 'app';
            $username = $_ENV['DB_USER']    ?? 'root';
            $password = $_ENV['DB_PASS']    ?? '';
            $charset  = $_ENV['DB_CHARSET'] ?? 'utf8mb4';

            $dsn = "mysql:host={$host};port={$port};dbname={$dbname};charset={$charset}";

            $options = [
                PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
                PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
                PDO::ATTR_EMULATE_PREPARES   => false,
                PDO::ATTR_PERSISTENT         => false,
                PDO::ATTR_TIMEOUT            => 5,
            ];

            try {
                self::$instance = new PDO($dsn, $username, $password, $options);
            } catch (PDOException $e) {
                error_log('Erro de conexão PDO: ' . $e->getMessage());
                throw new RuntimeException('Não foi possível conectar ao banco de dados.');
            }
        }

        return self::$instance;
    }

    /**
     * Fechar conexão manualmente (opcional — PHP fecha no final do request).
     */
    public static function disconnect(): void
    {
        self::$instance = null;
    }
}

// Uso
$pdo = Database::getConnection();
```

---

### 49.3 PDO::connect — Conexão Alternativa (PHP 8.4+)

```php
<?php

declare(strict_types=1);

/**
 * PDO::connect() é um método estático introduzido no PHP 8.4
 * para criar subclasses PDO específicas de cada driver.
 *
 * Quando disponível, retorna uma subclasse com métodos extras
 * específicos do driver (ex.: MySqlPDO, PgsqlPDO).
 */

// MySQL — retorna Pdo\Mysql quando disponível
$mysql = PDO::connect(
    'mysql:host=localhost;dbname=test',
    'user',
    'pass',
);

// PostgreSQL — retorna Pdo\Pgsql quando disponível
$pgsql = PDO::connect(
    'pgsql:host=localhost;dbname=test',
    'user',
    'pass',
);

// SQLite — retorna Pdo\Sqlite quando disponível
$sqlite = PDO::connect('sqlite::memory:');

/**
 * Vantagem: subclasses podem oferecer métodos exclusivos
 * do driver que o PDO genérico não possui.
 *
 * Se o driver não tiver subclasse, retorna PDO padrão.
 * É seguro usar como substituto direto de new PDO().
 */
```

---

### 49.4 PDO::getAttribute e setAttribute

Recuperar e definir atributos de configuração da conexão.

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ══════════════════════════════════════════════════
// DEFINIR ATRIBUTOS (setAttribute)
// ══════════════════════════════════════════════════

// 1. Modo de erro — SEMPRE use EXCEPTION!
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
// Opções:
// - PDO::ERRMODE_SILENT    → retorna false (padrão — NÃO USE!)
// - PDO::ERRMODE_WARNING   → emite E_WARNING
// - PDO::ERRMODE_EXCEPTION → lança PDOException (✅ RECOMENDADO)

// 2. Modo de busca padrão
$pdo->setAttribute(PDO::ATTR_DEFAULT_FETCH_MODE, PDO::FETCH_ASSOC);
// Opções:
// - PDO::FETCH_ASSOC  → ['nome' => 'João']       (✅ RECOMENDADO)
// - PDO::FETCH_NUM    → [0 => 'João']
// - PDO::FETCH_BOTH   → ['nome' => 'João', 0 => 'João']
// - PDO::FETCH_OBJ    → stdClass { nome: 'João' }
// - PDO::FETCH_CLASS  → instância de classe específica

// 3. Emulação de prepared statements
$pdo->setAttribute(PDO::ATTR_EMULATE_PREPARES, false);
// false → usa prepared statements nativos do driver (✅ RECOMENDADO)
// true  → emulado pelo PHP (pode ser útil para debugging)

// 4. Case dos nomes de colunas
$pdo->setAttribute(PDO::ATTR_CASE, PDO::CASE_NATURAL);
// - PDO::CASE_NATURAL → mantém original do banco
// - PDO::CASE_LOWER   → tudo minúsculo
// - PDO::CASE_UPPER   → tudo maiúsculo

// 5. Conversão de NULL e strings vazias
$pdo->setAttribute(PDO::ATTR_ORACLE_NULLS, PDO::NULL_NATURAL);
// - PDO::NULL_NATURAL      → mantém NULL como NULL
// - PDO::NULL_EMPTY_STRING → converte "" para NULL
// - PDO::NULL_TO_STRING    → converte NULL para ""

// 6. Autocommit (MySQL)
$pdo->setAttribute(PDO::ATTR_AUTOCOMMIT, true);

// 7. Timeout de conexão
$pdo->setAttribute(PDO::ATTR_TIMEOUT, 30);

// ══════════════════════════════════════════════════
// OBTER ATRIBUTOS (getAttribute)
// ══════════════════════════════════════════════════

// Nome do driver
$driver = $pdo->getAttribute(PDO::ATTR_DRIVER_NAME);
echo "Driver: {$driver}" . PHP_EOL;
// Saída: mysql, pgsql, sqlite, etc.

// Versão do servidor
$serverVersion = $pdo->getAttribute(PDO::ATTR_SERVER_VERSION);
echo "Servidor: {$serverVersion}" . PHP_EOL;

// Versão do cliente (biblioteca)
$clientVersion = $pdo->getAttribute(PDO::ATTR_CLIENT_VERSION);
echo "Cliente: {$clientVersion}" . PHP_EOL;

// Status da conexão
$status = $pdo->getAttribute(PDO::ATTR_CONNECTION_STATUS);
echo "Status: {$status}" . PHP_EOL;

// Info do servidor
$info = $pdo->getAttribute(PDO::ATTR_SERVER_INFO);
echo "Info: {$info}" . PHP_EOL;

// Modo de erro atual
$errorMode = $pdo->getAttribute(PDO::ATTR_ERRMODE);
echo "Modo de erro: {$errorMode}" . PHP_EOL;

// ══════════════════════════════════════════════════
// FUNÇÃO HELPER DE CONFIGURAÇÃO
// ══════════════════════════════════════════════════

/**
 * Aplica configurações recomendadas a uma conexão PDO.
 */
function configurePdo(PDO $pdo): void
{
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    $pdo->setAttribute(PDO::ATTR_DEFAULT_FETCH_MODE, PDO::FETCH_ASSOC);
    $pdo->setAttribute(PDO::ATTR_EMULATE_PREPARES, false);
    $pdo->setAttribute(PDO::ATTR_CASE, PDO::CASE_NATURAL);
    $pdo->setAttribute(PDO::ATTR_ORACLE_NULLS, PDO::NULL_NATURAL);
}
```

---

### 49.5 PDO::getAvailableDrivers

Retorna array com os drivers PDO instalados no servidor.

```php
<?php

declare(strict_types=1);

// Listar todos os drivers disponíveis
$drivers = PDO::getAvailableDrivers();

echo 'Drivers PDO instalados:' . PHP_EOL;
foreach ($drivers as $driver) {
    echo "  - {$driver}" . PHP_EOL;
}
// Saída típica:
//   - mysql
//   - sqlite
//   - pgsql

// ── Verificar se um driver específico está disponível ──
function isDriverAvailable(string $driver): bool
{
    return in_array($driver, PDO::getAvailableDrivers(), strict: true);
}

if (isDriverAvailable('mysql')) {
    echo '✅ MySQL disponível!' . PHP_EOL;
} else {
    echo '❌ MySQL não está instalado.' . PHP_EOL;
}

// ── Classe utilitária para checar pré-requisitos ──

final class PdoDriverChecker
{
    /**
     * Verifica quais drivers necessários estão faltando.
     *
     * @param list<string> $required  Drivers obrigatórios
     * @return list<string>           Drivers que faltam
     */
    public static function findMissing(array $required): array
    {
        $available = PDO::getAvailableDrivers();

        return array_values(
            array_filter(
                $required,
                fn(string $driver): bool => !in_array($driver, $available, strict: true),
            ),
        );
    }
}

// Uso
$missing = PdoDriverChecker::findMissing(['mysql', 'pgsql', 'sqlite']);

if ($missing !== []) {
    echo '⚠️  Instale os drivers: ' . implode(', ', $missing) . PHP_EOL;
} else {
    echo '✅ Todos os drivers necessários estão disponíveis.' . PHP_EOL;
}
```

---

### 49.6 PDO::prepare — Prepared Statements

Prepara uma instrução SQL para execução. **SEMPRE use para queries com dados do usuário!**

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ══════════════════════════════════════════════════
// PLACEHOLDERS NOMEADOS (:nome)
// ══════════════════════════════════════════════════

// 1. Preparar a query
$sql  = 'SELECT * FROM users WHERE email = :email AND active = :active';
$stmt = $pdo->prepare($sql);

// 2. Executar com dados (array associativo)
$stmt->execute([
    'email'  => 'joao@example.com',
    'active' => 1,
]);

// 3. Buscar resultado
$user = $stmt->fetch();
print_r($user);

// ══════════════════════════════════════════════════
// PLACEHOLDERS POSICIONAIS (?)
// ══════════════════════════════════════════════════

$sql  = 'SELECT * FROM users WHERE email = ? AND active = ?';
$stmt = $pdo->prepare($sql);

$stmt->execute(['joao@example.com', 1]);

$user = $stmt->fetch();

// ══════════════════════════════════════════════════
// bindValue — Bind de VALORES individuais
// ══════════════════════════════════════════════════

$sql  = 'INSERT INTO users (name, email, age) VALUES (:name, :email, :age)';
$stmt = $pdo->prepare($sql);

$stmt->bindValue(':name',  'João Silva');
$stmt->bindValue(':email', 'joao@example.com');
$stmt->bindValue(':age',   25, PDO::PARAM_INT); // Tipo explícito

$stmt->execute();

// ══════════════════════════════════════════════════
// bindParam — Bind de VARIÁVEIS por referência
// ══════════════════════════════════════════════════

/**
 * Diferença crucial:
 * - bindValue() copia o VALOR no momento do bind
 * - bindParam() vincula a VARIÁVEL; o valor é lido no execute()
 *
 * bindParam é ideal para executar o mesmo statement com valores diferentes.
 */

$sql  = 'INSERT INTO users (name, email) VALUES (:name, :email)';
$stmt = $pdo->prepare($sql);

$name  = '';
$email = '';

$stmt->bindParam(':name',  $name);
$stmt->bindParam(':email', $email);

// Executar múltiplas vezes com valores diferentes
$records = [
    ['João',  'joao@example.com'],
    ['Maria', 'maria@example.com'],
    ['Pedro', 'pedro@example.com'],
];

foreach ($records as [$name, $email]) {
    $stmt->execute(); // Usa o valor ATUAL de $name e $email
}

// ══════════════════════════════════════════════════
// TIPOS DE BIND (PDO::PARAM_*)
// ══════════════════════════════════════════════════

$sql  = 'SELECT * FROM products WHERE id = :id AND active = :active';
$stmt = $pdo->prepare($sql);

$stmt->bindValue(':id',     1,         PDO::PARAM_INT);   // Integer
$stmt->bindValue(':active', true,      PDO::PARAM_BOOL);  // Boolean
// $stmt->bindValue(':name', 'Produto', PDO::PARAM_STR);  // String (padrão)
// $stmt->bindValue(':col',  null,      PDO::PARAM_NULL);  // NULL
// $stmt->bindValue(':blob', $data,     PDO::PARAM_LOB);   // Large Object (BLOB)

$stmt->execute();

/**
 * Tipos disponíveis:
 * ┌───────────────────┬────────────────────────────────────────┐
 * │ Constante         │ Descrição                              │
 * ├───────────────────┼────────────────────────────────────────┤
 * │ PDO::PARAM_STR    │ String (padrão quando nada é passado) │
 * │ PDO::PARAM_INT    │ Integer                                │
 * │ PDO::PARAM_BOOL   │ Boolean                                │
 * │ PDO::PARAM_NULL   │ NULL                                   │
 * │ PDO::PARAM_LOB    │ Large Object (BLOB/CLOB)              │
 * └───────────────────┴────────────────────────────────────────┘
 */

// ══════════════════════════════════════════════════
// MODOS DE BUSCA (fetch)
// ══════════════════════════════════════════════════

$sql  = 'SELECT * FROM users WHERE active = :active';
$stmt = $pdo->prepare($sql);
$stmt->execute(['active' => 1]);

// fetch() — UM registro por vez
$user = $stmt->fetch();

// fetchAll() — TODOS os registros de uma vez
$stmt->execute(['active' => 1]); // Re-executar
$users = $stmt->fetchAll();

// fetchColumn() — Uma única coluna (primeira por padrão)
$sql   = 'SELECT COUNT(*) FROM users';
$stmt  = $pdo->prepare($sql);
$stmt->execute();
$total = $stmt->fetchColumn(); // string "42"
$total = (int) $stmt->fetchColumn(); // int 42

// fetchObject() — Como stdClass
$sql  = 'SELECT * FROM users WHERE id = :id';
$stmt = $pdo->prepare($sql);
$stmt->execute(['id' => 1]);
$user = $stmt->fetchObject();
echo $user->name . PHP_EOL;

// rowCount() — Linhas afetadas (INSERT/UPDATE/DELETE)
$sql  = 'UPDATE users SET active = 1 WHERE id = :id';
$stmt = $pdo->prepare($sql);
$stmt->execute(['id' => 1]);
echo "Linhas afetadas: {$stmt->rowCount()}" . PHP_EOL;

// ══════════════════════════════════════════════════
// PADRÃO REPOSITORY COMPLETO
// ══════════════════════════════════════════════════

final class UserRepository
{
    public function __construct(
        private readonly PDO $pdo,
    ) {}

    public function findById(int $id): ?array
    {
        $stmt = $this->pdo->prepare('SELECT * FROM users WHERE id = :id');
        $stmt->execute(['id' => $id]);

        $result = $stmt->fetch();

        return $result !== false ? $result : null;
    }

    public function findByEmail(string $email): ?array
    {
        $stmt = $this->pdo->prepare('SELECT * FROM users WHERE email = :email');
        $stmt->execute(['email' => $email]);

        $result = $stmt->fetch();

        return $result !== false ? $result : null;
    }

    /**
     * @return list<array<string, mixed>>
     */
    public function findAll(): array
    {
        $stmt = $this->pdo->prepare('SELECT * FROM users ORDER BY name ASC');
        $stmt->execute();

        return $stmt->fetchAll();
    }

    public function create(array $data): int
    {
        $stmt = $this->pdo->prepare(
            'INSERT INTO users (name, email, password_hash, created_at)
             VALUES (:name, :email, :password_hash, NOW())',
        );

        $stmt->execute([
            'name'          => $data['name'],
            'email'         => $data['email'],
            'password_hash' => password_hash($data['password'], PASSWORD_ARGON2ID),
        ]);

        return (int) $this->pdo->lastInsertId();
    }

    public function update(int $id, array $data): bool
    {
        $stmt = $this->pdo->prepare(
            'UPDATE users
             SET name = :name, email = :email, updated_at = NOW()
             WHERE id = :id',
        );

        return $stmt->execute([
            'id'    => $id,
            'name'  => $data['name'],
            'email' => $data['email'],
        ]);
    }

    public function delete(int $id): bool
    {
        $stmt = $this->pdo->prepare('DELETE FROM users WHERE id = :id');

        return $stmt->execute(['id' => $id]);
    }
}

// Uso
$pdo        = Database::getConnection();
$repository = new UserRepository($pdo);

$id   = $repository->create([
    'name'     => 'João Silva',
    'email'    => 'joao@example.com',
    'password' => 'MyS3cur3P@ss',
]);

$user = $repository->findById($id);
print_r($user);
```

---

### 49.7 PDO::query — Queries Diretas

Executa query e retorna PDOStatement. **Use apenas para queries seguras sem dados do usuário!**

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ── SELECT simples (sem dados do usuário) ──
$stmt  = $pdo->query('SELECT * FROM users');
$users = $stmt->fetchAll();

// ── Iterar diretamente sobre resultados ──
foreach ($pdo->query('SELECT * FROM products') as $product) {
    echo $product['name'] . PHP_EOL;
}

// ── Com fetch mode específico ──
$stmt = $pdo->query('SELECT * FROM users', PDO::FETCH_OBJ);
foreach ($stmt as $user) {
    echo $user->name . PHP_EOL;
}

// ── Fetch como instância de classe ──
final class User
{
    public int $id;
    public string $name;
    public string $email;
}

$stmt  = $pdo->query('SELECT id, name, email FROM users');
$stmt->setFetchMode(PDO::FETCH_CLASS, User::class);
$users = $stmt->fetchAll();

// ══════════════════════════════════════════════════
// QUANDO USAR query() vs prepare()
// ══════════════════════════════════════════════════

// ✅ USE query() para queries estáticas sem variáveis:
$pdo->query('TRUNCATE TABLE cache');
$pdo->query('OPTIMIZE TABLE users');
$count = $pdo->query('SELECT COUNT(*) FROM users')->fetchColumn();

// ❌ NUNCA use query() com dados do usuário:
// $email = $_POST['email'];
// $pdo->query("SELECT * FROM users WHERE email = '$email'"); // SQL INJECTION!

// ✅ SEMPRE use prepare() com dados do usuário:
$stmt = $pdo->prepare('SELECT * FROM users WHERE email = :email');
$stmt->execute(['email' => $_POST['email']]);
```

---

### 49.8 PDO::exec — Execução Direta

Executa statement e retorna o número de linhas afetadas. Não retorna resultados.

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ── INSERT ──
$affected = $pdo->exec("INSERT INTO logs (message, created_at) VALUES ('Sistema iniciado', NOW())");
echo "Linhas inseridas: {$affected}" . PHP_EOL; // 1

// ── UPDATE ──
$affected = $pdo->exec('UPDATE users SET active = 1 WHERE active = 0');
echo "Usuários ativados: {$affected}" . PHP_EOL;

// ── DELETE ──
$affected = $pdo->exec("DELETE FROM logs WHERE created_at < DATE_SUB(NOW(), INTERVAL 30 DAY)");
echo "Logs antigos removidos: {$affected}" . PHP_EOL;

// ── DDL (Data Definition Language) ──

// Criar tabela
$pdo->exec('CREATE TABLE IF NOT EXISTS temp_data (
    id         INT PRIMARY KEY AUTO_INCREMENT,
    value      VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
)');

// Alterar tabela
$pdo->exec('ALTER TABLE users ADD COLUMN phone VARCHAR(20) NULL');

// Remover tabela
$pdo->exec('DROP TABLE IF EXISTS temp_data');

// ══════════════════════════════════════════════════
// IMPORTANTE: exec() NÃO retorna resultados!
// ══════════════════════════════════════════════════

// ❌ Não funciona para SELECT:
// $data = $pdo->exec('SELECT * FROM users'); // Apenas retorna 0!

// ✅ Use query() ou prepare() para SELECT:
$stmt  = $pdo->query('SELECT * FROM users');
$users = $stmt->fetchAll();
```

---

### 49.9 PDO::quote — Escapar Strings

Adiciona aspas e escapa caracteres especiais. **NÃO RECOMENDADO — use `prepare()` sempre!**

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ── quote() escapa e envolve em aspas ──
$name = "O'Reilly";
$escaped = $pdo->quote($name);

echo $escaped . PHP_EOL;
// Saída: 'O\'Reilly' (com aspas e escape)

// ═══════════════════════════════════════════════════════
// ⚠️  IMPORTANTE: SEMPRE prefira prepare()
// ═══════════════════════════════════════════════════════

// ❌ Não recomendado:
$email = $pdo->quote($_POST['email'] ?? '');
$pdo->query("SELECT * FROM users WHERE email = {$email}");

// ✅ Recomendado:
$stmt = $pdo->prepare('SELECT * FROM users WHERE email = :email');
$stmt->execute(['email' => $_POST['email'] ?? '']);

// ═══════════════════════════════════════════════════════
// Quando quote() pode ser útil (último recurso)
// ═══════════════════════════════════════════════════════

/**
 * Para construir cláusulas IN() dinâmicas com inteiros,
 * quote() pode ser uma opção — mas placeholders são melhores.
 */

// Opção segura com placeholders dinâmicos:
$ids          = [1, 2, 3, 4, 5];
$placeholders = implode(',', array_fill(0, count($ids), '?'));
$stmt         = $pdo->prepare("SELECT * FROM users WHERE id IN ({$placeholders})");
$stmt->execute($ids);
```

---

### 49.10 PDO::lastInsertId

Retorna o ID da última linha inserida (auto increment).

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ── Obter ID após INSERT ──
$stmt = $pdo->prepare(
    'INSERT INTO users (name, email) VALUES (:name, :email)',
);

$stmt->execute([
    'name'  => 'João Silva',
    'email' => 'joao@example.com',
]);

$lastId = $pdo->lastInsertId();
echo "Usuário criado com ID: {$lastId}" . PHP_EOL;

// ══════════════════════════════════════════════════
// ATENÇÃO: lastInsertId() retorna STRING!
// ══════════════════════════════════════════════════

$id = $pdo->lastInsertId();
var_dump($id);       // string "123"

$id = (int) $pdo->lastInsertId();
var_dump($id);       // int 123

// ── Com sequência específica (PostgreSQL) ──
// PostgreSQL usa sequências nomeadas, não AUTO_INCREMENT
// $id = $pdo->lastInsertId('users_id_seq');

// ══════════════════════════════════════════════════
// CLASSE HELPER: INSERT + retornar ID
// ══════════════════════════════════════════════════

final class InsertHelper
{
    /**
     * Insere registro e retorna o ID gerado.
     *
     * @param array<string, mixed> $data Dados campo => valor
     */
    public static function insertAndGetId(
        PDO    $pdo,
        string $table,
        array  $data,
    ): int {
        $columns      = array_keys($data);
        $placeholders = array_map(fn(string $col): string => ":{$col}", $columns);

        $sql = sprintf(
            'INSERT INTO %s (%s) VALUES (%s)',
            $table,
            implode(', ', $columns),
            implode(', ', $placeholders),
        );

        $stmt = $pdo->prepare($sql);
        $stmt->execute($data);

        return (int) $pdo->lastInsertId();
    }
}

// Uso
$id = InsertHelper::insertAndGetId($pdo, 'users', [
    'name'  => 'Maria',
    'email' => 'maria@example.com',
]);
echo "Novo ID: {$id}" . PHP_EOL;
```

---

### 49.11 PDO::errorCode e errorInfo

Obter informações detalhadas sobre erros.

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ══════════════════════════════════════════════════
// errorCode() — Código SQLSTATE (5 caracteres)
// ══════════════════════════════════════════════════

// Após uma operação:
$pdo->exec("INSERT INTO users (name) VALUES ('João')");

$code = $pdo->errorCode();

if ($code !== '00000') {
    echo "Erro SQLSTATE: {$code}" . PHP_EOL;
} else {
    echo "Operação bem-sucedida." . PHP_EOL;
}

// ══════════════════════════════════════════════════
// errorInfo() — Informação detalhada (array)
// ══════════════════════════════════════════════════

$info = $pdo->errorInfo();
/**
 * Retorna array com 3 elementos:
 * [0] => SQLSTATE (5 caracteres, padrão ANSI)
 * [1] => Código de erro específico do driver (MySQL, PgSQL…)
 * [2] => Mensagem de erro legível
 */

// ══════════════════════════════════════════════════
// MODO EXCEPTION (✅ RECOMENDADO!)
// ══════════════════════════════════════════════════

$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

try {
    $pdo->query('SELECT * FROM nonexistent_table');
} catch (PDOException $e) {
    echo 'Erro: '   . $e->getMessage() . PHP_EOL;
    echo 'Código: ' . $e->getCode()    . PHP_EOL;

    // errorInfo() também funciona após exceção
    $info = $pdo->errorInfo();
    echo "SQLSTATE: {$info[0]}" . PHP_EOL;
    echo "Driver:   {$info[1]}" . PHP_EOL;
    echo "Mensagem: {$info[2]}" . PHP_EOL;
}

// ══════════════════════════════════════════════════
// CLASSE LOGGER DE ERROS PDO
// ══════════════════════════════════════════════════

final class PdoErrorLogger
{
    public static function log(PDO $pdo, string $context = ''): void
    {
        $info = $pdo->errorInfo();

        if ($info[0] !== '00000') {
            $message = sprintf(
                '[%s] SQLSTATE: %s | Driver: %s | Msg: %s | Context: %s',
                date('Y-m-d H:i:s'),
                $info[0],
                $info[1] ?? 'N/A',
                $info[2] ?? 'N/A',
                $context,
            );

            error_log($message);
        }
    }
}
```

---

### 49.12 Transações (beginTransaction, commit, rollBack)

Agrupar múltiplas operações em uma **unidade atômica** — tudo é confirmado ou tudo é revertido.

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ══════════════════════════════════════════════════
// TRANSAÇÃO BÁSICA
// ══════════════════════════════════════════════════

try {
    $pdo->beginTransaction();

    $pdo->exec("INSERT INTO users (name, email) VALUES ('João', 'joao@example.com')");
    $pdo->exec("INSERT INTO logs (message) VALUES ('Usuário criado')");

    // ✅ Tudo deu certo → confirmar
    $pdo->commit();

    echo 'Transação concluída!' . PHP_EOL;

} catch (Exception $e) {
    // ❌ Erro → reverter TUDO
    if ($pdo->inTransaction()) {
        $pdo->rollBack();
    }

    echo 'Erro: ' . $e->getMessage() . PHP_EOL;
}

// ══════════════════════════════════════════════════
// TRANSFERÊNCIA BANCÁRIA (exemplo clássico)
// ══════════════════════════════════════════════════

final class TransferService
{
    public function __construct(
        private readonly PDO $pdo,
    ) {}

    /**
     * Transferir valor entre contas.
     *
     * @throws RuntimeException Se saldo insuficiente ou conta não encontrada
     */
    public function transfer(int $fromAccountId, int $toAccountId, float $amount): bool
    {
        if ($amount <= 0) {
            throw new InvalidArgumentException('Valor deve ser positivo.');
        }

        try {
            $this->pdo->beginTransaction();

            // 1. Debitar da conta origem
            $stmt = $this->pdo->prepare(
                'UPDATE accounts SET balance = balance - :amount WHERE id = :id',
            );
            $stmt->execute(['amount' => $amount, 'id' => $fromAccountId]);

            // 2. Verificar se saldo ficou negativo
            $stmt = $this->pdo->prepare('SELECT balance FROM accounts WHERE id = :id');
            $stmt->execute(['id' => $fromAccountId]);
            $balance = (float) $stmt->fetchColumn();

            if ($balance < 0) {
                throw new RuntimeException('Saldo insuficiente.');
            }

            // 3. Creditar na conta destino
            $stmt = $this->pdo->prepare(
                'UPDATE accounts SET balance = balance + :amount WHERE id = :id',
            );
            $stmt->execute(['amount' => $amount, 'id' => $toAccountId]);

            // 4. Registrar a transação
            $stmt = $this->pdo->prepare(
                'INSERT INTO transfers (from_account_id, to_account_id, amount, created_at)
                 VALUES (:from_id, :to_id, :amount, NOW())',
            );
            $stmt->execute([
                'from_id' => $fromAccountId,
                'to_id'   => $toAccountId,
                'amount'  => $amount,
            ]);

            $this->pdo->commit();

            return true;

        } catch (Exception $e) {
            if ($this->pdo->inTransaction()) {
                $this->pdo->rollBack();
            }

            error_log("Erro na transferência: {$e->getMessage()}");
            throw $e;
        }
    }
}

// ══════════════════════════════════════════════════
// CRIAR PEDIDO COM ITENS E ESTOQUE
// ══════════════════════════════════════════════════

final class OrderService
{
    public function __construct(
        private readonly PDO $pdo,
    ) {}

    /**
     * Criar pedido com itens — atômico.
     *
     * @param list<array{product_id: int, quantity: int, price: float}> $items
     * @throws RuntimeException Se estoque insuficiente
     */
    public function createOrder(int $userId, array $items): int
    {
        try {
            $this->pdo->beginTransaction();

            // 1. Calcular total
            $total = array_sum(
                array_map(
                    fn(array $item): float => $item['price'] * $item['quantity'],
                    $items,
                ),
            );

            // 2. Criar pedido
            $stmt = $this->pdo->prepare(
                "INSERT INTO orders (user_id, total, status, created_at)
                 VALUES (:user_id, :total, 'pending', NOW())",
            );
            $stmt->execute(['user_id' => $userId, 'total' => $total]);

            $orderId = (int) $this->pdo->lastInsertId();

            // 3. Inserir itens + decrementar estoque
            $insertItem = $this->pdo->prepare(
                'INSERT INTO order_items (order_id, product_id, quantity, price)
                 VALUES (:order_id, :product_id, :quantity, :price)',
            );

            $updateStock = $this->pdo->prepare(
                'UPDATE products SET stock = stock - :quantity WHERE id = :id',
            );

            $checkStock = $this->pdo->prepare(
                'SELECT stock FROM products WHERE id = :id',
            );

            foreach ($items as $item) {
                // Inserir item do pedido
                $insertItem->execute([
                    'order_id'   => $orderId,
                    'product_id' => $item['product_id'],
                    'quantity'   => $item['quantity'],
                    'price'      => $item['price'],
                ]);

                // Decrementar estoque
                $updateStock->execute([
                    'quantity' => $item['quantity'],
                    'id'       => $item['product_id'],
                ]);

                // Verificar se estoque ficou negativo
                $checkStock->execute(['id' => $item['product_id']]);
                $stock = (int) $checkStock->fetchColumn();

                if ($stock < 0) {
                    throw new RuntimeException(
                        "Estoque insuficiente para produto {$item['product_id']}.",
                    );
                }
            }

            $this->pdo->commit();

            return $orderId;

        } catch (Exception $e) {
            if ($this->pdo->inTransaction()) {
                $this->pdo->rollBack();
            }

            throw new RuntimeException("Erro ao criar pedido: {$e->getMessage()}", previous: $e);
        }
    }
}

// ══════════════════════════════════════════════════
// SAVEPOINTS (pontos de salvamento intermediários)
// ══════════════════════════════════════════════════

try {
    $pdo->beginTransaction();

    // Operação 1 — esta sempre será mantida
    $pdo->exec("INSERT INTO users (name) VALUES ('João')");

    // Criar savepoint
    $pdo->exec('SAVEPOINT sp1');

    // Operação 2 — esta será cancelada
    $pdo->exec("INSERT INTO logs (message) VALUES ('Log temporário')");

    // Reverter APENAS até o savepoint (remove operação 2, mantém 1)
    $pdo->exec('ROLLBACK TO SAVEPOINT sp1');

    // Operação 3 — esta substitui a operação 2 cancelada
    $pdo->exec("INSERT INTO logs (message) VALUES ('Log definitivo')");

    // Confirmar tudo (operações 1 e 3)
    $pdo->commit();

} catch (Exception $e) {
    if ($pdo->inTransaction()) {
        $pdo->rollBack();
    }
}
```

---

### 49.13 PDO::inTransaction

Verifica se há uma transação ativa.

```php
<?php

declare(strict_types=1);

$pdo = Database::getConnection();

// ── Verificação simples ──
var_dump($pdo->inTransaction()); // false

$pdo->beginTransaction();
var_dump($pdo->inTransaction()); // true

$pdo->commit();
var_dump($pdo->inTransaction()); // false

// ══════════════════════════════════════════════════
// HELPER: Executar operação dentro de transação
// ══════════════════════════════════════════════════

/**
 * Executa callable dentro de transação com auto commit/rollback.
 *
 * @template T
 * @param callable(): T $operation
 * @return T
 */
function withTransaction(PDO $pdo, callable $operation): mixed
{
    try {
        $pdo->beginTransaction();

        $result = $operation();

        $pdo->commit();

        return $result;

    } catch (Exception $e) {
        if ($pdo->inTransaction()) {
            $pdo->rollBack();
        }

        throw $e;
    }
}

// Uso — simples e limpo
$userId = withTransaction($pdo, function () use ($pdo): string {
    $pdo->exec("INSERT INTO users (name) VALUES ('João')");
    $pdo->exec("INSERT INTO logs (message) VALUES ('Usuário criado')");

    return $pdo->lastInsertId();
});

echo "Novo ID: {$userId}" . PHP_EOL;

// ══════════════════════════════════════════════════
// TRANSACTION MANAGER — Transações Aninhadas
// ══════════════════════════════════════════════════

/**
 * Gerencia transações com suporte a aninhamento via SAVEPOINTs.
 *
 * Funcionamento:
 * - Nível 0 → beginTransaction()
 * - Nível 1+ → SAVEPOINT level_N
 */
final class TransactionManager
{
    private int $level = 0;

    public function __construct(
        private readonly PDO $pdo,
    ) {}

    public function begin(): void
    {
        if ($this->level === 0) {
            $this->pdo->beginTransaction();
        } else {
            $this->pdo->exec("SAVEPOINT level_{$this->level}");
        }

        $this->level++;
    }

    public function commit(): void
    {
        $this->level--;

        if ($this->level === 0) {
            $this->pdo->commit();
        } else {
            $this->pdo->exec("RELEASE SAVEPOINT level_{$this->level}");
        }
    }

    public function rollback(): void
    {
        $this->level--;

        if ($this->level === 0) {
            if ($this->pdo->inTransaction()) {
                $this->pdo->rollBack();
            }
        } else {
            $this->pdo->exec("ROLLBACK TO SAVEPOINT level_{$this->level}");
        }
    }

    public function inTransaction(): bool
    {
        return $this->level > 0;
    }
}

// Uso — transações aninhadas
$tm = new TransactionManager($pdo);

$tm->begin();                 // BEGIN TRANSACTION
    // operação A
    $tm->begin();             // SAVEPOINT level_1
        // operação B
    $tm->commit();            // RELEASE SAVEPOINT level_1
$tm->commit();                // COMMIT
```

---

### 49.14 Projeto Prático Completo

Sistema completo de gerenciamento de usuários com PDO — usando Entity + Repository + Service.

```php
<?php

declare(strict_types=1);

// ══════════════════════════════════════════════════
// 1. DATABASE (Singleton de conexão)
// ══════════════════════════════════════════════════

final class Database
{
    private static ?PDO $instance = null;

    private function __construct() {}

    public static function getConnection(): PDO
    {
        if (self::$instance === null) {
            $host     = $_ENV['DB_HOST']    ?? 'localhost';
            $port     = $_ENV['DB_PORT']    ?? '3306';
            $dbname   = $_ENV['DB_NAME']    ?? 'sistema';
            $username = $_ENV['DB_USER']    ?? 'root';
            $password = $_ENV['DB_PASS']    ?? '';
            $charset  = $_ENV['DB_CHARSET'] ?? 'utf8mb4';

            $dsn = "mysql:host={$host};port={$port};dbname={$dbname};charset={$charset}";

            $options = [
                PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
                PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
                PDO::ATTR_EMULATE_PREPARES   => false,
            ];

            self::$instance = new PDO($dsn, $username, $password, $options);
        }

        return self::$instance;
    }
}

// ══════════════════════════════════════════════════
// 2. ENTITY
// ══════════════════════════════════════════════════

final class User
{
    public function __construct(
        public ?int     $id        = null,
        public string   $name      = '',
        public string   $email     = '',
        public bool     $active    = true,
        public ?string  $createdAt = null,
        public ?string  $updatedAt = null,
    ) {}
}

// ══════════════════════════════════════════════════
// 3. REPOSITORY
// ══════════════════════════════════════════════════

final class UserRepository
{
    public function __construct(
        private readonly PDO $pdo,
    ) {}

    public function find(int $id): ?User
    {
        $stmt = $this->pdo->prepare('SELECT * FROM users WHERE id = :id');
        $stmt->execute(['id' => $id]);

        $data = $stmt->fetch();

        return $data !== false ? $this->hydrate($data) : null;
    }

    public function findByEmail(string $email): ?User
    {
        $stmt = $this->pdo->prepare('SELECT * FROM users WHERE email = :email');
        $stmt->execute(['email' => $email]);

        $data = $stmt->fetch();

        return $data !== false ? $this->hydrate($data) : null;
    }

    /**
     * @return list<User>
     */
    public function findAll(int $limit = 100, int $offset = 0): array
    {
        $stmt = $this->pdo->prepare(
            'SELECT * FROM users ORDER BY name ASC LIMIT :limit OFFSET :offset',
        );
        $stmt->bindValue(':limit',  $limit,  PDO::PARAM_INT);
        $stmt->bindValue(':offset', $offset, PDO::PARAM_INT);
        $stmt->execute();

        return array_map(
            fn(array $row): User => $this->hydrate($row),
            $stmt->fetchAll(),
        );
    }

    /**
     * Salvar (insert ou update, dependendo do ID).
     */
    public function save(User $user): int
    {
        if ($user->id === null) {
            return $this->insert($user);
        }

        $this->update($user);

        return $user->id;
    }

    private function insert(User $user): int
    {
        $stmt = $this->pdo->prepare(
            'INSERT INTO users (name, email, active, created_at)
             VALUES (:name, :email, :active, NOW())',
        );

        $stmt->execute([
            'name'   => $user->name,
            'email'  => $user->email,
            'active' => $user->active ? 1 : 0,
        ]);

        $user->id = (int) $this->pdo->lastInsertId();

        return $user->id;
    }

    private function update(User $user): void
    {
        $stmt = $this->pdo->prepare(
            'UPDATE users
             SET name = :name, email = :email, active = :active, updated_at = NOW()
             WHERE id = :id',
        );

        $stmt->execute([
            'id'     => $user->id,
            'name'   => $user->name,
            'email'  => $user->email,
            'active' => $user->active ? 1 : 0,
        ]);
    }

    public function delete(int $id): bool
    {
        $stmt = $this->pdo->prepare('DELETE FROM users WHERE id = :id');

        return $stmt->execute(['id' => $id]);
    }

    public function count(): int
    {
        return (int) $this->pdo->query('SELECT COUNT(*) FROM users')->fetchColumn();
    }

    /**
     * Converter array do banco para objeto User.
     */
    private function hydrate(array $data): User
    {
        return new User(
            id:        (int)  $data['id'],
            name:      $data['name'],
            email:     $data['email'],
            active:    (bool) $data['active'],
            createdAt: $data['created_at']  ?? null,
            updatedAt: $data['updated_at'] ?? null,
        );
    }
}

// ══════════════════════════════════════════════════
// 4. SERVICE (regras de negócio)
// ══════════════════════════════════════════════════

final class UserService
{
    public function __construct(
        private readonly UserRepository $repository,
    ) {}

    /**
     * Criar novo usuário com validação.
     */
    public function create(string $name, string $email, string $password): User
    {
        // Validar email
        if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
            throw new InvalidArgumentException('E-mail inválido.');
        }

        // Verificar duplicidade
        if ($this->repository->findByEmail($email) !== null) {
            throw new RuntimeException('E-mail já cadastrado.');
        }

        $user = new User(name: $name, email: $email);

        $this->repository->save($user);

        return $user;
    }

    /**
     * @param array{name?: string, email?: string, active?: bool} $data
     */
    public function update(int $id, array $data): User
    {
        $user = $this->repository->find($id)
            ?? throw new RuntimeException('Usuário não encontrado.');

        if (isset($data['name'])) {
            $user->name = $data['name'];
        }

        if (isset($data['email'])) {
            if (!filter_var($data['email'], FILTER_VALIDATE_EMAIL)) {
                throw new InvalidArgumentException('E-mail inválido.');
            }
            $user->email = $data['email'];
        }

        if (isset($data['active'])) {
            $user->active = (bool) $data['active'];
        }

        $this->repository->save($user);

        return $user;
    }

    public function delete(int $id): bool
    {
        return $this->repository->delete($id);
    }

    /**
     * Listar com paginação.
     *
     * @return array{users: list<User>, total: int, page: int, per_page: int}
     */
    public function list(int $page = 1, int $perPage = 10): array
    {
        $offset = ($page - 1) * $perPage;

        return [
            'users'    => $this->repository->findAll($perPage, $offset),
            'total'    => $this->repository->count(),
            'page'     => $page,
            'per_page' => $perPage,
        ];
    }
}

// ══════════════════════════════════════════════════
// 5. USO COMPLETO
// ══════════════════════════════════════════════════

$pdo        = Database::getConnection();
$repository = new UserRepository($pdo);
$service    = new UserService($repository);

// Criar usuário
try {
    $user = $service->create(
        name:     'João Silva',
        email:    'joao@example.com',
        password: 'MyS3cur3P@ss',
    );

    echo "✅ Usuário criado com ID: {$user->id}" . PHP_EOL;
} catch (Exception $e) {
    echo "❌ Erro: {$e->getMessage()}" . PHP_EOL;
}

// Listar usuários
$result = $service->list(page: 1, perPage: 10);

echo "Total de usuários: {$result['total']}" . PHP_EOL;
foreach ($result['users'] as $user) {
    echo "  - {$user->name} ({$user->email})" . PHP_EOL;
}

// Atualizar
$user = $service->update(1, ['name' => 'João Silva Santos']);

// Deletar
$service->delete(1);
```

---

### 📝 Exercícios do Capítulo 49

**Iniciante:**
1. Crie conexão PDO com tratamento completo de erros e exibição de atributos
2. Faça CRUD completo de **produtos** (create, read, update, delete)
3. Implemente paginação de resultados usando `LIMIT`/`OFFSET`
4. Use prepared statements para busca com múltiplos filtros (nome, categoria, preço)

**Intermediário:**
5. Crie sistema de **auditoria** (log de todas as alterações) usando transações
6. Implemente **soft delete** (coluna `deleted_at` ao invés de `DELETE`)
7. Faça relacionamento entre tabelas (usuário → pedidos → itens do pedido)
8. Crie `AbstractRepository` genérico reutilizável com métodos básicos de CRUD

**Avançado:**
9. Implemente **transferência bancária** com transações e verificação de saldo
10. Crie **query builder** orientado a objetos (`$qb->select('*')->from('users')->where(...)`)
11. Implemente cache de consultas com TTL e invalidação automática
12. Crie sistema de **migrations** simples usando PDO (up/down, versionamento)

---

### 🔒 Regras de Ouro do PDO

1. **SEMPRE** use `PDO::ERRMODE_EXCEPTION`
2. **SEMPRE** use `prepare()` para qualquer dado vindo do usuário
3. **NUNCA** concatene variáveis externas em queries SQL
4. **SEMPRE** use transações para operações múltiplas relacionadas
5. **SEMPRE** trate exceções adequadamente (`try/catch`)
6. **SEMPRE** converta tipos explicitamente (`(int)`, `(bool)`) nos resultados
7. **NUNCA** confie em dados não validados — valide **antes** de inserir

---

## 50. PHP e JSON — Guia Completo

JSON é o formato universal para troca de dados entre frontend, backend e APIs. PHP oferece `json_encode()`, `json_decode()`, `json_validate()` (8.3+), e a interface `JsonSerializable` para controle total da serialização.

### Índice do Capítulo

1. Introdução ao JSON
2. `json_encode()` — PHP para JSON
3. `json_decode()` — JSON para PHP
4. Flags e opções
5. Tratamento de erros
6. `JsonSerializable` Interface
7. JSON tipado com DTOs
8. `json_validate()` (PHP 8.3+)
9. Projeto prático: API Response Builder

---

### 50.1 Introdução ao JSON

JSON (JavaScript Object Notation) é o formato padrão para troca de dados em APIs modernas.

```php
<?php

declare(strict_types=1);

/**
 * JSON em PHP — funções principais:
 *
 * json_encode()   → converte PHP para JSON string
 * json_decode()   → converte JSON string para PHP
 * json_validate() → valida JSON sem decodificar (PHP 8.3+)
 *
 * Constantes importantes:
 * JSON_THROW_ON_ERROR   → lançar exceção em vez de retornar false/null
 * JSON_PRETTY_PRINT     → formatar com indentação
 * JSON_UNESCAPED_UNICODE → manter caracteres UTF-8 sem escapar
 */
```

---

### 50.2 json_encode() — PHP para JSON

Converte valores PHP (arrays, objetos, escalares) em uma string JSON.

```php
<?php

declare(strict_types=1);

// ══════════════════════════════════════
// Tipos básicos
// ══════════════════════════════════════

// String
echo json_encode('PHP 8.5') . PHP_EOL;
// "PHP 8.5"

// Número
echo json_encode(42) . PHP_EOL;
// 42

// Float
echo json_encode(3.14) . PHP_EOL;
// 3.14

// Boolean
echo json_encode(true) . PHP_EOL;
// true

// Null
echo json_encode(null) . PHP_EOL;
// null

// ══════════════════════════════════════
// Arrays
// ══════════════════════════════════════

// Array indexado → JSON array
$languages = ['PHP', 'JavaScript', 'Python'];
echo json_encode($languages) . PHP_EOL;
// ["PHP","JavaScript","Python"]

// Array associativo → JSON object
$user = [
    'name'  => 'João Silva',
    'email' => 'joao@example.com',
    'age'   => 25,
    'active' => true,
];
echo json_encode($user) . PHP_EOL;
// {"name":"João Silva","email":"joao@example.com","age":25,"active":true}

// Array multidimensional
$data = [
    'users' => [
        ['id' => 1, 'name' => 'João'],
        ['id' => 2, 'name' => 'Maria'],
    ],
    'total' => 2,
];
echo json_encode($data) . PHP_EOL;

// ══════════════════════════════════════
// Objetos
// ══════════════════════════════════════

// stdClass
$product = new stdClass();
$product->name  = 'Notebook';
$product->price = 4999.99;
$product->stock = 15;

echo json_encode($product) . PHP_EOL;
// {"name":"Notebook","price":4999.99,"stock":15}

// Classe customizada (propriedades públicas)
class Product
{
    public function __construct(
        public readonly string $name,
        public readonly float $price,
        public readonly int $stock,
        private readonly string $internalCode = 'PRIV', // ❌ NÃO incluído
    ) {}
}

$item = new Product('Teclado', 299.90, 50, 'KB-001');
echo json_encode($item) . PHP_EOL;
// {"name":"Teclado","price":299.9,"stock":50}
// ⚠️ Apenas propriedades PÚBLICAS são serializadas!

// ══════════════════════════════════════
// json_encode com flags
// ══════════════════════════════════════

$user = [
    'name'    => 'José da Silva',
    'city'    => 'São Paulo',
    'url'     => 'https://example.com/perfil',
    'bio'     => 'Desenvolvedor PHP & JavaScript',
];

// Sem flags — caracteres UTF-8 escapados
echo json_encode($user) . PHP_EOL;
// {"name":"Jos\u00e9 da Silva","city":"S\u00e3o Paulo",...}

// ✅ Com JSON_UNESCAPED_UNICODE — mantém UTF-8
echo json_encode($user, JSON_UNESCAPED_UNICODE) . PHP_EOL;
// {"name":"José da Silva","city":"São Paulo",...}

// ✅ Com JSON_PRETTY_PRINT — formatado para leitura
echo json_encode($user, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE) . PHP_EOL;
/*
{
    "name": "José da Silva",
    "city": "São Paulo",
    "url": "https://example.com/perfil",
    "bio": "Desenvolvedor PHP & JavaScript"
}
*/

// ✅ Com JSON_UNESCAPED_SLASHES — não escapar barras
echo json_encode($user, JSON_UNESCAPED_SLASHES | JSON_UNESCAPED_UNICODE) . PHP_EOL;
// URLs sem escapar: https://example.com/perfil (em vez de https:\/\/example.com\/perfil)

// ✅ Combinação recomendada para APIs
$apiFlags = JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES | JSON_THROW_ON_ERROR;
echo json_encode($user, $apiFlags) . PHP_EOL;
```

---

### 50.3 json_decode() — JSON para PHP

Converte uma string JSON em valores PHP.

```php
<?php

declare(strict_types=1);

$json = '{"name":"João Silva","age":25,"active":true,"scores":[95,87,92]}';

// ══════════════════════════════════════
// Decodificar como objeto (padrão)
// ══════════════════════════════════════

$data = json_decode($json);

echo $data->name . PHP_EOL;        // João Silva
echo $data->age . PHP_EOL;         // 25
var_dump($data->active);            // bool(true)
echo $data->scores[0] . PHP_EOL;   // 95

// $data é stdClass
echo get_class($data) . PHP_EOL;   // stdClass

// ══════════════════════════════════════
// Decodificar como array associativo
// ══════════════════════════════════════

$data = json_decode($json, associative: true);
// Ou: json_decode($json, true)

echo $data['name'] . PHP_EOL;        // João Silva
echo $data['age'] . PHP_EOL;         // 25
echo $data['scores'][1] . PHP_EOL;   // 87

// ══════════════════════════════════════
// Parâmetros de json_decode()
// ══════════════════════════════════════

// json_decode(
//     string $json,
//     ?bool $associative = null,  // true = array, false/null = object
//     int $depth = 512,           // profundidade máxima de aninhamento
//     int $flags = 0,             // flags de opções
// )

// ── Controle de profundidade ──
$deepJson = '{"a":{"b":{"c":{"d":"deep"}}}}';

$shallow = json_decode($deepJson, true, 2);
// null — profundidade excedida (3 níveis de aninhamento > limite 2)

$deep = json_decode($deepJson, true, 10);
echo $deep['a']['b']['c']['d'] . PHP_EOL; // deep

// ── Com JSON_THROW_ON_ERROR ──
try {
    $result = json_decode('invalid json', true, 512, JSON_THROW_ON_ERROR);
} catch (JsonException $e) {
    echo 'Erro JSON: ' . $e->getMessage() . PHP_EOL;
    // Erro JSON: Syntax error
}

// ── JSON_BIGINT_AS_STRING — inteiros grandes como string ──
$bigJson = '{"id": 9999999999999999999}';

$normal = json_decode($bigJson, true);
echo $normal['id'] . PHP_EOL;
// 1.0E+19 (precisão perdida!)

$safe = json_decode($bigJson, true, 512, JSON_BIGINT_AS_STRING);
echo $safe['id'] . PHP_EOL;
// "9999999999999999999" (string preserva valor!)

// ══════════════════════════════════════
// Tipos de dados: JSON → PHP
// ══════════════════════════════════════

$typesJson = '{
    "string": "texto",
    "integer": 42,
    "float": 3.14,
    "boolean_true": true,
    "boolean_false": false,
    "null_value": null,
    "array": [1, 2, 3],
    "object": {"key": "value"}
}';

$types = json_decode($typesJson, true);

foreach ($types as $key => $value) {
    printf("  %-15s → %-10s → %s\n", $key, gettype($value), var_export($value, true));
}
// string          → string     → 'texto'
// integer         → integer    → 42
// float           → double     → 3.14
// boolean_true    → boolean    → true
// boolean_false   → boolean    → false
// null_value      → NULL       → NULL
// array           → array      → [1, 2, 3]
// object          → array      → ['key' => 'value']
```

---

### 50.4 Tabela Completa de Flags

```php
<?php

declare(strict_types=1);

// ══════════════════════════════════════
// Flags de json_encode()
// ══════════════════════════════════════

// JSON_PRETTY_PRINT         → Indentação legível (dev/debug)
// JSON_UNESCAPED_UNICODE    → Mantém caracteres UTF-8: é, ã, ç
// JSON_UNESCAPED_SLASHES    → Não escapa / em URLs
// JSON_THROW_ON_ERROR       → Lança JsonException em vez de false
// JSON_FORCE_OBJECT         → Array indexado vira objeto: {} em vez de []
// JSON_NUMERIC_CHECK        → Strings numéricas viram números
// JSON_PRESERVE_ZERO_FRACTION → 1.0 mantém decimal (em vez de 1)
// JSON_HEX_TAG              → Escapa < e > como \u003C e \u003E
// JSON_HEX_AMP              → Escapa & como \u0026
// JSON_HEX_QUOT             → Escapa " como \u0022
// JSON_HEX_APOS             → Escapa ' como \u0027
// JSON_PARTIAL_OUTPUT_ON_ERROR → Saída parcial em erros

// ── Demonstrações práticas ──

// JSON_FORCE_OBJECT
$colors = ['red', 'green', 'blue'];
echo json_encode($colors) . PHP_EOL;
// ["red","green","blue"]

echo json_encode($colors, JSON_FORCE_OBJECT) . PHP_EOL;
// {"0":"red","1":"green","2":"blue"}

// JSON_NUMERIC_CHECK
$data = ['price' => '49.99', 'quantity' => '3'];
echo json_encode($data) . PHP_EOL;
// {"price":"49.99","quantity":"3"}

echo json_encode($data, JSON_NUMERIC_CHECK) . PHP_EOL;
// {"price":49.99,"quantity":3}

// JSON_PRESERVE_ZERO_FRACTION
echo json_encode(1.0) . PHP_EOL;
// 1 (sem flag — perde o .0)

echo json_encode(1.0, JSON_PRESERVE_ZERO_FRACTION) . PHP_EOL;
// 1.0 (mantém decimal)

// JSON_HEX_TAG — segurança em HTML
$htmlData = ['content' => '<script>alert("xss")</script>'];
echo json_encode($htmlData, JSON_HEX_TAG) . PHP_EOL;
// {"content":"\u003Cscript\u003Ealert(\"xss\")\u003C/script\u003E"}

// ══════════════════════════════════════
// Flags de json_decode()
// ══════════════════════════════════════

// JSON_THROW_ON_ERROR    → Lança JsonException
// JSON_BIGINT_AS_STRING  → Inteiros grandes como string
// JSON_OBJECT_AS_ARRAY   → Equivalente a associative: true

// ══════════════════════════════════════
// Presets de flags comuns
// ══════════════════════════════════════

// Para APIs REST
const JSON_API_FLAGS = JSON_UNESCAPED_UNICODE
                     | JSON_UNESCAPED_SLASHES
                     | JSON_THROW_ON_ERROR;

// Para debug/desenvolvimento
const JSON_DEBUG_FLAGS = JSON_PRETTY_PRINT
                       | JSON_UNESCAPED_UNICODE
                       | JSON_UNESCAPED_SLASHES;

// Para inserção segura em HTML
const JSON_HTML_SAFE_FLAGS = JSON_HEX_TAG
                           | JSON_HEX_AMP
                           | JSON_HEX_QUOT
                           | JSON_HEX_APOS
                           | JSON_THROW_ON_ERROR;
```

---

### 50.5 Tratamento de Erros

```php
<?php

declare(strict_types=1);

// ══════════════════════════════════════
// Modo LEGADO (sem exceções)
// ══════════════════════════════════════

$invalidJson = '{name: invalid}'; // Aspas obrigatórias nas chaves!

$result = json_decode($invalidJson);

if ($result === null && json_last_error() !== JSON_ERROR_NONE) {
    echo 'Erro: ' . json_last_error_msg() . PHP_EOL;
    // Erro: Syntax error

    echo 'Código: ' . json_last_error() . PHP_EOL;
    // Código: 4 (JSON_ERROR_SYNTAX)
}

// ══════════════════════════════════════
// Modo MODERNO (com exceções) ✅
// ══════════════════════════════════════

try {
    $data = json_decode($invalidJson, true, 512, JSON_THROW_ON_ERROR);
} catch (JsonException $e) {
    echo "JsonException: {$e->getMessage()}" . PHP_EOL;
    echo "Código: {$e->getCode()}" . PHP_EOL;
}

// json_encode também lança exceção
try {
    // Recurso PHP não pode ser convertido para JSON
    $resource = fopen('php://memory', 'r');
    json_encode($resource, JSON_THROW_ON_ERROR);
} catch (JsonException $e) {
    echo "Erro ao codificar: {$e->getMessage()}" . PHP_EOL;
    // Type is not supported
} finally {
    if (isset($resource) && is_resource($resource)) {
        fclose($resource);
    }
}

// ══════════════════════════════════════
// Códigos de erro JSON
// ══════════════════════════════════════

// JSON_ERROR_NONE               → Sem erro
// JSON_ERROR_DEPTH              → Profundidade máxima excedida
// JSON_ERROR_STATE_MISMATCH     → Modo ou incompatibilidade
// JSON_ERROR_CTRL_CHAR          → Caractere de controle inesperado
// JSON_ERROR_SYNTAX             → Erro de sintaxe
// JSON_ERROR_UTF8               → Caracteres UTF-8 malformados
// JSON_ERROR_RECURSION          → Referência circular encontrada
// JSON_ERROR_INF_OR_NAN         → Valor INF ou NAN no encode
// JSON_ERROR_UNSUPPORTED_TYPE   → Tipo não suportado no encode
// JSON_ERROR_NON_BACKED_ENUM    → Enum sem valor (PHP 8.1+)

// ══════════════════════════════════════
// Helper para encode/decode seguros
// ══════════════════════════════════════

class Json
{
    /**
     * Encode com exceção e flags padrão para API.
     */
    public static function encode(mixed $value, int $flags = 0): string
    {
        return json_encode(
            $value,
            $flags | JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES | JSON_THROW_ON_ERROR,
        );
    }

    /**
     * Decode com exceção, retornando array associativo.
     */
    public static function decode(string $json): array
    {
        return json_decode($json, true, 512, JSON_THROW_ON_ERROR);
    }

    /**
     * Encode formatado para debug/logs.
     */
    public static function pretty(mixed $value): string
    {
        return json_encode(
            $value,
            JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES | JSON_THROW_ON_ERROR,
        );
    }

    /**
     * Encode seguro para inserção em HTML.
     */
    public static function htmlSafe(mixed $value): string
    {
        return json_encode(
            $value,
            JSON_HEX_TAG | JSON_HEX_AMP | JSON_HEX_QUOT | JSON_HEX_APOS | JSON_THROW_ON_ERROR,
        );
    }
}

// Uso
$user = ['name' => 'José', 'city' => 'São Paulo'];

echo Json::encode($user) . PHP_EOL;
// {"name":"José","city":"São Paulo"}

echo Json::pretty($user) . PHP_EOL;
// {
//     "name": "José",
//     "city": "São Paulo"
// }

$decoded = Json::decode('{"name":"Maria","age":30}');
echo $decoded['name'] . PHP_EOL; // Maria
```

---

### 50.6 JsonSerializable Interface

Controle total sobre como um objeto é convertido para JSON.

```php
<?php

declare(strict_types=1);

// ══════════════════════════════════════
// Implementação básica
// ══════════════════════════════════════

class User implements JsonSerializable
{
    public function __construct(
        private readonly int $id,
        private readonly string $name,
        private readonly string $email,
        private readonly string $passwordHash, // ❌ Nunca expor!
        private readonly DateTimeImmutable $createdAt,
        private readonly bool $active = true,
    ) {}

    /**
     * Controla EXATAMENTE o que aparece no JSON.
     * Propriedades privadas ficam disponíveis sem expô-las.
     */
    public function jsonSerialize(): mixed
    {
        return [
            'id'         => $this->id,
            'name'       => $this->name,
            'email'      => $this->email,
            // ❌ passwordHash NUNCA é incluído
            'active'     => $this->active,
            'created_at' => $this->createdAt->format('c'), // ISO 8601
        ];
    }
}

$user = new User(
    id: 1,
    name: 'João Silva',
    email: 'joao@example.com',
    passwordHash: '$argon2id$v=19$m=65536...',
    createdAt: new DateTimeImmutable('2026-01-15 10:30:00'),
);

echo json_encode($user, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE) . PHP_EOL;
/*
{
    "id": 1,
    "name": "João Silva",
    "email": "joao@example.com",
    "active": true,
    "created_at": "2026-01-15T10:30:00+00:00"
}
*/
// ✅ passwordHash não aparece no JSON!

// ══════════════════════════════════════
// Serialização condicional e aninhada
// ══════════════════════════════════════

class Address implements JsonSerializable
{
    public function __construct(
        private readonly string $street,
        private readonly string $city,
        private readonly string $state,
        private readonly string $zipCode,
    ) {}

    public function jsonSerialize(): mixed
    {
        return [
            'street'   => $this->street,
            'city'     => $this->city,
            'state'    => $this->state,
            'zip_code' => $this->zipCode,
        ];
    }
}

class Customer implements JsonSerializable
{
    /** @param Address[] $addresses */
    public function __construct(
        private readonly int $id,
        private readonly string $name,
        private readonly array $addresses = [],
        private readonly array $tags = [],
    ) {}

    public function jsonSerialize(): mixed
    {
        return [
            'id'        => $this->id,
            'name'      => $this->name,
            'addresses' => $this->addresses, // JsonSerializable automático!
            'tags'      => $this->tags,
        ];
    }
}

$customer = new Customer(
    id: 1,
    name: 'Maria Santos',
    addresses: [
        new Address('Rua A, 100', 'São Paulo', 'SP', '01000-000'),
        new Address('Av B, 200', 'Rio de Janeiro', 'RJ', '20000-000'),
    ],
    tags: ['premium', 'verified'],
);

echo json_encode($customer, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE) . PHP_EOL;
/*
{
    "id": 1,
    "name": "Maria Santos",
    "addresses": [
        {
            "street": "Rua A, 100",
            "city": "São Paulo",
            "state": "SP",
            "zip_code": "01000-000"
        },
        {
            "street": "Av B, 200",
            "city": "Rio de Janeiro",
            "state": "RJ",
            "zip_code": "20000-000"
        }
    ],
    "tags": ["premium", "verified"]
}
*/

// ══════════════════════════════════════
// Enum serialização (PHP 8.1+)
// ══════════════════════════════════════

enum OrderStatus: string
{
    case Pending    = 'pending';
    case Processing = 'processing';
    case Shipped    = 'shipped';
    case Delivered  = 'delivered';
    case Cancelled  = 'cancelled';
}

class Order implements JsonSerializable
{
    public function __construct(
        private readonly int $id,
        private readonly OrderStatus $status,
        private readonly float $total,
    ) {}

    public function jsonSerialize(): mixed
    {
        return [
            'id'     => $this->id,
            'status' => $this->status->value, // String do enum backed
            'total'  => $this->total,
        ];
    }
}

$order = new Order(42, OrderStatus::Shipped, 199.90);
echo json_encode($order, JSON_UNESCAPED_UNICODE) . PHP_EOL;
// {"id":42,"status":"shipped","total":199.9}
```

---

### 50.7 JSON Tipado com DTOs

Decodificar JSON diretamente para classes PHP tipadas.

```php
<?php

declare(strict_types=1);

// ══════════════════════════════════════
// DTO (Data Transfer Object)
// ══════════════════════════════════════

readonly class UserDTO
{
    public function __construct(
        public int $id,
        public string $name,
        public string $email,
        public bool $active,
    ) {}

    /**
     * Factory: criar DTO a partir de JSON string.
     */
    public static function fromJson(string $json): self
    {
        $data = json_decode($json, true, 512, JSON_THROW_ON_ERROR);

        return new self(
            id:     (int) ($data['id'] ?? 0),
            name:   (string) ($data['name'] ?? ''),
            email:  (string) ($data['email'] ?? ''),
            active: (bool) ($data['active'] ?? false),
        );
    }

    /**
     * Factory: criar DTO a partir de array.
     */
    public static function fromArray(array $data): self
    {
        return new self(
            id:     (int) ($data['id'] ?? 0),
            name:   (string) ($data['name'] ?? ''),
            email:  (string) ($data['email'] ?? ''),
            active: (bool) ($data['active'] ?? false),
        );
    }

    /**
     * Criar múltiplos DTOs a partir de JSON array.
     *
     * @return self[]
     */
    public static function collectionFromJson(string $json): array
    {
        $items = json_decode($json, true, 512, JSON_THROW_ON_ERROR);

        return array_map(
            fn(array $item): self => self::fromArray($item),
            $items,
        );
    }
}

// Uso com JSON de API
$apiResponse = '{"id":1,"name":"João","email":"joao@ex.com","active":true}';
$user = UserDTO::fromJson($apiResponse);

echo "{$user->name} ({$user->email})" . PHP_EOL;
// João (joao@ex.com)

// Uso com lista JSON
$listJson = '[
    {"id":1,"name":"João","email":"joao@ex.com","active":true},
    {"id":2,"name":"Maria","email":"maria@ex.com","active":true},
    {"id":3,"name":"Pedro","email":"pedro@ex.com","active":false}
]';

$users = UserDTO::collectionFromJson($listJson);

foreach ($users as $user) {
    $status = $user->active ? '✅' : '❌';
    echo "  {$status} {$user->name}" . PHP_EOL;
}
// ✅ João
// ✅ Maria
// ❌ Pedro

// ══════════════════════════════════════
// DTO com validação
// ══════════════════════════════════════

readonly class ProductDTO
{
    public function __construct(
        public int $id,
        public string $name,
        public float $price,
        public int $stock,
    ) {
        // Validação no construtor
        if ($this->price < 0) {
            throw new InvalidArgumentException('Preço não pode ser negativo.');
        }
        if ($this->stock < 0) {
            throw new InvalidArgumentException('Estoque não pode ser negativo.');
        }
        if (trim($this->name) === '') {
            throw new InvalidArgumentException('Nome é obrigatório.');
        }
    }

    public static function fromJson(string $json): self
    {
        $data = json_decode($json, true, 512, JSON_THROW_ON_ERROR);

        return new self(
            id:    (int) ($data['id'] ?? 0),
            name:  (string) ($data['name'] ?? ''),
            price: (float) ($data['price'] ?? 0),
            stock: (int) ($data['stock'] ?? 0),
        );
    }
}

// ✅ Válido
$product = ProductDTO::fromJson('{"id":1,"name":"Teclado","price":199.90,"stock":50}');
echo "{$product->name}: R$ {$product->price}" . PHP_EOL;

// ❌ Lança InvalidArgumentException
try {
    ProductDTO::fromJson('{"id":2,"name":"","price":-10,"stock":0}');
} catch (InvalidArgumentException $e) {
    echo "Validação falhou: {$e->getMessage()}" . PHP_EOL;
}
```

---

### 50.8 json_validate() — Validação sem Decodificação (PHP 8.3+)

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.3+: validar JSON sem o custo de decodificar
// Mais eficiente quando você só precisa saber se é válido

$validJson   = '{"name": "João", "age": 25}';
$invalidJson = '{name: invalid}';
$emptyArray  = '[]';

var_dump(json_validate($validJson));    // true
var_dump(json_validate($invalidJson));  // false
var_dump(json_validate($emptyArray));   // true

// ── Com controle de profundidade ──
$deepJson = '{"a":{"b":{"c":{"d":"value"}}}}';

var_dump(json_validate($deepJson, 2));   // false (4 níveis > limite 2)
var_dump(json_validate($deepJson, 10));  // true

// ── Com flags ──
var_dump(json_validate($invalidJson, 512, JSON_INVALID_UTF8_IGNORE));

// ══════════════════════════════════════
// Uso prático: validar antes de processar
// ══════════════════════════════════════

function processApiRequest(string $body): array
{
    // Passo 1: validar rapidamente
    if (!json_validate($body)) {
        return [
            'error'   => true,
            'message' => 'JSON inválido no corpo da requisição.',
            'code'    => 400,
        ];
    }

    // Passo 2: decodificar (sabemos que é válido)
    $data = json_decode($body, true, 512, JSON_THROW_ON_ERROR);

    // Passo 3: processar
    return [
        'error' => false,
        'data'  => $data,
        'code'  => 200,
    ];
}

// Teste
$result = processApiRequest('{"action":"create","item":"produto"}');
echo "Status: {$result['code']}" . PHP_EOL; // 200

$result = processApiRequest('invalid json');
echo "Status: {$result['code']} — {$result['message']}" . PHP_EOL; // 400

// ══════════════════════════════════════
// Middleware de validação JSON
// ══════════════════════════════════════

class JsonValidationMiddleware
{
    public function handle(string $requestBody, callable $next): array
    {
        if ($requestBody === '') {
            return ['error' => 'Corpo da requisição vazio.', 'status' => 400];
        }

        if (!json_validate($requestBody)) {
            return ['error' => 'JSON malformado.', 'status' => 400];
        }

        $data = json_decode($requestBody, true, 512, JSON_THROW_ON_ERROR);

        return $next($data);
    }
}
```

---

### 50.9 Projeto Prático: API Response Builder

```php
<?php

declare(strict_types=1);

// ══════════════════════════════════════
// 1. Classe ApiResponse (Builder Pattern)
// ══════════════════════════════════════

class ApiResponse implements JsonSerializable
{
    private bool $success;
    private int $statusCode;
    private ?string $message = null;
    private mixed $data = null;
    private array $errors = [];
    private array $meta = [];

    private function __construct(bool $success, int $statusCode)
    {
        $this->success    = $success;
        $this->statusCode = $statusCode;
    }

    // ── Factory methods ──

    public static function ok(mixed $data = null, string $message = 'OK'): self
    {
        $response = new self(true, 200);
        $response->data    = $data;
        $response->message = $message;
        return $response;
    }

    public static function created(mixed $data = null): self
    {
        $response = new self(true, 201);
        $response->data    = $data;
        $response->message = 'Recurso criado com sucesso.';
        return $response;
    }

    public static function noContent(): self
    {
        return new self(true, 204);
    }

    public static function badRequest(string $message, array $errors = []): self
    {
        $response = new self(false, 400);
        $response->message = $message;
        $response->errors  = $errors;
        return $response;
    }

    public static function unauthorized(string $message = 'Não autorizado.'): self
    {
        $response = new self(false, 401);
        $response->message = $message;
        return $response;
    }

    public static function forbidden(string $message = 'Acesso negado.'): self
    {
        $response = new self(false, 403);
        $response->message = $message;
        return $response;
    }

    public static function notFound(string $message = 'Recurso não encontrado.'): self
    {
        $response = new self(false, 404);
        $response->message = $message;
        return $response;
    }

    public static function serverError(string $message = 'Erro interno do servidor.'): self
    {
        $response = new self(false, 500);
        $response->message = $message;
        return $response;
    }

    // ── Builder methods ──

    public function withMeta(array $meta): self
    {
        $this->meta = array_merge($this->meta, $meta);
        return $this;
    }

    public function withPagination(int $page, int $perPage, int $total): self
    {
        $this->meta['pagination'] = [
            'page'        => $page,
            'per_page'    => $perPage,
            'total'       => $total,
            'total_pages' => (int) ceil($total / $perPage),
        ];
        return $this;
    }

    // ── Output ──

    public function jsonSerialize(): mixed
    {
        $payload = [
            'success'     => $this->success,
            'status_code' => $this->statusCode,
        ];

        if ($this->message !== null) {
            $payload['message'] = $this->message;
        }

        if ($this->data !== null) {
            $payload['data'] = $this->data;
        }

        if ($this->errors !== []) {
            $payload['errors'] = $this->errors;
        }

        if ($this->meta !== []) {
            $payload['meta'] = $this->meta;
        }

        return $payload;
    }

    public function toJson(): string
    {
        return json_encode(
            $this,
            JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES | JSON_THROW_ON_ERROR,
        );
    }

    public function send(): never
    {
        http_response_code($this->statusCode);
        header('Content-Type: application/json; charset=utf-8');
        echo $this->toJson();
        exit;
    }

    public function getStatusCode(): int
    {
        return $this->statusCode;
    }
}

// ══════════════════════════════════════
// 2. Controller usando ApiResponse
// ══════════════════════════════════════

class UserApiController
{
    /**
     * GET /api/users
     */
    public function index(): ApiResponse
    {
        $users = [
            ['id' => 1, 'name' => 'João', 'email' => 'joao@example.com'],
            ['id' => 2, 'name' => 'Maria', 'email' => 'maria@example.com'],
            ['id' => 3, 'name' => 'Pedro', 'email' => 'pedro@example.com'],
        ];

        return ApiResponse::ok($users)
            ->withPagination(page: 1, perPage: 10, total: 3);
    }

    /**
     * GET /api/users/{id}
     */
    public function show(int $id): ApiResponse
    {
        // Simulação de busca no banco
        $user = match ($id) {
            1 => ['id' => 1, 'name' => 'João', 'email' => 'joao@example.com'],
            default => null,
        };

        if ($user === null) {
            return ApiResponse::notFound("Usuário #{$id} não encontrado.");
        }

        return ApiResponse::ok($user);
    }

    /**
     * POST /api/users
     */
    public function store(string $requestBody): ApiResponse
    {
        // Validar JSON
        if (!json_validate($requestBody)) {
            return ApiResponse::badRequest('JSON inválido.');
        }

        $data   = json_decode($requestBody, true, 512, JSON_THROW_ON_ERROR);
        $errors = [];

        // Validar campos
        if (empty($data['name'])) {
            $errors[] = ['field' => 'name', 'message' => 'Nome é obrigatório.'];
        }
        if (empty($data['email']) || !filter_var($data['email'], FILTER_VALIDATE_EMAIL)) {
            $errors[] = ['field' => 'email', 'message' => 'Email válido é obrigatório.'];
        }

        if ($errors !== []) {
            return ApiResponse::badRequest('Dados de validação inválidos.', $errors);
        }

        // Simular criação
        $newUser = [
            'id'    => random_int(100, 999),
            'name'  => $data['name'],
            'email' => $data['email'],
        ];

        return ApiResponse::created($newUser);
    }

    /**
     * DELETE /api/users/{id}
     */
    public function destroy(int $id): ApiResponse
    {
        // Simular deleção
        return ApiResponse::ok(message: "Usuário #{$id} removido com sucesso.");
    }
}

// ══════════════════════════════════════
// 3. Testes de uso
// ══════════════════════════════════════

$controller = new UserApiController();

// Listar
$response = $controller->index();
echo json_encode($response, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE) . PHP_EOL;
/*
{
    "success": true,
    "status_code": 200,
    "message": "OK",
    "data": [
        {"id": 1, "name": "João", "email": "joao@example.com"},
        {"id": 2, "name": "Maria", "email": "maria@example.com"},
        {"id": 3, "name": "Pedro", "email": "pedro@example.com"}
    ],
    "meta": {
        "pagination": {
            "page": 1,
            "per_page": 10,
            "total": 3,
            "total_pages": 1
        }
    }
}
*/

// Buscar inexistente
$response = $controller->show(999);
echo json_encode($response, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE) . PHP_EOL;
/*
{
    "success": false,
    "status_code": 404,
    "message": "Usuário #999 não encontrado."
}
*/

// Criar com validação falha
$response = $controller->store('{"name":"","email":"invalid"}');
echo json_encode($response, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE) . PHP_EOL;
/*
{
    "success": false,
    "status_code": 400,
    "message": "Dados de validação inválidos.",
    "errors": [
        {"field": "name", "message": "Nome é obrigatório."},
        {"field": "email", "message": "Email válido é obrigatório."}
    ]
}
*/

// Criar com sucesso
$response = $controller->store('{"name":"Ana Costa","email":"ana@example.com"}');
echo json_encode($response, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE) . PHP_EOL;
/*
{
    "success": true,
    "status_code": 201,
    "message": "Recurso criado com sucesso.",
    "data": {
        "id": 547,
        "name": "Ana Costa",
        "email": "ana@example.com"
    }
}
*/
```

### 📝 Exercícios do Capítulo 50

**Iniciante:**
1. Converta array de produtos para JSON e vice-versa
2. Implemente classe `Config` que lê arquivo `.json` e retorna valores tipados
3. Compare resultados de `json_decode()` com e sem `associative: true`
4. Use `json_validate()` para validar inputs do usuário antes de processar

**Intermediário:**
5. Crie DTO completo com `fromJson()`, `toJson()`, e `collectionFromJson()` para entidade `Order`
6. Implemente `ApiResponse` com suporte a cabeçalhos HTTP customizados e rate limiting
7. Crie middleware que valida, decodifica e injeta JSON em controllers
8. Implemente sistema de serialização condicional (campos diferentes por nível de acesso)

**Avançado:**
9. Crie JSON Schema validator que verifica estrutura e tipos de um JSON
10. Implemente streaming JSON encoder para datasets grandes (sem carregar tudo em memória)
11. Crie sistema de versionamento de API que serializa respostas de forma diferente por versão (v1, v2)
12. Implemente PATCH parcial com JSON Merge Patch (RFC 7396)

---

### 🔑 Regras de Ouro do JSON em PHP

1. **SEMPRE** use `JSON_THROW_ON_ERROR` — nunca ignore falhas silenciosas
2. **SEMPRE** use `JSON_UNESCAPED_UNICODE` para caracteres acentuados
3. **SEMPRE** valide JSON externo antes de decodificar (`json_validate()`)
4. **SEMPRE** implemente `JsonSerializable` em classes que serão serializadas
5. **NUNCA** exponha dados sensíveis (senhas, tokens) no JSON
6. **SEMPRE** use DTOs tipados para modelar dados de APIs externas
7. **SEMPRE** defina `Content-Type: application/json` em respostas HTTP


---

## 51. Extensão URI Nativa — PHP 8.5

O PHP 8.5 introduz uma **extensão nativa para URIs e URLs** que substitui `parse_url()` por uma API orientada a objetos, compatível com RFC 3986 e WHATWG URL. A nova extensão analisa, normaliza e manipula URIs de forma segura, eliminando erros comuns de concatenação de strings.

### 51.1 O Conceito Principal

A **nova extensão URI** no **PHP 8.5** é uma adição nativa projetada para substituir o uso de funções legadas e limitadas (como `parse_url`) por uma API robusta, orientada a objetos e compatível com os padrões modernos da web.

A extensão foi criada para resolver inconsistências históricas na manipulação de URLs no PHP. Diferente das abordagens anteriores que tratavam URLs apenas como strings ou arrays, a nova extensão oferece uma API dedicada para **analisar, normalizar e manipular** URIs e URLs de forma segura.

Ela é construída sobre duas bibliotecas robustas:

*   **uriparser:** Para conformidade com a **RFC 3986** (URIs genéricas).
*   **Lexbor:** Para conformidade com o padrão **WHATWG URL** (o padrão usado pelos navegadores modernos).

### 51.2 Principais Funcionalidades

Ao utilizar a extensão URI no PHP 8.5, você tem acesso a três capacidades principais que antes exigiam bibliotecas externas ou código complexo:

#### A. Análise (Parsing)

Em vez de receber um array simples (e muitas vezes incompleto) como o `parse_url` retornava, a nova extensão permite instanciar objetos que entendem a estrutura da URL. Isso garante que a análise seja consistente, seja para um endereço web (http) ou outros esquemas.

#### B. Normalização

Uma das grandes vantagens é a **normalização automática**. A extensão consegue limpar e padronizar URLs, resolvendo problemas como:

*   Segmentos de caminho relativos (ex: remover `../` ou `./` do meio de um caminho).
*   Codificação de caracteres inconsistente.
*   Formatação de portas e esquemas padrão.

#### C. Manipulação

Você pode alterar partes específicas de uma URL sem precisar recorrer à manipulação de strings (que é propensa a erros). A API permite modificar componentes individuais, como:

*   Alterar a *query string* (parâmetros GET) sem quebrar a codificação.
*   Mudar o *host* ou o *esquema* mantendo o restante da URL intacta.

### 51.3 Comparação: O Jeito Antigo vs. O Novo Jeito

**O Jeito Antigo (PHP < 8.5):**
Você usava `parse_url()`, recebia um array, modificava um índice desse array e depois precisava criar uma função manual para "remontar" a string da URL (já que o PHP não tinha um `unparse_url` nativo e confiável).

**O Novo Jeito (PHP 8.5):**
Você utiliza a extensão nativa para criar um objeto que representa a URI.

*   **Segurança:** A extensão valida se a URL segue os padrões RFC 3986 ou WHATWG.
*   **Confiabilidade:** Elimina erros comuns ao concatenar strings de URL manualmente.

### 51.4 Validação de Redirecionamento e Prevenção de Open Redirect

A extensão URI é crucial para prevenir ataques de *Open Redirect*, onde um atacante manipula o parâmetro `?redirect=` para enviar o usuário a um site malicioso após o login.

No PHP 8.5, a validação segue os padrões **RFC 3986** e **WHATWG URL**, garantindo que a interpretação da URL pelo servidor seja idêntica à do navegador.

#### Exemplo de Código Seguro

```php
<?php

declare(strict_types=1);

function validateRedirect(string $targetUrl): string
{
    try {
        // 1. Cria um objeto URL a partir da string recebida
        // Se a string for inválida, o construtor lançará uma exceção imediatamente.
        $uri = new \URI\URL($targetUrl);

        // 2. Define a "Allow List" de domínios permitidos
        // Isso impede que ?redirect=https://evil.com funcione
        $allowedHosts = ['meusite.com', 'app.meusite.com'];

        // 3. Verifica se o Host está na lista permitida
        if (!in_array($uri->getHost(), $allowedHosts, true)) {
            // Log de tentativa de ataque
            error_log("Redirecionamento suspeito bloqueado: " . $targetUrl);
            return '/dashboard'; // Fallback seguro
        }

        // 4. (Opcional) Força HTTPS para maior segurança
        if ($uri->getScheme() !== 'https') {
             return '/dashboard';
        }

        // 5. Retorna a URL normalizada (evita ofuscação como http://meusite.com@evil.com)
        return (string) $uri;

    } catch (\Throwable $e) {
        // Se a URL for malformada ou inválida
        return '/dashboard';
    }
}

// Uso no Controller de Login
$redirect = $_GET['redirect'] ?? '/dashboard';
$safeUrl = validateRedirect($redirect);
header("Location: $safeUrl");
exit;
```

#### Vantagens sobre o `parse_url()` antigo

*   **Normalização Automática:** A nova extensão resolve caminhos relativos complexos (ex: `/admin/../logout`) e caracteres codificados antes de você verificar, impedindo que atacantes escondam o verdadeiro destino.
*   **Padrão WHATWG:** Diferente do `parse_url()`, que apenas "quebra" a string, a nova extensão entende como os navegadores modernos processam URLs, fechando brechas onde o PHP via uma URL como segura, mas o Chrome a enviava para outro lugar.
*   **Tratamento de Erros:** Lança exceções claras em vez de retornar `false` ou `-1`, facilitando o uso em blocos `try-catch`.

### 51.5 Importância para Projetos Modernos

O domínio desta extensão é essencial para:

1.  **Segurança:** Evitar vulnerabilidades de *injection* ao construir links dinamicamente.
2.  **Interoperabilidade:** Garantir que as URLs geradas pelo seu backend PHP sejam interpretadas corretamente por navegadores modernos (graças ao suporte WHATWG).
3.  **Código Limpo:** Substitui lógicas complexas de validação de URL (Regex) por chamadas de métodos nativos.

Em resumo, para usar a extensão, você deve abandonar o uso de `parse_url` para tarefas complexas e adotar as novas classes da extensão para instanciar, modificar e validar seus endereços web.


---

## 52. Novidades do PHP 8.5 — Guia Completo

O PHP 8.5 traz atualizações significativas: **operador pipe** (`|>`), **extensão URI nativa**, **clone with**, `array_first()`/`array_last()`, `#[\NoDiscard]`, closures em expressões constantes e cURL persistente. Este capítulo resume cada novidade.

### 52.1 Operador Pipe (`|>`)

Esta é uma das mudanças sintáticas mais aguardadas. O operador pipe permite encadear chamadas de funções da esquerda para a direita. Isso elimina a necessidade de variáveis intermediárias e torna o código mais legível, evitando o aninhamento excessivo de funções (o famoso "hell de parênteses").

```php
<?php

declare(strict_types=1);

// ❌ Jeito antigo — difícil de ler (de dentro para fora)
$result = strtolower(trim(htmlspecialchars($input)));

// ✅ PHP 8.5 — leitura natural da esquerda para a direita
$result = $input
    |> trim(...)
    |> htmlspecialchars(...)
    |> strtolower(...);
```

### 52.2 Extensão URI Nativa

O PHP 8.5 introduz uma extensão nativa para análise e manipulação de URLs e URIs. Ela segue os padrões **RFC 3986** e **WHATWG URL**, baseando-se nas bibliotecas `uriparser` e `Lexbor`. Isso padroniza o tratamento de URLs que antes dependia de funções dispersas ou bibliotecas externas.

> Veja o **Capítulo 52** para detalhes completos sobre esta extensão.

### 52.3 Clone With (`clone $obj with [...]`)

Agora é possível clonar um objeto e modificar suas propriedades simultaneamente usando a sintaxe `clone ... with`. Isso facilita muito a implementação do padrão "with-er", especialmente útil para trabalhar com classes imutáveis (`readonly`), permitindo a criação de cópias modificadas sem quebrar a imutabilidade.

```php
<?php

declare(strict_types=1);

readonly class UserProfile
{
    public function __construct(
        public string $name,
        public string $email,
        public string $role = 'user',
    ) {}
}

$admin = new UserProfile(name: 'João', email: 'joao@example.com');

// ✅ PHP 8.5 — clonar e modificar em uma única expressão
$superAdmin = clone $admin with { role: 'super_admin' };

echo $superAdmin->role; // 'super_admin'
echo $superAdmin->name; // 'João' — mantém o original
```

### 52.4 Funções `array_first()` e `array_last()`

Foram adicionadas funções nativas para recuperar o primeiro e o último elemento de um array. Se o array estiver vazio, elas retornam `null`, o que facilita a integração com o operador de coalescência nula (`??`).

```php
<?php

declare(strict_types=1);

$users = ['Alice', 'Bob', 'Carlos'];

// ❌ Jeito antigo
$first = reset($users);    // Modifica o ponteiro interno!
$last  = end($users);      // Modifica o ponteiro interno!

// ✅ PHP 8.5 — sem efeitos colaterais
$first = array_first($users);  // 'Alice'
$last  = array_last($users);   // 'Carlos'

// Array vazio retorna null — perfeito com ??
$empty = [];
$fallback = array_first($empty) ?? 'Nenhum usuário';
```

### 52.5 Atributo `#[\NoDiscard]`

Você pode marcar funções com este atributo para que o PHP emita um aviso caso o valor retornado pela função seja ignorado. Isso é vital para APIs onde o retorno é crítico (como verificar se uma operação de segurança falhou).

```php
<?php

declare(strict_types=1);

class SecurityService
{
    #[\NoDiscard("O resultado da verificação de permissão DEVE ser verificado")]
    public function checkPermission(string $role): bool
    {
        // Lógica de verificação de permissão
        return $this->currentUser->role === $role;
    }
}

$security = new SecurityService();

// ❌ PHP 8.5 emitirá um WARNING — resultado ignorado!
$security->checkPermission('admin');

// ✅ Correto — resultado utilizado
if ($security->checkPermission('admin')) {
    // Acesso permitido
}
```

### 52.6 Closures em Expressões Constantes

Closures estáticas e *first-class callables* agora podem ser usadas em locais que exigem expressões constantes, como em valores padrão de parâmetros, constantes de classe e argumentos de atributos.

```php
<?php

declare(strict_types=1);

class Validator
{
    // ✅ PHP 8.5 — Closure como valor padrão de parâmetro
    public function validate(
        string $input,
        \Closure $sanitizer = trim(...),
    ): string {
        return $sanitizer($input);
    }
}
```

### 52.7 Performance e Infraestrutura

#### Handles Persistentes no cURL

A nova função `curl_share_init_persistent()` permite manter handles compartilhados entre requisições PHP distintas. Isso evita o custo de renegociar conexões (como handshakes SSL) repetidamente para o mesmo host.

#### Backtrace em Erros Fatais

Erros fatais, como exceder o tempo máximo de execução, agora exibem um *backtrace* (rastreamento de pilha), facilitando a depuração.

### 52.8 Descontinuações e Mudanças Importantes

Alguns recursos antigos foram marcados como obsoletos ou removidos, o que pode exigir ajustes em códigos legados:

| Recurso Descontinuado | Substituição Moderna | Impacto |
| --- | --- | --- |
| Operador Backtick (`` ` ``) | `shell_exec()` | Descontinuado |
| Diretiva `disable_classes` | — | Removida do INI |
| `(integer)`, `(boolean)`, `(double)`, `(binary)` | `(int)`, `(bool)`, `(float)`, `(string)` | Descontinuado |
| `__sleep()` / `__wakeup()` | `__serialize()` / `__unserialize()` | Suavemente descontinuado |
| `case X;` (com ponto e vírgula) | `case X:` (com dois pontos) | Descontinuado |
| `null` como offset de array | Verificação explícita | Descontinuado |
| Cast de `NAN` | Tratamento explícito | Emite warning |

### 52.9 Outras Melhorias

*   Suporte a visibilidade assimétrica em propriedades estáticas.
*   Capacidade de marcar propriedades promovidas no construtor como `final`.
*   `Closure::getCurrent()` para funções anônimas recursivas.
*   `#[\Override]` em propriedades e `#[\Deprecated]` em traits/constants.
*   `#[\DelayedTargetValidation]` para validação de atributos em contextos avançados.
*   `grapheme_levenshtein()` para comparação de strings baseada em grafemas Unicode.


---

## 53. Segurança em PHP 8.5 — Guia de Melhores Práticas

Este capítulo consolida as práticas essenciais de segurança para aplicações PHP modernas: SQL Injection, XSS, CSRF, validação de entrada, `#[\NoDiscard]` e conexão segura com PDO. Cada técnica é demonstrada com código pronto para produção.

### 53.1 Prevenção contra SQL Injection (A Regra de Ouro)

A falha mais crítica em CRUDs é permitir que comandos SQL maliciosos sejam injetados através dos formulários.

*   **A Prática:** Nunca concatene variáveis diretamente na string SQL.
*   **A Solução:** Use sempre **Prepared Statements** com o PDO. Isso separa a instrução SQL dos dados, neutralizando qualquer tentativa de injeção.

```php
<?php

declare(strict_types=1);

// ❌ ERRADO (Inseguro — vulnerável a SQL Injection)
$sql = "SELECT * FROM users WHERE email = '" . $_POST['email'] . "'";

// ✅ CORRETO (Seguro — Prepared Statement)
$stmt = $pdo->prepare("SELECT * FROM users WHERE email = :email");
$stmt->execute(['email' => $_POST['email']]);
```

### 53.2 Proteção contra XSS (Cross-Site Scripting)

Se um usuário mal-intencionado salvar um produto com o nome `<script>alert('Hacked')</script>`, esse script será executado no navegador de quem visualizar a lista de produtos.

*   **A Prática:** Nunca confie na saída de dados vinda do banco.
*   **A Solução:** Sempre "escape" os dados ao exibi-los no HTML usando `htmlspecialchars()`.

```php
<!-- No arquivo de template -->
<td><?= htmlspecialchars($product['name'], ENT_QUOTES, 'UTF-8') ?></td>
```

### 53.3 Proteção contra CSRF (Cross-Site Request Forgery)

O CSRF ocorre quando um site malicioso força o navegador de um usuário a realizar uma ação indesejada em uma aplicação onde ele está autenticado (ex: deletar um produto clicando em um link falso).

*   **A Solução:** Implementar tokens anti-CSRF em todos os formulários (`POST`).

**Implementação:**

1.  Gere um token na sessão ao carregar o formulário.
2.  Adicione o token como um `input hidden` no formulário.
3.  Verifique se o token enviado corresponde ao da sessão antes de processar.

```php
<?php

declare(strict_types=1);

// No início do script
session_start();
if (empty($_SESSION['csrf_token'])) {
    $_SESSION['csrf_token'] = bin2hex(random_bytes(32));
}
```

```html
<!-- No formulário HTML -->
<form method="POST" action="/process.php">
    <input type="hidden" name="csrf_token" value="<?= $_SESSION['csrf_token'] ?>">
    <!-- ... outros campos ... -->
    <button type="submit">Enviar</button>
</form>
```

```php
<?php

declare(strict_types=1);

// No processamento (create.php / edit.php)
if (!hash_equals($_SESSION['csrf_token'], $_POST['csrf_token'] ?? '')) {
    http_response_code(403);
    die("Token de segurança inválido!");
}
```

### 53.4 Validação e Sanitização de Entrada (Input Validation)

Não confie que os dados virão no formato esperado. O PHP 8.5 introduziu melhorias e depreciações importantes sobre tipos.

*   **Validação de Tipos:** Use `filter_input` e verifique os tipos estritamente.
*   **Atenção ao PHP 8.5:** Casts não canônicos como `(integer)` ou `(boolean)` foram descontinuados. Use sempre `(int)` e `(bool)`.

**Exemplo Moderno (Usando Property Hooks do PHP 8.4/8.5):**

Você pode validar os dados diretamente na classe, impedindo que o objeto fique em um estado inválido.

```php
<?php

declare(strict_types=1);

class Product
{
    public float $price {
        set(float $value) {
            if ($value < 0) {
                throw new \InvalidArgumentException("Preço não pode ser negativo");
            }
            $this->price = $value;
        }
    }
}
```

### 53.5 Uso do Atributo `#[\NoDiscard]` para Segurança (PHP 8.5)

Para operações críticas de segurança, como verificar se um usuário tem permissão para realizar uma ação, o retorno da função não pode ser ignorado. O PHP 8.5 introduziu o atributo `#[\NoDiscard]`.

```php
<?php

declare(strict_types=1);

class Auth
{
    // Se você chamar esta função e não verificar o resultado (true/false),
    // o PHP 8.5 emitirá um aviso.
    #[\NoDiscard("Verificar permissão é obrigatório!")]
    public function checkPermission(string $role): bool
    {
        return $this->currentUser->role === $role;
    }
}
```

### 53.6 Configurações de Ambiente e Erros

Em um ambiente de produção (site no ar), exibir erros detalhados do PHP expõe a estrutura do seu banco de dados e caminhos de arquivos para hackers.

*   **Desenvolvimento:** `display_errors = On`
*   **Produção:** `display_errors = Off` e `log_errors = On`

### 53.7 Conexão Segura com PDO (Database.php)

Primeiro, precisamos de uma conexão que lance exceções em caso de erro, ao invés de falhar silenciosamente. No PHP 8.5, usamos propriedades promovidas no construtor para um código mais limpo.

```php
<?php

declare(strict_types=1);

namespace App\Database;

use PDO;
use PDOException;

class Connection
{
    private ?PDO $pdo = null;

    public function __construct(
        private string $host,
        private string $dbname,
        private string $user,
        private string $pass,
    ) {}

    public function getPdo(): PDO
    {
        if ($this->pdo === null) {
            $dsn = "mysql:host={$this->host};dbname={$this->dbname};charset=utf8mb4";

            try {
                $this->pdo = new PDO($dsn, $this->user, $this->pass, [
                    // REGRA DE OURO DO PDO: Sempre use exceções para erros
                    PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
                    // Garante que os dados venham como array associativo por padrão
                    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
                    // Desabilita emulação de prepared statements (segurança real)
                    PDO::ATTR_EMULATE_PREPARES   => false,
                ]);
            } catch (PDOException $e) {
                // Logue o erro internamente, nunca mostre detalhes de conexão ao usuário
                error_log("Erro de Conexão: " . $e->getMessage());
                throw new \RuntimeException("Erro interno no servidor de banco de dados.");
            }
        }

        return $this->pdo;
    }
}
```

### 53.8 Busca Segura com Prepared Statements (UserRepository)

Aqui está a integração real. Em vez de concatenar o e-mail na string SQL (o que causaria falhas de segurança), usamos um **placeholder** (`:email`).

**O que acontece nos bastidores:**

1.  **Prepare:** O banco de dados recebe o "esqueleto" da query (`SELECT ... WHERE email = :email`) e a compila.
2.  **Bind/Execute:** O PHP envia o valor do e-mail separadamente. O banco trata esse valor estritamente como *dado*, nunca como *comando executável*.

```php
<?php

declare(strict_types=1);

namespace App\Auth;

use PDO;
use App\Database\Connection;

class UserRepository
{
    public function __construct(
        private Connection $db,
    ) {}

    /**
     * Busca um usuário pelo e-mail usando Prepared Statements.
     * Retorna o array do usuário ou null se não encontrado.
     */
    public function findUserByEmail(string $email): ?array
    {
        $pdo = $this->db->getPdo();

        // 1. PREPARE: Define a estrutura SQL com placeholder (:email)
        $sql = "SELECT id, password_hash, behavior_profile
                FROM users
                WHERE email = :email
                LIMIT 1";

        $stmt = $pdo->prepare($sql);

        // 2. EXECUTE: Envia os dados separadamente
        $stmt->execute(['email' => $email]);

        // 3. FETCH: Recupera o resultado
        $user = $stmt->fetch();

        // Se fetch retornar false (não achou), retornamos null
        return $user === false ? null : $user;
    }
}
```

### 53.9 Checklist de Segurança

1.  **Banco de Dados:** Use sempre PDO com Prepared Statements.
2.  **Output:** Use `htmlspecialchars()` ao exibir dados.
3.  **Formulários:** Use Tokens CSRF para `POST`, `PUT`, `DELETE`.
4.  **Input:** Valide tipos e formatos (email, números) antes de processar.
5.  **PHP Moderno:** Utilize `declare(strict_types=1);` e o atributo `#[\NoDiscard]` em métodos críticos.
6.  **Arquivos:** Nunca exponha arquivos sensíveis (como `.env` ou configurações de banco) na pasta pública do servidor web.


---

## 54. Autenticação 2FA com Gemini 3 Flash — Login Inteligente

Este capítulo implementa um sistema de autenticação adaptativa que usa **Gemini 3 Flash** para análise de risco em tempo real. Quando o modelo detecta comportamento anômalo (IP desconhecido, horário incomum, dispositivo novo), ativa 2FA automaticamente — sem incomodar logins legítimos.

### 54.1 Visão Geral

Integrar **Gemini 3 Flash** com autenticação de dois fatores (2FA) permite criar um sistema de login que detecta comportamentos anômalos em tempo real e ativa verificação extra automaticamente.

O fluxo lógico:

1.  **Login:** Credenciais corretas.
2.  **Análise:** Gemini 3 Flash retorna `RISCO_ALTO`.
3.  **Interrupção:** O sistema gera um código (OTP), envia ao usuário e pausa o login.
4.  **Verificação:** O usuário insere o código para "promover" a sessão parcial para uma sessão completa.

### 54.2 Por que Gemini 3 Flash para Login?

| Recurso | Regras Tradicionais (PHP Puro) | Gemini 3 Flash | Gemini 3 Pro |
| :--- | :--- | :--- | :--- |
| **Velocidade** | Instantânea | **Muito Rápida** (nível `minimal`) | Lenta (Raciocínio profundo) |
| **Custo** | Zero | **Baixíssimo** ($0.50/1M tokens) | Alto ($2.00/1M tokens) |
| **Inteligência** | Nenhuma (apenas regras) | **Alta** (Detecta padrões/anomalias) | Muito Alta (Exagero para login) |
| **Falsos Positivos** | Altos (Bloqueia usuários legítimos em viagens) | **Baixos** (Entende contexto) | Baixos |

**Vantagens do Gemini 3 Flash:**

*   **Thinking Level "Minimal":** Configuração exclusiva que minimiza a latência para aplicações de alto rendimento, permitindo análise de risco quase tão rápida quanto uma verificação de banco de dados.
*   **Custo-Eficiência:** A $0.50 por 1 milhão de tokens de entrada, você pode analisar centenas de milhares de logins por um custo irrisório.
*   **Detecção Contextual:** Diferente de firewalls com regras rígidas, o Flash usa raciocínio para entender anomalias baseadas no histórico.
*   **Visão Nativa:** Suporta entrada de imagens para verificação de identidade (KYC) ou recuperação de conta.

### 54.3 Enum de Status de Login

O enum `LoginStatus` representa os três resultados possíveis do fluxo de login: sucesso, falha ou necessidade de 2FA. Usar enum em vez de strings/booleans torna o código type-safe e auto-documentável:
```php
<?php

declare(strict_types=1);

namespace App\Auth;

enum LoginStatus
{
    case SUCCESS;
    case FAILED;
    case REQUIRE_2FA;
}
```

### 54.4 Authenticator com Detecção de Risco

```php
<?php

declare(strict_types=1);

namespace App\Auth;

use App\AI\RiskAnalyzer;
use Random\Randomizer;

class Authenticator
{
    public function __construct(
        private UserRepository $userRepo,
        private RiskAnalyzer $riskAnalyzer,
    ) {}

    #[\NoDiscard("O resultado do login DEVE ser verificado")]
    public function login(string $email, string $password, array $metaData): LoginStatus
    {
        // 1. Busca Segura com PDO
        $user = $this->userRepo->findUserByEmail($email);

        // 2. Verificação de Senha (Hash)
        // password_verify é resistente a timing attacks
        if (!$user || !password_verify($password, $user['password_hash'])) {
            // Falha genérica para não revelar se o e-mail existe ou não
            return LoginStatus::FAILED;
        }

        // 3. Análise de Risco com Gemini 3 Flash
        // Só gastamos tokens da IA se a senha estiver correta
        try {
            $analysis = $this->riskAnalyzer->analyzeLog(
                $user['behavior_profile'] ?? [],
                $metaData,
            );

            if ($analysis['risk_level'] === 'HIGH') {
                $this->initiate2FA($user, $analysis['reason']);
                return LoginStatus::REQUIRE_2FA;
            }
        } catch (\Exception $e) {
            // Fail-open: logar e permitir se a IA estiver indisponível
            error_log("Gemini indisponível: " . $e->getMessage());
        }

        // 4. Risco Baixo: Login direto
        $this->completeLogin($user);
        return LoginStatus::SUCCESS;
    }

    private function initiate2FA(array $user, string $reason): void
    {
        // Gera um código criptograficamente seguro de 6 dígitos
        $otp = (string) (new Randomizer())->getInt(100000, 999999);

        // Inicia uma sessão temporária/parcial
        if (session_status() === PHP_SESSION_NONE) {
            session_start();
        }

        // Armazena o hash do código (nunca o código puro) e expiração
        $_SESSION['2fa_pending'] = [
            'user_id'     => $user['id'],
            'hash'        => password_hash($otp, PASSWORD_DEFAULT),
            'expires'     => time() + 300, // 5 minutos
            'risk_reason' => $reason,
        ];

        // Envia o código ao usuário (e-mail/SMS)
        $this->sendAlertEmail($user['email'], $otp, $reason);
    }

    private function sendAlertEmail(string $email, string $code, string $reason): void
    {
        // Em produção, integre com serviço de e-mail real
        error_log("ENVIAR PARA $email: Código de segurança: $code. Motivo: $reason");
    }

    private function completeLogin(array $user): void
    {
        if (session_status() === PHP_SESSION_NONE) {
            session_start([
                'cookie_httponly'    => true,
                'cookie_secure'     => true,
                'cookie_samesite'   => 'Strict',
                'cookie_partitioned' => true, // PHP 8.5: Cookies particionados
            ]);
        }

        $_SESSION['user_id'] = $user['id'];
        session_regenerate_id(true); // Previne fixação de sessão
    }
}
```

### 54.5 Controlador de Verificação 2FA

Este script recebe o código digitado pelo usuário. Ele é a barreira final.

```php
<?php

declare(strict_types=1);

// verify_2fa.php

session_start();

if (!isset($_SESSION['2fa_pending'])) {
    header('Location: /login');
    exit;
}

$pending = $_SESSION['2fa_pending'];
$error = '';

// Verifica expiração
if (time() > $pending['expires']) {
    unset($_SESSION['2fa_pending']);
    die("O código expirou. Tente logar novamente.");
}

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $userCode = $_POST['code'] ?? '';

    // Verifica o código usando hash (seguro)
    if (password_verify($userCode, $pending['hash'])) {

        // SUCESSO: Promove para sessão real
        session_regenerate_id(true); // Previne Session Fixation
        $_SESSION['user_id'] = $pending['user_id'];

        // Limpa dados temporários
        unset($_SESSION['2fa_pending']);

        header('Location: /dashboard');
        exit;
    } else {
        $error = "Código incorreto.";
    }
}
?>

<!-- Frontend de verificação -->
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Verificação de Segurança</title>
</head>
<body>
    <h3>Login Suspeito Detectado</h3>
    <p>Nosso sistema de IA detectou uma anomalia:
       <strong><?= htmlspecialchars($pending['risk_reason'], ENT_QUOTES, 'UTF-8') ?></strong>
    </p>
    <p>Por favor, digite o código enviado ao seu e-mail.</p>

    <?php if ($error): ?>
        <p style="color: red;"><?= htmlspecialchars($error, ENT_QUOTES, 'UTF-8') ?></p>
    <?php endif; ?>

    <form method="POST">
        <input type="text" name="code" pattern="\d{6}" maxlength="6" required autofocus
               placeholder="000000">
        <button type="submit">Verificar</button>
    </form>
</body>
</html>
```

### 54.6 Sinergia com PHP 8.5

Ao combinar o **Gemini 3 Flash** (configurado com `thinking_level: "minimal"`) com o recurso de **cURL Persistente** do PHP 8.5 (`curl_share_init_persistent`), você elimina quase toda a latência de rede e processamento, criando um sistema de segurança "invisível" para o usuário, mas impenetrável para bots simples.

### 54.7 Boas Práticas PHP 8.5 neste Fluxo

1.  **`Randomizer` Engine:** Usamos a classe nativa segura para gerar o OTP, evitando `rand()` que é previsível.
2.  **Hashing do OTP:** Nunca guardamos o código `123456` na sessão. Guardamos o `password_hash('123456')`. Se um atacante roubar o arquivo de sessão do servidor, ele não saberá qual é o código.
3.  **Enumerações:** O uso de `enum LoginStatus` torna o código do controller muito mais legível do que retornar `true`, `false` ou `-1`.
4.  **Sessão Parcial:** A chave `user_id` (que dá acesso ao sistema) **nunca** é definida até que o 2FA seja validado. Apenas `2fa_pending` existe na sessão durante o risco.
5.  **`#[\NoDiscard]`:** Garante que o resultado de `login()` seja sempre verificado pelo controller.
6.  **Cookies Particionados:** Recurso PHP 8.5 para segurança em contextos de iframes/widgets.

---


---

## 55. Operador Pipe (`|>`) — Guia Prático Avançado

O operador pipe transforma chamadas aninhadas em pipelines legíveis: o resultado da expressão à esquerda é passado como argumento para a função à direita. Este capítulo demonstra usos práticos em higienização de dados, validação de regras e auditoria de segurança.

### 55.1 O Conceito: "De cima para baixo" em vez de "De dentro para fora"

Sem o Pipe Operator, o tratamento de um e-mail no login geralmente se parece com isso (leitura de dentro para fora):

```php
<?php

declare(strict_types=1);

// ❌ PHP 8.4 ou anterior (Difícil de ler)
$email = filter_var(strtolower(trim($_POST['email'])), FILTER_SANITIZE_EMAIL);
```

Com o **PHP 8.5**, você passa o valor da esquerda para a direita (ou de cima para baixo), transformando-o passo a passo.

### 55.2 Exemplo Prático: Higienização no Login

No seu método `login`, o uso do Pipe Operator torna a preparação dos dados óbvia e auditável.

```php
<?php

declare(strict_types=1);

class AuthController
{
    public function login(string $rawEmail, string $password): bool
    {
        // Higienização do E-mail com Pipe Operator
        // O valor flui através das funções sequencialmente
        $cleanEmail = $rawEmail
            |> trim(...)                 // Remove espaços extras
            |> strtolower(...)           // Converte para minúsculas
            |> fn($v) => filter_var($v, FILTER_SANITIZE_EMAIL); // Filtro específico

        // Busca no banco (usando o dado limpo)
        $user = $this->userRepo->findByEmail($cleanEmail);

        // ... restante da lógica de verificação de senha
        return true;
    }
}
```

### 55.3 Exemplo Avançado: Validação de Regras de Negócio

Você pode usar o Pipe Operator para passar o objeto de usuário por uma série de verificações de segurança antes de permitir o login. Se alguma falhar, o fluxo é interrompido.

```php
<?php

declare(strict_types=1);

namespace App\Security;

use App\Exception\LoginException;

class LoginRules
{
    public static function checkUserIsActive(array $user): array
    {
        if (!$user['is_active']) {
            throw new LoginException("Conta desativada.");
        }
        return $user;
    }

    public static function checkNotBanned(array $user): array
    {
        if ($user['is_banned']) {
            throw new LoginException("Conta banida.");
        }
        return $user;
    }

    public static function checkPasswordExpiry(array $user): array
    {
        if (strtotime($user['password_changed_at']) < strtotime('-90 days')) {
            throw new LoginException("Senha expirada. Troca obrigatória.");
        }
        return $user;
    }
}

// Uso com Pipe Operator
$user = $this->userRepo->findByEmail($email);

if ($user) {
    try {
        $user
            |> LoginRules::checkUserIsActive(...)     // Verifica se está ativo
            |> LoginRules::checkNotBanned(...)         // Verifica se não está banido
            |> LoginRules::checkPasswordExpiry(...);   // Verifica expiração de senha

        // Se chegou aqui, o usuário é válido
    } catch (LoginException $e) {
        return false;
    }
}
```

### 55.4 Vantagens no Contexto de Segurança

1.  **Auditoria de Segurança:** É muito fácil ver visualmente *quais* filtros foram aplicados ao input do usuário. Se você esquecer um `trim()`, ele se destaca pela ausência na lista vertical.
2.  **Imutabilidade:** Você evita reatribuir a variável `$email` várias vezes (`$email = trim($email); $email = strtolower($email);`), criando um fluxo único de transformação.
3.  **Closures:** Você pode usar arrow functions (`fn($v) => ...`) no pipe para injetar argumentos adicionais em funções que exigem mais de um parâmetro.

---

## 56. Validação de Senhas e Autoloading Moderno

Segurança começa na senha: validação com regex, hashing com `password_hash()`/`password_verify()` e entropia adequada. Autoloading com PSR-4 organiza o código em namespaces mapeados a diretórios, automatizado pelo Composer ou por `spl_autoload_register`.

### 56.1 Validação Técnica de Senhas com Regex (PHP 8.5)

No backend, não devemos confiar apenas no frontend. Devemos usar **Expressões Regulares (Regex)** para impor regras de complexidade.

```php
<?php

declare(strict_types=1);

namespace App\Security;

class PasswordValidator
{
    // PHP 8.5 permite constantes tipadas
    private const int MIN_LENGTH = 12;

    public static function validate(string $password): array
    {
        $errors = [];

        // 1. Comprimento (Fator mais importante para entropia)
        if (strlen($password) < self::MIN_LENGTH) {
            $errors[] = "A senha deve ter pelo menos " . self::MIN_LENGTH . " caracteres.";
        }

        // 2. Complexidade via Regex
        $patterns = [
            '/[A-Z]/'  => 'uma letra maiúscula',
            '/[a-z]/'  => 'uma letra minúscula',
            '/\d/'     => 'um número',
            '/[\W_]/'  => 'um símbolo especial (!@#$%)',
        ];

        foreach ($patterns as $regex => $message) {
            if (!preg_match($regex, $password)) {
                $errors[] = "A senha deve conter pelo menos $message.";
            }
        }

        return $errors;
    }
}
```

#### Armazenamento Seguro (Hash)

Nunca armazene a senha em texto puro. O PHP possui funções nativas robustas:

```php
<?php

declare(strict_types=1);

// Custo 12 é um bom equilíbrio entre segurança e performance
$hash = password_hash($password, PASSWORD_BCRYPT, ['cost' => 12]);

// Verificação — password_verify é resistente a timing attacks
if (password_verify($inputPassword, $hash)) {
    echo "Senha correta!";
}
```

#### Dica de Segurança

> **Tamanho > Complexidade:** Uma senha de 15 caracteres (`cavalo correto bateria grampo`) é muitas vezes mais forte que uma de 8 caracteres complexa (`Tr0ub4&`), e muito mais fácil de lembrar.

### 56.2 PSR-0 vs PSR-4 — Diferenças Práticas

Embora o PSR-0 esteja depreciado, é importante entender a diferença para manter sistemas legados.

#### Profundidade da Estrutura de Pastas

Imagine que temos a classe `App\Controllers\HomeController` e queremos que o código fique na pasta `src`.

*   **No PSR-0 (Obrigatório espelhamento total):**
    *   Caminho: `src/App/Controllers/HomeController.php`
    *   Você é obrigado a criar uma pasta `App` dentro de `src`.

*   **No PSR-4 (Mapeamento de prefixo):**
    *   Caminho: `src/Controllers/HomeController.php`
    *   A estrutura fica mais limpa e curta.

#### O Tratamento de Underscores

*   **No PSR-0:** Um underscore (`_`) no nome da classe é convertido em diretório.
    *   Classe: `App\Utils\String_Builder` → Arquivo: `.../App/Utils/String/Builder.php`

*   **No PSR-4:** Underscores são parte do nome, sem significado especial.
    *   Classe: `App\Utils\String_Builder` → Arquivo: `.../App/Utils/String_Builder.php`

#### Resumo Visual

| Classe Solicitada | Padrão | Onde o PHP procura |
| :--- | :--- | :--- |
| `Vendor\Pacote\User` | **PSR-0** | `lib/Vendor/Pacote/User.php` (redundante) |
| `Vendor\Pacote\User` | **PSR-4** | `lib/User.php` (limpo e direto) |

> **Conclusão:** No PHP Moderno, **sempre utilize PSR-4**.

### 56.3 Autoloader PSR-4 com Pipe Operator (PHP 8.5)

```php
<?php

declare(strict_types=1);

/**
 * Autoloader PSR-4 Avançado - PHP 8.5
 * Suporta múltiplos mapeamentos de namespaces para diretórios.
 */
spl_autoload_register(function (string $className): void {
    // Mapeamento de Namespace => Diretório Base
    $namespaceMap = [
        'App\\'    => __DIR__ . '/src/',
        'Core\\'   => __DIR__ . '/core/',
        'Shared\\' => __DIR__ . '/shared/',
    ];

    // 1. Encontra o prefixo que corresponde à classe atual
    $matchedPrefix = array_keys($namespaceMap)
        |> fn(array $prefixes): array => array_filter(
            $prefixes,
            fn(string $prefix) => str_starts_with($className, $prefix),
        )
        |> fn(array $matches): ?string => array_first($matches);

    // Se a classe não pertence a nenhum dos nossos namespaces, ignoramos
    if ($matchedPrefix === null) {
        return;
    }

    $baseDirectory = $namespaceMap[$matchedPrefix];

    // 2. Transforma o nome da classe no caminho físico do arquivo
    $filePath = $className
        |> fn(string $name): string => str_replace($matchedPrefix, '', $name)
        |> fn(string $relative): string => str_replace('\\', DIRECTORY_SEPARATOR, $relative)
        |> fn(string $path): string => $baseDirectory . $path . '.php';

    // 3. Carregamento seguro
    if (file_exists($filePath)) {
        require_once $filePath;
    }
});
```

### 56.4 Implementação PSR-4 Manual (Tradicional)

**Estrutura de Pastas:**

```text
meu-projeto/
├── src/
│   ├── Controller/
│   │   └── HomeController.php  (Namespace: App\Controller)
│   └── Service/
│       └── EmailService.php    (Namespace: App\Service)
├── index.php
└── autoload.php
```

**Autoloader (`autoload.php`):**

```php
<?php

declare(strict_types=1);

spl_autoload_register(function (string $class): void {
    $prefix   = 'App\\';
    $base_dir = __DIR__ . '/src/';

    $len = strlen($prefix);
    if (strncmp($prefix, $class, $len) !== 0) {
        return;
    }

    $relative_class = substr($class, $len);
    $file = $base_dir . str_replace('\\', '/', $relative_class) . '.php';

    if (file_exists($file)) {
        require $file;
    }
});
```

**Uso (`index.php`):**

```php
<?php

require 'autoload.php';

use App\Controller\HomeController;

$controller = new HomeController();
```

### 56.5 Implementação via Composer (Padrão da Indústria)

```json
{
    "autoload": {
        "psr-4": {
            "App\\": "src/"
        }
    }
}
```

```bash
composer dump-autoload
```

```php
<?php

require __DIR__ . '/vendor/autoload.php';
```

#### Regras Importantes da PSR-4

*   **Namespaces:** O namespace no arquivo deve corresponder exatamente à estrutura de pastas.
*   **Case Sensitivity:** O nome do arquivo deve ser idêntico ao nome da classe. Diferenças de maiúsculas/minúsculas causarão erros em sistemas Linux.


---

## 57. Property Hooks — Guia Completo

Os **Property Hooks** (PHP 8.4+, consolidados no 8.5) permitem anexar lógica de validação e transformação diretamente nas propriedades, eliminando getters/setters verbosos. Blocos `get` e `set` substituem métodos inteiros por 2-3 linhas.

Os **Property Hooks** (ganchos de propriedade), introduzidos no PHP 8.4 e consolidados no **PHP 8.5**, resolvem uma das maiores reclamações históricas do PHP: a verbosidade excessiva de *Getters* e *Setters*.

Antes, para proteger uma propriedade e validar um dado, você precisava de propriedades privadas e métodos públicos. Agora, a lógica vive **dentro** da própria propriedade.

### 57.1 O Conceito: Lógica Anexada aos Dados

Em vez de criar métodos separados (`getName()`, `setName()`), definimos blocos `get` e `set` diretamente na declaração da propriedade.

*   **`get`**: Executado quando alguém **lê** a propriedade.
*   **`set`**: Executado quando alguém **escreve** na propriedade.

### 57.2 Exemplo Completo: UserAccount

**Cenário:**
1.  O **nome** deve ser sempre capitalizado ao ser lido.
2.  A **senha** deve ser automaticamente convertida em *hash* ao ser definida.

```php
<?php

declare(strict_types=1);

class UserAccount
{
    // 1. Property Hook de Leitura (GET)
    // O valor real é armazenado, mas transformamos na saída.
    public string $displayName {
        get {
            return ucwords($this->displayName);
        }
        set(string $value) {
            $this->displayName = trim($value);
        }
    }

    // 2. Property Hook de Escrita (SET) com Backing Value
    // A senha nunca é salva em texto puro.
    public string $password {
        set(string $value) {
            if (strlen($value) < 8) {
                throw new \InvalidArgumentException(
                    "Password must be at least 8 characters long.",
                );
            }
            $this->password = password_hash($value, PASSWORD_DEFAULT);
        }
    }

    // 3. Sintaxe Curta (Arrow Function) para Getters Calculados
    // Propriedade virtual — não ocupa espaço na memória.
    public string $roleLabel {
        get => strtoupper($this->role);
    }

    public function __construct(
        string $displayName,
        string $password,
        public string $role = 'member',
    ) {
        $this->displayName = $displayName;
        $this->password = $password;
    }
}

// --- Testando a Implementação ---

try {
    $user = new UserAccount('  carlos silva  ', 'Secret123!');

    echo "User: " . $user->displayName . PHP_EOL;
    // Saída: User: Carlos Silva (trim no set + ucwords no get)

    echo "Role: " . $user->roleLabel . PHP_EOL;
    // Saída: Role: MEMBER

    // Testando a validação do Hook SET
    $user->password = 'short'; // Vai lançar exceção

} catch (\InvalidArgumentException $e) {
    echo "Error: " . $e->getMessage() . PHP_EOL;
}
```

### 57.3 Análise Técnica Detalhada

1.  **A variável `$value`**: No bloco `set`, o PHP injeta automaticamente o valor que está sendo atribuído. É boa prática ser explícito: `set(string $value)`.

2.  **O uso de `$this->propriedade` dentro do hook**: No PHP 8.5, quando você atribui à propriedade *dentro* do hook dela, o compilador entende que você quer escrever no **armazenamento bruto (backing value)**, ignorando o hook para evitar loop infinito.

3.  **Propriedades Virtuais**: Veja `$roleLabel`. Ela não ocupa espaço na memória como um dado duplicado; ela é calculada apenas no momento do acesso.

### 57.4 Comparativo: Legacy vs. Moderno

**❌ Legacy (PHP 7.x / 8.0 Antigo)**

```php
<?php

declare(strict_types=1);

class User
{
    private string $name;

    public function setName(string $name): void
    {
        $this->name = trim($name);
    }

    public function getName(): string
    {
        return ucwords($this->name);
    }
}
```

*Problema:* A classe fica cheia de métodos que só servem para encapsulamento básico.

**✅ PHP 8.5 Moderno**

```php
<?php

declare(strict_types=1);

class User
{
    public string $name {
        get => ucwords($this->name);
        set(string $value) => $this->name = trim($value);
    }
}
```

*Vantagem:* Código curto, intenção clara, propriedade pública para acesso mas protegida internamente.

### 57.5 Exemplo Prático: Classe Product

```php
<?php

declare(strict_types=1);

class Product
{
    public float $price {
        set(float $value) {
            if ($value < 0) {
                throw new \DomainException("Price cannot be negative.");
            }
            $this->price = round($value, 2);
        }
    }

    // Propriedade Virtual (não ocupa memória extra)
    public string $priceFormatted {
        get {
            return 'R$ ' . number_format($this->price, 2, ',', '.');
        }
    }

    public function __construct(float $price)
    {
        $this->price = $price;
    }
}

$item = new Product(19.999);
echo $item->price;          // 20.0 (arredondado)
echo $item->priceFormatted; // R$ 20,00
```

---

## 58. Visibilidade Assimétrica — Controle Granular de Acesso

Visibilidade assimétrica (PHP 8.4+, expandida no 8.5) permite definir níveis diferentes para leitura e escrita na mesma propriedade: `public private(set)` significa "todos leem, só eu escrevo". Combinada com Property Hooks, elimina praticamente todo boilerplate de encapsulamento.

A **Visibilidade Assimétrica** é o complemento perfeito para os *Property Hooks*. Juntos, eles eliminam quase todo o código repetitivo (boilerplate) que costumávamos escrever em PHP.

### 58.1 O Conceito

No PHP 8.5 (evoluindo o recurso do 8.4), você não precisa mais tornar uma propriedade `private` e criar um método `getPropriedade()` apenas para permitir que ela seja lida fora da classe, mas não alterada.

Agora, controlamos a **leitura** e a **escrita** separadamente na mesma linha.

### 58.2 Sintaxe

```php
<?php

declare(strict_types=1);

class Order
{
    // Pode ser LIDA publicamente, mas SÓ pode ser ESCRITA dentro da classe
    public private(set) string $status = 'pending';

    // Pode ser LIDA publicamente, mas SÓ pode ser ESCRITA pela classe ou subclasses
    public protected(set) float $total = 0.0;

    public function confirm(): void
    {
        // Dentro da classe, a escrita funciona normalmente
        $this->status = 'confirmed';
    }
}

$order = new Order();

// ✅ Leitura pública funciona
echo $order->status; // 'pending'

// ❌ Escrita externa NÃO funciona — Error!
// $order->status = 'cancelled';

// ✅ Escrita via método público
$order->confirm();
echo $order->status; // 'confirmed'
```

### 58.3 Combinando com Property Hooks

O verdadeiro poder surge ao combinar visibilidade assimétrica com property hooks:

```php
<?php

declare(strict_types=1);

class BankAccount
{
    // Saldo: leitura pública, escrita privada, com formatação no getter
    public private(set) float $balance {
        get => round($this->balance, 2);
    }

    public function __construct(float $initialBalance)
    {
        $this->balance = $initialBalance;
    }

    public function deposit(float $amount): void
    {
        if ($amount <= 0) {
            throw new \InvalidArgumentException("Deposit must be positive.");
        }
        $this->balance += $amount;
    }

    public function withdraw(float $amount): void
    {
        if ($amount > $this->balance) {
            throw new \DomainException("Insufficient funds.");
        }
        $this->balance -= $amount;
    }
}

$account = new BankAccount(1000.00);
$account->deposit(250.50);
echo $account->balance; // 1250.5

// ❌ Acesso direto bloqueado
// $account->balance = 999999; // Error!
```

### 58.4 Com Readonly e Constructor Promotion

```php
<?php

declare(strict_types=1);

readonly class UserDTO
{
    public function __construct(
        public string $name,
        public string $email,
        public string $role = 'user',
    ) {}
}

// Todas as propriedades são:
// - Públicas para leitura
// - Imutáveis após construção (readonly)
$user = new UserDTO(name: 'João', email: 'joao@example.com');
echo $user->name;   // 'João'
// $user->name = 'Maria'; // ❌ Error: Cannot modify readonly property
```

### 58.5 Quando Usar Cada Abordagem

| Cenário | Abordagem Recomendada |
| :--- | :--- |
| Dados imutáveis (DTOs, Value Objects) | `readonly class` |
| Propriedade legível externamente, controlada internamente | `public private(set)` |
| Propriedade com validação na escrita | Property Hook `set` |
| Propriedade com formatação na leitura | Property Hook `get` |
| Controle completo (validação + acesso) | Property Hook + Visibilidade Assimétrica |


---

## 59. PHP 8.5 por Nível — Exemplos Práticos

Este capítulo apresenta as novidades do PHP 8.5 em três níveis de complexidade: iniciante (arrays e funções), intermediário (OOP e Property Hooks) e avançado (Pipe Operator e extensão URI). Cada exemplo resolve um desafio prático real.

### 59.1 🟢 Nível Iniciante: Arrays e Funções Facilitadas

Se você está começando, o PHP 8.5 traz funções que eliminam a complexidade de manipular listas de dados.

**O Desafio:** Pegar o primeiro nome de uma lista de usuários.

```php
<?php

declare(strict_types=1);

$userList = ['Alice', 'Bob', 'Charlie'];

// ❌ Legacy (Antigo): Confuso e precisa lidar com ponteiros internos
// $firstUser = reset($userList);

// ✅ PHP 8.5 Moderno: Direto e legível
$firstUser = array_first($userList);

echo "First user: " . $firstUser; // Alice
```

### 59.2 🟡 Nível Intermediário: OOP e Property Hooks

Se você já entende classes, veja como o PHP 8.5 (e 8.4) limpa o código, eliminando *getters* e *setters* verbosos.

**O Desafio:** Criar uma classe de Usuário onde o nome é sempre salvo em letras maiúsculas.

```php
<?php

declare(strict_types=1);

class UserProfile
{
    // ✅ PHP 8.5 Moderno: Property Hooks definem a lógica na propriedade
    public string $userName {
        set(string $value) {
            $this->userName = strtoupper($value);
        }
    }

    public function __construct(string $name)
    {
        $this->userName = $name;
    }
}

$profile = new UserProfile('daniil');
echo $profile->userName; // Saída: DANIIL
```

### 59.3 🔴 Nível Avançado: Arquitetura e Pipe Operator

Se você busca código limpo e funcional, o PHP 8.5 introduz o **Operador Pipe (`|>`)**, permitindo encadear funções sem aninhamento.

**O Desafio:** Limpar uma URL, analisar e obter o domínio.

```php
<?php

declare(strict_types=1);

// ✅ PHP 8.5 Moderno: Usando a nova extensão URI e Pipe Operator
$rawUrl = "  https://www.php.net/releases/8.5  ";

$domain = $rawUrl
    |> trim(...)                            // Remove espaços
    |> new Uri\Rfc3986\Uri(...)             // Cria objeto URI nativo do PHP 8.5
    |> fn($uri) => $uri->getHost();         // Extrai o host

echo $domain; // Saída: www.php.net
```


---

## 60. Visibilidade Assimétrica — Aprofundamento e Herança

Este capítulo aprofunda a visibilidade assimétrica com cenários de herança, propriedades estáticas (PHP 8.5), combinação com Property Hooks e regras de sobrescrita (covariância). Inclui exemplos práticos com `ServerConnection`, `ShoppingCart` e um sistema de RPG.

### 60.1 Implementação Prática: ServerConnection

Este exemplo demonstra `public private(set)` e `public protected(set)` com Constructor Promotion — leitura pública, escrita controlada:
```php
<?php

declare(strict_types=1);

class ServerConnection
{
    // 'public': Todo mundo pode ler ($conn->status).
    // 'private(set)': Só esta classe pode alterar ($this->status = ...).
    public private(set) string $status = 'disconnected';

    // Também funciona com Constructor Promotion
    public function __construct(
        public private(set) string $dsn,
        public protected(set) int $retries = 3,
    ) {}

    public function connect(): void
    {
        $this->status = 'connected'; // Permitido (dentro da classe)
    }
}

$server = new ServerConnection('mysql:host=localhost', 5);

// ✅ Leitura permitida (Public Get)
echo "DSN: " . $server->dsn . PHP_EOL;
echo "Status: " . $server->status . PHP_EOL;

// ❌ Escrita proibida (Private Set) — Gera Erro Fatal
// $server->status = 'offline';
// Error: Cannot modify private(set) property ServerConnection::$status
```

### 60.2 Propriedades Estáticas com Visibilidade Assimétrica (PHP 8.5)

O PHP 8.5 expandiu a visibilidade assimétrica para **propriedades estáticas**, permitindo configurações globais legíveis externamente mas alteráveis apenas internamente. Isso é extremamente útil para padrões Singleton ou Registry sem precisar de métodos getters estáticos.

```php
<?php

declare(strict_types=1);

class AppConfig
{
    // Recurso exclusivo do PHP 8.5+
    // Leitura pública, escrita apenas interna
    public static private(set) string $environment = 'production';

    public static function setTestMode(): void
    {
        self::$environment = 'testing';
    }
}

// ✅ Leitura Pública
echo "Env: " . AppConfig::$environment;

// ❌ Escrita Externa Bloqueada
// AppConfig::$environment = 'dev'; // Erro!
```

### 60.3 Combinando Visibilidade Assimétrica com Property Hooks

O verdadeiro poder surge ao combinar **Visibilidade Assimétrica** (controle de acesso) com **Property Hooks** (controle de lógica).

**Cenário:** Um carrinho de compras onde o `total` é público para leitura, protegido para escrita, e calculado automaticamente.

```php
<?php

declare(strict_types=1);

class ShoppingCart
{
    // O array é privado (ninguém vê nem toca diretamente)
    private array $items = [];

    // Público para ler, protegido para escrever.
    // Hook GET calcula o valor dinamicamente.
    public protected(set) float $totalAmount {
        get {
            return array_sum(array_column($this->items, 'price'));
        }
    }

    public function addItem(string $name, float $price): void
    {
        $this->items[] = ['name' => $name, 'price' => $price];
        // Não precisamos atualizar $totalAmount manualmente,
        // pois o hook GET calcula dinamicamente.
    }
}

$cart = new ShoppingCart();
$cart->addItem('Keyboard', 150.00);
$cart->addItem('Mouse', 50.00);

echo "Total: " . $cart->totalAmount; // Saída: 200
// ❌ $cart->totalAmount = 0; // Erro: protected(set)
```

### 60.4 Comparativo: Legacy vs. PHP 8.5

A redução de boilerplate é dramática: o que exigia propriedade privada + método getter agora é uma única linha com `public private(set)`:
**❌ Legacy (PHP 8.0 - 8.3)**

```php
<?php

declare(strict_types=1);

class User
{
    private string $id;

    public function __construct(string $id)
    {
        $this->id = $id;
    }

    // Boilerplate apenas para leitura
    public function getId(): string
    {
        return $this->id;
    }
}
```

**✅ PHP 8.5 Moderno**

```php
<?php

declare(strict_types=1);

class User
{
    // Uma linha define a propriedade, o construtor e o controle de acesso
    public function __construct(
        public private(set) string $id,
    ) {}
}
```

### 60.5 Regras de Restrição

A visibilidade do `set` deve ser sempre **mais restrita** (ou igual) à visibilidade principal de leitura. Tentar ampliar o set além do get gera erro de compilação:

| Combinação | Válido? |
| :--- | :--- |
| `public private(set)` | ✅ Sim |
| `public protected(set)` | ✅ Sim |
| `protected private(set)` | ✅ Sim |
| `private public(set)` | ❌ Não (se é privado para ler, não pode ser público para escrever) |

---

## 61. Visibilidade Assimétrica na Herança

Este capítulo detalha como `private(set)` e `protected(set)` se comportam em hierarquias de classes, incluindo sobrescrita de visibilidade (covariância) e cenários práticos com sistemas de RPG e relatórios.

### 61.1 A Diferença Fundamental

1.  **`public private(set)`**: Apenas a classe que definiu a propriedade pode alterá-la. Classes filhas **não** podem tocar nela (apenas ler).
2.  **`public protected(set)`**: A classe que definiu **e** as classes que herdam dela podem alterar o valor. O mundo externo continua impedido.

### 61.2 Cenário Prático: Sistema de RPG

Este exemplo demonstra a diferença entre `private(set)` e `protected(set)` na herança: a classe `Character` define `$health` como `protected(set)`, permitindo que a subclasse `Paladin` altere o valor diretamente:

```php
<?php

declare(strict_types=1);

class Character
{
    // Leitura: Pública (qualquer um vê quanto de vida tem)
    // Escrita: Protegida (Pai e Filhos podem alterar)
    public protected(set) int $health;

    public function __construct(int $initialHealth)
    {
        $this->health = $initialHealth;
    }

    public function takeDamage(int $amount): void
    {
        $this->health -= $amount;
    }
}

class Paladin extends Character
{
    public function holyHeal(): void
    {
        // ✅ PERMITIDO: Classes filhas podem escrever em propriedades protected(set)
        // Se fosse private(set), esta linha geraria um Erro Fatal.
        $this->health += 10;
    }
}

// --- Testando a Herança ---

$hero = new Paladin(100);

echo "Start: " . $hero->health . PHP_EOL;      // Leitura pública: 100
$hero->takeDamage(20);
echo "After Hit: " . $hero->health . PHP_EOL;   // Alterado pelo Pai: 80
$hero->holyHeal();
echo "After Heal: " . $hero->health . PHP_EOL;  // Alterado pelo Filho: 90

// ❌ PROIBIDO: Escrita externa
// $hero->health = 500;
// Error: Cannot modify protected(set) property Character::$health from global scope
```

### 61.3 Sobrescrita de Visibilidade (Overriding)

No PHP 8.5, ao estender uma classe, você pode **redefinir** a visibilidade, mas deve seguir as regras de covariância (pode ampliar acesso, não restringir).

```php
<?php

declare(strict_types=1);

class BaseReport
{
    // Escrita restrita à hierarquia
    public protected(set) string $status = 'pending';
}

class PublicReport extends BaseReport
{
    // ✅ PERMITIDO: Tornar o set público na filha (ampliar acesso)
    public string $status = 'pending';
}

/*
class LockedReport extends BaseReport
{
    // ❌ ERRO: Não podemos restringir para private(set) se o pai era protected(set)
    public private(set) string $status;
}
*/
```

### 61.4 Tabela Resumo: Controle de Acesso na Herança

| Definição | Leitura (Get) | Escrita Pai | Escrita Filho | Escrita Externa |
| :--- | :--- | :--- | :--- | :--- |
| `public type $prop` | ✅ Sim | ✅ Sim | ✅ Sim | ✅ Sim |
| `public private(set)` | ✅ Sim | ✅ Sim | ❌ Não | ❌ Não |
| `public protected(set)` | ✅ Sim | ✅ Sim | ✅ Sim | ❌ Não |


---

## 62. Módulo Prático 1 — Fundamentos do PHP 8.5 Moderno

Este módulo prático cobre os fundamentos do PHP 8.5: `strict_types`, sistema de tipos, `match`, `array_first()`/`array_last()`, argumentos nomeados e uma prévia do operador pipe. Cada seção inclui exercícios para consolidação.

### 62.1 O Contrato de Rigor (`strict_types`)

No PHP moderno, não deixamos a linguagem "adivinhar" o que queremos. O PHP antigo tentava converter o texto `"10"` no número `10` automaticamente. Isso causava bugs silenciosos.

**Regra de Ouro:** Todo arquivo PHP deve começar definindo tipagem estrita.

```php
<?php

declare(strict_types=1); // A primeira linha de todo arquivo moderno.

// Sem isso, o PHP tentaria converter tipos incorretos.
// Com isso, ele lança um erro fatal se você passar o tipo errado.
```

### 62.2 Variáveis e Sistema de Tipos

Em PHP 8.5, as variáveis são representadas por `$`. Mas o mais importante é o **Tipo**.

**Tipos Primitivos Modernos:**

*   `string`: Textos.
*   `int`: Números inteiros.
*   `float`: Números decimais.
*   `bool`: Verdadeiro (`true`) ou Falso (`false`).
*   `null`: Ausência de valor.

**Atenção à Descontinuação no PHP 8.5:**

*   ✅ Use: `(bool)`, `(int)`, `(float)`, `(string)`.
*   ❌ Evite: `(boolean)`, `(integer)`, `(double)`, `(real)`.

```php
<?php

declare(strict_types=1);

$userName = "Carlos";      // string
$userAge = 30;             // int
$accountBalance = 150.50;  // float
$isActive = true;          // bool

// Interpolação de strings (aspas duplas interpretam variáveis)
echo "User {$userName} is {$userAge} years old.";

// Conversão segura (Casting)
$inputString = "100";
$score = (int) $inputString; // Converte string para int
```

### 62.3 Estruturas de Controle: O Poder do `match`

O `switch` tinha sintaxe verbosa e comparação fraca (`==`). O `match` (PHP 8.0+) é a evolução: mais curto, retorna valor e usa comparação estrita (`===`).

```php
<?php

declare(strict_types=1);

$orderStatus = 'pending';

// ✅ Expressão match
$message = match ($orderStatus) {
    'paid'                => 'Payment received.',
    'pending'             => 'Waiting for payment.',
    'canceled', 'failed'  => 'Order was not processed.',
    default               => 'Unknown status.',
};

echo $message;
```

Por que `match` é melhor:

1.  Não precisa de `break`.
2.  Retorna o resultado diretamente para uma variável.
3.  Se nenhum caso bater e não houver `default`, lança um erro (evita bugs lógicos).

### 62.4 Arrays e Funções Nativas do PHP 8.5

No **PHP 8.5**, ganhamos funções nativas para pegar o primeiro e o último elemento sem manipular ponteiros internos.

```php
<?php

declare(strict_types=1);

// Array Associativo (Chave => Valor)
$userData = [
    'name'  => 'Ana',
    'role'  => 'admin',
    'score' => 95,
];

// Array Indexado (Lista)
$accessLog = [
    'Login at 10:00',
    'Viewed page at 10:05',
    'Logout at 10:30',
];

// ✅ PHP 8.5: Novas funções auxiliares
$firstLog = array_first($accessLog);
$lastLog  = array_last($accessLog);

echo "First activity: " . $firstLog; // Login at 10:00

// Verificar existência de chave
if (array_key_exists('role', $userData)) {
    echo "Role: " . $userData['role'];
}

// Descontinuação PHP 8.5:
// Não use null como chave de array ou em array_key_exists.
// $data[null] = 'Erro'; // Deprecated!
```

### 62.5 Funções e Argumentos Nomeados

No PHP moderno, **tipamos tudo**: o que entra (parâmetros) e o que sai (retorno). Além disso, usamos **Argumentos Nomeados** (PHP 8.0+), que permitem pular parâmetros opcionais.

```php
<?php

declare(strict_types=1);

/**
 * Calculates the final price including tax and discount.
 */
function calculateTotal(
    float $price,
    float $taxRate = 0.1,
    float $discount = 0.0,
): float {
    $total = $price * (1 + $taxRate);
    return $total - $discount;
}

// Chamada Tradicional (Posicional)
echo calculateTotal(100.0, 0.2, 5.0); // 115.0

// ✅ Chamada Moderna (Argumentos Nomeados)
// Pula o $taxRate (usa o padrão 0.1) e nomeia o desconto
echo calculateTotal(
    price: 200.0,
    discount: 10.0,
); // 210.0
```

### 62.6 O Operador Pipe (`|>`) — Prévia

O PHP 8.5 introduziu o operador Pipe para evitar o "código cebola" (uma função dentro da outra).

```php
<?php

declare(strict_types=1);

$rawInput = "   FABIO   ";

// ❌ Estilo antigo (Aninhado)
// $clean = strtolower(trim($rawInput));

// ✅ PHP 8.5 (Pipe Operator)
$clean = $rawInput
    |> trim(...)
    |> strtolower(...);

echo $clean; // "fabio"
```

### 62.7 Exercício Prático

Escreva um script que:

1.  Comece com `declare(strict_types=1)`.
2.  Crie uma função `analyzeGrades` que receba um array de notas (`float`).
3.  Dentro da função:
    *   Use `array_first()` e `array_last()` para achar a primeira e última nota.
    *   Calcule a média.
    *   Use `match` para retornar: "Excellent" (média > 9), "Good" (média > 7) ou "Needs Improvement".
4.  Execute a função usando **Argumentos Nomeados**.


---

## 63. Módulo Prático 2 — Orientação a Objetos Moderna

Este módulo aprofunda OOP moderno: constructor promotion com `final`, enums com métodos, visibilidade assimétrica estática, `clone with` para classes `readonly`, e o atributo `#[\NoDiscard]` para segurança.

### 63.1 Construtores Modernos e Promoção de Propriedades

Com a **Promoção de Propriedade de Construtor** (PHP 8.0+), declaração, parâmetro e atribuição são feitos em uma linha.

**Novidade PHP 8.5:** Agora podemos usar `final` em propriedades promovidas, garantindo que não sejam sobrescritas em heranças.

```php
<?php

declare(strict_types=1);

class UserProfile
{
    // PHP 8.5: 'final' definido diretamente no construtor
    public function __construct(
        public final string $username,
        public string $email,
        private string $password,
    ) {}
}
```

### 63.2 Enums: Tipos Fortes e Lógica

Introduzidos no PHP 8.1, os **Enums** substituem constantes soltas ou arrays mágicos. Eles podem ter métodos e implementar interfaces.

```php
<?php

declare(strict_types=1);

enum UserRole: string
{
    case ADMIN  = 'admin';
    case EDITOR = 'editor';
    case VIEWER = 'viewer';

    public function label(): string
    {
        return match ($this) {
            self::ADMIN  => 'Administrator',
            self::EDITOR => 'Content Editor',
            self::VIEWER => 'Guest',
        };
    }
}

// Uso
$role = UserRole::ADMIN;
echo $role->label(); // "Administrator"
```

### 63.3 Propriedades Estáticas com Visibilidade Assimétrica (Revisão)

**Novidade PHP 8.5:** Propriedades **estáticas** agora suportam visibilidade assimétrica.

```php
<?php

declare(strict_types=1);

class ServerConfig
{
    // Apenas a classe pode alterar, mas todos podem ler
    public static private(set) string $status = 'offline';

    public static function boot(): void
    {
        self::$status = 'booting';
    }
}
```

### 63.4 Imutabilidade e o Novo `clone with` (PHP 8.5)

Classes `readonly` são excelentes para segurança, mas difíceis de modificar. O **PHP 8.5** introduziu o **`clone with`**, simplificando o padrão "Wither".

```php
<?php

declare(strict_types=1);

readonly class ProductConfig
{
    public function __construct(
        public string $name,
        public float $price,
        public bool $isActive = true,
    ) {}
}

$original = new ProductConfig('Laptop', 1000.0);

// ❌ Antes (PHP 8.3): Manual e verboso
// $new = new ProductConfig($original->name, 2000.0, $original->isActive);

// ✅ PHP 8.5: Clone With — altera APENAS o preço
$upgrade = clone($original, ['price' => 2000.0]);

echo $upgrade->price; // 2000.0
echo $upgrade->name;  // Laptop (mantido)
```

### 63.5 O Atributo `#[\NoDiscard]` (PHP 8.5)

O PHP 8.5 adiciona `#[\NoDiscard]` para avisar se o retorno de um método for ignorado.

```php
<?php

declare(strict_types=1);

class Security
{
    #[\NoDiscard]
    public function verifyToken(string $token): bool
    {
        return $token === 'secret';
    }
}

$security = new Security();

// ❌ Aviso no PHP 8.5: retorno de verifyToken() não utilizado!
$security->verifyToken('123');

// ✅ Uso correto
if (!$security->verifyToken('123')) {
    die('Access Denied');
}
```

### 63.6 Exercício Prático

Crie um arquivo `order_system.php` que contenha:

1.  Um **Enum** `OrderStatus` (string) com casos: `PENDING`, `PAID`, `SHIPPED`. Adicione um método `canCancel()` que retorna `true` apenas se for `PENDING`.
2.  Uma classe `Order` (`readonly`) com:
    *   Construtor usando **promoção de propriedade** para: `id` (int), `amount` (float) e `status` (OrderStatus).
    *   O `status` deve ter valor padrão `OrderStatus::PENDING`.
3.  No código principal:
    *   Instancie um pedido.
    *   Use **`clone with`** para criar `$paidOrder`, alterando o status para `PAID`.
    *   Chame `canCancel()` no pedido pago e exiba o resultado.


---

## 64. Service Locator Pattern e Union Types

O Service Locator centraliza a resolução de dependências em um único registro. Combinado com Union Types (`callable|object`), suporta tanto Lazy Loading (closures/fábricas) quanto Eager Loading (instâncias prontas). Este capítulo implementa o padrão completo com PSR-11.

### 64.1 O Contrato (Interface)

Inspirado na **PSR-11** (Container Interface), garantindo interoperabilidade.

```php
<?php

declare(strict_types=1);

interface ServiceLocatorInterface
{
    /**
     * Recupera uma entrada do localizador.
     */
    #[\NoDiscard]
    public function get(string $id): mixed;

    /**
     * Verifica se o localizador tem a entrada.
     */
    public function has(string $id): bool;
}
```

### 64.2 Implementação do Service Locator (PHP 8.5)

Diferente do Singleton, esta classe é um objeto comum que passaremos adiante via injeção.

```php
<?php

declare(strict_types=1);

class AppServiceLocator implements ServiceLocatorInterface
{
    private array $definitions = [];
    private array $instances = [];

    /**
     * Registra um serviço.
     *
     * @param string          $id      Identificador (geralmente nome da classe)
     * @param callable|object $service Closure fábrica OU instância pronta
     */
    public function set(string $id, callable|object $service): void
    {
        // Cenário 1: É uma fábrica (Closure/Função) — Lazy Loading
        if (is_callable($service)) {
            $this->definitions[$id] = $service;

            if (array_key_exists($id, $this->instances)) {
                unset($this->instances[$id]);
            }
        }
        // Cenário 2: É um objeto já instanciado — Eager Loading
        else {
            $this->instances[$id] = $service;

            if (array_key_exists($id, $this->definitions)) {
                unset($this->definitions[$id]);
            }
        }
    }

    #[\NoDiscard]
    public function get(string $id): mixed
    {
        // 1. Verifica cache
        if (array_key_exists($id, $this->instances)) {
            return $this->instances[$id];
        }

        // 2. Verifica se existe receita para criar
        if (!array_key_exists($id, $this->definitions)) {
            throw new \RuntimeException("Service '{$id}' not found in locator.");
        }

        // 3. Executa a fábrica (Lazy Loading)
        $factory = $this->definitions[$id];
        $service = $factory($this);

        // 4. Salva no cache (Singleton escopado)
        $this->instances[$id] = $service;

        return $service;
    }

    public function has(string $id): bool
    {
        return array_key_exists($id, $this->instances)
            || array_key_exists($id, $this->definitions);
    }
}
```

### 64.3 O Consumidor

A classe recebe o `ServiceLocatorInterface` no construtor em vez de acessar um singleton global.

```php
<?php

declare(strict_types=1);

class ReportGenerator
{
    public function __construct(
        private ServiceLocatorInterface $locator,
    ) {}

    public function createAiReport(string $topic): void
    {
        if ($this->locator->has(GeminiClient::class)) {
            /** @var GeminiClient $ai */
            $ai = $this->locator->get(GeminiClient::class);

            $content = $ai->generateContent("Generate a short report about: {$topic}");
            echo "Report Generated: " . PHP_EOL . $content . PHP_EOL;
        } else {
            echo "AI Service unavailable." . PHP_EOL;
        }
    }
}
```

### 64.4 Configuração da Aplicação

Registre serviços com closures (lazy) ou instâncias (eager), e injete o locator nos consumidores:
```php
<?php

declare(strict_types=1);

// 1. Instanciamos o Locator
$locator = new AppServiceLocator();

// 2. Registramos os serviços (Wiring)
$locator->set(GeminiClient::class, function () {
    return new GeminiClient('API_KEY_REAL');
});

// 3. Injeção do Localizador
$reporter = new ReportGenerator($locator);

// 4. Execução
$reporter->createAiReport('PHP 8.5 Features');
```

### 64.5 Union Types: Lazy Loading vs Eager Loading

A assinatura `callable|object` oferece flexibilidade com segurança de tipos:

**Callable (Lazy Loading)** — O objeto só é criado quando `get()` é chamado:

```php
<?php

declare(strict_types=1);

// Recomendado para serviços "pesados" (Database, API Client)
$locator->set(Database::class, fn() => new Database('dsn'));
```

**Object (Eager Loading)** — Instância pronta, injetada diretamente:

```php
<?php

declare(strict_types=1);

// Útil para configurações simples ou mocks em testes
$config = new AppConfig();
$locator->set(AppConfig::class, $config);
```

**Em testes (Mocking):**

```php
<?php

declare(strict_types=1);

// ❌ Verboso (sem Union Type)
$mock = $this->createMock(GeminiClient::class);
$locator->set(GeminiClient::class, fn() => $mock);

// ✅ Limpo (com Union Type)
$mock = $this->createMock(GeminiClient::class);
$locator->set(GeminiClient::class, $mock);
```

### 64.6 Singleton vs Service Locator

| Característica | Singleton Container | Service Locator |
| :--- | :--- | :--- |
| **Acesso** | Global (`Container::getInstance()`) | Injetado (`__construct($locator)`) |
| **Testabilidade** | Difícil (estado global persiste) | Fácil (pode injetar um Mock Locator) |
| **Dependências** | Ocultas (magic) | Ocultas (vê o Locator, não o conteúdo) |
| **Uso Recomendado** | Projetos pequenos / Legacy | Frameworks grandes / Plugin systems |

**Por que o Service Locator é considerado anti-padrão por alguns?**

Ao olhar para `__construct(ServiceLocator $locator)`, você não sabe o que a classe realmente precisa. Na **Injeção de Dependência Pura** (o ideal moderno), o construtor seria:

```php
public function __construct(private GeminiClient $client)
```

### 64.7 Cuidado com Objetos Invocáveis

Classes que implementam `__invoke` são tanto `object` quanto `callable`. A verificação `is_callable()` vem primeiro no método `set()`, então objetos invocáveis serão tratados como fábricas. Se sua intenção for armazenar o objeto invocável como serviço, use `Closure` como tipo em vez de `callable`.

### 64.8 Exemplo Completo

Este exemplo consolida Lazy Loading (callable), Eager Loading (object) e segurança de tipos numa demonstração completa:
```php
<?php

declare(strict_types=1);

$locator = new AppServiceLocator();

// 1. Performance (Callable) — Lazy Loading
$locator->set('HeavyDatabase', function () {
    echo "Connecting to Database..." . PHP_EOL;
    return new stdClass(); // Simulando conexão
});

// 2. Simplicidade (Object) — Eager Loading
$config = new stdClass();
$config->env = 'production';
$locator->set('AppConfig', $config);

echo "--- Locator Configured ---" . PHP_EOL;

// Ao recuperar:
$db   = $locator->get('HeavyDatabase'); // Só AQUI conecta ao banco
$conf = $locator->get('AppConfig');     // Retorna instância direta

// 3. Segurança de Tipos
// $locator->set('Invalid', 'string'); // TypeError: must be callable|object
```


---

## 65. Superglobais e Segurança de Input

Superglobais (`$_GET`, `$_POST`, `$_SESSION`, `$_COOKIE`, `$_FILES`, `$_SERVER`) são o ponto de entrada de dados do usuário no PHP. Este capítulo ensina a tratá-las com segurança: validação de tipo, prepared statements e sanitização de saída.

### 65.1 O que são Superglobais

**Superglobais** são variáveis predefinidas nativas do PHP que estão sempre disponíveis em qualquer escopo do script, sem a necessidade de declará-las como `global`. Elas são ferramentas essenciais para o desenvolvimento web, permitindo o acesso a dados de requisições HTTP, sessões e informações do servidor.

Principais superglobais:

*   **`$_GET` e `$_POST`**: Processam dados enviados por formulários HTML ou requisições HTTP.
    *   `$_GET`: Coleta dados enviados via parâmetros na URL.
    *   `$_POST`: Coleta dados enviados no corpo da requisição HTTP, sendo o método padrão para informações sensíveis ou volumosas.
*   **`$_SERVER`**: Contém informações sobre cabeçalhos, caminhos e locais de script. Frequentemente usada para verificar o método da requisição ou obter dados do ambiente.
*   **`$_SESSION`**: Gerenciamento de sessões, permitindo persistir dados do usuário entre diferentes páginas, fundamental para login e autenticação.
*   **`$_COOKIE`**: Base para o gerenciamento de cookies, essencial em segurança e fundamentos web.
*   **`$_FILES`**: Utilizada para upload de arquivos.

### 65.2 Contexto de Uso no PHP 8.5

No desenvolvimento de **APIs REST** ou aplicações web modernas:

*   As superglobais são a base para capturar a entrada do usuário (Input Validation) e gerenciar o estado da aplicação.
*   Em frameworks ou arquiteturas modernas (como MVC), é comum encapsular essas superglobais em classes de `Request` para facilitar testes e manutenção.

### 65.3 Validação de Superglobais contra SQL Injection

A validação de dados vindos de superglobais para prevenir **SQL Injection** não deve ser feita apenas "limpando" a string, mas sim alterando a forma como o banco de dados recebe esses dados.

**Regra de ouro:** Nunca concatene dados de superglobais diretamente em uma string SQL. A solução definitiva é o uso de **Prepared Statements** via **PDO**.

#### O Jeito Errado (Vulnerável)

```php
<?php

// ❌ PERIGO: Concatenação direta de superglobal
// Se $_GET['id'] for "1; DROP TABLE users;", o banco será apagado.
$sql = "SELECT * FROM users WHERE id = " . $_GET['id'];
$pdo->query($sql);
```

#### O Jeito Certo (PHP 8.5)

```php
<?php

declare(strict_types=1);

$dsn = 'mysql:host=localhost;dbname=meu_banco;charset=utf8mb4';
$options = [
    PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
    PDO::ATTR_EMULATE_PREPARES   => false,
];

try {
    $pdo = new PDO($dsn, 'user', 'pass', $options);

    $userId = $_GET['id'] ?? null;

    // Validação lógica
    if (!filter_var($userId, FILTER_VALIDATE_INT)) {
        throw new \InvalidArgumentException("ID inválido fornecido.");
    }

    // Prepared Statement com placeholder
    $stmt = $pdo->prepare("SELECT name, email FROM users WHERE id = :id");
    $stmt->execute(['id' => $userId]);

    $user = $stmt->fetch();

    if ($user) {
        // Prevenção de XSS ao exibir o dado
        echo "Usuário: " . htmlspecialchars($user['name'], ENT_QUOTES, 'UTF-8');
    }

} catch (\PDOException $e) {
    error_log($e->getMessage());
    echo "Erro interno no servidor.";
}
```

### 65.4 Por que não usar outras funções

*   **`PDO::quote()`**: Desencorajada. O manual é explícito: **NÃO RECOMENDADO — use `prepare()` ao invés**. Prepared statements são mais robustos e portáteis.
*   **`addslashes()` ou `str_replace()`**: Relíquias de versões antigas. Não protegem adequadamente contra todos os tipos de SQL Injection.
*   **`filter_var()`**: Excelente para **validar** formatos (email, inteiro), mas **não substitui** Prepared Statements para segurança do banco.

### 65.5 Defesa em Profundidade

1.  **Validação (Input):** Garante que o dado é do **tipo** correto.
    *   Exemplo: `filter_var($_POST['email'], FILTER_VALIDATE_EMAIL)`
2.  **Parametrização (SQL):** Garante que o dado não altere a **lógica** da query.
    *   Exemplo: `PDOStatement::execute(['id' => $userId])`
3.  **Sanitização (Output):** Garante que dados maliciosos não executem scripts no navegador.
    *   Exemplo: `htmlspecialchars()` ao exibir dados vindos do banco.

### 65.6 Regras para PHP 8.5

1.  **Nunca** confie em `$_POST`, `$_GET`, `$_COOKIE` ou `$_REQUEST`.
2.  **Sempre** use `PDO::prepare()` com placeholders (`:nome` ou `?`).
3.  **Sempre** configure o PDO para lançar exceções (`PDO::ERRMODE_EXCEPTION`).


---

## 66. Expressões Regulares (PCRE) — Guia Completo

Este capítulo detalha cada função `preg_*` do PHP com exemplos práticos: `preg_match`, `preg_match_all`, `preg_replace`, `preg_split` e `preg_grep`. Inclui sintaxe fundamental (metacaracteres, quantificadores, classes, grupos) e boas práticas para PHP 8.5.

O PHP utiliza nativamente o padrão **PCRE** (Perl Compatible Regular Expressions) através das funções `preg_*`.

### 66.1 Sintaxe Fundamental

Em PHP, uma expressão regular deve ser delimitada (geralmente por `/`), por exemplo: `/padrão/`.

#### Metacaracteres e Âncoras

*   `^` : Início da string (ou linha, com modificador `m`).
*   `$` : Fim da string (ou linha).
*   `.` : Qualquer caractere (exceto nova linha).
*   `|` : OU lógico (ex: `a|b` encontra "a" ou "b").
*   `\` : Escape (para tratar caracteres especiais como literais, ex: `\.`).

#### Quantificadores

Definem quantas vezes o elemento anterior deve aparecer.

*   `*` : 0 ou mais vezes.
*   `+` : 1 ou mais vezes.
*   `?` : 0 ou 1 vez (opcional).
*   `{n}` : Exatamente *n* vezes.
*   `{n,}` : Pelo menos *n* vezes.
*   `{n,m}` : Entre *n* e *m* vezes.

#### Classes de Caracteres

*   `[abc]` : Qualquer um dos caracteres listados.
*   `[^abc]` : Qualquer caractere **exceto** os listados (negação).
*   `[a-z]` : Intervalo (de 'a' até 'z').
*   `\d` : Qualquer dígito (equivalente a `[0-9]`).
*   `\w` : Qualquer caractere de palavra (letras, números e sublinhado).
*   `\s` : Qualquer espaço em branco (espaço, tab, quebra de linha).

#### Grupos e Captura

*   `( ... )` : Agrupa e captura o valor para uso posterior (`$1`, `$2`).
*   `(?: ... )` : Agrupa, mas **não** captura (grupo de não-captura).

#### Exemplo: Validando Data

```php
<?php

declare(strict_types=1);

$data = "25/12/2025";
$regex = '/^(\d{2})\/(\d{2})\/(\d{4})$/';

if (preg_match($regex, $data, $matches)) {
    echo "Dia: " . $matches[1]; // 25
    echo "Mês: " . $matches[2]; // 12
    echo "Ano: " . $matches[3]; // 2025
}
```

### 66.2 `preg_match()` — Primeira Correspondência

Verifica se um padrão existe na string. Para após a primeira correspondência.

*   **Retorno:** `1` se encontrou, `0` se não, `false` em caso de erro.
*   **Uso:** Validação de formatos (CPF, Telefone, CEP).

```php
<?php

declare(strict_types=1);

function validateProductCode(string $code): bool
{
    // Padrão: 3 letras maiúsculas + 4 números (ex: ABC1234)
    $pattern = '/^[A-Z]{3}\d{4}$/';

    return preg_match($pattern, $code) === 1;
}

$input = 'PRO8050';
if (validateProductCode($input)) {
    echo "Código de produto válido.";
}
```

### 66.3 `preg_match_all()` — Todas as Correspondências

Encontra **todas** as ocorrências no texto.

*   **Retorno:** O número de correspondências (pode ser 0).
*   **Uso:** Extração de dados (hashtags, emails, links).

```php
<?php

declare(strict_types=1);

function extractEmails(string $text): array
{
    $pattern = '/[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}/i';
    $matches = [];

    $count = preg_match_all($pattern, $text, $matches);

    return $count > 0 ? $matches[0] : [];
}

$content = "Entre em contato via suporte@empresa.com ou vendas@empresa.com.";
$emails = extractEmails($content);
// ['suporte@empresa.com', 'vendas@empresa.com']
```

### 66.4 `preg_replace()` — Busca e Substituição

Realiza substituição baseada em regex. Mais poderoso que `str_replace`.

*   **Retorno:** Nova string com as substituições.
*   **Uso:** Sanitização, formatação de máscaras, remoção de caracteres.

```php
<?php

declare(strict_types=1);

function formatDateToIso(string $dateBr): ?string
{
    // Transforma dd/mm/aaaa para aaaa-mm-dd
    $pattern = '/^(\d{2})\/(\d{2})\/(\d{4})$/';
    $replacement = '$3-$2-$1';

    $result = preg_replace($pattern, $replacement, $dateBr);

    return is_string($result) ? $result : null;
}

echo formatDateToIso('25/12/2025'); // 2025-12-25
```

### 66.5 `preg_split()` — Divisão por Padrão

Divide uma string em array usando regex como delimitador. Superior ao `explode` quando o delimitador é variável.

*   **Retorno:** Array contendo as substrings.
*   **Uso:** Quebrar tags, palavras-chave ou frases com separadores variáveis.

```php
<?php

declare(strict_types=1);

function parseTags(string $input): array
{
    // Divide por vírgula, ponto e vírgula ou pipe, com espaços opcionais
    $pattern = '/\s*[,;|]\s*/';

    return preg_split($pattern, $input, -1, PREG_SPLIT_NO_EMPTY) ?: [];
}

$rawTags = "php;  laravel, codeigniter | zend";
$tags = parseTags($rawTags);
// ['php', 'laravel', 'codeigniter', 'zend']
```

### 66.6 `preg_grep()` — Filtro de Array

Filtra um array retornando apenas elementos que correspondem ao padrão. Funciona como `array_filter` otimizado para regex.

*   **Retorno:** Array com os valores que deram match.
*   **Uso:** Filtrar listas de arquivos, validar arrays de inputs.

```php
<?php

declare(strict_types=1);

function filterImageFiles(array $files): array
{
    $pattern = '/\.(jpg|png|webp)$/i';

    return preg_grep($pattern, $files);
}

$fileList = ['image.jpg', 'script.php', 'logo.PNG', 'styles.css', 'banner.webp'];
$images = filterImageFiles($fileList);
// ['image.jpg', 'logo.PNG', 'banner.webp']
// Nota: preg_grep mantém as chaves originais do array
```

### 66.7 Boas Práticas no PHP 8.5

1.  **Segurança:** Evite criar regex baseadas em input do usuário sem tratamento — risco de ReDoS (Regular Expression Denial of Service).
2.  **Performance:** Para verificações simples (conter/iniciar/terminar), use `str_contains()`, `str_starts_with()` ou `str_ends_with()`, que são mais rápidas que `preg_match`.
3.  **Descontinuações:** Passar `null` para funções `preg_*` gera Deprecation Warnings. Sempre garanta que o input seja `string`.
4.  **PHP 8.5:** As funções `preg_*` continuam como padrão ouro para manipulação complexa de strings. Complementam novidades como `grapheme_levenshtein()`.


---

## 67. Namespaces e Autoloading PSR-4 Detalhado

Namespaces organizam classes em hierarquias lógicas (`App\Service`, `App\Controller`), e PSR-4 mapeia essas hierarquias a diretórios físicos. Este capítulo cobre declaração, importação com `use`, aliases, namespace global e implementação completa de autoloader.

### 67.1 O que são Namespaces

**Namespaces** (Espaços de Nomes) são uma forma de encapsular classes, interfaces, funções e constantes. Eles resolvem dois problemas principais:

1.  **Conflitos de nomes:** Permitem classes com o mesmo nome em partes diferentes do sistema, desde que em namespaces diferentes.
2.  **Organização:** Agrupam o código de forma lógica e estruturada (ex: `App\Model`, `App\Controller`).

Pense neles como **pastas no sistema operacional**. Dois arquivos não podem ter o nome `Relatorio.txt` na mesma pasta, mas podem coexistir em pastas diferentes.

### 67.2 Declaração

A declaração do namespace deve ser a **primeira linha** de código PHP (após `<?php` e `declare`).

```php
<?php

declare(strict_types=1);

namespace App\Service;

class PaymentProcessor
{
    public function process(): void
    {
        echo "Processando pagamento...";
    }
}
```

### 67.3 Importação com `use`

Quando você usa uma classe de outro namespace, importe-a com `use` para evitar nomes longos:

```php
<?php

declare(strict_types=1);

namespace App\Controller;

use App\Service\PaymentProcessor;

class CheckoutController
{
    public function checkout(): void
    {
        $processor = new PaymentProcessor();
        $processor->process();
    }
}
```

#### Aliases (Apelidos)

Para duas classes com o mesmo nome vindas de namespaces diferentes:

```php
<?php

declare(strict_types=1);

namespace App\Service;

use App\Logger\FileLogger;
use External\Lib\Logger as ThirdPartyLogger;

class LogService
{
    public function __construct(
        private FileLogger $localLogger,
        private ThirdPartyLogger $externalLogger,
    ) {}
}
```

### 67.4 O Namespace Global

Classes nativas do PHP (`DateTime`, `Exception`, `PDO`) residem no **Namespace Global** (a raiz).

Dentro de um namespace, use a barra invertida `\` para indicar a raiz, ou importe a classe:

```php
<?php

declare(strict_types=1);

namespace App\Service;

class Clock
{
    public function getCurrentTime(): string
    {
        // A barra invertida indica o namespace global
        $date = new \DateTime();
        return $date->format('H:i:s');
    }
}
```

### 67.5 PSR-4: Namespace = Caminho do Arquivo

A **PSR-4** define que o namespace da classe corresponde ao caminho do arquivo físico:

*   **Namespace:** `App\Service\User`
*   **Caminho:** `src/Service/User.php`

**Estrutura:**

```text
projeto/
├── src/
│   ├── Controller/
│   │   └── UserController.php  (Namespace: App\Controller)
│   └── Service/
│       └── EmailService.php    (Namespace: App\Service)
├── public/
│   └── index.php
└── autoload.php
```

### 67.6 Autoloader Manual com Função Reutilizável

Esta função registra um autoloader compatível com PSR-4, aceitando prefixo de namespace e diretório base como parâmetros:
```php
<?php

declare(strict_types=1);

/**
 * Registra um autoloader compatível com PSR-4.
 *
 * @param string $prefix  Prefixo do namespace (ex: 'App\\')
 * @param string $baseDir Diretório base (ex: __DIR__ . '/src/')
 */
function register_psr4_autoloader(string $prefix, string $baseDir): void
{
    $baseDir = rtrim($baseDir, DIRECTORY_SEPARATOR) . DIRECTORY_SEPARATOR;

    spl_autoload_register(function (string $class) use ($prefix, $baseDir): void {
        // Verifica se a classe usa o prefixo gerenciado
        $len = strlen($prefix);
        if (strncmp($prefix, $class, $len) !== 0) {
            return;
        }

        // Remove o prefixo para pegar o caminho relativo
        // App\Service\EmailService -> Service\EmailService
        $relativeClass = substr($class, $len);

        // Substitui \ por / e adiciona .php
        // Service\EmailService -> Service/EmailService.php
        $file = $baseDir . str_replace('\\', DIRECTORY_SEPARATOR, $relativeClass) . '.php';

        if (file_exists($file)) {
            require $file;
        }
    });
}

// Registra: 'App\' -> pasta 'src/'
register_psr4_autoloader('App\\', __DIR__ . '/src/');
```

### 67.7 Classe de Teste

Crie `src/Service/EmailService.php` para verificar que o autoloader encontra a classe corretamente:
```php
<?php

declare(strict_types=1);

namespace App\Service;

class EmailService
{
    public function send(string $message): string
    {
        return "Enviando e-mail: {$message}";
    }
}
```

### 67.8 Ponto de Entrada

O arquivo `public/index.php` carrega o autoloader e usa as classes com `use` — sem `require` manual:
```php
<?php

declare(strict_types=1);

require_once __DIR__ . '/../autoload.php';

use App\Service\EmailService;

// O PHP encontra src/Service/EmailService.php automaticamente
$emailService = new EmailService();
echo $emailService->send('Olá, Autoload PSR-4!');
```

### 67.9 Boas Práticas de Namespaces

1.  **Um por arquivo:** Declare apenas um namespace por arquivo.
2.  **PSR-4:** Alinhe namespaces com a estrutura de pastas.
3.  **Imports:** Sempre importe classes externas no topo do arquivo com `use`.
4.  **Classes Nativas:** Importe-as (`use Exception;`) ou use `\Exception` para clareza.


---

## 68. Orientação a Objetos — Fundamentos no PHP 8.5

Este capítulo ensina OOP do zero com as ferramentas do PHP 8.5: constructor promotion, visibilidade assimétrica, `readonly`, `#[\NoDiscard]` e `clone with`. Cobre os 4 pilares (encapsulamento, abstração, herança, polimorfismo) com boas práticas PSR-12.

### 68.1 O Conceito Fundamental

A OOP organiza o código em "objetos" que contêm **dados** (propriedades) e **comportamentos** (métodos).

*   **Classe:** É a planta ou o molde (ex: `Product`).
*   **Objeto:** É a instância concreta criada a partir do molde (ex: um iPhone específico).

### 68.2 Estrutura Moderna (PHP 8.5)

No PHP 8.5, usamos **Constructor Property Promotion** para reduzir código repetitivo.

```php
<?php

declare(strict_types=1);

namespace Domain\Entity;

class Product
{
    /**
     * Visibilidade assimétrica (PHP 8.4+):
     * 'public' para leitura, 'private' para escrita.
     */
    public private(set) float $price;

    public function __construct(
        public readonly string $name,
        float $price,
        public int $stock = 0,
    ) {
        $this->ensurePriceIsPositive($price);
        $this->price = $price;
    }

    public function applyDiscount(float $percentage): void
    {
        $discount = $this->price * ($percentage / 100);
        $newPrice = $this->price - $discount;

        $this->ensurePriceIsPositive($newPrice);
        $this->price = $newPrice;
    }

    private function ensurePriceIsPositive(float $amount): void
    {
        if ($amount < 0) {
            throw new \InvalidArgumentException('Price cannot be negative.');
        }
    }
}

// Instanciação
$laptop = new Product(
    name: 'MacBook Pro',
    price: 2500.00,
    stock: 5,
);

echo $laptop->name;  // ✅ Leitura pública
// $laptop->price = 10; // ❌ Erro: escrita é privada

$laptop->applyDiscount(10);
```

### 68.3 Os 4 Pilares da OOP

#### A. Encapsulamento

Protege os dados internos do objeto. Em vez de deixar tudo `public`, controlamos o acesso.

*   **Legacy:** Métodos `getPrice()` e `setPrice()`.
*   **PHP 8.5:** **Visibilidade Assimétrica** (`public private(set)`) ou **Property Hooks**.

#### B. Abstração e Interfaces

Interfaces definem um "contrato" que as classes devem seguir.

```php
<?php

declare(strict_types=1);

interface PaymentGatewayInterface
{
    public function charge(float $amount): bool;
}

class StripePayment implements PaymentGatewayInterface
{
    public function charge(float $amount): bool
    {
        // Lógica específica do Stripe
        return true;
    }
}
```

#### C. Herança

Permite que uma classe herde características de outra (`extends`).

*   Prefira **Composição** (ter um objeto dentro do outro) em vez de herança profunda.
*   Use `#[\Override]` em métodos herdados para garantir sobrescrita correta.

#### D. Polimorfismo

Objetos diferentes respondem à mesma mensagem. Se várias classes implementam `PaymentGatewayInterface`, seu código pode usar qualquer uma sem saber qual é especificamente.

### 68.4 Novidades do PHP 8.5 para OOP

#### Clone With (Imutabilidade)

```php
<?php

declare(strict_types=1);

// Clona o objeto alterando apenas o preço
$newLaptop = clone($laptop, ['price' => 2000.00]);
```

#### Atributo `#[\NoDiscard]`

```php
<?php

declare(strict_types=1);

class StringHelper
{
    #[\NoDiscard]
    public function toUpperCase(string $input): string
    {
        return strtoupper($input);
    }
}

$helper = new StringHelper();
$helper->toUpperCase('test'); // ❌ PHP 8.5 emitirá aviso (valor descartado)
```

### 68.5 Boas Práticas (PSR-12 / PER-CS)

1.  **Tipagem Estrita:** Sempre use `declare(strict_types=1);`.
2.  **Type Hints:** Sempre defina tipos dos argumentos e retorno (`: void`, `: string`).
3.  **Nomes:** Classes em `PascalCase` (ex: `UserRepository`), métodos e variáveis em `camelCase` (ex: `saveUser`).
4.  **Autoloading:** Uma classe por arquivo, use **Namespaces** seguindo a PSR-4.


---

## 69. Clone With e Value Objects — Imutabilidade no PHP 8.5

O `clone with` do PHP 8.5 permite clonar objetos `readonly` alterando propriedades específicas numa única expressão. Combinado com Value Objects (imutáveis por definição), elimina métodos `with*()` boilerplate e garante integridade dos dados.

### 69.1 A Sintaxe do Clone With

Em vez de `clone $obj`, agora usamos `clone()` como função, passando o objeto original e um array associativo com as propriedades a alterar.

```php
$novoObjeto = clone($objetoOriginal, ['nomeDaPropriedade' => $novoValor]);
```

### 69.2 Exemplo Prático: Produto Imutável

Com `readonly class`, todas as propriedades são imutáveis após construção. `clone with` cria cópias com modificações sem violar a imutabilidade:
```php
<?php

declare(strict_types=1);

readonly class Product
{
    public function __construct(
        public string $name,
        public float $price,
        public string $category,
    ) {}
}

// Criando o objeto original
$laptop = new Product(
    name: 'MacBook Air',
    price: 999.00,
    category: 'Electronics',
);

// PHP 8.5: Clonando e alterando APENAS o preço
$discountedLaptop = clone($laptop, ['price' => 899.00]);

echo $laptop->price;           // 999.00 (original intacto)
echo $discountedLaptop->price; // 899.00 (novo objeto)
echo $discountedLaptop->name;  // MacBook Air (mantido)
```

### 69.3 Por que Clone With é importante

1.  **Fim dos métodos `with...`:** Não é mais necessário poluir a classe com métodos manuais:
    ```php
    // ❌ LEGADO (Desnecessário no PHP 8.5)
    public function withNumber(string $newNumber): self
    {
        return new self($this->street, $newNumber, $this->city, ...);
    }
    ```
2.  **Segurança de Tipos:** O PHP verifica se as chaves existem na classe e se os tipos são compatíveis. Erros de digitação (ex: `'numbr'`) geram erro.
3.  **Código Limpo:** A classe foca apenas nos dados e regras de negócio.

### 69.4 Value Object com Clone With

**Value Objects** representam um valor (não uma identidade) e devem ser **imutáveis**. Se você precisa mudar uma propriedade, cria uma cópia com a informação corrigida.

```php
<?php

declare(strict_types=1);

namespace Domain\ValueObject;

/**
 * Value Objects devem ser imutáveis.
 * 'readonly' garante que ninguém altere as propriedades após a criação.
 */
final readonly class Address
{
    public function __construct(
        public string $street,
        public string $number,
        public string $city,
        public string $zipCode,
        public string $country = 'Brazil',
    ) {}

    public function toString(): string
    {
        return sprintf(
            '%s, %s - %s, %s',
            $this->street,
            $this->number,
            $this->city,
            $this->country,
        );
    }
}

// 1. Criamos o objeto original (Imutável)
$originalAddress = new Address(
    street: 'Paulista Avenue',
    number: '1000',
    city: 'São Paulo',
    zipCode: '01310-100',
);

echo "Original: " . $originalAddress->toString() . PHP_EOL;

// 2. A empresa mudou de número na mesma rua
$newAddress = clone($originalAddress, ['number' => '2500']);

echo "Novo:     " . $newAddress->toString() . PHP_EOL;

// 3. Mudança completa de cidade (múltiplas propriedades)
$branchAddress = clone($originalAddress, [
    'street'  => 'Copacabana Avenue',
    'number'  => '500',
    'city'    => 'Rio de Janeiro',
    'zipCode' => '22020-001',
]);

echo "Filial:   " . $branchAddress->toString() . PHP_EOL;

// Verificando que são objetos diferentes
var_dump($originalAddress === $newAddress); // bool(false)
```

### 69.5 Quando usar Clone With

| Cenário | Abordagem |
| :--- | :--- |
| Dados imutáveis (DTOs, Value Objects) | `readonly class` + `clone with` |
| Alteração de estado único | `clone($obj, ['prop' => valor])` |
| Alteração de múltiplos campos | `clone($obj, ['a' => 1, 'b' => 2])` |
| Objeto mutável comum | Altere diretamente (sem necessidade de clone) |


---

## 70. Projeto Prático — Sistema de Logística com PSR-4

Este projeto integra todos os conceitos: PSR-4 autoloading, namespaces, constructor promotion, visibilidade assimétrica, `readonly` Value Objects e separação Domain/Service. Calcula frete com base no peso e destino.

### 70.1 Estrutura de Pastas

```text
meu-projeto/
├── src/
│   ├── Domain/           # Entidades do negócio (Produto, Endereço)
│   ├── Service/          # Lógica do negócio (Calculadora de Frete)
│   └── Utils/            # Ferramentas úteis
├── public/
│   └── index.php         # Ponto de entrada
└── autoload.php          # Carregamento automático PSR-4
```

### 70.2 O Autoloader

Autoloader PSR-4 que mapeia `App\` para `src/`:
```php
<?php

declare(strict_types=1);

spl_autoload_register(function (string $class): void {
    $prefix   = 'App\\';
    $base_dir = __DIR__ . '/src/';

    $len = strlen($prefix);
    if (strncmp($prefix, $class, $len) !== 0) {
        return;
    }

    $relative_class = substr($class, $len);
    $file = $base_dir . str_replace('\\', '/', $relative_class) . '.php';

    if (file_exists($file)) {
        require $file;
    }
});
```

### 70.3 Classe Product

**Arquivo:** `src/Domain/Product.php`

```php
<?php

declare(strict_types=1);

namespace App\Domain;

class Product
{
    public function __construct(
        public readonly string $name,
        public private(set) float $price,
        public int $weightInGrams,
    ) {}
}
```

### 70.4 Classe Address (Value Object)

Value Object `readonly` para endereço — imutável após construção:
**Arquivo:** `src/Domain/Address.php`

```php
<?php

declare(strict_types=1);

namespace App\Domain;

readonly class Address
{
    public function __construct(
        public string $street,
        public string $city,
        public string $zipCode,
    ) {}

    public function getFullAddress(): string
    {
        return "{$this->street}, {$this->city} - CEP: {$this->zipCode}";
    }
}
```

### 70.5 Classe ShippingCalculator (Serviço)

**Arquivo:** `src/Service/ShippingCalculator.php`

```php
<?php

declare(strict_types=1);

namespace App\Service;

use App\Domain\Product;
use App\Domain\Address;

class ShippingCalculator
{
    private const PRICE_PER_KG = 15.50;

    public function calculate(Product $product, Address $destination): float
    {
        $weightInKg = $product->weightInGrams / 1000;
        $shippingCost = $weightInKg * self::PRICE_PER_KG;

        if ($destination->city === 'São Paulo') {
            $shippingCost += 5.00;
        }

        return $shippingCost;
    }
}
```

### 70.6 Ponto de Entrada

O `index.php` orquestra o fluxo montando objetos de domínio e delegando ao serviço:
**Arquivo:** `public/index.php`

```php
<?php

declare(strict_types=1);

require_once __DIR__ . '/../autoload.php';

use App\Domain\Product;
use App\Domain\Address;
use App\Service\ShippingCalculator;

try {
    $macbook = new Product(
        name: 'MacBook Pro M3',
        price: 12000.00,
        weightInGrams: 1500,
    );

    $myAddress = new Address(
        street: 'Av. Paulista, 1000',
        city: 'São Paulo',
        zipCode: '01310-100',
    );

    $calculator = new ShippingCalculator();
    $cost = $calculator->calculate($macbook, $myAddress);

    echo "Produto: {$macbook->name}" . PHP_EOL;
    echo "Destino: {$myAddress->getFullAddress()}" . PHP_EOL;
    echo "Frete: R$ " . number_format($cost, 2, ',', '.') . PHP_EOL;

} catch (\Throwable $e) {
    echo "Erro no sistema: " . $e->getMessage();
}
```

### 70.7 Como Rodar

```bash
php -S localhost:8000 -t public
```

### 70.8 Por que isso é profissional

1.  **PSR-4:** Seguimos o padrão mundial. Outro desenvolvedor saberá onde encontrar `App\Service\ShippingCalculator` (pasta `src/Service`).
2.  **Clean Code:** O `index.php` não tem lógica de classe, apenas orquestra o fluxo.
3.  **Encapsulamento e Tipagem:** Tipos estritos e modificadores de acesso modernos.


---

## 71. Value Objects com Validação — Fail Fast

Value Objects devem garantir sua própria integridade: se o dado está errado, o construtor lança exceção imediatamente ("Fail Fast"). Com `__clone()`, a validação também cobre `clone with`, impedindo cópias inválidas.

### 71.1 Validação no Construtor

Em Value Objects, a validação é crucial porque eles devem garantir sua própria integridade. Um objeto inválido (como um CEP com letras) não deve sequer existir.

Seguimos a regra **"Fail Fast"** — se o dado estiver errado, lançamos exceção imediatamente.

```php
<?php

declare(strict_types=1);

namespace App\Domain\ValueObject;

use InvalidArgumentException;

final readonly class Address
{
    private const CEP_PATTERN = '/^\d{5}-\d{3}$/';

    public function __construct(
        public string $street,
        public string $number,
        public string $city,
        public string $zipCode,
        public string $country = 'Brazil',
    ) {
        $this->ensureZipCodeIsValid($zipCode);
        $this->ensureNumberIsNotEmpty($number);
    }

    /**
     * Chamado APÓS o 'clone with' aplicar as mudanças.
     * Garante que clonagem com dados inválidos seja barrada.
     */
    public function __clone(): void
    {
        $this->ensureZipCodeIsValid($this->zipCode);
        $this->ensureNumberIsNotEmpty($this->number);
    }

    public function toString(): string
    {
        return sprintf(
            '%s, %s - %s, %s',
            $this->street,
            $this->number,
            $this->city,
            $this->zipCode,
        );
    }

    private function ensureZipCodeIsValid(string $zipCode): void
    {
        if (preg_match(self::CEP_PATTERN, $zipCode) !== 1) {
            throw new InvalidArgumentException(
                "O CEP '{$zipCode}' é inválido. Formato esperado: 99999-999.",
            );
        }
    }

    private function ensureNumberIsNotEmpty(string $number): void
    {
        if (trim($number) === '') {
            throw new InvalidArgumentException(
                "O número do endereço não pode ser vazio.",
            );
        }
    }
}
```

### 71.2 Testando a Validação

Testes demonstram que tanto a criação quanto a clonagem com dados inválidos são barradas:
```php
<?php

declare(strict_types=1);

try {
    // ❌ CEP errado (falta o hífen)
    $endereco = new Address(
        street: 'Rua A',
        number: '123',
        city: 'SP',
        zipCode: '01001000',
    );
} catch (InvalidArgumentException $e) {
    echo "Erro na criação: " . $e->getMessage() . PHP_EOL;
    // Saída: O CEP '01001000' é inválido...
}

// ✅ Endereço válido
$enderecoValido = new Address('Rua B', '10', 'SP', '01001-000');

try {
    // ❌ Clonagem com CEP inválido
    $enderecoClonado = clone($enderecoValido, ['zipCode' => 'ABCDE-123']);
} catch (InvalidArgumentException $e) {
    echo "Erro na clonagem: " . $e->getMessage() . PHP_EOL;
    // Saída: O CEP 'ABCDE-123' é inválido...
}
```

### 71.3 Pontos-chave

1.  **Regex Centralizada:** Constante `private const CEP_PATTERN` facilita manutenção.
2.  **Validação no `__clone`:** Como `clone with` não chama `__construct`, as validações devem estar também no `__clone()`.
3.  **Tipagem Estrita:** `string` nos argumentos já previne tipos incorretos.

Essa estrutura garante que **sempre** que você tiver uma instância de `Address`, ela contém dados confiáveis. Nunca será necessário verificar `$address->isValid()` externamente.


---

## 72. Value Object Dedicado — Classe ZipCode

Extrair a validação de CEP para uma classe dedicada (`ZipCode`) garante reutilização em qualquer entidade que precise de CEP. A classe implementa `Stringable` e oferece `toNumbers()` para integração com APIs e bancos.

### 72.1 Extraindo a Validação para uma Classe Própria

Transformar o `zipCode` em um Value Object dedicado garante que *qualquer* lugar que precise de um CEP use a mesma regra de validação.

**Arquivo:** `src/Domain/ValueObject/ZipCode.php`

```php
<?php

declare(strict_types=1);

namespace App\Domain\ValueObject;

use InvalidArgumentException;
use Stringable;

final readonly class ZipCode implements Stringable
{
    private const PATTERN = '/^\d{5}-\d{3}$/';

    public function __construct(
        public string $value,
    ) {
        $this->ensureIsValid($value);
    }

    private function ensureIsValid(string $value): void
    {
        if (preg_match(self::PATTERN, $value) !== 1) {
            throw new InvalidArgumentException(
                "O CEP '{$value}' é inválido. Formato esperado: 99999-999.",
            );
        }
    }

    /**
     * Remove o traço para APIs que pedem apenas números.
     */
    public function toNumbers(): string
    {
        return preg_replace('/\D/', '', $this->value);
    }

    public function __toString(): string
    {
        return $this->value;
    }
}
```

### 72.2 Refatorando a Classe Address

Agora `Address` não precisa saber como validar um CEP. Ela apenas declara que depende de um `ZipCode` válido.

**Arquivo:** `src/Domain/ValueObject/Address.php`

```php
<?php

declare(strict_types=1);

namespace App\Domain\ValueObject;

final readonly class Address
{
    public function __construct(
        public string $street,
        public string $number,
        public string $city,
        public ZipCode $zipCode,
        public string $country = 'Brazil',
    ) {}

    public function toString(): string
    {
        return sprintf(
            '%s, %s - %s, %s',
            $this->street,
            $this->number,
            $this->city,
            $this->zipCode,
        );
    }
}
```

### 72.3 Reutilização: Classe User

O mesmo `ZipCode` é reutilizado em qualquer entidade que precise de CEP:

```php
<?php

declare(strict_types=1);

namespace App\Domain\Entity;

use App\Domain\ValueObject\ZipCode;

class User
{
    public function __construct(
        public readonly string $name,
        public readonly string $email,
        public ?ZipCode $billingZipCode = null,
    ) {}
}
```

### 72.4 Demonstração com Clone With (PHP 8.5)

Exemplo completo demonstrando `ZipCode` isolado, composto em `Address`, reutilizado em `User` e clonado com `clone with`:
```php
<?php

declare(strict_types=1);

require_once __DIR__ . '/../autoload.php';

use App\Domain\ValueObject\ZipCode;
use App\Domain\ValueObject\Address;
use App\Domain\Entity\User;

try {
    // 1. CEP isolado (validado automaticamente)
    $cepPaulista = new ZipCode('01310-100');

    // 2. Usando no Endereço
    $enderecoEmpresa = new Address(
        street: 'Av. Paulista',
        number: '1000',
        city: 'São Paulo',
        zipCode: $cepPaulista,
    );

    echo "Endereço: " . $enderecoEmpresa->toString() . PHP_EOL;
    echo "Apenas números: " . $cepPaulista->toNumbers() . PHP_EOL;

    // 3. Reutilizando no Usuário
    $user = new User(
        name: 'Carlos Silva',
        email: 'carlos@example.com',
        billingZipCode: $cepPaulista,
    );

    echo "CEP Faturamento: " . $user->billingZipCode . PHP_EOL;

    // 4. Clone With em objetos aninhados
    $cepRio = new ZipCode('22020-001');

    $enderecoFilial = clone($enderecoEmpresa, [
        'zipCode' => $cepRio,
        'city'    => 'Rio de Janeiro',
        'street'  => 'Av. Atlântica',
    ]);

    echo "Original: " . $enderecoEmpresa->toString() . PHP_EOL;
    echo "Filial:   " . $enderecoFilial->toString() . PHP_EOL;

} catch (\InvalidArgumentException $e) {
    echo "Erro de Validação: " . $e->getMessage();
}
```

### 72.5 Benefícios

1.  **Type Safety:** `public ZipCode $zipCode` garante 100% que ali existe um CEP válido.
2.  **Manutenção Centralizada:** Se o formato mudar, altera-se apenas a classe `ZipCode`.
3.  **Código Expressivo:** `$cep->toNumbers()` é mais legível que `preg_replace` espalhado.


---

## 73. Persistência de Value Objects com PDO — Repository Pattern

Value Objects vivem no domínio como objetos ricos, mas o banco armazena escalares (strings, ints). O Repository faz a conversão (hidratação): `CHAR(8)` ↔ `ZipCode`. Este capítulo implementa o padrão completo com PDO puro.

### 73.1 Schema do Banco de Dados

Para CEPs salvos como números, use `CHAR(8)` (nunca `INT`, pois CEPs começam com zero):

```sql
CREATE TABLE addresses (
    id INT AUTO_INCREMENT PRIMARY KEY,
    street VARCHAR(255) NOT NULL,
    number VARCHAR(20) NOT NULL,
    city VARCHAR(100) NOT NULL,
    zip_code CHAR(8) NOT NULL
);
```

### 73.2 O Repositório (Hidratação)

O PDO retorna dados escalares (strings), mas o construtor `Address` exige um objeto `ZipCode`. A solução é buscar como array associativo e instanciar manualmente — isso é chamado de **hidratação**.

```php
<?php

declare(strict_types=1);

namespace App\Infrastructure\Repository;

use PDO;
use App\Domain\ValueObject\ZipCode;
use App\Domain\ValueObject\Address;
use InvalidArgumentException;

class AddressRepository
{
    public function __construct(
        private PDO $pdo,
    ) {}

    public function findById(int $id): ?Address
    {
        $sql = "SELECT street, number, city, zip_code FROM addresses WHERE id = :id";
        $stmt = $this->pdo->prepare($sql);
        $stmt->execute(['id' => $id]);

        $row = $stmt->fetch(PDO::FETCH_ASSOC);

        if ($row === false) {
            return null;
        }

        try {
            // Hidratação: converte string do banco em objeto ZipCode
            // Se o banco salva apenas números, formata antes de instanciar
            $rawZip = $row['zip_code'];
            $formattedZip = substr($rawZip, 0, 5) . '-' . substr($rawZip, 5, 3);

            return new Address(
                street: $row['street'],
                number: $row['number'],
                city: $row['city'],
                zipCode: new ZipCode($formattedZip),
            );
        } catch (InvalidArgumentException $e) {
            // Dados corrompidos/legados no banco
            throw $e;
        }
    }

    public function save(Address $address): void
    {
        $sql = "INSERT INTO addresses (street, number, city, zip_code)
                VALUES (:street, :number, :city, :zip)";

        $stmt = $this->pdo->prepare($sql);

        $stmt->execute([
            'street' => $address->street,
            'number' => $address->number,
            'city'   => $address->city,
            // Extrai apenas os números para o banco
            'zip'    => $address->zipCode->toNumbers(),
        ]);
    }
}
```

### 73.3 Uso no Código

Exemplo de recuperação do banco com tratamento de erros tanto de PDO quanto de validação:
```php
<?php

declare(strict_types=1);

use App\Infrastructure\Repository\AddressRepository;

try {
    $repo = new AddressRepository($pdo);

    // Carregando do banco
    $address = $repo->findById(1);

    if ($address) {
        echo "Cidade: " . $address->city . PHP_EOL;
        echo "CEP Formatado: " . $address->zipCode . PHP_EOL;
        echo "CEP Numérico: " . $address->zipCode->toNumbers() . PHP_EOL;
    }

} catch (\PDOException $e) {
    echo "Erro de Banco: " . $e->getMessage();
} catch (\InvalidArgumentException $e) {
    echo "Erro de Integridade: " . $e->getMessage();
}
```

### 73.4 Conversão Explícita vs Implícita

**Conversão Explícita (Recomendada):**

```php
<?php

declare(strict_types=1);

// Salvar formatado ("01310-100")
'zip' => (string) $address->zipCode,

// Salvar apenas números ("01310100")
'zip' => $address->zipCode->toNumbers(),
```

**Conversão Implícita (Stringable):**

```php
<?php

declare(strict_types=1);

// Funciona se ZipCode implementa __toString(), mas é menos explícito
'zip' => $address->zipCode,
```

### 73.5 Qual formato salvar no banco?

| Formato | Exemplo | Vantagem |
| :--- | :--- | :--- |
| **Formatado** | `01310-100` | Fácil de ler no banco, pronto para exibir |
| **Apenas números** | `01310100` | Menos espaço, facilita buscas sem traço |

### 73.6 Arquitetura de Camadas

| Camada | Formato | Exemplo | Responsabilidade |
| :--- | :--- | :--- | :--- |
| **Banco** | `CHAR(8)` | `01310100` | Armazenamento eficiente |
| **Repositório** | Conversor | `01310100` ↔ `01310-100` | Adaptar entre banco e domínio |
| **Domínio** | String validada | `01310-100` | Regras de negócio e formato visual |

### 73.7 Por que fazer assim

1.  **Integridade:** Nenhum `Address` existe com CEP inválido, mesmo vindo do banco (protege contra dados legados).
2.  **Desacoplamento:** A lógica SQL fica separada da lógica de negócio.
3.  **PDO Puro:** `fetch(PDO::FETCH_ASSOC)` é a maneira mais performática de hidratar objetos complexos sem ORMs pesados.


---

## 74. Sistema de Login Profissional — PHP 8.5

Este capítulo implementa um sistema de autenticação completo usando todas as ferramentas do PHP 8.5: `#[\NoDiscard]`, pipe operator, `clone with`, Property Hooks, `readonly` DTOs, Argon2id e sessões seguras.

### 74.1 Recursos PHP 8.5+ Utilizados

1.  **`#[\NoDiscard]`** — Garante que o resultado da autenticação não seja ignorado.
2.  **Pipe Operator `|>`** — Sanitização fluida de dados de entrada.
3.  **Clone with** — Atualização de objetos imutáveis (`readonly`).
4.  **Property Hooks (PHP 8.4)** — Validação automática de propriedades.
5.  **Readonly Classes (PHP 8.2)** — DTOs seguros.
6.  **Constructor Property Promotion** — Redução de boilerplate.

### 74.2 Banco de Dados (MySQL)

Schema com `utf8mb4` para suporte completo a Unicode e `UNIQUE` no email:
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    email VARCHAR(255) NOT NULL UNIQUE,
    password_hash VARCHAR(255) NOT NULL,
    full_name VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    last_login TIMESTAMP NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

### 74.3 Entidade User

Classe `readonly` com Property Hook para normalizar o e-mail automaticamente.

```php
<?php

declare(strict_types=1);

namespace App\Domain;

use DateTimeImmutable;

readonly class User
{
    public function __construct(
        public int $id,
        public string $email {
            // Property Hook (PHP 8.4): Normaliza ao definir
            set => strtolower($value);
        },
        public string $passwordHash,
        public string $fullName,
        public DateTimeImmutable $createdAt,
        public ?DateTimeImmutable $lastLogin = null,
    ) {}
}
```

### 74.4 Conexão PDO

Factory estática com as três regras de ouro: `ERRMODE_EXCEPTION`, `FETCH_ASSOC`, `EMULATE_PREPARES = false`:
```php
<?php

declare(strict_types=1);

namespace App\Infrastructure;

use PDO;

class DatabaseConnection
{
    public static function get(): PDO
    {
        $dsn  = 'mysql:host=localhost;dbname=meu_sistema;charset=utf8mb4';
        $user = 'db_user';
        $pass = 'db_pass_segura';

        return new PDO($dsn, $user, $pass, [
            PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
            PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
            PDO::ATTR_EMULATE_PREPARES   => false,
        ]);
    }
}
```

### 74.5 UserRepository

Hidratação de `User` a partir do array PDO, com conversão de timestamps para `DateTimeImmutable`:
```php
<?php

declare(strict_types=1);

namespace App\Repository;

use App\Domain\User;
use App\Infrastructure\DatabaseConnection;
use PDO;
use DateTimeImmutable;

class UserRepository
{
    private PDO $pdo;

    public function __construct()
    {
        $this->pdo = DatabaseConnection::get();
    }

    public function findByEmail(string $email): ?User
    {
        $stmt = $this->pdo->prepare("SELECT * FROM users WHERE email = :email");
        $stmt->execute(['email' => $email]);

        $data = $stmt->fetch();

        if (!$data) {
            return null;
        }

        return new User(
            id: (int) $data['id'],
            email: $data['email'],
            passwordHash: $data['password_hash'],
            fullName: $data['full_name'],
            createdAt: new DateTimeImmutable($data['created_at']),
            lastLogin: $data['last_login']
                ? new DateTimeImmutable($data['last_login'])
                : null,
        );
    }

    public function updateLastLogin(User $user): void
    {
        $stmt = $this->pdo->prepare("UPDATE users SET last_login = NOW() WHERE id = :id");
        $stmt->execute(['id' => $user->id]);
    }
}
```

### 74.6 AuthService (Coração da Lógica)

Fluxo completo: sanitização com pipe, busca, verificação time-constant, rehash, `clone with` e sessão segura:
```php
<?php

declare(strict_types=1);

namespace App\Service;

use App\Domain\User;
use App\Repository\UserRepository;
use Exception;

class AuthService
{
    public function __construct(
        private UserRepository $userRepository,
    ) {}

    /**
     * #[\NoDiscard] (PHP 8.5) emite aviso se o retorno for ignorado.
     */
    #[\NoDiscard]
    public function login(string $email, string $password): User
    {
        // 1. Sanitização com Pipe Operator (PHP 8.5)
        $cleanEmail = $email
            |> trim(...)
            |> fn($v) => filter_var($v, FILTER_SANITIZE_EMAIL);

        if (!$cleanEmail) {
            throw new Exception('Formato de e-mail inválido.');
        }

        // 2. Busca o usuário
        $user = $this->userRepository->findByEmail($cleanEmail);

        // 3. Verificação de senha (Time-Constant)
        if (!$user || !password_verify($password, $user->passwordHash)) {
            throw new Exception('Credenciais inválidas.');
        }

        // 4. Verificação de Rehash
        if (password_needs_rehash($user->passwordHash, PASSWORD_ARGON2ID)) {
            // Atualizar hash no banco (ver capítulo 76)
        }

        // 5. Clone With (PHP 8.5) — atualiza objeto imutável
        $updatedUser = clone $user with [
            'lastLogin' => new \DateTimeImmutable(),
        ];

        $this->userRepository->updateLastLogin($updatedUser);

        // 6. Sessão segura
        $this->startSecureSession($updatedUser);

        return $updatedUser;
    }

    private function startSecureSession(User $user): void
    {
        if (session_status() === PHP_SESSION_NONE) {
            session_set_cookie_params([
                'lifetime' => 0,
                'path'     => '/',
                'domain'   => 'seusite.com',
                'secure'   => true,
                'httponly'  => true,
                'samesite'  => 'Strict',
            ]);
            session_start();
        }

        session_regenerate_id(true);

        $_SESSION['user_id']    = $user->id;
        $_SESSION['user_agent'] = $_SERVER['HTTP_USER_AGENT'] ?? '';
        $_SESSION['ip_address'] = $_SERVER['REMOTE_ADDR'] ?? '';
    }
}
```

### 74.7 Controller de Login

Ponto de entrada HTTP que captura `$_POST`, delega ao `AuthService` e exibe resultado com `htmlspecialchars`:
```php
<?php

declare(strict_types=1);

require 'vendor/autoload.php';

use App\Service\AuthService;
use App\Repository\UserRepository;

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    try {
        $authService = new AuthService(new UserRepository());

        $email    = $_POST['email'] ?? '';
        $password = $_POST['password'] ?? '';

        $user = $authService->login($email, $password);

        echo "Bem-vindo, " . htmlspecialchars($user->fullName);

    } catch (Exception $e) {
        error_log($e->getMessage());
        echo "Erro no login: " . $e->getMessage();
    }
}
```

### 74.8 Resumo de Segurança

1.  **Hash:** `PASSWORD_ARGON2ID` ao criar usuários com `password_hash()`.
2.  **Prepared Statements:** `prepare()` + `execute()` elimina SQL Injection.
3.  **Session Fixation:** `session_regenerate_id(true)` após login.
4.  **XSS:** `HttpOnly` no cookie impede JavaScript de roubar a sessão.
5.  **CSRF:** `SameSite=Strict` previne envio de cookies em requisições externas.
6.  **Erros:** Nunca exiba detalhes de banco ao usuário.

---

## 75. Rehash de Senhas com Argon2id

O rehash atualiza hashes antigos (bcrypt, MD5 legado) para Argon2id transparentemente durante o login. `password_needs_rehash()` detecta quando o algoritmo ou custo mudou, e `password_hash()` gera o novo hash sem que o usuário perceba.

### 75.1 Por que Rehash

O rehash mantém seu sistema atualizado com padrões criptográficos sem forçar usuários a redefinirem senhas. É feito transparentemente durante o login.

### 75.2 Implementação no AuthService

O método `login()` verifica `password_needs_rehash()` após a autenticação e atualiza o hash no banco com `clone with`:
```php
<?php

declare(strict_types=1);

namespace App\Service;

use App\Domain\User;
use App\Repository\UserRepository;
use Exception;

class AuthService
{
    // Ajuste conforme seu hardware
    private const HASH_OPTIONS = [
        'memory_cost' => 65536, // 64MB
        'time_cost'   => 4,     // 4 iterações
        'threads'     => 1,
    ];

    public function __construct(
        private UserRepository $userRepository,
    ) {}

    #[\NoDiscard]
    public function login(string $email, string $password): User
    {
        $user = $this->userRepository->findByEmail($email);

        if (!$user || !password_verify($password, $user->passwordHash)) {
            throw new Exception('Credenciais inválidas.');
        }

        // Rehash: verifica se o hash precisa ser atualizado
        if (password_needs_rehash($user->passwordHash, PASSWORD_ARGON2ID, self::HASH_OPTIONS)) {
            $newHash = password_hash($password, PASSWORD_ARGON2ID, self::HASH_OPTIONS);

            $this->userRepository->updatePassword($user->id, $newHash);

            // Clone With (PHP 8.5) — atualiza o objeto em memória
            $user = clone $user with [
                'passwordHash' => $newHash,
            ];
        }

        return $user;
    }
}
```

### 75.3 Método updatePassword no Repositório

Prepared statement dedicado para atualizar apenas o hash, sem expor a senha:
```php
<?php

declare(strict_types=1);

namespace App\Repository;

class UserRepository
{
    // ... outros métodos ...

    public function updatePassword(int $userId, string $newHash): void
    {
        $stmt = $this->pdo->prepare(
            "UPDATE users SET password_hash = :hash WHERE id = :id",
        );

        $stmt->execute([
            'hash' => $newHash,
            'id'   => $userId,
        ]);
    }
}
```

### 75.4 Opções do Argon2id

| Opção | Descrição | Valor Recomendado |
| :--- | :--- | :--- |
| `memory_cost` | Memória em KiB | `65536` (64MB) |
| `time_cost` | Número de iterações | `4` |
| `threads` | Threads paralelas | `1` (para web) |

### 75.5 Vantagens

1.  **Evolução:** Se o hardware melhorar, aumente `memory_cost` ou `time_cost`. O `password_needs_rehash` detecta que o hash antigo tem custo menor e atualiza no próximo login.
2.  **Transparência:** O usuário nunca percebe — para ele é um login normal.
3.  **Migração:** Permite migrar gradualmente de Bcrypt ou MD5 legado para Argon2id sem interrupções.

---

## 76. Proteção contra Session Hijacking

Session Hijacking ocorre quando um atacante rouba o cookie de sessão e se faz passar pelo usuário. Este capítulo implementa proteção em camadas: cookies blindados (Secure, HttpOnly, SameSite), fingerprinting por User-Agent e rotação periódica do session ID.

### 76.1 Configuração de Cookies Blindados

Defina todos os flags de segurança antes de `session_start()`:
```php
<?php

declare(strict_types=1);

session_set_cookie_params([
    'lifetime' => 0,           // Expira ao fechar o navegador
    'path'     => '/',
    'domain'   => 'seusite.com',
    'secure'   => true,        // Apenas HTTPS (previne sniffing)
    'httponly'  => true,        // Bloqueia JavaScript (previne XSS)
    'samesite'  => 'Strict',   // Previne CSRF
]);
```

### 76.2 Classe SessionSecurity

Esta classe encapsula fingerprinting, validação e rotação automática do session ID a cada 30 minutos:
```php
<?php

declare(strict_types=1);

namespace App\Security;

class SessionSecurity
{
    /**
     * Inicia a sessão com configurações seguras e valida o cliente.
     */
    #[\NoDiscard]
    public static function startAndValidate(): bool
    {
        if (session_status() === PHP_SESSION_NONE) {
            session_set_cookie_params([
                'lifetime' => 0,
                'path'     => '/',
                'secure'   => true,
                'httponly'  => true,
                'samesite'  => 'Strict',
            ]);
            session_start();
        }

        // Sessão nova: cria fingerprint
        if (!isset($_SESSION['fingerprint'])) {
            static::createFingerprint();
            return true;
        }

        // Sessão existente: valida fingerprint
        if (!static::validateFingerprint()) {
            session_destroy();
            return false;
        }

        // Rotação periódica do ID
        static::rotateSessionPeriodic();

        return true;
    }

    private static function createFingerprint(): void
    {
        $_SESSION['fingerprint'] = hash(
            'sha256',
            $_SERVER['HTTP_USER_AGENT'] ?? 'unknown',
        );
        $_SESSION['last_regeneration'] = time();
    }

    private static function validateFingerprint(): bool
    {
        $current = hash('sha256', $_SERVER['HTTP_USER_AGENT'] ?? 'unknown');

        return hash_equals($_SESSION['fingerprint'], $current);
    }

    private static function rotateSessionPeriodic(): void
    {
        // Rotaciona o ID a cada 30 minutos
        $interval = 30 * 60;

        if (time() - ($_SESSION['last_regeneration'] ?? 0) > $interval) {
            session_regenerate_id(true);
            $_SESSION['last_regeneration'] = time();
        }
    }
}
```

### 76.3 Integração

No início de cada página protegida, valide a sessão e redirecione se comprometida:
```php
<?php

declare(strict_types=1);

use App\Security\SessionSecurity;

if (!SessionSecurity::startAndValidate()) {
    header('Location: /login.php?error=session_compromised');
    exit;
}

// ... Resto da aplicação ...
```

### 76.4 Camadas de Proteção

| Camada | Ataque Prevenido | Mecanismo |
| :--- | :--- | :--- |
| HTTPS + Secure Flag | Sniffing na rede | Cookie só trafega em HTTPS |
| HttpOnly Flag | XSS rouba cookie | JavaScript não acessa o cookie |
| `session_regenerate_id(true)` | Session Fixation | Novo ID após login |
| Fingerprint (User-Agent) | Session Hijacking | Valida navegador do cliente |
| SameSite=Strict | CSRF | Cookie não enviado em requisições externas |

**Nota:** Vincular ao IP (`$_SERVER['REMOTE_ADDR']`) é seguro, mas pode desconectar usuários em redes móveis onde o IP muda frequentemente. Recomenda-se usar apenas User-Agent para a maioria das aplicações.


---

## 77. Argon2i vs Argon2id — Comparativo Técnico

Argon2 é a família de algoritmos vencedora do Password Hashing Competition. PHP suporta `PASSWORD_ARGON2I` (anti side-channel) e `PASSWORD_ARGON2ID` (híbrido, recomendado). Este capítulo explica quando usar cada um.

### 77.1 Argon2i (Otimizado contra Side-Channel Attacks)

Usa acesso à memória independente dos dados.

*   **Como funciona:** A ordem de acesso à memória é pré-determinada e não depende da senha.
*   **Previne:** Ataques de canal lateral (side-channel), como timing attacks.
*   **Ponto fraco:** Ligeiramente menos resistente a força bruta com GPUs/FPGAs.

### 77.2 Argon2id (Híbrido — Recomendado)

Combina Argon2i e Argon2d em duas fases.

*   **Como funciona:** Primeira metade das iterações como Argon2i (independente dos dados), restante como Argon2d (dependente dos dados).
*   **Previne:** Side-channel attacks (fases iniciais) + GPU cracking (fases finais).

### 77.3 Tabela Comparativa

| Característica | Argon2i (`PASSWORD_ARGON2I`) | Argon2id (`PASSWORD_ARGON2ID`) |
| :--- | :--- | :--- |
| **Foco** | Side-Channel Attacks | Híbrido (Side-Channel + GPU) |
| **Acesso à Memória** | Independente dos dados | Misto (previsível no início, dependente depois) |
| **Uso Recomendado** | Apenas se side-channel é risco exclusivo | **Padrão para Web/Login** |
| **Resistência GPU** | Alta, mas menor que Argon2id | Muito Alta |

### 77.4 Por que Argon2id no PHP 8.5

1.  **Risco real:** Atacante obtém dump do banco e tenta quebrar senhas offline com GPUs. Argon2id resiste fortemente.
2.  **Risco menor:** Side-channel (monitorar hardware em tempo real) é raro em apps web. Argon2id mantém proteção suficiente.

```php
<?php

declare(strict_types=1);

// Recomendado: Híbrido
$hash = password_hash($senha, PASSWORD_ARGON2ID, ['memory_cost' => 65536]);

// Alternativa: Apenas se side-channel for preocupação exclusiva
$hash = password_hash($senha, PASSWORD_ARGON2I, ['memory_cost' => 65536]);
```

---

## 78. Pipe Operator (`|>`) para Sanitização de Inputs

O operador pipe transforma a sanitização de inputs num pipeline linear e auditável: cada função recebe o resultado da anterior, eliminando aninhamento e reatribuição de variáveis.

### 78.1 Sanitização de E-mail

Exemplo clássico de pipeline: trim → lowercase → filter_var:
```php
<?php

declare(strict_types=1);

$rawInput = '  USUARIO@Exemplo.com  ';

// ❌ Antes (aninhado, difícil de ler)
// $email = filter_var(strtolower(trim($input)), FILTER_SANITIZE_EMAIL);

// ✅ PHP 8.5 (Pipe Operator)
$cleanEmail = $rawInput
    |> trim(...)                              // 1. Remove espaços
    |> strtolower(...)                        // 2. Minúsculas
    |> fn(string $s): string => filter_var($s, FILTER_SANITIZE_EMAIL); // 3. Sanitiza

// Resultado: "usuario@exemplo.com"
```

### 78.2 Detalhamento do Fluxo

1.  **`trim(...)`**: `$rawInput` é passado para `trim`. O `...` indica que é o argumento.
2.  **`strtolower(...)`**: Resultado do `trim` vai para `strtolower`.
3.  **`filter_var(...)`**: Resultado vai como **primeiro argumento**. Argumentos adicionais (como `FILTER_SANITIZE_EMAIL`) seguem normalmente.

### 78.3 Sanitização de Nome

Pipeline para nomes: remove espaços, tags HTML, converte para minúsculas e aplica Title Case:
```php
<?php

declare(strict_types=1);

$nomeLimpo = $_POST['nome']
    |> trim(...)          // Remove espaços extras
    |> strip_tags(...)    // Remove tags HTML/PHP
    |> mb_strtolower(...) // Garante minúsculas primeiro
    |> ucwords(...);      // Converte para "Title Case"
```

### 78.4 Vantagens

*   **Legibilidade:** Fluxo linear — "pegue, limpe, diminua, sanitize".
*   **Imutabilidade:** Evita reatribuição repetitiva da mesma variável.
*   **Depuração:** Fácil comentar uma linha do pipe para testar.


---

## 79. Value Objects para Dados Brasileiros (CPF, RG, CEP)

Este capítulo implementa Value Objects imutáveis para documentos brasileiros: `Cpf` com validação por Módulo 11, `BrazilianDocuments` com Property Hooks para RG e CEP, e `Person` como entidade de domínio com factory method para `$_POST`.

### 79.1 Value Object: CPF

O CPF possui algoritmo verificador (Módulo 11). Esta classe imutável se autovalida.

```php
<?php

declare(strict_types=1);

namespace App\Domain\ValueObject;

use InvalidArgumentException;

readonly class Cpf
{
    public string $value;

    public function __construct(string $rawCpf)
    {
        // Sanitização com Pipe Operator (PHP 8.5)
        $cleanCpf = $rawCpf
            |> fn(string $s): string => preg_replace('/[^0-9]/', '', $s);

        if (!$this->validate($cleanCpf)) {
            throw new InvalidArgumentException("CPF inválido: {$rawCpf}");
        }

        $this->value = $cleanCpf;
    }

    private function validate(string $cpf): bool
    {
        if (strlen($cpf) !== 11 || preg_match('/(\d)\1{10}/', $cpf)) {
            return false;
        }

        // Cálculo dos dígitos verificadores (Módulo 11)
        for ($t = 9; $t < 11; $t++) {
            for ($d = 0, $c = 0; $c < $t; $c++) {
                $d += (int) $cpf[$c] * (($t + 1) - $c);
            }
            $d = ((10 * $d) % 11) % 10;
            if ((int) $cpf[$c] !== $d) {
                return false;
            }
        }

        return true;
    }

    public function format(): string
    {
        return preg_replace(
            '/(\d{3})(\d{3})(\d{3})(\d{2})/',
            '$1.$2.$3-$4',
            $this->value,
        );
    }

    public function __toString(): string
    {
        return $this->value;
    }
}
```

### 79.2 Value Object: BrazilianDocuments (RG + CEP)

O RG não possui padrão nacional único, então validamos o formato.

```php
<?php

declare(strict_types=1);

namespace App\Domain\ValueObject;

use InvalidArgumentException;

readonly class BrazilianDocuments
{
    public string $rg {
        set {
            $clean = strtoupper(preg_replace('/[^0-9xX]/', '', $value));

            if (strlen($clean) < 5 || strlen($clean) > 14) {
                throw new InvalidArgumentException("RG inválido.");
            }
            $this->rg = $clean;
        }
    }

    public string $cep {
        set {
            $clean = preg_replace('/[^0-9]/', '', $value);

            if (strlen($clean) !== 8) {
                throw new InvalidArgumentException("CEP deve conter 8 dígitos.");
            }
            $this->cep = $clean;
        }
    }

    public function __construct(string $rg, string $cep)
    {
        $this->rg = $rg;
        $this->cep = $cep;
    }
}
```

### 79.3 Entidade Person

A entidade `Person` compõe Value Objects tipados e oferece `fromArray()` para criação segura a partir de `$_POST`:
```php
<?php

declare(strict_types=1);

namespace App\Domain;

use App\Domain\ValueObject\Cpf;
use DateTimeImmutable;
use Exception;

readonly class Person
{
    public function __construct(
        public string $fullName,
        public Cpf $cpf,
        public string $rg,
        public DateTimeImmutable $birthDate,
        public string $address,
        public string $cep,
    ) {}

    /**
     * Factory method para criar a partir de inputs brutos ($_POST).
     */
    public static function fromArray(array $data): self
    {
        $date = DateTimeImmutable::createFromFormat('d/m/Y', $data['birth_date'] ?? '');

        if (!$date || $date->format('d/m/Y') !== $data['birth_date']) {
            throw new Exception("Data de nascimento inválida. Use DD/MM/AAAA.");
        }

        return new self(
            fullName: trim($data['full_name'] ?? ''),
            cpf: new Cpf($data['cpf'] ?? ''),
            rg: preg_replace('/[^0-9xX]/', '', $data['rg'] ?? ''),
            birthDate: $date,
            address: trim($data['address'] ?? ''),
            cep: preg_replace('/[^0-9]/', '', $data['cep'] ?? ''),
        );
    }
}
```

### 79.4 Persistência no MySQL

Schema recomendado: CPF como `VARCHAR(11)` com `UNIQUE`, RG como `VARCHAR(20)`, CEP como `CHAR(8)`, datas em `DATE`:
**Estrutura recomendada:**

*   `cpf`: `VARCHAR(11)` com `UNIQUE INDEX` (nunca `INT`, zeros à esquerda importam).
*   `rg`: `VARCHAR(20)` (variações estaduais e letras).
*   `cep`: `CHAR(8)` (tamanho fixo).
*   `birth_date`: `DATE` (formato `YYYY-MM-DD`).

```php
<?php

declare(strict_types=1);

namespace App\Repository;

use App\Domain\Person;
use PDO;

class PersonRepository
{
    public function __construct(private PDO $pdo) {}

    public function save(Person $person): void
    {
        $stmt = $this->pdo->prepare("
            INSERT INTO people (full_name, cpf, rg, birth_date, address, cep)
            VALUES (:name, :cpf, :rg, :birth, :addr, :cep)
        ");

        $stmt->execute([
            'name'  => $person->fullName,
            'cpf'   => $person->cpf->value,
            'rg'    => $person->rg,
            'birth' => $person->birthDate->format('Y-m-d'),
            'addr'  => $person->address,
            'cep'   => $person->cep,
        ]);
    }
}
```

### 79.5 Boas Práticas

1.  **LGPD:** CPF e RG são dados sensíveis. Considere criptografar antes de salvar.
2.  **Imutabilidade:** Use `readonly`. CPF não muda; se precisar, crie nova instância.
3.  **Sanitização na Entrada:** Use Pipe Operator para limpar dados do `$_POST` antes de validar.
4.  **Armazenamento:** Datas: `d/m/Y` → `Y-m-d`. Documentos: apenas dígitos, formate só na exibição.


---

## 80. Validação de Titularidade de CPF — grapheme_levenshtein

Além da validação algorítmica (Módulo 11), a titularidade verifica se o CPF pertence ao nome informado. PHP 8.5 introduz `grapheme_levenshtein()`, que calcula distância de edição respeitando grafemas Unicode — essencial para nomes com acentos.

### 80.1 Interface do Contrato

Contrato para validação de titularidade, desacoplando a fonte de dados (banco, API):
```php
<?php

declare(strict_types=1);

namespace App\Domain\Service;

use App\Domain\ValueObject\Cpf;

interface CpfOwnershipValidatorInterface
{
    /**
     * Verifica se o CPF pertence ao nome informado.
     */
    public function matchesName(Cpf $cpf, string $inputName): bool;
}
```

### 80.2 Implementação com `grapheme_levenshtein` (PHP 8.5)

A função `grapheme_levenshtein()` é superior às antigas `levenshtein()` e `similar_text()` para nomes com acentos e caracteres UTF-8 (multibyte).

```php
<?php

declare(strict_types=1);

namespace App\Infrastructure\Service;

use App\Domain\Service\CpfOwnershipValidatorInterface;
use App\Domain\ValueObject\Cpf;
use PDO;

readonly class DatabaseCpfValidator implements CpfOwnershipValidatorInterface
{
    public function __construct(
        private PDO $pdo,
    ) {}

    public function matchesName(Cpf $cpf, string $inputName): bool
    {
        $officialName = $this->getOfficialNameFromDb($cpf);

        if ($officialName === null) {
            return false;
        }

        // Normalização com Pipe Operator (PHP 8.5)
        $n1 = $inputName |> trim(...) |> mb_strtoupper(...);
        $n2 = $officialName |> trim(...) |> mb_strtoupper(...);

        // grapheme_levenshtein (PHP 8.5) — lida com grafemas Unicode
        $distance = grapheme_levenshtein($n1, $n2);

        // Tolerância: 0 = idêntico, <= 3 aceita erros como "Luiz" vs "Luis"
        $maxDistance = 3;

        // Se distância alta, verifica se um nome contém o outro
        // ex: "João da Silva" vs "João Silva"
        if ($distance > $maxDistance) {
            return str_contains($n2, $n1) || str_contains($n1, $n2);
        }

        return $distance <= $maxDistance;
    }

    private function getOfficialNameFromDb(Cpf $cpf): ?string
    {
        $stmt = $this->pdo->prepare("SELECT full_name FROM users WHERE cpf = :cpf");
        $stmt->execute(['cpf' => $cpf->value]);

        return $stmt->fetchColumn() ?: null;
    }
}
```

### 80.3 Integração com APIs Externas

Para usuários novos, consulte APIs de Bureau de Dados (Serasa, Receita) usando cURL persistente do PHP 8.5:
Para validar usuários novos que não estão no banco, consulte APIs de Bureau de Dados (Serasa, Receita):

```php
<?php

declare(strict_types=1);

private function getOfficialNameFromApi(Cpf $cpf): ?string
{
    // PHP 8.5: Handles persistentes para alta performance
    $sh = curl_share_init_persistent('api_receita_share');
    curl_share_setopt($sh, CURLSHOPT_SHARE, CURL_LOCK_DATA_DNS);

    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, "https://api.parceiro.com.br/cpf/" . $cpf->value);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SHARE, $sh);
    curl_setopt($ch, CURLOPT_HTTPHEADER, [
        'Authorization: Bearer ' . getenv('API_TOKEN'),
    ]);

    $response = curl_exec($ch);
    $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

    if ($httpCode !== 200 || !$response) {
        return null;
    }

    $data = json_decode($response, true);
    return $data['nome'] ?? null;
}
```

### 80.4 Boas Práticas

1.  **Algoritmo primeiro:** O Value Object `Cpf` (Módulo 11) prova que o número existe matematicamente. Titularidade é um passo adicional.
2.  **`grapheme_levenshtein` (PHP 8.5):** Nunca compare nomes com `==`. Lida corretamente com grafemas Unicode.
3.  **LGPD:** Ao consultar APIs externas, certifique-se de que seus termos permitem a verificação. Não armazene dados retornados desnecessariamente.
4.  **Custo:** APIs de titularidade cobram por consulta. Valide algoritmicamente primeiro para descartar CPFs inválidos.

---

## 81. Criptografia de Dados Sensíveis (LGPD) — Sodium

A LGPD exige que dados como CPF e RG sejam protegidos em repouso. Diferente de senhas (hash unidirecional), documentos precisam ser recuperados — por isso usamos **criptografia simétrica** (bidirecional) com Sodium.

### 81.1 Por que Criptografar e não fazer Hash

Documentos como CPF e RG precisam ser recuperados para exibição ou contratos. Diferente de senhas (hash unidirecional), usamos **Criptografia Simétrica** (bidirecional).

### 81.2 Extensão Sodium

No PHP 8.5, a extensão **Sodium** (libsodium) oferece criptografia autenticada (AEAD), garantindo que o dado não foi adulterado.

Para atender à LGPD, dados sensíveis não devem ser armazenados em texto puro. A combinação de Sodium com **Blind Indexing** permite criptografar e ainda buscar registros no banco.


---

## 82. Criptografia com Sodium — CryptoService e Blind Indexing

Este capítulo implementa o padrão completo: `CryptoService` para encrypt/decrypt com Sodium AEAD, Blind Indexing via HMAC para buscas `WHERE cpf_blind_index = ?`, e um repositório que une ambos.

### 82.1 Gerenciamento de Chaves

A chave de criptografia nunca deve ficar no banco de dados. Mantenha no ambiente (`.env` ou variáveis de servidor):

```php
<?php

declare(strict_types=1);

// Gere uma chave e salve como ENCRYPTION_KEY no .env
echo base64_encode(sodium_crypto_secretbox_keygen());
```

### 82.2 CryptoService

Implementação com `#[SensitiveParameter]`, nonce aleatório por operação e verificação de integridade:
```php
<?php

declare(strict_types=1);

namespace App\Infrastructure\Security;

use Exception;
use SensitiveParameter;

readonly class CryptoService
{
    private string $key;

    public function __construct(
        #[SensitiveParameter] string $base64Key,
    ) {
        $key = base64_decode($base64Key);

        if (mb_strlen($key, '8bit') !== SODIUM_CRYPTO_SECRETBOX_KEYBYTES) {
            throw new Exception('Chave de criptografia inválida.');
        }

        $this->key = $key;
    }

    public function encrypt(#[SensitiveParameter] string $plaintext): string
    {
        // Nonce único aleatório para cada operação
        $nonce = random_bytes(SODIUM_CRYPTO_SECRETBOX_NONCEBYTES);

        $ciphertext = sodium_crypto_secretbox($plaintext, $nonce, $this->key);

        // Nonce + Ciphertext em Base64 para o banco
        return base64_encode($nonce . $ciphertext);
    }

    public function decrypt(string $encryptedBase64): string
    {
        $decoded  = base64_decode($encryptedBase64);
        $nonceLen = SODIUM_CRYPTO_SECRETBOX_NONCEBYTES;

        if (mb_strlen($decoded, '8bit') < $nonceLen) {
            throw new Exception('Dado corrompido ou inválido.');
        }

        $nonce      = mb_substr($decoded, 0, $nonceLen, '8bit');
        $ciphertext = mb_substr($decoded, $nonceLen, null, '8bit');

        $plaintext = sodium_crypto_secretbox_open($ciphertext, $nonce, $this->key);

        if ($plaintext === false) {
            throw new Exception('Falha na decriptação: integridade violada.');
        }

        return $plaintext;
    }
}
```

### 82.3 Blind Indexing — O Problema da Busca

CPF criptografado gera string aleatória diferente a cada salvamento (por causa do Nonce). Para buscar `WHERE cpf = ?`, criamos uma coluna extra `cpf_hash` com HMAC determinístico.

```sql
CREATE TABLE people (
    id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(100) NOT NULL,
    cpf_encrypted VARCHAR(255) NOT NULL,
    rg_encrypted VARCHAR(255) NOT NULL,
    cpf_blind_index CHAR(64) NOT NULL UNIQUE,
    birth_date DATE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 82.4 Repositório com Criptografia

Hidratação completa: encrypt ao salvar, blind index para busca, decrypt ao ler:
```php
<?php

declare(strict_types=1);

namespace App\Repository;

use App\Domain\Person;
use App\Domain\ValueObject\Cpf;
use App\Infrastructure\Security\CryptoService;
use PDO;
use DateTimeImmutable;

class PersonRepository
{
    private string $blindIndexKey;

    public function __construct(
        private PDO $pdo,
        private CryptoService $crypto,
    ) {
        $this->blindIndexKey = $_ENV['BLIND_INDEX_KEY'] ?? '';
    }

    public function save(Person $person): void
    {
        $cpfLimpo = $person->cpf->value;
        $rgLimpo  = $person->rg;

        // Criptografar para armazenamento
        $cpfEncrypted = $this->crypto->encrypt($cpfLimpo);
        $rgEncrypted  = $this->crypto->encrypt($rgLimpo);

        // Blind Index com HMAC para busca
        $cpfIndex = hash_hmac('sha256', $cpfLimpo, $this->blindIndexKey);

        $stmt = $this->pdo->prepare("
            INSERT INTO people (full_name, cpf_encrypted, rg_encrypted, cpf_blind_index, birth_date)
            VALUES (:name, :cpf_enc, :rg_enc, :cpf_idx, :birth)
        ");

        $stmt->execute([
            'name'    => $person->fullName,
            'cpf_enc' => $cpfEncrypted,
            'rg_enc'  => $rgEncrypted,
            'cpf_idx' => $cpfIndex,
            'birth'   => $person->birthDate->format('Y-m-d'),
        ]);
    }

    public function findByCpf(Cpf $cpf): ?Person
    {
        $cpfIndex = hash_hmac('sha256', $cpf->value, $this->blindIndexKey);

        $stmt = $this->pdo->prepare(
            "SELECT * FROM people WHERE cpf_blind_index = :cpf_idx",
        );
        $stmt->execute(['cpf_idx' => $cpfIndex]);

        $data = $stmt->fetch();

        if (!$data) {
            return null;
        }

        try {
            $cpfReal = $this->crypto->decrypt($data['cpf_encrypted']);
            $rgReal  = $this->crypto->decrypt($data['rg_encrypted']);
        } catch (\Exception $e) {
            return null;
        }

        return new Person(
            fullName: $data['full_name'],
            cpf: new Cpf($cpfReal),
            rg: $rgReal,
            birthDate: new DateTimeImmutable($data['birth_date']),
            address: '',
            cep: '',
        );
    }
}
```

### 82.5 Práticas LGPD

1.  **Criptografia em Repouso:** Dados reais nunca tocam o disco em formato legível.
2.  **Segregação de Chaves:** Encryption Key (Sodium) separada da Blind Index Key (HMAC).
3.  **Integridade:** `sodium_crypto_secretbox_open` verifica se o dado foi adulterado.
4.  **Minimização:** Só decripte o que for exibir. Use o blind index para verificar existência.


---

## 83. Busca de CEP via API — ViaCEP com cURL

Este capítulo implementa integração com a API pública ViaCEP: Value Object `Cep` com Property Hook, entidade `Address` imutável, `CepService` com `#[\NoDiscard]` e Enum de estados brasileiros.

### 83.1 Value Object: Cep

Property Hook sanitiza automaticamente a entrada, removendo formatação e validando 8 dígitos:
```php
<?php

declare(strict_types=1);

namespace App\Domain\ValueObject;

use InvalidArgumentException;

readonly class Cep
{
    public string $value {
        // Property Hook: sanitização automática
        set {
            $clean = preg_replace('/[^0-9]/', '', $value);

            if (strlen($clean) !== 8) {
                throw new InvalidArgumentException("CEP inválido: deve conter 8 dígitos.");
            }

            $this->value = $clean;
        }
    }

    public function __construct(string $value)
    {
        $this->value = $value;
    }

    public function __toString(): string
    {
        return $this->value;
    }
}
```

### 83.2 Entidade Address

DTO imutável com constructor promotion e complemento opcional:
```php
<?php

declare(strict_types=1);

namespace App\Domain;

use App\Domain\ValueObject\Cep;

readonly class Address
{
    public function __construct(
        public Cep $cep,
        public string $street,
        public string $neighborhood,
        public string $city,
        public string $state,
        public ?string $complement = null,
    ) {}
}
```

### 83.3 CepService

`#[\NoDiscard]` garante que o `Address` retornado não seja ignorado. Valida `json_validate()` antes de decodificar:
```php
<?php

declare(strict_types=1);

namespace App\Service;

use App\Domain\Address;
use App\Domain\ValueObject\Cep;
use Exception;
use RuntimeException;

class CepService
{
    private const API_URL = 'https://viacep.com.br/ws/%s/json/';

    #[\NoDiscard]
    public function fetchAddress(string|Cep $cepInput): Address
    {
        $cep = $cepInput instanceof Cep ? $cepInput : new Cep($cepInput);

        $url = sprintf(self::API_URL, $cep->value);

        $ch = curl_init();
        curl_setopt_array($ch, [
            CURLOPT_URL            => $url,
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_TIMEOUT        => 5,
            CURLOPT_CONNECTTIMEOUT => 2,
        ]);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        $error    = curl_error($ch);
        curl_close($ch);

        if ($error || $httpCode !== 200) {
            throw new RuntimeException("Erro ao consultar CEP: " . ($error ?: "HTTP $httpCode"));
        }

        if (!json_validate($response)) {
            throw new RuntimeException("Resposta da API inválida.");
        }

        $data = json_decode($response, true);

        if (isset($data['erro'])) {
            throw new Exception("CEP não encontrado na base de dados.");
        }

        return new Address(
            cep: $cep,
            street: $data['logradouro'] ?? '',
            neighborhood: $data['bairro'] ?? '',
            city: $data['localidade'] ?? '',
            state: $data['uf'] ?? '',
            complement: $data['complemento'] ?? null,
        );
    }
}
```

### 83.4 Integração com Pipe Operator

Ponto de entrada HTTP sanitizando o CEP com pipe antes de consultar:
```php
<?php

declare(strict_types=1);

use App\Service\CepService;

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    try {
        $rawCep = $_POST['cep'] ?? '';

        $cepString = $rawCep
            |> trim(...)
            |> htmlspecialchars(..., ENT_QUOTES);

        $service = new CepService();
        $address = $service->fetchAddress($cepString);

        echo "Logradouro: " . $address->street . PHP_EOL;
        echo "Bairro: " . $address->neighborhood . PHP_EOL;
        echo "Cidade/UF: " . $address->city . " / " . $address->state;

    } catch (Exception $e) {
        error_log($e->getMessage());
        echo "Não foi possível buscar o endereço.";
    }
}
```

### 83.5 Enum de Estados Brasileiros

Backed Enum com `tryFrom()` para validação segura de UF:
```php
<?php

declare(strict_types=1);

enum BrazilianState: string
{
    case SP = 'SP';
    case RJ = 'RJ';
    case MG = 'MG';
    case RS = 'RS';
    case PR = 'PR';
    case BA = 'BA';
    // ... outros estados

    public static function isValid(string $uf): bool
    {
        return !empty(self::tryFrom(strtoupper($uf)));
    }
}
```

### 83.6 Boas Práticas

1.  **Cache:** Implemente cache (Redis ou arquivo) para CEPs consultados.
2.  **Frontend:** Preencha via AJAX no cliente; use PHP para validação final.
3.  **MySQL:** Colunas separadas: `zip_code` (VARCHAR 8), `street`, `city`, `state` (CHAR 2).
4.  **Validar UF:** Use Enum de estados para integridade referencial.


---

## 84. Pipe Operator com PDO — Buscas Dinâmicas

O pipe operator transforma a sanitização de parâmetros de busca num pipeline linear antes de enviá-los ao MySQL via prepared statements. Este capítulo mostra buscas simples e múltiplos filtros.

### 84.1 Busca Simples com LIKE

O Pipe Operator prepara, limpa e formata os dados de busca *antes* de enviá-los ao MySQL via PDO.

```php
<?php

declare(strict_types=1);

namespace App\Repository;

use PDO;

readonly class ProductRepository
{
    public function __construct(
        private PDO $pdo,
    ) {}

    public function searchByName(string $rawInput): array
    {
        // Pipe Operator (PHP 8.5): fluxo linear de sanitização
        $searchTerm = $rawInput
            |> trim(...)           // Remove espaços
            |> strip_tags(...)     // Remove tags HTML
            |> mb_strtolower(...)  // Minúsculas (case-insensitive)
            |> fn($s) => "%{$s}%"; // Adiciona coringas do MySQL

        if ($searchTerm === '%%') {
            return [];
        }

        $sql = "SELECT id, name, price FROM products WHERE LOWER(name) LIKE :term";

        $stmt = $this->pdo->prepare($sql);
        $stmt->bindValue(':term', $searchTerm);
        $stmt->execute();

        return $stmt->fetchAll();
    }
}
```

### 84.2 Buscas com Múltiplos Filtros

Construção dinâmica de SQL com pipes individuais por filtro:
```php
<?php

declare(strict_types=1);

public function searchAdvanced(array $filters): array
{
    $sql = "SELECT * FROM products WHERE 1=1";
    $params = [];

    // Filtro de Nome
    if (!empty($filters['name'])) {
        $sql .= " AND name LIKE :name";

        $params[':name'] = $filters['name']
            |> trim(...)
            |> fn($s) => "%{$s}%";
    }

    // Filtro de Status
    if (!empty($filters['status'])) {
        $sql .= " AND status = :status";

        $params[':status'] = $filters['status']
            |> trim(...)
            |> strtolower(...);
    }

    $stmt = $this->pdo->prepare($sql);
    $stmt->execute($params);

    return $stmt->fetchAll();
}
```

### 84.3 Vantagens sobre o Código Tradicional

| Aspecto | Tradicional | Pipe Operator (PHP 8.5) |
| :--- | :--- | :--- |
| **Leitura** | De fora para dentro (aninhado) | De cima para baixo (linear) |
| **Variáveis** | Temporárias ou sobrescrita | Fluxo direto, sem intermediárias |
| **Depuração** | Desmontar cadeia de funções | Comentar uma linha do pipe |

---

## 85. Validação de NIS e CPF Mascarado

O NIS (PIS/PASEP) é um documento com validação algorítmica (Módulo 11), enquanto o CPF mascarado (`***.123.456-**`) é um dado parcial comum em relatórios legados que requer validação de formato.

### 85.1 Contexto

*   **NIS (Número de Identificação Social):** Documento completo (PIS/PASEP) com validação algorítmica (Módulo 11).
*   **CPF Mascarado:** Dado parcial (`***.123.456-**`). Não serve para validação de identidade, mas precisa de validação de formato para importação de relatórios legados.


---

## 86. NIS (PIS/PASEP) e CPF Mascarado

Implementação prática dos Value Objects apresentados no capítulo anterior: `Nis` com Property Hook e Módulo 11, `MaskedCpf` para correspondência parcial, e pipeline de processamento com pipe operator.

### 86.1 Value Object: NIS

Property Hook valida tamanho e dígito verificador com pesos específicos do PIS:
O NIS possui 11 dígitos e usa Módulo 11 com pesos específicos.

```php
<?php

declare(strict_types=1);

namespace App\Domain\ValueObject;

use InvalidArgumentException;

readonly class Nis
{
    public string $value {
        set {
            $clean = preg_replace('/[^0-9]/', '', $value);

            if (strlen($clean) !== 11) {
                throw new InvalidArgumentException("NIS inválido: deve conter 11 dígitos.");
            }

            if (!$this->validateCheckDigit($clean)) {
                throw new InvalidArgumentException("NIS inválido: dígito verificador incorreto.");
            }

            $this->value = $clean;
        }
    }

    public function __construct(string $value)
    {
        $this->value = $value;
    }

    private function validateCheckDigit(string $nis): bool
    {
        // Pesos padrão do PIS/NIS: 3, 2, 9, 8, 7, 6, 5, 4, 3, 2
        $weights = [3, 2, 9, 8, 7, 6, 5, 4, 3, 2];
        $sum = 0;

        for ($i = 0; $i < 10; $i++) {
            $sum += (int) $nis[$i] * $weights[$i];
        }

        $remainder = $sum % 11;
        $digit = 11 - $remainder;
        $digit = ($digit >= 10) ? 0 : $digit;

        return $digit === (int) $nis[10];
    }

    public function format(): string
    {
        return preg_replace(
            '/(\d{1})(\d{3})(\d{3})(\d{3})(\d{1})/',
            '$1.$2.$3.$4-$5',
            $this->value,
        );
    }

    public function __toString(): string
    {
        return $this->value;
    }
}
```

### 86.2 CPF Mascarado (Dados Parciais)

DTO imutável que valida formato `***.NNN.NNN-**` e oferece `matchesFullCpf()` para cruzamento:
O CPF `***.728.995-**` é comum em relatórios públicos. Não pode ser validado matematicamente, mas o formato deve ser verificado.

```php
<?php

declare(strict_types=1);

namespace App\Domain\DTO;

use InvalidArgumentException;

readonly class MaskedCpf
{
    public function __construct(
        public string $displayValue,
    ) {
        // Formato: ***.123.456-**
        if (!preg_match('/^\*{3}\.\d{3}\.\d{3}\-\*{2}$/', $displayValue)) {
            throw new InvalidArgumentException("Formato de CPF mascarado inválido.");
        }
    }

    /**
     * Verifica se um CPF completo corresponde a este mascarado.
     */
    public function matchesFullCpf(string $fullCpf): bool
    {
        $cleanFull = preg_replace('/[^0-9]/', '', $fullCpf);

        // Extrai o miolo visível (posições 3-8)
        $visiblePart = preg_replace('/[^0-9]/', '', $this->displayValue);
        $core = substr($cleanFull, 3, 6);

        return $core === $visiblePart;
    }
}
```

### 86.3 Pipeline de Processamento

Exemplo completo integrando `Nis`, `MaskedCpf` e pipe operator para processar dados de beneficiários:
```php
<?php

declare(strict_types=1);

use App\Domain\ValueObject\Nis;
use App\Domain\DTO\MaskedCpf;

$inputData = [
    'nome'        => 'DOUGLAS COSTA ANDRADE',
    'cpf_parcial' => '***.728.995-**',
    'nis'         => '2.372.162.443-9',
];

try {
    $nome = $inputData['nome']
        |> trim(...)
        |> mb_strtoupper(...);

    $nis       = new Nis($inputData['nis']);
    $maskedCpf = new MaskedCpf($inputData['cpf_parcial']);

    echo "Beneficiário: {$nome}" . PHP_EOL;
    echo "NIS Validado: {$nis->format()}" . PHP_EOL;

    // Verificar correspondência com CPF real do banco
    $cpfNoBanco = '11172899500';

    if ($maskedCpf->matchesFullCpf($cpfNoBanco)) {
        echo "MATCH! CPF mascarado corresponde ao registro interno.";
    }

} catch (\Exception $e) {
    echo "Erro: " . $e->getMessage();
}
```

### 86.4 Boas Práticas

1.  **NIS:** Armazene apenas números (`VARCHAR(11)`), valide dígito verificador, use Value Objects.
2.  **Dados Mascarados:** Nunca armazene `***` como identificador único. Trate como DTO de visualização.
3.  **Sanitização:** Use Pipe Operator para limpar espaços e formatação antes da validação.


---

## 87. Escalabilidade MySQL — Do Monólito ao Sharding

Este capítulo apresenta a evolução natural de infraestrutura MySQL: do monólito otimizado até sharding e microserviços, com código PHP para cada nível.

### 87.1 Nível 1: Monólito Otimizado (1 Banco)

Para a maioria das aplicações (até milhões de registros), um único MySQL bem configurado é suficiente.

*   **Engine:** InnoDB (padrão do MySQL 8.0/8.4).
*   **Índices:** Colunas usadas em `WHERE`, `JOIN` e `ORDER BY`.
*   **Particionamento:** MySQL divide tabelas grandes em pedaços menores, invisível para o PHP.

### 87.2 Nível 2: Separação Leitura/Escrita (Replication)

Quando acessos simultâneos tornam o sistema lento. A `ConnectionFactory` implementa fallback automático:
*   **Source (Master):** PHP faz `INSERT`, `UPDATE`, `DELETE`.
*   **Replicas (Slaves):** PHP faz `SELECT`.

```php
<?php

declare(strict_types=1);

namespace App\Infrastructure\Database;

use PDO;

readonly class ConnectionFactory
{
    public function __construct(
        private string $dsnWriter,
        private string $dsnReader,
        private string $user,
        private string $password,
    ) {}

    public function createWriter(): PDO
    {
        return $this->createConnection($this->dsnWriter);
    }

    public function createReader(): PDO
    {
        // Fallback para Writer se réplica cair
        try {
            return $this->createConnection($this->dsnReader);
        } catch (\PDOException) {
            return $this->createWriter();
        }
    }

    private function createConnection(string $dsn): PDO
    {
        return new PDO($dsn, $this->user, $this->password, [
            PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
            PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
            PDO::ATTR_EMULATE_PREPARES   => false,
        ]);
    }
}
```

### 87.3 Nível 3: Sharding (Fragmentação Horizontal)

Para bilhões de registros — dados divididos em vários bancos.

*   **Banco A:** Usuários ID 1 a 1.000.000.
*   **Banco B:** Usuários ID 1.000.001 a 2.000.000.
*   **Desafio:** `JOIN` entre bancos é complexo. A lógica de roteamento fica no PHP.

### 87.4 Nível 4: Separação por Domínio (Microserviços)

*   **Banco de Usuários:** Login, perfil, LGPD (criptografado).
*   **Banco Financeiro:** Transações, pagamentos.
*   **Banco de Logs:** Auditoria e histórico.

### 87.5 Recomendação

1.  Comece com **1 banco MySQL** bem configurado.
2.  Dados sensíveis criptografados com Sodium + Blind Indexing.
3.  Se leitura ficar lenta: adicione réplicas.
4.  Se armazenamento estourar: arquive dados antigos.

Não crie múltiplos bancos antes de precisar (evite otimização prematura).


---

## 88. Validação de CNPJ e Documentos com Pipe Operator

CNPJ segue o mesmo padrão de validação por Módulo 11, com 14 dígitos e pesos específicos. O pipe operator encadeia sanitização e validação num único fluxo. Este capítulo também demonstra validação de passaportes com closures inline.

### 88.1 Value Object: CNPJ

O CNPJ possui 14 dígitos e algoritmo de verificação com Módulo 11.

```php
<?php

declare(strict_types=1);

namespace App\Domain\ValueObject;

use InvalidArgumentException;

readonly class Cnpj
{
    public string $value;

    public function __construct(string $rawInput)
    {
        // Pipeline: Entrada -> Trim -> Remove não-dígitos -> Valida
        $cleanCnpj = $rawInput
            |> trim(...)
            |> preg_replace('/[^0-9]/', '', ...)
            |> $this->assertValid(...);

        $this->value = $cleanCnpj;
    }

    private function assertValid(string $cnpj): string
    {
        if (strlen($cnpj) !== 14 || preg_match('/(\d)\1{13}/', $cnpj)) {
            throw new InvalidArgumentException("CNPJ inválido: formato incorreto.");
        }

        // Valida dígitos verificadores
        $cnpj
            |> fn($c) => $this->calculateDigit($c, 12)
            |> fn($c) => $this->calculateDigit($c, 13);

        return $cnpj;
    }

    private function calculateDigit(string $cnpj, int $length): string|bool
    {
        if ($cnpj === false) {
            return false;
        }

        $soma = 0;
        $pos  = $length - 7;

        for ($i = $length; $i >= 1; $i--) {
            $soma += (int) $cnpj[$length - $i] * $pos--;
            if ($pos < 2) {
                $pos = 9;
            }
        }

        $d = $soma % 11 < 2 ? 0 : 11 - ($soma % 11);

        if ((int) $cnpj[$length] !== $d) {
            throw new InvalidArgumentException("CNPJ inválido: dígitos incorretos.");
        }

        return $cnpj;
    }

    public function format(): string
    {
        return preg_replace(
            '/(\d{2})(\d{3})(\d{3})(\d{4})(\d{2})/',
            '$1.$2.$3/$4-$5',
            $this->value,
        );
    }
}
```

### 88.2 Documentos Genéricos (Passaporte)

Para documentos sem algoritmo matemático, closures inline no pipe fazem validação por regex:
Para documentos sem algoritmo matemático, o Pipe Operator usa Closures para validação inline.

```php
<?php

declare(strict_types=1);

class DocumentService
{
    public function validatePassport(string $input): string
    {
        // Padrão: 2 letras + 6 números
        $passport = $input
            |> trim(...)
            |> strtoupper(...)
            |> str_replace(' ', '', ...)
            |> function (string $p) {
                if (!preg_match('/^[A-Z]{2}\d{6}$/', $p)) {
                    throw new \InvalidArgumentException("Passaporte inválido: {$p}");
                }
                return $p;
            };

        return $passport;
    }
}

// Uso:
$doc = new DocumentService();
echo $doc->validatePassport("  br 123456 "); // "BR123456"
```

### 88.3 Dicas do Pipe Operator

1.  **`...` (First-Class Callable):** `preg_replace('/[^0-9]/', '', ...)` — o valor do pipe entra no lugar dos `...`.
2.  **Tratamento de Erros:** Use exceções (`throw`) dentro do pipe. Não retorne `false`.
3.  **`#[\NoDiscard]`:** Em métodos que retornam `true/false`, garanta que o resultado seja checado.


---

## 89. Armazenamento Seguro de NIS (LGPD)

O NIS é classificado como dado pessoal pela LGPD (pode revelar condição socioeconômica). Este capítulo aplica o mesmo rigor de CPF/RG: Sodium para criptografia, blind index para busca, logs de acesso e avaliação de necessidade de armazenamento.

### 89.1 Três Pilares: Confidencialidade, Integridade, Rastreabilidade

O NIS é classificado como **Dado Pessoal** (pode revelar condição socioeconômica). Segue o mesmo rigor do CPF e RG.

### 89.2 Criptografia em Repouso

Sodium encrypt + HMAC blind index, idêntico ao padrão de CPF:
```php
<?php

declare(strict_types=1);

public function saveNis(int $userId, Nis $nis): void
{
    // 1. Criptografar (recuperável)
    $nisEncrypted = $this->cryptoService->encrypt($nis->value);

    // 2. Hash para busca (irreversível e determinístico)
    $nisIndex = hash_hmac('sha256', $nis->value, $this->blindIndexKey);

    $stmt = $this->pdo->prepare("
        UPDATE users
        SET nis_encrypted = :enc, nis_blind_index = :idx
        WHERE id = :id
    ");

    $stmt->execute([
        'enc' => $nisEncrypted,
        'idx' => $nisIndex,
        'id'  => $userId,
    ]);
}
```

### 89.3 Minimização de Dados

Se o NIS é usado apenas para validação momentânea (ex: verificar elegibilidade via API externa) e não é necessário depois, **não o armazene**. Processe em memória e descarte.

### 89.4 Controle de Acesso e Auditoria

Registre em `sensitive_data_access_logs` toda vez que `decrypt()` for chamada. Apenas usuários autorizados podem ver o dado descriptografado.

### 89.5 Validação na Entrada

O Value Object `Nis` garante integridade antes de qualquer operação de persistência:
```php
<?php

declare(strict_types=1);

try {
    $nis = new Nis($_POST['nis']); // Valida formato e dígito verificador
    $userRepo->saveNis($user->id, $nis);
} catch (\InvalidArgumentException $e) {
    error_log("Tentativa de salvar NIS inválido para usuário " . $user->id);
}
```

### 89.6 Resumo LGPD para NIS

| Requisito | Solução Técnica |
| :--- | :--- |
| **Sigilo** | Sodium (`sodium_crypto_secretbox`) antes do `INSERT` |
| **Necessidade** | Avaliar se armazenar é vital; se não, descartar |
| **Integridade** | Value Object `Nis` (Módulo 11) |
| **Transparência** | Tabela de logs de acesso (quem viu, quando) |
| **Prevenção** | Prepared Statements contra SQL Injection |


---

## 90. Cliente de API de Titularidade com cURL Persistente

Este capítulo implementa um cliente HTTP que usa `curl_share_init_persistent()` do PHP 8.5 para reutilizar handles DNS/TLS entre requisições, combinado com `#[\NoDiscard]` para garantir que o resultado da validação não seja ignorado.

### 90.1 Implementação

Handle persistente reutiliza conexão TLS, POST com JSON, timeout curto para APIs de bureau:
```php
<?php

declare(strict_types=1);

namespace App\Infrastructure\Api;

use App\Domain\ValueObject\Cpf;
use RuntimeException;

class TitularityApiClient
{
    private string $baseUrl;
    private string $apiKey;

    public function __construct()
    {
        $this->baseUrl = getenv('CPF_API_URL');
        $this->apiKey  = getenv('CPF_API_TOKEN');
    }

    #[\NoDiscard]
    public function validateOwnership(Cpf $cpf, string $name): bool
    {
        // PHP 8.5: Handle persistente para reutilizar conexões TLS
        // Recebe array de CURL_LOCK_DATA_* constants (NÃO string)
        $sh = curl_share_init_persistent([
            CURL_LOCK_DATA_DNS,
            CURL_LOCK_DATA_CONNECT,
            CURL_LOCK_DATA_SSL_SESSION,
        ]);

        $ch = curl_init();

        curl_setopt_array($ch, [
            CURLOPT_URL            => $this->baseUrl . '/validate',
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_POST           => true,
            CURLOPT_SHARE          => $sh,
            CURLOPT_POSTFIELDS     => json_encode([
                'cpf'  => $cpf->value,
                'name' => $name,
            ]),
            CURLOPT_HTTPHEADER => [
                'Authorization: Bearer ' . $this->apiKey,
                'Content-Type: application/json',
            ],
            CURLOPT_TIMEOUT => 5,
        ]);

        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

        if ($httpCode !== 200 || !$response) {
            return false;
        }

        $data = json_decode($response, true);

        return $data['match'] ?? false;
    }
}
```

---

## 91. Criptografia Simétrica vs Blind Indexing

Este capítulo consolida a diferença conceitual entre os dois pilares de proteção LGPD: criptografia simétrica (para recuperar dados) e blind indexing (para buscá-los sem descriptografar).

### 91.1 Criptografia Simétrica (O "Cofre")

*   **Objetivo:** Confidencialidade e recuperação.
*   **Reversível:** Sim — com a chave correta, recupera-se o texto original.
*   **Não Determinística:** Cada criptografia gera resultado diferente (por causa do Nonce).

### 91.2 Blind Indexing (O "Rastreador")

*   **Objetivo:** Pesquisa (searchability).
*   **Irreversível:** Sim — é um hash, não se converte de volta.
*   **Determinística:** Mesmo input + mesma chave = mesmo resultado sempre.

### 91.3 Tabela Comparativa

| Característica | Criptografia Simétrica | Blind Indexing |
| :--- | :--- | :--- |
| **Função PHP 8.5** | `sodium_crypto_secretbox` | `hash_hmac('sha256')` |
| **Pode ler o dado?** | Sim (decriptação) | Não (apenas comparação) |
| **Resultado mesma entrada** | Diferente (aleatório/Nonce) | Igual (determinístico) |
| **Uso no MySQL** | Armazenamento (`blob/text`) | Busca em `WHERE` |
| **Segurança** | Protege o conteúdo | Oculta conteúdo, revela igualdade |

### 91.4 Fluxo Prático

Exemplo completo de INSERT com ambos os mecanismos e SELECT usando blind index:
```php
<?php

declare(strict_types=1);

// --- SALVAR (INSERT) ---

// Blind Index: hash fixo para busca futura
$blindIndex = hash_hmac('sha256', '12345678900', $blindIndexKey);

// Criptografia: dado criptografado para ler depois (Nonce aleatório)
$encryptedData = $cryptoService->encrypt('12345678900');

// SQL: INSERT INTO users (cpf_blind_index, cpf_encrypted) VALUES (...)

// --- BUSCAR (SELECT) ---

// Gera o mesmo Blind Index para buscar
$searchHash = hash_hmac('sha256', '12345678900', $blindIndexKey);

// SQL: SELECT cpf_encrypted FROM users WHERE cpf_blind_index = $searchHash
// O banco devolve $encryptedData → PHP descriptografa para exibir
$cpfOriginal = $cryptoService->decrypt($resultadoDoBanco['cpf_encrypted']);
```

### 91.5 Por que usar ambos

*   **Só Blind Index:** Irreversível — nunca exibiria o CPF na tela.
*   **Só Criptografia:** Para buscar, teria que descriptografar **todos** os registros no PHP (O(n)).
*   **Ambos:** Criptografia para ler + Blind Index para buscar = padrão da indústria LGPD.


---

## 92. Gerenciamento de .env com PHP Puro

Sem dependências externas: este capítulo implementa um `EnvLoader` nativo que lê `.env`, pula comentários, popula `putenv()`, `$_ENV` e `$_SERVER`, e demonstra a importância de `strict_types` para dados como CPF.

### 92.1 Arquivo `.gitignore`

```text
.env
.DS_Store
vendor/
```

### 92.2 Arquivo `.env`

```ini
GEMINI_API_KEY=sua_chave_secreta_aqui_xyz
DB_HOST=localhost
DB_NAME=sistema_lgpd
DB_USER=app_user
DB_PASS=senha_super_secreta
```

### 92.3 EnvLoader

Lê o arquivo linha a linha, ignora comentários (`#`), extrai `chave=valor` e popula os três scopes:
```php
<?php

declare(strict_types=1);

namespace App\Infrastructure\Config;

use RuntimeException;

class EnvLoader
{
    public static function load(string $path): void
    {
        if (!file_exists($path)) {
            throw new RuntimeException("Arquivo .env não encontrado: {$path}");
        }

        $lines = file($path, FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);

        foreach ($lines as $line) {
            if (str_starts_with(trim($line), '#')) {
                continue;
            }

            if (str_contains($line, '=')) {
                [$name, $value] = explode('=', $line, 2);

                $name  = trim($name);
                $value = trim(trim($value), '"\'');

                putenv("{$name}={$value}");
                $_ENV[$name]    = $value;
                $_SERVER[$name] = $value;
            }
        }
    }
}
```

### 92.4 Inicialização (Bootstrap)

Carregue o `.env` no ponto de entrada da aplicação, antes de qualquer uso:
```php
<?php

declare(strict_types=1);

require_once __DIR__ . '/src/Infrastructure/Config/EnvLoader.php';

use App\Infrastructure\Config\EnvLoader;

try {
    EnvLoader::load(__DIR__ . '/.env');
} catch (\RuntimeException $e) {
    error_log($e->getMessage());
}
```

### 92.5 Tipagem Estrita (`strict_types=1`)

Sem `strict_types=1`, o PHP converte tipos automaticamente. Um CPF `"01234567890"` passado como `int` perderia o zero à esquerda (`1234567890`), corrompendo o dado. Adicione `declare(strict_types=1);` em **todos** os arquivos PHP.

---

## 93. Ecossistema cURL — Categorias de Funções

Referência rápida de todas as famílias de funções cURL, incluindo `curl_share_init_persistent` do PHP 8.5 para handles que sobrevivem entre requisições.

### 93.1 Novidade PHP 8.5: `curl_share_init_persistent`

Handles criados com `curl_share_init_persistent()` **não são destruídos ao final da requisição**. Se um handle com as mesmas opções já existir, é reutilizado automaticamente. Benefício: evita custo de handshake DNS/TLS/SSL repetido.

### 93.2 Sessão Única (Uso Básico)

*   `curl_init` / `curl_close` — Abrir e fechar sessão.
*   `curl_setopt` / `curl_setopt_array` — Definir opções (URL, headers, POST).
*   `curl_exec` — Executar a transferência.
*   `curl_getinfo` — Informações (código HTTP, tempo, tamanho).

### 93.3 Execução Múltipla (cURL Multi)

Para requisições paralelas (assíncronas):

*   `curl_multi_init` / `curl_multi_close` — Pool de execução.
*   `curl_multi_add_handle` / `curl_multi_remove_handle` — Gerenciar sessões no pool.
*   `curl_multi_exec` — Executar todas em paralelo.

### 93.4 Compartilhamento (cURL Share)

*   `curl_share_init` / `curl_share_close` — Compartilhar DNS e cookies entre conexões.
*   **`curl_share_init_persistent`** — PHP 8.5: Persistir entre requisições.

### 93.5 Diagnóstico e Erros

*   `curl_errno` / `curl_error` — Número e mensagem de erro.
*   `curl_strerror` / `curl_multi_strerror` — Traduzir códigos para texto.

### 93.6 Utilitários

*   `curl_escape` / `curl_unescape` — URL encoding/decoding.
*   `curl_version` — Versão e protocolos suportados.


---

## 94. Pipe Operator com cURL — Processamento de Respostas

O pipe operator não serve para configurar cURL (as funções de config retornam booleano), mas é ideal para o **pós-processamento** da resposta: trim → decode → transform.

### 94.1 Conceito

O Pipe Operator não encadeia funções de configuração do cURL (`curl_setopt` retorna booleano, não o handle). Use-o no **pós-processamento** da resposta.

### 94.2 Exemplo: Processar Resposta com `array_first`

Pipeline funcional: resposta bruta → trim → decode → primeiro item:
```php
<?php

declare(strict_types=1);

namespace App\Service;

final class ApiService
{
    public function fetchFirstItem(string $url): ?array
    {
        $handle = curl_init($url);
        curl_setopt($handle, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($handle, CURLOPT_TIMEOUT, 10);

        $response = curl_exec($handle);
        curl_close($handle);

        if (!is_string($response) || $response === '') {
            return null;
        }

        // Processamento funcional com Pipe (PHP 8.5)
        return $response
            |> trim(...)
            |> fn(string $json): array => json_decode($json, true) ?? []
            |> array_first(...);
    }
}
```

---

## 95. ApiClient — GET e POST com cURL

Classe reutilizável que encapsula GET e POST com JSON, validação de status HTTP e pós-processamento com pipe operator.

### 95.1 Requisição GET

Método `fetch()` com pipe para decodificação da resposta:
```php
<?php

declare(strict_types=1);

namespace App\Service;

final class ApiClient
{
    public function fetch(string $url): ?array
    {
        $handle = curl_init($url);

        curl_setopt($handle, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($handle, CURLOPT_TIMEOUT, 10);

        $response = curl_exec($handle);
        $httpCode = curl_getinfo($handle, CURLINFO_HTTP_CODE);
        curl_close($handle);

        if (!is_string($response) || $response === '' || $httpCode >= 400) {
            return null;
        }

        return $response
            |> trim(...)
            |> fn(string $json): array => json_decode($json, true) ?? [];
    }

    /**
     * Requisição POST com payload JSON.
     */
    public function create(string $url, array $payload): ?array
    {
        $handle      = curl_init($url);
        $jsonPayload = json_encode($payload);

        curl_setopt($handle, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($handle, CURLOPT_TIMEOUT, 15);
        curl_setopt($handle, CURLOPT_POST, true);
        curl_setopt($handle, CURLOPT_POSTFIELDS, $jsonPayload);
        curl_setopt($handle, CURLOPT_HTTPHEADER, [
            'Content-Type: application/json',
            'Accept: application/json',
            'Content-Length: ' . strlen($jsonPayload),
        ]);

        $response = curl_exec($handle);
        $httpCode = curl_getinfo($handle, CURLINFO_HTTP_CODE);
        curl_close($handle);

        if (!is_string($response) || $response === '' || $httpCode >= 400) {
            return null;
        }

        return $response
            |> trim(...)
            |> fn(string $json): array => json_decode($json, true) ?? [];
    }
}
```

### 95.2 Pontos-Chave

1.  **`CURLOPT_RETURNTRANSFER`:** Sem isso, `curl_exec` imprime a resposta na tela e retorna booleano.
2.  **`CURLOPT_POST`:** Muda método de GET para POST.
3.  **`Content-Type: application/json`:** Obrigatório para POST com JSON. Sem ele, o servidor rejeita com `400`.
4.  **Código HTTP:** `curl_exec` não falha em `404` ou `500` — valide `curl_getinfo` manualmente.


---

## 96. `#[\NoDiscard]` para Integrações de Rede

Ignorar o retorno de requisições HTTP causa bugs silenciosos: a API cai mas o sistema continua como se nada acontecesse. `#[\NoDiscard]` força o desenvolvedor a tratar o resultado.

### 96.1 O Problema

Ignorar o retorno de `curl_exec()` faz requisições "às cegas". Se a API cair ou retornar erro, seu sistema continua como se tudo estivesse perfeito — bugs silenciosos e desperdício de quota.

### 96.2 NotificationService com NoDiscard

POST com JSON, retorna `bool` — `#[\NoDiscard]` garante que o resultado seja capturado:
```php
<?php

declare(strict_types=1);

namespace App\Service;

final class NotificationService
{
    #[\NoDiscard]
    public function sendNotification(string $url, array $payload): bool
    {
        $handle      = curl_init($url);
        $jsonPayload = json_encode($payload);

        curl_setopt_array($handle, [
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_POST           => true,
            CURLOPT_POSTFIELDS     => $jsonPayload,
            CURLOPT_HTTPHEADER     => [
                'Content-Type: application/json',
                'Content-Length: ' . strlen($jsonPayload),
            ],
        ]);

        $response = curl_exec($handle);
        $httpCode = curl_getinfo($handle, CURLINFO_HTTP_CODE);
        curl_close($handle);

        return $response !== false && $httpCode < 400;
    }
}
```

### 96.3 Cenários de Uso

Exemplos de uso correto, incorreto e descarte intencional com `(void)`:
```php
<?php

declare(strict_types=1);

$service = new NotificationService();

// ❌ PHP 8.5 emite aviso: retorno descartado!
$service->sendNotification('https://api.exemplo.com/webhook', ['status' => 'ok']);

// ✅ Correto: captura o retorno
$isSuccess = $service->sendNotification('https://api.exemplo.com/webhook', ['status' => 'ok']);

if (!$isSuccess) {
    error_log('Falha ao enviar notificação.');
}

// ✅ Descarte intencional (fire-and-forget)
(void) $service->sendNotification('https://api.exemplo.com/ping', ['evento' => 'clique']);
```


---

## 97. Biblioteca de Segurança do Zero — PHP 8.5 Puro

Projeto final da Masterclass: biblioteca completa com CSRF (tokens time-constant), XSS (escape), sanitização com pipe, URI segura com RFC 3986, e autoloading PSR-4 nativo — tudo sem dependências externas.

### 97.1 Estrutura de Diretórios

```text
/security-lib
├── src/
│   ├── Autoloader.php
│   └── Security/
│       ├── CsrfManager.php
│       ├── InputSanitizer.php
│       ├── SafeUriBuilder.php
│       └── XssProtector.php
└── public/
    └── index.php
```

### 97.2 Autoloader PSR-4 Nativo

Usa `spl_autoload_register` com first-class callable para mapear `App\` → `src/`:
```php
<?php

declare(strict_types=1);

namespace App;

final class Autoloader
{
    public static function register(): void
    {
        spl_autoload_register(self::loadClass(...));
    }

    private static function loadClass(string $className): void
    {
        $prefix  = 'App\\';
        $baseDir = __DIR__ . '/';

        $len = strlen($prefix);
        if (strncmp($prefix, $className, $len) !== 0) {
            return;
        }

        $relativeClass = substr($className, $len);
        $file = $baseDir . str_replace('\\', '/', $relativeClass) . '.php';

        if (file_exists($file)) {
            require $file;
        }
    }
}
```

### 97.3 CsrfManager

`#[\NoDiscard]` em `isValidToken()` com `hash_equals()` para comparação time-constant:
```php
<?php

declare(strict_types=1);

namespace App\Security;

final class CsrfManager
{
    private const int TOKEN_LENGTH = 32;

    public function getToken(): string
    {
        if (session_status() === PHP_SESSION_NONE) {
            session_start();
        }

        if (empty($_SESSION['csrf_token'])) {
            $_SESSION['csrf_token'] = bin2hex(random_bytes(self::TOKEN_LENGTH));
        }

        return $_SESSION['csrf_token'];
    }

    #[\NoDiscard]
    public function isValidToken(string $submittedToken): bool
    {
        if (session_status() === PHP_SESSION_NONE) {
            session_start();
        }

        $sessionToken = $_SESSION['csrf_token'] ?? '';

        if ($sessionToken === '' || $submittedToken === '') {
            return false;
        }

        return hash_equals($sessionToken, $submittedToken);
    }
}
```

### 97.4 XssProtector

Wrapper estático para `htmlspecialchars` com `ENT_QUOTES` e `UTF-8`:
```php
<?php

declare(strict_types=1);

namespace App\Security;

final class XssProtector
{
    #[\NoDiscard]
    public static function escapeHtml(string $data): string
    {
        return htmlspecialchars($data, ENT_QUOTES, 'UTF-8');
    }
}
```

### 97.5 InputSanitizer (Pipe Operator)

`#[\NoDiscard]` garante que o email sanitizado não seja descartado:
```php
<?php

declare(strict_types=1);

namespace App\Security;

final class InputSanitizer
{
    #[\NoDiscard]
    public function sanitizeEmail(string $rawEmail): string
    {
        return $rawEmail
            |> trim(...)
            |> strtolower(...)
            |> fn(string $email): string => filter_var($email, FILTER_SANITIZE_EMAIL);
    }
}
```

### 97.6 SafeUriBuilder (RFC 3986)

Usa a extensão nativa `Uri\Rfc3986\Uri` do PHP 8.5 para parsing seguro:
```php
<?php

declare(strict_types=1);

namespace App\Security;

use Uri\Rfc3986\Uri;

final class SafeUriBuilder
{
    #[\NoDiscard]
    public function buildSecureEndpoint(string $rawUrl): Uri
    {
        return new Uri($rawUrl);
    }
}
```

### 97.7 Ponto de Entrada (index.php)

Orquestração final: carrega autoloader, valida CSRF, sanitiza input e constrói URI segura:
```php
<?php

declare(strict_types=1);

require_once __DIR__ . '/../src/Autoloader.php';
\App\Autoloader::register();

use App\Security\CsrfManager;
use App\Security\InputSanitizer;
use App\Security\XssProtector;
use App\Security\SafeUriBuilder;

$csrf       = new CsrfManager();
$sanitizer  = new InputSanitizer();
$uriBuilder = new SafeUriBuilder();

// Simulação de POST
$_POST['csrf_token'] = $csrf->getToken();
$_POST['email']      = '   Hacker@EXEMPLO.com   ';
$_POST['website']    = 'https://meusite.com/admin?login=true';

$isSafe = $csrf->isValidToken($_POST['csrf_token']);

if ($isSafe) {
    $cleanEmail = $sanitizer->sanitizeEmail($_POST['email']);
    $secureUri  = $uriBuilder->buildSecureEndpoint($_POST['website']);

    echo "E-mail: " . XssProtector::escapeHtml($cleanEmail) . PHP_EOL;
    echo "Host: " . XssProtector::escapeHtml($secureUri->getHost()) . PHP_EOL;
} else {
    http_response_code(403);
    echo "Falha de validação CSRF detectada.";
}
```
