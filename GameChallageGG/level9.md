# # Level 9

## Objective

Stop the timer countdown and ensure the game progresses correctly upon completion.

## Solution

1. **Modify the `L9_Timer` Class:**
   
   - Open the game’s `Assembly-CSharp.dll` file in dnSpyEx.
   - Search for the `L9_Timer` class.

2. **Stop Timer Countdown:**
   
   - Find the `OnTriggerEnter` method in the `L9_Timer` class.
   - Remove the line `MMGameEvent.Trigger("TimerStart");` to prevent the timer from starting.
   
   **Modified Code:**
   
   ```csharp
   private void OnTriggerEnter(Collider other)
   {
       if (other.CompareTag("Player"))
           {
               GameObject[] coins = this.Coins;
               for (int i = 0; i < coins.Length; i++)
               {
                   coins[i].SetActive(true);
               }
               this.playerHealth = other.GetComponent<Health>();
               //comment MMGameEvent.Trigger it or remove it
               //MMGameEvent.Trigger("TimerStart");
           }
   }
   ```

3. Replace `MMGameEvent.Trigger("KillPlayer");` with `MMGameEvent.Trigger("LevelComplete");` to ensure the level completes correctly.

```csharp
private void OnTriggerEnter(Collider other)
{
    if (other.CompareTag("Player"))
    {
        if (this.gameOver)
        {
            return;
        }
        if (!this.checkGameEndRequirements())
        {
            // Change to level_complete
            MMGameEvent.Trigger("LevelComplete");
        }
        this.completionFeedbacks.PlayFeedbacks();
        this.gameOver = true;
        UnityEngine.Object.Instantiate<GameObject>(this.speedFlag, base.transform.position, Quaternion.identity);
    }
}
```

4.**Save and Test:**
Save the changes and reopen the game. The timer countdown should stop, and the level should progress correctly when completed.

## Flag

<details>
<summary>Flag</summary>
GHCTF{zoom_zoom_money_maker}  
</details>
