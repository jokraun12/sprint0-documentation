# Team 602 Project Documentation
## High-Level Project Overview:
- What we're actually implementing
- Topics & Tasks
## Design Decisions:
### 1. CodeCoins
### 2. Best Answer Model



### 3. Betting System
### 4. Notification System
### 5. Introduction of New Game
### 6. Leaderboard Implementation
### 7. Badge Shop

Badge Schema:
_id: ObjectID
type: "VERIFIED" | "OTHER"
price: number

Badge Service:
GET allows you to get badges given a user id
PATCH for buying a badge 
- implement something similar on the backend to biography logic
- excepr updateBadges gets called when purchasing a badhe
- only show VERIFIED next to username, but in UserCard, show all badges 

BadgeProgress schema:
badge: Badge
unlocked: bool
progress: String 

Endpoints:
/badges/getBadges/:username --> returns a list of badges 

User Schema Updates:
Need to add list of badges to user schema.
badges: `[Badges]`


