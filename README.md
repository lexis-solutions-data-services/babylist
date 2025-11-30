# Babylist Scraper

![Babylist Scraper](https://i.ibb.co/MXvG7Ry/babylist-cover.png)

## 1. Introduction

This Apify actor scrapes product data from Babylist’s online store. It supports scraping of:

<p align="center">
  <img src="https://apify-image-uploads-prod.s3.us-east-1.amazonaws.com/DevbkY3adMTBuoECt-actor-VLHYs7ZtLvv4dJmsJ-mOZ1mxeY36-images-6.jpeg" alt="Babylist.com Scraper" style="height: 60px; margin-right: 15px;" /><a href="https://apify.com/lexis-solutions/babylist" target="_blank">
    <img src="https://img.shields.io/badge/Try%20it%20on-Apify-0066FF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDA4IiBoZWlnaHQ9IjQwOCIgdmlld0JveD0iMCAwIDQwOCA0MDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGNsaXAtcGF0aD0idXJsKCNjbGlwMF8zNDFfNDE1NykiPgo8cGF0aCBkPSJNMjE4LjY5NSAxMDRIMzAwLjk3QzMwMi42NDMgMTA0IDMwNCAxMDUuMzU3IDMwNCAxMDcuMDNWMjMyLjc2NkMzMDQgMjM1Ljc3OCAzMDAuMDgzIDIzNi45NDUgMjk4LjQzNCAyMzQuNDI1TDIxNi4xNTkgMTA4LjY5QzIxNC44NDEgMTA2LjY3NCAyMTYuMjg3IDEwNCAyMTguNjk1IDEwNFoiIGZpbGw9IndoaXRlIi8+CjxwYXRoIGQ9Ik0xODkuMzA1IDEwNEgxMDcuMDNDMTA1LjM1NyAxMDQgMTA0IDEwNS4zNTcgMTA0IDEwNy4wM1YyMzIuNzY2QzEwNCAyMzUuNzc4IDEwNy45MTcgMjM2Ljk0NSAxMDkuNTY2IDIzNC40MjVMMTkxLjg0IDEwOC42OUMxOTMuMTU5IDEwNi42NzQgMTkxLjcxMyAxMDQgMTg5LjMwNSAxMDRaIiBmaWxsPSJ3aGl0ZSIvPgo8cGF0aCBkPSJNMjAyLjU5MSAyMDQuNjY4TDEwOS4xMjcgMjk4LjgzNUMxMDcuMjI5IDMwMC43NDcgMTA4LjU4MyAzMDQgMTExLjI3OCAzMDRIMjk2LjhDMjk5LjQ4MyAzMDQgMzAwLjg0MiAzMDAuNzcgMjk4Ljk2NyAyOTguODUyTDIwNi45MDggMjA0LjY4NUMyMDUuNzI2IDIwMy40NzUgMjAzLjc4MiAyMDMuNDY4IDIwMi41OTEgMjA0LjY2OFoiIGZpbGw9IndoaXRlIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMzQxXzQxNTciPgo8cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwNCAxMDQpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==&logoColor=white" alt="Try it on Apify" style="border-radius: 12px; height: 60px;" />
  </a>
</p>


- **Search pages** (e.g. keyword-based results)
- **Category pages** (e.g. category-based products)
- **Product detail pages** (individual pages)


## 📊 Actor Stats

| Stat | Value |
|------|-------|
| **Version** | `0.1.2` |
| **Total Runs** | 123 |
| **Total Users** | 4 |
| **Stats Date** | Nov 30, 2025 |

---


## 2. Key Features

- Extracts full product metadata: IDs, names, slugs, breadcrumbs, ratings, reviews, brand info, and SEO details.
- Captures rich media: images (multiple sizes) and videos (if available).
- Gathers detailed descriptions, specifications, highlights, summaries, and callouts.
- Retrieves pricing information, sale attributes, and eligibility details.
- Supports configurable limits (`maxItems`) and optional proxy usage.

## 3. Why This Actor Is Important

Babylist.com is a leading baby registry and e-commerce platform. Automating data collection enables:

- **Market research** on trending baby products
- **Price monitoring** and sale tracking
- **Competitive analysis** for brands and retailers
- **Content aggregation** for parenting blogs and newsletters

## 4. Who This Actor Is Suitable For

- **E-commerce analysts** tracking product performance and pricing
- **Market researchers** studying baby-care trends
- **Developers** building product comparison or recommendation engines
- **Content creators** gathering up-to-date product details

## 5. Input Schema

```json
{
  "startUrls": [
    // search page
    {
      "url": "https://www.babylist.com/store/search?order=asc&search_term=baby"
    },
    // category page
    {
      "url": "https://www.babylist.com/store/top-registered"
    },
    // page detail
    {
      "url": "https://www.babylist.com/gp/babylist-glass-bottle-box/46229/1857318"
    }
  ],
  "query": "baby",
  "category": "top-registered",
  "maxItems": 10,
  "proxyConfiguration": {
    "useApifyProxy": true
  }
}
```

## 6. Output Schema

```json
{
  "id": 46229,
  "category_breadcrumbs": [
    { "title": "Home", "url_slug": "" },
    { "title": "Newborn Must-Haves", "url_slug": "newborn-must-haves" },
    { "title": "Nursing & Feeding", "url_slug": "feeding" },
    { "title": "Breastfeeding", "url_slug": "pumping" },
    { "title": "Bottle Feeding", "url_slug": "bottle-feeding" },
    { "title": "Bottles", "url_slug": "bottles" }
  ],
  "slug": "babylist-glass-bottle-box",
  "name": "Babylist Glass Bottle Box",
  "short_name": "Glass Bottle Box",
  "image": {
    "url": "https://images.ctfassets.net/.../glass-bottle-box-v2_noBG.png?fl=progressive&fm=jpg&bg=rgb:f9f9f9&w=620&h=620",
    "thumbnail_url": "https://images.ctfassets.net/.../glass-bottle-box-v2_noBG.png?fl=progressive&fm=jpg&bg=rgb:f9f9f9&w=210&h=210"
  },
  "videos": [],
  "attributes": {},
  "product_attribute_map": {},
  "active_product_id": 1857318,
  "pdp_type": "product",
  "rating": 4.8,
  "review_count": 38,
  "brand": "Babylist",
  "brand_id": 873,
  "brand_page_url": "https://www.babylist.com/store/b/babylist/873",
  "seo_url": "https://www.babylist.com/gp/babylist-glass-bottle-box/46229/1857318",
  "seo_title": "Babylist Glass Bottle Box | Babylist Shop",
  "show_babylist_health_cta": false,
  "babylist_health_cta_product_type": null,
  "categories": [
    { "title": "Newborn Must-Haves", "url_slug": "newborn-must-haves" },
    { "title": "Nursing & Feeding", "url_slug": "feeding" },
    { "title": "Breastfeeding", "url_slug": "pumping" },
    { "title": "Bottles", "url_slug": "bottles" }
  ],
  "callouts": [],
  "details": {
    "url": "https://www.babylist.com/p/46229/description",
    "description": "<p>Every baby is different. Some babies will take to any bottle...</p>",
    "specs": "<p><strong>Dr. Brown’s Options+ Glass Narrow Baby Bottles</strong></p><ul>...</ul>",
    "highlight": "A bundle of popular glass baby bottles that lets new parents try out different ones to see which works best for them—before buying a whole set.",
    "summary": "<ul><li>11.5” x 8.5” x 3”</li><li>4 glass baby bottles...</li></ul>",
    "overview": null
  },
  "fsa_hsa_eligible": false,
  "price": { "msrp": 57.84, "current": 42.99 },
  "price_details": {
    "list_price": { "price": "42.99" },
    "msrp": { "price": "57.84" },
    "sale_attributes": {
      "sale_percent_off": { "percent_int": 26 },
      "sale_type": "everyday_selling_price",
      "sale_types": ["everyday_selling_price"]
    }
  },
  "similar_products": [],
  "same_brand_products": [],
  "reviews": [],
  "related_assortments": null,
  "product_info": {
    "id": 1857318,
    "created_at": "2024-01-05T15:44:04.000Z",
    "...": "..."
  },
  "primary_image_url": "https://images.ctfassets.net/.../glass-bottle-box-v2_noBG.png?fl=progressive&fm=jpg&bg=rgb:f9f9f9&w=1240&h=1240",
  "price_value": 42.99
}
```

---

👀 p.s.

Got feedback or need an extension?

Lexis Solutions is a [certified Apify Partner](https://apify.com/partners/find). We can help you with custom solutions or data extraction projects.

Contact us over [Email](mailto:scraping@lexis.solutions) or [LinkedIn](https://www.linkedin.com/company/lexis-solutions)

## Support Our Work 💝

If you're happy with our work and scrapers, you're welcome to leave us a company review [here](https://apify.com/partners/find/lexis-solutions/review) and leave a review for the scrapers you're subscribed to. It will take you less than a minute but it will mean a lot to us!

Image Credit: https://www.babylist.com/
