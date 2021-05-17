# API Automation Framework

## HTTP URL Connection
HttpUrlConnection is a built-in Java class which provides a way of performing HTTP requests in Java. The HttpUrlConnection class allows us to perform basic
HTTP requests without the use of any additional libraries. All the classes that we need are part of the java.net package. 

### Sample Usage

1. Creating a request
The HttpUrlConnection class is used for all types of requests by setting the requestMethod attribute to one of the values: GET, POST, HEAD, OPTIONS, PUT, DELETE, TRACE.
```
  URL url = new URL("http://example.com");
  HttpURLConnection con = (HttpURLConnection) url.openConnection();
  con.setRequestMethod("GET");
```

2. Setting Request Headers
Adding headers to a request can be achieved by using the setRequestProperty() method:
```
  con.setRequestProperty("Content-Type", "application/json");
```

3. Reading the Response
Reading the response of the request can be done by parsing the InputStream of the HttpUrlConnection instance.
```
  BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
  String inputLine; 
  StringBuffer content = new StringBuffer();
  while ((inputLine = in.readLine()) != null) {
    content.append(inputLine);
  }
  in.close();
```
Reference: 
Refer to the `src/test/java/com/apitest/httpurlconnection/helper/ApiHelper.java` class for creating HTTP requests using HttpURLConnection

## Rest Assured
