# FCUK Backend Integration Prompt

## Context

The FCUK website frontend is already built and working visually - when users click buttons, the UI shows credits transferring from MAIN account to their wallet. But this is currently just illustration/animation with no backend connection.

You need to hook into the existing button clicks so they produce real ledger records in Bean Counter.

### Current System
- GitHub: https://github.com/unclehowell/FCUK
- Live: datro/static/fcuk/
- Working: Button click UI/animation shows credit transfer
- Missing: Backend API endpoint to catch the click event

### Reference
- Review existing FCUK pages to see current button implementations
- Understand how credits visually move from MAIN → user wallet

---

## Task

Modify the frontend to send API calls when buttons are clicked, so the backend can record transactions:

### 1. Add API Hook to Button Clicks
- When user clicks a credit button, send request to backend endpoint
- Include: user identifier, credit amount, button source
- Keep the visual/animation unchanged

### 2. Create Backend Endpoint
- Receive POST request from frontend button click
- Validate request (sufficient credits available)
- Record transaction to Bean Counter ledger
- Return success/failure to frontend

### 3. Bean Counter Integration
- POST transactions to Bean Counter
- Format: double-entry entries
- Track: Main account → User wallet transfers

### 4. Optional: Exchange Page (Future)
- Users can exchange credits for fiat/crypto
- Credentials collection (banking or wallet address)
- But not priority right now

---

## Requirements

- Minimal frontend changes (preserve existing UI)
- Secure API endpoint
- Bean Counter recording for audit trail
- Error handling with user feedback

---

## Deliverable

1. Frontend JavaScript changes: API call on button click
2. Backend endpoint code to receive requests
3. Bean Counter transaction recording logic