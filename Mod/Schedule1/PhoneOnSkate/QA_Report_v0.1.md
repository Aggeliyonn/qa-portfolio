# 🧪 QA Report – PhoneOnSkate v0.1

**Games:** Schedule 1 - PhoneOnSkate

---

## 📊 Summary

🔴 Reviews: 1
🟠 Major: 1
🟡 Minor: 1
🟢 Visuals: 0

### 📌 Overall Status

✔ Fixed: 2
🔧 In Progress: 1
❗ Remaining: 1

---

## 🔧 Dev Log

**Goal:**
To be able to use the phone on the skateboard without dismounting and continue riding.

### Step – Block Dismount
- Prevent dismounting when opening the phone

### Step – Slow Dismount
- Prevent dismounting for 6 frames

### Step – Dismount Remount
- Automatic remounting after controlled dismounting

---

## 🐞 QA Bug Report

---

### 🔴 Bug – Screen Freeze

**Origin:** Step Block Dismount

#### Conditions
- Be on the skateboard
- Open the phone

#### Steps
1. Get on the skateboard
2. Open the phone

#### Current Result
- Complete game freeze
- Appearance of a black area

#### 📷 Bug Screenshot
![Bug](Pictures/bug-block-dismount.png)

#### Expected Result
- Remain on the skateboard with the phone open

#### Frequency
- 10/10

#### Reproducibility
- Always → reliably triggers

#### Analysis
- Seems related to the camera, the player, and the phone
- Only occurs on the skateboard
- Likely UI/camera conflict

#### Status
✔ Fixed

---

### 🟠 Bug – Remount impossible

**Origin:** Step: Slow down dismount

#### Conditions
- Open the phone
- Wait 6 frames

#### Steps
1. Get on the skateboard
2. Open the phone

#### Current result
- No remount

#### Expected result
- Remount after delay

#### Frequency
- 10/10

#### Reproducibility
- Always

#### Analysis
- The skateboard temporarily disappears
- Remount cannot be applied

#### Status
✔ Fixed

---

### 🟡 Bug – Camera Desynchronization

**Origin:** Step Dismount Remount

#### Conditions
- Open then close the phone

#### Steps
1. Get on the skateboard
2. Open the phone
3. Close the phone

#### Current Result
- Camera bug

#### Expected Result
- Consistent camera

#### Frequency
- 10/10

#### Reproducibility
- Always

#### Analysis
- Conflict between player state and camera
- The camera doesn't know whether to be in first or third person

#### Status
🔧 In progress
