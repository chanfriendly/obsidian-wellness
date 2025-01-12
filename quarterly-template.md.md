---
type: quarterly-review
year: <% tp.date.now("YYYY") %>
quarter: <% Math.floor((Number(tp.date.now("MM")) - 1) / 3) + 1 %>
---

# Quarterly Wellness Review: Q<% Math.floor((Number(tp.date.now("MM")) - 1) / 3) + 1 %> <% tp.date.now("YYYY") %>

## 🎯 Wellness Priorities
*What are your top 3 wellness priorities for next quarter?*

1. 
2. 
3. 

## 🎨 360 Wellness Wheel

![[wellness-wheel.svg]]

### Rate Each Pillar (1-10)

#### ⚡ Energy
Rating: 
- [ ] 10 [ ] 9 [ ] 8 [ ] 7 [ ] 6 [ ] 5 [ ] 4 [ ] 3 [ ] 2 [ ] 1
*Why this rating?*

#### 🧠 Mind
Rating: 
- [ ] 10 [ ] 9 [ ] 8 [ ] 7 [ ] 6 [ ] 5 [ ] 4 [ ] 3 [ ] 2 [ ] 1
*Why this rating?*

#### 🏃‍♂️ Movement
Rating: 
- [ ] 10 [ ] 9 [ ] 8 [ ] 7 [ ] 6 [ ] 5 [ ] 4 [ ] 3 [ ] 2 [ ] 1
*Why this rating?*

#### 🥗 Nourishment
Rating: 
- [ ] 10 [ ] 9 [ ] 8 [ ] 7 [ ] 6 [ ] 5 [ ] 4 [ ] 3 [ ] 2 [ ] 1
*Why this rating?*

#### 🤝 Connection
Rating: 
- [ ] 10 [ ] 9 [ ] 8 [ ] 7 [ ] 6 [ ] 5 [ ] 4 [ ] 3 [ ] 2 [ ] 1
*Why this rating?*

#### 😌 Rest
Rating: 
- [ ] 10 [ ] 9 [ ] 8 [ ] 7 [ ] 6 [ ] 5 [ ] 4 [ ] 3 [ ] 2 [ ] 1
*Why this rating?*

## 📊 Quarterly Overview
```dataview
TABLE 
    round(avg(energy),1) as "Avg Energy",
    round(avg(sleep_hours),1) as "Avg Sleep",
    count(movement) as "Movement Days",
    count(connection) as "Connection Days",
    count(rest_activity) as "Rest Days"
FROM "<% tp.date.now("YYYY") %>"
WHERE type = "daily-wellness"
GROUP BY month
SORT date DESC
LIMIT 3
```

## 🔄 Reflection & Planning
*What patterns do you notice in your wellness journey? What would you like to focus on next quarter?*