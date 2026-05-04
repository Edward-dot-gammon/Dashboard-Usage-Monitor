# Dashboard Usage Monitor

This repository holds the Tableau workbook **Dashboard Usage Monitor 2.0** (`Dashboard Usage Monitor 2.0.twb`). The dashboard answers a simple question for owners and stewards of published dashboards: **for a chosen Tableau workbook, who could use it, who actually used it, and how engagement looks over time?**

## What you should take away from the dashboard

1. **Reach of permissions** — **Permitted Users** is the count of distinct people (by employee ID) who have permission to the selected workbook. That is the upper bound of who *could* open the content, independent of whether they have viewed it recently.

2. **Actual usage** — **Total Views** counts view events (rows with a recorded view time and user). **Unique Viewers** is the count of distinct people (by display name) who generated those views in the filtered period. Together, these show whether the audience is a small set of heavy users or a broader group.

3. **Engagement pattern** — The **Trend Panel** (titled *Unique Viewers / Month*) plots how many distinct viewers appeared each calendar month. Use it to see growth, seasonality, or drop-off after launches or process changes.

4. **Who is in the tail** — The **Permitted User Data Table** lists individuals (name, title, job function, OBU) with **Total Views**, **No of Days Visited** (how many different calendar days they viewed), and **Last View** (most recent activity in Hong Kong time). Rows are sorted with higher total views toward the top so active users are easy to spot.

## How to slice the story

- **Dashboards** — Parameter (labeled *Dashboards* on the layout) that selects which **workbook** the whole dashboard is scoped to. Some workbooks use friendlier display names in the control than the underlying Tableau name.

- **Date Period** — Limits view history and related metrics to the dates you care about (aligned to **Hong Kong time**: view timestamps from the source are shifted by +8 hours for “Created At HK” / **Create HK date**).

- **Job Function** and **OBU** — Optional breakdown filters so you can focus usage within a role or operating unit.

## Data it relies on

The workbook uses the published Tableau data source **User Dashboard Permission & History view**, which combines Tableau permission and usage history with employee attributes (for example name, title, job function, OBU). Exact refresh cadence and field definitions are governed by that data source on your Tableau Server or Cloud site.

## Files in this repo

| File | Role |
|------|------|
| `Dashboard Usage Monitor 2.0.twb` | Tableau workbook (XML). Open in Tableau Desktop or publish to Tableau Server / Cloud. |

If the data source connection or site path changes after publishing, reconnect the workbook to the same logical model your environment provides for dashboard usage and permissions.

<img width="797" height="451" alt="image" src="https://github.com/user-attachments/assets/90b65f71-7aeb-41fc-942c-e8fdfcf112f9" />

