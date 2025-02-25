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

Badge Schema:<br>
_id: ObjectID<br>
type: "VERIFIED" | "OTHER"<br>
price: number<br>

Badge Service:<br>
GET allows you to get badges given a user id<br>
PATCH for buying a badge<br> 
- implement something similar on the backend to biography logic
- excepr updateBadges gets called when purchasing a badhe
- only show VERIFIED next to username, but in UserCard, show all badges 

BadgeProgress schema:<br>
badge: Badge<br>
unlocked: bool<br>
progress: String<br>

Endpoints:<br>
/badges/getBadges/:username --> returns a list of badges<br>

User Schema Updates:<br>
Need to add list of badges to user schema.<br>
badges: `[Badges]`


