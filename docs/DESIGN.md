# Technical design — mobile

## Proposed implementation

Godot scenes present the tutorial, work-at-height and temporary-works cases. Keep reviewed scenario content versioned separately from session state. Persist decisions and enqueue synchronization atomically in SQLite. Mark the attempt confirmed after server acknowledgment. Use the API for explicit assignment submission.

## Verification

In airplane mode save a decision, terminate the app and resume the same attempt. Retry a lost upload with the same ID. Start corrective practice and confirm the new ID preserves the original evidence. Record device, Godot version, scene or APK, network state and save/restart result.
