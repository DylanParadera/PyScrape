# PyScrape

A lightweight and flexible data extraction tool that can scrape web pages (HTML) or extract data from API responses (JSON).

## Features
- Supports both HTML and JSON extraction
- Customisable mapping structure for dynamic data extraction
- REST API for easy integration
- Lightweight and efficient with Flask and BeautifulSoup

## Example Requests

### HTML Scraping:
Request:
```json
{
  "url": "https://example.com",
  "type": "html",
  "collection": true,
  "mapping": {
    "base": ".content-wrapper > .item",
    "data": {
      "title": {
        "action": "filter",
        "query": "h1",
        "next": {
          "action": "text"
        }
      }
    }
  }
}
```
Response:
```json
[
  { "title": "Example title 1" },
  { "title": "Example title 2" },
  { "title": "Example title 3" },
  { "title": "Example title 4" }
]
```

### JSON API Extraction:
Request:
```json
{
  "url": "https://api.example.com/data",
  "type": "json",
  "collection": false,
  "mapping": {
    "base": "data",
    "data": {
      "title": "title"
    }
  }
}
```
Response:
```json
{
  "title": "Item Title"
}
```

## License

MIT License.
