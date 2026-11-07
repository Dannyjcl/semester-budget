# semester-budget
A simple semester budget designed for college students

# How it works
This is a simple html with local storage to keep their data saved as they revisit the application on different occasions. 

# Planned upgrades 
I will upgrade using Firebase to make put this onto a cloud database. 


## Cloud sync (Firebase)

Tap **Sign in to sync** (bottom right) and sign in with Google. Your budget is mirrored to Firestore at `users/{uid}/apps/budget` and stays in sync live across every device. It still works offline, and edits upload when you're back online.

- `cloud-sync.js` is the shared sync module, also used by the [TimeBudget planner](https://dannyjcl.github.io/weekly-planner/). Both apps are on `dannyjcl.github.io`, so one sign-in covers both.
- Each app publishes a small `summary`. The budget screen shows this week's free hours and today's tasks from the planner, and the planner shows this month's budget.
- `firestore.rules` holds the security rules: each user can only read and write their own data.
