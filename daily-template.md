---
created: <% tp.file.creation_date() %>
type: daily-wellness
date: <% tp.date.now("YYYY-MM-DD") %>
year: <% tp.date.now("YYYY") %>
month: <% tp.date.now("MMMM") %>
energy: 
sleep_hours: 
rest_activity: 
movement: 
mood: 
nourishment: 
connection: 
gratitude: 
weekday: <% tp.date.now("dddd") %>
---
<%*
let folder = `Daily Notes/${tp.date.now("YYYY")}/${tp.date.now("MMMM")}`;

// Create the necessary folders if they don't exist
await app.vault.createFolder(folder).catch(() => { /* Folder already exists */ });

// Move the current file to the desired location
await tp.file.move(folder + "/" + tp.file.title);
%>

# 🌅 Morning Reflection

## ☀️  Daily Intentions
1. [ ] 
2. [ ] 
3. [ ] 

## 🔋 Energy Level
Select your energy level:
- [ ] 5 - Energized and vibrant ^energy-5
- [ ] 4 - Alert and focused      ^energy-4
- [ ] 3 - Balanced and steady    ^energy-3
- [ ] 2 - Somewhat tired ^energy-2
- [ ] 1 - Depleted              ^energy-1

## 😴 Sleep Quality
Hours slept: __ ^sleep-hours

Sleep notes: 

## ☮️ Restful Moment
Today I will rest by: ^rest-activity
- [ ] Meditation
- [ ] Deep breathing
- [ ] Reading
- [ ] Nature time
- [ ] Other: 

## 🏃 Movement
Today I will move through: ^movement
- [ ] Walking
- [ ] Yoga
- [ ] Stretching
- [ ] Exercise
- [ ] Other: 

## 😊 Morning Mood
Select your current mood: ^mood
- [ ] 😄 Joyful - Feeling great!
- [ ] 😊 Content - Pretty good
- [ ] 😐 Neutral - Ok
- [ ] 😕 Down - Not great
- [ ] 😔 Struggling - Need support

---

# 🌙 Evening Reflection

## 🥤 Nourishment
Rate your wellness (1-5):
Physical: [nourishment_physical:: ]
Mental: [nourishment_mental:: ]
Emotional: [nourishment_emotional:: ]

What made you feel good today?
- Physical:
- Mental:
- Emotional:

## 🤗 Connection
Quality of connections today: [connection_quality:: ] *(1-5)*
Number of meaningful interactions: [connection_count:: ]

Moments of connection and kindness:
- 
- 

## ✍️ Journal
Overall mood: [journal_mood:: ] *(1-5)*
*Reflections on today:*

## 🙏 Daily Gratitude
Number of gratitudes: [gratitude_count:: ]
1. 
2. 
3. 

---

## 📊 Recent Wellness Trends
```dataview
TABLE 
    energy as "Energy",
    sleep_hours as "Sleep",
    mood as "Mood"
FROM "Daily Notes"
WHERE type = "daily-wellness"
SORT date DESC
LIMIT 7
```