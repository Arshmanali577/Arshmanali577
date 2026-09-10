# Profile README — setup

Everything here belongs in your **`Arshmanali577/Arshmanali577`** repo (the one whose
name matches your username). Drop the files in at the root, keeping the folders:

```
README.md
SETUP.md
assets/
  header.svg          hero banner
  divider.svg         the animated rule between sections
  footer.svg          closing banner
  card-arc.svg        project card — ARC-2.0
  card-fgbc.svg       project card — FGBC-2.0
  card-portfolio.svg  project card — portfolio
.github/workflows/
  snake.yml           generates the contribution snake
```

```bash
git add README.md SETUP.md assets .github
git commit -m "Rebuild profile README"
git push
```

## 1. Turn the snake on

`snake.yml` needs one setting before its first run:

**Settings → Actions → General → Workflow permissions → Read and write permissions → Save**

Then **Actions → Generate contribution snake → Run workflow**. It creates an `output`
branch holding `snake.svg` and `snake-dark.svg`, which is where the README reads them
from. Until that first run finishes, the snake image in the README is a broken image —
that's expected. After that it refreshes twice a day on its own.

## 2. Add your email

Two `mailto:your.email@example.com` links in `README.md` are placeholders. Swap in your
real address, or delete those two badges.

## 3. Optional — the stats cards

The classic stats card, top-languages card, pinned-repo cards and trophy cabinet all come
from `github-readme-stats` and `github-profile-trophy`. **Their free public deployments are
paused right now** (`503 DEPLOYMENT_PAUSED`), which is why every profile using them shows
broken images. That block is in `README.md` inside an HTML comment, ready to switch on once
you run your own copy:

1. Fork <https://github.com/anuraghazra/github-readme-stats>
2. vercel.com → **Add New → Project** → import your fork → **Deploy**
3. Add an env var `PAT_1` = a GitHub personal access token (no scopes needed)
4. In `README.md`, replace `github-readme-stats.vercel.app` with your own Vercel domain
   and move the block out of the `<!-- ... -->` comment

## 4. Pin your repos

The README carries its own project cards, but GitHub's native pins sit above it on your
profile page. **Profile → Customize your pins →** pick `ARC-2.0`, `FGBC-2.0`, `portfolio`.

While you're there: ARC-2.0, FGBC-2.0 and portfolio all have an empty **About** field on
GitHub. One line each — the descriptions in the cards work fine — makes the repo list read
as well as the README does.

## Editing the artwork

The SVGs are plain text, no build step. The palette lives in the `<defs>` of each file:

| Colour | Hex |
|---|---|
| Teal | `#00F5D4` |
| Purple | `#8E2DE2` |
| Pink | `#FF2E97` |
| Plate | `#0F0C29` |
| Body text | `#9BA6C4` |

To add a fourth project, copy `card-portfolio.svg`, change the text, the `04` index and the
`accent` colour, then add another `<a><img …></a>` pair in the projects section.
