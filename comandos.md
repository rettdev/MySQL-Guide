## Introdução aos Comandos SQL Fundamentais

Nesta seção, você será introduzido aos comandos SQL fundamentais: SELECT, INSERT, UPDATE e DELETE. Esses comandos são amplamente utilizados para manipular e consultar dados em bancos de dados relacionais, incluindo o MySQL. A seguir, vamos explorar cada um desses comandos em detalhes, juntamente com exemplos de uso.

### CREATE TABLE

O comando CREATE TABLE é usado para criar uma nova tabela no banco de dados. Ele permite que você especifique o nome da tabela, as colunas e os tipos de dados para cada coluna.

Exemplo de uso:

```sql
CREATE TABLE tabela (
    coluna1 tipo_de_dado1,
    coluna2 tipo_de_dado2,
    ...
);
```

Exemplo prático:

```sql
CREATE TABLE usuarios (
    id INT,
    nome VARCHAR(50),
    email VARCHAR(100),
    idade INT
);
```

Neste exemplo, estamos criando uma nova tabela chamada "usuarios" com as colunas "id", "nome", "email" e "idade".

### ALTER TABLE

O comando ALTER TABLE é usado para modificar uma tabela existente no banco de dados. Ele permite que você adicione, altere ou remova colunas da tabela.

Exemplo de uso:

```sql
ALTER TABLE tabela
    ADD coluna tipo_de_dado;
```

Exemplo prático:

```sql
ALTER TABLE usuarios
    ADD sobrenome VARCHAR(50);
```

Neste exemplo, estamos adicionando uma nova coluna chamada "sobrenome" na tabela "usuarios".

### SELECT DISTINCT

O comando SELECT DISTINCT é usado para retornar valores únicos em uma coluna de uma tabela. Ele elimina registros duplicados e retorna apenas uma ocorrência de cada valor distinto.

Exemplo de uso:

```sql
SELECT DISTINCT coluna FROM tabela;
```

Exemplo prático:

```sql
SELECT DISTINCT cidade FROM clientes;
```

Neste exemplo, estamos selecionando todos os valores distintos da coluna "cidade" da tabela "clientes".

### ORDER BY

O comando ORDER BY é usado para classificar os resultados de uma consulta em ordem ascendente (ASC) ou descendente (DESC) com base em uma ou mais colunas.

Exemplo de uso:

```sql
SELECT coluna1, coluna2 FROM tabela ORDER BY coluna ASC/DESC;
```

Exemplo prático:

```sql
SELECT nome, idade FROM usuarios ORDER BY idade DESC;
```

Neste exemplo, estamos selecionando os nomes e idades dos usuários da tabela "usuarios" e ordenando-os em ordem decrescente com base na idade.

### SELECT

O comando SELECT é usado para recuperar dados de uma tabela ou visualização em um banco de dados. Ele permite que você especifique as colunas que deseja selecionar, as tabelas em que deseja realizar a consulta e quaisquer condições para filtrar os resultados.

Exemplo de uso:

```sql
SELECT coluna1, coluna2 FROM tabela WHERE condição;
```

Exemplo prático:

```sql
SELECT nome, email FROM usuarios WHERE idade > 25;
```

Neste exemplo, estamos selecionando as colunas "nome" e "email" da tabela "usuarios" apenas para os registros em que a idade seja maior que 25.

### INSERT

O comando INSERT é usado para inserir novos registros em uma tabela do banco de dados. Ele permite que você especifique os valores que deseja inserir para cada coluna na tabela.

Exemplo de uso:

```sql
INSERT INTO tabela (coluna1, coluna2) VALUES (valor1, valor2);
```

Exemplo prático:

```sql
INSERT INTO usuarios (nome, email) VALUES ('João', 'joao@email.com');
```

Neste exemplo, estamos inserindo um novo registro na tabela "usuarios" com os valores 'João' e 'joao@email.com'.

### UPDATE

O comando UPDATE é usado para modificar registros existentes em uma tabela do banco de dados. Ele permite que você atualize os valores das colunas especificadas com novos valores.

Exemplo de uso:

```sql
UPDATE tabela SET coluna1 = novo_valor WHERE condição;
```

Exemplo prático:

```sql
UPDATE usuarios SET email = 'novoemail@email.com' WHERE id = 1;
```

Neste exemplo, estamos atualizando o valor da coluna "email" para 'novoemail@email.com' para o registro com ID igual a 1 na tabela "usuarios".

### DELETE

O comando DELETE é usado para excluir registros existentes de uma tabela do banco de dados. Ele permite que você especifique as condições para selecionar os registros que deseja excluir.

Exemplo de uso:

```sql
DELETE FROM tabela WHERE condição;
```

Exemplo prático:

```sql
DELETE FROM usuarios WHERE idade > 30;
```

Neste exemplo, estamos excluindo todos os registros da tabela "usuarios" em que a idade seja maior que 30.

### WHERE

O comando WHERE é usado para filtrar os resultados de uma consulta com base em uma condição específica. Ele permite que você especifique critérios para selecionar registros que atendam a determinadas condições.

Exemplo de uso:

```sql
SELECT coluna1, coluna2 FROM tabela WHERE condição;
```

Exemplo prático:

```sql
SELECT nome, idade FROM usuarios WHERE idade > 30;
```

Neste exemplo, estamos selecionando os nomes e idades dos usuários da tabela "usuarios" apenas para os registros em que a idade seja maior que 30.

### GROUP BY

O comando GROUP BY é usado para agrupar registros com base nos valores de uma ou mais colunas. Ele permite que você realize operações agregadas, como COUNT, SUM, AVG, etc., em grupos de registros.

Exemplo de uso:

```sql
SELECT coluna1, funcao_agregada(coluna2) FROM tabela GROUP BY coluna1;
```
Exemplo prático:

```sql
SELECT cidade, COUNT(*) FROM clientes GROUP BY cidade;
```

Neste exemplo, estamos contando o número de clientes em cada cidade, agrupando os registros com base na coluna "cidade".

### JOIN

O comando JOIN é usado para combinar registros de duas ou mais tabelas com base em uma condição de junção. Ele permite que você recupere informações de várias tabelas relacionadas.

Exemplo de uso:

```sql
SELECT colunas FROM tabela1 JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

Exemplo prático:

```sql
SELECT usuarios.nome, pedidos.produto FROM usuarios JOIN pedidos ON usuarios.id = pedidos.usuario_id;
```

Neste exemplo, estamos selecionando o nome do usuário e o produto do pedido, combinando registros das tabelas "usuarios" e "pedidos" com base na coluna "id" em "usuarios" e "usuario_id" em "pedidos".

### LIMIT

O comando LIMIT é usado para limitar o número de registros retornados por uma consulta. Ele permite que você especifique uma quantidade máxima de registros a serem retornados.

Exemplo de uso:

```sql
SELECT colunas FROM tabela LIMIT quantidade;
```

Exemplo prático:

```sql
SELECT nome FROM usuarios LIMIT 10;
```

Neste exemplo, estamos selecionando apenas os 10 primeiros nomes da tabela "usuarios".

### HAVING

O comando HAVING é usado para filtrar os resultados de uma consulta após a aplicação do comando GROUP BY. Ele permite que você especifique critérios para selecionar grupos de registros que atendam a determinadas condições.

Exemplo de uso:

```sql
SELECT coluna1, funcao_agregada(coluna2) FROM tabela GROUP BY coluna1 HAVING condição;
```

Exemplo prático:

```sql
SELECT cidade, COUNT(*) FROM clientes GROUP BY cidade HAVING COUNT(*) > 10;
```

Neste exemplo, estamos contando o número de clientes em cada cidade, agrupando os registros com base na coluna "cidade", e selecionando apenas os grupos de registros em que a contagem seja maior que 10.

### UNION

O comando UNION é usado para combinar os resultados de duas ou mais consultas em uma única lista de resultados. Ele permite que você execute consultas separadas e combine seus resultados em uma única tabela.

Exemplo de uso:

```sql
SELECT colunas FROM tabela1
UNION
SELECT colunas FROM tabela2;
```

Exemplo prático:

```sql
SELECT nome FROM clientes
UNION
SELECT nome FROM fornecedores;
```

Neste exemplo, estamos selecionando os nomes dos clientes e fornecedores em duas consultas separadas e combinando os resultados em uma única lista.

### EXISTS

O comando EXISTS é usado para verificar a existência de registros em uma subconsulta. Ele retorna verdadeiro se a subconsulta retornar algum resultado e falso caso contrário.

Exemplo de uso:

```sql
SELECT colunas FROM tabela1 WHERE EXISTS (SELECT colunas FROM tabela2 WHERE condição);
```

Exemplo prático:

```sql
SELECT nome FROM clientes WHERE EXISTS (SELECT * FROM pedidos WHERE pedidos.cliente_id = clientes.id);
```

Neste exemplo, estamos selecionando os nomes dos clientes que possuem pelo menos um pedido na tabela "pedidos".

### IN

O comando IN é usado para verificar se um valor corresponde a qualquer valor em uma lista ou subconsulta. Ele retorna verdadeiro se houver uma correspondência e falso caso contrário.

Exemplo de uso:

```sql
SELECT colunas FROM tabela WHERE coluna IN (valor1, valor2, ...);
```

Exemplo prático:

```sql
SELECT nome FROM produtos WHERE categoria IN ('Eletrônicos', 'Informática');
```

Neste exemplo, estamos selecionando os nomes dos produtos que pertencem às categorias 'Eletrônicos' ou 'Informática'.

### LIKE

O comando LIKE é usado para comparar um valor em uma coluna com um padrão especificado usando caracteres curinga. Ele permite que você realize pesquisas baseadas em padrões de texto.

Exemplo de uso:

```sql
SELECT colunas FROM tabela WHERE coluna LIKE padrão;
```

Exemplo prático:

```sql
SELECT nome FROM clientes WHERE telefone LIKE '55%';
```

Neste exemplo, estamos selecionando os nomes dos clientes cujo número de telefone começa com "55".

### BETWEEN

O comando BETWEEN é usado para verificar se um valor está dentro de um intervalo especificado. Ele permite que você verifique se um valor está entre dois limites, inclusivamente.

Exemplo de uso:

```sql
SELECT colunas FROM tabela WHERE coluna BETWEEN valor1 AND valor2;
```

Exemplo prático:

```sql
SELECT nome FROM produtos WHERE preco BETWEEN 10.00 AND 50.00;
```

Neste exemplo, estamos selecionando os nomes dos produtos que têm preço entre 10.00 e 50.00.

### DISTINCT

O comando DISTINCT é usado para retornar valores únicos em uma coluna de uma tabela. Ele elimina registros duplicados e retorna apenas uma ocorrência de cada valor distinto.

Exemplo de uso:

```sql
SELECT DISTINCT coluna FROM tabela;
```

Exemplo prático:

```sql
SELECT DISTINCT categoria FROM produtos;
```

Neste exemplo, estamos selecionando todas as categorias únicas da tabela "produtos".

### CASE

O comando CASE é usado para realizar avaliações condicionais em consultas SQL. Ele permite que você execute diferentes ações com base em condições especificadas.

Exemplo de uso:

```sql
SELECT coluna,
       CASE
           WHEN condição1 THEN resultado1
           WHEN condição2 THEN resultado2
           ELSE resultado_padrao
       END
FROM tabela;
```

Exemplo prático:

```sql
SELECT nome,
       CASE
           WHEN idade < 18 THEN 'Menor de idade'
           WHEN idade >= 18 AND idade < 60 THEN 'Adulto'
           ELSE 'Idoso'
       END
FROM clientes;
```

Neste exemplo, estamos selecionando o nome dos clientes e usando uma avaliação condicional CASE para determinar a faixa etária de cada cliente com base em sua idade.

### INNER JOIN

O comando INNER JOIN é usado para combinar registros de duas ou mais tabelas com base em uma condição de junção. Ele retorna apenas os registros que possuem correspondência em todas as tabelas envolvidas na junção.

Exemplo de uso:

```sql
SELECT colunas FROM tabela1 INNER JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

Exemplo prático:

```sql
SELECT pedidos.id, clientes.nome FROM pedidos INNER JOIN clientes ON pedidos.cliente_id = clientes.id;
```

Neste exemplo, estamos selecionando o ID dos pedidos e o nome dos clientes, combinando registros das tabelas "pedidos" e "clientes" com base na correspondência das colunas "cliente_id" em "pedidos" e "id" em "clientes".

### LEFT JOIN

O comando LEFT JOIN é usado para combinar todos os registros da tabela esquerda com os registros correspondentes da tabela direita com base em uma condição de junção. Ele retorna todos os registros da tabela esquerda e os registros correspondentes da tabela direita. Se não houver correspondência na tabela direita, ele retorna NULL para as colunas da tabela direita.

Exemplo de uso:

```sql
SELECT colunas FROM tabela1 LEFT JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

Exemplo prático:

```sql
SELECT clientes.nome, pedidos.id FROM clientes LEFT JOIN pedidos ON clientes.id = pedidos.cliente_id;
```

Neste exemplo, estamos selecionando o nome dos clientes e o ID dos pedidos, combinando todos os registros da tabela "clientes" com os registros correspondentes da tabela "pedidos" com base na correspondência das colunas "id" em "clientes" e "cliente_id" em "pedidos".

### RIGHT JOIN

O comando RIGHT JOIN é usado para combinar todos os registros da tabela direita com os registros correspondentes da tabela esquerda com base em uma condição de junção. Ele retorna todos os registros da tabela direita e os registros correspondentes da tabela esquerda. Se não houver correspondência na tabela esquerda, ele retorna NULL para as colunas da tabela esquerda.

Exemplo de uso:

```sql
SELECT colunas FROM tabela1 RIGHT JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

Exemplo prático:

```sql
SELECT pedidos.id, clientes.nome FROM pedidos RIGHT JOIN clientes ON pedidos.cliente_id = clientes.id;
```

Neste exemplo, estamos selecionando o ID dos pedidos e o nome dos clientes, combinando todos os registros da tabela "pedidos" com os registros correspondentes da tabela "clientes" com base na correspondência das colunas "cliente_id" em "pedidos" e "id" em "clientes".

### FULL OUTER JOIN

O comando FULL OUTER JOIN é usado para combinar todos os registros de ambas as tabelas, independentemente da correspondência. Ele retorna todos os registros da tabela esquerda e todos os registros da tabela direita, preenchendo com NULL quando não há correspondência.

Exemplo de uso:

```sql
SELECT colunas FROM tabela1 FULL OUTER JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

Exemplo prático:

```sql
SELECT clientes.nome, pedidos.id FROM clientes FULL OUTER JOIN pedidos ON clientes.id = pedidos.cliente_id;
```

Neste exemplo, estamos selecionando o nome dos clientes e o ID dos pedidos, combinando todos os registros das tabelas "clientes" e "pedidos" independentemente da correspondência entre as colunas "id" em "clientes" e "cliente_id" em "pedidos".

### GROUP BY ... WITH ROLLUP

O comando GROUP BY ... WITH ROLLUP é usado para gerar linhas adicionais que representam resumos de grupo, além dos grupos individuais. Ele permite que você obtenha totais parciais e totais gerais em uma única consulta.

Exemplo de uso:

```sql
SELECT coluna1, coluna2, SUM(coluna3) 
FROM tabela 
GROUP BY coluna1, coluna2 WITH ROLLUP;
```

Exemplo prático:

```sql
SELECT categoria, subcategoria, SUM(vendas) 
FROM produtos 
GROUP BY categoria, subcategoria WITH ROLLUP;
```

Neste exemplo, estamos selecionando a categoria e subcategoria dos produtos, juntamente com a soma das vendas, agrupando os resultados com base nas colunas "categoria" e "subcategoria" e gerando linhas adicionais com totais parciais e totais gerais.

Esses são apenas exemplos básicos dos comandos SQL fundamentais. O SQL oferece uma ampla variedade de recursos avançados, como junções de tabelas, agregações e subconsultas, que permitem consultas e manipulações mais complexas de dados em bancos de dados relacionais. À medida que você avança em sua jornada de aprendizado do MySQL, é altamente recomendável explorar mais sobre os comandos SQL e suas possibilidades. Consulte a documentação oficial do MySQL e outros recursos educacionais para obter exemplos mais detalhados e aprofundar seu conhecimento em SQL.
