## Exemplos Práticos de Interação com o MySQL em Diferentes Linguagens de Programação

A interação com o MySQL em diferentes linguagens de programação é facilitada pelo uso de bibliotecas e drivers específicos. Aqui estão alguns exemplos práticos que demonstram como interagir com o MySQL em várias linguagens de programação:

### Python

```python
import mysql.connector

# Conectar ao banco de dados
conn = mysql.connector.connect(
    host="localhost",
    user="usuario",
    password="senha",
    database="nome_do_banco"
)

# Criar um cursor para executar comandos SQL
cursor = conn.cursor()

# Executar uma consulta
cursor.execute("SELECT * FROM tabela")

# Recuperar os resultados
results = cursor.fetchall()

# Exibir os resultados
for row in results:
    print(row)

# Fechar a conexão
cursor.close()
conn.close()
```

### Java

```java
import java.sql.*;

public class Main {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/nome_do_banco";
        String user = "usuario";
        String password = "senha";

        try {
            // Registrar o driver JDBC
            Class.forName("com.mysql.jdbc.Driver");

            // Conectar ao banco de dados
            Connection conn = DriverManager.getConnection(url, user, password);

            // Criar uma instrução SQL
            Statement stmt = conn.createStatement();

            // Executar uma consulta
            ResultSet rs = stmt.executeQuery("SELECT * FROM tabela");

            // Exibir os resultados
            while (rs.next()) {
                System.out.println(rs.getString("coluna"));
            }

            // Fechar os recursos
            rs.close();
            stmt.close();
            conn.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

### PHP

```php
<?php
$servername = "localhost";
$username = "usuario";
$password = "senha";
$dbname = "nome_do_banco";

// Criar uma conexão
$conn = new mysqli($servername, $username, $password, $dbname);

// Verificar a conexão
if ($conn->connect_error) {
    die("Falha na conexão: " . $conn->connect_error);
}

// Executar uma consulta
$sql = "SELECT * FROM tabela";
$result = $conn->query($sql);

// Exibir os resultados
if ($result->num_rows > 0) {
    while ($row = $result->fetch_assoc()) {
        echo $row["coluna"] . "<br>";
    }
} else {
    echo "0 resultados";
}

// Fechar a conexão
$conn->close();
?>
```

Esses são apenas exemplos básicos de como interagir com o MySQL em algumas linguagens de programação populares. Lembre-se de que cada linguagem pode ter sua própria biblioteca ou driver específico para o MySQL, portanto, consulte a documentação oficial correspondente para obter mais detalhes e exemplos completos.
