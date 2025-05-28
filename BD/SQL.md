# 📘 Super Resumo de Comandos Básicos do PostgreSQL

## 🧱 Estrutura Exemplo do Banco de Dados

Este resumo usa como base o seguinte esquema de tabelas:

| Tabela   | Campos                                               |
|----------|------------------------------------------------------|
| pessoa   | id, nome, idade, ativo, id_cidade                    |
| cidade   | id, nome, id_pais (chave estrangeira para pais.id)  |
| pais     | id, nome                                             |

Relacionamentos:
- `pessoa.id_cidade` → `cidade.id`
- `cidade.id_pais` → `pais.id`

---

## 🛠️ 1. Criação de Estrutura

### Criar banco de dados
```sql
CREATE DATABASE nome_do_banco;
```

### Conectar ao banco
```sql
\c nome_do_banco
```

### Criar tabela
```sql
CREATE TABLE nome_tabela (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100),
  idade INTEGER,
  ativo BOOLEAN DEFAULT TRUE
);
```

### Apagar tabela
```sql
DROP TABLE IF EXISTS nome_tabela CASCADE;
```

---

## 📥 2. Inserção de Dados

```sql
INSERT INTO nome_tabela (nome, idade) VALUES ('João', 30);
```

---

## 📤 3. Consulta de Dados (SELECT)

### Tudo da tabela
```sql
SELECT * FROM nome_tabela;
```

### Selecionar colunas específicas
```sql
SELECT nome, idade FROM nome_tabela;
```

### Filtros (WHERE)
```sql
SELECT * FROM nome_tabela WHERE idade > 25;
```

### Operadores lógicos
```sql
SELECT * FROM nome_tabela WHERE idade > 25 AND ativo = TRUE;
SELECT * FROM nome_tabela WHERE idade BETWEEN 20 AND 30;
SELECT * FROM nome_tabela WHERE nome LIKE 'J%';
SELECT * FROM nome_tabela WHERE nome ILIKE '%joão%'; -- case insensitive
SELECT * FROM nome_tabela WHERE idade IN (25, 30, 35);
SELECT * FROM nome_tabela WHERE idade IS NULL;
SELECT * FROM nome_tabela WHERE idade IS NOT NULL;
```

### Ordenação
```sql
SELECT * FROM nome_tabela ORDER BY idade DESC, nome ASC;
```

### Limitar e pular resultados
```sql
SELECT * FROM nome_tabela LIMIT 5;
SELECT * FROM nome_tabela OFFSET 10;
SELECT * FROM nome_tabela LIMIT 5 OFFSET 10;
```

---

## 🔄 4. Atualização e Exclusão

### Atualizar
```sql
UPDATE nome_tabela SET idade = 35 WHERE nome = 'João';
```

### Deletar
```sql
DELETE FROM nome_tabela WHERE nome = 'João';
```

---

## 🔗 5. Relacionamentos (Chaves Estrangeiras)

```sql
CREATE TABLE pais (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100)
);

CREATE TABLE cidade (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100),
  id_pais INTEGER REFERENCES pais(id)
);

CREATE TABLE pessoa (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100),
  idade INTEGER,
  ativo BOOLEAN DEFAULT TRUE,
  id_cidade INTEGER REFERENCES cidade(id)
);
```

---

## 🔍 6. Junções (JOIN)

### Exemplo com 2 tabelas
```sql
SELECT p.nome, c.nome AS cidade
FROM pessoa p
JOIN cidade c ON p.id_cidade = c.id;
```

### Exemplo com 3 tabelas (INNER JOIN)
```sql
SELECT p.nome AS pessoa, c.nome AS cidade, pa.nome AS pais
FROM pessoa p
JOIN cidade c ON p.id_cidade = c.id
JOIN pais pa ON c.id_pais = pa.id;
```

#### Sem apelidos para Tabelas
```sql
SELECT pessoa.nome AS pessoa, cidade.nome AS cidade, pais.nome AS pais
FROM pessoa
JOIN cidade ON pessoa.id_cidade = cidade.id
JOIN pais ON cidade.id_pais = pais.id;
```

---

## 🔢 7. Funções Agregadas

```sql
SELECT COUNT(*), AVG(idade), MAX(idade), MIN(idade)
FROM pessoa;
```

### Agrupamento
```sql
SELECT id_cidade, COUNT(*) 
FROM pessoa 
GROUP BY id_cidade;
```

---

## 📘 8. Outros Comandos Úteis

### Listar tabelas
```sql
\dt
```

### Ver estrutura de uma tabela
```sql
\d nome_tabela
```

### Ver os bancos disponíveis
```sql
\l
```
---

## 🧠 Exemplos de Uso Úteis

### 📊 Quantidade de pessoas por cidade
```sql
SELECT cidade.nome, COUNT(*)  
FROM pessoa
JOIN cidade ON pessoa.id_cidade = cidade.id
GROUP BY cidade.nome;
```

### 📋 Listar todas as pessoas ativas maiores de 18 anos
```sql
SELECT * FROM pessoa
WHERE idade > 18 AND ativo = TRUE;
```

### 📅 Pessoas ordenadas por idade (mais velhas primeiro)
```sql
SELECT * FROM pessoa
ORDER BY idade DESC;
```

### 🔍 Buscar pessoas cujo nome começa com 'A'
```sql
SELECT * FROM pessoa
WHERE nome LIKE 'A%';
```

### 🔎 Buscar pessoas com nome que contém 'ana' (ignorando maiúsculas/minúsculas)
```sql
SELECT * FROM pessoa
WHERE nome ILIKE '%ana%';
```

### 📉 Cidades sem nenhuma pessoa associada (usando LEFT JOIN)
```sql
SELECT cidade.nome
FROM cidade
LEFT JOIN pessoa ON cidade.id = pessoa.id_cidade
WHERE pessoa.id IS NULL;
```


---

## ✅ Dicas Extras

| Conceito         | PostgreSQL usa                  |
|------------------|---------------------------------|
| ID automático    | `SERIAL`                        |
| Booleano         | `BOOLEAN` (`TRUE`, `FALSE`)     |
| Texto variável   | `VARCHAR(n)` ou `TEXT`          |
| Data e hora      | `DATE`, `TIMESTAMP`             |
| Default          | `DEFAULT valor`                 |
