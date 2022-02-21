# Backend Technical Test

Write a REST API with a simple CRUD that mainly contains users and their events. 

## Code usage example 

```javascript
const { getUserById } = require('models/user.js')

const user = getUserById(1) // 1 is the user id
const nearestEvent = user.getNearestEvent() // nearest event contains the (event type, the event date, the user id)
```

The user's events should be compared and calculated according to multiple criteria; for example, a user can have a joining anniversary event (that should be triggered each year starting from his inscription date). 

The user can meet on DD/MM/YYYY and be notified x days before/after this meet. 

We can assign different events to a user; the nearest one should be calculated using the set of the linked events. 

### Event types examples: 
- Inscription
- Start of the subscription offer
- End of the subscription offer

### Events example: 
- **2** days __after__ inscription offer
- **5** days __after__ the start of subscription offer
- **3** days __before__ the end of the subscription offer
- **4** days __after__ the end of the subscription offer

## Requirements
- The work should be implemented using Javascript; you can use some frameworks/microframeworks like expressjs). 
- The database should be PostgreSQL, MySQL, or SQLite. 
- The work should contain at least unit tests. 
- Adding a new **event types/events** should be as easy as possible. 

## Bonus
- A generic cache, where we can choose the provider (Memcached, Redis, files...) with just a one-line configuration for the usage. 
- The cache should be revalidated automatically if the result has a chance. 

## Deliverability
- The code should be delivered as a working REST API.
- The code should be delivered as a Git repository with an incremental set of meaningful commits and not only one. 
- Will be judged: the quality of the code, the quality of commits, the quality of the documentation (in and outside of code), capacity in asking for help, and the elegance of the solution.
- The point is not for you to figure things out from scratch if you have never done something similar. Feel free to ask for pointers and help when stuck.
- Bonus (not needed): deployed version of the app.