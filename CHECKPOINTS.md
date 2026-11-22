# Checkpoints

Save points for the Aion 2 Tracker. Each one is a git tag, so you can return to it if a later change goes wrong.

## Checkpoint #1: Aion 2 Tracker EP01

Tag: `checkpoint-1-ep01`

### How to come back to this point

See what changed since the checkpoint:

    git diff checkpoint-1-ep01

Look at the checkpoint without changing anything (safe):

    git switch --detach checkpoint-1-ep01
    git switch main        # to go back to the latest

Throw away everything after the checkpoint and return to it (this deletes later work):

    git reset --hard checkpoint-1-ep01

Rescue a single file from the checkpoint:

    git restore --source=checkpoint-1-ep01 index.html

### What the app does at this point

- **Clocks:** Singapore time, Aion 2 server time (KST), daily reset and weekly reset. They resize to fit their own box. Daily reset is 3:00 PM Singapore, weekly reset is Wednesday 3:00 PM.
- **Checklist:** one row of tabs (Account plus each character). One card shows at a time. Every task is a single tap. The Account card holds the tasks shared by all characters. Tasks reset by themselves at the daily and weekly reset, including when the app was closed.
- **Odyle energy:** each character has an energy number that rises by itself on server time (default +15 every 3 hours). Setup is two steps: the time left on the game's recharge timer (hours and minutes), then the amount and the hours between recharges. It shows gain today, the next recharge countdown, and time to full.
- **Characters (menu):** open the hamburger menu, then Characters. Add a character with a name and a class. Each row has an editable name, a class picker and a delete button. Names must be filled in and unique (Account is reserved and locked), at least one character must stay, and delete asks first. Deleting the character on screen falls back to Account.
- **Charged energy:** one quiet line per character. Tap the number to change it.
- **Events:** a 12-hour timeline of the major events, a pulse strip for the two hourly events, and a Coming up list.
- **Build guide:** Ranger and Sorcerer stat priorities, with search.
- **Quick links.**
- **Layout:** drag widgets between a top strip and three columns, or use the arrow buttons. Hide or show widgets from the menu.
- **Themes:** dark Asmodian theme (obsidian, crimson, violet, a little cyan) and a light variant. Accent colour choice.
- **Installable app:** works offline once installed from a hosted address.
- **Privacy:** the public page holds no character names. `my-data.json` (your characters) stays on your PC and is loaded with Import.

### Files in this checkpoint

`index.html` (the whole app), `sw.js` (offline cache), `manifest.webmanifest`, `icons/`, `robots.txt`, `README.md`.

Not in the repository on purpose: `my-data.json`, `Daily Checklist.xlsx`, `New Requirement.docx`.

### Settings to remember

- Odyle recharge defaults to +15 every 3 hours. These are your own numbers from the game and can be changed under "Set up" on the Odyle panel.
- Saved data lives in each browser (key `top1tracker.v2`, data version 14). Use Menu, Data, Export to back it up.

### Known gaps at this point

- Not tested on a real phone. All testing was in a desktop headless browser.
- The Wednesday weekly reset was tested by its arithmetic, but I did not watch a real Wednesday 3 PM pass in the live page.
- The recharge interval (3 hours) is a default taken from your first message. Confirm it against the game.
- The Odyle recharge amount and interval apply to every character.
- The GitHub Pages copy is older than this checkpoint until you upload the new files.

### History of this checkpoint

- First saved without the Characters menu.
- Moved once, at your request, to include the Characters menu. The earlier commit is still in the history.

---

## Checkpoint #2: November 23, 2026 - Life Skill Tags

Tag: `checkpoint-2-life-skill-tags`

### How to come back to this point

See what changed since the checkpoint:

    git diff checkpoint-2-life-skill-tags

Look at the checkpoint without changing anything (safe):

    git switch --detach checkpoint-2-life-skill-tags
    git switch main        # to go back to the latest

Throw away everything after the checkpoint and return to it (this deletes later work):

    git reset --hard checkpoint-2-life-skill-tags

Rescue a single file from the checkpoint:

    git restore --source=checkpoint-2-life-skill-tags index.html

### What is new since Checkpoint #1

- **Life skill tags:** each character can be tagged with the life skills it has maxed: Odyle, Ore, Gem, Log, Herb, Ingredient. A character can have several. Set them in the menu, under Characters, with the six small buttons under each character's row.
- **Where they show:** as small tags under the character's name and class on its Checklist card. The Account card has none.
- **Data:** saved with the rest of the data, so Export and Import carry it. Data version is now 15 (was 14). Existing characters start with no tags.
- **Offline cache:** version `top1-v3-9`.
- **GitHub:** the project is now pushed to `straycatdev/t1-k7x9qm2wv4`. The two earlier web-upload commits on GitHub were merged into the history, keeping the local files.

### Known gaps at this point

- Not tested on a real phone. The tags were tested in a desktop headless browser only.
- No "who should I use?" lookup yet. The tags are display only.
- Same open items as Checkpoint #1 about the weekly reset and the 3-hour Odyle interval.

### Ideas parked for later

World boss respawn tracker, item level per character with unlock hints, Rift timer check, Sunday Abyss Order scroll reminder, weekly history (skipped for now).
