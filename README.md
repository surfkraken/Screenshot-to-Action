# Screenshot to Action

See it. Sort it. Save it.

Screenshot to Action turns a screenshot into useful next steps. Choose a photo or take one, let Apple Intelligence analyze it, then save, search, or act on the details it finds.

## Download

Visit [the opening page](index.html) to get the current shortcut. The download link is loaded from latest.json, so release details stay in one place.

The shortcut is distributed for signing with your preferred tool before installing it. See the [test report](Screenshot-to-Action-Test-Report.md) for verification details and known limits.

## What it does

- Extracts visible text, a summary, addresses, and contact details using Apple's Shortcuts Use Model action.
- Saves captures locally in iCloud Drive, where you can browse, rename, edit text, and delete with confirmation.
- Creates reminders, calendar events, checklist reminders, and Notes; copies or reads text aloud; opens addresses and links; creates contacts; or exports a PDF.
- Creates ZIP backups and restores validated JSON capture records, skipping records already saved.

The first menu is kept intentionally simple: Choose Photo, Take a Photo, All Captures, Backup and Restore, About and Help, and Quit.

## Requirements and verification

Requires a compatible iPhone running iOS 27 with Apple Intelligence enabled for image analysis. Internet access and Apple's model availability are required for analysis.

The shortcut passed automated structural and modeled workflow checks across multiple rounds, including all menu branches. These checks do not execute Apple's Shortcuts runtime. Import and verify Apple Intelligence, Notes, Reminders, Calendar, Maps, Contacts, permissions, and performance on your device. The test report describes known limits.

## Files

- The shortcut download is linked dynamically from latest.json.
- The source archive contains the generator, test suite, and build documentation.
- latest.json contains current release metadata for the future update-check workflow.

## Project

Created by [SurfKraken](https://github.com/surfkraken). This repository is the source of truth for releases and future update checks.# Screenshot to Action

See it. Sort it. Save it.

Screenshot to Action turns a screenshot into useful next steps. Choose a photo or take one, let Apple Intelligence analyze it, then save, search, or act on the details it finds.

## Download

Get the latest shortcut: [Screenshot-to-Action-v2.0-Build-213.shortcut](Screenshot-to-Action-v2.0-Build-213.shortcut)

The shortcut is distributed for signing with your preferred tool before installing it. See [the opening page](index.html) and [the Build 213 test report](Screenshot-to-Action-Test-Report.md) for details.

## What it does

- Extracts visible text, a summary, addresses, and contact details using Apple's Shortcuts Use Model action.
- Saves captures locally in iCloud Drive, where you can browse, rename, edit text, and delete with confirmation.
- Creates reminders, calendar events, checklist reminders, and Notes; copies or reads text aloud; opens addresses and links; creates contacts; or exports a PDF.
- Creates ZIP backups and restores validated JSON capture records, skipping records already saved.

The first menu is kept intentionally simple: Choose Photo, Take a Photo, All Captures, Backup and Restore, About and Help, and Quit.

## Requirements and verification

Requires a compatible iPhone running iOS 27 with Apple Intelligence enabled for image analysis. Internet access and Apple's model availability are required for analysis.

The current build passed 93 automated structural and modeled workflow checks across three rounds, including all 32 menu branches. These checks do not execute Apple's Shortcuts runtime. Import and verify Apple Intelligence, Notes, Reminders, Calendar, Maps, Contacts, permissions, and performance on your device. The test report describes known limits.

## Files

- Screenshot-to-Action-v2.0-Build-213.shortcut: installable shortcut package.
- Screenshot-to-Action-Build-213-Source.zip: generator, test suite, and build documentation.
- latest.json: current version metadata for a future update-check workflow.

## Project

Created by [SurfKraken](https://github.com/surfkraken). This repository will be the source of truth for releases and future update checks.
