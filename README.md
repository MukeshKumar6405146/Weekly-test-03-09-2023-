# Weekly-test-03-09-2023-
Fetching data from an API using JAVA
# -------------Flow of the Project----------------------

* ### first import these libraries
```
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
```

* ### Define the api URL and create URL object
  ```
   String apiUrl = "https://api.nationalize.io/?name=nathaniel";
   URL url = new URL(apiUrl);
  ```
* ### Open a connection to the URL and get response code
```
  HttpURLConnection connection = (HttpURLConnection) url.openConnection();
  connection.setRequestMethod("GET");
  int responseCode = connection.getResponseCode();
```

* ### Read the response Data
```
BufferedReader in = new BufferedReader(new InputStreamReader(connection.getInputStream()));
                String inputLine;
                StringBuilder response = new StringBuilder();

                while ((inputLine = in.readLine()) != null) {
                    response.append(inputLine);
                }
                in.close();
```
* ### Parse the JSON response
```
String jsonResponse = response.toString();
System.out.println(jsonResponse);

```
