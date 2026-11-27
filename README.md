# DreamFree World QA

A reusable QA starter for DreamFree World. It includes a Lumi walkthrough, an 8–12 minute daily check-in, browser regression tests, native companion drafts for iPhone and Android, and a local wearable connector.

## Start here

Download and extract the **DreamFree-World-Wearable-Test-Kit.zip** from the project owner. Open `START-HERE.md` for the walkthrough, device setup and test instructions.

The starter uses a synthetic player in a separate browser session. Do not put credentials or private player backups in a QA report.

## Hardware covered

- Apple Watch and compatible sleep apps, through Apple Health.
- Android watches and compatible sleep apps, through Health Connect.
- Oura Ring, through supported health sharing or a direct Oura API connection.
- Ray-Ban Meta, through a user-selected, reviewed photo share.
- Pavlok, for the count of one selected habit’s logged entries.
- Fieldy, for selected, unlocked wearable memo titles that begin with “DreamFree”.

## Current status

The bundled web build and synthetic device bridges passed 20 browser regression checks. The application source tests passed 588 cases with one private-backup test skipped. Four simulated connector tests passed.

The browser and connector checks used synthetic data. Real provider accounts, physical devices, iPhone and Android compilation, signing, permissions and camera sharing still require device testing. See [device connection details](DEVICE-CONNECTIONS.md).

This is a review branch. The repository’s default branch has not been changed.

