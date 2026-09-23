<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/AgentScraper/.github/main/profile/assets/github-profile-banner-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/AgentScraper/.github/main/profile/assets/github-profile-banner-light.png">
  <img alt="AgentScraper" src="https://raw.githubusercontent.com/AgentScraper/.github/main/profile/assets/github-profile-banner-light.png" width="1280">
</picture>

## Web data your agents can use.

**Turn public websites into readable content, structured records, and useful inputs for your applications.**

Start with a URL. Read a page, crawl related pages, or extract the fields you need. Keep the source with the result, inspect what completed, and put the data to work in your own tools.

**[Try AgentScraper](https://agentscraper-preview-20260919.vercel.app) · [Read the Docs](https://agentscraper-preview-20260919.vercel.app/docs) · [Docs for agents](https://agentscraper-preview-20260919.vercel.app/llms.txt) · [Talk to us](https://agentscraper-preview-20260919.vercel.app/contact)**

### Start with the output you need

| You need | Use AgentScraper to |
| --- | --- |
| Content for an agent or knowledge base | Read pages as Markdown, plain text, or HTML, with their source URLs and links. |
| A collection of related pages | Crawl a site within an explicit page budget and inspect each page's outcome. |
| Records with specific fields | Extract named fields with CSS selectors, or use prompts and JSON Schema with a configured AI extraction engine. |
| Content that loads with JavaScript | Request browser rendering when a static page does not contain the information you need. |

### What will you build?

The Docs explore web-data workflows for developers, researchers, and business teams. Use the extraction API as the collection layer for projects like these:

- **Agent knowledge and RAG:** turn documentation, support articles, and product pages into source-linked material for retrieval and answers.
- **Commerce data:** collect product names, variants, displayed prices, currencies, and availability from selected pages.
- **SaaS research:** compare published plans and features while preserving billing periods, usage limits, and undisclosed prices.
- **Company and supplier research:** organize published capabilities, products, and operating locations with the pages that support them.
- **Hiring and location data:** collect advertised roles, skills, branch details, opening hours, or menus from a defined source list.
- **Research collections:** bring relevant pages into a consistent format for your own analysis, with source material available for review.

Start with a small sample. Check whether the output answers your question before expanding the collection.

### Keep the context with the content

A price belongs to a variant and currency. A company claim needs its source. A missing value should stay unknown.

Page results retain requested and final URLs, extracted content, and warnings. Saved jobs let you inspect completed pages and individual failures without submitting the collection again. Page budgets and visible usage help you control the work; idempotent submissions let your application retry an uncertain request without creating another job.

### Make your first API request

Create an account and an API key. Store the key in your server-side `AGENTSCRAPER_API_KEY` environment variable, then submit a page through the current REST API:

```bash
curl --fail-with-body \
  --request POST "https://api.agentscraper.harshith.com/v1/scrape" \
  --header "Authorization: Bearer $AGENTSCRAPER_API_KEY" \
  --header "Content-Type: application/json" \
  --header "Idempotency-Key: my-first-page" \
  --data '{"url":"https://example.com","selectors":{"title":"h1"}}'
```

Keep the returned `job.id`. Check `GET /v1/jobs/{job_id}` for completion, then use the finished results and review any page failures. Reuse the same idempotency key for a retry of the same request; use a new key for new work.

Use ordinary HTTP from JavaScript, Python, an automation, or your agent's tool layer. The [API documentation](https://agentscraper-preview-20260919.vercel.app/docs) explains requests, results, authentication, and credits.

### Building with an agent?

Give it the [compact documentation index](https://agentscraper-preview-20260919.vercel.app/llms.txt), your source URLs, the fields you need, and a page budget. It can read the relevant API guidance before preparing a request and keep the source context alongside its answer.

**Have a business workflow in mind?** Bring a sample source and the output you need. [Talk to us](https://agentscraper-preview-20260919.vercel.app/contact) about how web data fits your application or decision.

---

**On GitHub:** our public [brand repository](https://github.com/AgentScraper/brand) contains the official logos, artwork, and [usage guidelines](https://github.com/AgentScraper/brand/blob/main/GUIDELINES.md). The application source is maintained privately within this organization.

<sub>AgentScraper is currently in developer beta.</sub>
