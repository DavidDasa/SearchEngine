

# Search Engine

This is a search engine project that crawls websites, indexes the content in Elasticsearch, and enables searching through the crawled pages.

## Features

- Website crawling with adjustable depth and other parameters
- Redis used to track crawl status and track visited URLs
- Kafka handles distributing crawl requests 
- Elasticsearch indexes page content
- Search UI allows searching through indexed pages

## Architecture

The main components are:

- **Crawler Service** - Crawls websites and publishes pages to Kafka
- **Kafka** - Distributes crawl requests and pages for indexing
- **Elasticsearch** - Indexes page content for searching 
- **Web UI** - Allows configuring and monitoring crawls, and searching through indexed pages

## Getting Started

### Prerequisites

- Java 8
- Docker and Docker Compose

### Running

```
docker-compose up
```

This will start Kafka, Elasticsearch, and the Crawler Service.

The Web UI will be available at http://localhost:8080.

From there you can create a new crawl by entering a seed URL.

After crawling, the pages will be indexed in Elasticsearch. Use the Search tab in the UI to search through pages.

## Configuration

The main configuration is in the `application.properties` file. This allows configuring the Kafka and Elasticsearch servers.

Crawler parameters can be set on a per-crawl basis via the API.

## Contributing

Pull requests are welcome! Let me know if you encounter any bugs or have ideas for improvements.

## License

This project is MIT licensed. See [LICENSE](LICENSE).
