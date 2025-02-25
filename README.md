# Team 602 Project Documentation
## High-Level Project Overview:
- What we're actually implementing
- Topics & Tasks
## Design Decisions:
### 1. CodeCoins
#### Introduction:
Users now have the ability to earn rewards for engaging with FakeStackOverflow!  These rewards come in the form of our proprietary currency - CodeCoins.  Each user will have a wallet that contains the amount of CodeCoins they currently hold.  Users can acquire CodeCoins in the following ways:
1. Upon signup, users will be granted a "starter pack" of 10 CodeCoins.
2. Every new day a user logs onto the website, they receive 1 CodeCoin.
3. When a user answers a question and it is edorsed as the correct answer by the question poster, that user will be gifted the bounty that was listed for that question.
4. Users can enter gambling rooms where they can bet an arbitrary amount of CodeCoins on a game of their choosing; a victory will see the pot returned to the winning user.
#### Design Choices:
`questionSchema = { bounty: number }`
`userSchema = { wallet: number }`
- When an answer is endorsed as the correct answer, the user who posted that answer will be paid the listed question bounty.
- When a user posts a question and therefore lists a bounty, they will see that bounty immediately deducted from their CodeCoins wallet.
- To post a question, a user must post a bounty of <i>at least</i> 1 CodeCoin.
- A user's wallet will be visible to all other users through their profile card.
#### API Endpoints:
Can utilize `GET /users/getUserByUsername/:username` route

### 2. Best Answer Model

Modify `Question` and `questionSchema` to include:
- `bestAnswerId`: ObjectId of the best answer (optional)

#### API Endpoints:
- `PATCH /questions/resolve/`: Set the best answer for a question
  - Body: { qid: string, answerId: string }

Add service methods:
- `resolveQuestion(questionId, answerId)`: Set the best answer for a question, and pay out bounty.

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
`GET /badges/getBadges/:username` --> returns a list of badges<br>

User Schema Updates:<br>
Need to add list of badges to user schema.<br>
badges: `[Badges]`


