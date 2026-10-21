# Army Rush

A 3D hyper-casual troop runner that plays in a mobile browser. Swipe to steer your soldier through gates that grow your army, dodge traps, defeat enemy squads and a boss, then march down the bonus runway to multiply your coins.

## How to play

- **Swipe left and right** to steer (arrow keys or A/D on a computer).
- Your army **runs and shoots automatically**.
- **Blue and green gates** help (+10, ×2, ×3). **Red gates** hurt (−10, ÷2).
- Avoid spinning arms, saw blades and pop-up spikes.
- Robots shoot orange blasts at you. Steer away from them.
- Bosses fight back: stomp shockwaves (move to the other side of the track) and summoned reinforcements.
- Beat the boss at the finish line, then reach as far as you can on the **×1 to ×5 bonus runway**. Each zone leaves some soldiers behind.
- Spend coins in the **Store** on upgrades, weapons and army skins.
- Tap the **pause** button (or press Esc / P) to pause, restart or quit to the menu.

## Features

- Generated levels: each level is built from shuffled pieces and gets harder as you progress. Retrying replays the same layout.
- Enemies: soldiers, monster brutes with health bars, and robots that shoot back.
- Four bosses: Brute King, Stomper (shockwaves), Summoner (reinforcements) and Overlord (both).
- Four worlds that change every 3 levels: Meadow, Desert, Snowfield and Night Ops.
- Tips that teach each new thing the first time you meet it.
- Daily reward with a 7-day streak.
- Pause menu, and the game pauses itself when you leave the app.
- Upgrades: starting troops, damage, fire rate, troop health and gate bonus.
- Weapons: Rifle, Rapid SMG, Heavy Blaster and Laser Rifle.
- Skins: five army uniforms.
- Synthesized sound effects with a mute button.
- Progress saved in the browser (localStorage).

## Run it locally

It's a single file with no build step. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## Offline play

The game includes a service worker (`sw.js`) and an app manifest. The first time you open it online over HTTPS (for example on GitHub Pages), it saves the page, the 3D library and the fonts on your device. After that it works with no connection, and the main menu shows "Saved for offline play".

To install it like an app:

- **iPhone (Safari):** tap Share, then **Add to Home Screen**.
- **Android (Chrome):** tap the menu, then **Install app** or **Add to Home screen**.

When you change `index.html`, raise `VERSION` in `sw.js` (for example to `army-rush-v2`) so players get the new version.

## Publish with GitHub Pages

1. Push this folder to a GitHub repository.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
4. After a minute your game is live at `https://<your-username>.github.io/<repo-name>/`. Open that link on your phone and add it to your home screen.

## Tech

- [three.js](https://threejs.org/) r128 for 3D rendering (instanced meshes for large crowds).
- Web Audio API for sound effects, with no audio files.
- Plain HTML, CSS and JavaScript.
