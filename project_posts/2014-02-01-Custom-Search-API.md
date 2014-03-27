## Custom Search API

Google Custom Search enables you to create a search engine for your website, your blog, or a collection of websites. You can configure your search engine to search both web pages and images. You can fine-tune the ranking, customize the look and feel of the search results.

The Custom Search API has a number of features available but we are going to use only one that is searching across the web for a specific collection of images. The images are going to be store locally and there are going to be process to the main aplication.

The Custom Search API with JSON / Atom lets you develop applications to retrive and disply results forn the Google Custom Search programmatically. With this we can search the web and retrive images in a JSON like format and save the images locally.

To create a search is necesarie to create a Custom Search Engine which provies a 100 search queries per day for free. This is only to obtain the API key from the Seatch Engine and use it to create queries in Google Cloud Console.

Once having that done is fearly easy to create custom searches. Th searches can ge obtain using a HTTP GET Request in a URL. Using this reques the output is JSON format.

```html
https://developers.google.com/custom-search/json-api/v1/using_rest
```







Source Custom Search  https://developers.google.com/custom-search/docs/overview
