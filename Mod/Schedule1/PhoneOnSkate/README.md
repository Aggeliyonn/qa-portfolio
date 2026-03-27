# 🧪 In Progress - PhoneOnSkate

**Status:** 🟠 In Progress
**Version:** v0.1
**Type:** Client-side Mod
**Target Project:** Schedule I

**Main Objective:**

> Allow the player to use the phone while riding a skateboard without triggering dismount or breaking camera behavior

**Final Vision:**

> Smooth phone usage on skateboard with no desync, no clone, and stable transitions

---

## 🧱 Architecture

### Core

* State tracking (Phone / Skate / Player)
* Transition control (open / close phone)
* Dismount blocking logic

### UI (if applicable)

* No custom UI (uses in-game phone)

### Data

* Player state (riding / not riding)
* Phone state (open / closed)

### Hooks / Integration

* GameInput.OnTogglePhone
* Skateboard / Player state methods
* Camera behavior on transition

### Debug

* MelonLoader logs
* State tracking logs
* Transition timing observation

---

## ⚙️ Progress

### 🧩 Core

* [x] Functional Initialization
* [x] State Management (basic)
* [ ] Stable transition system

### 🧩 UI

* [x] Phone usable while riding
* [ ] No visual glitch

### 🧩 Data

* [x] Player state detected
* [x] Phone state detected
* [ ] Fully synchronized states

### 🧩 Integration

* [x] Hook on phone open
* [x] Partial dismount blocking
* [ ] Stable behavior on close

### 🧩 Debug

* [x] Logs implemented
* [x] Issues identified
* [ ] Fully validated behavior

---

## 🔍 Technical Discoveries

* Phone opening triggers state changes affecting camera
* Dismount logic tied to transitions and timing
* Camera behavior not synced with player state

### Assumptions

* Camera reset occurs during phone close
* Timing (frame window) is critical

### Important Targets

* Phone open/close methods
* Dismount triggers
* Camera update logic

---

## 🧠 Problems Encountered

### ❌ Camera Desynchronization

* **Description:** Camera switches incorrectly after closing phone
* **Probable Cause:** Transition timing conflict
* **Impact:** Breaks player perspective
* **Status:** In progress

### ❌ Skateboard Clone

* **Description:** Temporary duplicate appears
* **Probable Cause:** Object lifecycle issue
* **Impact:** Visual glitch
* **Status:** In progress

---

## 🛠 Tested Solutions

### ✔ Transition Blocking

* **Action:** Block dismount during phone usage
* **Result:** Player stays on skateboard
* **Notes:** Causes new camera issue

---

## 🛠 Technical Choices

* **Main Technology:** C#
* **Framework / Loader:** MelonLoader
* **Integration:** Harmony patches

### Validated Choices

* Use of Harmony for method interception
* Logging via MelonLoader

### Rejected

* Blocking object destruction (unstable results)

---

## 📊 Current Status

### ✅ Working

* Phone usable on skateboard
* Basic state detection

### ⚠️ Partial

* Transition stability
* Dismount control

### ❗ To Do

* Fix camera behavior
* Remove clone issue
* Stabilize transitions

---

## 🔮 Roadmap

### Phase 1 - Base

* [x] Setup
* [x] Initial Tests

### Phase 2 - Main Function

* [x] Phone usage on skateboard
* [ ] Stable integration

### Phase 3 - Improvement

* [ ] Fix camera
* [ ] Fix clone
* [ ] Improve timing

### Phase 4 - Finalization

* [ ] Cleanup
* [ ] Final Tests
* [ ] Release

---

## 🧾 Dev Notes

### Session [Current]

* Phone usable on skateboard
* Identified camera desync
* Clone issue reproduced
* Next step: stabilize transitions

---

## 📤 Export

### DevLog

* PhoneOnSkate functional but unstable

### QA Report

* Camera + clone issues documented

---

## 🧿 Free Notes

* Transition timing is the key
* Multiple systems conflict during phone close
