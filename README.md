# www.botreck.com

+ togomat.com

## Scenario

+ imacro

## Tools

+ pologos


## Using Cheerio and Axios for Web Scraping

The basic workflow is simple:

+ Axios to make an HTTP request to a web page
+ Cheerio to parse the HTML document and extract the data you need

Here's an example of how to use Cheerio and Axios together to extract the titles of the top posts on the Hacker News homepage:


```js
const axios = require('axios')
const cheerio = require('cheerio');

const url = 'https://news.ycombinator.com/';
axios.get(url)
  .then(response => {
    const $ = cheerio.load(response.data);
    const titles = [];
    $('.titleline > a').each((index, element) => {
      titles.push($(element).text());
    });
    console.log(titles);
  })
  .catch(error => {
    console.error(error);
  });;
```


This code sends a GET request to the Hacker News homepage and then uses Cheerio to extract the text content of all the .titleline elements on the page. It then logs the titles to the console.

As you can see, using Cheerio and Axios together is a powerful way to extract data from web pages. By combining the fast and efficient parsing capabilities of Cheerio with the simple and intuitive API of Axios, you can quickly and easily scrape data from any website.
Tips for Successful Web Scraping



