# Lesson 05 — Coroutines and Timing

Coroutines help a mod control actions over time instead of doing everything instantly. They are very useful for waits, short timing windows, and state transitions.

---

## Concept

A coroutine is a method that runs in steps over time. Instead of executing everything at once, it can pause, wait, and continue later.

- **What is it?**  
  A way to manage delayed or timed actions in code.

- **Where is it used?**  
  In UI transitions, temporary states, cooldowns, and frame-based timing.

- **Why does it matter in modding?**  
  Because games often update systems across several frames, so mods must react at the right moment.

---

## Core Parts

- `IEnumerator`: used to define a coroutine  
- `yield return null`: waits until the next frame  
- `WaitForSecondsRealtime(x)`: waits for real time, even if game time changes  

---

## Example

```csharp
internal static IEnumerator BlockForAFrameWindow()
{
    BlockDismount = true;
    yield return new WaitForSecondsRealtime(1.0f);
    BlockDismount = false;
}
```

---

## What Happens Here

This code creates a short timed window.

1. `BlockDismount` is set to `true`  
2. The coroutine waits for 1 real second  
3. During that time, dismount logic can be blocked  
4. After the wait, `BlockDismount` is set back to `false`  

---

## Why It Is Useful

Coroutines are useful when a mod must respect the game’s timing.

- Helps control temporary behavior  
- Allows safe transitions between states  
- Prevents actions from happening too early or too late  

---

## Key Idea

> A coroutine lets a mod control **when** something happens, not only **what** happens.

---

## What I Learned

- I understood that a coroutine can pause and resume code over time  
- I learned how `yield return` creates waits between actions  
- I now see the difference between a one-frame wait and a real-time delay  

---

## What I Still Need to Practice

- I still need to practice choosing the right wait duration  
- I want to better understand frame timing during UI transitions  
- I should test this with phone opening and closing states  

---

## Link to Real Project Use

- **PhoneOnSkate** → used to block dismount during phone open/close transitions  
- **ProfitCalculator** → can be used to wait for the phone UI before scanning data  
