# Screenshot to Action v2.0, Build 213

Created by SurfKraken.

## Changes requested by Andy

The main menu contains Choose Photo, Take a Photo, All Captures, Backup and Restore, About and Help, and Quit last. It displays the tagline “See it. Sort it. Save it.” The earlier-action popup, tags, categories, inbox/archive statuses, action logging, and previous-version menus are removed. Rename and Delete remain on each capture. All ten output types remain.

The Notes action matches the identifier and App Intent descriptor from the user-provided iPhone export. The image is passed in the input alongside text; rendering both has not been confirmed on iPhone. Reminder asks for an optional day, without a time prompt. Completed outputs and handled validation errors return to the relevant menu.

Calendar asks once for the event day and time, supplies a one-hour duration, prompts for the user's calendar, then opens Apple's event editor. There is no separate end-date question. The duration remains editable in that editor.

Capture schemas 1, 2, and 3 are accepted by restore. Old pending fields are ignored. New schema-3 records contain the image, title, transcription, summary, address, detected contact fields, identifier, and timestamps.

## Fixes from Andy's device recording

Build 200 passed a Photos file directly to Get Dictionary from Input while listing captures. The phone showed “This action could not be run with the current user interface.” Build 202 first converts file content to text, then parses the JSON dictionary. It replaces the macOS-only image prompt with Apple Cloud Use Model and passes the photo directly for structured extraction. The map action uses the saved address instead of asking you to type it; contact details prefill Apple's review sheet. It also hashes the PNG's base64 text instead of passing the Photos image object to Generate Hash, which had produced an empty capture ID on-device. Deletion now uses the shortcut's explicit confirmation and suppresses the second native file-delete prompt that displayed the JSON record.

## Native input correction

Earlier builds assigned dictionary Value inputs as WFTextTokenAttachment objects. Apple's native text fields expect WFTextTokenString objects containing the reference. That is a concrete serialization defect consistent with the blank Value chips reported on the phone. The new audit checks field serialization types and the workflow model rejects the old encoding. Other dynamic text, URL, and date inputs receive the same audit.

Use Model receives the selected photo and returns a dictionary containing transcription, summary, a clear address, and any visible contact details. Map lookup uses that saved address directly, with no address-entry question. The contact sheet is prefilled from detected details and remains reviewable before saving. Cloud analysis requires Apple Intelligence support, connectivity, and available Apple usage allowance. The editor and model are simulated in the automated tests, not executed by Apple Shortcuts here.

## Automated results

Overall: PASS. This does not establish iPhone runtime compatibility.

| Round | Test methods | Result |
|---|---:|---|
| 1. Native structure and input connections | 21 | Passed |
| 2. Simplified user workflows | 40 | Passed |
| 3. Cancellation, legacy data, and backup failures | 32 | Passed |

The failure round includes 50 additional randomized Unicode/JSON/ZIP restore round trips. Native menu branches exercised by the model: 32 of 32.

Artifact: `Screenshot-to-Action-v2.0-Build-213.shortcut`

SHA-256: `6f3d51c1b6ab256760e08bec2f67da8b92b891913368aa04d8a10b79704c41fc`

Native actions: 649, down from 2,568 (74.7% fewer). Capture creation writes one archive file; output actions do not write the archive. Actual iPhone elapsed time was not measured.

## Reference lint

The separate external linter was not run for this build. The automated results are model and structural checks, not device execution.

## What still needs an iPhone

After signing and importing, verify the photo picker, camera, Apple Cloud extraction, one calendar date/time prompt, calendar chooser, event editor, other native output actions, delete confirmation, and backup/restore with actual Files/iCloud permissions. The tests here execute a model of the plist rather than Apple's runtime.

## Limits

- Apple Shortcuts is unavailable in this environment. Import, native UI, picker appearance, calendar discovery, Apple Cloud model serialization/runtime, permissions, and app effects still require an iPhone run.
- The model runs the emitted plist with real JSON, SHA-256, PNG conversion, base64, and ZIP operations. Apple Use Model, Camera, Photos, Calendar, Reminders, Contacts, sharing, Maps, speech, and PDF rendering are test doubles.
- Elapsed time and the native date-only reminder behavior have not been measured on iPhone. The selected day is passed to the native alert field, which may apply a time.
- The original photo remains available if AI analysis or the first save fails. This compact version saves once after analysis and does not keep per-edit recovery snapshots or action checkpoints.
- A native service, permission, malformed JSON, or storage error can stop the run. Previously saved captures remain available. Interrupted native creation can leave a created item, so review its destination before manually retrying.
- Backups include current capture JSON files with their images. Version-1 Recovery files and older backup ZIPs are not included. Deleting a legacy capture also removes its matching old recovery copy after confirmation.
- Existing captures are skipped on restore. Avoid simultaneous edits to this archive from different devices.
- GitHub backup remains pending owner approval. About links to the verified SurfKraken profile until a project repository is selected or created.
