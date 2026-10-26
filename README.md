<div align="center">

# SplitMate

### Split expenses. Keep things simple.

A minimal, mobile-first expense splitter that calculates fair balances and shows who should pay whom — without an account or a backend.

![Static HTML](https://img.shields.io/badge/HTML-CSS%20%2B%20JavaScript-e87935?style=for-the-badge&logo=html5&logoColor=white)
![Offline friendly](https://img.shields.io/badge/Offline-friendly-19764b?style=for-the-badge&logo=icloud&logoColor=white)
![Privacy](https://img.shields.io/badge/Privacy-Local%20by%20default-315b83?style=for-the-badge&logo=privacy&logoColor=white)

[Launch website](#deploy-with-github-pages) · [Add Android APK](#publish-the-android-apk) · [Report an issue](../../issues)

</div>

---

## About

SplitMate makes group expense settlement straightforward. Enter each person's contribution, and it calculates the fair share, shows each person's balance, and suggests a set of transfers to settle up.

### Features

- **Fast expense splitting** — enter participants and how much each person paid.
- **Clear settlement instructions** — see who pays whom and how much.
- **Settlement tracking** — mark transfers as paid and view progress.
- **Shareable summary** — copy the settlement or use your device's share menu.
- **Currency selector** — choose from the currencies included in the app.
- **Light and dark themes** — choose the appearance you prefer.
- **Local saving** — the current group is saved in this browser on this device.
- **Mobile-first UI** — responsive on phones, tablets and desktop browsers.
- **No login or backend** — the website is a static HTML, CSS and JavaScript app.
- **Android download section** — the site automatically enables the download button when `apk/SplitMate.apk` is available on the hosted site.

> **Privacy note:** The web calculator stores its current group in your browser's local storage. Clearing browser data can remove it. This is local browser storage, not encrypted storage or a backup system. Export or back up important information separately.

## Repository structure

```text
SplitMate/
├── index.html             # Website (HTML, CSS and JavaScript in one file)
├── README.md              # Project documentation
└── apk/
    ├── README.md          # Instructions for adding the Android build
    ├── .gitkeep           # Keeps the folder visible before an APK is added
    └── SplitMate.apk       # Add your signed/release APK here
```

The APK is intentionally **not included yet**. Build the Android app first, then copy the actual APK into `apk/SplitMate.apk`. The download button will remain disabled until the file is available on the hosted website.

## Run locally

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. Start entering participants and contributions.

No package installation or build step is needed for the website. For the most reliable browser storage and APK availability check, run it through a local static server or GitHub Pages rather than a `file://` preview.

## Deploy with GitHub Pages

1. Create a GitHub repository and upload `index.html`, `README.md` and the `apk/` folder.
2. Open **Settings → Pages** in the repository.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select your main branch and the repository root (`/`).
5. Save and wait for GitHub Pages to publish the site.
6. Open the published URL and verify the calculator works.
7. After adding `apk/SplitMate.apk`, reload the page and test the Android download button.

The download uses a relative path (`./apk/SplitMate.apk`), so it works with a project site hosted under a repository subpath as well as a custom domain.

## Publish the Android APK

1. Build the Android app's release APK in Android Studio.
2. Sign the release build with your own release signing key.
3. Copy the generated APK into this repository at exactly:

   ```text
   apk/SplitMate.apk
   ```

4. Commit and push the file.
5. Wait for GitHub Pages to deploy, then test the download on a phone.

Only distribute an APK you built and trust. Android may show an install warning for apps installed outside the Play Store. Users should install it only if they trust the source.

### Recommended release tags

Use Git tags to label source releases, for example:

```bash
git tag -a v1.0.0 -m "SplitMate v1.0.0"
git push origin v1.0.0
```

A Git tag is a version label; it is **not** a secret and does not securely store signing credentials.

## GitHub Secrets and signing keys

- **Never commit** keystores, passwords, signing keys, API tokens, or `.env` files.
- If you later automate Android release builds with GitHub Actions, store signing credentials in **Repository Settings → Secrets and variables → Actions** and reference them from the workflow.
- Do not put secret values in the README, source code, commit messages, Git tags, release notes, or APK download URL.
- The static website itself does not need GitHub Secrets to host or link to a public APK.

## Data and limitations

- The website currently saves its calculator state in browser local storage.
- Data is not synced between devices and is not sent to a server by the website.
- Browser storage may be removed by the user or browser; keep separate backups for important records.
- The Android APK download becomes available only after a real APK is added to `apk/SplitMate.apk`.
- The settlement calculation is intended to minimize practical transfers; test financial edge cases before relying on it for high-value settlements.

## Contributing

Suggestions and bug reports are welcome. Please include clear reproduction steps and avoid sharing real personal or financial data in issues.

---

<div align="center">

**SplitMate** · Small steps. Fair splits.

</div>
