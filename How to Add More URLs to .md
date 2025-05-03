# How to Add More URLs to `urls.yaml`

The `urls.yaml` file contains the list of websites (`jobs`) that `urlwatch` will monitor. It uses the YAML format, which is human-readable.

## File Structure

*   Each website you want to monitor is defined as a separate block (a "job").
*   Each job block starts with basic information like `name` (a descriptive name for the job) and `url` (the website address).
*   Jobs are separated from each other by a line containing only three hyphens: `---`.

## Current File (`urls.yaml`)

Currently, your `urls.yaml` file looks like this:

```yaml
---
name: "VervLife Careers Page"
url: "https://vervlife.talosats-careers.com/join-us?what=&where=&iso=gb&radius=30#vacancies-section-filters"
# Add more jobs below, separated by '---
```

## Adding a New URL

To monitor another website, simply add a new block below the existing one, making sure to separate them with `---`.

**Example:** Let's say you also want to monitor `https://example.com/another-page`.
You would edit `urls.yaml` to look like this:

```yaml
---
name: "VervLife Careers Page"
url: "https://vervlife.talosats-careers.com/join-us?what=&where=&iso=gb&radius=30#vacancies-section-filters"

---
name: "Another Example Page"
url: "https://example.com/another-page"
# Add more jobs below, separated by '---
```

**Key Points:**

1.  **Separator:** Always use `---` on its own line between jobs.
2.  **Indentation:** YAML is sensitive to indentation, but for simple `name` and `url` keys, just ensure they start at the same level (usually no indentation needed right after the `---`).
3.  **Keys:** Each job needs at least a `url`. A `name` is highly recommended for clarity.
4.  **Save:** After editing the file in your GitHub repository, commit and push the changes. The GitHub Action will automatically pick up the updated list on its next scheduled run.

There are many more advanced options (like filtering specific parts of a page), which you can explore in the [urlwatch documentation](https://urlwatch.readthedocs.io/) if needed.
