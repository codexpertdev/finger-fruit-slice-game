# Finger Fruit Slice

A fruit-cutting game controlled by your **index finger** using webcam hand tracking. Slice fruits, dodge bombs, grab power-ups, and build combos for a high score.

## How to Play

1. Open `index.html` in a modern browser (Chrome recommended) or visit `http://localhost:8080` if using a local server.
2. Allow **webcam access** when prompted.
3. Click **Start Game**.
4. Wait for the **3-2-1-GO** countdown.
5. Hold your hand in front of the camera and **swipe with your index finger** to slice falling fruits.
6. You start with **3 lives**. Only **bombs** take a life — missing fruits is fine.

## Controls

| Input | Action |
|-------|--------|
| **Index finger** | Move and swipe to slice fruits |
| **Mouse click + drag** | Backup slicing if the camera lags |
| **⏸ Pause** button or **P** / **Esc** | Pause / resume |
| **📷 Cam** button | Show or hide camera preview |
| **🔊 Sound** button | Mute / unmute sound effects |

## Fruits

Slice any fruit to earn points. Faster swipes cut more reliably.

| Fruit | Points |
|-------|--------|
| 🍎 Apple | 10 |
| 🍋 Lemon | 12 |
| 🍊 Orange | 15 |
| 🍌 Banana | 18 |
| 🍇 Grape | 20 |
| 🍓 Strawberry | 22 |
| 🍉 Watermelon | 25 |

### Golden Fruit ★

- Any normal fruit can spawn as a **golden fruit** (~7% chance).
- Glows gold with a **★** above it.
- Worth **50 points** (before combo and power-up multipliers).

## Bombs 💣

- Black bombs with a sparking fuse fall with the fruits.
- **Do not slice bombs** — each bomb you cut costs **1 life**.
- Bombs that fall off the screen are harmless.
- Bomb spawn rate increases as your score goes up (~6% → ~16%).

### Shield vs Bombs

If you have an active **🛡️ Shield** and slice a bomb, the shield absorbs the hit. You see **BLOCKED!** and keep your life (the shield is used up).

## Power-Ups

Purple glowing orbs that fall occasionally (~4.5% spawn chance). **Slice them** to activate the effect.

| Power-Up | Icon | Effect | Duration |
|----------|------|--------|----------|
| **Shield** | 🛡️ | Blocks the next bomb hit | Until used |
| **Slow-Mo** | ⏱️ | Fruits move at half speed | ~7 seconds |
| **Double Points** | ✖️2 | All fruit scores are doubled | ~9 seconds |

Power-ups stack with combos — e.g. a golden fruit during 2x points and a x2 combo can earn a lot.

## Combo System

- Slice multiple fruits in a row without a long pause to build a **combo**.
- A timer bar appears under the combo — keep slicing before it runs out (~1.5 seconds).
- Combo callouts: **NICE!** (5), **AMAZING!** (10), **UNSTOPPABLE!** (20).

| Combo count | Score multiplier |
|-------------|------------------|
| 1 | x1 |
| 2+ | x1.5 |
| 4+ | x2 |
| 6+ | x2.5 |
| 10+ | x3 |

**Final points per fruit** = fruit value × combo multiplier × double-points (if active).

## Difficulty Levels

Speed ramps up gradually as your score increases. The current level is shown in the HUD.

| Level | Score range | What changes |
|-------|-------------|--------------|
| **Easy** | 0 – 249 | Slow fruits, fewer spawns, fewer bombs |
| **Medium** | 250 – 599 | Faster fall, more fruits, more bombs |
| **Hard** | 600 – 1199 | Quick fruits, frequent double spawns |
| **Insane** | 1200+ | Maximum speed and spawn rate |

Reaching a new level triggers a screen flash and callout (e.g. **MEDIUM!**).

## Scoring & Stats

- **Best score** is saved automatically in your browser (use the same URL each time, e.g. always `http://localhost:8080`).
- **Lifetime stats** on the start screen: games played and total fruits sliced.
- **Game over screen** shows: final score, best score, fruits sliced, max combo, and bombs hit.

## Git & GitHub

- **GitHub:** [github.com/awnish9002](https://github.com/awnish9002)

Clone the project with Git:

```bash
git clone https://github.com/awnish9002/finger-fruit-slice.git
cd finger-fruit-slice
```

Then run a local server (see [Run Locally](#run-locally) below).

## Run Locally

Because the game uses the webcam, use a local server for best results:

```bash
python -m http.server 8080
```

Then open **http://localhost:8080** in Chrome.

You can also open `index.html` directly, but always use the **same method** so your high score saves correctly.

## Requirements

- Webcam
- Modern browser with WebRTC support (Chrome recommended)
- Good lighting on your hand for reliable tracking
