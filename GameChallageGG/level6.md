# # Level 6

## Objective

A guardian is protecting the exit and requires a fish, but you only have an apple.

## Solution

1. **Locate the `HasFish` Class:**
   
   - Open the game’s `Assembly-CSharp.dll` file in dnSpyEx.
   - Search for the `HasFish` class.

2. **Modify the `OnTriggerEnter` Method:**
   
   - Find the `OnTriggerEnter` method within the `HasFish` class.
   - Locate the line that sets `this.fishItems` to check for "Fish".
   - Change the value from "Fish" to "Apple".
   
   **Modified Code:**
   
   ```csharp
   private void OnTriggerEnter(Collider other)
   {
       // Change this line to check for "Apple" instead of "Fish"
       this.fishItems = this.inventory.InventoryContains("Apple");
   }
   ```

### **

3. **Save and Test:**
   - Save the changes and reopen the game. When you give the apple to the guardian, it should disappear, and the flag will be given to you. Additionally, the vent will open.

## Flag

<details>
<summary>Flag</summary>
GHCTF{Kitty_appreciates_the_fish_magic}  
<br/>

# [Next Challange](level7.MD)
