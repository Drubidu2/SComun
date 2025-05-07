# ToDo

---

## [ ] 1. Implement Blockchain Smart Contract Logic

**Folder:** `src/blockchain/src/`  
**File:** `main.rs`

- Implement the following functions:
  - [ ] `handle_fire` : Process fire commands, validate receipts, and update game state.
  - [ ] `handle_report` : Process report commands, validate receipts, and update game state.
  - [ ] `handle_wave` : Process wave commands, validate receipts, and update game state.
  - [ ] `handle_win` : Process win commands, validate receipts, and finalize the game.
- [ ] Ensure that each function updates the `SharedData` structure correctly and sends appropriate log messages via the broadcast channel.

---

## [ ] 2. Complete Host Game Actions

**Folder:** `src/host/src/`  
**File:** `game_actions.rs`

- Implement the logic for generating receipts and sending them to the blockchain for the following functions:
  - [ ] `join_game`
  - [ ] `fire`
  - [ ] `report`
  - [ ] `wave`
  - [ ] `win`
- [ ] Replace the `"OK".to_string()` placeholders with actual receipt generation and sending logic using the `send_receipt` function.

---

## [ ] 3. Add Logic to Guest Methods

**Folder:** `src/methods/guest/src\bin/`  
**Files:**

- [ ] `win.rs`  
  - [ ] Process the `BaseInputs` and generate a `BaseJournal` output.
- [ ] `wave.rs`  
  - [ ] Process the `BaseInputs` and generate a `BaseJournal` output.
- [ ] `report.rs`  
  - [ ] Process the `FireInputs` and generate a `ReportJournal` output.
- [ ] `join.rs`  
  - [ ] Process the `BaseInputs` and generate a `BaseJournal` output.
- [ ] `fire.rs`  
  - [ ] Process the `FireInputs` and generate a `FireJournal` output.

---

## [ ] 4. Update Frontend Integration

**Folder:** `src/host/src/`  
**File:** `page.html`

- [ ] Validate form inputs (e.g., `gameid`, `fleetid`, `x`, `y`) before submission.
- [ ] Test the JavaScript logic for grid interactions and form submission.
- [ ] Replace placeholders like `{board}`, `{shots}`, `{gameid}`, `{fleetid}`, and `{response_html}` with dynamic values.

---

## [ ] 5. Write Unit Tests

**Folders:** `src/host/src/`
**Files:**
- [ ] Host logic in `lib.rs` and `game_actions.rs`.

**Folders:** `src/blockchain/src/` 
**Files:**
- [ ] Blockchain logic in `main.rs`.

**Folders:** `src/methods/guest/src\bin/` 
**Files:**
- [ ] Guest logic in the folder.

---

## [ ] 6. Finalize Docker Setup

**Folder:** Root (`/`)  
**Files:**

- [ ] `Dockerfile`
  - [ ] Ensure all dependencies are installed and the environment is correctly set up.
- [ ] `docker-compose.yml`
  - [ ] Verify that the `player0` and `chain0` services are correctly configured and can communicate with each other.

---

## [ ] 7. Update `.devcontainer` Configurations

**Folder:** `.devcontainer`  
**Files:**

- [ ] `player/devcontainer.json`
  - [ ] Ensure the `player0` container is configured for development.
- [ ] `chain/devcontainer.json`
  - [ ] Ensure the `chain0` container is configured for development.

---

## [ ] 8. Improve Error Handling

**Folders:** `src`, `bin`  
**Files:**

- [ ] Add error handling for:
  - [ ] Invalid inputs in the host logic (e.g., missing `gameid`, `fleetid`, or coordinates).
  - [ ] Receipt validation failures in the blockchain logic.
  - [ ] Invalid inputs or states in the guest methods.

---

## [ ] 9. Perform End-to-End Testing

**Folders:** Entire project  
**Steps:**

- [ ] Simulate a full game lifecycle:
  - [ ] Join a game.
  - [ ] Fire at a target.
  - [ ] Report the result.
  - [ ] Wave to other players.
  - [ ] Declare a win.
- [ ] Test multiple players interacting with the blockchain.

---

## [ ] 10. Audit Security

**Folders:** Entire project  
**Steps:**

- [ ] Audit the code for potential vulnerabilities, especially in:
  - [ ] Input validation.
  - [ ] Receipt verification.
  - [ ] Communication between the host and blockchain.
