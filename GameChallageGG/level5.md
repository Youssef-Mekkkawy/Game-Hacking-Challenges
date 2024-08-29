# # Level 5

## Objective

The Unicorn Raft now has a laser fence guarded by laser turrets. The goal is to bypass these turrets.

## Solution

1. **Locate the `LaserTurret` Class:**
   
   - Open the game’s `Assembly-CSharp.dll` file in dnSpyEx.
   - Search for the `LaserTurret` class.

2. **Modify the `OnTriggerEnter` Method:**
   
   - Find the `OnTriggerEnter` method within the `LaserTurret` class.
   - Remove the `if` statement and make the method an empty `void`.
   
   **Modified Code:**
   
   ```csharp
   private void OnTriggerEnter(Collider other)
   {
       // Remove the if statement and make it an empty void
       // This will prevent the turret from firing lasers when the player enters the trigger zone
   }
   ```

### **Save and Test:**

- Save the changes and reopen the game. The laser turrets should no longer fire at you, allowing you to pass through the laser fence.

## Flag

<details>
<summary>Flag</summary>
GHCTF{oops_sorry_mr_unicorn}

</details>

# [Next Challange](level6.md)
