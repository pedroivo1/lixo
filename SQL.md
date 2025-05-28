# 📘 Super Resumo de Comandos Básicos do PostgreSQL

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

### Filtros (WHERE)
```sql
SELECT * FROM nome_tabela WHERE idade > 25;
```

### Ordenação
```sql
SELECT * FROM nome_tabela ORDER BY idade DESC;
```

### Limitar resultados
```sql
SELECT * FROM nome_tabela LIMIT 5;
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
CREATE TABLE cidade (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100)
);

CREATE TABLE pessoa (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100),
  id_cidade INTEGER REFERENCES cidade(id)
);
```

---

## 🔍 6. Junções (JOIN)

```sql
SELECT p.nome, c.nome AS cidade
FROM pessoa p
JOIN cidade c ON p.id_cidade = c.id;
```

---

## 🔢 7. Funções Agregadas

```sql
SELECT COUNT(*), AVG(idade), MAX(idade), MIN(idade)
FROM pessoa;
```

### Agrupamento
```sql
SELECT cidade_id, COUNT(*) 
FROM pessoa 
GROUP BY cidade_id;
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

## ✅ Dicas Extras

| Conceito         | PostgreSQL usa      |
|------------------|---------------------|
| ID automático    | `SERIAL`            |
| Booleano         | `BOOLEAN` (`TRUE`, `FALSE`) |
| Texto variável   | `VARCHAR(n)` ou `TEXT` |
| Data e hora      | `DATE`, `TIMESTAMP` |
| Default          | `DEFAULT valor`     |
