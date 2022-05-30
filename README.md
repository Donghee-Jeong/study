# study

## PostgreSQL 연결
```java
import javax.xml.transform.Result;
import java.sql.*;

public class Postgresql {
    public static void main(String[] args) throws ClassNotFoundException{
        Class.forName("org.postgresql.Driver");

        String url = "jdbc:postgresql://localhost:5432/postgres";
        String user = "postgres";
        String password = "password";

        try {
            Connection conn = DriverManager.getConnection(url, user, password);
            Statement stmt = conn.createStatement();
            ResultSet rs = stmt.executeQuery("select * from testtable");

            while(rs.next()){
                System.out.println(rs.getString("id"));
            }

            rs.close();
            stmt.close();
            conn.close();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}

```
