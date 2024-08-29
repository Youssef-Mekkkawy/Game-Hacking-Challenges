# # Level 4

Objective

The Unicorn Raft has given up... Now he is just going to GIVE you the flag... or is he?

## Solution

To solve this level, follow these steps:

1. **Locate and Modify the `Pitfall` Class:**
   
   - Open the game’s `Assembly-CSharp.dll` file in dnSpyEx.
   - Search for the `Pitfall` class.

2. **Update the Code:**
   
   - Change the values of `floor` and `floor2` to `true`.
   - In the `for` loop, set the `active` property to `false`.
   
   **Modified Code:**
   
   ```csharp
   private void OnTriggerEnter(Collider other)
   {
       if (other.CompareTag("Player"))
       {
           this.floor.SetActive(true);
           this.floor2.SetActive(true);
           GameObject[] array = this.pitObjects;
           for (int i = 0; i < array.Length; i++)
           {
               array[i].SetActive(false);
           }
           UnityEngine.Object.Destroy(this.flag);
       }
   }
   ```

3. **Save and Test:**
   
   - Save the changes and reopen the game. You should now see that the floor does not fall, and when you reach the finish line, the flag will appear.

## Flag

<details>
<summary>Flag</summary>
GHCTF{oops_sorry_mr_unicorn}  

</details>

# [Next Challange](level5.MD)
