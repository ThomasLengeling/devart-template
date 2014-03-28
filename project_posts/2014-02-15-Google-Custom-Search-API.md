## Custom Search API

Google Custom Search enables you to create a search engine for your website, your blog, or a collection of websites. You can configure your search engine to search both web pages and images. You can fine-tune the ranking, customize the look and feel of the search results.

The Custom Search API has a number of features available but we are going to use only one that is searching across the web for a specific collection of images. The images are going to be store locally and there are going to be process to the main application.

The Custom Search API with JSON / Atom lets you develop applications to retrieve and display results forn the Google Custom Search programmatically. With this we can search the web and retrieve images in a JSON like format and save the images locally.

To create a search is necessary creating a Custom Search Engine. The engine provides 100 search queries per day for free. This is only to obtain the API key from the Search Engine and use it to create queries in Google Cloud Console.

Once having that done is fairly easy to create custom searches. The searches can be obtain using a HTTP GET Request with a URL. The output of the request is JSON format.

```html
https://www.googleapis.com/customsearch/v1?parameters
```
To make a search you only need three parameters that can be obtained from the  Custom Search Engine and the Google Cloud Console

- Searh Engine ID (cx)
- A Public API access from the cloud Console (key)
- Something to Search (q)

A web search for “Picasso” would look like something like this

```html
https://www.googleapis.com/customsearch/v1?key="YOUR_KEY"&cx="ENGINE_API"&q="picasso&alt=json
```

More information about all the query parameters 

https://developers.google.com/custom-search/json-api/v1/using_rest

So we want to search only Images with file type .jpg and .png we need the following code.

```html
https://www.googleapis.com/customsearch/v1?key="YOUR_KEY"&cx="ENGINE_API"&q="picasso"&searchType="image"&fileType="png,jpg"&alt=json
```
Source Custom Search  https://developers.google.com/custom-search/docs/overview
