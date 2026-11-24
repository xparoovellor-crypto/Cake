# Cake EXPO live setup (project: cake-expo)

The Firebase config is already filled in index.html. Do these once in the Firebase console (console.firebase.google.com -> project "cake-expo"):

1. Build -> Authentication -> Get started -> Sign-in method: enable **Anonymous** and **Email/Password** (Google is no longer needed).
2. Authentication -> Users -> Add user: email **rabiaparbin7860@gmail.com** + a strong password of your choice. (If your owner email is different, tell me / change OWNER_EMAIL in index.html and the email in firestore.rules.)
3. Build -> Firestore Database -> Create database (production mode, any region).
4. Firestore -> Rules tab -> paste the contents of firestore.rules -> Publish.
5. Deploy this folder on Netlify (app.netlify.com/drop). Photos are stored inside Firestore, so Firebase Storage is NOT needed.
6. Authentication -> Settings -> Authorized domains -> Add your Netlify domain (e.g. cakeexpo.netlify.app).

## Testing
- Owner: menu (three lines) -> Owner login with the email/password from step 2. The status bar must say "Online".
- Customer on another phone: open the Netlify link in Chrome/Safari (not inside Instagram/WhatsApp), fill the sign-in form (name, email, phone, address, PIN), order a cake. The owner dashboard shows it within seconds.

## Troubleshooting
- "DEMO MODE": Firebase did not load (check internet / ad-blocker) or you deployed an old copy.
- "Database error: permission-denied": Firestore rules not published, or the owner email in the rules differs from the owner user you created.
- "Sign-in problem: auth/admin-restricted-operation" or "auth/operation-not-allowed": Anonymous sign-in is not enabled (step 1).
- Customers: a customer's account lives in the browser they used. Clearing browser data starts a fresh account.
