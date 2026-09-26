# News Article Search Engine

A search engine over **~150,000 New York Times articles**, built as a Master's group project
(UC Riverside — Information Retrieval and Web Search).

**Pipeline:** Crawl → Scrape → Store (JSON) → Index (Lucene + Hadoop MapReduce, MongoDB) →
Search (Spring Boot REST API + AngularJS web app)

## What it does
- Crawls the New York Times and scrapes ~150,000 articles into structured JSON documents (Python, BeautifulSoup).
- Builds an inverted index two ways: a from-scratch Java implementation and Apache Lucene. At scale, a Hadoop MapReduce job builds the index in parallel.
- Stores corpus/index data in MongoDB.
- Serves ranked search results through a Spring Boot REST API and an AngularJS front end.

## Repository structure
| Module | Location | What it does |
| --- | --- | --- |
| Crawler | `Crawler/` | Discovers article URLs to scrape |
| Scraper + scripts | `Crawler/`, `scripts/` | Extracts article text with BeautifulSoup → JSON |
| Inverted index (from scratch) | `Inverted Index Java/` | Hand-built Java inverted index |
| Lucene indexing/search | `Lucene/` | Apache Lucene index + queries |
| MapReduce indexing | `MapReduce/` | Hadoop MapReduce job for distributed indexing |
| REST API | `RestApi/lucene/` | Spring Boot API over the Lucene index |
| Web app | `webapp-SE/` | AngularJS search front end |

## Tech stack
Python · BeautifulSoup · Java · Apache Lucene · Hadoop MapReduce · MongoDB · Spring Boot · AngularJS · JSON
