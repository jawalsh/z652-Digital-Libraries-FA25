# 🌐 Week 8 Activity — Exploring APIs and Parameters

---

## 🧩 What You’ll Learn
In this activity, you’ll:
1. Send API requests in your browser and terminal.  
2. Change parameters to see how they affect results.  
3. Record observations about how APIs deliver structured data.

---

## 🔍 Quick Refresher: What’s an API?
An **API** (Application Programming Interface) lets one program request information or perform an action on another system.

When you use a **web API**, you:
- send a request to a **URL**,
- include **parameters** that specify what you want,
- receive a structured **response** (usually in JSON format).

Example:

```
https://api.open-meteo.com/v1/forecast
  ?latitude=39.1653
  &longitude=-86.5264
  &hourly=temperature_2m
```

| Part | Meaning |
|------|----------|
| Base URL | `https://api.open-meteo.com/v1/forecast` (the main API endpoint) |
| Query Parameters | `latitude`, `longitude`, `hourly` (control the output) |
| Response | JSON data showing forecast values |

---

## 1️⃣ Wikipedia API (Path Parameters)

**Base:** `https://en.wikipedia.org/api/rest_v1/page/summary/`

Try these URLs in your browser or with `curl`:

| Version | URL | What Changed? | What Did You Notice? |
|----------|-----|----------------|----------------------|
| Original | https://en.wikipedia.org/api/rest_v1/page/summary/International_Image_Interoperability_Framework |  |  |
| Variation 1 | https://en.wikipedia.org/api/rest_v1/page/summary/Albert_Camus | Changed article name |  |
| Variation 2 | https://en.wikipedia.org/api/rest_v1/page/html/Albert_Camus | Changed endpoint from “summary” to “html” |  |
| Variation 3 | https://en.wikipedia.org/api/rest_v1/page/summary/ThisArticleDoesNotExist | Invalid title |  |

**Reflection:**  
- How does the *path parameter* (part of the URL path) define what you get?  
- What happens if you change the endpoint?

---

## 2️⃣ Open-Meteo API (Query Parameters)

**Base:** `https://api.open-meteo.com/v1/forecast`

Try each variation and observe the differences:

| Version | URL | Parameters Added or Changed | Result or Observation |
|----------|-----|------------------------------|-----------------------|
| Original | https://api.open-meteo.com/v1/forecast?latitude=39.1653&longitude=-86.5264&hourly=temperature_2m | baseline |  |
| Variation 1 | https://api.open-meteo.com/v1/forecast?latitude=39.1653&longitude=-86.5264&hourly=temperature_2m,relative_humidity_2m | add second variable |  |
| Variation 2 | https://api.open-meteo.com/v1/forecast?latitude=48.8566&longitude=2.3522&hourly=temperature_2m | change location to Paris |  |
| Variation 3 | https://api.open-meteo.com/v1/forecast?latitude=39.1653&longitude=-86.5264&hourly=temperature_2m&timezone=America/New_York | add timezone |  |

**Reflection:**  
- Which parameters control *what* vs *where* vs *how* results appear?  
- How could this be useful in your own digital projects?

---

## 3️⃣ GitHub API (Pagination Parameters)

**Base:** `https://api.github.com/repos/UniversalViewer/universalviewer/releases`

| Version | URL | Parameter(s) | What Changed? |
|----------|-----|--------------|----------------|
| Original | https://api.github.com/repos/UniversalViewer/universalviewer/releases?per_page=3 | `per_page=3` |  |
| Variation 1 | https://api.github.com/repos/UniversalViewer/universalviewer/releases?per_page=5 | `per_page=5` |  |
| Variation 2 | https://api.github.com/repos/UniversalViewer/universalviewer/releases?per_page=3&page=2 | add `page=2` |  |
| Variation 3 | https://api.github.com/repos/IIIF/api/releases?per_page=3 | change repository |  |

**Reflection:**  
- How do `per_page` and `page` control how much data you see?  
- What stays constant (the endpoint)? What changes (the parameters)?

---

## 4️⃣ JSONPlaceholder (Path, Query, and Body Parameters)

**Base:** `https://jsonplaceholder.typicode.com/todos`

| Version | Method | Example | Parameter Type | Observation |
|----------|---------|----------|----------------|-------------|
| GET single record | Browser | https://jsonplaceholder.typicode.com/todos/1 | path |  |
| Filtered list | Browser | https://jsonplaceholder.typicode.com/todos?userId=2 | query |  |
| POST new record | Terminal | `curl -s -X POST https://jsonplaceholder.typicode.com/posts -H "Content-Type: application/json" -d '{"title":"hello api","body":"this is a demo","userId":1}'` | body |  |

**Reflection:**  
- How does a query parameter differ from a path parameter?  
- Which method (GET or POST) *reads* data vs *creates* data?

---
## 5️⃣ NASA Astronomy Picture of the Day (JSON vs XML Formats)

**Base:** `https://api.nasa.gov/planetary/apod`

This API returns information about NASA’s “Astronomy Picture of the Day.”  
It’s free to use for small-scale demos — just include the public key `api_key=DEMO_KEY`.

---

### Step 1 — Try It in Your Browser

| Version | URL | Parameters Used | What You Notice |
|----------|-----|-----------------|-----------------|
| JSON (default) | https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY | `api_key=DEMO_KEY` |  |
| XML format | https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&format=xml | add `format=xml` |  |
| JSON for a specific date | https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=2020-01-01 | add `date=2020-01-01` |  |
| XML for a specific date | https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&format=xml&date=2020-01-01 | add `format=xml` + `date=2020-01-01` |  |

---

### Step 2 — Try It in the Terminal (Optional)

```
# JSON (default)
curl -s "https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY"

# XML version
curl -s "https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&format=xml"

# Specific date (e.g., Jan 1, 2020)
curl -s "https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&format=xml&date=2020-01-01"
```

---

### Step 3 — Observe and Compare

| Format | What Does the Data Look Like? | How Are Fields Marked? |
|---------|-------------------------------|------------------------|
| JSON | `{ "title": "...", "date": "...", "url": "..." }` | key:value pairs |
| XML | `<title>...</title>` | nested tags |

---

### Reflection

1. Which format (JSON or XML) is easier for you to read as a human?  
2. Which format might be easier for a computer to parse? Why?  
3. Why might digital libraries or archives offer *both* formats?  
   (Hint: legacy systems and metadata standards often use XML.)  
4. What parameter controls the format of the response?  
5. How could a project like **IIIF** or **CollectionBuilder** make use of an API that supports multiple formats?

---

✅ **Goal:** Recognize that APIs can offer **the same content in multiple data formats** through parameters.  
You’ve now seen JSON (structured for JavaScript and modern apps) and XML (widely used for metadata and archival interchange).
---

## 6️⃣ Library of Congress Digital Collections API (Library/Archive Example)

**Base:** `https://www.loc.gov/`

The Library of Congress exposes its collections and metadata through a public API—no key required!

---

### Step 1 — Try It in Your Browser

| Version | URL | Parameters Used | What You Notice |
|----------|-----|-----------------|-----------------|
| JSON (default) | https://www.loc.gov/collections/?q=comic+books&fo=json | `q=comic+books`, `fo=json` |  |
| XML | https://www.loc.gov/collections/?q=comic+books&fo=xml | change `fo` to `xml` |  |
| Limit results | https://www.loc.gov/collections/?q=comic+books&fo=json&c=3 | add `c=3` |  |
| Filter to photographs | https://www.loc.gov/collections/?q=indiana&fa=original-format:photograph&fo=json | add `fa=original-format:photograph` |  |

---

### Step 2 — Try It in the Terminal (Optional)

```
# JSON response
curl -s "https://www.loc.gov/collections/?q=comic+books&fo=json"

# XML response
curl -s "https://www.loc.gov/collections/?q=comic+books&fo=xml"
```

---

### Step 3 — Observe and Compare

| Format | What Does the Data Look Like? | How Are Fields Marked? |
|---------|-------------------------------|------------------------|
| JSON | `"title": "..."`, `"date": "..."` | key:value pairs |
| XML | `<title>...</title>` | nested tags |

---

### Reflection

1. What parameter changes the format of the response?  
2. How are search terms and filters expressed in the URL?  
3. What kinds of metadata fields appear in the results (title, date, subject)?  
4. How could this API support a digital exhibit or research collection?  
5. How is this similar to IIIF in allowing machine-to-machine access?

---

✅ **Goal:** See how a *real library API* exposes collection metadata in both JSON and XML—perfect for connecting technical skills to digital-library practice.

---
## 🧠 Wrap-Up Questions

1. What is a **parameter** in the context of an API request?  
2. How does changing parameter **values** affect the data you receive?  
3. Which APIs you tried today could support your **own digital collections or research projects** (e.g., IIIF, weather, Wikipedia)?  
4. Why do digital library tools like **IIIF** rely on well-structured APIs?

---
<!--
### ✅ Deliverable
Complete the observation tables and submit your filled-in worksheet (as Markdown, text, or PDF).
-->