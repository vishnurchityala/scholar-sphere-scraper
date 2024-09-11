

# Scrapy Project: ACM & IEEE Spider

This project contains two Scrapy spiders that scrape research papers, titles, authors, abstracts, and citation counts from the **IEEE Xplore** and **ACM Digital Library** websites.

## Project Description

The **ACM & IEEE Spiders** are designed to scrape research paper metadata from their respective digital libraries. Both spiders handle dynamic content using `scrapy-splash` to ensure proper loading of JavaScript-rendered pages.

### Spider Capabilities:
- Scrapes research paper titles, links, abstracts, citation counts, and author details.
- Handles JavaScript-rendered content using Splash.

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
   ```

2. **Install the Dependencies**
   Install Scrapy and the necessary libraries:
   ```bash
   pip install scrapy scrapy-splash
   ```

3. **Install Splash**
   Install Docker from [here](https://docs.docker.com/get-docker/) and run Splash to handle JavaScript rendering:
   ```bash
   docker run -p 8050:8050 scrapinghub/splash
   ```

4. **Ensure Splash is Running**
   Ensure Splash is running in Docker:
   ```bash
   docker run -p 8050:8050 scrapinghub/splash
   ```

### Spiders Overview

#### `ieee_spider`
- **Description**: The IEEE spider scrapes research papers from IEEE Xplore. It extracts information like the paper title, link, abstract, citation count, and authors.
- **Command**: 
   ```bash
   scrapy crawl ieee_spider -a search_term="Your Search Term" -o results.json
   ```

#### `acm_spider`
- **Description**: The ACM spider scrapes research papers from ACM Digital Library. It extracts information like the paper title, link, abstract, citation count, and authors.
- **Command**:
   ```bash
   scrapy crawl acm_spider -a search_term="Your Search Term" -o results.json
   ```

## Example Output

After running the spiders, the output will be stored in a resule.json. Here’s an example structure:

```json
{
  "title": "Example Research Paper Title",
  "link": "https://example.com",
  "details":"Example details of publication",
  "abstract": "This is a sample abstract.",
  "authors": ["Author One", "Author Two"],
  "citation_count": 120
}
```
