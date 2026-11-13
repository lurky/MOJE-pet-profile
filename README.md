# Juan Carlos Moje Profile - Unit 8 Exercise

Project: `moje_unit8_exercise/`. Profile, Lurk with bark audio, gallery, Open Library books, OMDb movies, and Contentful My Picks. Version: `1.1.0+2`.

## Run locally

```powershell
cd moje_unit8_exercise
flutter pub get
flutter run -d chrome --dart-define-from-file=cms.json
```

Or select **Unit 8 Profile (local CMS)** in VS Code Run and Debug. Private configuration is retained locally and ignored. Use `cms.example.json` as a template on another computer.

## GitHub Pages

Publish this repository publicly. Set Settings > Pages > Source to GitHub Actions.
Add repository secrets `OMDB_KEY` and `CMS_TOKEN`, and variable `CMS_SPACE`. Optional variable `CMS_ENVIRONMENT` defaults to `master`.
The app uses Contentful's HTTPS endpoint with a space ID and token instead of a generic CMS_URL, so the workflow passes the settings actually read by this app.
Push to main or manually run the workflow. Add the verified live URL here after deployment.

## Android

From the project folder:

```powershell
flutter build apk --release --dart-define-from-file=cms.json
flutter build apk --debug --dart-define-from-file=cms.json
Get-ChildItem build/app/outputs/flutter-apk/*.apk | Select-Object Name,Length
```

The existing debug signing configuration is retained as permitted for this exercise only, not for store publication.

## Evidence to collect

- Test photos, bark audio, book/movie search and My Picks on the live site and phone browser. Record actual issues and fixes.
- Search compiled JavaScript for the OMDb key; redact its value in screenshots and explain client-side exposure.
- Install the Android release, test sound and APIs, and capture Settings > Apps showing version 1.1.0.
- Compare debug/release APK sizes.
- Upload the release APK to Google Drive and grant the instructor access. Submit that link, the live website URL, and screenshots.

API configuration, signing passwords, keystores, and build output must stay out of Git. GitHub secrets do not hide values embedded in downloaded clients.

The old `MOJE-UNIT-8-EXERCISE/` folder is preserved locally because Windows locked it; it is ignored and is not the active project.
