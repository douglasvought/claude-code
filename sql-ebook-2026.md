# 📄 SQL — Do Zero ao Profissional
### Ebook Completo · Edição 2026
> Explicações em pt-BR · Código em inglês (US)
> Compatível com MySQL · PostgreSQL · SQL Server · Oracle · SQLite

---

## 📂 Sumário

1. [Introdução ao SQL](#1-introdução-ao-sql)
2. [Como o banco de dados funciona](#2-como-o-banco-de-dados-funciona)
3. [Sintaxe e estrutura SQL](#3-sintaxe-e-estrutura-sql)
4. [SELECT — Consultando dados](#4-select--consultando-dados)
5. [SELECT DISTINCT — Eliminando duplicatas](#5-select-distinct--eliminando-duplicatas)
6. [WHERE — Filtrando com precisão](#6-where--filtrando-com-precisão)
7. [ORDER BY — Ordenando resultados](#7-order-by--ordenando-resultados)
8. [AND — Todas as condições verdadeiras](#8-and--todas-as-condições-verdadeiras)
9. [OR — Pelo menos uma condição verdadeira](#9-or--pelo-menos-uma-condição-verdadeira)
10. [NOT — Negando condições](#10-not--negando-condições)
11. [INSERT INTO — Inserindo dados](#11-insert-into--inserindo-dados)
12. [Boas práticas e armadilhas comuns](#12-boas-práticas-e-armadilhas-comuns)
13. [NULL Values — A ausência de dados](#13-null-values--a-ausência-de-dados)
14. [UPDATE — Atualizando registros](#14-update--atualizando-registros)
15. [DELETE — Removendo registros](#15-delete--removendo-registros)
16. [LIMIT / TOP / FETCH FIRST — Limitando resultados](#16-limit--top--fetch-first--limitando-resultados)
17. [Funções de agregação — MIN, MAX, COUNT, SUM, AVG](#17-funções-de-agregação--min-max-count-sum-avg)
18. [LIKE e Wildcards — Busca por padrões](#18-like-e-wildcards--busca-por-padrões)
19. [IN — Verificando listas de valores](#19-in--verificando-listas-de-valores)
20. [BETWEEN — Selecionando intervalos](#20-between--selecionando-intervalos)
21. [Aliases — Nomeando colunas e tabelas](#21-aliases--nomeando-colunas-e-tabelas)
22. [JOIN — Unindo tabelas](#22-join--unindo-tabelas)
23. [INNER JOIN — Apenas correspondências](#23-inner-join--apenas-correspondências)
24. [LEFT JOIN — Todos da esquerda](#24-left-join--todos-da-esquerda)
25. [RIGHT JOIN — Todos da direita](#25-right-join--todos-da-direita)
26. [FULL JOIN — Todos de ambos os lados](#26-full-join--todos-de-ambos-os-lados)
27. [Self JOIN — Uma tabela unida a si mesma](#27-self-join--uma-tabela-unida-a-si-mesma)
28. [UNION e UNION ALL — Combinando resultados](#28-union-e-union-all--combinando-resultados)
29. [GROUP BY — Agrupando registros](#29-group-by--agrupando-registros)
30. [HAVING — Filtrando grupos](#30-having--filtrando-grupos)
31. [EXISTS — Verificando existência](#31-exists--verificando-existência)
32. [ANY e ALL — Comparando com subqueries](#32-any-e-all--comparando-com-subqueries)
33. [SELECT INTO — Criando tabelas a partir de consultas](#33-select-into--criando-tabelas-a-partir-de-consultas)
34. [INSERT INTO SELECT — Copiando dados entre tabelas](#34-insert-into-select--copiando-dados-entre-tabelas)
35. [CASE — Lógica condicional em queries](#35-case--lógica-condicional-em-queries)
36. [NULL Functions — COALESCE, IFNULL, ISNULL, NVL](#36-null-functions--coalesce-ifnull-isnull-nvl)
37. [Stored Procedures — Procedimentos armazenados](#37-stored-procedures--procedimentos-armazenados)
38. [Comentários SQL — Documentando o código](#38-comentários-sql--documentando-o-código)
39. [Operadores SQL — Referência completa](#39-operadores-sql--referência-completa)
40. [CREATE DATABASE e DROP DATABASE](#40-create-database-e-drop-database)
41. [BACKUP DATABASE — Estratégias de backup](#41-backup-database--estratégias-de-backup)
42. [CREATE TABLE — Criando tabelas](#42-create-table--criando-tabelas)
43. [DROP TABLE e TRUNCATE TABLE](#43-drop-table-e-truncate-table)
44. [ALTER TABLE — Modificando estruturas](#44-alter-table--modificando-estruturas)
45. [Constraints — Regras de integridade de dados](#45-constraints--regras-de-integridade-de-dados)
46. [NOT NULL — Tornando campos obrigatórios](#46-not-null--tornando-campos-obrigatórios)
47. [UNIQUE — Garantindo valores únicos](#47-unique--garantindo-valores-únicos)
48. [PRIMARY KEY — Identificando linhas de forma única](#48-primary-key--identificando-linhas-de-forma-única)
49. [FOREIGN KEY — Relacionando tabelas com integridade](#49-foreign-key--relacionando-tabelas-com-integridade)
50. [CHECK — Validando dados com condições](#50-check--validando-dados-com-condições)
51. [DEFAULT — Valores padrão automáticos](#51-default--valores-padrão-automáticos)
52. [CREATE INDEX — Otimizando performance de buscas](#52-create-index--otimizando-performance-de-buscas)
53. [AUTO INCREMENT — IDs automáticos por banco](#53-auto-increment--ids-automáticos-por-banco)
54. [Trabalhando com Datas](#54-trabalhando-com-datas)
55. [Views — Tabelas virtuais reutilizáveis](#55-views--tabelas-virtuais-reutilizáveis)
56. [SQL Injection — O ataque e a defesa](#56-sql-injection--o-ataque-e-a-defesa)
57. [Parameterized Queries — Consultas parametrizadas](#57-parameterized-queries--consultas-parametrizadas)
58. [Prepared Statements — Máxima segurança e performance](#58-prepared-statements--máxima-segurança-e-performance)
59. [Hospedagem SQL — Escolhendo o banco certo](#59-hospedagem-sql--escolhendo-o-banco-certo)
60. [Ordem de execução de uma query SQL](#60-ordem-de-execução-de-uma-query-sql)
61. [Subqueries — Consultas aninhadas](#61-subqueries--consultas-aninhadas)
62. [INTERSECT e EXCEPT — Operações de conjunto](#62-intersect-e-except--operações-de-conjunto)
63. [Window Functions — Funções de janela](#63-window-functions--funções-de-janela)
64. [Transactions — COMMIT, ROLLBACK e ACID](#64-transactions--commit-rollback-e-acid)
65. [Versões atuais dos bancos de dados em 2026](#65-versões-atuais-dos-bancos-de-dados-em-2026)
66. [CTEs — Common Table Expressions](#66-ctes--common-table-expressions)
67. [Funções de String — Manipulando texto](#67-funções-de-string--manipulando-texto)
68. [Funções de Data — Trabalhando com tempo](#68-funções-de-data--trabalhando-com-tempo)
69. [Funções Numéricas — Cálculos e arredondamentos](#69-funções-numéricas--cálculos-e-arredondamentos)
70. [MERGE — Upsert em uma única instrução](#70-merge--upsert-em-uma-única-instrução)

---

# 1. Introdução ao SQL

## O que é SQL?

**SQL** (Structured Query Language — Linguagem de Consulta Estruturada) é a linguagem universal para comunicação com bancos de dados relacionais. Pense no SQL como a "língua franca" do mundo dos dados: independente do banco de dados que você usa — MySQL, PostgreSQL, SQL Server, Oracle — você utilizará SQL para interagir com ele.

SQL foi criado nos laboratórios da IBM na década de 1970, tornou-se padrão **ANSI em 1986** e **ISO em 1987**. Mais de 50 anos depois, continua sendo uma das habilidades mais demandadas no mercado de tecnologia.

## Por que aprender SQL em 2026?

Em um mundo onde **dados são o novo petróleo**, saber SQL é tão essencial quanto saber usar uma planilha. Desenvolvedores, analistas de dados, cientistas de dados, administradores de sistemas e até profissionais de negócios precisam de SQL no dia a dia.

Com SQL você consegue:

| Operação | O que significa na prática |
|---|---|
| Consultar dados | Responder perguntas como "quais foram os 10 produtos mais vendidos este mês?" |
| Inserir dados | Cadastrar novos clientes, pedidos, produtos |
| Atualizar dados | Corrigir um endereço, alterar um preço |
| Deletar dados | Remover registros obsoletos ou duplicados |
| Criar estruturas | Definir novas tabelas e bancos de dados |
| Gerenciar acesso | Controlar quem pode ver ou modificar cada dado |

## SQL é um padrão — mas com dialetos

⚠️ Embora o núcleo do SQL seja padronizado, cada banco de dados possui suas **extensões proprietárias**. Isto significa que 90% do que você aprende aqui funciona em qualquer banco, mas pequenos detalhes de sintaxe podem variar.

| Banco de dados | Particularidade comum |
|---|---|
| MySQL | `LIMIT` para paginar resultados |
| SQL Server | `TOP` no lugar de `LIMIT` |
| Oracle | `ROWNUM` para limitar linhas |
| PostgreSQL | Suporte amplo ao padrão SQL + extensões avançadas |
| SQLite | Leve, embutido em aplicações, sem servidor |

Neste ebook, focaremos no **SQL padrão** que funciona em todos os bancos, indicando variações quando necessário.

---

# 2. Como o banco de dados funciona

## O conceito de RDBMS

**RDBMS** (Relational Database Management System — Sistema Gerenciador de Banco de Dados Relacional) é o software responsável por armazenar, organizar e gerenciar os dados. MySQL, PostgreSQL, SQL Server e Oracle são exemplos de RDBMS.

A palavra **relacional** vem do conceito matemático de *relação*, que na prática se traduz em **tabelas** que podem se relacionar entre si por meio de chaves.

## Tabelas, colunas e linhas

A unidade básica de armazenamento em um banco relacional é a **tabela**. Imagine uma tabela como uma planilha do Excel: ela tem **colunas** (os campos, os atributos) e **linhas** (os registros, as entradas de dados).

📄 Exemplo — tabela `Customers` (Clientes):

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|---|---|---|---|---|---|---|
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo | Ana Trujillo | Avda. Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbköp | Christina Berglund | Berguvsvägen 8 | Luleå | S-958 22 | Sweden |

Anatomia desta tabela:

- **Colunas** (campos): `CustomerID`, `CustomerName`, `ContactName`, `Address`, `City`, `PostalCode`, `Country` — cada uma representa um **atributo** do cliente
- **Linhas** (registros): cada linha representa **um cliente** específico
- **Célula**: a interseção de uma coluna com uma linha — por exemplo, a célula da linha 1 na coluna `City` contém o valor `Berlin`
- **Chave primária** (`CustomerID`): um identificador **único** para cada registro — nenhum cliente pode ter o mesmo `CustomerID`

## Como o SQL se encaixa nisto tudo?

Quando você escreve um comando SQL, você está essencialmente **fazendo uma pergunta** (ou uma instrução) ao RDBMS. Ele interpreta o comando, acessa os dados armazenados em disco e retorna o resultado para você. O SQL abstrai toda a complexidade de como os dados são fisicamente armazenados — você não precisa saber onde estão os arquivos no disco, só precisa saber **o que quer**.

---

# 3. Sintaxe e estrutura SQL

## Como um comando SQL é estruturado?

Um comando SQL é composto por **palavras-chave reservadas** combinadas com **nomes de tabelas**, **colunas** e **valores**. A estrutura mais completa de uma consulta segue esta ordem lógica:

```sql
-- Ordem de escrita de uma query SQL completa
SELECT   column1, column2         -- O que você quer ver
FROM     table_name               -- De qual tabela
WHERE    condition                -- Filtro: quais linhas
GROUP BY column1                  -- Agrupamento
HAVING   aggregate_condition      -- Filtro sobre grupos
ORDER BY column1 ASC|DESC         -- Ordenação do resultado
LIMIT    number;                  -- Quantas linhas retornar
```

Você não precisa usar todas essas cláusulas ao mesmo tempo — cada uma é opcional (exceto `SELECT` e `FROM`). Elas são usadas conforme a necessidade da consulta.

## Regras fundamentais da sintaxe

**SQL não diferencia maiúsculas de minúsculas** para palavras-chave:

```sql
-- Estes três comandos são equivalentes ao banco de dados
select * from customers;
SELECT * FROM Customers;
Select * From CUSTOMERS;
```

✅ **Convenção adotada neste ebook:** palavras-chave SQL sempre em **MAIÚSCULAS** para facilitar a leitura e diferenciá-las dos nomes de tabelas e colunas.

**O ponto e vírgula `;` encerra a instrução:**

```sql
-- O ponto e vírgula é obrigatório em vários bancos de dados
-- e altamente recomendado mesmo onde é opcional
SELECT * FROM Customers;
```

⚠️ Em ferramentas interativas (como o MySQL Workbench ou pgAdmin) você geralmente executa uma query por vez e o `;` pode ser opcional. Mas em scripts com múltiplas instruções, ele é **obrigatório** para separar cada comando.

**Comentários em SQL:**

```sql
-- Isto é um comentário de linha única (padrão SQL, funciona em todos os bancos)

/*
   Isto é um comentário
   de múltiplas linhas
*/

SELECT CustomerName  -- comentário inline ao final de uma linha
FROM Customers;
```

## Os principais grupos de comandos SQL

Os comandos SQL são divididos em categorias:

| Categoria | Sigla | Comandos | Finalidade |
|---|---|---|---|
| Linguagem de Consulta | DQL | `SELECT` | Consultar dados |
| Linguagem de Manipulação | DML | `INSERT`, `UPDATE`, `DELETE` | Manipular dados |
| Linguagem de Definição | DDL | `CREATE`, `ALTER`, `DROP` | Definir estruturas |
| Linguagem de Controle | DCL | `GRANT`, `REVOKE` | Controlar permissões |
| Linguagem de Transação | TCL | `COMMIT`, `ROLLBACK` | Gerenciar transações |

---

# 4. SELECT — Consultando dados

## O comando mais importante do SQL

O `SELECT` é, sem dúvida, o comando que você mais usará na sua carreira com SQL. Ele é responsável por **recuperar dados** de uma ou mais tabelas. Pense nele como a pergunta que você faz ao banco de dados: *"Me mostre estes dados"*.

## Sintaxe completa do SELECT

```sql
-- Forma básica: seleciona colunas específicas de uma tabela
SELECT column1, column2, column3
FROM table_name;
```

## Selecionando colunas específicas

A forma mais recomendada de usar o `SELECT` é **listando explicitamente** as colunas que você precisa:

```sql
-- Retorna apenas o nome do cliente e a cidade
-- Mais eficiente que SELECT * pois trafega menos dados
SELECT CustomerName, City
FROM Customers;
```

📄 Resultado:

| CustomerName | City |
|---|---|
| Alfreds Futterkiste | Berlin |
| Ana Trujillo | México D.F. |
| Antonio Moreno | México D.F. |
| Around the Horn | London |
| Berglunds snabbköp | Luleå |

## Selecionando todas as colunas com `SELECT *`

O asterisco `*` é um atalho para selecionar **todas as colunas** da tabela de uma vez:

```sql
-- Retorna absolutamente todas as colunas da tabela Customers
SELECT * FROM Customers;
```

⚠️ **Por que evitar `SELECT *` em produção?**

Embora seja conveniente para exploração rápida dos dados, o `SELECT *` tem desvantagens sérias em aplicações reais:

1. **Performance:** busca e trafega dados de colunas que você não precisa
2. **Fragilidade:** se alguém adicionar ou reordenar colunas na tabela, sua aplicação pode quebrar
3. **Legibilidade:** quem lê o código não sabe quais colunas são realmente usadas
4. **Segurança:** pode expor dados sensíveis (senhas, tokens, dados pessoais) acidentalmente

✅ Use `SELECT *` apenas para exploração rápida e aprendizado. Em código de aplicação, sempre liste as colunas.

## Renomeando colunas no resultado com AS

O `AS` cria um **alias** (apelido) para uma coluna no resultado. O nome original na tabela não é alterado — é apenas uma renomeação visual no retorno da consulta:

```sql
-- AS renomeia a coluna apenas no resultado da query
-- Útil para tornar o resultado mais legível ou para integração com APIs
SELECT
    CustomerName  AS name,
    City          AS city,
    Country       AS country
FROM Customers;
```

📄 Resultado:

| name | city | country |
|---|---|---|
| Alfreds Futterkiste | Berlin | Germany |
| Ana Trujillo | México D.F. | Mexico |

✅ Aliases são especialmente úteis quando você usa funções de agregação, pois os nomes das colunas gerados automaticamente (como `COUNT(*)`) podem ser confusos:

```sql
-- Sem alias: o nome da coluna no resultado seria COUNT(*)
-- Com alias: o nome fica legível e pode ser referenciado no código da aplicação
SELECT COUNT(*) AS total_customers
FROM Customers;
```

## SELECT com expressões calculadas

O `SELECT` não serve apenas para buscar colunas — você também pode usá-lo para **calcular valores**:

```sql
-- Calcula o preço com 10% de desconto diretamente na query
-- Útil para transformações simples sem precisar de código na aplicação
SELECT
    ProductName,
    Price                        AS original_price,
    Price * 0.9                  AS price_with_discount,
    Price * 0.9 * 1.0875         AS final_price_with_tax
FROM Products;
```

---

# 5. SELECT DISTINCT — Eliminando duplicatas

## O problema das duplicatas

Imagine que você precisa saber **quais países** estão cadastrados na sua base de clientes. Se você fizer um `SELECT Country FROM Customers`, o resultado trará um país para **cada cliente** — se você tem 91 clientes de 21 países diferentes, terá 91 linhas com muitas repetições.

É aí que entra o `SELECT DISTINCT`.

## Como o DISTINCT funciona

O `DISTINCT` instrui o banco de dados a retornar apenas valores **únicos**, eliminando as repetições do resultado:

```sql
-- Sem DISTINCT: retorna uma linha por cliente, com países repetidos
SELECT Country FROM Customers;
-- Resultado: Germany, Mexico, Mexico, UK, Sweden, Germany, ...

-- Com DISTINCT: retorna cada país apenas uma vez
SELECT DISTINCT Country FROM Customers;
-- Resultado: Germany, Mexico, UK, Sweden, ...
```

## Sintaxe

```sql
-- O DISTINCT é colocado imediatamente após o SELECT
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

## Contando valores únicos com COUNT + DISTINCT

Uma das combinações mais usadas é `COUNT(DISTINCT coluna)`, que conta **quantos valores únicos** existem:

```sql
-- Conta quantos países diferentes existem na base de clientes
-- Muito útil para relatórios de cobertura geográfica
SELECT COUNT(DISTINCT Country) AS total_countries
FROM Customers;
```

📄 Resultado:

| total_countries |
|---|
| 21 |

⚠️ **Atenção ao Microsoft Access:** O `COUNT(DISTINCT coluna)` não é suportado nesse banco. Use a alternativa com subquery:

```sql
-- Workaround para Microsoft Access
-- A subquery interna retorna os países únicos
-- O COUNT externo conta quantas linhas essa subquery retornou
SELECT COUNT(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);
```

## DISTINCT com múltiplas colunas

Quando você aplica `DISTINCT` em mais de uma coluna, a unicidade é avaliada pela **combinação** de todas as colunas listadas:

```sql
-- Retorna combinações únicas de cidade e país
-- Se duas cidades têm o mesmo nome mas em países diferentes, ambas aparecem
SELECT DISTINCT City, Country
FROM Customers
ORDER BY Country, City;
```

📄 Exemplo de resultado:

| City | Country |
|---|---|
| Buenos Aires | Argentina |
| São Paulo | Brazil |
| Rio de Janeiro | Brazil |
| Berlin | Germany |

✅ Note que `São Paulo` e `Rio de Janeiro` ambas aparecem — elas são cidades diferentes mesmo sendo do mesmo país. A unicidade é da **combinação** `(City, Country)`.

---

# 6. WHERE — Filtrando com precisão

## Por que filtrar dados?

Em um banco de dados real, tabelas podem ter **milhões de linhas**. Buscar todos os registros toda vez seria extremamente ineficiente — e inútil, pois você raramente precisa de todos os dados de uma vez. A cláusula `WHERE` resolve isso: ela diz ao banco de dados quais linhas você quer, **antes** de retornar o resultado.

## Sintaxe

```sql
-- WHERE é sempre colocado após o FROM
-- O banco avalia cada linha da tabela e retorna apenas as que satisfazem a condição
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

✅ A cláusula `WHERE` não é exclusiva do `SELECT`. Ela também é usada com `UPDATE` e `DELETE` — e é **absolutamente crítica** nestes casos (veremos isso nas boas práticas).

## Filtrando por texto

Valores de texto devem ser envolvidos por **aspas simples** `'`:

```sql
-- Retorna todos os clientes cujo país é 'Mexico'
-- ⚠️ SQL é case-sensitive para valores de dados na maioria dos bancos
-- 'Mexico' é diferente de 'mexico' em MySQL com collation case-sensitive
SELECT * FROM Customers
WHERE Country = 'Mexico';
```

📄 Resultado:

| CustomerID | CustomerName | Country |
|---|---|---|
| 2 | Ana Trujillo | Mexico |
| 3 | Antonio Moreno | Mexico |

## Filtrando por número

Valores numéricos **não usam aspas**:

```sql
-- Retorna o cliente com ID exatamente igual a 1
-- ⚠️ Se você colocar aspas: WHERE CustomerID = '1'
--    pode funcionar, mas é semanticamente incorreto e pode causar problemas de performance
--    pois força uma conversão de tipo implícita
SELECT * FROM Customers
WHERE CustomerID = 1;
```

## Todos os operadores de comparação

```sql
-- Igual a
SELECT * FROM Customers WHERE Country = 'Germany';

-- Diferente de (ambas as formas são equivalentes)
SELECT * FROM Customers WHERE Country <> 'Germany';
SELECT * FROM Customers WHERE Country != 'Germany';

-- Maior que
SELECT * FROM Products WHERE Price > 50;

-- Menor que
SELECT * FROM Products WHERE Price < 20;

-- Maior ou igual a
SELECT * FROM Products WHERE Price >= 18;

-- Menor ou igual a
SELECT * FROM Products WHERE Price <= 10;
```

## O operador BETWEEN — Intervalos

O `BETWEEN` é uma forma mais legível de expressar um intervalo. Ele é **inclusivo** em ambas as extremidades:

```sql
-- Seleciona produtos com preço entre 10 e 50 (inclusive)
-- Equivalente a: WHERE Price >= 10 AND Price <= 50
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 50;
```

⚠️ **BETWEEN inclui os extremos!** `BETWEEN 10 AND 50` retorna registros onde o valor é exatamente 10 ou exatamente 50.

```sql
-- Funciona também com datas
-- Retorna pedidos feitos durante o ano de 2024
SELECT * FROM Orders
WHERE OrderDate BETWEEN '2024-01-01' AND '2024-12-31';
```

## O operador LIKE — Buscando padrões

O `LIKE` é usado para buscar **padrões** em strings, utilizando dois caracteres especiais:

| Caractere | Significado | Exemplo |
|---|---|---|
| `%` | Zero ou mais caracteres quaisquer | `'A%'` → começa com A |
| `_` | Exatamente um caractere qualquer | `'_r%'` → segundo caractere é 'r' |

```sql
-- Clientes cujo nome começa com 'A'
SELECT * FROM Customers WHERE CustomerName LIKE 'A%';

-- Clientes cujo nome termina com 'a'
SELECT * FROM Customers WHERE CustomerName LIKE '%a';

-- Clientes cujo nome contém 'bert' em qualquer posição
SELECT * FROM Customers WHERE CustomerName LIKE '%bert%';

-- Clientes cujo nome tem exatamente 5 caracteres
SELECT * FROM Customers WHERE CustomerName LIKE '_____';

-- Clientes cujo nome tem 'r' como segundo caractere
SELECT * FROM Customers WHERE CustomerName LIKE '_r%';
```

⚠️ O `LIKE` pode ser **lento em colunas sem índice** quando o padrão começa com `%` (ex: `'%bert'`). Neste caso, o banco precisa verificar cada linha da tabela. Para buscas textuais avançadas, considere usar **Full-Text Search**.

## O operador IN — Lista de valores

O `IN` verifica se um valor está dentro de uma **lista**. É uma alternativa mais limpa a vários `OR`:

```sql
-- ❌ Verboso: múltiplos OR
SELECT * FROM Customers
WHERE Country = 'Germany'
   OR Country = 'France'
   OR Country = 'UK';

-- ✅ Limpo: usando IN
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');
```

```sql
-- IN também funciona com subqueries (consultas aninhadas)
-- Retorna clientes que fizeram pelo menos um pedido
SELECT * FROM Customers
WHERE CustomerID IN (
    SELECT DISTINCT CustomerID FROM Orders
);
```

## Tabela de operadores do WHERE

| Operador | Descrição | Exemplo |
|---|---|---|
| `=` | Igual a | `WHERE Status = 'active'` |
| `<>` / `!=` | Diferente de | `WHERE Status <> 'deleted'` |
| `>` | Maior que | `WHERE Age > 18` |
| `<` | Menor que | `WHERE Price < 100` |
| `>=` | Maior ou igual | `WHERE Score >= 7` |
| `<=` | Menor ou igual | `WHERE Quantity <= 0` |
| `BETWEEN` | Dentro de intervalo (inclusivo) | `WHERE Price BETWEEN 10 AND 50` |
| `LIKE` | Busca por padrão | `WHERE Name LIKE 'A%'` |
| `IN` | Dentro de uma lista | `WHERE Country IN ('BR', 'US')` |
| `IS NULL` | Valor é nulo | `WHERE Phone IS NULL` |
| `IS NOT NULL` | Valor não é nulo | `WHERE Email IS NOT NULL` |

---

# 7. ORDER BY — Ordenando resultados

## Por que a ordem importa?

Bancos de dados **não garantem** uma ordem natural de retorno dos dados. Sem um `ORDER BY`, o banco pode retornar os registros em qualquer ordem — e essa ordem pode mudar entre execuções ou após inserções e atualizações. Sempre que a ordem dos resultados importar para você, use o `ORDER BY`.

## Sintaxe

```sql
-- ORDER BY é sempre a última cláusula da query (exceto LIMIT)
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 ASC|DESC, column2 ASC|DESC, ...;
```

- `ASC` (Ascending) = ordem **crescente** — é o padrão, pode ser omitido
- `DESC` (Descending) = ordem **decrescente** — deve ser explicitado

## Ordenação numérica

```sql
-- Produtos do mais barato ao mais caro (ASC é o padrão)
SELECT ProductName, Price
FROM Products
ORDER BY Price;

-- Produtos do mais caro ao mais barato
SELECT ProductName, Price
FROM Products
ORDER BY Price DESC;
```

📄 Resultado de `ORDER BY Price DESC` (parcial):

| ProductName | Price |
|---|---|
| Côte de Blaye | 263.50 |
| Thüringer Rostbratwurst | 123.79 |
| Mishi Kobe Niku | 97.00 |

## Ordenação alfabética

Para colunas de texto, o `ORDER BY` ordena **alfabeticamente** seguindo a collation definida no banco de dados:

```sql
-- Produtos em ordem alfabética (A → Z)
SELECT ProductName FROM Products ORDER BY ProductName ASC;

-- Produtos em ordem alfabética reversa (Z → A)
SELECT ProductName FROM Products ORDER BY ProductName DESC;
```

⚠️ **Cuidado com acentos e collation:** em bancos configurados com collation `utf8_general_ci`, palavras com acento podem ser ordenadas de formas inesperadas. Garanta que seu banco use uma collation adequada para o idioma dos dados (ex: `utf8mb4_unicode_ci` para suporte completo a acentos em MySQL).

## Ordenação por múltiplas colunas

Quando você ordena por múltiplas colunas, a ordenação acontece em **cascata**: o banco primeiro ordena pela primeira coluna; registros com o mesmo valor na primeira coluna são então ordenados pela segunda coluna, e assim por diante.

```sql
-- Ordena primeiro por País (A→Z)
-- Dentro do mesmo país, ordena por Nome (A→Z)
SELECT CustomerName, City, Country
FROM Customers
ORDER BY Country, CustomerName;
```

📄 Resultado (parcial):

| CustomerName | City | Country |
|---|---|---|
| Alfreds Futterkiste | Berlin | Germany |
| Blauer See Delikatessen | Mannheim | Germany |
| Drachenblut Delikatessen | Aachen | Germany |
| Ana Trujillo | México D.F. | Mexico |
| Antonio Moreno | México D.F. | Mexico |

## Combinando ASC e DESC

Cada coluna no `ORDER BY` pode ter sua própria direção de ordenação:

```sql
-- Ordena por País crescente (A→Z)
-- Dentro do mesmo país, ordena por Nome decrescente (Z→A)
SELECT CustomerName, City, Country
FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```

## Ordenando por número da coluna (posição)

Uma forma alternativa menos recomendada é referenciar a coluna pela sua **posição** no SELECT:

```sql
-- Ordena pela 3ª coluna do SELECT (Country) em seguida pela 1ª (CustomerName)
SELECT CustomerName, City, Country
FROM Customers
ORDER BY 3, 1;
```

❌ **Evite esta prática!** Se alguém alterar a ordem das colunas no `SELECT`, a ordenação muda silenciosamente sem dar erro — um bug difícil de rastrear. Sempre use os **nomes das colunas**.

---

# 8. AND — Todas as condições verdadeiras

## Como o AND funciona

O operador `AND` é uma **porta lógica E**: ele combina duas ou mais condições e retorna um registro **somente se todas as condições forem verdadeiras** ao mesmo tempo.

Imagine que você está filtrando candidatos para uma vaga: o candidato precisa falar inglês **E** ter 3 anos de experiência **E** morar em São Paulo. Se qualquer um desses critérios não for atendido, o candidato não passa. É exatamente assim que o `AND` funciona.

## Sintaxe

```sql
-- Todas as condições devem ser TRUE para o registro ser incluído no resultado
SELECT column1, column2, ...
FROM table_name
WHERE condition1
  AND condition2
  AND condition3;
```

## Exemplos práticos

```sql
-- Retorna clientes da Espanha cujo nome começa com 'G'
-- Ambas as condições precisam ser verdadeiras simultaneamente
SELECT *
FROM Customers
WHERE Country = 'Spain'
  AND CustomerName LIKE 'G%';
```

```sql
-- Filtra com três condições ao mesmo tempo
-- Só retorna clientes do Brasil, da cidade do Rio de Janeiro, com ID > 50
SELECT *
FROM Customers
WHERE Country = 'Brazil'
  AND City = 'Rio de Janeiro'
  AND CustomerID > 50;
```

## AND com intervalos de data

O `AND` é muito usado para filtrar intervalos de data quando se prefere não usar `BETWEEN`:

```sql
-- Retorna pedidos feitos em 2024 com valor acima de 1000
SELECT OrderID, CustomerID, OrderDate, TotalAmount
FROM Orders
WHERE OrderDate >= '2024-01-01'
  AND OrderDate <= '2024-12-31'
  AND TotalAmount > 1000;
```

## A precedência do AND sobre o OR

Este é um dos pontos mais críticos do SQL e fonte de muitos bugs. O `AND` tem **precedência maior** que o `OR` — assim como a multiplicação tem precedência sobre a adição na matemática.

```sql
-- ❌ ARMADILHA: sem parênteses, a lógica não é o que parece
-- O banco avalia como: (Country = 'Spain' AND CustomerName LIKE 'G%') OR (CustomerName LIKE 'R%')
-- Resultado: todos os clientes da Espanha começando com 'G'
--          + TODOS os clientes de qualquer país começando com 'R'
SELECT * FROM Customers
WHERE Country = 'Spain'
  AND CustomerName LIKE 'G%' OR CustomerName LIKE 'R%';

-- ✅ CORRETO: parênteses forçam a avaliação que realmente queremos
-- Resultado: apenas clientes da Espanha começando com 'G' OU 'R'
SELECT * FROM Customers
WHERE Country = 'Spain'
  AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
```

⚠️ **Regra de ouro:** Sempre que combinar `AND` e `OR` na mesma query, use **parênteses** para tornar a lógica explícita e inequívoca.

---

# 9. OR — Pelo menos uma condição verdadeira

## Como o OR funciona

O operador `OR` é uma **porta lógica OU**: ele retorna um registro se **pelo menos uma** das condições for verdadeira.

Voltando à analogia da vaga de emprego: agora o critério é que o candidato fale inglês **OU** francês. Basta dominar um dos dois idiomas para passar — não precisa ter ambos.

## Sintaxe

```sql
-- Pelo menos UMA condição deve ser TRUE para o registro ser incluído
SELECT column1, column2, ...
FROM table_name
WHERE condition1
   OR condition2
   OR condition3;
```

## Exemplos práticos

```sql
-- Retorna clientes da Alemanha OU da Espanha
SELECT * FROM Customers
WHERE Country = 'Germany'
   OR Country = 'Spain';
```

```sql
-- Retorna clientes que estão em Berlin
-- OU cujo nome começa com 'G'
-- OU que são da Noruega
-- Qualquer uma dessas três condições é suficiente para incluir o registro
SELECT * FROM Customers
WHERE City = 'Berlin'
   OR CustomerName LIKE 'G%'
   OR Country = 'Norway';
```

## OR vs IN — quando preferir cada um

Para comparações de igualdade com a **mesma coluna**, o `IN` é equivalente ao `OR` porém muito mais legível:

```sql
-- ❌ Verboso com OR (especialmente quando a lista cresce)
SELECT * FROM Customers
WHERE Country = 'Germany'
   OR Country = 'France'
   OR Country = 'UK'
   OR Country = 'Italy'
   OR Country = 'Spain';

-- ✅ Limpo com IN
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK', 'Italy', 'Spain');
```

✅ Use `OR` quando as condições envolvem **colunas diferentes** ou **operadores diferentes** (LIKE, BETWEEN, etc.). Use `IN` quando você está comparando **a mesma coluna** contra uma lista de valores.

## AND vs. OR — Tabela comparativa

| Situação | Operador | Comportamento |
|---|---|---|
| Todas as condições devem ser verdadeiras | `AND` | Registro incluído somente se **todas** forem TRUE |
| Pelo menos uma condição deve ser verdadeira | `OR` | Registro incluído se **qualquer uma** for TRUE |
| Nenhuma condição pode ser verdadeira | `NOT` | Registro incluído somente se a condição for FALSE |

---

# 10. NOT — Negando condições

## Como o NOT funciona

O operador `NOT` **inverte** o resultado de uma condição: o que retornaria `TRUE` passa a retornar `FALSE` e vice-versa. É usado para **excluir** registros que satisfazem um critério.

## Sintaxe

```sql
-- NOT é colocado antes da condição que você quer negar
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```

## NOT com igualdade

```sql
-- Retorna TODOS os clientes, EXCETO os da Espanha
SELECT * FROM Customers
WHERE NOT Country = 'Spain';

-- Equivalente usando o operador de diferença (mais comum na prática)
SELECT * FROM Customers
WHERE Country <> 'Spain';
```

## NOT LIKE — Excluindo padrões

```sql
-- Retorna clientes cujo nome NÃO começa com a letra 'A'
SELECT * FROM Customers
WHERE CustomerName NOT LIKE 'A%';

-- Retorna clientes cujo e-mail NÃO é do domínio Gmail
SELECT * FROM Users
WHERE Email NOT LIKE '%@gmail.com';
```

## NOT BETWEEN — Fora de um intervalo

```sql
-- Retorna clientes com CustomerID fora do intervalo 10 a 60
-- ⚠️ Os valores extremos (10 e 60) também são excluídos
SELECT * FROM Customers
WHERE CustomerID NOT BETWEEN 10 AND 60;

-- Retorna produtos com preço fora da faixa "econômica"
SELECT * FROM Products
WHERE Price NOT BETWEEN 5 AND 30;
```

## NOT IN — Excluindo uma lista

```sql
-- Retorna clientes que NÃO estão nas cidades de Paris ou Londres
SELECT * FROM Customers
WHERE City NOT IN ('Paris', 'London');

-- Retorna clientes que ainda NÃO fizeram nenhum pedido
-- NOT IN com subquery: uma das combinações mais poderosas do SQL
SELECT * FROM Customers
WHERE CustomerID NOT IN (
    SELECT DISTINCT CustomerID FROM Orders
);
```

⚠️ **Cuidado com NULL e NOT IN!** Se a subquery ou a lista contiver um valor `NULL`, o `NOT IN` pode retornar zero resultados — este é um dos bugs mais sutis do SQL. Use `NOT EXISTS` nestes casos:

```sql
-- ✅ Mais seguro que NOT IN quando pode haver NULLs
SELECT * FROM Customers c
WHERE NOT EXISTS (
    SELECT 1 FROM Orders o WHERE o.CustomerID = c.CustomerID
);
```

## NOT com maior/menor que

O `NOT` pode ser combinado com operadores de comparação, embora na prática seja mais comum usar os operadores equivalentes:

```sql
-- Retorna clientes com CustomerID não maior que 50
-- Equivalente a: WHERE CustomerID <= 50
SELECT * FROM Customers WHERE NOT CustomerID > 50;

-- Retorna clientes com CustomerID não menor que 50
-- Equivalente a: WHERE CustomerID >= 50
SELECT * FROM Customers WHERE NOT CustomerID < 50;
```

## IS NOT NULL — Verificando valores nulos

`NULL` em SQL representa **ausência de valor** — não é zero, não é string vazia, é a ausência de qualquer dado. Para verificar NULLs, você **não pode** usar `= NULL` ou `<> NULL`. Deve usar `IS NULL` e `IS NOT NULL`:

```sql
-- ❌ INCORRETO: nunca funciona, pois NULL não é igual a nada
SELECT * FROM Customers WHERE Phone = NULL;
SELECT * FROM Customers WHERE Phone <> NULL;

-- ✅ CORRETO: IS NULL / IS NOT NULL
SELECT * FROM Customers WHERE Phone IS NULL;       -- clientes sem telefone cadastrado
SELECT * FROM Customers WHERE Phone IS NOT NULL;   -- clientes com telefone cadastrado
```

---

# 11. INSERT INTO — Inserindo dados

## Adicionando novos registros

O `INSERT INTO` é o comando responsável por **adicionar novos registros** a uma tabela existente. É a porta de entrada dos dados no banco.

## Sintaxe 1 — Especificando colunas (recomendado)

```sql
-- ✅ RECOMENDADO: lista explícita de colunas
-- Independe da ordem das colunas na tabela
-- Deixa claro quais campos estão sendo preenchidos
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);
```

## Sintaxe 2 — Omitindo os nomes das colunas

```sql
-- ⚠️ USE COM CUIDADO: omite os nomes das colunas
-- Os valores devem estar na mesma ordem que as colunas foram definidas na tabela
-- Se a estrutura da tabela mudar, este INSERT pode quebrar silenciosamente
INSERT INTO table_name
VALUES (value1, value2, value3);
```

## Exemplo completo — Inserindo um cliente

```sql
-- Inserindo um novo cliente com todos os campos
-- ⚠️ Não passamos o CustomerID pois é AUTO_INCREMENT — o banco gera automaticamente
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
```

📄 Após a inserção, o novo registro na tabela:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|---|---|---|---|---|---|---|
| 92 | Cardinal | Tom B. Erichsen | Skagen 21 | Stavanger | 4006 | Norway |

✅ O `CustomerID = 92` foi gerado **automaticamente** pelo mecanismo de auto-increment. Você não precisa (e não deve) informar o valor de colunas com `AUTO_INCREMENT` ou `IDENTITY`.

## Inserindo apenas em colunas específicas

Você pode omitir colunas no `INSERT INTO` — as colunas omitidas receberão o valor padrão (`DEFAULT`) ou `NULL`:

```sql
-- Inserindo apenas nome, cidade e país
-- As colunas ContactName, Address e PostalCode receberão NULL
INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');
```

📄 Resultado:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|---|---|---|---|---|---|---|
| 92 | Cardinal | NULL | NULL | Stavanger | NULL | Norway |

⚠️ **Atenção às restrições `NOT NULL`:** Se uma coluna está definida como `NOT NULL` sem valor padrão e você não informar um valor para ela, o banco retornará um erro. Sempre verifique as constraints da tabela antes de inserir dados.

## Inserindo múltiplas linhas de uma vez

Você pode inserir várias linhas em um único comando `INSERT INTO`:

```sql
-- ✅ Inserção em lote: muito mais eficiente que múltiplos INSERTs individuais
-- Cada conjunto de valores é separado por vírgula
-- Reduz o número de round-trips ao servidor drasticamente
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES
    ('Cardinal',      'Tom B. Erichsen', 'Skagen 21',       'Stavanger',  '4006',   'Norway'),
    ('Greasy Burger', 'Per Olsen',       'Gateveien 15',    'Sandnes',    '4306',   'Norway'),
    ('Tasty Tee',     'Finn Egan',       'Streetroad 19B',  'Liverpool',  'L1 0AA', 'UK');
```

📄 Resultado — três registros inseridos em uma única operação:

| CustomerID | CustomerName | City | Country |
|---|---|---|---|
| 92 | Cardinal | Stavanger | Norway |
| 93 | Greasy Burger | Sandnes | Norway |
| 94 | Tasty Tee | Liverpool | UK |

✅ A inserção em lote é especialmente relevante quando você está carregando grandes volumes de dados. Inserir 1000 linhas em um único `INSERT` é muito mais rápido do que 1000 `INSERT`s individuais.

## INSERT com SELECT — Copiando dados de outra tabela

Uma funcionalidade poderosa é inserir dados a partir de uma consulta `SELECT`:

```sql
-- Copia todos os clientes alemães para uma tabela de backup
-- A estrutura das colunas do SELECT deve corresponder ao INSERT INTO
INSERT INTO CustomersBackup (CustomerName, City, Country)
SELECT CustomerName, City, Country
FROM Customers
WHERE Country = 'Germany';
```

---

# 12. Boas práticas e armadilhas comuns

Esta seção consolida os padrões profissionais que separam código SQL amador de código SQL de produção.

## ✅ Escreva queries legíveis

SQL é lido muito mais vezes do que é escrito. Sempre escreva pensando na pessoa que lerá o código 6 meses depois — que pode ser você mesmo.

```sql
-- ❌ EVITE: difícil de ler, debugar e manter
SELECT CustomerName,City,Country FROM Customers WHERE Country='Brazil' AND CustomerID>10 ORDER BY CustomerName;

-- ✅ PREFIRA: indentado, claro e com alias descritivo
SELECT
    c.CustomerName   AS customer_name,
    c.City           AS city,
    c.Country        AS country
FROM Customers AS c
WHERE c.Country = 'Brazil'
  AND c.CustomerID > 10
ORDER BY c.CustomerName ASC;
```

## ✅ Evite SELECT * em produção

```sql
-- ❌ EVITE: trafega todas as colunas, mesmo as que não precisa
--           fragiliza o código quando a tabela muda
SELECT * FROM Orders;

-- ✅ PREFIRA: explícito, eficiente e resiliente a mudanças de schema
SELECT
    OrderID,
    CustomerID,
    OrderDate,
    TotalAmount
FROM Orders;
```

## ✅ Sempre use WHERE no UPDATE e DELETE

Esta é a regra mais importante desta seção. Um `UPDATE` ou `DELETE` sem `WHERE` afeta **todos** os registros da tabela — é um dos erros mais destrutivos que existem em SQL.

```sql
-- ❌ CATÁSTROFE: atualiza Country para 'Brazil' em TODOS os registros
UPDATE Customers SET Country = 'Brazil';

-- ✅ CORRETO: atualiza apenas o cliente específico
UPDATE Customers
SET Country = 'Brazil'
WHERE CustomerID = 42;

-- ❌ CATÁSTROFE: deleta TODOS os registros da tabela
DELETE FROM Customers;

-- ✅ CORRETO: deleta apenas o registro específico
DELETE FROM Customers
WHERE CustomerID = 42;
```

⚠️ **Dica de segurança:** Antes de executar um `UPDATE` ou `DELETE`, teste a cláusula `WHERE` com um `SELECT` primeiro para confirmar que está selecionando exatamente os registros corretos.

```sql
-- Passo 1: confirme com SELECT quais registros serão afetados
SELECT * FROM Customers
WHERE CustomerID = 42;

-- Passo 2: apenas após confirmar, execute o UPDATE ou DELETE
UPDATE Customers
SET Country = 'Brazil'
WHERE CustomerID = 42;
```

## ✅ Use parênteses ao combinar AND e OR

```sql
-- ❌ LÓGICA AMBÍGUA: resultado inesperado devido à precedência do AND
SELECT * FROM Customers
WHERE Country = 'Brazil' AND City = 'São Paulo' OR City = 'Rio de Janeiro';
-- Avaliado como: (Country = 'Brazil' AND City = 'São Paulo') OR (City = 'Rio de Janeiro')
-- Retorna clientes do Brasil em SP + clientes de RIO DE QUALQUER PAÍS

-- ✅ LÓGICA CLARA: parênteses tornam a intenção inequívoca
SELECT * FROM Customers
WHERE Country = 'Brazil'
  AND (City = 'São Paulo' OR City = 'Rio de Janeiro');
-- Retorna apenas clientes do Brasil que estão em SP ou RJ
```

## ✅ Prefira IN para listas, NOT EXISTS para subqueries com possíveis NULLs

```sql
-- ✅ IN é ideal para listas estáticas e pequenas
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');

-- ⚠️ NOT IN pode falhar silenciosamente se houver NULL na subquery
SELECT * FROM Customers
WHERE CustomerID NOT IN (SELECT CustomerID FROM BlacklistedCustomers);

-- ✅ NOT EXISTS é mais seguro e geralmente mais performático com subqueries
SELECT * FROM Customers c
WHERE NOT EXISTS (
    SELECT 1 FROM BlacklistedCustomers b
    WHERE b.CustomerID = c.CustomerID
);
```

## ✅ Insira em lote sempre que possível

```sql
-- ❌ INEFICIENTE: 3 round-trips ao servidor
INSERT INTO Products (ProductName, Price) VALUES ('Item A', 10.00);
INSERT INTO Products (ProductName, Price) VALUES ('Item B', 20.00);
INSERT INTO Products (ProductName, Price) VALUES ('Item C', 30.00);

-- ✅ EFICIENTE: 1 round-trip ao servidor
INSERT INTO Products (ProductName, Price)
VALUES
    ('Item A', 10.00),
    ('Item B', 20.00),
    ('Item C', 30.00);
```

## ✅ Use IS NULL e IS NOT NULL corretamente

```sql
-- ❌ NUNCA funciona: NULL não é igual a nada, nem a si mesmo
SELECT * FROM Customers WHERE Phone = NULL;
SELECT * FROM Customers WHERE Phone != NULL;

-- ✅ SEMPRE use IS NULL ou IS NOT NULL
SELECT * FROM Customers WHERE Phone IS NULL;
SELECT * FROM Customers WHERE Phone IS NOT NULL;
```

## ✅ Ordene sempre que a ordem importar

```sql
-- ❌ Sem ORDER BY: o banco pode retornar em qualquer ordem
--    A ordem pode mudar entre execuções — não confie nela
SELECT * FROM Products;

-- ✅ Com ORDER BY: ordem garantida e explícita
SELECT * FROM Products
ORDER BY Price DESC, ProductName ASC;
```

---

---

# 13. NULL Values — A ausência de dados

## O que é NULL?

`NULL` é um dos conceitos mais mal compreendidos por quem está aprendendo SQL. Muitos iniciantes confundem `NULL` com zero (`0`) ou com string vazia (`''`), mas são coisas completamente diferentes.

**`NULL` representa a ausência de qualquer valor.** É como dizer "não sabemos", "não se aplica" ou "não foi informado". Quando um campo é deixado em branco ao criar ou editar um registro, o banco armazena `NULL` naquele campo.

Veja a diferença na prática:

| Valor | O que significa |
|---|---|
| `NULL` | Ausência de dado — o valor é desconhecido ou não foi preenchido |
| `0` | Número zero — um valor concreto e conhecido |
| `''` | String vazia — uma cadeia de texto sem nenhum caractere, mas que existe |

Por exemplo: um cliente cadastrado sem telefone terá `NULL` no campo `Phone`. Um produto com desconto de zero terá `0` no campo `Discount`. Um produto com descrição em branco terá `''` no campo `Description`. São situações completamente diferentes.

## Por que NULL não funciona com operadores comuns?

Esta é a armadilha mais clássica do SQL. Como `NULL` representa o desconhecido, qualquer comparação com `NULL` usando `=`, `<>`, `>` ou qualquer outro operador matemático retorna `NULL` (que é tratado como `FALSE` em condições), nunca `TRUE`:

```sql
-- ❌ NUNCA funciona: retorna zero linhas, mesmo que existam NULLs na coluna
SELECT * FROM Customers WHERE Address = NULL;
SELECT * FROM Customers WHERE Address <> NULL;
SELECT * FROM Customers WHERE Address != NULL;

-- A lógica: NULL = NULL é NULL (desconhecido), não TRUE
-- É como perguntar: "o desconhecido é igual ao desconhecido?" — impossível saber.
```

A única forma correta de verificar valores nulos é com os operadores `IS NULL` e `IS NOT NULL`:

## IS NULL — Encontrando campos vazios

```sql
-- Sintaxe correta para verificar NULL
SELECT column_name
FROM table_name
WHERE column_name IS NULL;
```

```sql
-- Retorna todos os clientes que não têm endereço cadastrado
-- Útil para identificar registros incompletos que precisam de atenção
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;
```

📄 Resultado esperado (clientes sem endereço):

| CustomerName | ContactName | Address |
|---|---|---|
| Cardinal | Tom B. Erichsen | NULL |
| Greasy Burger | Per Olsen | NULL |

## IS NOT NULL — Encontrando campos preenchidos

```sql
-- Sintaxe para verificar campos com valor
SELECT column_name
FROM table_name
WHERE column_name IS NOT NULL;
```

```sql
-- Retorna apenas os clientes que TÊM endereço cadastrado
-- Garante que você está trabalhando com dados completos
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;
```

## NULL em cálculos e funções

`NULL` se propaga em operações matemáticas: qualquer cálculo que envolva `NULL` resulta em `NULL`:

```sql
-- Qualquer operação com NULL resulta em NULL
-- Se o campo Discount for NULL, o resultado também será NULL
SELECT ProductName, Price, Discount, Price - Discount AS final_price
FROM Products;
-- ⚠️ Se Discount for NULL, final_price também será NULL — não zero!
```

Para tratar isso, use a função `COALESCE()` ou `ISNULL()` (dependendo do banco):

```sql
-- COALESCE substitui NULL por um valor padrão (funciona em todos os bancos)
-- Se Discount for NULL, trata como 0 no cálculo
SELECT
    ProductName,
    Price,
    COALESCE(Discount, 0)            AS discount,
    Price - COALESCE(Discount, 0)    AS final_price
FROM Products;
```

## NULL e funções de agregação

As funções de agregação (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`) **ignoram valores NULL** — com uma exceção importante:

```sql
-- COUNT(*) conta TODAS as linhas, incluindo as que têm NULL em qualquer coluna
SELECT COUNT(*) AS total_rows FROM Customers;

-- COUNT(column) conta apenas linhas onde a coluna NÃO é NULL
-- Se 5 clientes não têm telefone, esses 5 não são contados aqui
SELECT COUNT(Phone) AS customers_with_phone FROM Customers;

-- AVG também ignora NULLs — calcula a média apenas sobre os valores existentes
-- ⚠️ Isso pode distorcer a média se muitos valores forem NULL
SELECT AVG(Discount) AS avg_discount FROM Products;
```

---

# 14. UPDATE — Atualizando registros

## O poder e o perigo do UPDATE

O `UPDATE` é o comando para **modificar dados já existentes** em uma tabela. É um dos comandos mais poderosos do SQL — e também um dos mais perigosos, se usado sem cuidado.

A regra mais importante ao usar `UPDATE`: **sempre use a cláusula `WHERE`**. Um `UPDATE` sem `WHERE` atualiza **todos os registros** da tabela — e em um banco de produção, isso pode ser catastrófico e irreversível.

## Sintaxe

```sql
-- O SET define quais colunas serão alteradas e para quais valores
-- O WHERE determina quais linhas serão afetadas
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

## Atualizando um único registro

A forma mais comum é atualizar um registro específico, identificado pela sua chave primária:

```sql
-- Atualiza o contato e a cidade do cliente com ID = 1
-- O CustomerID na cláusula WHERE garante que apenas UM registro será alterado
UPDATE Customers
SET ContactName = 'Alfred Schmidt',
    City        = 'Frankfurt'
WHERE CustomerID = 1;
```

📄 Antes e depois:

| CustomerID | CustomerName | ContactName | City |
|---|---|---|---|
| **Antes** | Alfreds Futterkiste | Maria Anders | Berlin |
| **Depois** | Alfreds Futterkiste | Alfred Schmidt | Frankfurt |

✅ Repare que apenas as colunas `ContactName` e `City` foram alteradas. Todas as outras permanecem intactas.

## Atualizando múltiplos registros

Quando o `WHERE` corresponde a mais de uma linha, todas elas são atualizadas:

```sql
-- Atualiza o ContactName de TODOS os clientes cujo país é 'Mexico'
-- Se existirem 10 clientes mexicanos, todos os 10 terão o ContactName alterado
UPDATE Customers
SET ContactName = 'Juan'
WHERE Country = 'Mexico';
```

📄 Resultado (todos os clientes do México tiveram o contato alterado):

| CustomerID | CustomerName | ContactName | Country |
|---|---|---|---|
| 2 | Ana Trujillo | Juan | Mexico |
| 3 | Antonio Moreno | Juan | Mexico |

## ⚠️ UPDATE sem WHERE — O maior erro do SQL

```sql
-- ❌ CATÁSTROFE TOTAL: atualiza ContactName para 'Juan' em TODOS os registros
-- Não há como desfazer sem um backup — pense bem antes de executar qualquer UPDATE
UPDATE Customers
SET ContactName = 'Juan';
```

📄 Resultado devastador:

| CustomerID | CustomerName | ContactName | Country |
|---|---|---|---|
| 1 | Alfreds Futterkiste | Juan | Germany |
| 2 | Ana Trujillo | Juan | Mexico |
| 3 | Antonio Moreno | Juan | Mexico |
| 4 | Around the Horn | Juan | UK |
| 5 | Berglunds snabbköp | Juan | Sweden |

⚠️ **Protocolo de segurança antes de todo UPDATE:**

```sql
-- Passo 1: Execute o SELECT com o mesmo WHERE para confirmar quais registros serão afetados
SELECT * FROM Customers
WHERE Country = 'Mexico';

-- Passo 2: Só após confirmar, execute o UPDATE
UPDATE Customers
SET ContactName = 'Juan'
WHERE Country = 'Mexico';
```

## UPDATE com expressão calculada

```sql
-- Aumenta o preço de todos os produtos da categoria 1 em 10%
-- O próprio valor atual da coluna é usado no cálculo
UPDATE Products
SET Price = Price * 1.10
WHERE CategoryID = 1;
```

## UPDATE com NULL — Limpando um campo

```sql
-- Define o campo PostalCode como NULL para o cliente 5
-- Útil para limpar dados inválidos ou desconhecidos
UPDATE Customers
SET PostalCode = NULL
WHERE CustomerID = 5;
```

---

# 15. DELETE — Removendo registros

## Deletar é irreversível

O `DELETE` **remove registros** de uma tabela permanentemente. Assim como o `UPDATE`, ele exige atenção máxima: um `DELETE` sem `WHERE` apaga **todos os dados** da tabela, e sem backup não há recuperação.

## Sintaxe

```sql
-- A cláusula WHERE é OBRIGATÓRIA na prática — nunca omita
DELETE FROM table_name
WHERE condition;
```

## Deletando um registro específico

```sql
-- Remove apenas o cliente chamado 'Alfreds Futterkiste'
-- ⚠️ Prefira usar a chave primária (CustomerID) ao invés do nome,
--    pois pode haver clientes com nomes similares ou idênticos
DELETE FROM Customers
WHERE CustomerName = 'Alfreds Futterkiste';
```

📄 Resultado — o cliente com ID 1 foi removido:

| CustomerID | CustomerName | Country |
|---|---|---|
| 2 | Ana Trujillo | Mexico |
| 3 | Antonio Moreno | Mexico |
| 4 | Around the Horn | UK |
| 5 | Berglunds snabbköp | Sweden |

✅ **Melhor prática:** sempre delete pela chave primária:

```sql
-- ✅ Mais seguro: usa o ID único, sem risco de deletar registros errados
DELETE FROM Customers
WHERE CustomerID = 1;
```

## Deletando todos os registros — mas mantendo a tabela

É possível apagar todos os dados de uma tabela sem destruir sua estrutura (colunas, índices, constraints permanecem intactos):

```sql
-- Remove TODOS os dados da tabela, mas a tabela em si continua existindo
-- Útil para limpar tabelas temporárias ou de staging
DELETE FROM Customers;
```

⚠️ Em tabelas grandes, `DELETE FROM table` pode ser lento pois registra cada linha removida no log de transações. Para isso, use `TRUNCATE TABLE` (onde disponível):

```sql
-- TRUNCATE é muito mais rápido para apagar todos os dados
-- ⚠️ Mas não pode ser usado com WHERE e geralmente não dispara triggers
TRUNCATE TABLE Customers;
```

## DELETE vs DROP TABLE — Diferença fundamental

```sql
-- DELETE: remove os DADOS, mas a tabela permanece
DELETE FROM Customers;

-- DROP TABLE: remove os DADOS e a própria TABELA (estrutura, índices, tudo)
-- ❌ Irreversível — use com extremo cuidado
DROP TABLE Customers;
```

| Comando | Remove dados | Remove a tabela | Reversível? |
|---|---|---|---|
| `DELETE FROM table` | ✅ Sim | ❌ Não | ✅ Com ROLLBACK |
| `TRUNCATE TABLE` | ✅ Sim | ❌ Não | ❌ Geralmente não |
| `DROP TABLE` | ✅ Sim | ✅ Sim | ❌ Não |

## DELETE com subquery

```sql
-- Remove todos os clientes que nunca fizeram um pedido
-- A subquery retorna os IDs dos clientes COM pedidos
-- O NOT IN exclui esses IDs, deixando apenas os que não têm pedidos
DELETE FROM Customers
WHERE CustomerID NOT IN (
    SELECT DISTINCT CustomerID FROM Orders
);
```

---

# 16. LIMIT / TOP / FETCH FIRST — Limitando resultados

## Por que limitar resultados?

Em tabelas de produção com milhões de registros, uma query sem limite pode demorar minutos para executar e retornar dados desnecessários. Limitar o número de linhas retornadas é essencial para **performance** e **paginação** de dados.

O desafio: cada banco de dados usa uma sintaxe diferente para isso.

## Sintaxe por banco de dados

```sql
-- MySQL e MariaDB: LIMIT
SELECT * FROM Customers
LIMIT 3;

-- SQL Server e MS Access: TOP
SELECT TOP 3 * FROM Customers;

-- Oracle 12+: FETCH FIRST
SELECT * FROM Customers
FETCH FIRST 3 ROWS ONLY;

-- PostgreSQL: suporta LIMIT (padrão MySQL) e também FETCH FIRST
SELECT * FROM Customers
LIMIT 3;
```

📄 Todos os exemplos acima retornam os **3 primeiros registros** da tabela:

| CustomerID | CustomerName | Country |
|---|---|---|
| 1 | Alfreds Futterkiste | Germany |
| 2 | Ana Trujillo | Mexico |
| 3 | Antonio Moreno | Mexico |

## LIMIT com WHERE — Filtrando e limitando

```sql
-- MySQL: retorna os 3 primeiros clientes alemães
SELECT * FROM Customers
WHERE Country = 'Germany'
LIMIT 3;

-- SQL Server: equivalente
SELECT TOP 3 * FROM Customers
WHERE Country = 'Germany';

-- Oracle: equivalente
SELECT * FROM Customers
WHERE Country = 'Germany'
FETCH FIRST 3 ROWS ONLY;
```

## LIMIT com ORDER BY — O uso mais importante

A combinação de `ORDER BY` + `LIMIT` é uma das mais usadas na prática. Sem o `ORDER BY`, o "primeiro" registro não tem significado concreto. Com ele, você pode buscar os N maiores, menores, mais recentes, etc.:

```sql
-- MySQL: os 3 produtos mais caros
SELECT ProductName, Price
FROM Products
ORDER BY Price DESC
LIMIT 3;

-- SQL Server: equivalente
SELECT TOP 3 ProductName, Price
FROM Products
ORDER BY Price DESC;

-- Oracle: equivalente
SELECT ProductName, Price
FROM Products
ORDER BY Price DESC
FETCH FIRST 3 ROWS ONLY;
```

📄 Resultado:

| ProductName | Price |
|---|---|
| Côte de Blaye | 263.50 |
| Thüringer Rostbratwurst | 123.79 |
| Mishi Kobe Niku | 97.00 |

## TOP com PERCENT — Porcentagem dos registros

No SQL Server e MS Access, você pode limitar por porcentagem:

```sql
-- SQL Server: retorna os primeiros 50% dos registros da tabela
SELECT TOP 50 PERCENT * FROM Customers;

-- Oracle: equivalente
SELECT * FROM Customers
FETCH FIRST 50 PERCENT ROWS ONLY;
```

## Paginação com LIMIT e OFFSET

Para implementar **paginação** (página 1, página 2, etc.), use `LIMIT` com `OFFSET`:

```sql
-- MySQL/PostgreSQL: paginação — 10 registros por página
-- Página 1: linhas 1 a 10
SELECT * FROM Products ORDER BY ProductID LIMIT 10 OFFSET 0;

-- Página 2: linhas 11 a 20
SELECT * FROM Products ORDER BY ProductID LIMIT 10 OFFSET 10;

-- Página 3: linhas 21 a 30
SELECT * FROM Products ORDER BY ProductID LIMIT 10 OFFSET 20;

-- Fórmula: OFFSET = (numero_da_pagina - 1) * registros_por_pagina
```

```sql
-- SQL Server: paginação equivalente (usando OFFSET-FETCH)
SELECT * FROM Products
ORDER BY ProductID
OFFSET 10 ROWS        -- pula os primeiros 10
FETCH NEXT 10 ROWS ONLY;  -- pega os próximos 10
```

---

# 17. Funções de Agregação — MIN, MAX, COUNT, SUM, AVG

## O que são funções de agregação?

Funções de agregação realizam **cálculos sobre um conjunto de valores** e retornam um **único resultado**. Em vez de retornar linha por linha, elas consolidam os dados em uma resposta: qual é o maior preço? Quantos clientes existem? Qual é a receita total?

As cinco funções de agregação mais importantes do SQL são:

| Função | O que faz | Ignora NULL? |
|---|---|---|
| `MIN()` | Retorna o menor valor | ✅ Sim |
| `MAX()` | Retorna o maior valor | ✅ Sim |
| `COUNT()` | Conta o número de linhas/valores | ⚠️ Depende do uso |
| `SUM()` | Soma os valores de uma coluna numérica | ✅ Sim |
| `AVG()` | Calcula a média dos valores | ✅ Sim |

## MIN() — O menor valor

`MIN()` retorna o **menor valor** de uma coluna. Funciona com números, texto (alfabeticamente) e datas (o mais antigo):

```sql
-- Retorna o menor preço entre todos os produtos
SELECT MIN(Price) AS lowest_price
FROM Products;
```

📄 Resultado:

| lowest_price |
|---|
| 2.50 |

```sql
-- MIN com texto: retorna o nome de produto que vem primeiro alfabeticamente
SELECT MIN(ProductName) AS first_alphabetically
FROM Products;

-- MIN com data: retorna a data de nascimento mais antiga (funcionário mais velho)
SELECT MIN(BirthDate) AS earliest_birthdate
FROM Employees;

-- MIN por grupo: menor preço de cada categoria
-- GROUP BY divide os produtos por categoria antes de aplicar MIN()
SELECT CategoryID, MIN(Price) AS lowest_price
FROM Products
GROUP BY CategoryID;
```

⚠️ Sempre use `AS` para nomear o resultado — sem alias, a coluna se chama literalmente `MIN(Price)`, difícil de referenciar no código.

## MAX() — O maior valor

`MAX()` retorna o **maior valor** de uma coluna. Segue a mesma lógica do `MIN()`, mas na direção oposta:

```sql
-- Retorna o maior preço entre todos os produtos
SELECT MAX(Price) AS highest_price
FROM Products;
```

📄 Resultado:

| highest_price |
|---|
| 263.50 |

```sql
-- MAX com data: retorna a contratação mais recente
SELECT MAX(HireDate) AS most_recent_hire
FROM Employees;

-- MAX por grupo: produto mais caro de cada categoria
SELECT CategoryID, MAX(Price) AS highest_price
FROM Products
GROUP BY CategoryID;
```

## COUNT() — Contando linhas

`COUNT()` conta registros, mas seu comportamento varia conforme o argumento:

```sql
-- COUNT(*): conta TODAS as linhas, incluindo as que têm NULL em alguma coluna
-- Responde: "quantos produtos existem na tabela?"
SELECT COUNT(*) AS total_products
FROM Products;

-- COUNT(column): conta apenas as linhas onde a coluna NÃO é NULL
-- Responde: "quantos produtos têm nome cadastrado?"
SELECT COUNT(ProductName) AS products_with_name
FROM Products;

-- COUNT(DISTINCT column): conta apenas valores únicos, ignorando NULLs
-- Responde: "quantos preços diferentes existem?"
SELECT COUNT(DISTINCT Price) AS unique_prices
FROM Products;
```

📄 Comparação dos três comportamentos:

| Consulta | O que conta | Resultado típico |
|---|---|---|
| `COUNT(*)` | Todas as linhas | 77 |
| `COUNT(ProductName)` | Linhas sem NULL na coluna | 77 (se não há nulos) |
| `COUNT(DISTINCT Price)` | Valores únicos não nulos | 62 (se há preços repetidos) |

```sql
-- COUNT com WHERE: conta apenas os que satisfazem a condição
SELECT COUNT(ProductID) AS expensive_products
FROM Products
WHERE Price > 20;

-- COUNT por grupo: quantos produtos existem em cada categoria
SELECT CategoryID, COUNT(*) AS total_products
FROM Products
GROUP BY CategoryID
ORDER BY total_products DESC;
```

## SUM() — Somando valores

`SUM()` calcula a **soma total** de uma coluna numérica, ignorando NULLs:

```sql
-- Soma total de todas as quantidades vendidas
SELECT SUM(Quantity) AS total_quantity
FROM OrderDetails;
```

```sql
-- SUM com WHERE: soma apenas os itens do produto 11
SELECT SUM(Quantity) AS total_sold
FROM OrderDetails
WHERE ProductID = 11;

-- SUM por pedido: total de itens de cada pedido
SELECT OrderID, SUM(Quantity) AS total_quantity
FROM OrderDetails
GROUP BY OrderID
ORDER BY total_quantity DESC;
```

### SUM com expressão — Calculando receita

Uma das aplicações mais poderosas do `SUM()` é calcular receita multiplicando quantidade por preço:

```sql
-- Supondo que cada item custe 10 reais
-- SUM() pode receber uma expressão, não só uma coluna
SELECT SUM(Quantity * 10) AS total_revenue
FROM OrderDetails;

-- Versão real: usando o preço real do produto via JOIN
-- SUM(preço * quantidade) = receita total de todas as vendas
SELECT SUM(od.Quantity * p.Price) AS total_revenue
FROM OrderDetails AS od
LEFT JOIN Products AS p ON od.ProductID = p.ProductID;
```

## AVG() — Calculando a média

`AVG()` retorna a **média aritmética** dos valores de uma coluna, ignorando NULLs:

```sql
-- Preço médio de todos os produtos
SELECT AVG(Price) AS average_price
FROM Products;
```

📄 Resultado:

| average_price |
|---|
| 28.87 |

```sql
-- AVG com WHERE: média de preço da categoria 1
SELECT AVG(Price) AS avg_price_category_1
FROM Products
WHERE CategoryID = 1;

-- AVG por grupo: preço médio de cada categoria
SELECT CategoryID, AVG(Price) AS avg_price
FROM Products
GROUP BY CategoryID
ORDER BY avg_price DESC;
```

### AVG em subquery — Comparando com a média

Uma das combinações mais úteis: usar `AVG()` em uma subquery para filtrar registros acima ou abaixo da média:

```sql
-- Retorna todos os produtos com preço ACIMA da média geral
-- A subquery é executada primeiro, calcula a média,
-- e o resultado é usado como filtro no WHERE externo
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products)
ORDER BY Price DESC;
```

📄 Resultado (produtos mais caros que a média de ~$28.87):

| ProductName | Price |
|---|---|
| Côte de Blaye | 263.50 |
| Thüringer Rostbratwurst | 123.79 |
| Mishi Kobe Niku | 97.00 |

---

# 18. LIKE e Wildcards — Busca por padrões

## O que é busca por padrão?

Às vezes você não sabe exatamente o valor que está buscando, mas conhece parte dele. O `LIKE` resolve isso: ele permite buscar registros onde uma coluna de texto **corresponde a um padrão** definido com caracteres especiais chamados **wildcards** (curingas).

## Os dois wildcards universais

Dois wildcards funcionam em todos os bancos de dados:

| Wildcard | Representa | Exemplo | Resultado |
|---|---|---|---|
| `%` | Zero ou mais caracteres quaisquer | `'A%'` | Começa com A |
| `_` | Exatamente um único caractere | `'_r%'` | Segundo caractere é 'r' |

## O wildcard % — Flexível e poderoso

```sql
-- Começa com 'a' (seguido de qualquer coisa)
SELECT * FROM Customers WHERE CustomerName LIKE 'a%';

-- Termina com 'a' (qualquer coisa antes)
SELECT * FROM Customers WHERE CustomerName LIKE '%a';

-- Contém 'or' em qualquer posição
SELECT * FROM Customers WHERE CustomerName LIKE '%or%';

-- Começa com 'La' (case-insensitive na maioria dos bancos)
SELECT * FROM Customers WHERE CustomerName LIKE 'La%';

-- Começa com 'b' E termina com 's'
SELECT * FROM Customers WHERE CustomerName LIKE 'b%s';

-- Contém 'mer' em qualquer posição
SELECT * FROM Customers WHERE CustomerName LIKE '%mer%';

-- Começa com 'a' OU começa com 'b'
SELECT * FROM Customers
WHERE CustomerName LIKE 'a%' OR CustomerName LIKE 'b%';
```

## O wildcard _ — Precisão de posição

O `_` substitui **exatamente um caractere** — não mais, não menos:

```sql
-- Cidade com qualquer primeiro caractere, seguido de 'ondon'
-- Encontra: London (L + ondon), por exemplo
SELECT * FROM Customers WHERE City LIKE '_ondon';

-- Cidade que começa com 'L', tem 3 caracteres no meio, termina com 'on'
-- Encontra: Lisbon (L + isb + on) = 6 caracteres
SELECT * FROM Customers WHERE City LIKE 'L___on';

-- Clientes cujo nome tem 'r' na segunda posição
SELECT * FROM Customers WHERE CustomerName LIKE '_r%';

-- Nome com pelo menos 3 caracteres começando com 'a'
-- 'a' + pelo menos 2 chars quaisquer (__ = exatamente 2, depois % = qualquer coisa)
SELECT * FROM Customers WHERE CustomerName LIKE 'a__%';
```

## Combinando % e _ com AND/OR

```sql
-- Cidades que têm exatamente 6 caracteres (6 underscores)
SELECT * FROM Customers WHERE City LIKE '______';

-- Clientes cujo nome começa com 'A' e tem pelo menos 5 caracteres
SELECT * FROM Customers WHERE CustomerName LIKE 'A____%';

-- Nomes que começam com 'a' ou 'b', com pelo menos 3 caracteres
SELECT * FROM Customers
WHERE CustomerName LIKE 'a__%' OR CustomerName LIKE 'b__%';
```

## Wildcards avançados — Suporte varia por banco

Além de `%` e `_`, alguns bancos oferecem wildcards mais específicos:

```sql
-- SQL Server e MS Access: [] — qualquer um dos caracteres dentro dos colchetes
-- Retorna clientes começando com 'b', 's' ou 'p'
SELECT * FROM Customers WHERE CustomerName LIKE '[bsp]%';

-- SQL Server e MS Access: [a-f] — qualquer caractere no intervalo de 'a' a 'f'
SELECT * FROM Customers WHERE CustomerName LIKE '[a-f]%';

-- SQL Server e MS Access: [^bsp] — qualquer caractere NÃO seja 'b', 's' ou 'p'
SELECT * FROM Customers WHERE CustomerName LIKE '[^bsp]%';
```

⚠️ `[]`, `^` e `-` dentro de colchetes **não funcionam** em MySQL e PostgreSQL. Para esses bancos, use expressões regulares:

```sql
-- MySQL: usando REGEXP para o mesmo efeito de [bsp]%
SELECT * FROM Customers WHERE CustomerName REGEXP '^[bsp]';

-- PostgreSQL: usando SIMILAR TO ou ~
SELECT * FROM Customers WHERE CustomerName SIMILAR TO '[bsp]%';
```

## LIKE sem wildcard — Correspondência exata

Quando você usa `LIKE` sem nenhum wildcard, ele funciona como `=`:

```sql
-- Equivalente a: WHERE Country = 'Spain'
-- Raramente usado assim — prefira o operador = para clareza
SELECT * FROM Customers WHERE Country LIKE 'Spain';
```

## Tabela de wildcards por banco de dados

| Wildcard | MySQL | PostgreSQL | SQL Server | Oracle | MS Access |
|---|---|---|---|---|---|
| `%` | ✅ | ✅ | ✅ | ✅ | `*` |
| `_` | ✅ | ✅ | ✅ | ✅ | `?` |
| `[abc]` | ❌ | ✅ (SIMILAR TO) | ✅ | ❌ | ✅ |
| `[a-z]` | ❌ | ✅ (SIMILAR TO) | ✅ | ❌ | ✅ |
| `[^abc]` | ❌ | ❌ | ✅ | ❌ | `!` |
| `{}` (escape) | ❌ | ❌ | ❌ | ✅ | ❌ |

## ⚠️ Performance e LIKE

O `LIKE` com `%` no **início** do padrão (ex: `'%palavra'`) é especialmente lento em tabelas grandes, pois o banco não consegue usar índices e precisa varrer linha por linha:

```sql
-- ❌ LENTO: % no início impede uso de índice
SELECT * FROM Products WHERE ProductName LIKE '%syrup';

-- ✅ RÁPIDO: % apenas no final permite uso de índice
SELECT * FROM Products WHERE ProductName LIKE 'anise%';
```

Para buscas textuais avançadas em grandes volumes de dados, considere usar **Full-Text Search** (disponível no MySQL, PostgreSQL e SQL Server), que é significativamente mais eficiente.

---

# 19. IN — Verificando listas de valores

## Por que o IN existe?

Imagine que você precisa buscar clientes da Alemanha, França ou Reino Unido. Com `OR`, seria:

```sql
SELECT * FROM Customers
WHERE Country = 'Germany'
   OR Country = 'France'
   OR Country = 'UK';
```

Funciona, mas fica verboso conforme a lista cresce. O operador `IN` resolve isso de forma elegante.

## Sintaxe

```sql
-- IN verifica se o valor da coluna está dentro da lista fornecida
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, value3, ...);
```

## IN com lista estática

```sql
-- Retorna clientes da Alemanha, França ou Reino Unido
-- Muito mais legível que três ORs separados
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');

-- IN também funciona com números
SELECT * FROM Products
WHERE CategoryID IN (1, 2, 4);

-- IN com datas
SELECT * FROM Orders
WHERE OrderDate IN ('2024-01-15', '2024-02-20', '2024-03-10');
```

## NOT IN — Excluindo uma lista

```sql
-- Retorna todos os clientes que NÃO são da Alemanha, França ou Reino Unido
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

## IN com subquery — A combinação mais poderosa

O `IN` se torna extremamente poderoso quando combinado com subqueries. Em vez de uma lista estática, você pode usar o resultado de outra consulta como a lista de valores:

```sql
-- Retorna todos os clientes que têm pelo menos um pedido registrado
-- A subquery retorna os CustomerIDs que existem na tabela Orders
-- O IN filtra apenas os clientes cujo ID aparece nessa lista
SELECT * FROM Customers
WHERE CustomerID IN (
    SELECT DISTINCT CustomerID FROM Orders
);
```

```sql
-- Retorna todos os clientes que NUNCA fizeram um pedido
-- NOT IN com subquery para encontrar o complemento
SELECT * FROM Customers
WHERE CustomerID NOT IN (
    SELECT DISTINCT CustomerID FROM Orders
);
```

📄 Este é um padrão clássico: se a primeira query retornou 74 clientes com pedidos, e a tabela tem 91 clientes no total, a segunda retornará 17 clientes sem pedidos.

## ⚠️ Armadilha: NOT IN com NULL na subquery

Este é um dos bugs mais sutis e difíceis de debugar em SQL. Se a subquery usada com `NOT IN` retornar qualquer valor `NULL`, o resultado inteiro da query será vazio:

```sql
-- ⚠️ PERIGOSO: se Orders.CustomerID tiver algum NULL,
--    a query inteira retorna zero linhas — um bug silencioso e confuso
SELECT * FROM Customers
WHERE CustomerID NOT IN (
    SELECT CustomerID FROM Orders  -- e se algum CustomerID for NULL aqui?
);

-- ✅ SEGURO: use NOT EXISTS quando há risco de NULL na subquery
-- NOT EXISTS é imune a NULLs e geralmente mais eficiente
SELECT * FROM Customers AS c
WHERE NOT EXISTS (
    SELECT 1 FROM Orders AS o
    WHERE o.CustomerID = c.CustomerID
);

-- ✅ ALTERNATIVA: use IS NOT NULL na subquery para garantir
SELECT * FROM Customers
WHERE CustomerID NOT IN (
    SELECT CustomerID FROM Orders WHERE CustomerID IS NOT NULL
);
```

## IN vs OR — Quando usar cada um

| Situação | Recomendação |
|---|---|
| Mesma coluna, lista pequena e estática | `IN` — mais limpo e legível |
| Mesma coluna, lista dinâmica (subquery) | `IN` com subquery |
| Colunas diferentes | `OR` — IN não se aplica |
| Lista grande com possível NULL | `EXISTS` / `NOT EXISTS` |
| Lista de 1 item | `=` — mais simples e claro |

---

# 20. BETWEEN — Selecionando intervalos

## O que é o BETWEEN?

O operador `BETWEEN` é uma forma expressiva e legível de filtrar valores dentro de um **intervalo contínuo**. Em vez de escrever duas condições com `>=` e `<=`, você declara explicitamente o início e o fim do intervalo que quer. Funciona com números, texto (ordem alfabética) e datas.

A regra mais importante: o `BETWEEN` é **inclusivo** — os valores nas extremidades do intervalo **estão incluídos** no resultado.

## Sintaxe

```sql
-- Seleciona registros onde column_name está entre value1 e value2 (inclusive)
-- Equivalente a: WHERE column_name >= value1 AND column_name <= value2
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

## BETWEEN com números

```sql
-- Retorna produtos com preço entre 10 e 20 (inclusive)
-- Produtos com preço exatamente 10 ou exatamente 20 também são retornados
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20;

-- Equivalente explícito com operadores de comparação
SELECT * FROM Products
WHERE Price >= 10 AND Price <= 20;
```

📄 Produtos da tabela de exemplo que seriam retornados:

| ProductID | ProductName | Price |
|---|---|---|
| 1 | Chais | 18.00 |
| 2 | Chang | 19.00 |
| 3 | Aniseed Syrup | 10.00 |

## NOT BETWEEN — Fora do intervalo

O `NOT BETWEEN` é o oposto: retorna registros **fora** do intervalo especificado. Os valores das extremidades também são excluídos:

```sql
-- Retorna produtos com preço FORA do intervalo entre 10 e 20
-- Produtos com preço exatamente 10 ou 20 NÃO são retornados
SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;
```

## BETWEEN combinado com IN

É possível combinar `BETWEEN` com outras cláusulas para criar filtros mais específicos:

```sql
-- Retorna produtos com preço entre 10 e 20
-- E que pertencem às categorias 1, 2 ou 3
-- Ambas as condições devem ser satisfeitas simultaneamente
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
  AND CategoryID IN (1, 2, 3);
```

## BETWEEN com texto — Ordem alfabética

Quando usado com strings, o `BETWEEN` filtra pela **ordem alfabética** (collation). O resultado inclui todos os valores que ficam entre as duas strings fornecidas, na ordem do dicionário:

```sql
-- Retorna produtos cujo nome está alfabeticamente entre 'Geitost' e 'Louisiana Hot Spiced Okra'
-- Inclui nomes que começam com G, H, I, J, K e L (até essa string específica)
SELECT * FROM Products
WHERE ProductName BETWEEN 'Geitost' AND 'Louisiana Hot Spiced Okra'
ORDER BY ProductName;
```

```sql
-- Retorna produtos fora desse intervalo alfabético
SELECT * FROM Products
WHERE ProductName NOT BETWEEN 'Geitost' AND 'Louisiana Hot Spiced Okra'
ORDER BY ProductName;
```

⚠️ **Atenção com acentos:** a ordem alfabética depende da **collation** do banco. Em collations case-insensitive, `'a'` e `'A'` são tratados igualmente. Em collations com suporte a acentos, `'é'` pode vir antes ou depois de `'e'` dependendo da configuração.

## BETWEEN com datas — Filtros temporais

Uma das aplicações mais comuns do `BETWEEN` é filtrar por períodos de tempo:

```sql
-- Retorna todos os pedidos realizados no mês de julho de 1996
-- O formato da data deve corresponder ao formato do banco (YYYY-MM-DD é o padrão ISO)
SELECT * FROM Orders
WHERE OrderDate BETWEEN '1996-07-01' AND '1996-07-31';
```

📄 Resultado (pedidos de julho/1996):

| OrderID | CustomerID | OrderDate |
|---|---|---|
| 10248 | 90 | 1996-07-04 |
| 10249 | 81 | 1996-07-05 |
| 10250 | 34 | 1996-07-08 |
| 10251 | 84 | 1996-07-08 |
| 10252 | 76 | 1996-07-09 |

⚠️ **Cuidado com datas e horários:** quando a coluna armazena `DATETIME` (data + hora), o valor `'1996-07-31'` é interpretado como `'1996-07-31 00:00:00'`. Pedidos feitos às 14h do dia 31 **não seriam incluídos**. Para cobrir o dia inteiro, use:

```sql
-- ✅ Cobre todo o dia 31 de julho, incluindo qualquer horário
SELECT * FROM Orders
WHERE OrderDate BETWEEN '1996-07-01' AND '1996-07-31 23:59:59';

-- ✅ Alternativa mais robusta usando o primeiro dia do mês seguinte
SELECT * FROM Orders
WHERE OrderDate >= '1996-07-01'
  AND OrderDate < '1996-08-01';
```

## BETWEEN vs >= e <= — Quando usar cada um

```sql
-- Ambos são equivalentes em resultado
-- Use BETWEEN quando quiser deixar o intervalo mais explícito e legível
SELECT * FROM Products WHERE Price BETWEEN 10 AND 20;
SELECT * FROM Products WHERE Price >= 10 AND Price <= 20;
```

✅ Prefira `BETWEEN` quando o intervalo é o foco principal do filtro — é mais fácil de ler e comunicar a intenção. Prefira `>=` e `<=` quando precisa de intervalos assimétricos ou quando está filtrando com `DATETIME` incluindo horários.

---

# 21. Aliases — Nomeando colunas e tabelas

## O que são aliases?

Um **alias** é um nome temporário que você atribui a uma coluna ou tabela dentro de uma query. Ele existe apenas durante a execução daquela consulta — o nome real da coluna ou tabela no banco de dados não é alterado.

Aliases são criados com a palavra-chave `AS` e servem para tornar o resultado mais legível, simplificar referências a expressões complexas e facilitar a escrita de queries com múltiplas tabelas.

## Sintaxe

```sql
-- Alias para coluna
SELECT column_name AS alias_name
FROM table_name;

-- Alias para tabela
SELECT column_name(s)
FROM table_name AS alias_name;
```

## Alias para colunas — Tornando o resultado legível

O caso de uso mais comum: renomear colunas no resultado para que façam mais sentido para quem vai consumir os dados:

```sql
-- Sem alias: as colunas se chamam CustomerID e CustomerName no resultado
SELECT CustomerID, CustomerName FROM Customers;

-- Com alias: as colunas se chamam ID e Customer no resultado
-- Útil para APIs, relatórios e integrações que esperam nomes específicos
SELECT CustomerID AS ID, CustomerName AS Customer
FROM Customers;
```

📄 Resultado com aliases:

| ID | Customer |
|---|---|
| 1 | Alfreds Futterkiste |
| 2 | Ana Trujillo |
| 3 | Antonio Moreno |

## Aliases com espaços no nome

Quando o alias precisa conter espaços, envolva-o em **colchetes** `[]` (SQL Server / MS Access) ou **aspas duplas** `""` (padrão SQL, funciona na maioria dos bancos):

```sql
-- SQL Server e MS Access: colchetes
SELECT ProductName AS [My Great Products]
FROM Products;

-- Padrão SQL (MySQL, PostgreSQL, Oracle): aspas duplas
SELECT ProductName AS "My Great Products"
FROM Products;
```

⚠️ **Recomendação:** evite espaços em aliases sempre que possível. Prefira `snake_case` (`my_great_products`) ou `camelCase` (`myGreatProducts`) para compatibilidade máxima.

## Alias para concatenar colunas

Uma das aplicações mais práticas: combinar múltiplas colunas em uma única coluna formatada no resultado:

```sql
-- SQL Server: usa o operador + para concatenar strings
SELECT
    CustomerName,
    Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS full_address
FROM Customers;

-- MySQL e MariaDB: usa a função CONCAT()
SELECT
    CustomerName,
    CONCAT(Address, ', ', PostalCode, ', ', City, ', ', Country) AS full_address
FROM Customers;

-- Oracle: usa o operador || para concatenar
SELECT
    CustomerName,
    Address || ', ' || PostalCode || ' ' || City || ', ' || Country AS full_address
FROM Customers;

-- PostgreSQL: aceita tanto CONCAT() quanto ||
SELECT
    CustomerName,
    CONCAT(Address, ', ', PostalCode, ', ', City, ', ', Country) AS full_address
FROM Customers;
```

📄 Resultado:

| CustomerName | full_address |
|---|---|
| Alfreds Futterkiste | Obere Str. 57, 12209 Berlin, Germany |
| Ana Trujillo | Avda. Constitución 2222, 05021 México D.F., Mexico |

## Alias para tabelas — Essencial nos JOINs

Aliases de tabela são especialmente importantes em queries com `JOIN`, pois evitam repetir nomes longos de tabelas e resolvem ambiguidades quando duas tabelas têm colunas com o mesmo nome:

```sql
-- Sem alias de tabela: verboso e repetitivo
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
JOIN Orders ON Customers.CustomerID = Orders.CustomerID;

-- Com alias de tabela: compacto e legível
-- 'c' é o alias para Customers, 'o' é o alias para Orders
SELECT c.CustomerName, o.OrderID
FROM Customers AS c
JOIN Orders AS o ON c.CustomerID = o.CustomerID;
```

```sql
-- Alias resolve ambiguidade: CustomerID existe em ambas as tabelas
-- Sem qualificar com alias/tabela, o banco retornaria um erro
SELECT
    c.CustomerID,      -- claramente o CustomerID da tabela Customers
    c.CustomerName,
    o.OrderID,
    o.OrderDate
FROM Customers AS c
JOIN Orders AS o ON c.CustomerID = o.CustomerID
WHERE c.Country = 'Brazil'
ORDER BY o.OrderDate DESC;
```

## Quando usar aliases — Resumo

| Situação | Benefício |
|---|---|
| Funções de agregação: `COUNT(*)` | Transforma em nome legível: `total_records` |
| Colunas calculadas: `Price * 0.9` | Dá um nome ao resultado: `discounted_price` |
| Nomes longos de colunas | Simplifica referências no código |
| Queries com múltiplas tabelas | Evita repetição e resolve ambiguidades |
| Subqueries | Obrigatório — subqueries sempre precisam de alias |
| Concatenação de colunas | Cria uma coluna composta com nome claro |

---

# 22. JOIN — Unindo tabelas

## Por que precisamos de JOIN?

Em bancos de dados bem projetados, as informações são distribuídas em **múltiplas tabelas** para evitar redundância — um princípio chamado **normalização**. Por exemplo: em vez de guardar o nome do cliente em cada pedido, guardamos apenas o `CustomerID` e buscamos o nome na tabela de clientes quando necessário.

O `JOIN` é o mecanismo que **reconecta** essas informações: ele combina linhas de duas ou mais tabelas com base em uma coluna relacionada entre elas.

## O conceito de chave relacionada

Para entender o JOIN, é preciso entender como as tabelas se relacionam. Observe:

📄 Tabela `Orders` (pedido):

| OrderID | CustomerID | OrderDate |
|---|---|---|
| 10308 | 2 | 1996-09-18 |

📄 Tabela `Customers` (cliente):

| CustomerID | CustomerName | Country |
|---|---|---|
| 2 | Ana Trujillo | Mexico |

A coluna `CustomerID` aparece nas duas tabelas. Na tabela `Orders`, ela é uma **chave estrangeira** (foreign key) que referencia a **chave primária** da tabela `Customers`. O JOIN une as duas tabelas por essa coluna:

```sql
-- Une Orders e Customers pela coluna CustomerID
-- Retorna o nome do cliente junto com os dados do pedido
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

📄 Resultado:

| OrderID | CustomerName | OrderDate |
|---|---|---|
| 10308 | Ana Trujillo | 1996-09-18 |
| 10365 | Antonio Moreno | 1996-11-27 |
| 10383 | Around the Horn | 1996-11-15 |

## Os quatro tipos de JOIN

| Tipo | O que retorna |
|---|---|
| `INNER JOIN` | Apenas linhas com correspondência nas **duas** tabelas |
| `LEFT JOIN` | **Todas** as linhas da tabela esquerda + correspondências da direita (NULL se não houver) |
| `RIGHT JOIN` | **Todas** as linhas da tabela direita + correspondências da esquerda (NULL se não houver) |
| `FULL JOIN` | **Todas** as linhas de **ambas** as tabelas (NULL onde não houver correspondência) |

Cada tipo responde a uma pergunta diferente — escolher o tipo errado de JOIN é uma das fontes mais comuns de resultados incorretos em SQL.

---

# 23. INNER JOIN — Apenas correspondências

## Como o INNER JOIN funciona

O `INNER JOIN` — ou simplesmente `JOIN` (pois INNER é o tipo padrão) — retorna **apenas as linhas que têm correspondência nas duas tabelas**. Se um registro existe em uma tabela mas não tem par na outra, ele é silenciosamente descartado do resultado.

Visualize assim: é a **interseção** dos dois conjuntos de dados.

## Sintaxe

```sql
-- INNER JOIN e JOIN são equivalentes — INNER é opcional
SELECT column_name(s)
FROM table1
INNER JOIN table2 ON table1.column_name = table2.column_name;
```

## Exemplo fundamental — Produtos e Categorias

```sql
-- Une Products com Categories para mostrar o nome da categoria de cada produto
-- Produtos sem CategoryID válido NÃO aparecerão no resultado
SELECT
    p.ProductID,
    p.ProductName,
    c.CategoryName
FROM Products AS p
INNER JOIN Categories AS c ON p.CategoryID = c.CategoryID;
```

📄 Resultado (parcial):

| ProductID | ProductName | CategoryName |
|---|---|---|
| 1 | Chais | Beverages |
| 2 | Chang | Beverages |
| 3 | Aniseed Syrup | Condiments |
| 4 | Chef Anton's Cajun Seasoning | Condiments |

⚠️ **Importante:** Se existir um produto com `CategoryID = 99` e essa categoria não existir na tabela `Categories`, esse produto **não aparecerá** no resultado. O INNER JOIN exige correspondência em ambos os lados.

## Qualificando colunas com nome de tabela

Quando os nomes das colunas existem em apenas uma das tabelas, você não precisa qualificar. Mas quando uma coluna existe em ambas (como `CategoryID` nesse exemplo), é **obrigatório** especificar de qual tabela ela vem:

```sql
-- ✅ Sem ambiguidade: CategoryID qualificado com o nome da tabela
SELECT
    Products.ProductID,
    Products.ProductName,
    Categories.CategoryName,
    Products.CategoryID        -- obrigatório qualificar: existe nas duas tabelas
FROM Products
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID;

-- ✅ Com aliases: mais compacto e igualmente claro
SELECT
    p.ProductID,
    p.ProductName,
    c.CategoryName,
    p.CategoryID
FROM Products AS p
INNER JOIN Categories AS c ON p.CategoryID = c.CategoryID;
```

## INNER JOIN com múltiplas tabelas

Você pode encadear quantos `INNER JOIN` forem necessários para unir três, quatro ou mais tabelas:

```sql
-- Une três tabelas: Orders, Customers e Shippers
-- Mostra o pedido com o nome do cliente e o nome da transportadora
SELECT
    o.OrderID,
    c.CustomerName,
    s.ShipperName,
    o.OrderDate
FROM Orders AS o
INNER JOIN Customers AS c  ON o.CustomerID  = c.CustomerID
INNER JOIN Shippers  AS s  ON o.ShipperID   = s.ShipperID
ORDER BY o.OrderDate DESC;
```

📄 Tabela `Shippers` usada no exemplo:

| ShipperID | ShipperName | Phone |
|---|---|---|
| 1 | Speedy Express | (503) 555-9831 |
| 2 | United Package | (503) 555-3199 |
| 3 | Federal Shipping | (503) 555-9931 |

📄 Resultado (parcial):

| OrderID | CustomerName | ShipperName | OrderDate |
|---|---|---|---|
| 10308 | Ana Trujillo | Federal Shipping | 1996-09-18 |
| 10309 | Rattlesnake Canyon | Speedy Express | 1996-09-19 |

✅ **Dica de leitura:** ao encadear múltiplos JOINs, leia da esquerda para a direita: "comece com Orders, junte com Customers onde os CustomerIDs batem, depois junte com Shippers onde os ShipperIDs batem".

---

# 24. LEFT JOIN — Todos da esquerda

## Como o LEFT JOIN funciona

O `LEFT JOIN` (também chamado `LEFT OUTER JOIN`) garante que **todas as linhas da tabela da esquerda** (a que vem antes do JOIN) apareçam no resultado — independentemente de haver ou não correspondência na tabela da direita.

Quando não há correspondência na tabela da direita, as colunas dessa tabela aparecem como `NULL` no resultado.

Pense assim: o LEFT JOIN é como uma pesquisa onde você lista **todos os clientes** e, para cada um, mostra os pedidos que ele fez — mas **clientes sem pedido também aparecem**, com `NULL` na coluna de pedido.

## Sintaxe

```sql
-- LEFT JOIN e LEFT OUTER JOIN são equivalentes — OUTER é opcional
SELECT column_name(s)
FROM table1                          -- tabela "esquerda" — aparece sempre
LEFT JOIN table2                     -- tabela "direita" — aparece só se houver match
ON table1.column_name = table2.column_name;
```

## Exemplo — Clientes com e sem pedidos

```sql
-- Retorna TODOS os clientes, com seus pedidos quando existirem
-- Clientes que nunca compraram aparecem com OrderID = NULL
SELECT
    c.CustomerName,
    o.OrderID,
    o.OrderDate
FROM Customers AS c
LEFT JOIN Orders AS o ON c.CustomerID = o.CustomerID
ORDER BY c.CustomerName;
```

📄 Resultado (parcial — observe os NULLs):

| CustomerName | OrderID | OrderDate |
|---|---|---|
| Alfreds Futterkiste | NULL | NULL |
| Ana Trujillo | 10308 | 1996-09-18 |
| Antonio Moreno | NULL | NULL |
| Around the Horn | 10355 | 1996-12-16 |
| Around the Horn | 10383 | 1996-11-15 |

✅ `Alfreds Futterkiste` e `Antonio Moreno` aparecem mesmo sem pedidos — seus campos de `Orders` ficam `NULL`. `Around the Horn` aparece duas vezes porque tem dois pedidos.

## Encontrando registros sem correspondência — Anti-JOIN

Uma das aplicações mais poderosas do LEFT JOIN é identificar registros que **não têm par** na outra tabela. Isso é chamado de **anti-JOIN** e é realizado filtrando os NULLs:

```sql
-- Retorna APENAS os clientes que NUNCA fizeram um pedido
-- Lógica: LEFT JOIN traz todos os clientes, WHERE filtra os que têm NULL em Orders
SELECT
    c.CustomerName,
    c.Country
FROM Customers AS c
LEFT JOIN Orders AS o ON c.CustomerID = o.CustomerID
WHERE o.CustomerID IS NULL
ORDER BY c.CustomerName;
```

Este padrão (`LEFT JOIN ... WHERE right_table.column IS NULL`) é preferível ao `NOT IN` com subquery quando há risco de NULLs, pois é mais robusto e geralmente mais eficiente.

## LEFT JOIN vs INNER JOIN — A diferença prática

```sql
-- INNER JOIN: retorna apenas os 74 clientes que têm pedidos
SELECT c.CustomerName, o.OrderID
FROM Customers AS c
INNER JOIN Orders AS o ON c.CustomerID = o.CustomerID;

-- LEFT JOIN: retorna todos os 91 clientes
-- Os 17 que não têm pedidos aparecem com OrderID = NULL
SELECT c.CustomerName, o.OrderID
FROM Customers AS c
LEFT JOIN Orders AS o ON c.CustomerID = o.CustomerID;
```

---

# 25. RIGHT JOIN — Todos da direita

## Como o RIGHT JOIN funciona

O `RIGHT JOIN` (também chamado `RIGHT OUTER JOIN`) é o espelho do LEFT JOIN: garante que **todas as linhas da tabela da direita** (a que vem depois do JOIN) apareçam no resultado. Se não houver correspondência na tabela da esquerda, as colunas dela aparecem como `NULL`.

Na prática, o `RIGHT JOIN` é menos usado que o `LEFT JOIN`, pois qualquer `RIGHT JOIN` pode ser reescrito como um `LEFT JOIN` invertendo a ordem das tabelas — e a maioria dos desenvolvedores mantém o padrão de usar LEFT JOIN para consistência.

## Sintaxe

```sql
-- RIGHT JOIN e RIGHT OUTER JOIN são equivalentes
SELECT column_name(s)
FROM table1                          -- tabela "esquerda" — aparece só se houver match
RIGHT JOIN table2                    -- tabela "direita" — aparece sempre
ON table1.column_name = table2.column_name;
```

## Exemplo — Todos os funcionários e seus pedidos

```sql
-- Retorna TODOS os funcionários, com os pedidos que processaram
-- Funcionários que não processaram nenhum pedido aparecem com OrderID = NULL
SELECT
    o.OrderID,
    e.LastName,
    e.FirstName
FROM Orders AS o
RIGHT JOIN Employees AS e ON o.EmployeeID = e.EmployeeID
ORDER BY o.OrderID;
```

📄 Resultado (parcial):

| OrderID | LastName | FirstName |
|---|---|---|
| NULL | Davolio | Nancy |
| 10309 | Leverling | Janet |
| 10310 | Fuller | Andrew |

✅ `Davolio` aparece mesmo sem ter processado nenhum pedido — porque está na tabela **direita** (`Employees`), que é a tabela preservada no RIGHT JOIN.

## Reescrevendo RIGHT JOIN como LEFT JOIN

Como mencionado, qualquer `RIGHT JOIN` pode ser convertido em `LEFT JOIN` simplesmente invertendo a ordem das tabelas. A maioria dos times prefere padronizar em LEFT JOIN para legibilidade:

```sql
-- ✅ RIGHT JOIN original
SELECT o.OrderID, e.LastName, e.FirstName
FROM Orders AS o
RIGHT JOIN Employees AS e ON o.EmployeeID = e.EmployeeID;

-- ✅ LEFT JOIN equivalente (mesmo resultado, ordem das tabelas invertida)
SELECT o.OrderID, e.LastName, e.FirstName
FROM Employees AS e
LEFT JOIN Orders AS o ON e.EmployeeID = o.EmployeeID;
```

⚠️ **Atenção:** o MySQL não suporta `FULL OUTER JOIN` nativamente. Nesse banco, é comum reescrever usando `LEFT JOIN UNION RIGHT JOIN` — veremos isso no próximo capítulo.

---

# 26. FULL JOIN — Todos de ambos os lados

## Como o FULL JOIN funciona

O `FULL JOIN` (também chamado `FULL OUTER JOIN`) é o tipo de JOIN mais abrangente: retorna **todas as linhas de ambas as tabelas**. Quando há correspondência, as colunas de ambos os lados são preenchidas. Quando não há, as colunas do lado sem correspondência ficam como `NULL`.

Pense assim: é a **união** completa dos dois conjuntos, incluindo registros que existem apenas em uma das tabelas.

⚠️ **Atenção:** FULL JOIN pode gerar **resultados muito grandes**, especialmente se poucas linhas têm correspondência entre as tabelas.

## Sintaxe

```sql
-- FULL JOIN e FULL OUTER JOIN são equivalentes
SELECT column_name(s)
FROM table1
FULL JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```

## Exemplo — Todos os clientes e todos os pedidos

```sql
-- Retorna TODOS os clientes e TODOS os pedidos
-- Clientes sem pedido: OrderID = NULL
-- Pedidos sem cliente válido: CustomerName = NULL
SELECT
    c.CustomerName,
    o.OrderID
FROM Customers AS c
FULL JOIN Orders AS o ON c.CustomerID = o.CustomerID
ORDER BY c.CustomerName;
```

📄 Resultado (parcial — observe os NULLs nos dois sentidos):

| CustomerName | OrderID |
|---|---|
| NULL | 10309 |
| NULL | 10310 |
| Alfreds Futterkiste | NULL |
| Ana Trujillo | 10308 |
| Antonio Moreno | NULL |

- Linhas com `CustomerName = NULL`: pedidos que não têm cliente correspondente na tabela `Customers`
- Linhas com `OrderID = NULL`: clientes que nunca fizeram pedido

## FULL JOIN no MySQL — Workaround obrigatório

O MySQL **não suporta** `FULL OUTER JOIN`. Para obter o mesmo resultado, combine `LEFT JOIN` e `RIGHT JOIN` com `UNION`:

```sql
-- MySQL: simulando FULL OUTER JOIN com UNION de LEFT + RIGHT JOIN
-- UNION elimina duplicatas automaticamente

SELECT c.CustomerName, o.OrderID
FROM Customers AS c
LEFT JOIN Orders AS o ON c.CustomerID = o.CustomerID

UNION

SELECT c.CustomerName, o.OrderID
FROM Customers AS c
RIGHT JOIN Orders AS o ON c.CustomerID = o.CustomerID

ORDER BY CustomerName;
```

## Comparativo visual dos tipos de JOIN

```
Tabela A (Customers)    Tabela B (Orders)
[  A only  |  A∩B  |  B only  ]

INNER JOIN  →  apenas A∩B
LEFT JOIN   →  A only + A∩B
RIGHT JOIN  →  A∩B + B only
FULL JOIN   →  A only + A∩B + B only
```

## Tabela de decisão — Qual JOIN usar?

| Pergunta que você quer responder | JOIN recomendado |
|---|---|
| Quais clientes fizeram pedidos? | `INNER JOIN` |
| Todos os clientes, com ou sem pedidos? | `LEFT JOIN` |
| Quais clientes NUNCA fizeram pedidos? | `LEFT JOIN ... WHERE b.id IS NULL` |
| Todos os funcionários, com ou sem vendas? | `RIGHT JOIN` (ou `LEFT JOIN` invertido) |
| Quais funcionários NUNCA venderam? | `RIGHT JOIN ... WHERE a.id IS NULL` |
| Todos os registros de ambas as tabelas? | `FULL JOIN` |
| Registros que existem em A mas não em B? | `LEFT JOIN ... WHERE b.id IS NULL` |
| Registros que existem em B mas não em A? | `RIGHT JOIN ... WHERE a.id IS NULL` |

---

# 27. Self JOIN — Uma tabela unida a si mesma

## O que é um Self JOIN?

Um **Self JOIN** é um JOIN onde a tabela é unida com ela mesma. À primeira vista parece estranho — por que uma tabela se juntaria consigo? — mas é extremamente útil quando os dados de uma tabela se relacionam internamente.

Casos de uso clássicos: encontrar clientes da mesma cidade, funcionários que têm o mesmo gerente, ou qualquer situação onde você precisa comparar linhas de uma tabela com outras linhas da **mesma** tabela.

## Como funciona na prática

Como SQL não permite referenciar a mesma tabela duas vezes pelo mesmo nome, você usa **dois aliases diferentes** para a mesma tabela — fazendo o banco tratá-la como se fossem duas tabelas distintas:

```sql
-- Sintaxe do Self JOIN: a mesma tabela referenciada com dois aliases
-- T1 e T2 são aliases para a mesma tabela física
SELECT column_name(s)
FROM table1 AS T1, table1 AS T2
WHERE condition;
```

## Exemplo — Encontrando clientes da mesma cidade

```sql
-- Encontra pares de clientes que moram na mesma cidade
-- A é o alias de um cliente, B é o alias de outro cliente — ambos da tabela Customers
-- A condição A.CustomerID <> B.CustomerID evita que um cliente seja pareado consigo mesmo
SELECT
    A.CustomerName AS customer_1,
    B.CustomerName AS customer_2,
    A.City          AS city
FROM Customers AS A, Customers AS B
WHERE A.CustomerID <> B.CustomerID    -- evita auto-pareamento
  AND A.City = B.City                 -- condição de match: mesma cidade
ORDER BY A.City;
```

📄 Resultado (parcial):

| customer_1 | customer_2 | city |
|---|---|---|
| Ana Trujillo | Antonio Moreno | México D.F. |
| Antonio Moreno | Ana Trujillo | México D.F. |
| Around the Horn | B's Beverages | London |
| B's Beverages | Around the Horn | London |

⚠️ Observe que os pares aparecem **duplicados** — (Ana, Antonio) e (Antonio, Ana). Para retornar cada par apenas uma vez, use `<` ao invés de `<>`:

```sql
-- ✅ Evita duplicação de pares: cada par aparece apenas uma vez
SELECT
    A.CustomerName AS customer_1,
    B.CustomerName AS customer_2,
    A.City          AS city
FROM Customers AS A, Customers AS B
WHERE A.CustomerID < B.CustomerID    -- garante ordem: só (A,B), nunca (B,A)
  AND A.City = B.City
ORDER BY A.City;
```

## Self JOIN com hierarquias — Funcionários e gerentes

O caso de uso mais comum em aplicações reais: tabelas hierárquicas onde uma coluna referencia outra linha da mesma tabela (ex: `ManagerID` que aponta para outro `EmployeeID`):

```sql
-- Exemplo com tabela de funcionários onde cada um tem um gerente (que também é funcionário)
-- emp = o funcionário, mgr = o gerente do funcionário
SELECT
    emp.FirstName  AS employee_name,
    mgr.FirstName  AS manager_name
FROM Employees AS emp
LEFT JOIN Employees AS mgr ON emp.ManagerID = mgr.EmployeeID
ORDER BY manager_name, employee_name;
```

✅ O `LEFT JOIN` é usado aqui para incluir o CEO (que não tem gerente — `ManagerID = NULL`).

---

# 28. UNION e UNION ALL — Combinando resultados

## O que é UNION?

Enquanto o `JOIN` combina tabelas **horizontalmente** (adicionando colunas), o `UNION` combina resultados **verticalmente** (empilhando linhas de múltiplas queries). Ele serve para unir o resultado de dois ou mais `SELECT` em um único conjunto de dados.

## Regras obrigatórias do UNION

Para que o `UNION` funcione, as queries combinadas devem seguir três regras:

```
✅ Regra 1: Mesmo número de colunas em cada SELECT
✅ Regra 2: Colunas compatíveis em tipo de dado (ex: texto com texto, número com número)
✅ Regra 3: Colunas na mesma ordem em cada SELECT
```

## UNION — Eliminando duplicatas automaticamente

O `UNION` por padrão retorna apenas valores **distintos** — duplicatas são removidas automaticamente:

```sql
-- Retorna os países únicos que aparecem em Customers OU em Suppliers (sem repetição)
-- Se UK aparece em ambas as tabelas, aparece apenas uma vez no resultado
SELECT Country FROM Customers
UNION
SELECT Country FROM Suppliers
ORDER BY Country;
```

⚠️ **O nome das colunas** no resultado vem sempre do **primeiro** `SELECT`. Mesmo que a segunda query use nomes diferentes, o resultado adota os nomes da primeira.

## UNION ALL — Mantendo duplicatas

Use `UNION ALL` quando quiser **todas** as linhas, incluindo as repetidas. É mais rápido que `UNION` pois não precisa fazer a deduplicação:

```sql
-- Retorna TODOS os países de ambas as tabelas — incluindo repetições
-- Se UK aparece 5x em Customers e 3x em Suppliers, aparece 8x no resultado
SELECT Country FROM Customers
UNION ALL
SELECT Country FROM Suppliers
ORDER BY Country;
```

| Operador | Duplicatas | Performance | Quando usar |
|---|---|---|---|
| `UNION` | Remove | Mais lento | Quando você precisa de valores únicos |
| `UNION ALL` | Mantém | Mais rápido | Quando duplicatas são válidas ou irrelevantes |

## UNION com WHERE — Filtrando antes de unir

Cada `SELECT` pode ter seu próprio `WHERE`. O filtro se aplica individualmente antes da união:

```sql
-- Retorna cidades únicas da Alemanha, de Customers E Suppliers
SELECT City, Country FROM Customers
WHERE Country = 'Germany'
UNION
SELECT City, Country FROM Suppliers
WHERE Country = 'Germany'
ORDER BY City;
```

## UNION com coluna de origem — Identificando a fonte

Um uso elegante e prático: adicionar uma coluna literal para identificar de qual tabela veio cada linha:

```sql
-- Cria uma coluna 'record_type' que indica se o contato é Cliente ou Fornecedor
-- A string literal 'Customer' e 'Supplier' são valores fixos, não colunas
SELECT 'Customer' AS record_type, ContactName, City, Country
FROM Customers
UNION
SELECT 'Supplier', ContactName, City, Country
FROM Suppliers
ORDER BY record_type, ContactName;
```

📄 Resultado (parcial):

| record_type | ContactName | City | Country |
|---|---|---|---|
| Customer | Ana Trujillo | México D.F. | Mexico |
| Customer | Maria Anders | Berlin | Germany |
| Supplier | Charlotte Cooper | London | UK |
| Supplier | Regina Murphy | Ann Arbor | USA |

✅ Este padrão é muito útil para consolidar dados de múltiplas fontes em relatórios únicos.

## UNION ALL para simular FULL JOIN no MySQL

Como vimos no capítulo de FULL JOIN, o MySQL não suporta esse tipo de JOIN nativamente. A solução é usar `UNION ALL` combinando LEFT JOIN e RIGHT JOIN:

```sql
-- MySQL: simulação de FULL OUTER JOIN
SELECT c.CustomerName, o.OrderID
FROM Customers AS c
LEFT JOIN Orders AS o ON c.CustomerID = o.CustomerID

UNION ALL

SELECT c.CustomerName, o.OrderID
FROM Customers AS c
RIGHT JOIN Orders AS o ON c.CustomerID = o.CustomerID
WHERE c.CustomerID IS NULL    -- evita duplicar as linhas que já vieram do LEFT JOIN

ORDER BY CustomerName;
```

---

# 29. GROUP BY — Agrupando registros

## O que faz o GROUP BY?

O `GROUP BY` **agrupa linhas que têm o mesmo valor** em uma ou mais colunas, transformando múltiplas linhas em uma única linha de sumário por grupo. É quase sempre combinado com funções de agregação (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`) para calcular estatísticas por grupo.

Pense assim: em vez de ver todos os 91 clientes individualmente, o `GROUP BY Country` "colapsa" os clientes país a país e você pode contar, somar ou calcular médias dentro de cada país.

## Sintaxe

```sql
-- GROUP BY vem depois do WHERE e antes do HAVING e ORDER BY
SELECT column1, aggregate_function(column2)
FROM table_name
WHERE condition
GROUP BY column1
ORDER BY column_name;
```

## Exemplo fundamental — Clientes por país

```sql
-- Conta quantos clientes existem em cada país
-- Sem GROUP BY, COUNT retornaria um único total para toda a tabela
-- Com GROUP BY, retorna um total POR PAÍS
SELECT
    Country,
    COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country;
```

📄 Resultado (parcial):

| Country | total_customers |
|---|---|
| Germany | 11 |
| Mexico | 5 |
| UK | 7 |
| France | 11 |
| Sweden | 2 |

```sql
-- Mesmo exemplo, mas ordenado do país com mais para o com menos clientes
SELECT
    Country,
    COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country
ORDER BY total_customers DESC;
```

## GROUP BY com múltiplas colunas

Você pode agrupar por mais de uma coluna. O grupo é formado pela **combinação única** de todas as colunas listadas:

```sql
-- Agrupa por País E Cidade — cada combinação única forma um grupo
-- Responde: "quantos clientes existem em cada cidade de cada país?"
SELECT
    Country,
    City,
    COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country, City
ORDER BY Country, total_customers DESC;
```

## GROUP BY com JOIN — Análise cruzada

Combinar `GROUP BY` com `JOIN` permite análises muito poderosas:

```sql
-- Conta quantos pedidos cada transportadora processou
-- JOIN une Orders com Shippers para ter o nome da transportadora
-- GROUP BY agrupa por nome da transportadora
SELECT
    s.ShipperName,
    COUNT(o.OrderID) AS total_orders
FROM Orders AS o
LEFT JOIN Shippers AS s ON o.ShipperID = s.ShipperID
GROUP BY s.ShipperName
ORDER BY total_orders DESC;
```

📄 Resultado:

| ShipperName | total_orders |
|---|---|
| United Package | 74 |
| Federal Shipping | 68 |
| Speedy Express | 54 |

## GROUP BY com SUM — Receita por categoria

```sql
-- Receita total por categoria de produto
-- Cruza OrderDetails com Products para ter o preço real de cada item vendido
SELECT
    p.CategoryID,
    SUM(od.Quantity * p.Price) AS total_revenue
FROM OrderDetails AS od
INNER JOIN Products AS p ON od.ProductID = p.ProductID
GROUP BY p.CategoryID
ORDER BY total_revenue DESC;
```

⚠️ **Regra fundamental do GROUP BY:** toda coluna no `SELECT` que **não** é uma função de agregação **deve** aparecer no `GROUP BY`. Caso contrário, o banco retornará um erro (ou um resultado imprevisível em versões antigas do MySQL):

```sql
-- ❌ ERRO: City não está nem no GROUP BY nem é uma agregação
SELECT Country, City, COUNT(*) AS total
FROM Customers
GROUP BY Country;

-- ✅ CORRETO: City incluída no GROUP BY
SELECT Country, City, COUNT(*) AS total
FROM Customers
GROUP BY Country, City;
```

---

# 30. HAVING — Filtrando grupos

## Por que o HAVING existe?

Você já sabe que o `WHERE` filtra **linhas individuais** antes do agrupamento. Mas e se você quiser filtrar os **grupos** depois de calculada a agregação? Por exemplo: "mostre apenas os países com mais de 5 clientes".

O `WHERE` não funciona para isso porque nele ainda não existe o resultado de `COUNT()`. É para isso que existe o `HAVING` — ele filtra grupos **depois** da agregação acontecer.

## Sintaxe

```sql
-- A ordem das cláusulas é: WHERE → GROUP BY → HAVING → ORDER BY
SELECT column1, aggregate_function(column2)
FROM table_name
WHERE condition                        -- filtra linhas ANTES do agrupamento
GROUP BY column1
HAVING aggregate_condition             -- filtra GRUPOS DEPOIS do agrupamento
ORDER BY column_name;
```

## WHERE vs HAVING — A diferença fundamental

```sql
-- WHERE: filtra linhas ANTES de agrupar
-- Aqui, removemos clientes inativos ANTES de contar por país
SELECT Country, COUNT(CustomerID) AS total
FROM Customers
WHERE IsActive = 1                    -- filtra linhas individuais
GROUP BY Country;

-- HAVING: filtra grupos DEPOIS de agregar
-- Aqui, calculamos o total por país e DEPOIS filtramos os que têm > 5
SELECT Country, COUNT(CustomerID) AS total
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;         -- filtra grupos já calculados
```

| Cláusula | Atua sobre | Momento | Pode usar agregação? |
|---|---|---|---|
| `WHERE` | Linhas individuais | Antes do GROUP BY | ❌ Não |
| `HAVING` | Grupos | Depois do GROUP BY | ✅ Sim |

## Exemplo — Países com mais de 5 clientes

```sql
-- Retorna apenas os países que têm MAIS de 5 clientes cadastrados
SELECT
    Country,
    COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5
ORDER BY total_customers DESC;
```

📄 Resultado:

| Country | total_customers |
|---|---|
| USA | 13 |
| Germany | 11 |
| France | 11 |
| Brazil | 9 |
| UK | 7 |

## HAVING com ORDER BY

```sql
-- Países com mais de 5 clientes, ordenados do maior para o menor
SELECT
    Country,
    COUNT(CustomerID) AS total_customers
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5
ORDER BY total_customers DESC;
```

## Combinando WHERE e HAVING

`WHERE` e `HAVING` podem ser usados juntos — cada um filtrando em seu momento correto:

```sql
-- Passo 1 (WHERE): considera apenas os funcionários Davolio e Fuller
-- Passo 2 (GROUP BY): agrupa por funcionário
-- Passo 3 (HAVING): mantém apenas quem processou MAIS de 25 pedidos
SELECT
    e.LastName,
    COUNT(o.OrderID) AS total_orders
FROM Orders AS o
INNER JOIN Employees AS e ON o.EmployeeID = e.EmployeeID
WHERE e.LastName = 'Davolio' OR e.LastName = 'Fuller'   -- filtra antes de agrupar
GROUP BY e.LastName
HAVING COUNT(o.OrderID) > 25;                           -- filtra depois de agrupar
```

## HAVING com múltiplas condições de agregação

```sql
-- Funcionários que processaram mais de 10 pedidos
SELECT
    e.LastName,
    COUNT(o.OrderID)         AS total_orders,
    SUM(od.Quantity * p.Price) AS total_revenue
FROM Orders AS o
INNER JOIN Employees   AS e  ON o.EmployeeID  = e.EmployeeID
INNER JOIN OrderDetails AS od ON o.OrderID     = od.OrderID
INNER JOIN Products     AS p  ON od.ProductID  = p.ProductID
GROUP BY e.LastName
HAVING COUNT(o.OrderID) > 10
   AND SUM(od.Quantity * p.Price) > 50000
ORDER BY total_revenue DESC;
```

---

# 31. EXISTS — Verificando existência

## O que faz o EXISTS?

O operador `EXISTS` verifica se uma **subquery retorna ao menos uma linha**. Ele não se preocupa com os dados retornados pela subquery — só importa se existe ou não algum resultado. Se existir, retorna `TRUE`; se não existir, retorna `FALSE`.

É mais eficiente que `IN` em muitos casos, porque o banco para de avaliar a subquery assim que encontra a primeira linha correspondente.

## Sintaxe

```sql
-- EXISTS avalia a subquery para cada linha da query externa
-- Se a subquery retornar pelo menos 1 linha para aquela combinação → TRUE
SELECT column_name(s)
FROM table_name
WHERE EXISTS (subquery);
```

## Como o EXISTS funciona internamente

O `EXISTS` é uma **subquery correlacionada**: para cada linha da query externa (ex: cada fornecedor), ele executa a subquery verificando se existe ao menos uma linha que satisfaça a condição. A referência da query externa dentro da subquery é o que torna isso possível:

```sql
-- Para cada Supplier, a subquery verifica se existe algum produto
-- cujo SupplierID corresponda ao Supplier atual E que tenha preço < 10
-- Suppliers.supplierID na subquery referencia a linha atual da query externa
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (
    SELECT ProductName
    FROM Products
    WHERE Products.SupplierID = Suppliers.supplierID   -- correlação com a query externa
      AND Price < 10
);
```

📄 Resultado: lista apenas fornecedores que têm pelo menos um produto abaixo de $10.

```sql
-- Fornecedores com algum produto no preço exato de 22
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (
    SELECT ProductName
    FROM Products
    WHERE Products.SupplierID = Suppliers.supplierID
      AND Price = 22
);
```

## NOT EXISTS — O anti-padrão mais robusto

O `NOT EXISTS` retorna `TRUE` quando a subquery **não** retorna nenhuma linha. É a forma mais robusta de encontrar registros "órfãos" ou sem correspondência, e é imune ao problema de NULLs que afeta o `NOT IN`:

```sql
-- ✅ Clientes que NUNCA fizeram um pedido — versão com NOT EXISTS
-- Para cada cliente, verifica se NÃO existe nenhum pedido com seu ID
SELECT CustomerName, Country
FROM Customers AS c
WHERE NOT EXISTS (
    SELECT 1
    FROM Orders AS o
    WHERE o.CustomerID = c.CustomerID
);
```

⚠️ Note o uso de `SELECT 1` na subquery — é uma convenção. Como `EXISTS` só verifica se há resultado (não importa o que), usar `SELECT 1` é mais claro e evita processamento desnecessário de colunas reais.

## EXISTS vs IN vs JOIN — Quando usar cada um

| Operação | EXISTS | IN | LEFT JOIN + IS NULL |
|---|---|---|---|
| Existe ao menos um | ✅ Ideal | ✅ Funciona | ✅ Funciona |
| Não existe nenhum | `NOT EXISTS` ✅ | `NOT IN` ⚠️ (risco NULL) | `IS NULL` ✅ |
| Performance em grandes volumes | ✅ Para de buscar ao achar 1 | ⚠️ Carrega toda a lista | ✅ Usa índices |
| Imune a NULLs | ✅ Sim | ❌ NOT IN falha com NULL | ✅ Sim |

---

# 32. ANY e ALL — Comparando com subqueries

## O que são ANY e ALL?

`ANY` e `ALL` são operadores que comparam um valor com **um conjunto de valores** retornado por uma subquery, usando um operador de comparação padrão (`=`, `<>`, `>`, `<`, `>=`, `<=`).

A diferença entre eles está na condição de disparo:

- **`ANY`**: retorna `TRUE` se **ao menos um** valor do conjunto satisfaz a condição
- **`ALL`**: retorna `TRUE` somente se **todos** os valores do conjunto satisfazem a condição

## Sintaxe

```sql
-- ANY: verdadeiro se PELO MENOS UM valor da subquery satisfaz a condição
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY (subquery);

-- ALL: verdadeiro se TODOS os valores da subquery satisfazem a condição
SELECT column_name(s)
FROM table_name
WHERE column_name operator ALL (subquery);
```

⚠️ O operador entre a coluna e `ANY`/`ALL` deve ser um operador de comparação padrão: `=`, `<>`, `!=`, `>`, `>=`, `<`, `<=`.

## ANY — Exemplos práticos

```sql
-- Retorna o nome do produto se ALGUM registro em OrderDetails
-- tiver Quantity = 10 para aquele produto
-- (TRUE porque existem itens pedidos em quantidade 10)
SELECT ProductName
FROM Products
WHERE ProductID = ANY (
    SELECT ProductID
    FROM OrderDetails
    WHERE Quantity = 10
);
```

```sql
-- Retorna produtos pedidos em quantidade MAIOR que 99 (em qualquer pedido)
SELECT ProductName
FROM Products
WHERE ProductID = ANY (
    SELECT ProductID
    FROM OrderDetails
    WHERE Quantity > 99
);
```

```sql
-- Retorna vazio: nenhum produto tem pedido com quantidade > 1000
SELECT ProductName
FROM Products
WHERE ProductID = ANY (
    SELECT ProductID
    FROM OrderDetails
    WHERE Quantity > 1000
);
-- Resultado: zero linhas retornadas
```

## ALL — Exemplo prático

```sql
-- Retorna produtos cujo ProductID é igual a TODOS os ProductIDs
-- retornados pela subquery onde Quantity = 10
-- Na prática, raramente retorna algo com =ALL, pois o mesmo ID
-- precisaria ser todos os IDs da lista ao mesmo tempo
SELECT ProductName
FROM Products
WHERE ProductID = ALL (
    SELECT ProductID
    FROM OrderDetails
    WHERE Quantity = 10
);
-- Resultado: geralmente zero linhas com =ALL
```

O `ALL` é mais útil com operadores de comparação diferentes de `=`:

```sql
-- Retorna produtos com preço MAIOR QUE TODOS os preços da categoria 2
-- Ou seja: mais caro que o produto mais caro da categoria 2
SELECT ProductName, Price
FROM Products
WHERE Price > ALL (
    SELECT Price
    FROM Products
    WHERE CategoryID = 2
)
ORDER BY Price;
```

## ANY vs EXISTS vs IN — Quando preferir cada um

```sql
-- Estes três exemplos produzem resultados equivalentes:

-- Com EXISTS (mais expressivo para "existe ao menos um")
SELECT ProductName FROM Products AS p
WHERE EXISTS (
    SELECT 1 FROM OrderDetails od
    WHERE od.ProductID = p.ProductID AND od.Quantity = 10
);

-- Com ANY (mais conciso quando a condição é simples)
SELECT ProductName FROM Products
WHERE ProductID = ANY (
    SELECT ProductID FROM OrderDetails WHERE Quantity = 10
);

-- Com IN (mais legível para igualdade simples)
SELECT ProductName FROM Products
WHERE ProductID IN (
    SELECT ProductID FROM OrderDetails WHERE Quantity = 10
);
```

✅ Use `EXISTS` quando a lógica é "existe ao menos um registro relacionado". Use `ANY` quando a comparação é com um valor específico de uma lista. Use `ALL` quando todos os valores do conjunto precisam satisfazer a condição.

---

# 33. SELECT INTO — Criando tabelas a partir de consultas

## O que faz o SELECT INTO?

O `SELECT INTO` cria uma **nova tabela** e a preenche com dados copiados de uma tabela existente. É ideal para criar backups rápidos, tabelas temporárias de análise, ou snapshots de dados em um momento específico.

⚠️ **Importante:** a nova tabela herda os nomes e tipos de dados das colunas, mas **não** herda chaves primárias, índices, constraints `NOT NULL` ou triggers. É uma cópia dos dados, não da estrutura completa.

## Sintaxe

```sql
-- Copia todas as colunas para uma nova tabela
SELECT *
INTO new_table [IN external_database]
FROM source_table
WHERE condition;

-- Copia apenas colunas específicas
SELECT column1, column2, column3
INTO new_table
FROM source_table
WHERE condition;
```

## Exemplos práticos

```sql
-- Cria um backup completo da tabela Customers chamado CustomersBackup2026
-- A nova tabela é criada automaticamente com a mesma estrutura de colunas
SELECT * INTO CustomersBackup2026
FROM Customers;
```

```sql
-- Cria o backup em outro banco de dados (SQL Server / MS Access)
SELECT * INTO CustomersBackup2026 IN 'Backup.mdb'
FROM Customers;
```

```sql
-- Copia apenas colunas específicas para uma nova tabela
-- Útil quando você quer um subconjunto de dados para análise
SELECT CustomerName, ContactName
INTO Customers2
FROM Customers;
```

```sql
-- Copia apenas clientes dos EUA para uma nova tabela
-- O WHERE filtra quais linhas são copiadas
SELECT * INTO US_Customers
FROM Customers
WHERE Country = 'USA';
```

```sql
-- Combina dados de múltiplas tabelas usando JOIN antes de copiar
-- Cria uma tabela com clientes e seus pedidos em uma única estrutura desnormalizada
SELECT
    c.CustomerName,
    o.OrderID,
    o.OrderDate
INTO CustomersWithOrders
FROM Customers AS c
LEFT JOIN Orders AS o ON c.CustomerID = o.CustomerID;
```

## Criando tabela vazia com a mesma estrutura

Um truque muito útil: criar uma tabela vazia com a mesma estrutura de outra, usando um `WHERE` impossível que nunca retorna linhas:

```sql
-- Cria uma tabela vazia com a mesma estrutura de Customers
-- WHERE 1 = 0 é sempre FALSE, então nenhuma linha é copiada
-- Mas a estrutura de colunas é criada normalmente
SELECT * INTO CustomersTemplate
FROM Customers
WHERE 1 = 0;
```

✅ Isso é especialmente útil para criar tabelas de staging (área de preparação) com a mesma estrutura da tabela de origem antes de processar dados.

⚠️ `SELECT INTO` é suportado no **SQL Server** e **MS Access**. No **MySQL** e **PostgreSQL**, use `CREATE TABLE AS SELECT`:

```sql
-- MySQL e PostgreSQL: equivalente ao SELECT INTO
CREATE TABLE CustomersBackup2026 AS
SELECT * FROM Customers;

-- MySQL e PostgreSQL: versão vazia (sem dados)
CREATE TABLE CustomersTemplate AS
SELECT * FROM Customers
WHERE 1 = 0;
```

---

# 34. INSERT INTO SELECT — Copiando dados entre tabelas

## Qual a diferença para o SELECT INTO?

Enquanto o `SELECT INTO` **cria uma nova tabela** e a preenche, o `INSERT INTO SELECT` insere dados em uma **tabela que já existe**. Os registros existentes na tabela de destino não são afetados — os novos dados são apenas adicionados ao final.

## Requisito fundamental

Os tipos de dados das colunas selecionadas devem ser **compatíveis** com as colunas de destino. Se tentar inserir um texto em uma coluna numérica, o banco retornará um erro.

## Sintaxe

```sql
-- Copia todas as colunas de uma tabela para outra
-- A ordem e quantidade de colunas devem ser idênticas
INSERT INTO target_table
SELECT * FROM source_table
WHERE condition;

-- Copia apenas colunas específicas (forma mais segura e recomendada)
INSERT INTO target_table (column1, column2, column3)
SELECT column1, column2, column3
FROM source_table
WHERE condition;
```

## Exemplos práticos

```sql
-- Copia dados de Suppliers para Customers
-- Colunas não mapeadas (ContactName, Address, PostalCode) receberão NULL
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country
FROM Suppliers;
```

```� Antes e depois na tabela Customers:

Antes: 91 registros
Depois: 91 + 29 (fornecedores) = 120 registros
As colunas não mapeadas ficam com NULL
```

```sql
-- Copia apenas fornecedores da Alemanha para Customers
-- O WHERE na subquery filtra a origem antes de inserir
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country
FROM Suppliers
WHERE Country = 'Germany';
```

```sql
-- Copia todos os dados de Suppliers para Customers (todas as colunas)
-- ⚠️ A quantidade, ordem e tipos de todas as colunas devem ser idênticos
INSERT INTO Customers
SELECT * FROM Suppliers;
```

## Caso de uso real — Arquivamento de dados históricos

```sql
-- Arquiva pedidos de 2023 para uma tabela histórica antes de deletá-los
-- Passo 1: copia os pedidos antigos para o arquivo
INSERT INTO OrdersArchive (OrderID, CustomerID, OrderDate, TotalAmount)
SELECT OrderID, CustomerID, OrderDate, TotalAmount
FROM Orders
WHERE OrderDate < '2024-01-01';

-- Passo 2: deleta os pedidos antigos da tabela principal
-- ⚠️ Só execute após confirmar que a cópia foi bem-sucedida!
DELETE FROM Orders
WHERE OrderDate < '2024-01-01';
```

## SELECT INTO vs INSERT INTO SELECT — Resumo comparativo

| Característica | `SELECT INTO` | `INSERT INTO SELECT` |
|---|---|---|
| Tabela de destino | ❌ Não existe (é criada) | ✅ Deve existir |
| Registros existentes | — | ✅ São preservados |
| Cria índices/PKs | ❌ Não | ✅ Já existem na tabela |
| Suporte MySQL/PG | ❌ Não (use CREATE TABLE AS) | ✅ Sim |
| Suporte SQL Server | ✅ Sim | ✅ Sim |
| Melhor para | Backups rápidos, tabelas temporárias | Migração, consolidação, arquivamento |

---

# 35. CASE — Lógica condicional em queries

## O que é o CASE?

O `CASE` é a estrutura de **lógica condicional** do SQL — o equivalente ao `if/else` das linguagens de programação. Ele permite que você defina diferentes resultados baseados em condições, diretamente dentro de uma query, sem precisar de código na aplicação.

O `CASE` percorre as condições em ordem e **para na primeira que for verdadeira**, retornando o resultado correspondente. Se nenhuma condição for verdadeira, retorna o valor do `ELSE`. Se não houver `ELSE` e nenhuma condição for satisfeita, retorna `NULL`.

## Sintaxe

```sql
-- Forma pesquisada (mais flexível — cada WHEN pode ter condição diferente)
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE default_result
END

-- Forma simples (compara uma expressão com valores fixos)
CASE expression
    WHEN value1 THEN result1
    WHEN value2 THEN result2
    ELSE default_result
END
```

## Categorizando dados com CASE

O uso mais comum: criar uma **coluna calculada** que classifica os dados em categorias baseadas em condições:

```sql
-- Categoriza produtos por faixa de preço
-- CASE cria uma coluna nova chamada price_category no resultado
SELECT
    ProductName,
    Price,
    CASE
        WHEN Price < 20                  THEN 'Low Cost'
        WHEN Price BETWEEN 20 AND 50     THEN 'Medium Cost'
        ELSE                                  'High Cost'
    END AS price_category
FROM Products
ORDER BY Price;
```

📄 Resultado (parcial):

| ProductName | Price | price_category |
|---|---|---|
| Aniseed Syrup | 10.00 | Low Cost |
| Chais | 18.00 | Low Cost |
| Chang | 19.00 | Low Cost |
| Chef Anton's Gumbo Mix | 21.35 | Medium Cost |
| Côte de Blaye | 263.50 | High Cost |

## CASE para ordenação dinâmica

Um uso avançado e elegante: usar `CASE` no `ORDER BY` para criar uma **ordenação customizada** que não segue a ordem natural dos dados:

```sql
-- Ordena por prioridade de status customizada (não alfabética)
-- Active primeiro, depois Pending, depois Inactive
SELECT OrderID, Status, OrderDate
FROM Orders
ORDER BY
    CASE Status
        WHEN 'Active'   THEN 1
        WHEN 'Pending'  THEN 2
        WHEN 'Inactive' THEN 3
        ELSE                 4
    END;
```

## CASE com agregação — Pivot manual

O `CASE` dentro de funções de agregação permite criar **relatórios pivotados** (transformar linhas em colunas):

```sql
-- Conta clientes por região dentro de uma única linha
-- SUM(CASE...) é um padrão clássico para pivot manual em SQL
SELECT
    COUNT(*)                                                    AS total_customers,
    SUM(CASE WHEN Country = 'Germany' THEN 1 ELSE 0 END)       AS germany,
    SUM(CASE WHEN Country = 'Brazil'  THEN 1 ELSE 0 END)       AS brazil,
    SUM(CASE WHEN Country = 'USA'     THEN 1 ELSE 0 END)       AS usa,
    SUM(CASE WHEN Country NOT IN ('Germany','Brazil','USA')
             THEN 1 ELSE 0 END)                                 AS other_countries
FROM Customers;
```

📄 Resultado:

| total_customers | germany | brazil | usa | other_countries |
|---|---|---|---|---|
| 91 | 11 | 9 | 13 | 58 |

## CASE no UPDATE — Atualização condicional

O `CASE` pode ser usado no `SET` do `UPDATE` para aplicar valores diferentes por condição em uma única operação:

```sql
-- Aplica descontos diferentes por categoria em uma única query
-- Sem CASE, precisaria de múltiplos UPDATEs separados
UPDATE Products
SET Price = Price *
    CASE
        WHEN CategoryID = 1 THEN 0.90   -- 10% de desconto em Bebidas
        WHEN CategoryID = 2 THEN 0.85   -- 15% de desconto em Condimentos
        WHEN CategoryID = 3 THEN 0.95   -- 5% de desconto em Sobremesas
        ELSE 1.00                        -- sem desconto nas demais categorias
    END;
```

## CASE vs IIF — Alternativa simplificada

Em SQL Server e MS Access, existe o `IIF()` para condições simples de dois caminhos:

```sql
-- SQL Server / MS Access: IIF(condição, valor_se_true, valor_se_false)
SELECT ProductName, IIF(Price < 20, 'Acessível', 'Premium') AS price_tier
FROM Products;

-- Equivalente com CASE (funciona em todos os bancos)
SELECT ProductName,
    CASE WHEN Price < 20 THEN 'Acessível' ELSE 'Premium' END AS price_tier
FROM Products;
```

✅ Prefira sempre o `CASE` para compatibilidade universal entre bancos de dados.

---

# 36. NULL Functions — COALESCE, IFNULL, ISNULL, NVL

## O problema do NULL em cálculos

Como vimos no capítulo 13, qualquer operação matemática com `NULL` resulta em `NULL`. Isso pode causar resultados incorretos em relatórios e cálculos:

```sql
-- ⚠️ PROBLEMA: se InOrder for NULL, a expressão inteira retorna NULL
-- Em vez do estoque total, você vê NULL na linha do Mascarpone
SELECT ProductName, Price * (InStock + InOrder) AS stock_value
FROM Products;
```

📄 Tabela `Products` com NULL:

| PId | ProductName | Price | InStock | InOrder |
|---|---|---|---|---|
| 1 | Jarlsberg | 10.45 | 16 | 15 |
| 2 | Mascarpone | 32.56 | 23 | NULL |
| 3 | Gorgonzola | 15.67 | 9 | 20 |

📄 Resultado problemático:

| ProductName | stock_value |
|---|---|
| Jarlsberg | 323.95 |
| Mascarpone | NULL ← problema! |
| Gorgonzola | 582.90 |

## COALESCE() — O padrão universal recomendado

`COALESCE()` retorna o **primeiro valor não-NULL** de uma lista de argumentos. É o padrão SQL e funciona em praticamente todos os bancos de dados modernos:

```sql
-- COALESCE(InOrder, 0): se InOrder for NULL, usa 0 no lugar
-- Agora o cálculo de Mascarpone será 32.56 * (23 + 0) = 748.88
SELECT
    ProductName,
    Price * (InStock + COALESCE(InOrder, 0)) AS stock_value
FROM Products;
```

📄 Resultado correto:

| ProductName | stock_value |
|---|---|
| Jarlsberg | 323.95 |
| Mascarpone | 748.88 ← correto! |
| Gorgonzola | 582.90 |

### COALESCE com múltiplos argumentos

O poder do `COALESCE` vai além de substituir NULL por um valor fixo — ele aceita múltiplos argumentos e retorna o primeiro não-NULL:

```sql
-- Retorna o primeiro valor disponível: MobilePhone, então HomePhone, então Email
-- Útil para campos alternativos de contato
SELECT
    CustomerName,
    COALESCE(MobilePhone, HomePhone, Email, 'Sem contato') AS best_contact
FROM Customers;
```

## Funções equivalentes por banco de dados

Cada banco tem sua própria função para substituir NULL, mas todas fazem essencialmente a mesma coisa:

### IFNULL() — MySQL e MariaDB

```sql
-- MySQL: IFNULL(expressão, valor_se_null)
-- Substitui NULL pelo segundo argumento
SELECT ProductName, Price * (InStock + IFNULL(InOrder, 0))
FROM Products;
```

### ISNULL() — SQL Server

```sql
-- SQL Server: ISNULL(expressão, valor_substituto)
-- Funciona como IFNULL do MySQL, mas nome diferente
SELECT ProductName, Price * (InStock + ISNULL(InOrder, 0))
FROM Products;
```

⚠️ Atenção: no MySQL, `ISNULL(expr)` é uma função booleana que retorna 1 se a expressão for NULL — comportamento diferente do SQL Server!

### NVL() — Oracle

```sql
-- Oracle: NVL(expressão, valor_se_null)
-- O mais antigo dos quatro, exclusivo do Oracle
SELECT ProductName, Price * (InStock + NVL(InOrder, 0))
FROM Products;
```

### IIf() + IsNull() — MS Access

```sql
-- MS Access: combinação de IIf e IsNull para o mesmo efeito
-- IIf(condição, valor_se_true, valor_se_false)
SELECT ProductName, Price * (InStock + IIf(IsNull(InOrder), 0, InOrder))
FROM Products;
```

## Tabela comparativa — Qual usar em cada banco

| Banco | Função recomendada | Alternativa universal |
|---|---|---|
| MySQL / MariaDB | `IFNULL(expr, alt)` | `COALESCE(expr, alt)` |
| SQL Server | `ISNULL(expr, alt)` | `COALESCE(expr, alt)` |
| Oracle | `NVL(expr, alt)` | `COALESCE(expr, alt)` |
| PostgreSQL | — | `COALESCE(expr, alt)` |
| MS Access | `IIf(IsNull(expr), alt, expr)` | — |
| **Todos** | **`COALESCE(expr, alt)`** ✅ | — |

✅ **Recomendação:** use sempre `COALESCE()`. É o padrão SQL, funciona em todos os bancos modernos e é mais expressivo por aceitar múltiplos argumentos.

## NULLIF() — O inverso do COALESCE

`NULLIF()` faz o oposto: retorna `NULL` se dois valores forem iguais, e o primeiro valor caso contrário. Útil para evitar divisão por zero:

```sql
-- NULLIF(Quantity, 0): retorna NULL se Quantity = 0
-- Divisão por NULL = NULL (evita o erro "division by zero")
SELECT
    ProductName,
    TotalRevenue / NULLIF(Quantity, 0) AS average_price
FROM SalesReport;

-- Sem NULLIF, um Quantity = 0 causaria erro fatal em alguns bancos
```

---

# 37. Stored Procedures — Procedimentos armazenados

## O que é uma Stored Procedure?

Uma **Stored Procedure** (procedimento armazenado) é um bloco de código SQL **pré-compilado** e salvo no banco de dados com um nome. Em vez de escrever e enviar a mesma query repetidamente, você a salva como uma procedure e a chama quando precisar — passando parâmetros diferentes conforme a necessidade.

Pense como uma função em programação: você define uma vez, chama quantas vezes quiser.

## Benefícios das Stored Procedures

| Benefício | Descrição |
|---|---|
| ✅ Reutilização de código | A mesma procedure pode ser chamada de múltiplas aplicações |
| ✅ Performance | São pré-compiladas — o banco não precisa reinterpretar o SQL a cada chamada |
| ✅ Segurança | Usuários podem ter permissão para chamar a procedure sem acesso direto às tabelas |
| ✅ Manutenção | Atualizar a procedure atualiza todos os pontos que a utilizam automaticamente |
| ✅ Redução de tráfego | O código SQL fica no banco — a aplicação só envia o nome da procedure e os parâmetros |

## Criando uma Stored Procedure (SQL Server)

```sql
-- CREATE PROCEDURE define o nome e os parâmetros da procedure
-- AS BEGIN...END delimita o bloco de código que será executado
CREATE PROCEDURE GetCustomersByCity
    @City nvarchar(50)          -- parâmetro de entrada: nome da cidade
AS
BEGIN
    -- Retorna todos os clientes da cidade especificada pelo parâmetro
    SELECT * FROM Customers
    WHERE City = @City;
END;
```

## Executando uma Stored Procedure

```sql
-- EXEC chama a procedure e passa o valor do parâmetro
-- Retorna todos os clientes de Londres
EXEC GetCustomersByCity @City = 'London';

-- Equivalente (passando o valor diretamente, sem nomear o parâmetro)
EXEC GetCustomersByCity 'London';
```

## Stored Procedure com múltiplos parâmetros

```sql
-- Procedure que filtra por cidade E por CEP
-- Cada parâmetro tem seu tipo de dado especificado
CREATE PROCEDURE GetCustomersByCityAndPostal
    @City       nvarchar(50),
    @PostalCode nvarchar(10)
AS
BEGIN
    SELECT * FROM Customers
    WHERE City       = @City
      AND PostalCode = @PostalCode;
END;
```

```sql
-- Chamada com múltiplos parâmetros
EXEC GetCustomersByCityAndPostal
    @City       = 'London',
    @PostalCode = 'WA1 1DP';
```

## Sintaxe por banco de dados

A criação de Stored Procedures varia significativamente entre os bancos:

```sql
-- MySQL: usa DELIMITER para evitar conflito com o ; do bloco interno
DELIMITER //

CREATE PROCEDURE GetCustomersByCity(IN city_param VARCHAR(50))
BEGIN
    SELECT * FROM Customers
    WHERE City = city_param;
END //

DELIMITER ;

-- Chamada no MySQL
CALL GetCustomersByCity('London');
```

```sql
-- PostgreSQL: usa $$ como delimitador e especifica a linguagem
CREATE OR REPLACE FUNCTION GetCustomersByCity(city_param VARCHAR)
RETURNS TABLE(CustomerID INT, CustomerName VARCHAR, City VARCHAR)
LANGUAGE plpgsql
AS $$
BEGIN
    RETURN QUERY
    SELECT c.CustomerID, c.CustomerName, c.City
    FROM Customers AS c
    WHERE c.City = city_param;
END;
$$;

-- Chamada no PostgreSQL
SELECT * FROM GetCustomersByCity('London');
```

## Excluindo uma Stored Procedure

```sql
-- Remove a procedure do banco de dados
DROP PROCEDURE GetCustomersByCity;

-- ✅ Com verificação: não retorna erro se a procedure não existir
DROP PROCEDURE IF EXISTS GetCustomersByCity;
```

⚠️ **Atenção:** uma vez removida, a procedure não pode ser recuperada. Mantenha os scripts de criação em controle de versão (Git).

---

# 38. Comentários SQL — Documentando o código

## Por que comentar código SQL?

SQL escrito sem comentários se torna difícil de entender com o tempo — especialmente queries complexas com múltiplos JOINs, subqueries e lógica de negócio embutida. Bons comentários explicam o **porquê** das decisões, não apenas o que o código faz.

⚠️ Comentários não são suportados no **Microsoft Access**.

## Comentário de linha única — `--`

Tudo após `--` até o final da linha é ignorado pelo banco:

```sql
-- Seleciona todos os clientes alemães
-- Esta query é usada no relatório mensal de vendas por região
SELECT * FROM Customers
WHERE Country = 'Germany';
```

```sql
-- Comentário inline: útil para explicar colunas específicas
SELECT
    CustomerID,        -- chave primária da tabela
    CustomerName,      -- nome fantasia ou razão social
    Country            -- código ISO do país
FROM Customers;
```

```sql
-- Desativando temporariamente parte do filtro para debug
SELECT * FROM Customers
-- WHERE City = 'Berlin';    ← desativado temporariamente para testes
WHERE Country = 'Germany';
```

## Comentário de múltiplas linhas — `/* */`

Tudo entre `/*` e `*/` é ignorado, podendo abranger múltiplas linhas:

```sql
/*
    Relatório de clientes ativos por região
    Autor: equipe de dados
    Atualizado: 2026-04-01
    Versão: 2.3
*/
SELECT CustomerName, City, Country
FROM Customers
WHERE Country = 'Germany' AND City = 'Berlin';
```

```sql
/* Desativando múltiplas queries durante manutenção */
/*
SELECT * FROM Customers;
SELECT * FROM Products;
SELECT * FROM Orders;
*/
SELECT * FROM Suppliers;   -- apenas esta query está ativa
```

## Comentário inline em meio ao código

Comentários multi-linha podem ser inseridos **dentro** de uma instrução para comentar partes específicas:

```sql
-- Comenta apenas a coluna City no SELECT, mantendo o resto ativo
SELECT CustomerName, /*City,*/ Country
FROM Customers;
```

```sql
-- Comenta parte de uma condição WHERE complexa
SELECT * FROM Customers
WHERE (CustomerName LIKE 'L%'
    OR CustomerName LIKE 'R%'
    /*OR CustomerName LIKE 'S%'
    OR CustomerName LIKE 'T%'*/  -- desativado: fora do escopo desta análise
    OR CustomerName LIKE 'W%')
  AND Country = 'USA'
ORDER BY CustomerName;
```

## Boas práticas de comentários SQL

```sql
-- ❌ EVITE: comentários que repetem o óbvio
SELECT * FROM Customers;   -- seleciona clientes

-- ✅ PREFIRA: comentários que explicam o propósito e contexto
-- Exclui clientes sem pedido nos últimos 12 meses (inativos)
-- Ver regra de negócio: DOC-2024-087
SELECT c.CustomerName
FROM Customers AS c
LEFT JOIN Orders AS o
    ON c.CustomerID = o.CustomerID
    AND o.OrderDate >= DATEADD(MONTH, -12, GETDATE())
WHERE o.CustomerID IS NULL;
```

---

# 39. Operadores SQL — Referência completa

## Visão geral dos tipos de operadores

SQL possui cinco categorias de operadores, cada uma para um tipo diferente de operação. Conhecê-los todos é fundamental para escrever queries expressivas e corretas.

## Operadores Aritméticos

Realizam cálculos matemáticos entre valores numéricos:

| Operador | Descrição | Exemplo | Resultado |
|---|---|---|---|
| `+` | Adição | `SELECT 10 + 5` | `15` |
| `-` | Subtração | `SELECT 10 - 3` | `7` |
| `*` | Multiplicação | `SELECT Price * Quantity` | valor calculado |
| `/` | Divisão | `SELECT Total / Count` | valor calculado |
| `%` | Módulo (resto) | `SELECT 10 % 3` | `1` |

```sql
-- Aplicando operadores aritméticos em uma query real
SELECT
    ProductName,
    Price,
    Price * 0.9                     AS price_with_10_discount,
    Price * 1.0875                  AS price_with_tax,
    ROUND(Price * 0.9 * 1.0875, 2)  AS final_price
FROM Products
ORDER BY final_price DESC;
```

## Operadores de Comparação

Comparam dois valores e retornam `TRUE` ou `FALSE`:

| Operador | Descrição | Exemplo |
|---|---|---|
| `=` | Igual a | `WHERE Status = 'active'` |
| `>` | Maior que | `WHERE Price > 50` |
| `<` | Menor que | `WHERE Age < 18` |
| `>=` | Maior ou igual | `WHERE Score >= 7.0` |
| `<=` | Menor ou igual | `WHERE Quantity <= 0` |
| `<>` | Diferente de (padrão SQL) | `WHERE Country <> 'Brazil'` |

⚠️ `!=` e `<>` são equivalentes na maioria dos bancos, mas `<>` é o padrão SQL oficial.

## Operadores Compostos (SQL Server)

Atalhos para operações do tipo `coluna = coluna + valor`:

| Operador | Equivalente | Descrição |
|---|---|---|
| `+=` | `col = col + val` | Adiciona e atribui |
| `-=` | `col = col - val` | Subtrai e atribui |
| `*=` | `col = col * val` | Multiplica e atribui |
| `/=` | `col = col / val` | Divide e atribui |
| `%=` | `col = col % val` | Módulo e atribui |

```sql
-- SQL Server: aumenta o preço em 10% usando operador composto
UPDATE Products SET Price *= 1.10 WHERE CategoryID = 1;

-- Equivalente sem operador composto (funciona em todos os bancos)
UPDATE Products SET Price = Price * 1.10 WHERE CategoryID = 1;
```

## Operadores Lógicos

Combinam condições em expressões booleanas:

| Operador | Descrição | Retorna TRUE quando... |
|---|---|---|
| `AND` | E lógico | Todas as condições são TRUE |
| `OR` | OU lógico | Ao menos uma condição é TRUE |
| `NOT` | Negação | A condição é FALSE |
| `IN` | Pertence à lista | Valor está na lista |
| `BETWEEN` | Dentro do intervalo | Valor está entre os extremos (inclusive) |
| `LIKE` | Corresponde ao padrão | Texto corresponde ao padrão com wildcards |
| `EXISTS` | Subquery retorna linhas | Subquery tem ao menos 1 resultado |
| `ANY` | Algum da subquery atende | Ao menos 1 valor da subquery satisfaz |
| `ALL` | Todos da subquery atendem | Todos os valores da subquery satisfazem |
| `SOME` | Sinônimo de ANY | Igual ao ANY |

## Operadores Bitwise (avançado)

Operam diretamente nos bits dos valores inteiros — raramente usados em SQL cotidiano, mais comuns em stored procedures e triggers:

| Operador | Descrição |
|---|---|
| `&` | AND bit a bit |
| `\|` | OR bit a bit |
| `^` | XOR (OU exclusivo) bit a bit |
| `~` | NOT bit a bit (complemento) |

```sql
-- Exemplo prático de bitwise: verificar se uma flag está ativa
-- Útil para sistemas de permissões onde bits representam permissões diferentes
-- Bit 1 = leitura, Bit 2 = escrita, Bit 4 = admin
SELECT UserName
FROM Users
WHERE Permissions & 4 = 4;  -- usuários com bit de admin ativo
```

---

# 40. CREATE DATABASE e DROP DATABASE

## Criando um banco de dados

O `CREATE DATABASE` cria um novo banco de dados vazio no servidor. Você precisa de **privilégios de administrador** para executar este comando:

```sql
-- Cria um banco de dados chamado 'testDB'
CREATE DATABASE testDB;
```

⚠️ O nome do banco de dados é **case-sensitive** na maioria dos sistemas Linux. `testDB` e `testdb` seriam bancos diferentes no MySQL em Linux.

## Verificando bancos existentes

```sql
-- SQL Server: lista todos os bancos de dados do servidor
SELECT name FROM sys.databases;

-- MySQL / MariaDB: lista todos os bancos de dados
SHOW DATABASES;

-- PostgreSQL: lista todos os bancos de dados
SELECT datname FROM pg_database;
```

## Excluindo um banco de dados

O `DROP DATABASE` remove **permanentemente** um banco de dados e todo seu conteúdo — tabelas, views, stored procedures, dados, tudo:

```sql
-- ❌ IRREVERSÍVEL: remove o banco 'testDB' e tudo que está dentro dele
DROP DATABASE testDB;
```

⚠️ **Nunca execute `DROP DATABASE` em produção sem backup confirmado.** Não há como desfazer essa operação sem restaurar um backup.

```sql
-- MySQL: listando bancos após remoção para confirmar
DROP DATABASE testDB;
SHOW DATABASES;   -- testDB não deve mais aparecer

-- SQL Server: verificando após remoção
DROP DATABASE testDB;
SELECT name FROM sys.databases;  -- testDB não deve mais aparecer
```

---

# 41. BACKUP DATABASE — Estratégias de backup

## Por que backups são críticos?

Backups são a única proteção real contra perda de dados causada por erros humanos (`DELETE` sem `WHERE`), falhas de hardware, ataques de ransomware ou corrupção de dados. Um banco sem backup é um banco com data de expiração.

⚠️ O `BACKUP DATABASE` é exclusivo do **SQL Server**. Outros bancos têm suas próprias ferramentas (`mysqldump` para MySQL, `pg_dump` para PostgreSQL).

## Backup completo (Full Backup)

```sql
-- Cria um backup completo do banco 'testDB' no caminho especificado
-- Sempre salve o backup em disco diferente do banco de dados!
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak';
```

✅ **Regra fundamental:** nunca salve o backup no mesmo disco do banco de dados. Se o disco falhar, você perde os dois.

## Backup diferencial (Differential Backup)

O backup diferencial captura apenas os **dados que mudaram desde o último backup completo**. É muito mais rápido e ocupa menos espaço:

```sql
-- Backup diferencial: salva apenas as alterações desde o último backup completo
-- Requer que um backup completo já exista anteriormente
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB_diff.bak'
WITH DIFFERENTIAL;
```

## Estratégia de backup recomendada

| Tipo | Frequência recomendada | Tempo | Espaço |
|---|---|---|---|
| Backup completo | Semanal (ex: domingo) | Lento | Grande |
| Backup diferencial | Diário (ex: toda noite) | Médio | Médio |
| Backup de log | A cada hora (ou menos) | Rápido | Pequeno |

✅ Esta estratégia permite restaurar dados com perda mínima em caso de falha.

---

# 42. CREATE TABLE — Criando tabelas

## Sintaxe completa

```sql
-- CREATE TABLE define a estrutura de uma nova tabela
-- Cada coluna tem: nome, tipo de dado e constraints opcionais
CREATE TABLE table_name (
    column1  datatype  constraint,
    column2  datatype  constraint,
    column3  datatype  constraint,
    ...
);
```

## Exemplo completo e explicado

```sql
-- Criando a tabela Persons com cinco colunas
CREATE TABLE Persons (
    PersonID    int            PRIMARY KEY,    -- identificador único, não pode repetir
    LastName    varchar(255)   NOT NULL,       -- sobrenome, campo obrigatório
    FirstName   varchar(255),                  -- primeiro nome, opcional (permite NULL)
    Address     varchar(255),                  -- endereço, opcional
    City        varchar(255)                   -- cidade, opcional
);
```

Anatomia de cada linha:

- `int` — tipo numérico inteiro (sem decimais)
- `varchar(255)` — texto variável com até 255 caracteres
- `PRIMARY KEY` — identificador único da linha (implica NOT NULL + UNIQUE)
- `NOT NULL` — campo obrigatório, não aceita ausência de valor

📄 A tabela `Persons` vazia após criação:

| PersonID | LastName | FirstName | Address | City |
|---|---|---|---|---|
| | | | | |

## Tipos de dados mais comuns

```sql
-- Referência dos tipos mais usados no dia a dia
CREATE TABLE DataTypesReference (
    -- Numéricos
    age             INT,                -- inteiro: -2.1 bilhões a +2.1 bilhões
    salary          DECIMAL(10, 2),     -- decimal preciso: 10 dígitos, 2 casas
    temperature     FLOAT,              -- ponto flutuante (impreciso para dinheiro!)
    is_active       BOOLEAN,            -- verdadeiro/falso (MySQL usa TINYINT(1))

    -- Texto
    code            CHAR(3),            -- texto de tamanho FIXO (sempre 3 chars)
    name            VARCHAR(255),       -- texto de tamanho VARIÁVEL (até 255)
    description     TEXT,               -- texto longo sem limite prático

    -- Data e hora
    birth_date      DATE,               -- apenas data: YYYY-MM-DD
    created_at      DATETIME,           -- data + hora: YYYY-MM-DD HH:MM:SS
    updated_at      TIMESTAMP           -- como DATETIME, mas atualiza automaticamente
);
```

## CREATE TABLE a partir de outra tabela

```sql
-- Cria uma nova tabela com os dados de clientes da Alemanha
-- A estrutura de colunas é herdada automaticamente do SELECT
CREATE TABLE GermanCustomers AS
SELECT * FROM Customers
WHERE Country = 'Germany';

-- Criando tabela vazia com a mesma estrutura (WHERE impossível = zero linhas)
CREATE TABLE CustomersTemplate AS
SELECT * FROM Customers
WHERE 1 = 0;
```

⚠️ A sintaxe `CREATE TABLE ... AS SELECT` funciona em MySQL, PostgreSQL e Oracle. No SQL Server, use `SELECT * INTO new_table FROM source_table`.

---

# 43. DROP TABLE e TRUNCATE TABLE

## DROP TABLE — Removendo a tabela por completo

```sql
-- Remove a tabela e todos os seus dados permanentemente
-- ❌ IRREVERSÍVEL sem backup
DROP TABLE Shippers;

-- ✅ Com verificação: não retorna erro se a tabela não existir
DROP TABLE IF EXISTS Shippers;
```

⚠️ Em bancos com **Foreign Keys**, você não pode remover uma tabela referenciada por outra. Primeiro remova a constraint ou a tabela dependente:

```sql
-- ❌ ERRO: Orders referencia Customers via CustomerID (FK)
DROP TABLE Customers;

-- ✅ CORRETO: remova as dependências primeiro
DROP TABLE IF EXISTS Orders;     -- remove a tabela que tem a FK
DROP TABLE IF EXISTS Customers;  -- agora pode remover a referenciada
```

## TRUNCATE TABLE — Limpando os dados, mantendo a estrutura

```sql
-- Remove TODOS os dados da tabela, mas preserva a estrutura
-- Colunas, índices, constraints e a tabela em si continuam existindo
TRUNCATE TABLE Customers;
```

## DROP TABLE vs DELETE vs TRUNCATE — Diferenças críticas

| Aspecto | `DROP TABLE` | `DELETE FROM` | `TRUNCATE TABLE` |
|---|---|---|---|
| Remove dados | ✅ | ✅ | ✅ |
| Remove a tabela | ✅ | ❌ | ❌ |
| Aceita WHERE | ❌ | ✅ | ❌ |
| Pode fazer ROLLBACK | ❌ | ✅ (com transação) | ❌ (geralmente) |
| Velocidade | Rápido | Lento em grandes tabelas | Muito rápido |
| Reseta AUTO_INCREMENT | ✅ | ❌ | ✅ |
| Dispara triggers | ❌ | ✅ | ❌ |

✅ **Quando usar cada um:**
- `DROP TABLE` — quando você quer eliminar a tabela completamente
- `DELETE FROM table` — quando quer apagar linhas específicas (com WHERE) ou precisa de ROLLBACK
- `TRUNCATE TABLE` — quando quer limpar todos os dados rapidamente mantendo a estrutura

---

# 44. ALTER TABLE — Modificando estruturas

## O que o ALTER TABLE pode fazer?

O `ALTER TABLE` é usado para **modificar a estrutura** de uma tabela existente sem precisar recriá-la do zero. É especialmente valioso em produção, onde você não pode perder dados ao ajustar o schema.

## Adicionando uma coluna

```sql
-- Adiciona a coluna Email na tabela Customers
-- A nova coluna aparece no final e começa com NULL em todos os registros existentes
ALTER TABLE Customers
ADD Email varchar(255);

-- Adicionando com constraint
ALTER TABLE Customers
ADD CreatedAt DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP;
```

## Removendo uma coluna

```sql
-- Remove a coluna Email da tabela Customers
-- ⚠️ Todos os dados dessa coluna são perdidos permanentemente
ALTER TABLE Customers
DROP COLUMN Email;
```

⚠️ Alguns bancos não permitem remover uma coluna que seja referenciada por um índice, constraint ou view. Remova as dependências primeiro.

## Renomeando uma coluna

```sql
-- Padrão SQL (MySQL 8+, PostgreSQL, Oracle)
ALTER TABLE Customers
RENAME COLUMN ContactName TO contact_name;

-- SQL Server: usa stored procedure do sistema
EXEC sp_rename 'Customers.ContactName', 'contact_name', 'COLUMN';
```

## Modificando o tipo ou constraint de uma coluna

```sql
-- SQL Server / MS Access: usa ALTER COLUMN
ALTER TABLE Customers
ALTER COLUMN Email varchar(100) NOT NULL;

-- MySQL / Oracle: usa MODIFY
ALTER TABLE Customers
MODIFY Email varchar(100) NOT NULL;
```

⚠️ **Atenção ao modificar tipos:** se você reduzir o tamanho de um `VARCHAR(255)` para `VARCHAR(50)` e existirem dados com mais de 50 caracteres, o banco retornará erro. Sempre verifique os dados antes de alterar tipos.

## Adicionando uma constraint

```sql
-- Adiciona uma constraint CHECK para garantir que Age >= 18
ALTER TABLE Members
ADD CONSTRAINT CHK_Age CHECK (Age >= 18);

-- Adiciona chave estrangeira
ALTER TABLE Orders
ADD CONSTRAINT FK_CustomerID
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID);
```

## Renomeando a tabela

```sql
-- Padrão SQL (MySQL, PostgreSQL, Oracle)
ALTER TABLE Customers
RENAME TO Clients;

-- SQL Server: usa stored procedure
EXEC sp_rename 'Customers', 'Clients';
```

## Sequência segura para alterações em produção

```sql
-- ✅ Protocolo recomendado para ALTER TABLE em produção:

-- Passo 1: faça backup antes de qualquer alteração estrutural
-- Passo 2: teste em ambiente de desenvolvimento/staging primeiro
-- Passo 3: execute a alteração em horário de baixo tráfego
-- Passo 4: monitore a aplicação após a alteração

-- Exemplo: adicionando a coluna DateOfBirth em Persons
ALTER TABLE Persons ADD DateOfBirth date;

-- Verificando o resultado
SELECT PersonID, LastName, DateOfBirth FROM Persons LIMIT 5;

-- Mudando o tipo se necessário
ALTER TABLE Persons MODIFY DateOfBirth year;

-- Removendo se não for mais necessária
ALTER TABLE Persons DROP COLUMN DateOfBirth;
```

---

# 45. Constraints — Regras de integridade de dados

## O que são Constraints?

**Constraints** (restrições) são regras aplicadas às colunas de uma tabela para garantir a **integridade e confiabilidade dos dados**. Elas funcionam como guardiões: se uma operação violar uma constraint, o banco de dados a rejeita automaticamente.

São definidas no `CREATE TABLE` ou adicionadas depois com `ALTER TABLE`.

## Tipos de Constraints disponíveis

| Constraint | Função |
|---|---|
| `NOT NULL` | Garante que a coluna sempre tenha um valor — nunca NULL |
| `UNIQUE` | Garante que todos os valores da coluna sejam diferentes |
| `PRIMARY KEY` | Identifica cada linha de forma única (NOT NULL + UNIQUE) |
| `FOREIGN KEY` | Garante referência válida entre duas tabelas |
| `CHECK` | Valida que o valor satisfaz uma condição específica |
| `DEFAULT` | Define um valor padrão quando nenhum é fornecido |
| `CREATE INDEX` | Melhora a velocidade de buscas (não é uma constraint de integridade, mas é definida junto) |

```sql
-- Tabela com múltiplas constraints demonstradas
CREATE TABLE Orders (
    OrderID     int             PRIMARY KEY,                -- identificador único
    CustomerID  int             NOT NULL,                   -- obrigatório
    OrderDate   date            NOT NULL DEFAULT (CURDATE()), -- obrigatório, padrão hoje
    Status      varchar(20)     DEFAULT 'pending',          -- valor padrão
    TotalAmount decimal(10, 2)  CHECK (TotalAmount >= 0),   -- não pode ser negativo

    -- Foreign Key: CustomerID deve existir na tabela Customers
    CONSTRAINT FK_Orders_Customers
        FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

---

# 46. NOT NULL — Tornando campos obrigatórios

## O que faz o NOT NULL?

Por padrão, qualquer coluna em SQL aceita `NULL` (ausência de valor). A constraint `NOT NULL` **torna o campo obrigatório**: qualquer tentativa de inserir ou atualizar um registro sem fornecer um valor para essa coluna resultará em erro.

## NOT NULL no CREATE TABLE

```sql
-- ID, LastName e FirstName são obrigatórios
-- Age é opcional (aceita NULL)
CREATE TABLE Persons (
    ID          int             NOT NULL,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255)    NOT NULL,
    Age         int                         -- opcional, sem NOT NULL aceita NULL
);
```

## NOT NULL no ALTER TABLE — Adicionando a constraint depois

```sql
-- SQL Server / MS Access: adicionando NOT NULL em coluna existente
ALTER TABLE Persons
ALTER COLUMN Age int NOT NULL;

-- MySQL: usa MODIFY
ALTER TABLE Persons
MODIFY COLUMN Age int NOT NULL;

-- Oracle 10G+: usa MODIFY sem a palavra COLUMN
ALTER TABLE Persons
MODIFY Age int NOT NULL;
```

⚠️ **Antes de adicionar NOT NULL a uma coluna existente**, verifique se há registros com NULL nessa coluna. Se houver, o banco rejeitará a alteração:

```sql
-- Verificar antes de aplicar a constraint
SELECT COUNT(*) AS null_count FROM Persons WHERE Age IS NULL;

-- Se retornar 0, é seguro adicionar NOT NULL
-- Se retornar > 0, você precisa tratar os NULLs primeiro
UPDATE Persons SET Age = 0 WHERE Age IS NULL;

-- Agora pode adicionar a constraint
ALTER TABLE Persons MODIFY COLUMN Age int NOT NULL;
```

## Removendo a constraint NOT NULL

```sql
-- SQL Server: permite NULL novamente
ALTER TABLE Persons ALTER COLUMN Age int NULL;

-- MySQL: remove o NOT NULL (permite NULL)
ALTER TABLE Persons MODIFY COLUMN Age int NULL;
```

---

# 47. UNIQUE — Garantindo valores únicos

## O que faz o UNIQUE?

A constraint `UNIQUE` garante que **todos os valores em uma coluna (ou combinação de colunas) sejam distintos**. Nenhum registro pode ter o mesmo valor que outro registro naquela coluna.

A diferença para `PRIMARY KEY`: você pode ter **múltiplas** constraints UNIQUE em uma tabela, mas apenas uma PRIMARY KEY.

## UNIQUE no CREATE TABLE

```sql
-- SQL Server, Oracle, MS Access: UNIQUE inline na coluna
CREATE TABLE Persons (
    ID          int             NOT NULL UNIQUE,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int
);

-- MySQL: UNIQUE é declarado separadamente no final
CREATE TABLE Persons (
    ID          int             NOT NULL,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int,
    UNIQUE (ID)                          -- declaração separada
);
```

## UNIQUE nomeado e em múltiplas colunas

Nomear a constraint facilita gerenciá-la depois (remover, alterar):

```sql
-- UNIQUE em múltiplas colunas: a combinação de ID + LastName deve ser única
-- Dois registros podem ter o mesmo ID ou o mesmo LastName, mas não ambos iguais
CREATE TABLE Persons (
    ID          int             NOT NULL,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int,
    CONSTRAINT UC_Person UNIQUE (ID, LastName)   -- constraint nomeada
);
```

## UNIQUE no ALTER TABLE

```sql
-- Adicionando UNIQUE em coluna já existente
ALTER TABLE Persons
ADD UNIQUE (ID);

-- Adicionando UNIQUE nomeado e em múltiplas colunas
ALTER TABLE Persons
ADD CONSTRAINT UC_Person UNIQUE (ID, LastName);
```

## Removendo a constraint UNIQUE

```sql
-- MySQL: usa DROP INDEX (UNIQUE cria um índice interno)
ALTER TABLE Persons
DROP INDEX UC_Person;

-- SQL Server / Oracle / MS Access: usa DROP CONSTRAINT
ALTER TABLE Persons
DROP CONSTRAINT UC_Person;
```

## UNIQUE vs PRIMARY KEY

| Característica | UNIQUE | PRIMARY KEY |
|---|---|---|
| Garante unicidade | ✅ | ✅ |
| Permite NULL | ✅ (geralmente 1 NULL) | ❌ |
| Quantidade por tabela | Múltiplas | Apenas 1 |
| Cria índice automaticamente | ✅ | ✅ |
| Pode ser referenciada por FK | ✅ | ✅ |

---

# 48. PRIMARY KEY — Identificando linhas de forma única

## O que é uma PRIMARY KEY?

A `PRIMARY KEY` (chave primária) é a constraint que **identifica de forma única cada registro** de uma tabela. Ela garante que nenhuma linha seja duplicada e que o campo identificador nunca seja `NULL`. É a combinação de `NOT NULL` + `UNIQUE` aplicada a uma ou mais colunas.

Cada tabela pode ter **apenas uma** PRIMARY KEY, mas ela pode ser composta por múltiplas colunas (chave composta). A PRIMARY KEY é também o alvo natural de `FOREIGN KEY` em outras tabelas — é ela que sustenta os relacionamentos entre tabelas.

## PRIMARY KEY no CREATE TABLE

```sql
-- Forma mais simples: PRIMARY KEY inline na definição da coluna
CREATE TABLE Persons (
    ID          int             PRIMARY KEY,     -- identificador único, NOT NULL implícito
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int
);
```

### PRIMARY KEY composta — múltiplas colunas

Uma chave composta é usada quando nenhuma coluna sozinha garante unicidade, mas a **combinação** de duas ou mais colunas sim:

```sql
-- PRIMARY KEY composta: a combinação de ID + LastName deve ser única
-- Dois registros podem ter o mesmo ID ou o mesmo LastName, mas não ambos iguais
CREATE TABLE Persons (
    ID          int,
    LastName    varchar(255),
    FirstName   varchar(255),
    Age         int,
    PRIMARY KEY (ID, LastName)       -- sem nome de constraint
);
```

```sql
-- PRIMARY KEY composta NOMEADA — recomendado para facilitar gerenciamento
-- O nome PK_Person permite referenciar e remover a constraint facilmente
CREATE TABLE Persons (
    ID          int,
    LastName    varchar(255),
    FirstName   varchar(255),
    Age         int,
    CONSTRAINT PK_Person PRIMARY KEY (ID, LastName)
);
```

✅ Sempre nomeie suas constraints (`PK_`, `FK_`, `CHK_`, `UC_`). Facilita muito o gerenciamento e as mensagens de erro se tornam mais claras.

## PRIMARY KEY no ALTER TABLE

```sql
-- Adicionando PRIMARY KEY em tabela existente
-- ⚠️ A coluna DEVE ter sido criada como NOT NULL — PRIMARY KEY não pode ter NULL
ALTER TABLE Persons
ADD PRIMARY KEY (ID);

-- Adicionando PRIMARY KEY composta nomeada
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID, LastName);
```

## Removendo a PRIMARY KEY

```sql
-- SQL Server, Oracle, MS Access: usa DROP CONSTRAINT pelo nome
ALTER TABLE Persons
DROP CONSTRAINT PK_Person;

-- MySQL: DROP PRIMARY KEY (não precisa do nome)
ALTER TABLE Persons
DROP PRIMARY KEY;
```

## PRIMARY KEY com AUTO_INCREMENT — O padrão mais comum

Na prática, a PRIMARY KEY quase sempre é usada junto com auto-increment para gerar IDs automáticos:

```sql
-- MySQL: combinação mais comum no dia a dia
CREATE TABLE Customers (
    CustomerID  int             AUTO_INCREMENT PRIMARY KEY,
    CustomerName varchar(255)   NOT NULL,
    Country     varchar(100)
);

-- Inserindo sem informar o ID — gerado automaticamente
INSERT INTO Customers (CustomerName, Country)
VALUES ('Alfreds Futterkiste', 'Germany');
-- CustomerID será gerado automaticamente: 1, 2, 3...
```

---

# 49. FOREIGN KEY — Relacionando tabelas com integridade

## O que é uma FOREIGN KEY?

A `FOREIGN KEY` (chave estrangeira) é a constraint que **estabelece e protege o relacionamento** entre duas tabelas. Ela garante que um valor em uma coluna da tabela filha corresponda a um valor existente na PRIMARY KEY da tabela pai — impedindo dados órfãos e quebras de integridade referencial.

A FOREIGN KEY age em dois sentidos:
- **Ao inserir/atualizar** na tabela filha: impede inserir um valor que não existe na tabela pai
- **Ao deletar/atualizar** na tabela pai: impede remover um registro que ainda é referenciado pela filha

## Anatomia do relacionamento

```
Tabela PAI (parent): Persons
┌────────────┬──────────┬───────────┬─────┐
│ PersonID   │ LastName │ FirstName │ Age │  ← PRIMARY KEY: PersonID
│    1       │ Hansen   │ Ola       │ 30  │
│    2       │ Svendson │ Tove      │ 23  │
└────────────┴──────────┴───────────┴─────┘
         ↑
         │ referenciada por
         │
Tabela FILHA (child): Orders
┌─────────┬─────────────┬────────────┐
│ OrderID │ OrderNumber │ PersonID   │  ← FOREIGN KEY: PersonID → Persons.PersonID
│    3    │    22456    │     2      │
│    4    │    24562    │     1      │
└─────────┴─────────────┴────────────┘
```

## FOREIGN KEY no CREATE TABLE

```sql
-- Criando a tabela Orders com FOREIGN KEY nomeada para a tabela Persons
CREATE TABLE Orders (
    OrderID     int     PRIMARY KEY,
    OrderNumber int     NOT NULL,
    PersonID    int,

    -- A constraint FK garante que PersonID deve existir em Persons.PersonID
    CONSTRAINT fk_Person
        FOREIGN KEY (PersonID)
        REFERENCES Persons(PersonID)
);
```

## FOREIGN KEY no ALTER TABLE

```sql
-- Adicionando FK em tabela já existente
ALTER TABLE Orders
ADD CONSTRAINT fk_Person
    FOREIGN KEY (PersonID)
    REFERENCES Persons(PersonID);
```

## O que a FOREIGN KEY protege na prática?

```sql
-- ❌ ERRO: PersonID = 99 não existe na tabela Persons
INSERT INTO Orders (OrderID, OrderNumber, PersonID)
VALUES (10, 55555, 99);

-- ✅ CORRETO: PersonID = 1 existe em Persons
INSERT INTO Orders (OrderID, OrderNumber, PersonID)
VALUES (10, 55555, 1);

-- ❌ ERRO: não pode deletar PersonID = 1 de Persons enquanto Orders referencia esse ID
DELETE FROM Persons WHERE PersonID = 1;
```

## Comportamentos ON DELETE e ON UPDATE

Você pode definir o que acontece na tabela filha quando um registro pai é deletado ou atualizado:

```sql
CREATE TABLE Orders (
    OrderID     int     PRIMARY KEY,
    OrderNumber int     NOT NULL,
    PersonID    int,

    CONSTRAINT fk_Person
        FOREIGN KEY (PersonID)
        REFERENCES Persons(PersonID)
        ON DELETE CASCADE       -- deleta pedidos automaticamente se o cliente for deletado
        ON UPDATE CASCADE       -- atualiza o PersonID nos pedidos se o pai mudar
);
```

| Opção | Comportamento |
|---|---|
| `RESTRICT` (padrão) | Impede DELETE/UPDATE no pai se houver filhos |
| `CASCADE` | Propaga DELETE/UPDATE para os filhos automaticamente |
| `SET NULL` | Define a FK como NULL nos filhos quando o pai é removido |
| `SET DEFAULT` | Define a FK com o valor DEFAULT nos filhos |

⚠️ `CASCADE` é poderoso mas perigoso: deletar um cliente pode deletar todos os pedidos, itens de pedido, pagamentos em cascata. Use com consciência.

## Removendo uma FOREIGN KEY

```sql
-- SQL Server, Oracle, MS Access
ALTER TABLE Orders DROP CONSTRAINT fk_Person;

-- MySQL
ALTER TABLE Orders DROP FOREIGN KEY fk_Person;
```

---

# 50. CHECK — Validando dados com condições

## O que faz o CHECK?

A constraint `CHECK` valida que os dados de uma coluna satisfazem uma **condição específica** antes de serem aceitos. Se o dado não atender à condição, a operação `INSERT` ou `UPDATE` é rejeitada com erro. É como ter uma validação de regra de negócio direto no banco de dados.

## CHECK no CREATE TABLE

```sql
-- Garante que Age seja sempre >= 18
CREATE TABLE Persons (
    ID          int             PRIMARY KEY,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int             CHECK (Age >= 18)   -- inline, sem nome
);
```

### CHECK nomeado e em múltiplas colunas

```sql
-- CHECK nomeado que valida duas colunas simultaneamente
-- A pessoa deve ter >= 18 anos E morar em Sandnes
-- ⚠️ Se a pessoa tiver 20 anos mas morar em Oslo, o INSERT é rejeitado
CREATE TABLE Persons (
    ID          int             PRIMARY KEY,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int,
    City        varchar(255),
    CONSTRAINT chk_PersonAge CHECK (Age >= 18 AND City = 'Sandnes')
);
```

## CHECK no ALTER TABLE

```sql
-- Adicionando CHECK simples
ALTER TABLE Persons
ADD CHECK (Age >= 18);

-- Adicionando CHECK nomeado e em múltiplas colunas
ALTER TABLE Persons
ADD CONSTRAINT chk_PersonAge CHECK (Age >= 18 AND City = 'Sandnes');
```

## Exemplos práticos de CHECK

```sql
-- CHECK em múltiplas regras de negócio em uma única tabela
CREATE TABLE Products (
    ProductID   int             PRIMARY KEY,
    ProductName varchar(255)    NOT NULL,
    Price       decimal(10,2)   CHECK (Price >= 0),              -- preço não negativo
    Discount    decimal(5,2)    CHECK (Discount BETWEEN 0 AND 100), -- desconto 0-100%
    Stock       int             CHECK (Stock >= 0),              -- estoque não negativo
    Status      varchar(20)     CHECK (Status IN ('active', 'inactive', 'discontinued'))
);
```

⚠️ **Suporte ao CHECK no MySQL:** Até o MySQL **8.0.15**, a sintaxe `CHECK` era aceita sem erro, mas completamente **ignorada** — nenhuma validação era aplicada. A partir do MySQL **8.0.16** (lançado em abril de 2019), o `CHECK` passou a ser totalmente funcional e enforced por padrão.

⚠️ **Comportamento com NULL:** Um `CHECK` é satisfeito se a expressão for `TRUE` **ou** `UNKNOWN` (quando a coluna é `NULL`). Ou seja, `NULL` sempre passa pelo CHECK — se quiser bloquear NULL, combine `CHECK` com `NOT NULL`.

```sql
-- Em MySQL 8.0.15 e anterior: aceita o INSERT abaixo sem erro (CHECK ignorado)
-- Em MySQL 8.0.16+: rejeita com ERROR 3819 (HY000): Check constraint violated
INSERT INTO Persons (ID, LastName, Age) VALUES (1, 'Silva', 15);
-- Age = 15 viola CHECK (Age >= 18)
```

## Removendo a constraint CHECK

```sql
-- SQL Server, Oracle, MS Access
ALTER TABLE Persons DROP CONSTRAINT chk_PersonAge;

-- MySQL 8+
ALTER TABLE Persons DROP CHECK chk_PersonAge;
```

---

# 51. DEFAULT — Valores padrão automáticos

## O que faz o DEFAULT?

A constraint `DEFAULT` define um **valor automático** para uma coluna quando nenhum valor é fornecido no `INSERT`. Sem `DEFAULT`, colunas omitidas no `INSERT` recebem `NULL`. Com `DEFAULT`, recebem o valor pré-definido.

## DEFAULT no CREATE TABLE

```sql
-- City recebe 'Sandnes' automaticamente se não for informada no INSERT
CREATE TABLE Persons (
    ID          int             PRIMARY KEY,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int,
    City        varchar(255)    DEFAULT 'Sandnes'
);
```

```sql
-- Inserindo sem informar City → recebe 'Sandnes' automaticamente
INSERT INTO Persons (ID, LastName, FirstName, Age)
VALUES (1, 'Hansen', 'Ola', 30);
-- City será 'Sandnes'
```

## DEFAULT com funções do sistema — Data atual

```sql
-- MySQL: data atual automática no INSERT
CREATE TABLE Orders (
    ID          int             PRIMARY KEY,
    OrderNumber int             NOT NULL,
    OrderDate   date            DEFAULT (CURRENT_DATE())     -- data de hoje
);

-- SQL Server: equivalente usando CAST + GETDATE()
CREATE TABLE Orders (
    ID          int             PRIMARY KEY,
    OrderNumber int             NOT NULL,
    OrderDate   date            DEFAULT CAST(GETDATE() AS date)
);

-- Ambos: ao inserir sem informar OrderDate, a data atual é usada
INSERT INTO Orders (ID, OrderNumber) VALUES (1, 10248);
-- OrderDate = data de hoje automaticamente
```

## DEFAULT no ALTER TABLE — Adicionando depois

```sql
-- MySQL
ALTER TABLE Persons
ALTER City SET DEFAULT 'Sandnes';

-- SQL Server: com nome de constraint
ALTER TABLE Persons
ADD CONSTRAINT df_City DEFAULT 'Sandnes' FOR City;

-- MS Access
ALTER TABLE Persons
ALTER COLUMN City SET DEFAULT 'Sandnes';

-- Oracle
ALTER TABLE Persons
MODIFY City DEFAULT 'Sandnes';
```

## Removendo a constraint DEFAULT

```sql
-- MySQL
ALTER TABLE Persons ALTER City DROP DEFAULT;

-- SQL Server
ALTER TABLE Persons DROP CONSTRAINT df_City;

-- MS Access
ALTER TABLE Persons ALTER COLUMN City DROP DEFAULT;

-- Oracle
ALTER TABLE Persons MODIFY (City DEFAULT NULL);
```

## DEFAULT vs NOT NULL — Diferença importante

```sql
-- Coluna com DEFAULT mas sem NOT NULL:
-- → Se não informada: recebe o DEFAULT
-- → Se explicitamente NULL: aceita NULL
City varchar(255) DEFAULT 'Sandnes'

-- Coluna com DEFAULT E NOT NULL:
-- → Se não informada: recebe o DEFAULT
-- → Se explicitamente NULL: ERRO — NOT NULL rejeita
City varchar(255) DEFAULT 'Sandnes' NOT NULL
```

---

# 52. CREATE INDEX — Otimizando performance de buscas

## O que é um índice?

Um **índice** em SQL funciona como o índice de um livro: em vez de ler o livro página por página para encontrar um assunto, você consulta o índice e vai direto à página certa. Da mesma forma, um índice no banco de dados permite localizar registros **sem varrer a tabela inteira** — o que faz uma diferença enorme em tabelas com milhões de linhas.

Os usuários não veem os índices — eles são transparentes. O banco decide automaticamente quando usá-los.

## O custo dos índices

Índices aceleram `SELECT`, mas **aumentam o custo** de `INSERT`, `UPDATE` e `DELETE`, pois o índice também precisa ser atualizado a cada modificação. Por isso, indexe apenas colunas que são frequentemente usadas em filtros (`WHERE`), ordenações (`ORDER BY`) e JOINs.

## Tipos de índice

```sql
-- Índice não-único: duplicatas são permitidas (mais comum)
-- Cria um índice chamado idx_lastname na coluna LastName da tabela Persons
CREATE INDEX idx_lastname
ON Persons (LastName);

-- Índice único: não permite valores duplicados
-- Equivalente a uma constraint UNIQUE com melhor performance de busca
CREATE UNIQUE INDEX idx_email
ON Customers (Email);
```

## Índice composto — múltiplas colunas

```sql
-- Índice em combinação de colunas
-- Otimiza queries que filtram ou ordenam por LastName E FirstName juntos
CREATE INDEX idx_lname_fname
ON Persons (LastName, FirstName);
```

✅ A **ordem** das colunas em um índice composto importa: o índice acima otimiza queries com `WHERE LastName = ?` ou `WHERE LastName = ? AND FirstName = ?`, mas **não** otimiza `WHERE FirstName = ?` sozinho.

## Quando criar índices

```sql
-- ✅ Boas candidatas para índice:
-- 1. Colunas frequentemente usadas no WHERE
CREATE INDEX idx_country ON Customers (Country);

-- 2. Colunas de JOIN (chaves estrangeiras)
CREATE INDEX idx_orders_customerid ON Orders (CustomerID);

-- 3. Colunas frequentemente usadas no ORDER BY
CREATE INDEX idx_products_price ON Products (Price);

-- 4. Colunas com alta cardinalidade (muitos valores distintos)
CREATE INDEX idx_email ON Users (Email);
```

```sql
-- ❌ Evite índices em:
-- 1. Tabelas muito pequenas (a varredura completa é mais rápida)
-- 2. Colunas raramente usadas em filtros
-- 3. Colunas com poucos valores distintos (ex: Boolean, Status com 2-3 opções)
-- 4. Tabelas com muitas operações de escrita (INSERT/UPDATE/DELETE intensos)
```

## Removendo um índice

```sql
-- SQL Server
DROP INDEX Persons.idx_lastname;

-- MySQL
ALTER TABLE Persons DROP INDEX idx_lastname;

-- MS Access
DROP INDEX idx_lastname ON Persons;

-- Oracle / DB2
DROP INDEX idx_lastname;
```

---

# 53. AUTO INCREMENT — IDs automáticos por banco

## O que é AUTO INCREMENT?

O auto-increment é um mecanismo que **gera automaticamente um número único** e crescente toda vez que um novo registro é inserido. É usado quase sempre na coluna de `PRIMARY KEY` para garantir que cada linha tenha um identificador único sem precisar calculá-lo manualmente.

Cada banco de dados tem sua própria sintaxe para implementar esse recurso.

## MySQL — AUTO_INCREMENT

```sql
-- Personid é gerado automaticamente: 1, 2, 3, 4...
CREATE TABLE Persons (
    Personid    int             AUTO_INCREMENT PRIMARY KEY,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int
);

-- Inserindo sem informar o Personid
INSERT INTO Persons (FirstName, LastName)
VALUES ('Lars', 'Monsen');
-- Personid = 1 (gerado automaticamente)

INSERT INTO Persons (FirstName, LastName)
VALUES ('Maria', 'Santos');
-- Personid = 2 (próximo valor automático)
```

```sql
-- Alterando o valor inicial do AUTO_INCREMENT
-- Útil para sistemas que precisam de IDs a partir de um número específico
ALTER TABLE Persons AUTO_INCREMENT = 100;
-- O próximo INSERT gerará Personid = 100, depois 101, 102...
```

## SQL Server — IDENTITY

```sql
-- IDENTITY(valor_inicial, incremento)
-- IDENTITY(1,1): começa em 1, incrementa de 1 em 1
CREATE TABLE Persons (
    Personid    int             IDENTITY(1,1) PRIMARY KEY,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int
);

-- IDENTITY(10,5): começa em 10, incrementa de 5 em 5
-- Geraria: 10, 15, 20, 25, 30...
CREATE TABLE Persons2 (
    Personid    int             IDENTITY(10,5) PRIMARY KEY,
    LastName    varchar(255)    NOT NULL
);
```

## MS Access — AUTOINCREMENT

```sql
-- MS Access usa a palavra AUTOINCREMENT
CREATE TABLE Persons (
    Personid    AUTOINCREMENT   PRIMARY KEY,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255),
    Age         int
);

-- Com valor inicial e incremento: AUTOINCREMENT(10,5)
CREATE TABLE Persons2 (
    Personid    AUTOINCREMENT(10,5) PRIMARY KEY,
    LastName    varchar(255)    NOT NULL
);
```

## Oracle — SEQUENCE

```sql
-- Oracle usa um objeto SEQUENCE separado
-- Cria a sequência seq_person
CREATE SEQUENCE seq_person
MINVALUE 1
START WITH 1
INCREMENT BY 1
CACHE 10;           -- pré-carrega 10 valores em memória para performance

-- Ao inserir, usa seq_person.nextval para obter o próximo ID
INSERT INTO Persons (Personid, FirstName, LastName)
VALUES (seq_person.nextval, 'Lars', 'Monsen');
```

## PostgreSQL — SERIAL (legado) e GENERATED AS IDENTITY (recomendado)

```sql
-- ⚠️ SERIAL: ainda funciona, mas é sintaxe proprietária do PostgreSQL
-- Considerado legado desde PostgreSQL 10 (2017) — evite em novos projetos
CREATE TABLE Persons (
    Personid    SERIAL          PRIMARY KEY,
    LastName    varchar(255)    NOT NULL,
    FirstName   varchar(255)
);

-- ✅ GENERATED ALWAYS AS IDENTITY: padrão SQL, recomendado desde PostgreSQL 10+
-- Vantagens sobre SERIAL:
--   1. É padrão SQL — código mais portável
--   2. GENERATED ALWAYS impede inserção manual acidental de IDs
--   3. Gerenciamento de sequência é mais robusto
--   4. Evita conflitos de duplicata ao inserir valores explícitos
CREATE TABLE Persons (
    Personid    int GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    LastName    varchar(255) NOT NULL,
    FirstName   varchar(255)
);

-- GENERATED BY DEFAULT: permite inserir valor manual quando necessário
-- Use quando precisar migrar dados com IDs existentes
CREATE TABLE PersonsMigration (
    Personid    int GENERATED BY DEFAULT AS IDENTITY PRIMARY KEY,
    LastName    varchar(255) NOT NULL
);
```

⚠️ **Por que não usar mais `SERIAL`?** Ao usar `SERIAL`, a sequência interna é criada separada da coluna — o que pode causar problemas de permissão, conflitos ao copiar schemas e dificuldade de migração para outros bancos. O `GENERATED AS IDENTITY` é padrão SQL desde a versão 10 e é unanimemente recomendado pela comunidade PostgreSQL para novos projetos.

## Tabela comparativa por banco de dados

| Banco | Sintaxe atual recomendada | Status |
|---|---|---|
| MySQL / MariaDB | `AUTO_INCREMENT` | ✅ Atual |
| SQL Server | `IDENTITY(start, step)` | ✅ Atual |
| MS Access | `AUTOINCREMENT(start, step)` | ✅ Atual |
| Oracle | `SEQUENCE` separado ou `GENERATED AS IDENTITY` (12c+) | ✅ Atual |
| PostgreSQL | `GENERATED ALWAYS AS IDENTITY` | ✅ Padrão SQL (desde v10) |
| PostgreSQL | `SERIAL` | ⚠️ Legado — ainda funciona, não recomendado |
| SQLite | `INTEGER PRIMARY KEY` | ✅ Atual (ROWID implícito) |

---

# 54. Trabalhando com Datas

## A maior fonte de bugs em SQL

Datas são, de longe, a maior fonte de bugs sutis e difíceis de reproduzir em SQL. O motivo principal: **formato de data vs componente de hora**. Um campo `DATETIME` com hora `13:23:44` não é igual a uma comparação com `'2025-11-11'` que o banco interpreta como `'2025-11-11 00:00:00'`.

## Tipos de dados de data por banco

**MySQL:**

| Tipo | Formato | Exemplo |
|---|---|---|
| `DATE` | YYYY-MM-DD | `2025-11-11` |
| `DATETIME` | YYYY-MM-DD HH:MI:SS | `2025-11-11 13:23:44` |
| `TIMESTAMP` | YYYY-MM-DD HH:MI:SS | `2025-11-11 13:23:44` |
| `TIME` | HH:MI:SS | `13:23:44` |
| `YEAR` | YYYY ou YY | `2025` |

**SQL Server:**

| Tipo | Formato | Observação |
|---|---|---|
| `DATE` | YYYY-MM-DD | Apenas data |
| `DATETIME` | YYYY-MM-DD HH:MI:SS | Data + hora |
| `SMALLDATETIME` | YYYY-MM-DD HH:MI:SS | Menos precisão, menor espaço |
| `TIME` | HH:MI:SS | Apenas hora |
| `TIMESTAMP` | número único | Versão do registro, não data real |

## O problema do componente de hora

```sql
-- Tabela Orders com colunas DATE (sem hora) e DATETIME (com hora)
-- ✅ FUNCIONA: OrderDate é DATE, comparação direta funciona
SELECT * FROM Orders WHERE OrderDate = '2025-11-11';
-- Resultado: retorna pedidos do dia 11/11/2025

-- ❌ NÃO FUNCIONA: se OrderDate for DATETIME com hora
-- '2025-11-11' é interpretado como '2025-11-11 00:00:00'
-- Nenhum pedido das 13h será retornado!
SELECT * FROM Orders WHERE OrderDate = '2025-11-11';
```

📄 Tabela com DATETIME — comparação falha:

| OrderId | ProductName | OrderDate |
|---|---|---|
| 1 | Geitost | 2025-11-11 **13:23:44** |
| 3 | Mozzarella | 2025-11-11 **11:12:01** |

A query acima retornaria **zero linhas** porque `13:23:44 ≠ 00:00:00`.

## Soluções para filtrar DATETIME por data

```sql
-- ✅ Opção 1: usar BETWEEN cobrindo o dia inteiro
SELECT * FROM Orders
WHERE OrderDate BETWEEN '2025-11-11 00:00:00' AND '2025-11-11 23:59:59';

-- ✅ Opção 2: usar >= e < (mais robusto, evita problema com milissegundos)
SELECT * FROM Orders
WHERE OrderDate >= '2025-11-11'
  AND OrderDate <  '2025-11-12';

-- ✅ Opção 3: extrair apenas a parte da data (MySQL)
SELECT * FROM Orders
WHERE DATE(OrderDate) = '2025-11-11';

-- ✅ Opção 4: SQL Server — converter para DATE
SELECT * FROM Orders
WHERE CAST(OrderDate AS DATE) = '2025-11-11';
```

⚠️ A opção `DATE(OrderDate) = '2025-11-11'` e `CAST(OrderDate AS DATE)` funcionam, mas **não aproveitam índices** na coluna `OrderDate`. Para tabelas grandes, a opção 2 (com `>=` e `<`) é a mais eficiente pois permite uso de índice.

## Boas práticas com datas

```sql
-- ✅ Use sempre o formato ISO 8601: YYYY-MM-DD
-- Funciona em todos os bancos e evita ambiguidade regional
WHERE OrderDate = '2025-11-11';    -- ✅ sem ambiguidade

-- ❌ Evite formatos regionais — podem ser interpretados diferente por banco
WHERE OrderDate = '11/11/2025';    -- ❌ DD/MM ou MM/DD?
WHERE OrderDate = '11-Nov-2025';   -- ❌ dependente de configuração de idioma
```

---

# 55. Views — Tabelas virtuais reutilizáveis

## O que é uma View?

Uma **View** é uma tabela virtual baseada no resultado de uma query SQL. Ela não armazena dados — apenas armazena a **definição** (o `SELECT`). Quando você consulta uma View, o banco executa a query subjacente e retorna os dados em tempo real.

Views são usadas para:
- **Simplificar** queries complexas reutilizadas frequentemente
- **Restringir acesso** a colunas sensíveis (ex: esconder salários)
- **Padronizar** a forma como diferentes equipes enxergam os dados
- **Encapsular** lógica de negócio na camada de banco de dados

## Criando uma View

```sql
-- Cria uma View que mostra apenas clientes do Brasil
-- A View se comporta como uma tabela — pode ser consultada com SELECT
CREATE VIEW BrazilCustomers AS
SELECT CustomerName, ContactName, City
FROM Customers
WHERE Country = 'Brazil';
```

```sql
-- Consultando a View exatamente como uma tabela normal
SELECT * FROM BrazilCustomers;

-- Filtrando sobre a View
SELECT * FROM BrazilCustomers
WHERE City = 'São Paulo';
```

```sql
-- View mais complexa: produtos acima da média de preço
-- Encapsula a subquery de AVG para reutilização
CREATE VIEW ProductsAboveAveragePrice AS
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);

-- Consultando a View
SELECT * FROM ProductsAboveAveragePrice
ORDER BY Price DESC;
```

## Atualizando uma View

```sql
-- SQL Server: usa ALTER VIEW para modificar a definição
ALTER VIEW BrazilCustomers AS
SELECT CustomerName, ContactName, City, PostalCode   -- adicionou PostalCode
FROM Customers
WHERE Country = 'Brazil';

-- MySQL e Oracle: usa CREATE OR REPLACE VIEW (cria se não existir, substitui se existir)
CREATE OR REPLACE VIEW BrazilCustomers AS
SELECT CustomerName, ContactName, City, PostalCode
FROM Customers
WHERE Country = 'Brazil';
```

## Removendo uma View

```sql
-- Remove a definição da View (os dados originais não são afetados)
DROP VIEW BrazilCustomers;

-- ✅ Com verificação: não retorna erro se a View não existir
DROP VIEW IF EXISTS BrazilCustomers;
```

## Casos de uso práticos

```sql
-- View para relatório executivo: esconde colunas sensíveis
CREATE VIEW CustomerPublicInfo AS
SELECT CustomerID, CustomerName, City, Country
FROM Customers;
-- A coluna CreditLimit não aparece na View

-- View para análise: join pré-feito, pronto para uso
CREATE VIEW OrderSummary AS
SELECT
    o.OrderID,
    c.CustomerName,
    o.OrderDate,
    s.ShipperName,
    SUM(od.Quantity * p.Price) AS order_total
FROM Orders           AS o
INNER JOIN Customers  AS c  ON o.CustomerID  = c.CustomerID
INNER JOIN Shippers   AS s  ON o.ShipperID   = s.ShipperID
INNER JOIN OrderDetails AS od ON o.OrderID   = od.OrderID
INNER JOIN Products   AS p  ON od.ProductID  = p.ProductID
GROUP BY o.OrderID, c.CustomerName, o.OrderDate, s.ShipperName;

-- Qualquer analista pode usar sem conhecer os JOINs
SELECT * FROM OrderSummary WHERE CustomerName LIKE 'A%';
```

---

# 56. SQL Injection — O ataque e a defesa

## O que é SQL Injection?

SQL Injection é um dos ataques mais antigos e ainda mais perigosos da web. Ele ocorre quando um atacante insere **código SQL malicioso** em campos de entrada de dados (formulários, URLs, APIs), e esse código é executado pelo banco de dados como se fosse uma query legítima.

O resultado pode ser: leitura de dados sensíveis, alteração ou exclusão de dados, autenticação bypassed, ou até destruição completa do banco.

## Como o ataque funciona

### Cenário vulnerável — código que NÃO deve ser escrito

```sql
-- ❌ CÓDIGO VULNERÁVEL: concatenação direta de input do usuário no SQL
-- txtUserId vem diretamente do input do usuário sem validação
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```

Se o usuário inserir normalmente `105`, a query gerada é:
```sql
SELECT * FROM Users WHERE UserId = 105;
-- ✅ Comportamento esperado — retorna apenas o usuário 105
```

### Ataque 1 — OR 1=1 (sempre verdadeiro)

Se o atacante inserir `105 OR 1=1` no campo:
```sql
-- Query resultante — retorna TODOS os usuários
SELECT * FROM Users WHERE UserId = 105 OR 1=1;
-- 1=1 é sempre TRUE → WHERE é ignorado → todos os dados expostos
```

### Ataque 2 — Bypass de login

```sql
-- ❌ CÓDIGO VULNERÁVEL: login por concatenação
sql = 'SELECT * FROM Users WHERE Name="' + uName + '" AND Pass="' + uPass + '"'

-- Atacante insere no campo username: " OR ""="
-- Query resultante:
SELECT * FROM Users WHERE Name="" OR ""="" AND Pass="" OR ""=""
-- ""="" é sempre TRUE → autentica qualquer usuário sem senha
```

### Ataque 3 — Injeção de múltiplos comandos

```sql
-- ❌ CÓDIGO VULNERÁVEL
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;

-- Atacante insere: 105; DROP TABLE Suppliers
-- Query resultante — executa DUAS queries:
SELECT * FROM Users WHERE UserId = 105;
DROP TABLE Suppliers;   -- ← tabela destruída!
```

## A defesa — Nunca concatene input direto em SQL

A regra é simples e absoluta: **nunca construa queries SQL com concatenação de strings vindas do usuário**. Sempre use Parameterized Queries ou Prepared Statements (próximos capítulos).

---

# 57. Parameterized Queries — Consultas parametrizadas

## O que são Parameterized Queries?

Em vez de embutir os valores diretamente na string SQL, as Parameterized Queries usam **placeholders** no lugar dos valores. O banco de dados trata os valores como dados puros — nunca como parte do código SQL — eliminando completamente o risco de SQL Injection.

## Como funciona

```sql
-- ❌ VULNERÁVEL: valor embutido diretamente
"SELECT * FROM Users WHERE UserId = " + userId

-- ✅ SEGURO: placeholder no lugar do valor
"SELECT * FROM Users WHERE UserId = @userid"
-- O valor real é enviado separadamente ao banco
```

## Sintaxe de placeholder por banco

| Banco | Placeholder | Exemplo |
|---|---|---|
| SQL Server | `@nome` | `WHERE UserId = @userid` |
| MySQL | `?` | `WHERE UserId = ?` |
| PostgreSQL | `$1`, `$2`... | `WHERE UserId = $1` |
| Oracle | `:nome` | `WHERE UserId = :userid` |

## Exemplo em ASP.NET (SQL Server)

```csharp
// SELECT parametrizado — ASP.NET com SQL Server
userid = getRequestString("UserId");
query = "SELECT * FROM Customers WHERE CustomerId = @userid";

cmd = new SqlCommand(query);
cmd.Parameters.AddWithValue("@userid", userid);
cmd.ExecuteReader();
// O valor de userid é passado separadamente — nunca como código SQL
```

```csharp
// INSERT parametrizado — múltiplos parâmetros
cname   = getRequestString("CustomerName");
caddress = getRequestString("Address");
ccity   = getRequestString("City");

query = "INSERT INTO Customers (CustomerName, Address, City) VALUES(@cname, @caddress, @ccity)";

cmd = new SqlCommand(query);
cmd.Parameters.AddWithValue("@cname",    cname);
cmd.Parameters.AddWithValue("@caddress", caddress);
cmd.Parameters.AddWithValue("@ccity",    ccity);
cmd.ExecuteNonQuery();
```

---

# 58. Prepared Statements — Máxima segurança e performance

## O que são Prepared Statements?

Prepared Statements levam o conceito de parameterized queries um passo adiante: a query é **compilada uma vez** pelo banco de dados e pode ser **executada múltiplas vezes** com valores diferentes. Isso traz dois benefícios simultâneos: **segurança** (imunidade a SQL Injection) e **performance** (parsing e otimização acontecem apenas uma vez).

## Como funcionam em duas etapas

```
Etapa 1 — PREPARE:
  ↓ Aplicação envia o template SQL com placeholders (?)
  ↓ Banco analisa, compila e otimiza o template
  ↓ Banco aguarda os valores reais

Etapa 2 — EXECUTE:
  ↓ Aplicação envia os valores vinculados aos placeholders
  ↓ Banco substitui e executa com os valores reais
  ↓ Processo pode se repetir N vezes com valores diferentes
```

## Vantagens dos Prepared Statements

| Vantagem | Descrição |
|---|---|
| ✅ Segurança | Imune a SQL Injection — valores nunca são interpretados como código |
| ✅ Performance | Query compilada apenas uma vez; execuções subsequentes são muito rápidas |
| ✅ Economia de banda | Apenas os parâmetros são enviados nas execuções repetidas |
| ✅ Código mais limpo | Separação clara entre estrutura SQL e dados |

## Exemplo em PHP com MySQL

```php
<?php
$servername = "localhost";
$username   = "username";
$password   = "password";
$dbname     = "myDB";

// Criando a conexão
$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// Template SQL com placeholders (?) — enviado ao banco para compilação
$sql = "INSERT INTO MyGuests (firstname, lastname, email) VALUES (?, ?, ?)";

// Prepare: banco compila o template
if ($stmt = $conn->prepare($sql)) {

    // Bind: vincula variáveis PHP aos placeholders
    // "sss" = três strings (s=string, i=integer, d=double, b=binary)
    $stmt->bind_param("sss", $firstname, $lastname, $email);

    // Execute 1: primeiro registro
    $firstname = "John";
    $lastname  = "Doe";
    $email     = "john@example.com";
    $stmt->execute();   // usa a query já compilada — muito rápido

    // Execute 2: segundo registro — mesma query compilada, valores diferentes
    $firstname = "Mary";
    $lastname  = "Moe";
    $email     = "mary@example.com";
    $stmt->execute();

    // Execute 3: terceiro registro
    $firstname = "Julie";
    $lastname  = "Dooley";
    $email     = "julie@example.com";
    $stmt->execute();

    echo "Registros inseridos com sucesso!";
} else {
    echo "Erro: " . $conn->error;
}

$stmt->close();
$conn->close();
?>
```

### Tipos de binding no PHP/MySQL

| Código | Tipo SQL | Exemplo de valor |
|---|---|---|
| `i` | INTEGER | `42`, `-5`, `1000` |
| `d` | DOUBLE | `19.99`, `3.14` |
| `s` | STRING (VARCHAR, TEXT) | `"João"`, `"Brazil"` |
| `b` | BINARY (imagem, PDF) | dados binários |

---

# 59. Hospedagem SQL — Escolhendo o banco certo

## O cenário de escolha

Se você vai construir uma aplicação web que armazena e recupera dados de um banco de dados, precisará de um servidor com um RDBMS instalado. Ao contratar um serviço de hospedagem, verifique qual banco de dados está disponível no plano.

## MySQL

MySQL é o banco de dados open-source mais popular da web e uma das primeiras escolhas para aplicações web de todos os tamanhos.

| Aspecto | Avaliação |
|---|---|
| Performance | ✅ Excelente para leitura intensiva |
| Facilidade de uso | ✅ Excelente, ampla documentação |
| Custo | ✅ Open-source e gratuito |
| Suporte | ✅ Vasta comunidade |
| Melhor para | Aplicações web, startups, projetos de médio porte |

## Microsoft SQL Server

SQL Server é a escolha natural para aplicações empresariais no ecossistema Microsoft, com forte integração com .NET, Azure e ferramentas de BI.

| Aspecto | Avaliação |
|---|---|
| Performance | ✅ Excelente para alto tráfego |
| Integração Microsoft | ✅ Azure, Power BI, .NET nativos |
| Segurança | ✅ Recursos avançados |
| Custo | ⚠️ Licenciamento caro |
| Melhor para | Empresas no ecossistema Microsoft, alto tráfego |

## Oracle

Oracle é o banco de dados enterprise por excelência — extremamente robusto e escalável, mas com alto custo e complexidade de administração.

| Aspecto | Avaliação |
|---|---|
| Escalabilidade | ✅ Extrema — bancos de nível global |
| Performance | ✅ Excelente |
| Confiabilidade | ✅ Altíssima |
| Custo | ❌ Muito caro |
| Complexidade | ⚠️ Alta curva de aprendizado |
| Melhor para | Grandes corporações, bancos, telecomunicações |

## PostgreSQL

PostgreSQL é o banco open-source mais avançado tecnicamente — suporte completo ao padrão SQL, extensibilidade, tipos de dados avançados (JSON, arrays, geoespacial) e alta integridade de dados.

| Aspecto | Avaliação |
|---|---|
| Conformidade SQL | ✅ A melhor entre os open-source |
| Recursos avançados | ✅ JSON, Full-Text Search, geoespacial |
| Performance | ✅ Excelente para operações complexas |
| Custo | ✅ Open-source e gratuito |
| Comunidade | ✅ Ativa e crescente |
| Melhor para | Aplicações complexas, ciência de dados, startups técnicas |

## Tabela comparativa final

| Critério | MySQL | SQL Server | Oracle | PostgreSQL |
|---|---|---|---|---|
| Custo | Gratuito | Pago | Muito caro | Gratuito |
| Facilidade | Alta | Média | Baixa | Média |
| Performance leitura | ✅ | ✅ | ✅ | ✅ |
| Performance escrita | ✅ | ✅ | ✅ | ✅ |
| Conformidade SQL | Média | Alta | Alta | Muito alta |
| JSON/NoSQL híbrido | ✅ | ✅ | ✅ | ✅ |
| Escalabilidade | Alta | Muito alta | Máxima | Alta |
| Ecosistema cloud | AWS, GCP, Azure | Azure | OCI, AWS | AWS, GCP, Azure |

---

# 60. Ordem de execução de uma query SQL

## O conceito mais importante que ninguém explica

Uma das confusões mais comuns entre iniciantes e mesmo desenvolvedores intermediários é não entender a **ordem em que o banco de dados executa** as cláusulas de uma query. A ordem em que você *escreve* o SQL não é a ordem em que ele é *executado*.

Entender isso explica muitos comportamentos aparentemente estranhos: por que você não pode usar um alias do `SELECT` dentro do `WHERE`, por que o `HAVING` filtra agrupamentos mas o `WHERE` não pode usar agregações, e por que aliases de tabela precisam existir antes de serem referenciados.

## A query completa — ordem de escrita vs. ordem de execução

```sql
-- ORDEM DE ESCRITA (como você digita):
SELECT   DISTINCT column, AGG_FUNC(column_or_expression) AS alias  -- 1º escrito
FROM     mytable                                                     -- 2º escrito
JOIN     another_table ON mytable.column = another_table.column      -- 3º escrito
WHERE    constraint_expression                                        -- 4º escrito
GROUP BY column                                                       -- 5º escrito
HAVING   aggregate_condition                                          -- 6º escrito
ORDER BY column ASC|DESC                                              -- 7º escrito
LIMIT    count OFFSET count;                                          -- 8º escrito
```

```
ORDEM DE EXECUÇÃO (como o banco processa):

Etapa 1 → FROM + JOINs        — define o conjunto total de dados de trabalho
Etapa 2 → WHERE               — filtra linhas individuais do conjunto
Etapa 3 → GROUP BY            — agrupa as linhas restantes
Etapa 4 → HAVING              — filtra os grupos
Etapa 5 → SELECT              — calcula as expressões e escolhe as colunas
Etapa 6 → DISTINCT            — remove duplicatas do resultado
Etapa 7 → ORDER BY            — ordena o resultado
Etapa 8 → LIMIT / OFFSET      — recorta o número final de linhas
```

## Por que isso importa na prática?

### Aliases do SELECT não estão disponíveis no WHERE

```sql
-- ❌ ERRO: o alias 'discounted_price' não existe ainda quando WHERE é avaliado
-- O WHERE é executado ANTES do SELECT calcular o alias
SELECT Price * 0.9 AS discounted_price
FROM Products
WHERE discounted_price < 20;      -- erro: coluna desconhecida

-- ✅ CORRETO: repita a expressão no WHERE (o banco vai otimizar)
SELECT Price * 0.9 AS discounted_price
FROM Products
WHERE Price * 0.9 < 20;

-- ✅ ALTERNATIVA: use subquery para aproveitar o alias
SELECT * FROM (
    SELECT Price * 0.9 AS discounted_price, ProductName
    FROM Products
) AS subquery
WHERE discounted_price < 20;
```

### WHERE não pode usar funções de agregação

```sql
-- ❌ ERRO: o WHERE é executado ANTES do GROUP BY e HAVING
-- As agregações (COUNT, SUM, etc.) ainda não existem nessa etapa
SELECT Country, COUNT(*) AS total
FROM Customers
WHERE COUNT(*) > 5;       -- erro: não pode usar agregação no WHERE

-- ✅ CORRETO: use HAVING para filtrar após a agregação
SELECT Country, COUNT(*) AS total
FROM Customers
GROUP BY Country
HAVING COUNT(*) > 5;
```

### ORDER BY pode usar aliases — HAVING não pode

```sql
-- ✅ ORDER BY é executado APÓS o SELECT → pode usar aliases
SELECT Country, COUNT(*) AS total_customers
FROM Customers
GROUP BY Country
HAVING COUNT(*) > 5
ORDER BY total_customers DESC;  -- alias disponível aqui ✅

-- ❌ HAVING é executado ANTES do SELECT → não pode usar aliases na maioria dos bancos
SELECT Country, COUNT(*) AS total_customers
FROM Customers
GROUP BY Country
HAVING total_customers > 5;    -- erro na maioria dos bancos ❌
```

## Tabela completa de ordem de execução

| Etapa | Cláusula | O que faz | Acessa aliases do SELECT? |
|---|---|---|---|
| 1 | `FROM` + `JOIN` | Define o conjunto de trabalho completo | ❌ |
| 2 | `WHERE` | Filtra linhas individuais | ❌ |
| 3 | `GROUP BY` | Agrupa as linhas restantes | ❌ |
| 4 | `HAVING` | Filtra grupos (após agregação) | ❌ (maioria dos bancos) |
| 5 | `SELECT` | Calcula expressões e aliases | — (é aqui que surgem) |
| 6 | `DISTINCT` | Remove duplicatas | ✅ |
| 7 | `ORDER BY` | Ordena o resultado final | ✅ |
| 8 | `LIMIT`/`OFFSET` | Recorta o número de linhas | ✅ |

---

# 61. Subqueries — Consultas aninhadas

## O que são subqueries?

Uma **subquery** (subconsulta) é uma query `SELECT` aninhada dentro de outra query. Ela pode aparecer no `WHERE`, no `FROM`, no `SELECT` ou no `HAVING` — em qualquer lugar onde uma tabela ou valor seria normalmente esperado.

Subqueries resolvem problemas que precisam de duas etapas: primeiro calcular algo, depois usar esse resultado para filtrar ou transformar dados.

## Subquery no WHERE — O caso mais comum

```sql
-- Problema: quais associados custam mais do que a receita média gerada pela equipe?
-- Passo 1 (subquery): calcula a receita média
-- Passo 2 (query externa): compara o salário de cada associado com a média

SELECT *
FROM sales_associates
WHERE salary > (
    SELECT AVG(revenue_generated)
    FROM sales_associates
);
-- A subquery executa primeiro e retorna um único valor
-- Esse valor é então usado na comparação do WHERE externo
```

```sql
-- Produto mais caro da tabela
SELECT ProductName, Price
FROM Products
WHERE Price = (
    SELECT MAX(Price) FROM Products
);
```

## Onde subqueries podem aparecer

```sql
-- 1. No WHERE (mais comum)
SELECT * FROM Employees
WHERE DepartmentID IN (
    SELECT DepartmentID FROM Departments WHERE Location = 'São Paulo'
);

-- 2. No FROM (subquery como tabela — DEVE ter alias)
SELECT avg_data.department, avg_data.avg_salary
FROM (
    SELECT Department, AVG(Salary) AS avg_salary
    FROM Employees
    GROUP BY Department
) AS avg_data           -- alias obrigatório
WHERE avg_data.avg_salary > 8000;

-- 3. No SELECT (subquery escalar — retorna um único valor por linha)
SELECT
    ProductName,
    Price,
    (SELECT AVG(Price) FROM Products) AS overall_avg,
    Price - (SELECT AVG(Price) FROM Products) AS diff_from_avg
FROM Products
ORDER BY diff_from_avg DESC;

-- 4. No HAVING
SELECT Department, AVG(Salary) AS avg_salary
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > (
    SELECT AVG(Salary) FROM Employees
);
```

## Subquery correlacionada — O tipo mais poderoso

Uma **subquery correlacionada** referencia uma coluna da query externa. Para cada linha da query externa, a subquery é re-executada. São mais poderosas mas também mais lentas:

```sql
-- Encontra funcionários com salário acima da média do SEU PRÓPRIO departamento
-- Para cada funcionário (query externa), a subquery recalcula a média
-- usando dept_employees.department = employees.department como correlação
SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(revenue_generated)
    FROM employees AS dept_employees
    WHERE dept_employees.department = employees.department  -- correlação aqui
);
```

```sql
-- Clientes que fizeram pelo menos um pedido (usando EXISTS correlacionado)
SELECT CustomerName, Country
FROM Customers AS c
WHERE EXISTS (
    SELECT 1 FROM Orders AS o
    WHERE o.CustomerID = c.CustomerID   -- correlação com a query externa
);
```

⚠️ Subqueries correlacionadas podem ser lentas em tabelas grandes porque são re-executadas para cada linha da query externa. Sempre verifique o plano de execução (`EXPLAIN`) e considere reescrever com `JOIN` quando a performance for crítica.

## Subquery vs JOIN — Quando usar cada um

```sql
-- Estas duas queries retornam o mesmo resultado:

-- Com subquery (mais legível para quem está aprendendo)
SELECT * FROM Customers
WHERE CustomerID IN (
    SELECT CustomerID FROM Orders WHERE OrderDate >= '2024-01-01'
);

-- Com JOIN (geralmente mais eficiente)
SELECT DISTINCT c.*
FROM Customers AS c
INNER JOIN Orders AS o ON c.CustomerID = o.CustomerID
WHERE o.OrderDate >= '2024-01-01';
```

✅ Prefira `JOIN` quando possível para melhor performance. Use subquery quando a lógica é mais clara com ela, ou quando precisar de agregações intermediárias no `FROM`.

---

# 62. INTERSECT e EXCEPT — Operações de conjunto

## Além do UNION

O SQL tem três operadores de conjunto que combinam resultados de múltiplos `SELECT`. Já vimos o `UNION` e `UNION ALL`. Agora vamos aos outros dois: `INTERSECT` (interseção) e `EXCEPT` (diferença).

As mesmas regras do `UNION` se aplicam: mesmo número de colunas, tipos compatíveis, mesma ordem.

## Sintaxe geral

```sql
-- Estrutura dos operadores de conjunto
SELECT column, another_column FROM table1
UNION | UNION ALL | INTERSECT | EXCEPT
SELECT other_column, yet_another_column FROM table2
ORDER BY column DESC
LIMIT n;
```

⚠️ O `ORDER BY` e `LIMIT` se aplicam ao resultado **final** da operação de conjunto — não a cada `SELECT` individualmente.

## INTERSECT — Apenas o que existe em ambos

O `INTERSECT` retorna apenas as linhas que existem **simultaneamente** nos dois resultados. Remove duplicatas por padrão.

```sql
-- Retorna países que aparecem TANTO em Customers QUANTO em Suppliers
-- Apenas os países presentes nos dois conjuntos são retornados
SELECT Country FROM Customers
INTERSECT
SELECT Country FROM Suppliers
ORDER BY Country;
```

📄 Exemplo visual:

```
Customers Countries:  {Germany, Mexico, UK, Brazil, France}
Suppliers Countries:  {UK, USA, Germany, Japan, Australia}

INTERSECT resultado:  {Germany, UK}   ← apenas os que estão nos dois
```

```sql
-- Funcionários que estão em AMBAS as listas (ativa e treinamento)
SELECT EmployeeID FROM ActiveEmployees
INTERSECT
SELECT EmployeeID FROM TrainingProgram;
```

## EXCEPT — O que existe no primeiro mas não no segundo

O `EXCEPT` retorna as linhas que existem no **primeiro** resultado mas **não** no segundo. É sensível à ordem: `A EXCEPT B` ≠ `B EXCEPT A`.

```sql
-- Países de Customers que NÃO aparecem em Suppliers
SELECT Country FROM Customers
EXCEPT
SELECT Country FROM Suppliers
ORDER BY Country;
```

📄 Exemplo visual:

```
Customers Countries:  {Germany, Mexico, UK, Brazil, France}
Suppliers Countries:  {UK, USA, Germany, Japan, Australia}

EXCEPT resultado:     {Mexico, Brazil, France}  ← só em Customers, não em Suppliers
```

```sql
-- Clientes que NÃO têm pedido (alternativa ao LEFT JOIN + IS NULL)
SELECT CustomerID FROM Customers
EXCEPT
SELECT DISTINCT CustomerID FROM Orders;
```

## Versões ALL — Mantendo duplicatas

```sql
-- INTERSECT ALL: mantém duplicatas nas linhas coincidentes
SELECT ProductID FROM OrdersQ1
INTERSECT ALL
SELECT ProductID FROM OrdersQ2;

-- EXCEPT ALL: mantém duplicatas nas linhas excluídas
SELECT ProductID FROM AllProducts
EXCEPT ALL
SELECT ProductID FROM DiscontinuedProducts;
```

⚠️ `INTERSECT ALL` e `EXCEPT ALL` são suportados no PostgreSQL, mas com suporte variado em outros bancos. O MySQL, por exemplo, não suporta `INTERSECT` nem `EXCEPT` nativamente até recentemente (foram adicionados no MySQL 8.0.31).

## Tabela comparativa dos operadores de conjunto

| Operador | O que retorna | Duplicatas |
|---|---|---|
| `UNION` | Linhas de A **ou** B | Remove |
| `UNION ALL` | Linhas de A **ou** B | Mantém |
| `INTERSECT` | Linhas em A **e** B | Remove |
| `INTERSECT ALL` | Linhas em A **e** B | Mantém |
| `EXCEPT` | Linhas em A mas **não** em B | Remove |
| `EXCEPT ALL` | Linhas em A mas **não** em B | Mantém |

---

# 63. Window Functions — Funções de janela

## O que são Window Functions?

Window Functions (funções de janela) são um dos recursos mais poderosos do SQL moderno. Elas realizam **cálculos sobre um conjunto de linhas relacionadas à linha atual**, sem colapsar as linhas em uma única linha de sumário como o `GROUP BY` faz.

Em termos simples: com `GROUP BY` você perde as linhas individuais para obter agregações. Com Window Functions você mantém todas as linhas e adiciona a agregação como uma coluna extra.

Introduzidas no padrão SQL:2003, são suportadas em PostgreSQL, SQL Server, Oracle e MySQL 8.0+.

## Sintaxe

```sql
-- A cláusula OVER() define a "janela" sobre a qual a função opera
-- PARTITION BY divide os dados em grupos (como GROUP BY, mas sem colapsar)
-- ORDER BY dentro do OVER define a ordem dentro da janela
aggregate_function(column) OVER (
    PARTITION BY partition_column
    ORDER BY order_column
    ROWS/RANGE frame_specification
)
```

## RANK e ROW_NUMBER — Numerando e classificando

```sql
-- ROW_NUMBER: número sequencial único para cada linha, sem empates
SELECT
    EmployeeID,
    LastName,
    Department,
    Salary,
    ROW_NUMBER() OVER (
        PARTITION BY Department    -- reinicia a contagem por departamento
        ORDER BY Salary DESC       -- do maior para o menor salário
    ) AS salary_rank_in_dept
FROM Employees;
```

📄 Resultado:

| EmployeeID | LastName | Department | Salary | salary_rank_in_dept |
|---|---|---|---|---|
| 5 | Silva | Engineering | 12000 | 1 |
| 3 | Costa | Engineering | 10000 | 2 |
| 1 | Santos | Engineering | 8000 | 3 |
| 4 | Alves | Sales | 9000 | 1 |
| 2 | Lima | Sales | 7000 | 2 |

```sql
-- RANK: mesma posição para empates, pula posições seguintes (1, 2, 2, 4...)
-- DENSE_RANK: mesma posição para empates, sem pular (1, 2, 2, 3...)
SELECT
    ProductName,
    CategoryID,
    Price,
    RANK()       OVER (PARTITION BY CategoryID ORDER BY Price DESC) AS rank_with_gap,
    DENSE_RANK() OVER (PARTITION BY CategoryID ORDER BY Price DESC) AS rank_no_gap
FROM Products;
```

## LAG e LEAD — Acessando linhas vizinhas

```sql
-- LAG: acessa o valor de uma linha ANTERIOR
-- LEAD: acessa o valor de uma linha POSTERIOR
-- Muito úteis para análises de variação entre períodos

SELECT
    OrderDate,
    TotalAmount,
    LAG(TotalAmount)  OVER (ORDER BY OrderDate) AS previous_day_amount,
    LEAD(TotalAmount) OVER (ORDER BY OrderDate) AS next_day_amount,
    TotalAmount - LAG(TotalAmount) OVER (ORDER BY OrderDate) AS day_over_day_change
FROM DailySales
ORDER BY OrderDate;
```

## SUM e AVG como Window Functions — Running totals

```sql
-- Total acumulado (running total) de vendas por data
SELECT
    OrderDate,
    TotalAmount,
    SUM(TotalAmount) OVER (
        ORDER BY OrderDate
        ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
    ) AS cumulative_total
FROM DailySales;

-- Média móvel dos últimos 7 dias
SELECT
    OrderDate,
    TotalAmount,
    AVG(TotalAmount) OVER (
        ORDER BY OrderDate
        ROWS BETWEEN 6 PRECEDING AND CURRENT ROW  -- janela de 7 dias
    ) AS moving_avg_7days
FROM DailySales;
```

## NTILE — Dividindo em percentis

```sql
-- Divide os produtos em 4 quartis de preço
SELECT
    ProductName,
    Price,
    NTILE(4) OVER (ORDER BY Price) AS price_quartile
FROM Products;
-- Quartil 1 = produtos mais baratos, Quartil 4 = mais caros
```

## Window Functions vs GROUP BY

```sql
-- COM GROUP BY: perde as linhas individuais — apenas o sumário permanece
SELECT Department, AVG(Salary) AS avg_salary
FROM Employees
GROUP BY Department;
-- Resultado: 1 linha por departamento

-- COM WINDOW FUNCTION: mantém todas as linhas + adiciona a média como coluna
SELECT
    EmployeeID,
    LastName,
    Department,
    Salary,
    AVG(Salary) OVER (PARTITION BY Department) AS dept_avg_salary,
    Salary - AVG(Salary) OVER (PARTITION BY Department) AS diff_from_dept_avg
FROM Employees;
-- Resultado: todas as linhas dos funcionários, cada uma com a média do seu departamento
```

---

# 64. Transactions — COMMIT, ROLLBACK e ACID

## O que é uma Transaction?

Uma **Transaction** (transação) é uma sequência de operações SQL tratadas como uma **unidade atômica**: ou todas as operações são executadas com sucesso e confirmadas, ou nenhuma delas é aplicada ao banco de dados.

Transações protegem seus dados contra falhas parciais. Imagine uma transferência bancária: o débito na conta A e o crédito na conta B devem acontecer juntos — se qualquer uma falhar, nenhuma deve ser aplicada.

## As propriedades ACID

Transações seguem as propriedades **ACID**, o padrão de confiabilidade dos bancos de dados relacionais:

| Propriedade | Significado |
|---|---|
| **A**tomicity (Atomicidade) | Tudo ou nada — se qualquer parte falhar, tudo é revertido |
| **C**onsistency (Consistência) | O banco parte de um estado válido e chega a outro estado válido |
| **I**solation (Isolamento) | Transações simultâneas não interferem entre si |
| **D**urability (Durabilidade) | Uma vez confirmada (COMMIT), a transação persiste mesmo após falhas |

## Sintaxe básica

```sql
-- Iniciando uma transação explícita
BEGIN;                     -- MySQL/PostgreSQL
-- ou
BEGIN TRANSACTION;         -- SQL Server / padrão SQL

-- Operações dentro da transação
UPDATE Accounts SET Balance = Balance - 1000 WHERE AccountID = 1;  -- débito
UPDATE Accounts SET Balance = Balance + 1000 WHERE AccountID = 2;  -- crédito

-- Se tudo correu bem: confirma permanentemente
COMMIT;

-- Se algo deu errado: reverte todas as operações da transação
ROLLBACK;
```

## Exemplo prático — Transferência bancária segura

```sql
-- ✅ Transferência segura usando transação
BEGIN;

-- Passo 1: debitar da conta de origem
UPDATE Accounts
SET Balance = Balance - 500.00
WHERE AccountID = 101;

-- Verificar se o saldo ficou negativo (validação de negócio)
-- Se o saldo for insuficiente, revertemos
-- (Em linguagem procedural como PL/pgSQL ou T-SQL, seria um IF/ELSE)

-- Passo 2: creditar na conta de destino
UPDATE Accounts
SET Balance = Balance + 500.00
WHERE AccountID = 205;

-- Confirmar: ambas as operações foram bem-sucedidas
COMMIT;

-- Se qualquer erro ocorreu entre BEGIN e COMMIT:
-- ROLLBACK; -- reverte tudo como se nada tivesse acontecido
```

## SAVEPOINT — Pontos de salvamento parcial

```sql
-- SAVEPOINTs permitem reverter apenas parte de uma transação
BEGIN;

INSERT INTO Orders (CustomerID, OrderDate) VALUES (1, '2026-04-15');
SAVEPOINT after_order;         -- ponto de salvamento criado aqui

INSERT INTO OrderDetails (OrderID, ProductID, Quantity) VALUES (1001, 5, 3);

-- Algo deu errado nos detalhes, mas queremos manter o pedido
ROLLBACK TO SAVEPOINT after_order;   -- reverte apenas até o savepoint

-- O INSERT do Orders permanece; apenas o OrderDetails foi revertido
COMMIT;   -- confirma o que restou (o Orders)
```

## AUTOCOMMIT — O comportamento padrão

A maioria dos bancos opera em modo **AUTOCOMMIT** por padrão, onde cada instrução SQL é automaticamente uma transação própria — confirmada imediatamente após execução:

```sql
-- Em modo AUTOCOMMIT (padrão):
DELETE FROM Customers WHERE CustomerID = 42;
-- → Executado e COMMITADO imediatamente. Sem ROLLBACK possível.

-- Para desabilitar o AUTOCOMMIT no MySQL:
SET autocommit = 0;

-- Para desabilitar no PostgreSQL:
-- Use BEGIN explicitamente para iniciar a transação
BEGIN;
DELETE FROM Customers WHERE CustomerID = 42;
-- Ainda pode fazer ROLLBACK aqui
ROLLBACK;  -- registro restaurado
```

---

# 65. Versões atuais dos bancos de dados em 2026

## Por que versões importam?

Recursos como `GENERATED AS IDENTITY` (PostgreSQL 10+), `CHECK` funcional (MySQL 8.0.16+), `INTERSECT`/`EXCEPT` (MySQL 8.0.31+) e Window Functions (MySQL 8.0+) dependem da versão do banco. Conhecer as versões ativas em produção é essencial para saber quais features são seguras de usar.

## Versões estáveis atuais — Abril 2026

| Banco | Versão atual | LTS | Observação |
|---|---|---|---|
| **MySQL** | **9.6** (Innovation) / **8.4** (LTS) | 8.4 | Documentação: `dev.mysql.com/doc/refman/8.4/en/` |
| **PostgreSQL** | **18.1** | — | LTS informal (5 anos de suporte) |
| **SQL Server** | **2022** (16.x) | — | Build mais recente: CU17+ |
| **Oracle** | **23ai** (23c) | — | LTS enterprise |
| **MariaDB** | **11.4** (LTS) | 11.4 | Fork do MySQL com recursos próprios |
| **SQLite** | **3.47+** | — | Embutido em aplicações |

## Impacto das versões no ebook

```sql
-- ✅ MySQL 8.4 (LTS atual): todos os recursos do ebook funcionam
-- ✅ PostgreSQL 18: todos os recursos do ebook funcionam + Window Functions avançadas
-- ⚠️ MySQL 5.7 (EOL desde Out/2023): EVITE — sem suporte de segurança

-- Verificando a versão do seu banco:
SELECT VERSION();           -- MySQL, PostgreSQL, MariaDB
SELECT @@VERSION;           -- SQL Server
SELECT * FROM v$version;    -- Oracle
```

## MySQL 8.4 LTS vs MySQL 9.x Innovation

O MySQL agora segue duas trilhas de lançamento:

| Trilha | Versão | Para quem |
|---|---|---|
| **LTS** (Long Term Support) | 8.4 | Produção — suporte garantido por anos |
| **Innovation** | 9.6 | Novidades — atualiza a cada trimestre |

✅ Para produção, sempre prefira a versão LTS. Recursos novos da trilha Innovation chegam ao próximo LTS.

## PostgreSQL 18 — Novidades relevantes

A documentação atual (postgresql.org/docs/current) refere-se ao **PostgreSQL 18**, lançado em novembro de 2025:

- **`GENERATED ALWAYS AS IDENTITY`** — padrão e amplamente recomendado (desde v10)
- **Window Functions** — suporte completo e robusto (desde v8.4)
- **`MERGE`** — inserir/atualizar/deletar em uma única instrução (desde v15)
- **`JSON_TABLE()`** — transformar JSON em linhas relacionais (desde v17)
- **`COPY` otimizado** — importação massiva de dados performática

---

## 📂 Este ebook está completo — Edição 2026

**65 capítulos** cobrindo SQL do zero ao avançado, verificado contra fontes oficiais:

| Módulo | Capítulos | Tópicos |
|---|---|---|
| **Fundamentos** | 1–5 | Introdução, RDBMS, Sintaxe, SELECT, DISTINCT |
| **Filtragem e ordenação** | 6–10 | WHERE, ORDER BY, AND, OR, NOT |
| **Manipulação de dados** | 11–15 | INSERT, Boas práticas, NULL, UPDATE, DELETE |
| **Limitação e agregação** | 16–17 | LIMIT/TOP, MIN/MAX/COUNT/SUM/AVG |
| **Buscas avançadas** | 18–20 | LIKE, Wildcards, IN, BETWEEN |
| **JOINs completo** | 21–27 | Aliases, JOIN, INNER, LEFT, RIGHT, FULL, Self |
| **Operações de conjunto** | 28–34 | UNION, GROUP BY, HAVING, EXISTS, ANY/ALL, SELECT INTO, INSERT SELECT |
| **Lógica e nulos** | 35–36 | CASE, COALESCE/NULL Functions |
| **Programabilidade** | 37 | Stored Procedures |
| **Código e operadores** | 38–39 | Comentários, Operadores completos |
| **DDL — Definição** | 40–44 | CREATE/DROP DB, BACKUP, CREATE/DROP TABLE, ALTER TABLE |
| **Constraints** | 45–52 | NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, CHECK, DEFAULT, INDEX |
| **IDs e datas** | 53–54 | AUTO INCREMENT, Working with Dates |
| **Views e segurança** | 55–58 | Views, SQL Injection, Parameterized Queries, Prepared Statements |
| **Infraestrutura** | 59 | Escolhendo o banco de dados |
| **Avançado** | 60–65 | Ordem de execução, Subqueries, INTERSECT/EXCEPT, Window Functions, Transactions, Versões 2026 |
| **SQL Moderno** | 66 | CTEs — Common Table Expressions |

---

**📄 Fontes utilizadas na construção e verificação deste ebook:**

- **SQLBolt** — sqlbolt.com (Lições 1–18, Subqueries, Set Operations)
- **SQLZoo** — sqlzoo.net (SQL Tutorial interativo)
- **MySQL 8.4 Reference Manual** — dev.mysql.com/doc/refman/8.4/en/
- **PostgreSQL 18 Documentation** — postgresql.org/docs/current/
- **Percona Blog** — percona.com/blog
- **CYBERTEC PostgreSQL** — cybertec-postgresql.com

---

*📄 SQL — Do Zero ao Profissional · Edição 2026*
*Ebook RAG · Explicações em pt-BR · Código em inglês (US)*
*66 capítulos · Verificado contra fontes oficiais em Abril/2026*
*Compatível com MySQL 8.4/9.6 · PostgreSQL 18 · SQL Server 2022 · Oracle 23ai · SQLite*

---

# 66. CTEs — Common Table Expressions

## Por que CTEs existem?

Antes de aprender a sintaxe, é fundamental entender o problema que as CTEs resolvem — porque quando você entender o problema, a solução vai fazer sentido imediato.

Imagine que você precisa responder a seguinte pergunta de negócio:

> *"Quais vendedores tiveram receita acima da média do time deles em 2024, e qual foi o percentual de cada um acima da média?"*

Sem CTEs, você precisaria de subqueries aninhadas — uma dentro da outra — que ficam cada vez mais difíceis de ler, debugar e manter:

```sql
-- ❌ SEM CTE: subqueries aninhadas — difícil de ler, impossível de reutilizar
SELECT
    s.salesperson_name,
    s.team,
    s.total_revenue,
    team_avg.avg_revenue,
    ROUND((s.total_revenue - team_avg.avg_revenue) / team_avg.avg_revenue * 100, 2)
        AS pct_above_avg
FROM
    (SELECT salesperson_id, salesperson_name, team, SUM(amount) AS total_revenue
     FROM sales
     WHERE YEAR(sale_date) = 2024
     GROUP BY salesperson_id, salesperson_name, team) AS s
INNER JOIN
    (SELECT team, AVG(total) AS avg_revenue
     FROM
         (SELECT team, SUM(amount) AS total
          FROM sales
          WHERE YEAR(sale_date) = 2024
          GROUP BY team, salesperson_id) AS team_totals
     GROUP BY team) AS team_avg
ON s.team = team_avg.team
WHERE s.total_revenue > team_avg.avg_revenue
ORDER BY pct_above_avg DESC;
```

Agora compare com a versão usando CTEs:

```sql
-- ✅ COM CTE: cada etapa tem nome e propósito claro
WITH
-- Etapa 1: calcular o total de vendas de cada vendedor em 2024
salesperson_revenue AS (
    SELECT
        salesperson_id,
        salesperson_name,
        team,
        SUM(amount) AS total_revenue
    FROM sales
    WHERE YEAR(sale_date) = 2024
    GROUP BY salesperson_id, salesperson_name, team
),

-- Etapa 2: calcular a média por time (usando a CTE anterior)
team_averages AS (
    SELECT
        team,
        AVG(total_revenue) AS avg_revenue
    FROM salesperson_revenue
    GROUP BY team
)

-- Consulta final: comparar cada vendedor com a média do seu time
SELECT
    sr.salesperson_name,
    sr.team,
    sr.total_revenue,
    ta.avg_revenue,
    ROUND((sr.total_revenue - ta.avg_revenue) / ta.avg_revenue * 100, 2)
        AS pct_above_avg
FROM salesperson_revenue AS sr
INNER JOIN team_averages AS ta ON sr.team = ta.team
WHERE sr.total_revenue > ta.avg_revenue
ORDER BY pct_above_avg DESC;
```

O resultado é idêntico. A legibilidade é completamente diferente.

---

## O que é uma CTE?

Uma **CTE** (Common Table Expression — Expressão de Tabela Comum) é um resultado temporário nomeado que você define com a cláusula `WITH` antes da query principal. Ela funciona como uma tabela virtual que:

- **Existe apenas durante a execução** da query — não persiste no banco
- **Tem um nome** — pode ser referenciada como qualquer tabela
- **Pode ser reutilizada** — referenciada múltiplas vezes na mesma query
- **Pode referenciar outras CTEs** — você pode encadear várias
- **Pode ser recursiva** — referenciar a si mesma (veremos adiante)

### Suporte por banco de dados

| Banco | Suporte a CTE | Desde |
|---|---|---|
| PostgreSQL | ✅ Completo (incluindo recursivo) | v8.4 (2009) |
| SQL Server | ✅ Completo | SQL Server 2005 |
| Oracle | ✅ Completo | Oracle 9i |
| MySQL | ✅ Completo | MySQL 8.0 (2018) |
| MariaDB | ✅ Completo | MariaDB 10.2 |
| SQLite | ✅ Completo | SQLite 3.8.3 |

⚠️ **MySQL 5.7 e anteriores não suportam CTEs**. Se você ainda usa MySQL 5.7 (que chegou ao EOL em outubro de 2023), precisa usar subqueries no `FROM`.

---

## Sintaxe completa

```sql
-- CTE simples — uma única expressão nomeada
WITH cte_name AS (
    SELECT column1, column2
    FROM table_name
    WHERE condition
)
SELECT *
FROM cte_name
WHERE another_condition;


-- Múltiplas CTEs — separadas por vírgula, sem WITH repetido
WITH
    first_cte AS (
        SELECT ...
        FROM table_a
    ),

    second_cte AS (
        SELECT ...
        FROM table_b
        JOIN first_cte ON ...    -- pode referenciar CTEs anteriores
    ),

    third_cte AS (
        SELECT ...
        FROM second_cte          -- encadeamento
    )

-- A query principal vem aqui, após as CTEs
SELECT *
FROM third_cte
WHERE condition
ORDER BY column;
```

**Regras fundamentais:**
- A palavra `WITH` aparece apenas **uma vez**, antes da primeira CTE
- Múltiplas CTEs são separadas por **vírgula** `,`
- Cada CTE posterior pode referenciar as anteriores
- A query final (após as CTEs) **não** termina com vírgula
- CTEs podem ser usadas em `SELECT`, `INSERT`, `UPDATE` e `DELETE`

---

## Caso de uso 1 — Quebrando lógica complexa em etapas

### Problema real: relatório financeiro de e-commerce

Você precisa gerar um relatório que mostre, para cada cliente:
- Total de pedidos
- Valor total gasto
- Valor médio por pedido
- Classificação do cliente (VIP, Regular, Novo)

```sql
WITH
-- Etapa 1: agregar dados brutos de pedidos por cliente
customer_orders AS (
    SELECT
        c.customer_id,
        c.customer_name,
        c.customer_email,
        c.registration_date,
        COUNT(o.order_id)          AS total_orders,
        SUM(o.order_total)         AS total_spent,
        AVG(o.order_total)         AS avg_order_value,
        MAX(o.order_date)          AS last_order_date
    FROM customers AS c
    LEFT JOIN orders AS o ON c.customer_id = o.customer_id
    WHERE o.order_date >= '2024-01-01'
       OR o.order_date IS NULL
    GROUP BY c.customer_id, c.customer_name, c.customer_email, c.registration_date
),

-- Etapa 2: calcular os percentis globais para categorização
spending_thresholds AS (
    SELECT
        PERCENTILE_CONT(0.75) WITHIN GROUP (ORDER BY total_spent) AS p75_threshold,
        PERCENTILE_CONT(0.25) WITHIN GROUP (ORDER BY total_spent) AS p25_threshold
    FROM customer_orders
    WHERE total_orders > 0
),

-- Etapa 3: classificar cada cliente com base nos percentis
customer_segments AS (
    SELECT
        co.customer_id,
        co.customer_name,
        co.customer_email,
        co.total_orders,
        co.total_spent,
        ROUND(co.avg_order_value, 2)   AS avg_order_value,
        co.last_order_date,
        CASE
            WHEN co.total_orders = 0
                THEN 'Nunca comprou'
            WHEN co.total_spent >= st.p75_threshold
                THEN 'VIP'
            WHEN co.total_spent >= st.p25_threshold
                THEN 'Regular'
            ELSE
                'Novo'
        END AS customer_segment
    FROM customer_orders AS co
    CROSS JOIN spending_thresholds AS st
)

-- Resultado final: relatório completo com contagem por segmento
SELECT
    customer_segment,
    COUNT(*)                       AS customer_count,
    ROUND(AVG(total_spent), 2)     AS avg_spending,
    ROUND(SUM(total_spent), 2)     AS total_revenue,
    ROUND(AVG(total_orders), 1)    AS avg_orders_per_customer
FROM customer_segments
GROUP BY customer_segment
ORDER BY total_revenue DESC;
```

📄 Resultado esperado:

| customer_segment | customer_count | avg_spending | total_revenue | avg_orders_per_customer |
|---|---|---|---|---|
| VIP | 23 | 4580.00 | 105340.00 | 12.4 |
| Regular | 68 | 890.00 | 60520.00 | 4.1 |
| Novo | 41 | 145.00 | 5945.00 | 1.2 |
| Nunca comprou | 17 | 0.00 | 0.00 | 0.0 |

**Por que CTE aqui e não subquery?** Porque `spending_thresholds` é referenciada em `customer_segments`, e `customer_segments` é referenciada na query final. Com subqueries aninhadas, você precisaria repetir o mesmo código ou criar tabelas temporárias.

---

## Caso de uso 2 — Reutilizando o mesmo cálculo sem repetição

### Problema real: comparação de receita mês a mês

```sql
-- ❌ SEM CTE: a mesma subquery repetida duas vezes (manutenção cara)
SELECT
    current_month.month,
    current_month.revenue,
    previous_month.revenue AS previous_revenue,
    current_month.revenue - previous_month.revenue AS revenue_change
FROM
    (SELECT DATE_FORMAT(sale_date, '%Y-%m') AS month, SUM(amount) AS revenue
     FROM sales GROUP BY month) AS current_month
LEFT JOIN
    (SELECT DATE_FORMAT(sale_date, '%Y-%m') AS month, SUM(amount) AS revenue
     FROM sales GROUP BY month) AS previous_month  -- ← idêntica à anterior!
ON current_month.month = DATE_FORMAT(
       DATE_SUB(STR_TO_DATE(CONCAT(previous_month.month, '-01'), '%Y-%m-%d'),
       INTERVAL -1 MONTH), '%Y-%m');
-- Impossível de ler e manter

-- ✅ COM CTE: define uma vez, usa duas vezes
WITH monthly_revenue AS (
    SELECT
        DATE_FORMAT(sale_date, '%Y-%m') AS revenue_month,
        SUM(amount)                      AS revenue
    FROM sales
    GROUP BY revenue_month
)

SELECT
    current_month.revenue_month,
    current_month.revenue,
    previous_month.revenue                               AS previous_revenue,
    current_month.revenue - previous_month.revenue       AS revenue_change,
    ROUND(
        (current_month.revenue - previous_month.revenue)
        / previous_month.revenue * 100, 1
    )                                                    AS pct_change
FROM monthly_revenue AS current_month
LEFT JOIN monthly_revenue AS previous_month   -- mesma CTE, alias diferente
    ON current_month.revenue_month = DATE_FORMAT(
           DATE_ADD(
               STR_TO_DATE(CONCAT(previous_month.revenue_month, '-01'), '%Y-%m-%d'),
               INTERVAL 1 MONTH
           ), '%Y-%m')
ORDER BY current_month.revenue_month;
```

📄 Resultado:

| revenue_month | revenue | previous_revenue | revenue_change | pct_change |
|---|---|---|---|---|
| 2024-01 | 48500.00 | NULL | NULL | NULL |
| 2024-02 | 52300.00 | 48500.00 | 3800.00 | 7.8 |
| 2024-03 | 61200.00 | 52300.00 | 8900.00 | 17.0 |
| 2024-04 | 55400.00 | 61200.00 | -5800.00 | -9.5 |

**Vantagem chave:** `monthly_revenue` foi definida apenas uma vez. Se você precisar ajustar o período ou adicionar um filtro, muda em um único lugar.

---

## Caso de uso 3 — CTEs em UPDATE e DELETE

CTEs não servem apenas para `SELECT` — elas funcionam com `INSERT`, `UPDATE` e `DELETE`, tornando operações complexas de manipulação de dados muito mais legíveis.

### Atualizando com lógica derivada de múltiplos passos

```sql
-- Problema: atualizar o status dos clientes com base no comportamento de compra
WITH
-- Identifica clientes inativos: sem pedidos nos últimos 12 meses
inactive_customers AS (
    SELECT c.customer_id
    FROM customers AS c
    LEFT JOIN orders AS o
        ON c.customer_id = o.customer_id
        AND o.order_date >= DATE_SUB(CURDATE(), INTERVAL 12 MONTH)
    WHERE o.order_id IS NULL
      AND c.status = 'active'     -- apenas os que ainda estão como 'active'
),

-- Identifica clientes VIP: mais de 10 pedidos nos últimos 12 meses
vip_candidates AS (
    SELECT customer_id
    FROM orders
    WHERE order_date >= DATE_SUB(CURDATE(), INTERVAL 12 MONTH)
    GROUP BY customer_id
    HAVING COUNT(*) > 10
)

-- MySQL: UPDATE via JOIN com CTE (usando subquery equivalente)
UPDATE customers
SET status = 'inactive'
WHERE customer_id IN (SELECT customer_id FROM inactive_customers);
```

```sql
-- PostgreSQL: UPDATE direto com CTE (sintaxe mais elegante)
WITH inactive_customers AS (
    SELECT c.customer_id
    FROM customers AS c
    LEFT JOIN orders AS o
        ON c.customer_id = o.customer_id
        AND o.order_date >= NOW() - INTERVAL '12 months'
    WHERE o.order_id IS NULL
      AND c.status = 'active'
)
UPDATE customers
SET status     = 'inactive',
    updated_at = NOW()
WHERE customer_id IN (SELECT customer_id FROM inactive_customers);
```

### Deletando com lógica encadeada

```sql
-- Deletar logs antigos de usuários que já foram removidos do sistema
-- PostgreSQL
WITH
deleted_users AS (
    SELECT user_id FROM users WHERE deleted_at < NOW() - INTERVAL '1 year'
),
orphan_logs AS (
    SELECT log_id
    FROM activity_logs AS al
    INNER JOIN deleted_users AS du ON al.user_id = du.user_id
)
DELETE FROM activity_logs
WHERE log_id IN (SELECT log_id FROM orphan_logs);
```

---

## Caso de uso 4 — CTEs Recursivas

Esta é a funcionalidade mais poderosa e única das CTEs. Uma **CTE recursiva** referencia a si mesma, permitindo processar estruturas hierárquicas — como organogramas, menus de navegação em árvore, categorias aninhadas, ou qualquer dado que tenha relacionamento pai-filho.

### Como uma CTE recursiva funciona

```sql
WITH RECURSIVE cte_name AS (
    -- Parte 1: ÂNCORA (anchor member)
    -- Define o ponto de partida da recursão — executada uma única vez
    SELECT ...
    FROM table
    WHERE id = 1   -- começa na raiz

    UNION ALL      -- sempre UNION ALL, nunca UNION

    -- Parte 2: RECURSIVA (recursive member)
    -- Referencia a própria CTE — executada repetidamente até não haver mais linhas
    SELECT ...
    FROM table
    INNER JOIN cte_name ON table.parent_id = cte_name.id
)
SELECT * FROM cte_name;
```

**Como o banco processa:**
1. Executa a âncora → gera o conjunto inicial de linhas
2. Executa a parte recursiva usando o resultado anterior
3. Junta o resultado com `UNION ALL`
4. Repete o passo 2 com as novas linhas
5. Para quando a parte recursiva não retorna nenhuma linha nova

### Problema real: organograma de empresa

```sql
-- Tabela de funcionários com hierarquia (manager_id → employee_id)
-- employee_id | employee_name | manager_id | department | salary
-- 1           | Ana Costa     | NULL       | Diretoria  | 25000   ← CEO
-- 2           | Bruno Lima    | 1          | TI         | 15000   ← reporta à Ana
-- 3           | Carla Silva   | 1          | Vendas     | 14000   ← reporta à Ana
-- 4           | Diego Alves   | 2          | TI         | 10000   ← reporta ao Bruno
-- 5           | Eva Santos    | 2          | TI         | 11000   ← reporta ao Bruno
-- 6           | Fábio Rocha   | 3          | Vendas     |  9000   ← reporta à Carla

WITH RECURSIVE org_chart AS (

    -- ÂNCORA: começa pelo CEO (sem gerente)
    SELECT
        employee_id,
        employee_name,
        manager_id,
        department,
        salary,
        0                          AS hierarchy_level,    -- nível 0 = topo
        employee_name              AS reporting_chain      -- caminho hierárquico
    FROM employees
    WHERE manager_id IS NULL       -- condição de parada: sem gerente = raiz

    UNION ALL

    -- RECURSIVA: busca funcionários que reportam ao nível anterior
    SELECT
        e.employee_id,
        e.employee_name,
        e.manager_id,
        e.department,
        e.salary,
        oc.hierarchy_level + 1,                          -- incrementa o nível
        oc.reporting_chain || ' → ' || e.employee_name   -- acumula o caminho
    FROM employees AS e
    INNER JOIN org_chart AS oc ON e.manager_id = oc.employee_id
)

SELECT
    REPEAT('  ', hierarchy_level) || employee_name    AS name_indented,
    department,
    salary,
    hierarchy_level,
    reporting_chain
FROM org_chart
ORDER BY reporting_chain;
```

📄 Resultado:

| name_indented | department | salary | hierarchy_level | reporting_chain |
|---|---|---|---|---|
| Ana Costa | Diretoria | 25000 | 0 | Ana Costa |
|   Bruno Lima | TI | 15000 | 1 | Ana Costa → Bruno Lima |
|     Diego Alves | TI | 10000 | 2 | Ana Costa → Bruno Lima → Diego Alves |
|     Eva Santos | TI | 11000 | 2 | Ana Costa → Bruno Lima → Eva Santos |
|   Carla Silva | Vendas | 14000 | 1 | Ana Costa → Carla Silva |
|     Fábio Rocha | Vendas | 9000 | 2 | Ana Costa → Carla Silva → Fábio Rocha |

### Problema real: categorias aninhadas de e-commerce

```sql
-- Tabela: categories (category_id, category_name, parent_id)
-- Exemplo: Eletrônicos → Computadores → Notebooks → Ultrabooks

WITH RECURSIVE category_tree AS (
    -- ÂNCORA: categorias raiz (sem pai)
    SELECT
        category_id,
        category_name,
        parent_id,
        category_name              AS full_path,
        1                          AS depth
    FROM categories
    WHERE parent_id IS NULL

    UNION ALL

    -- RECURSIVA: filhas de cada categoria
    SELECT
        c.category_id,
        c.category_name,
        c.parent_id,
        ct.full_path || ' > ' || c.category_name   AS full_path,
        ct.depth + 1                                 AS depth
    FROM categories AS c
    INNER JOIN category_tree AS ct ON c.parent_id = ct.category_id
)

SELECT
    full_path,
    depth,
    -- Conta quantos produtos existem em cada categoria
    (SELECT COUNT(*) FROM products p WHERE p.category_id = category_tree.category_id)
        AS product_count
FROM category_tree
ORDER BY full_path;
```

📄 Resultado:

| full_path | depth | product_count |
|---|---|---|
| Eletrônicos | 1 | 0 |
| Eletrônicos > Computadores | 2 | 0 |
| Eletrônicos > Computadores > Notebooks | 3 | 45 |
| Eletrônicos > Computadores > Notebooks > Ultrabooks | 4 | 12 |
| Eletrônicos > Smartphones | 2 | 128 |

### Cuidado: loop infinito em CTEs recursivas

Se os dados tiverem referências circulares (ex: A é pai de B, e B é pai de A), a CTE recursiva entrará em loop infinito. Use `MAXRECURSION` ou `LIMIT` para se proteger:

```sql
-- SQL Server: limitar a profundidade máxima
WITH RECURSIVE org_chart AS (...)
SELECT * FROM org_chart
OPTION (MAXRECURSION 100);   -- SQL Server: para após 100 níveis

-- MySQL / PostgreSQL: usar LIMIT na query final
WITH RECURSIVE org_chart AS (...)
SELECT * FROM org_chart
LIMIT 10000;   -- proteção contra loops muito longos

-- PostgreSQL: adicionar condição anti-loop explícita
WITH RECURSIVE safe_tree AS (
    SELECT id, parent_id, ARRAY[id] AS visited_ids   -- rastreia IDs visitados
    FROM categories WHERE parent_id IS NULL

    UNION ALL

    SELECT c.id, c.parent_id, st.visited_ids || c.id
    FROM categories AS c
    INNER JOIN safe_tree AS st ON c.parent_id = st.id
    WHERE NOT c.id = ANY(st.visited_ids)   -- impede revisitar nós já visitados
)
SELECT * FROM safe_tree;
```

---

## CTEs vs Alternativas — Quando usar o quê

Esta é a decisão mais importante: CTEs não são sempre a melhor escolha. Entender quando cada abordagem brilha é o que diferencia um SQL competente de um SQL excelente.

### CTEs vs Subqueries no FROM

```sql
-- SUBQUERY NO FROM: válida para uso único e simples
SELECT department, avg_salary
FROM (
    SELECT department, AVG(salary) AS avg_salary
    FROM employees
    GROUP BY department
) AS dept_avg
WHERE avg_salary > 8000;

-- CTE: preferível quando o resultado é reutilizado ou a lógica é complexa
WITH dept_avg AS (
    SELECT department, AVG(salary) AS avg_salary
    FROM employees
    GROUP BY department
)
SELECT department, avg_salary
FROM dept_avg
WHERE avg_salary > 8000;
```

| Critério | Subquery no FROM | CTE |
|---|---|---|
| Uso único e simples | ✅ Mais conciso | ⚠️ Mais verboso |
| Reutilização | ❌ Deve repetir o código | ✅ Define uma vez |
| Legibilidade em lógica complexa | ❌ Difícil de ler | ✅ Clara e nomeada |
| Hierarchia/recursão | ❌ Impossível | ✅ Suportado |
| Compatibilidade antiga (MySQL 5.7) | ✅ Funciona | ❌ Não suportado |

### CTEs vs Views

```sql
-- VIEW: armazenada no banco, disponível para qualquer query e usuário
CREATE VIEW active_customers AS
SELECT customer_id, customer_name, email
FROM customers
WHERE status = 'active';

-- Pode ser usada por qualquer pessoa, a qualquer momento
SELECT * FROM active_customers WHERE country = 'Brazil';


-- CTE: temporária, existe apenas durante a query atual
WITH active_customers AS (
    SELECT customer_id, customer_name, email
    FROM customers
    WHERE status = 'active'
)
SELECT * FROM active_customers WHERE country = 'Brazil';
```

| Critério | CTE | View |
|---|---|---|
| Persistência | ❌ Temporária (só dura a query) | ✅ Permanente no banco |
| Compartilhamento entre usuários | ❌ Apenas no contexto atual | ✅ Qualquer usuário pode usar |
| Manutenção centralizada | ❌ Cada query tem a própria | ✅ Um lugar para atualizar |
| Lógica específica de uma query | ✅ Ideal | ❌ Polui o namespace |
| Recursividade | ✅ Suportado | ❌ Views não suportam recursão |
| Sem necessidade de DDL (CREATE) | ✅ Não precisa de permissão | ❌ Requer permissão de CREATE VIEW |

**Regra prática:** Se a mesma lógica é usada em múltiplas queries ou por múltiplos usuários → **View**. Se é específica de uma query → **CTE**.

### CTEs vs Tabelas Temporárias

```sql
-- TABELA TEMPORÁRIA: existe na sessão inteira, pode ter índices
CREATE TEMPORARY TABLE temp_customer_stats AS
SELECT customer_id, COUNT(*) AS orders, SUM(total) AS revenue
FROM orders
GROUP BY customer_id;

CREATE INDEX idx_temp_customer ON temp_customer_stats (customer_id);

SELECT c.customer_name, t.orders, t.revenue
FROM customers AS c
INNER JOIN temp_customer_stats AS t ON c.customer_id = t.customer_id;

DROP TEMPORARY TABLE temp_customer_stats;


-- CTE: sem persistência, sem índices, descartada automaticamente
WITH customer_stats AS (
    SELECT customer_id, COUNT(*) AS orders, SUM(total) AS revenue
    FROM orders
    GROUP BY customer_id
)
SELECT c.customer_name, cs.orders, cs.revenue
FROM customers AS c
INNER JOIN customer_stats AS cs ON c.customer_id = cs.customer_id;
```

| Critério | CTE | Tabela Temporária |
|---|---|---|
| Código necessário | ✅ Simples | ❌ CREATE + DROP |
| Disponível na sessão inteira | ❌ Apenas na query | ✅ Sim |
| Pode ter índices | ❌ Não | ✅ Sim |
| Performance em grande volume | ⚠️ Recalculada a cada referência* | ✅ Materializada em disco |
| Limpeza automática | ✅ Automática | ❌ Precisa de DROP |

*⚠️ **Nota importante sobre performance:** Na maioria dos bancos (MySQL, SQL Server, Oracle), uma CTE pode ser recalculada toda vez que é referenciada. No PostgreSQL 12+, CTEs não-recursivas são otimizadas pelo planner e geralmente calculadas apenas uma vez. Para grandes volumes de dados com múltiplas referências, tabelas temporárias ou `MATERIALIZED` (PostgreSQL) podem ser mais eficientes.

```sql
-- PostgreSQL 12+: forçar materialização de uma CTE cara
WITH MATERIALIZED expensive_cte AS (
    SELECT ...    -- cálculo pesado que não deve ser repetido
    FROM big_table
)
SELECT * FROM expensive_cte AS e1
JOIN expensive_cte AS e2 ON ...;   -- usa o resultado já calculado

-- PostgreSQL: forçar re-execução (quando o otimizador tomaria decisão errada)
WITH NOT MATERIALIZED inline_cte AS (
    SELECT ...
)
SELECT * FROM inline_cte;
```

---

## Boas práticas com CTEs

### ✅ Nomeie as CTEs de forma descritiva

```sql
-- ❌ Nomes genéricos não comunicam a intenção
WITH a AS (...), b AS (...), c AS (...)

-- ✅ Nomes que descrevem o que o dado representa
WITH
    active_orders_2024 AS (...),
    customer_spending_totals AS (...),
    vip_threshold AS (...)
```

### ✅ Adicione comentários explicando a finalidade de cada CTE

```sql
WITH
    -- Filtra apenas pedidos entregues no Q4 de 2024
    q4_delivered_orders AS (
        SELECT order_id, customer_id, total_amount, delivery_date
        FROM orders
        WHERE delivery_date BETWEEN '2024-10-01' AND '2024-12-31'
          AND status = 'delivered'
    ),

    -- Agrega o total gasto por cliente no período
    customer_q4_spending AS (
        SELECT customer_id, SUM(total_amount) AS q4_total
        FROM q4_delivered_orders    -- referencia a CTE anterior
        GROUP BY customer_id
    )

SELECT ...
```

### ✅ Mantenha cada CTE focada em uma única responsabilidade

```sql
-- ❌ CTE fazendo tudo de uma vez — difícil de testar e debugar
WITH everything AS (
    SELECT c.customer_name, COUNT(o.order_id) AS orders,
           SUM(o.total) AS revenue, AVG(o.total) AS avg,
           MAX(o.order_date) AS last_order,
           CASE WHEN SUM(o.total) > 5000 THEN 'VIP' ELSE 'Regular' END AS segment
    FROM customers c LEFT JOIN orders o ON c.customer_id = o.customer_id
    GROUP BY c.customer_id, c.customer_name
)

-- ✅ Cada CTE com responsabilidade única — fácil de testar individualmente
WITH
    order_metrics AS (   -- responsabilidade: agregar métricas de pedido
        SELECT customer_id, COUNT(*) AS orders, SUM(total) AS revenue,
               AVG(total) AS avg_value, MAX(order_date) AS last_order
        FROM orders
        GROUP BY customer_id
    ),
    customer_segments AS (   -- responsabilidade: classificar clientes
        SELECT customer_id,
               CASE WHEN revenue > 5000 THEN 'VIP' ELSE 'Regular' END AS segment
        FROM order_metrics
    )
-- query final: juntar tudo
SELECT c.customer_name, om.orders, om.revenue, cs.segment
FROM customers AS c
LEFT JOIN order_metrics AS om ON c.customer_id = om.customer_id
LEFT JOIN customer_segments AS cs ON c.customer_id = cs.customer_id;
```

### ✅ Use CTEs para debugar queries complexas — teste cada etapa individualmente

```sql
-- Durante o desenvolvimento: comente a query final e teste cada CTE sozinha
WITH
    step_1_raw_data AS (
        SELECT customer_id, order_date, total
        FROM orders
        WHERE order_date >= '2024-01-01'
    )
-- Teste: SELECT * FROM step_1_raw_data LIMIT 10;
-- Quando estiver correto, adicione a próxima CTE

    -- ,step_2_aggregated AS (...)
    -- ,step_3_classified AS (...)
SELECT * FROM step_1_raw_data LIMIT 10;   -- ← substitua quando avançar
```

### ❌ Evite CTEs quando uma query simples resolve

```sql
-- ❌ CTE desnecessária: a subquery é simples o suficiente
WITH recent_orders AS (
    SELECT * FROM orders WHERE order_date >= '2024-01-01'
)
SELECT * FROM recent_orders;

-- ✅ Use direto — mais limpo e não há benefício na CTE aqui
SELECT * FROM orders WHERE order_date >= '2024-01-01';
```

---

## Resumo — CTEs em uma página

```sql
-- ESTRUTURA BÁSICA
WITH cte_name AS (
    SELECT ... FROM ... WHERE ...
)
SELECT * FROM cte_name;

-- MÚLTIPLAS CTEs
WITH
    cte_a AS (SELECT ...),
    cte_b AS (SELECT ... FROM cte_a ...)   -- pode referenciar a anterior
SELECT * FROM cte_b;

-- CTE RECURSIVA (estruturas hierárquicas)
WITH RECURSIVE tree AS (
    SELECT id, parent_id, name, 1 AS depth FROM table WHERE parent_id IS NULL  -- âncora
    UNION ALL
    SELECT t.id, t.parent_id, t.name, tr.depth + 1
    FROM table AS t INNER JOIN tree AS tr ON t.parent_id = tr.id               -- recursão
)
SELECT * FROM tree;

-- CTE EM UPDATE (PostgreSQL)
WITH targets AS (SELECT id FROM table WHERE condition)
UPDATE table SET col = value WHERE id IN (SELECT id FROM targets);

-- CTE MATERIALIZADA (PostgreSQL 12+ — força cálculo único)
WITH MATERIALIZED expensive AS (SELECT ... FROM big_table)
SELECT * FROM expensive AS e1 JOIN expensive AS e2 ON ...;
```

| Situação | Melhor escolha |
|---|---|
| Lógica usada apenas nesta query | ✅ CTE |
| Mesma lógica em várias queries | ✅ View |
| Grande volume com múltiplas referências | ✅ Tabela temporária |
| Estrutura hierárquica (árvore) | ✅ CTE recursiva |
| Query simples e de uso único | ✅ Subquery inline |
| Compartilhada entre usuários/times | ✅ View |

---

*📄 SQL — Do Zero ao Profissional · Edição 2026*
*Ebook RAG · Explicações em pt-BR · Código em inglês (US)*
*66 capítulos · Verificado contra fontes oficiais em Abril/2026*
*Compatível com MySQL 8.4/9.6 · PostgreSQL 18 · SQL Server 2022 · Oracle 23ai · SQLite*

---

# 67. Funções de String — Manipulando texto

## Por que funções de string são essenciais?

Dados do mundo real raramente chegam limpos. Nomes com espaços extras, e-mails em maiúsculas misturadas, CPFs com e sem formatação — funções de string transformam dados brutos em dados utilizáveis **direto no banco**, sem precisar de código na aplicação.

---

## CONCAT — Concatenando texto

```sql
-- MySQL / padrão SQL
SELECT CONCAT('São Paulo', ', ', 'SP');              -- 'São Paulo, SP'

-- CONCAT_WS (With Separator): separador automático, ignora NULLs
SELECT CONCAT_WS(', ', 'São Paulo', NULL, 'Brasil'); -- 'São Paulo, Brasil'

-- PostgreSQL / Oracle: operador ||
SELECT 'Hello' || ' ' || 'World';

-- SQL Server: operador +
SELECT 'Hello' + ' ' + 'World';
```

⚠️ **Armadilha:** `CONCAT('texto', NULL)` retorna `NULL` no MySQL e SQL Server. Use `CONCAT_WS` ou `COALESCE` para proteção.

### Caso de uso real — Endereço completo e mascaramento de cartão

```sql
SELECT
    customer_name,
    -- CONCAT_WS ignora NULLs automaticamente
    CONCAT_WS(', ', street, number, neighborhood, city, state, postal_code)
        AS full_address,
    -- Máscara de cartão: exibe apenas os 4 últimos dígitos
    CONCAT(REPEAT('*', CHAR_LENGTH(card_number) - 4), RIGHT(card_number, 4))
        AS masked_card
FROM customers
WHERE status = 'active';
```

---

## UPPER e LOWER — Padronizando capitalização

```sql
SELECT UPPER('são paulo');      -- 'SÃO PAULO'
SELECT LOWER('ANA@GMAIL.COM'); -- 'ana@gmail.com'
```

### Caso de uso real — Normalizando e-mails

```sql
-- Armazenar e-mails sempre em minúsculas
INSERT INTO users (email, name)
VALUES (LOWER('Ana@Gmail.COM'), 'Ana Costa');

-- Busca case-insensitive
SELECT * FROM users
WHERE LOWER(email) = LOWER('ANA@GMAIL.COM');
```

⚠️ **Performance:** `LOWER(coluna)` no `WHERE` impede uso de índice. Configure a collation da coluna (`utf8mb4_unicode_ci` no MySQL) para buscas case-insensitive com índice.

---

## TRIM — Removendo espaços e caracteres

```sql
SELECT TRIM('  olá mundo  ');            -- 'olá mundo'
SELECT LTRIM('  olá mundo  ');           -- 'olá mundo  '
SELECT RTRIM('  olá mundo  ');           -- '  olá mundo'
SELECT TRIM(LEADING '0' FROM '00123');   -- '123'
SELECT TRIM(BOTH '*' FROM '***SQL***');  -- 'SQL'
```

### Caso de uso real — Limpeza de dados importados de CSV

```sql
UPDATE imported_customers
SET
    customer_name = TRIM(customer_name),
    email         = TRIM(LOWER(email)),   -- limpa E padroniza em uma operação
    postal_code   = TRIM(postal_code)
WHERE import_batch_id = 2026;

-- Diagnóstico: quantos registros estão sujos
SELECT COUNT(*) AS dirty_records
FROM imported_customers
WHERE customer_name != TRIM(customer_name)
   OR email != TRIM(LOWER(email));
```

---

## LENGTH e CHAR_LENGTH — Contando caracteres

```sql
SELECT CHAR_LENGTH('ção');   -- 3 (MySQL: conta caracteres Unicode)
SELECT LENGTH('ção');        -- 5 (MySQL: conta bytes UTF-8)
-- Para texto com acentos no MySQL, use CHAR_LENGTH
```

### Caso de uso real — Validação de formato

```sql
SELECT
    customer_id,
    phone,
    CASE
        WHEN phone IS NULL              THEN 'Vazio'
        WHEN CHAR_LENGTH(phone) < 10   THEN 'Curto demais'
        WHEN CHAR_LENGTH(phone) > 15   THEN 'Longo demais'
        ELSE                                'Valido'
    END AS phone_status
FROM customers;

-- Produtos com codigo incorreto (deve ter exatamente 8 caracteres)
SELECT * FROM products
WHERE CHAR_LENGTH(product_code) != 8;
```

---

## SUBSTRING — Extraindo partes de texto

```sql
-- Posição começa em 1, nao em 0
SELECT SUBSTRING('Brasil 2026', 1, 6);  -- 'Brasil'
SELECT SUBSTRING('Brasil 2026', 8);     -- '2026' (ate o fim)
SELECT LEFT('Brasil 2026', 6);          -- 'Brasil'
SELECT RIGHT('Brasil 2026', 4);         -- '2026'
```

### Caso de uso real — Parsing de códigos estruturados

```sql
-- Codigo: 'ELE-NB-2024-00123' (categoria-subcategoria-ano-sequencial)
SELECT
    product_code,
    LEFT(product_code, 3)                     AS category,     -- 'ELE'
    SUBSTRING(product_code, 5, 2)             AS subcategory,  -- 'NB'
    SUBSTRING(product_code, 8, 4)             AS prod_year,    -- '2024'
    RIGHT(product_code, 5)                    AS sequence,     -- '00123'
    -- Extraindo dominio do e-mail
    SUBSTRING(email, LOCATE('@', email) + 1)  AS email_domain  -- 'gmail.com'
FROM products
LEFT JOIN users ON products.owner_id = users.user_id
LIMIT 10;
```

---

## REPLACE — Substituindo texto

```sql
SELECT REPLACE('aaa bbb aaa', 'aaa', 'xxx');   -- 'xxx bbb xxx'
SELECT REPLACE('R$ 1.500,00', 'R$ ', '');       -- '1.500,00'
```

### Caso de uso real — Limpeza de telefones e migração de URLs

```sql
-- Removendo formatacao de telefones (so digitos)
UPDATE contacts
SET phone = REPLACE(REPLACE(REPLACE(REPLACE(phone, '(', ''), ')', ''), '-', ''), ' ', '')
WHERE phone REGEXP '[^0-9]';
-- '(11) 9 9999-8888' -> '11999998888'

-- Migracao de dominio em massa
UPDATE articles
SET content = REPLACE(content, 'http://old.domain.com', 'https://new.domain.com')
WHERE content LIKE '%http://old.domain.com%';
```

---

## Tabela de referência — Funções de string por banco

| Função | MySQL | PostgreSQL | SQL Server | Oracle |
|---|---|---|---|---|
| Concatenar | `CONCAT()` / `CONCAT_WS()` | `||` / `CONCAT()` | `+` / `CONCAT()` | `||` / `CONCAT()` |
| Maiúsculas/minúsculas | `UPPER()` / `LOWER()` | `UPPER()` / `LOWER()` | `UPPER()` / `LOWER()` | `UPPER()` / `LOWER()` |
| Remover espaços | `TRIM()` | `TRIM()` | `TRIM()` | `TRIM()` |
| Extrair parte | `SUBSTRING()` `LEFT()` `RIGHT()` | `SUBSTRING()` | `SUBSTRING()` | `SUBSTR()` |
| Tamanho | `CHAR_LENGTH()` | `LENGTH()` | `LEN()` | `LENGTH()` |
| Substituir | `REPLACE()` | `REPLACE()` | `REPLACE()` | `REPLACE()` |
| Posição | `LOCATE()` | `STRPOS()` | `CHARINDEX()` | `INSTR()` |
| Repetir | `REPEAT()` | `REPEAT()` | `REPLICATE()` | `RPAD()` |

---

# 68. Funções de Data — Trabalhando com tempo

## A armadilha mais comum com datas

```sql
-- Se OrderDate for DATETIME contendo hora, esta query retorna ZERO linhas!
-- '2025-11-11' = '2025-11-11 00:00:00' — pedidos das 13h nao batem
SELECT * FROM Orders WHERE OrderDate = '2025-11-11';

-- Correto: cobre o dia inteiro independente do horario
SELECT * FROM Orders
WHERE OrderDate >= '2025-11-11'
  AND OrderDate <  '2025-11-12';
```

---

## Obtendo a data/hora atual

```sql
-- Data e hora completa
SELECT NOW();               -- MySQL, PostgreSQL: '2026-04-18 14:35:22'
SELECT CURRENT_TIMESTAMP;   -- Padrao SQL (todos os bancos)
SELECT GETDATE();           -- SQL Server

-- Apenas a data
SELECT CURDATE();           -- MySQL: '2026-04-18'
SELECT CURRENT_DATE;        -- Padrao SQL, PostgreSQL

-- Apenas a hora
SELECT CURTIME();           -- MySQL
SELECT CURRENT_TIME;        -- Padrao SQL, PostgreSQL
```

---

## DATE_FORMAT — Formatando datas para exibição

```sql
-- MySQL
SELECT DATE_FORMAT(NOW(), '%d/%m/%Y');            -- '18/04/2026'
SELECT DATE_FORMAT(NOW(), '%d/%m/%Y %H:%i:%s');   -- '18/04/2026 14:35:22'
SELECT DATE_FORMAT(NOW(), '%Y-%m');               -- '2026-04' (para agrupamento)

-- PostgreSQL: TO_CHAR()
SELECT TO_CHAR(NOW(), 'DD/MM/YYYY');
SELECT TO_CHAR(NOW(), 'DD/MM/YYYY HH24:MI:SS');

-- SQL Server: FORMAT()
SELECT FORMAT(GETDATE(), 'dd/MM/yyyy');
SELECT CONVERT(VARCHAR, GETDATE(), 103);          -- 103 = dd/mm/yyyy
```

| Code MySQL | Significado | Exemplo |
|---|---|---|
| `%Y` | Ano 4 dígitos | 2026 |
| `%m` | Mês com zero | 04 |
| `%d` | Dia com zero | 18 |
| `%H` | Hora 24h | 14 |
| `%i` | Minutos | 35 |
| `%M` | Nome do mês (inglês) | April |

### Caso de uso real — Relatório mensal de vendas

```sql
SELECT
    DATE_FORMAT(order_date, '%Y-%m')        AS month_key,
    DATE_FORMAT(order_date, '%m/%Y')        AS month_display,
    COUNT(*)                                AS total_orders,
    ROUND(SUM(order_total), 2)              AS revenue,
    ROUND(AVG(order_total), 2)              AS avg_ticket
FROM orders
WHERE order_date BETWEEN '2024-01-01' AND '2024-12-31'
GROUP BY month_key, month_display
ORDER BY month_key;
```

---

## Extraindo partes de uma data

```sql
-- MySQL: funções dedicadas
SELECT YEAR(NOW());       -- 2026
SELECT MONTH(NOW());      -- 4
SELECT DAY(NOW());        -- 18
SELECT DAYOFWEEK(NOW());  -- 7 (1=domingo, 7=sabado no MySQL)
SELECT QUARTER(NOW());    -- 2

-- PostgreSQL: EXTRACT()
SELECT EXTRACT(YEAR    FROM NOW());   -- 2026
SELECT EXTRACT(MONTH   FROM NOW());   -- 4
SELECT EXTRACT(QUARTER FROM NOW());   -- 2
SELECT EXTRACT(DOW     FROM NOW());   -- 6 (0=domingo no PostgreSQL)

-- SQL Server: DATEPART()
SELECT DATEPART(YEAR,    GETDATE());
SELECT DATEPART(QUARTER, GETDATE());
```

### Caso de uso real — Sazonalidade e churn

```sql
-- Em qual dia da semana as vendas são maiores?
SELECT
    DAYOFWEEK(order_date)        AS day_number,
    DAYNAME(order_date)          AS day_name,
    COUNT(*)                     AS total_orders,
    ROUND(SUM(order_total), 2)   AS revenue
FROM orders
WHERE YEAR(order_date) = 2024
GROUP BY day_number, day_name
ORDER BY revenue DESC;

-- Clientes classificados por inatividade (churn analysis)
SELECT
    c.customer_name,
    MAX(o.order_date)                       AS last_purchase,
    DATEDIFF(CURDATE(), MAX(o.order_date))  AS days_inactive,
    CASE
        WHEN DATEDIFF(CURDATE(), MAX(o.order_date)) > 365 THEN 'Churned'
        WHEN DATEDIFF(CURDATE(), MAX(o.order_date)) > 180 THEN 'Em Risco'
        WHEN DATEDIFF(CURDATE(), MAX(o.order_date)) > 90  THEN 'Frio'
        ELSE 'Ativo'
    END AS customer_status
FROM customers AS c
LEFT JOIN orders AS o ON c.customer_id = o.customer_id
GROUP BY c.customer_id, c.customer_name
ORDER BY days_inactive DESC;
```

---

## DATE_ADD e DATE_SUB — Aritmética de datas

```sql
-- MySQL
SELECT DATE_ADD(NOW(), INTERVAL 7  DAY);   -- daqui a 7 dias
SELECT DATE_ADD(NOW(), INTERVAL 1  MONTH); -- daqui a 1 mes
SELECT DATE_SUB(NOW(), INTERVAL 30 DAY);   -- 30 dias atras
SELECT NOW() + INTERVAL 7 DAY;             -- atalho equivalente

-- PostgreSQL
SELECT NOW() + INTERVAL '7 days';
SELECT NOW() - INTERVAL '30 days';
SELECT NOW() + INTERVAL '2 hours 30 minutes';

-- SQL Server: DATEADD(unidade, quantidade, data)
SELECT DATEADD(DAY,    7, GETDATE());
SELECT DATEADD(MONTH,  1, GETDATE());
SELECT DATEADD(DAY,  -30, GETDATE());      -- negativo = subtrair
```

### Caso de uso real — Pedidos próximos ao vencimento

```sql
-- Pedidos que vencem nos próximos 7 dias
SELECT
    o.order_id,
    c.customer_name,
    o.due_date,
    DATEDIFF(o.due_date, CURDATE()) AS days_until_due
FROM orders AS o
INNER JOIN customers AS c ON o.customer_id = c.customer_id
WHERE o.due_date BETWEEN CURDATE() AND DATE_ADD(CURDATE(), INTERVAL 7 DAY)
  AND o.payment_status = 'pending'
ORDER BY days_until_due;
```

---

## DATEDIFF — Diferença entre datas

```sql
-- MySQL: DATEDIFF(fim, inicio) -> diferenca em DIAS
SELECT DATEDIFF('2026-12-31', '2026-01-01');      -- 364
SELECT DATEDIFF(NOW(), birth_date) / 365 AS age   -- idade aproximada em anos
FROM users;

-- PostgreSQL: subtracao direta
SELECT '2026-12-31'::date - '2026-01-01'::date;   -- 364 dias
SELECT EXTRACT(YEAR FROM AGE(NOW(), birth_date)) AS age FROM users;

-- SQL Server: DATEDIFF(unidade, inicio, fim)
SELECT DATEDIFF(DAY,   '2026-01-01', '2026-12-31');  -- 364
SELECT DATEDIFF(MONTH, '2026-01-01', '2026-12-31');  -- 11
SELECT DATEDIFF(YEAR,  '2000-01-01', '2026-01-01');  -- 26
```

---

## Tabela comparativa — Funções de data por banco

| Operação | MySQL | PostgreSQL | SQL Server | Oracle |
|---|---|---|---|---|
| Data/hora atual | `NOW()` | `NOW()` | `GETDATE()` | `SYSDATE` |
| Apenas data | `CURDATE()` | `CURRENT_DATE` | `CAST(GETDATE() AS DATE)` | `TRUNC(SYSDATE)` |
| Formatar | `DATE_FORMAT()` | `TO_CHAR()` | `FORMAT()` | `TO_CHAR()` |
| Extrair parte | `YEAR()` `MONTH()` `DAY()` | `EXTRACT()` | `DATEPART()` | `EXTRACT()` |
| Adicionar | `DATE_ADD()` / `+INTERVAL` | `+INTERVAL` | `DATEADD()` | `+INTERVAL` |
| Diferença (dias) | `DATEDIFF(end,start)` | `date1-date2` | `DATEDIFF(DAY,s,e)` | `date1-date2` |
| Truncar ao mês | `DATE_FORMAT(d,'%Y-%m-01')` | `DATE_TRUNC('month',d)` | `DATEADD(DAY,1-DAY(d),d)` | `TRUNC(d,'MM')` |

---

# 69. Funções Numéricas — Cálculos e arredondamentos

## Por que funções numéricas importam?

Preços precisam de arredondamento preciso. Porcentagens precisam de casas decimais controladas. Divisões podem gerar zero no denominador. Funções numéricas resolvem tudo isso **dentro do banco**, garantindo consistência independente da linguagem que acessa os dados.

---

## ROUND — Arredondando valores

```sql
SELECT ROUND(3.14159, 2);  -- 3.14  (2 casas decimais)
SELECT ROUND(3.75, 1);     -- 3.8   (arredonda para cima)
SELECT ROUND(3.74, 1);     -- 3.7   (arredonda para baixo)
SELECT ROUND(1234.5, -2);  -- 1200  (arredonda para centenas)
SELECT ROUND(1750, -3);    -- 2000  (arredonda para milhares)
```

### Caso de uso real — Preços, impostos e comissões

```sql
SELECT
    product_name,
    list_price,
    discount_pct,
    ROUND(list_price * (1 - discount_pct / 100), 2)          AS discounted_price,
    ROUND(list_price * 0.18, 2)                               AS icms_18pct,
    ROUND(list_price * (1 - discount_pct / 100) * 1.18, 2)   AS final_price_with_tax
FROM products
WHERE status = 'active'
ORDER BY final_price_with_tax DESC;

-- Comissao de vendedores
SELECT
    salesperson_name,
    ROUND(SUM(sale_amount), 2)                           AS total_sales,
    commission_rate_pct,
    ROUND(SUM(sale_amount) * commission_rate_pct / 100, 2) AS commission
FROM sales AS s
INNER JOIN salespersons AS sp ON s.salesperson_id = sp.salesperson_id
WHERE YEAR(sale_date) = 2024
GROUP BY salesperson_name, commission_rate_pct
ORDER BY commission DESC;
```

---

## FLOOR e CEIL — Arredondamentos direcionais

```sql
SELECT FLOOR(4.9);   -- 4   (sempre para baixo)
SELECT FLOOR(-4.1);  -- -5  (mais negativo = para baixo no eixo numerico)
SELECT CEIL(4.1);    -- 5   (sempre para cima)
SELECT CEIL(-4.9);   -- -4  (menos negativo = para cima)
```

### Caso de uso real — Paginação e agrupamento em faixas

```sql
-- Quantas paginas sao necessarias? (93 itens, 10 por pagina = 10 paginas)
SELECT
    COUNT(*)              AS total_products,
    CEIL(COUNT(*) / 10.0) AS total_pages     -- .0 essencial: forca divisao decimal
FROM products
WHERE status = 'active';

-- Distribuindo produtos em faixas de preco de R$50
SELECT
    FLOOR(price / 50) * 50       AS bucket_start,  -- 50, 100, 150...
    FLOOR(price / 50) * 50 + 49  AS bucket_end,    -- 99, 149, 199...
    COUNT(*)                      AS product_count
FROM products
GROUP BY bucket_start, bucket_end
ORDER BY bucket_start;
-- Preco 73 -> faixa 50-99 | Preco 120 -> faixa 100-149
```

---

## ABS — Valor absoluto

```sql
SELECT ABS(-150);   -- 150
SELECT ABS(150);    -- 150
SELECT ABS(-3.14);  -- 3.14
```

### Caso de uso real — Variações e desvios

```sql
-- Variacao entre custo estimado e real (magnitude, nao direcao)
SELECT
    product_name,
    estimated_cost,
    actual_cost,
    actual_cost - estimated_cost              AS variance,
    ABS(actual_cost - estimated_cost)         AS variance_magnitude,
    ROUND(ABS(actual_cost - estimated_cost)
          / estimated_cost * 100, 1)          AS variance_pct
FROM production_costs
ORDER BY variance_magnitude DESC;
```

---

## MOD — Resto da divisão

```sql
SELECT MOD(10, 3);  -- 1  (10 / 3 = 3 resto 1)
SELECT MOD(15, 5);  -- 0  (divisivel exato)
SELECT MOD(7, 2);   -- 1  (impar)
SELECT 10 % 3;      -- 1  (operador alternativo)
```

### Caso de uso real — Distribuição A/B e validações

```sql
-- Distribuindo clientes em 3 grupos para teste A/B/C
SELECT
    customer_id,
    customer_name,
    CASE MOD(customer_id, 3)
        WHEN 0 THEN 'Grupo A'
        WHEN 1 THEN 'Grupo B'
        WHEN 2 THEN 'Grupo C'
    END AS test_group
FROM customers
WHERE status = 'active';

-- Amostragem: somente clientes com ID par
SELECT order_id, customer_id, order_total
FROM orders
WHERE MOD(order_id, 2) = 0
  AND YEAR(order_date) = 2024
LIMIT 100;
```

---

## POWER e SQRT — Potência e raiz

```sql
SELECT POWER(2, 10);  -- 1024
SELECT POWER(3, 3);   -- 27
SELECT SQRT(144);     -- 12
SELECT SQRT(2);       -- 1.41421356...
```

### Caso de uso real — Juros compostos

```sql
-- Valor futuro: PV * (1 + r)^n
SELECT
    investment_name,
    initial_value                                                  AS present_value,
    annual_rate_pct,
    investment_years,
    ROUND(initial_value * POWER(1 + annual_rate_pct/100, investment_years), 2)
                                                                   AS future_value,
    ROUND(initial_value * POWER(1 + annual_rate_pct/100, investment_years)
          - initial_value, 2)                                      AS total_interest
FROM investments
ORDER BY future_value DESC;
```

---

## Tabela de referência — Funções numéricas por banco

| Função | MySQL | PostgreSQL | SQL Server | Oracle |
|---|---|---|---|---|
| Arredondar | `ROUND(n, d)` | `ROUND(n, d)` | `ROUND(n, d)` | `ROUND(n, d)` |
| Para baixo | `FLOOR(n)` | `FLOOR(n)` | `FLOOR(n)` | `FLOOR(n)` |
| Para cima | `CEIL(n)` | `CEIL(n)` | `CEILING(n)` | `CEIL(n)` |
| Absoluto | `ABS(n)` | `ABS(n)` | `ABS(n)` | `ABS(n)` |
| Módulo | `MOD(a,b)` / `%` | `MOD(a,b)` / `%` | `%` | `MOD(a,b)` |
| Potência | `POWER(b,e)` | `POWER(b,e)` / `^` | `POWER(b,e)` | `POWER(b,e)` |
| Raiz | `SQRT(n)` | `SQRT(n)` | `SQRT(n)` | `SQRT(n)` |
| Truncar | `TRUNCATE(n,d)` | `TRUNC(n,d)` | `ROUND(n,d,1)` | `TRUNC(n,d)` |
| Aleatório | `RAND()` | `RANDOM()` | `RAND()` | `DBMS_RANDOM.VALUE` |

---

# 70. MERGE — Upsert em uma única instrução

## O problema que o MERGE resolve

Sincronizar dados exige: atualizar se já existe, inserir se não existe. Sem `MERGE`, duas queries separadas criam risco de **race condition** — entre o `SELECT` e o `INSERT`, outro processo pode inserir o mesmo registro. O `MERGE` é uma **instrução atômica** que elimina esse risco.

---

## Sintaxe padrão SQL (SQL Server, Oracle, PostgreSQL 15+)

```sql
MERGE INTO target_table AS target        -- tabela a ser modificada
USING source_table AS source             -- fonte: tabela, subquery ou CTE
ON target.key_col = source.key_col       -- condição de correspondência

WHEN MATCHED THEN                        -- registro JA EXISTE no target
    UPDATE SET
        target.column1    = source.column1,
        target.updated_at = NOW()

WHEN NOT MATCHED BY TARGET THEN          -- registro NAO EXISTE (novo)
    INSERT (column1, column2, created_at)
    VALUES (source.column1, source.column2, NOW())

WHEN NOT MATCHED BY SOURCE THEN          -- existe no target, nao na source
    UPDATE SET target.status = 'discontinued';
```

---

## Exemplo completo — Sincronização de catálogo de produtos

```sql
MERGE INTO products AS target
USING products_import AS source
ON target.sku = source.sku

-- Atualiza apenas se algo mudou (evita writes desnecessários)
WHEN MATCHED AND (
    target.price != source.price OR
    target.stock != source.stock OR
    target.name  != source.name
) THEN
    UPDATE SET
        target.name       = source.name,
        target.price      = source.price,
        target.stock      = source.stock,
        target.updated_at = NOW()

-- Produto novo: insere
WHEN NOT MATCHED BY TARGET THEN
    INSERT (sku, name, price, stock, status, created_at)
    VALUES (source.sku, source.name, source.price, source.stock, 'active', NOW())

-- Produto sumiu do fornecedor: descontinua
WHEN NOT MATCHED BY SOURCE THEN
    UPDATE SET
        target.status     = 'discontinued',
        target.updated_at = NOW();
```

---

## SQL Server — com OUTPUT para rastrear ações

```sql
MERGE INTO products AS target
USING products_import AS source ON target.sku = source.sku

WHEN MATCHED THEN
    UPDATE SET target.price = source.price, target.stock = source.stock

WHEN NOT MATCHED THEN
    INSERT (sku, price, stock) VALUES (source.sku, source.price, source.stock)

OUTPUT
    $action          AS merge_action,   -- 'INSERT' ou 'UPDATE'
    inserted.sku     AS sku,
    inserted.price   AS new_price,
    deleted.price    AS old_price;      -- NULL se foi INSERT
```

---

## MySQL — INSERT ... ON DUPLICATE KEY UPDATE

MySQL **não suporta** `MERGE`. Use `INSERT ... ON DUPLICATE KEY UPDATE` quando há chave `UNIQUE` ou `PRIMARY KEY`:

```sql
-- Se o SKU violar a UNIQUE constraint → executa UPDATE
-- Se nao existe → executa INSERT
INSERT INTO products (sku, name, price, stock, created_at)
VALUES
    ('ABC-123', 'Produto A', 99.90, 50, NOW()),
    ('DEF-456', 'Produto B', 149.90, 30, NOW())
ON DUPLICATE KEY UPDATE
    name       = VALUES(name),
    price      = VALUES(price),
    stock      = VALUES(stock),
    updated_at = NOW();

-- MySQL 8.0.19+: alias mais legível (recomendado)
INSERT INTO products (sku, name, price, stock)
VALUES ('ABC-123', 'Produto A', 99.90, 50) AS new_data
ON DUPLICATE KEY UPDATE
    name  = new_data.name,
    price = new_data.price,
    stock = new_data.stock;
```

---

## PostgreSQL — INSERT ... ON CONFLICT

```sql
-- Disponível desde PostgreSQL 9.5 (qualquer versão moderna)
INSERT INTO products (sku, name, price, stock, created_at)
VALUES ('ABC-123', 'Produto A', 99.90, 50, NOW())
ON CONFLICT (sku)          -- quando 'sku' viola UNIQUE constraint
DO UPDATE SET
    name       = EXCLUDED.name,    -- EXCLUDED = valores que tentaríamos inserir
    price      = EXCLUDED.price,
    stock      = EXCLUDED.stock,
    updated_at = NOW();

-- Ignorar silenciosamente duplicatas
INSERT INTO products (sku, name) VALUES ('ABC-123', 'Produto A')
ON CONFLICT (sku) DO NOTHING;
```

---

## Caso de uso real — ETL incremental diário (SQL Server)

```sql
-- Pode ser executado todo dia: insere novos, corrige retificações, sem duplicar
MERGE INTO sales_fact AS target
USING (
    SELECT order_id, product_id, customer_id, sale_date,
           quantity, unit_price, quantity * unit_price AS total_amount
    FROM staging_orders
    WHERE CAST(loaded_at AS DATE) = CAST(GETDATE() AS DATE)
) AS source ON target.order_id = source.order_id

-- Retificacao: preco ou quantidade mudou
WHEN MATCHED AND (
    target.quantity   != source.quantity OR
    target.unit_price != source.unit_price
) THEN
    UPDATE SET
        target.quantity     = source.quantity,
        target.unit_price   = source.unit_price,
        target.total_amount = source.total_amount,
        target.updated_at   = GETDATE()

-- Novo pedido
WHEN NOT MATCHED BY TARGET THEN
    INSERT (order_id, product_id, customer_id, sale_date, quantity, unit_price, total_amount, created_at)
    VALUES (source.order_id, source.product_id, source.customer_id, source.sale_date,
            source.quantity, source.unit_price, source.total_amount, GETDATE());
```

---

## Comparativo — Escolhendo a abordagem certa

| Critério | MERGE | INSERT ON CONFLICT (PG) | ON DUPLICATE KEY (MySQL) |
|---|---|---|---|
| Padrão SQL | ✅ | ❌ extensão PG | ❌ extensão MySQL |
| NOT MATCHED BY SOURCE | ✅ | ❌ | ❌ |
| Múltiplos WHEN condicionais | ✅ | ❌ | ❌ |
| OUTPUT / log de ações | ✅ SQL Server | ❌ | ❌ |
| Suporte MySQL | ❌ | ❌ | ✅ |
| Suporte PostgreSQL | ✅ v15+ | ✅ v9.5+ | ❌ |
| Performance grande volume | ✅ | ✅ | ✅ |

**Regra de decisão:**

- SQL Server / Oracle / PostgreSQL 15+ → **MERGE**
- PostgreSQL (qualquer versão) → **INSERT ... ON CONFLICT**
- MySQL / MariaDB → **INSERT ... ON DUPLICATE KEY UPDATE**

---

## 📄 Resumo — Capítulos 67–70

| Capítulo | Tema | Principais funções/comandos |
|---|---|---|
| 67 | Funções de String | `CONCAT`, `UPPER`, `LOWER`, `TRIM`, `LENGTH`, `SUBSTRING`, `REPLACE`, `LOCATE` |
| 68 | Funções de Data | `NOW()`, `DATE_FORMAT()`, `YEAR/MONTH/DAY()`, `DATE_ADD/SUB()`, `DATEDIFF()` |
| 69 | Funções Numéricas | `ROUND()`, `FLOOR()`, `CEIL()`, `ABS()`, `MOD()`, `POWER()`, `SQRT()` |
| 70 | MERGE / Upsert | `MERGE`, `INSERT ON CONFLICT`, `INSERT ON DUPLICATE KEY UPDATE` |

---

*SQL — Do Zero ao Profissional · Edicao 2026*
*Ebook RAG · Explicacoes em pt-BR · Codigo em ingles (US)*
*70 capitulos · Verificado contra fontes oficiais em Abril/2026*
*Compativel com MySQL 8.4/9.6 · PostgreSQL 18 · SQL Server 2022 · Oracle 23ai · SQLite*
