# Device acceptance matrix

Use this matrix for physical-device acceptance after the native builds are signed and installed. It complements the overview in [DEVICE-CONNECTIONS.md](DEVICE-CONNECTIONS.md); it does not replace browser or source tests.

## Record each run

Record the date, app build, operating system version, device model, provider app/version, test ID, result, and a short note for each case. Use a synthetic player and test records where possible. Never include API keys, tokens, private backups, Fieldy transcripts, location data, or unredacted health records in screenshots or reports.

Mark each case **Pass**, **Fail**, or **Blocked**. For a failure, note the steps to reproduce and the expected and observed behavior. Mark unavailable hardware or provider accounts **Blocked** rather than treating a simulated result as device acceptance.

## Cases

| ID | Setup | Steps | Pass criteria |
| --- | --- | --- | --- |
| HLT-01 | Test account has no sleep records shared to the phone. | Open the daily check-in before and after granting health read access. | Sleep remains blank when no records are available. The app does not substitute a sample or fabricated value. |
| HLT-02 | Share one known sleep session from a watch or compatible ring app. Record the session's source and interval in the run notes. | Connect Apple Health on iPhone or Health Connect on Android. Open the check-in and compare the displayed minutes and source with the source app. | The displayed total matches the documented aggregation rules, names the source used, and does not include data outside the previous-noon-to-current-noon window. |
| HLT-03 | Share overlapping sleep records from two sources with different total coverage. | Open the check-in and inspect the selected source and total. | Overlapping intervals are not counted twice. The source with the most minutes is named. Reopening the screen does not create extra minutes. |
| HLT-04 | Record one workout today and note its duration in the provider app. | Open the daily check-in after the workout syncs. | The workout summary reflects the available records from midnight to the current time. No game resources are awarded for sensor readings. |
| HLT-05 | Health access has been granted once. | Revoke access in operating-system settings, reopen DreamFree, then repeat while offline. | The screen reflects missing or unavailable access clearly and shows no stale or invented reading as current. |
| EXT-01 | Configure a Fieldy test account with one unlocked wearable-source conversation titled with the “DreamFree” prefix, plus one nonmatching item. | Connect Fieldy and inspect the result. | Only the eligible title is shown. Transcript text, locations, and nonmatching recordings are not exposed. |
| EXT-02 | Configure one Pavlok habit with known log entries. | Connect Pavlok and compare the displayed count with the selected habit. Inspect available actions. | The count matches that habit's total log count. DreamFree sends no command that changes wearable behavior. |
| EXT-03 | Configure the local Oura connector with a test account and the supported daily-summary access. | Pair the browser session, request the summary, then disconnect. | Only the documented daily sleep and readiness summary is displayed. The connector is limited to the paired world and does not modify the saved world. |
| IMG-01 | Have one test image available in the iOS share sheet or Android share flow. | Share the image to DreamFree, cancel once, then repeat and review before saving to a meal or workout log. | Cancel leaves no entry. The saved image is private by default and appears on My Page only after a separate explicit share action. |
| CON-01 | Connect each configured provider, then revoke its provider or operating-system access. | Disconnect in DreamFree, revoke access, and reopen the app offline. | The disconnected source is no longer presented as connected. Missing or expired access is explained without exposing credentials. |

## Evidence and privacy

Attach only redacted screenshots or notes needed to explain a result. Crop out account identifiers and blur any personal health details. Do not attach raw provider responses, credentials, private player backups, or Fieldy transcript content. Keep test records in the approved private QA location and follow the device owner's cleanup process after the run.

A passing row records behavior observed on the named physical device and build. Browser simulations and source tests should be reported separately.
