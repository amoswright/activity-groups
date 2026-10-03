# Activity Groups

A small offline web app for sorting students into activity groups from a CSV of their choices.

## What it does
- Reads a CSV with one row per student: name, day, and choices 1 to 4.
- On each day, every student is placed in 3 of the 4 activities, one per time slot. Each activity runs in every slot, with at most 15 students per group. Both numbers can be changed before building.
- Assignments are chosen to give as many students as possible their top three choices. Missing a 1st choice counts as much worse than missing a 3rd.
- Shows a board for each day where students can be dragged between activities. On a touchscreen, press and hold to drag, or tap a name to pick from a list.
- Exports a Groups CSV (one row per student, with a Result column), a Rosters CSV (one row per student per group), or an Excel file with both as sheets.
- Everything stays in the browser's local storage. Nothing is sent anywhere.

## Hosting it
Every file in this folder has to be served together over HTTPS. Offline mode and installing the app won't work if index.html is opened straight from disk.
- **GitHub Pages:** push the folder to a repo, then turn on Pages under Settings.
- **Netlify Drop:** drag the folder onto app.netlify.com/drop.

Have the teacher open the URL once while online. After that it works offline, and it can be installed from the browser menu: Add to Home Screen on iPad, or Install on Chrome or Edge.

## Updating
After changing any file, bump `VERSION` in `sw.js` so installed copies pick up the new version. The update shows on the second reload after deployment.

## Files
- `index.html`: the whole app, with no external dependencies.
- `sw.js`: offline cache.
- `manifest.webmanifest` and the icons: what makes it installable.
- `sample-students.csv`: 90 made-up students for trying it out.
