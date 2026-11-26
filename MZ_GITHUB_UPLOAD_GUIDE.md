# Publish LastWave MZ Edition on GitHub

You will publish this as your own repository/fork. These steps do not require sharing your GitHub password with anyone.

## Option A — GitHub website (easiest)

1. Sign in to GitHub.
2. Click **New repository**.
3. Repository name: `LastWave-MZ-Edition`.
4. Description: `Independent LastWave Native fork focused on app-private offline downloads and storage visibility.`
5. Choose **Public** only if you are comfortable making the source public and complying with GPL-3.0. Do not initialize with a README, license, or `.gitignore` because this source already contains them.
6. Create the repository.
7. Extract `LastWave-MZ-Edition-source.zip` on your PC.
8. Open the extracted `LastWave-Native-main` folder. Select all its contents (including hidden `.github` and `.gitignore`) and upload them to the new repository. GitHub's web uploader has file-count/size limits; if it rejects the project, use Option B.
9. Add a commit message such as `Add MZ app-private offline downloads and storage overview` and commit.
10. Open `MZ_EDITION_README.md` and use it as the project overview, or copy its introduction into the repository README after reviewing upstream attribution.

## Option B — Git command line (recommended for a full Android project)

Install Git, extract the ZIP, open PowerShell in the extracted `LastWave-Native-main` folder, then run:

```powershell
git init
git add .
git commit -m "Initial LastWave MZ Edition source"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/LastWave-MZ-Edition.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username. GitHub will open a browser sign-in flow or request a Personal Access Token depending on your Git setup. Never paste a token/password into chat or commit it into the repository.

If you are publishing inside a fork of the upstream repository instead, use GitHub's **Fork** button first and set `origin` to the URL of your fork. Keep the upstream remote if you want to sync future changes.

## After upload

1. Check the Actions tab. The repository includes upstream GitHub Actions workflows; inspect their settings and run the build workflow.
2. Wait for a successful Android build. Download the APK from the workflow artifact only after success.
3. Install and test the APK on your own phone.
4. Create a GitHub Release only after build and device tests pass. Use a version such as `v0.1.0-mz-preview` and describe it as a preview.
5. Attach the tested APK and the corresponding source archive. Keep the GPL-3.0 license and upstream notices.

## Important

Do not call this an official LastWave release. Clearly identify it as an independent community fork. The current prepared package is source-only; the build has not succeeded in this offline environment, so there is no verified APK to attach yet.
