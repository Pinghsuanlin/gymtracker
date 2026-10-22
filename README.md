# Gym log

A phone-friendly workout tracker. This repository holds only the app; all logs and photos live in the private `gym-log` repository and are read and written through a GitHub access token stored on each phone.

App link (after GitHub Pages is on): https://pinghsuanlin.github.io/gymtracker/

## Setup (once)

1. **Fill the private data repository.** Open `gym-log` on GitHub → **Add file → Upload files** → drag in everything from the `gym-log` folder (`routines`, `logs`, `body`, `images`, `README.md`) → **Commit changes**.
2. **Fill this repository.** Open `gymtracker` → **Add file → Upload files** → drag in `index.html`, `manifest.webmanifest`, `icon-180.png`, `icon-512.png`, `README.md` → **Commit changes**.
3. **Turn on GitHub Pages.** In `gymtracker`: **Settings → Pages** → under *Build and deployment*, Source: **Deploy from a branch**, Branch: **main**, folder **/ (root)** → **Save**. After 1–2 minutes the app is live at the link above.
4. **Create an access token.** On GitHub: your profile picture → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
   - Token name: `gym log – phone 1`
   - Expiration: 1 year (GitHub reminds you before it expires)
   - Repository access: **Only select repositories** → `gym-log`
   - Permissions → Repository permissions → **Contents: Read and write**
   - **Generate token** and copy it right away (GitHub shows it only once).
5. **Connect your phone.** Open the app link in Safari → paste the token → choose **User 1** → **Connect and sync**. Then tap **Share → Add to Home Screen** so it opens like an app.
6. **Second person.** Repeat step 4 with the name `gym log – phone 2`, open the link on their phone, paste that token and choose **User 2**. Each phone has its own token, so you can remove one without affecting the other.

## Good to know

- **If a phone is lost:** delete its token on GitHub (step 4's page). The logs stay safe.
- **No signal at the gym:** workouts are kept on the phone and upload automatically next time it's online.
- **Forgot to log a day:** open that workout and change **Workout date** at the top to the day you trained. It's saved under that date, and "Last time" compares with the session before it.
- **Saving part-way:** saving twice on the same day stays one session. Reopen the workout to see the sets already saved; new sets continue the numbering.
- **Extra exercises:** in a workout, tap **+ Add warm-up or extra** (top) or **+ Add exercise** (bottom). Pick a quick warm-up, an exercise from another day, or a new one. Tick *Keep it in this routine* to have it there next time.
- **Weight on bodyweight moves:** each set has a selector: *Bodyweight* or *+2.5 / +5 / … kg*. The options can be changed per exercise in **Edit routines**.
- **Photo and tips:** tap an exercise's picture for a large photo, how to do it, and avoid-injury tips. Tips can be edited per exercise in **Edit routines**.
- **Progress:** sessions per week, upper vs lower sets, cardio minutes, weights over time and body weight, with written insights. Tick *Compare with …* to see the other user alongside.
- **Names:** Settings → Names. Both phones show the same names; the log files keep their `user1` / `user2` names, so past workouts are never affected.
- **Changing exercises:** use **Edit routines** in the app, or edit `routines/user1.json` in `gym-log` directly.
- **Weights:** each exercise lists the weights your gym actually has (for example `20, 25, 30`). The app only ever suggests those.
