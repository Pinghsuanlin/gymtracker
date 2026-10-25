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

- **Runs:** log distance, time (minutes or mm:ss) and, optionally, average heart rate; pace and speed are worked out as you type. Each run day shows how to run it for your current stage, and "Done as planned" logs the planned time in one tap. History and Progress show pace (lower is faster) and kilometres per week.
- **Time or reps:** timed exercises such as mountain climbers or jumping jacks have a Time | Reps switch; your choice is remembered per exercise.
- **Charts** have grid lines with round values; tap any dot or bar to see its value. Scales never zoom into tiny ranges, so small wobbles look small.
- **Balance** (Progress): average sets per week over the last 4 weeks for upper body, lower body and core, against your plan, with a one-line verdict. Strength shows your 3 most-logged lifts first; the rest are under *Show all lifts*.

- **Fast for years:** new workouts go into one file per year (`logs/<user>/2026.csv`); the original `logs/<user>.csv` stays and is still read. Saving only touches this year's file, and syncing only downloads files that changed, so speed stays the same however much history you keep. The offline copy is kept in the browser's IndexedDB storage, which has plenty of room. Open the app from its Home Screen icon so the phone keeps that copy.

- **If a phone is lost:** delete its token on GitHub (step 4's page). The logs stay safe.
- **No signal at the gym:** workouts are kept on the phone and upload automatically next time it's online.
- **Stages:** weeks 1–6 Foundation, 7–12 Build, 13–15 Sharpen, then Maintain in alternating 6-week blocks (goal: lean and fit). The home screen shows the week and stage; when a new stage starts, tap **Update my routine** (your old routine is backed up in `gym-log/routines/`). Set the plan's start date in **Settings → Plan**.
- **Lighter weeks:** suggested only when it's been 5+ weeks *and* there are at least 2 signs of fatigue (stalled lifts, dropping reps, workouts that felt hard, notes about soreness or tiredness; after 8+ weeks one sign is enough). During a lighter week workouts show half the sets at about 80% of the weight.
- **How did it feel?** tap Easy / OK / Hard / Exhausted before saving a workout; it helps spot fatigue.
- **One-tap sets:** tap ✓ on a set to log the planned weight and reps; tap again to undo. Type a number only if you did something different.
- **Fix a mistake:** History → **Edit** (or **Edit** next to *Saved today*) to change or delete logged sets; Body check-in → **Edit** for check-ins. Changes rewrite the CSV, and GitHub keeps every earlier version.
- **Token expiry:** enter the token's expiry date in Settings (GitHub shows it next to the token). The app reminds you 2 weeks before and explains how to renew.
- **Forgot to log a day:** open that workout and change **Workout date** at the top to the day you trained. It's saved under that date, and "Last time" compares with the session before it.
- **Saving part-way:** saving twice on the same day stays one session. Reopen the workout to see the sets already saved; new sets continue the numbering.
- **Logging weights:** machines and cables: the number on the weight stack (not the machine's own weight). Plate-loaded machines: only the plates you add. Dumbbells: one dumbbell's weight (5 kg in each hand = 5). Barbells: bar plus plates. Bodyweight moves: only any added weight. Log the same way on the same machine; numbers on different machines aren't comparable.
- **Extra exercises:** in a workout, tap **+ Add warm-up or extra** (top) or **+ Add exercise** (bottom). Pick a quick warm-up (elliptical, stair climber, bike, rowing machine, treadmill, jog, jump rope, band warm-up or mobility), search about 40 built-in exercises plus your own plan in English or 中文, or add a new one. Tick *Keep it in this routine* to have it there next time.
- **Weight on bodyweight moves:** each set has a selector: *Bodyweight* or *+2.5 / +5 / … kg*. The options can be changed per exercise in **Edit routines**.
- **Photo and tips:** tap an exercise's picture for a large photo, how to do it, and avoid-injury tips. Tips can be edited per exercise in **Edit routines**.
- **Progress:** plan adherence, week streak, a training calendar, personal records, estimated max strength (1RM) per lift, upper vs lower sets and weight lifted, cardio minutes and a smoothed body-weight trend, with written insights. Tick *Compare with …* to see the other user alongside.
- **Body check-in:** weight, body fat %, waist, hips and thigh. Add sex, birth year and height under *Your profile* to see BMI (Taiwan's cut-offs), the healthy body-fat range for your age, waist checks and your weekly trend. The profile is saved in `gym-log/profile/`.
- **Names:** Settings → Names. Both phones show the same names; the log files keep their `user1` / `user2` names, so past workouts are never affected.
- **Changing exercises:** use **Edit routines** in the app, or edit `routines/user1.json` in `gym-log` directly.
- **Weights:** each exercise lists the weights your gym actually has (for example `20, 25, 30`). The app only ever suggests those.
