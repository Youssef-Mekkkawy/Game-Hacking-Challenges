# # Level 7

## Objective

At the start of this level, there's a message saying no more cheating, but you've taken care of that already.

## Solution

1. **Locate the `Wackamole` Class:**
   
   - Open the game’s `Assembly-CSharp.dll` file in dnSpyEx.
   - Search for the `Wackamole` class.

2. **Modify the `EndGame` Method:**
   
   - Find the `EndGame` method within the `Wackamole` class.
   - Remove all existing code in this method and replace it with the following lines:
   
   **Modified Code:**
   
   ```csharp
   private void EndGame()
   {
       this.gameActive = false;
       base.StopAllCoroutines();
       this.CheckWin();
   }
   ```

**Save and Test:**

- Save the changes and reopen the game. The `EndGame` method should now correctly stop the game and check for a win condition.

## Flag

<details>
<summary>Flag</summary>
GHCTF{nice_shooting_tex}  
</details>

# [Next Challange](level8.MD)
