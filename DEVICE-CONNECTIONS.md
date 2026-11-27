# Device connections and acceptance checks

## User flow

From **My Garden**, choose **Learn to play with Lumi** to practice the soil-to-Camp game loop. The guide uses example balances and does not spend the player's resources.

Choose **Start my daily check-in** for a resumable 8–12 minute routine. It saves one priority to Today, a sleep and recovery observation to the Routine Laboratory, and a reflection to Today. From the same screen, **From your devices → Manage device connections** controls wearable sources.

## Readings and privacy

The phone check-in can request Apple HealthKit sleep and workout read access. The Android companion can request Health Connect sleep and exercise session read access. A source with no shared records stays blank. Sleep samples from the previous noon through current noon are grouped by data source, overlapping intervals are combined, and the source with the most minutes is displayed. Workouts are summarized from midnight to the current time. Sensor readings do not award game resources.

On iPhone, a native prompt can collect the player's Fieldy API key or Pavlok token and a selected habit ID. Fieldy queries today's wearable-source conversations and passes only unlocked titles beginning with “DreamFree”. Pavlok queries one configured habit's total log count. Tokens are saved in the phone's protected, device-only Keychain. The APIs are read-only.

The local Python connector supports Fieldy, Pavlok and Oura for one world on one computer. Oura requests only daily summary access and displays sleep and readiness scores. Provider credentials are configured privately. The connector binds to loopback, pairs one browser session, limits world scope, and does not write readings into the player's saved world.

The iPhone share extension accepts one selected image from the iOS share sheet. Android accepts a selected image shared from another app, including Meta AI. DreamFree previews it before the player saves it in a private meal or workout log. Imported images remain private unless the player separately chooses to share them.

## Manual device checks

1. Pair an Apple Watch or configure a ring vendor app to share a sleep session through the phone's health service. Connect the matching health service in DreamFree and compare sleep minutes against the source app.
2. Wear two sleep sources and confirm DreamFree names the source used. Deny then revoke one permission, reopen the screen, and check that no fabricated value appears.
3. Record one workout and confirm the check-in displays the expected minutes.
4. Create a Fieldy wearable memo whose title starts with “DreamFree”. Connect Fieldy and verify only its eligible title appears. Ensure transcript content, locations and other recordings do not appear.
5. Choose one Pavlok habit with at least one log. Connect the source and compare the reported count. Verify DreamFree sends no command to the wearable.
6. Share a Ray-Ban Meta meal photo to DreamFree, cancel once, then review and save it. Confirm the entry remains private and does not appear on My Page without a second explicit choice.
7. Disconnect each service and revoke its operating-system or provider access. Reopen the app offline and verify the screen explains a missing or expired source clearly.

## Boundaries

A browser pass is not a native build. Hardware integration still requires configured developer accounts, signed iPhone and Android apps, platform permissions, paired devices, and physical acceptance tests. Automatic access to the entire Meta AI gallery is not included. Apple and Android share the phone's world storage; distinct devices do not automatically share their local player saves.

Planner and social proposals are tracked as planned scenarios in the QA kit. Completed local game, planner, photo and sample-neighbor behavior has separate browser checks.

