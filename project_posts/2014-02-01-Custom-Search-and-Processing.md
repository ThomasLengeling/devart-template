Google Custom Search lets you search the web programmatically via HTTP and giving a JSON output.
We are going to use processing and some external java libraries. Java provides with a set of libraries that lets you connect to a HTTP protocol fairly easy.

Import the java library, for network comunication, exeption handelling and input/output files.

```java
import java.net.*;
import java.net.MalformedURLException;
import java.net.URISyntaxException;
import java.io.Reader.*;
```

The information from the search is beeing saved in class called GResults, more about the class check the gitHub link.

```java
void Search()  throws MalformedURLException, URISyntaxException, IOException {

  String key = "";
  String qry = "nebulas"; 
  String cx  = "";
  String fileType = "png,jpg";
  String searchType = "image";

  URL url = new URL ("https://www.googleapis.com/customsearch/v1?key=" +key+ "&cx=" +cx+ "&q=" +qry+"&fileType="+fileType+"&searchType="+searchType+"&alt=json");

  HttpURLConnection conn = (HttpURLConnection) url.openConnection();
  conn.setRequestMethod("GET");
  conn.setRequestProperty("Accept", "application/json");
  BufferedReader br = new BufferedReader(new InputStreamReader ( ( conn.getInputStream() ) ) );
  GResults results = new Gson().fromJson(br, GResults.class);

  conn.disconnect();
}
```
To parse the JSON obtain from the search Google to java objects, there is a open source java library called GSon just for doing that. More about Gson [here](https://code.google.com/p/google-gson/)  

and to get results we just simple interate the GResults class like this

```java
  for (int i=0; i < 10; i++) {
    String path  = results.getLink(i)
  }
```

