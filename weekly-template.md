<%* let folder = `Daily Notes/${tp.date.now("YYYY")}/${tp.date.now("MMMM")}`; await tp.file.move(folder + "/Week of " + tp.date.weekday("YYYY-MM-DD", 0)) _%>
---
created: <% tp.file.creation_date("YYYY-MM-DD HH:mm") %>
type: weekly-review
week_start: <% tp.date.weekday("YYYY-MM-DD", 0) %>
year: <% tp.date.now("YYYY") %>
month: <% tp.date.now("MMMM") %>
---

# Weekly Wellness Review: Week of <% tp.date.weekday("YYYY-MM-DD", 0) %> 


## 🤔 Thoughts and Feelings
*Reflect on your emotional landscape this week:*


## 🌟 Wellness Pillars

### Best Pillar This Week
Select which area you felt strongest in:
- [ ] ⚡ Energy
- [ ] 🧠 Mind
- [ ] 🏃‍♂️ Movement
- [ ] 🥗 Nourishment
- [ ] 🤝 Connection
- [ ] 😌 Rest

### Pillar Check-In

#### ⚡ Energy Analysis

**Daily Energy Levels:**
```dataview
TABLE WITHOUT ID
    date as "Date",
    choice(energy = 5, "⚡⚡⚡⚡⚡",
    choice(energy = 4, "⚡⚡⚡⚡",
    choice(energy = 3, "⚡⚡⚡",
    choice(energy = 2, "⚡⚡",
    choice(energy = 1, "⚡", ""))))) as "Energy Level",
    choice(energy = 5, "Energized",
    choice(energy = 4, "Alert",
    choice(energy = 3, "Balanced",
    choice(energy = 2, "Tired",
    choice(energy = 1, "Depleted", ""))))) as "Status"
FROM "Daily Notes"
WHERE type = "daily-wellness"
AND file.day >= date(this.week_start) 
AND file.day < date(this.week_start) + dur(7 days)
SORT date ASC
```

**Energy by Day of Week:**
```dataview
TABLE WITHOUT ID
    weekday as "Day",
    round(average(energy), 1) as "Average Energy",
    length(rows) as "# of Entries"
FROM "Daily Notes"
WHERE type = "daily-wellness"
AND file.day >= date(this.week_start) 
AND file.day < date(this.week_start) + dur(7 days)
GROUP BY weekday
SORT weekday asc
```

**Energy Distribution:**
```dataview
LIST WITHOUT ID
length(rows) + " days at energy level " + energy + " (" + 
    choice(energy = 5, "Energized",
    choice(energy = 4, "Alert",
    choice(energy = 3, "Balanced",
    choice(energy = 2, "Tired",
    choice(energy = 1, "Depleted", ""))))) + ")"
FROM "Daily Notes"
WHERE type = "daily-wellness"
AND file.day >= date(this.week_start) 
AND file.day < date(this.week_start) + dur(7 days)
GROUP BY energy
SORT energy DESC
```

#### 🧠 Mind
Areas for improvement:
```dataview
TABLE mood
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
WHERE date >= date("<% tp.date.weekday("YYYY-MM-DD", 0) %>") AND date <= date("<% tp.date.weekday("YYYY-MM-DD", 6) %>")
SORT date ASC
```

#### 🏃‍♂️ Movement
Areas for improvement:
```dataview
TABLE movement
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
WHERE date >= date("<% tp.date.weekday("YYYY-MM-DD", 0) %>") AND date <= date("<% tp.date.weekday("YYYY-MM-DD", 6) %>")
SORT date ASC
```

#### 🥗 Nourishment
Areas for improvement:
```dataview
TABLE nourishment
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
WHERE date >= date("<% tp.date.weekday("YYYY-MM-DD", 0) %>") AND date <= date("<% tp.date.weekday("YYYY-MM-DD", 6) %>")
SORT date ASC
```

#### 🤝 Connection
Areas for improvement:
```dataview
TABLE connection
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
WHERE date >= date("<% tp.date.weekday("YYYY-MM-DD", 0) %>") AND date <= date("<% tp.date.weekday("YYYY-MM-DD", 6) %>")
SORT date ASC
```

#### 😌 Rest
Areas for improvement:
```dataview
TABLE rest_activity
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
WHERE date >= date("<% tp.date.weekday("YYYY-MM-DD", 0) %>") AND date <= date("<% tp.date.weekday("YYYY-MM-DD", 6) %>")
SORT date ASC
```

## 👀 Looking Forward
*What would you like to focus on next week?*
