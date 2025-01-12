---
type: monthly-review
year: <% tp.date.now("YYYY") %>
month: <% tp.date.now("MMMM") %>
---
<%*
let folder = `Daily Notes/${tp.date.now("YYYY")}/${tp.date.now("MMMM")}`;
let fileName = `${tp.date.now("YYYY-MM")} Monthly Review`;

// Create the necessary folders if they don't exist
await app.vault.createFolder(folder).catch(() => { /* Folder already exists */ });

// Move the current file to the desired location
await tp.file.move(folder + "/" + fileName);
%>
---
created: <% tp.file.creation_date("YYYY-MM-DD HH:mm") %>
type: monthly-review
year: <% tp.date.now("YYYY") %>

---
# Monthly Wellness Review: <% tp.date.now("MMMM YYYY") %>

## ✨ Monthly Highlights
*What moments stood out this month?*


## 📈 What Went Well
*Celebrate your achievements and positive experiences:*
1. 
2. 
3. 


## 🤔 What Didn't Go As Planned
*Reflect on challenges and learning opportunities:*
1. 
2. 
3. 


## 🌟 Wellness Pillar Review

### ⚡ Energy
```dataview
TABLE energy as "Energy Level"
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
SORT date DESC
```

### 🧠 Mind
```dataview
TABLE mood as "Daily Mood"
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
SORT date DESC
```

### 🏃‍♂️ Movement
```dataview
TABLE movement as "Movement Type"
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
SORT date DESC
```

### 🥗 Nourishment
```dataview
TABLE nourishment
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
SORT date DESC
```

### 🤝 Connection
```dataview
TABLE connection as "Social Connections"
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
SORT date DESC
```

### 😌 Rest
```dataview
TABLE rest_activity as "Rest Activities"
FROM "<% tp.date.now("YYYY") %>/<% tp.date.now("MMMM") %>"
WHERE type = "daily-wellness"
SORT date DESC
```

## 🎯 Next Month's Intentions
*Set your focus for the coming month:*
1. 
2. 
3.