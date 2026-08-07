# Attendance

An attendance tracker that processes biometric records and validates scholar time-ins/time-outs.

**Status:** Under development (core logic complete, output formatting and ux improvement in progress)

## How it works

This tool reconciles raw biometric exports with scholar records by:

1. Reading two CSV files:
   - `users.csv` — extracted from CrossHex (requires: `id`, `name` columns)
   - Weekly biometric records — all biometric entries for a given week (requires: `id`, `date\time`, `status` columns)
   
2. Filtering entries to extract only **first check-in** and **last check-out per date** per user
3. Outputting a cleaned attendance record

This reduces noise from multiple biometric captures throughout the day to meaningful entry/exit events.
