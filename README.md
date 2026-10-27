# Gym log

A phone-friendly workout tracker. This repository holds only the app; all logs and photos live in the private `gym-log` repository and are read and written through a GitHub access token stored on each phone.

App link (after GitHub Pages is on): [https://pinghsuanlin.github.io/gymtracker/](https://pinghsuanlin.github.io/gymtracker/)

## Setup (once)

1. **Fill the private data repository.** Open `gym-log` on GitHub → **Add file → Upload files** → drag in everything from the `gym-log` folder (`routines`, `logs`, `body`, `images`, `library.json`, `README.md`) → **Commit changes**.
2. **Fill this repository.** Open `gymtracker` → **Add file → Upload files** → drag in `index.html`, `manifest.webmanifest`, `icon-180.png`, `icon-512.png`, `README.md` → **Commit changes**.
3. **Turn on GitHub Pages.** In `gymtracker`: **Settings → Pages** → Source: **Deploy from a branch**, Branch: **main**, folder **/ (root)** → **Save**. After 1–2 minutes the app is live at the link above.
4. **Create an access token.** On GitHub: your profile picture → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
   - Token name: `gym log – phone 1`
   - Expiration: 1 year
   - Repository access: **Only select repositories** → `gym-log`
   - Permissions → Repository permissions → **Contents: Read and write**
   - **Generate token** and copy it right away (GitHub shows it only once).
5. **Connect your phone.** Open the app link in Safari → paste the token → choose **User 1** → **Connect and sync**. Then tap **Share → Add to Home Screen**.
6. **Second person.** Repeat step 4 with the name `gym log – phone 2`, open the link on their phone, paste that token and choose **User 2**.

Updating an existing install: upload the new `index.html` to `gymtracker` and the new `library.json` and `images` to `gym-log`. Open the app and tap **Sync** (Settings). Nothing in your logs or routines changes.

## New: movements, versions and swapping

- **A movement is the muscle pattern** (chest press, row, leg curl). **A version is one piece of equipment for it**: the stack machine, a plate-loaded machine, a barbell, dumbbells. Every version keeps its own weights and history, because the numbers aren't comparable (10 on a stack is not 10 on a bar).
- **Swap** (button on each weighted exercise): pick another version, **Just today** or **From now on**. Use it when a machine is busy or your gym is different. Your sets and rep range carry over; the weight starts fresh for that version.
- **A machine that isn't listed:** type its name and how its weight is shown. It's remembered and appears in the swap list next time.
- **Make this your usual?** After 3 sessions in a row on one version, the app offers to switch your routine to it. Your history stays.
- **Stages and tips follow the movement.** When a new stage starts, a swapped-in machine gets the same sets and reps as the one it replaced. In Edit routines, give your own exercises a **Movement** so they follow too.

## Logging weights

The app always shows what your number means, next to the weights.

| Equipment | You enter | The app shows |
| --- | --- | --- |
| Dumbbells, one in each hand | 5 | 5 each = 10 total |
| One dumbbell held with both hands | 12 | 12 kg |
| Plate-loaded machine | 10 (plates on **one** side) | 10 each side = 20 total |
| Barbell or Smith machine | 40 (bar + plates) | 40 total = bar 20 + 10 each side |
| Stack machine or cable | 25 (the pin) | Pin on 25 |
| Assisted machine | 30 (the help) | 30 kg of help; less help = stronger |
| Bodyweight | reps; any added weight | Bodyweight + 5 kg added |

- **Bar weight:** barbells and Smith machines show a "Bar weighs" selector under the sets. Smith bars differ between gyms, so set what yours weighs.
- **Assisted machines:** less help counts as progress, so the app suggests going *down* in help.
- **First time on a version:** the app says "pick a weight you can lift N times with 3–4 reps left".
- Log the same way on the same machine.

## Photos and tips

- Tap an exercise's picture for the large photo, how to do it, how to log the weight, and avoid-injury tips. Tap the photo to enlarge it. Several photos per exercise are supported: `name.jpg`, `name_2.jpg`, `name_3.jpg`.
- For the first 3 sessions on an exercise, the form tips are open on the workout screen. Close them and they stay closed while you log.
- Photo names are the exercise id (`plate_loaded_chest_press.jpg`). Replace a file in `gym-log/images` and the app picks up the new one after the next sync.
- **`library.json`** (in `gym-log`) holds the tips, safety text, weight steps and movement of every built-in exercise. Edit it on GitHub to change them without a new app; entries override the built-in list by `id`.

## Good to know

- **Runs:** log distance, time (minutes or mm:ss) and, optionally, average heart rate; pace and speed are worked out as you type. History and Progress show pace (lower is faster) and kilometres per week.
- **Time or reps:** timed exercises such as mountain climbers have a Time | Reps switch; your choice is remembered per exercise.
- **Charts** have grid lines with round values; tap any dot or bar to see its value.
- **Balance** (Progress): average sets per week over the last 4 weeks for upper body, lower body and core, against your plan. **Strength** groups the versions of a movement into one chart, one line per version; assisted machines have their own chart.
- **Fast for years:** new workouts go into one file per year (`logs/<user>/2026.csv`); the original `logs/<user>.csv` is still read. The offline copy is kept in the browser's IndexedDB storage, so open the app from its Home Screen icon.
- **If a phone is lost:** delete its token on GitHub. The logs stay safe.
- **No signal at the gym:** workouts are kept on the phone and upload automatically next time it's online. Swapping "From now on" and saving a new machine need a connection; if there isn't one, the swap applies to today only.
- **Stages:** weeks 1–6 Foundation, 7–12 Build, 13–15 Sharpen, then Maintain in alternating 6-week blocks. When a new stage starts, tap **Update my routine** (the old routine is backed up in `gym-log/routines/`). Set the plan's start date in **Settings → Plan**.
- **Lighter weeks:** suggested only when it's been 5+ weeks *and* there are at least 2 signs of fatigue (after 8+ weeks one sign is enough). During a lighter week workouts show half the sets at about 80% of the weight (assisted machines keep their help).
- **How did it feel?** Easy / OK / Hard / Exhausted before saving; it helps spot fatigue.
- **One-tap sets:** tap ✓ on a set to log the planned weight and reps; tap again to undo.
- **Fix a mistake:** History → **Edit** (or **Edit** next to *Saved today*). GitHub keeps every earlier version.
- **Token expiry:** enter the token's expiry date in Settings; the app reminds you 2 weeks before.
- **Forgot to log a day:** change **Workout date** at the top of the workout.
- **Saving part-way:** saving twice on the same day stays one session.
- **Extra exercises:** **+ Add warm-up or extra** (top) or **+ Add exercise** (bottom). Search the built-in list in English or 中文, or add a new one. Tick *Keep it in this routine* to have it there next time.
- **Weight on bodyweight moves:** each set has a selector: *Bodyweight* or *+2.5 / +5 / … kg*.
- **Progress:** plan adherence, week streak, training calendar, personal records, estimated max strength (1RM) per lift, upper vs lower sets and weight lifted, cardio minutes, a smoothed body-weight trend, with written insights. Tick *Compare with …* to see the other user alongside.
- **Body check-in:** weight, body fat %, waist, hips and thigh. Add sex, birth year and height under *Your profile* for BMI (Taiwan's cut-offs), the healthy body-fat range for your age and your weekly trend.
- **Names:** Settings → Names. Log files keep their `user1` / `user2` names.
- **Changing exercises:** use **Edit routines**, or edit `routines/user1.json` in `gym-log` directly.
