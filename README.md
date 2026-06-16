[Espn Sports Scraper](https://apify.com/fortuitous_pirate/espn-sports-scraper?fpr=data)

# ESPN Sports Data API Scraper

## Overview

Extract comprehensive sports data from ESPN's hidden API. Get live scores, standings, schedules, team rosters, and game summaries for NFL, NBA, MLB, NHL, College Football, College Basketball, and Soccer (Premier League, La Liga, MLS, etc. ).

## Features

- Search by keywords to find specific results
- Filter results by category or type
- Export data in JSON, CSV, or Excel formats

## Use Cases

- **Track** - Track entertainment listings and reviews
- **Build** - Build media databases for content analysis
- **Monitor** - Monitor entertainment industry trends and ratings
- **Aggregate** - Aggregate entertainment data for recommendation engines

## Input Parameters

| Parameter | Type | Description | Default |
| --- | --- | --- | --- |
| `dataType` | string **(required)** | Type of data to scrape | `scoreboard` |
| `sport` | string **(required)** | Sport category | `football` |
| `league` | string **(required)** | League to scrape. For soccer, use league codes like 'eng.1' (Premier League),... | `nfl` |
| `startDate` | string | Start date for scores/schedule (YYYYMMDD format, e.g., 20250115) |  |
| `endDate` | string | End date for date range queries (YYYYMMDD format). If only startDate is provi... |  |
| `teamId` | string | ESPN team ID for team-specific data (roster, schedule). Find IDs by first scr... |  |
| `eventId` | string | ESPN event ID for game summary/box score data |  |
| `season` | integer | Season year (e.g., 2025). Defaults to current season. | `2025` |
| `seasonType` | string | 1=Preseason, 2=Regular Season, 3=Postseason, 4=Offseason | `2` |
| `limit` | integer | Maximum number of results to return | `100` |

## Output Example

Each result contains structured data like this:

```
{
  "type": "Standard",
  "eventId": "ABC-12345",
  "name": "ESPN Sports Data API Sample Item",
  "date": "2025-01-15",
  "status": "Active",
  "homeTeam": "Sample homeTeam",
  "awayTeam": "Sample awayTeam",
  "venue": "Convention Center",
  "sport": "Sample sport",
  "league": "Sample league"
}
```

## Pricing

This actor uses pay-per-result pricing:

- **$0.002** per result
- **$2.00** per 1,000 results

No monthly fees. You only pay for what you scrape. [Apify Free plan](https://apify.com/pricing) includes $5/month in platform credits.

## How to Run

### Apify Console

1. Go to the [ESPN Sports Data API Scraper](https://apify.com/fortuitous_pirate/espn-sports-scraper) actor page
2. Configure your input parameters
3. Click **Start** and wait for the results
4. Download data in JSON, CSV, or Excel format

### API

```
curl -X POST "https://api.apify.com/v2/acts/fortuitous_pirate~espn-sports-scraper/runs?token=YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"maxItems": 10}'
```

### Python SDK

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")
run = client.actor("fortuitous_pirate/espn-sports-scraper").call(
    run_input={"maxItems": 10}
)

for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Integration

Connect ESPN Sports Data API Scraper with your existing tools and workflows:

- **API access** - Programmatic access via [Apify API](https://docs.apify.com/api/v2)
- **Webhooks** - Get notified when scraping completes
- **Scheduling** - Set up recurring runs on any schedule
- **Zapier / Make** - Connect with 5,000+ apps via [Apify integrations](https://apify.com/integrations)
- **Python / Node.js SDKs** - Native client libraries for easy integration