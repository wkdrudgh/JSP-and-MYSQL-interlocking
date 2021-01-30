MYSQL연동 및 테스트
=======

외부 라이브러리
-----------
1. mysql-connector-java-5.1.47.jar<br/>
> jdbc드라이버, 데이터베이스 접속을 위해 사용

MYSQL 연동 클래스 만들기
----------
````````JAVA
package util;

import java.sql.Connection;
import java.sql.DriverManager;

public class DatabaseUtil {
	public static Connection getConnection() {
		try {
			String dbURL = "jdbc:mysql://localhost:3306/TUTORIAL?serverTimezone=Asia/Seoul";
			String dbID = "root";
			String dbPassword = "oracle";
			// 클래스를 가지고 와서 사용한다는 의미
			Class.forName("com.mysql.cj.jdbc.Driver");
			return DriverManager.getConnection(dbURL, dbID, dbPassword);
		}catch(Exception e) {
			e.printStackTrace();
		}
		return null;
	}
}

```````
