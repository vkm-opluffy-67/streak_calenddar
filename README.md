# Show Up Every Day

Your streak calendar as a normal website. Everything works as before, plus a
**GitHub backup** button that saves your data to a private repo automatically.

## 1. Put the site on GitHub

1. On GitHub create a **private** repo, for example `show-up-every-day`.
2. Upload `index.html`, `netlify.toml` and this README (Add file > Upload files).

## 2. Host it on Netlify

1. In Netlify choose Add new site > Import an existing project > GitHub, and pick the repo.
2. Leave the build command empty and the publish directory as `.`, then deploy.
3. Every push to the repo redeploys the site.

## 3. Create a separate private repo for backups

Use a different repo from the site code, for example `show-up-backups`.
If backups went into the site repo, each one would trigger a new Netlify deploy.
Add an empty README so the repo has a first commit.

## 4. Create a GitHub token (once)

1. Open https://github.com/settings/personal-access-tokens/new
2. Repository access: **Only select repositories**, pick `show-up-backups` only.
3. Permissions > Repository permissions > **Contents: Read and write**.
4. Generate the token and copy it.

## 5. Connect the site

On the site open **Export & backup > GitHub backup**, enter `yourname/show-up-backups`
and the token, then press **Save & back up now**.

- Every change is committed about 12 seconds after you make it.
- `backups/latest.json` always holds the newest data.
- `snapshots/YYYY-MM-DD.json` keeps one file per day. Full history is in the repo's commits.
- On your phone, open the site, connect with the same repo and token, and it loads your newest backup.
- **Restore from GitHub** lets you pick the latest or any daily snapshot.

The token is stored only in that browser, so enter it once on each device.

## Moving your existing data

Your data on the old Claude page is not shared with a new web address.
On the old page press **Download backup**, then on the new site press **Restore backup**
and pick that file. After that, GitHub backup takes over.

## Not included in the backup

Your own background photos are stored in your browser, as before, and are not part of
the backup file (same as the existing Download backup).
