# Level 1 Walkthrough

## Objective

The goal is to obtain the gun located in the middle of the room. However, there's a turret in the corner that will shoot at you if you approach the gun. The challenge is to bypass or neutralize this threat so you can safely get the gun.

## Solution

# 

### 1. Use dnSpyEx to Locate the Health Class:

- Open the game’s `Assembly-CSharp.dll` file in dnSpyEx.
- Use the search bar to find the `Health` class. This class typically manages the health mechanics of characters, including the player and enemies.

### 2. Identify Key Functions:

- Look for functions related to health manipulation within the `Health` class. These include:
  - `SetHealth`
  - `ReceiveHealth`
  - `ResetHealthToMaxHealth`
  - `Damage`

### 3. Modify the `Damage` Function:

- The `Damage` function is responsible for reducing health when the player or other entities take damage.
- To prevent the player from taking damage, modify the function to include an `if` statement that checks if the entity taking damage is the player. If it is, the function will return early, effectively preventing any damage from being applied.

#### Code Modification:

```csharp
if (base.CompareTag("Player"))
{
    return;
}
```

> as following
> 
> ```csharp
> public virtual void Damage(float damage, GameObject instigator, float flickerDuration, float invincibilityDuration, Vector3 damageDirection, List<TypedDamage> typedDamages = null)
> {
>     if (base.CompareTag("Player"))
>     {
>         return;
>     }
>     if (!this.CanTakeDamageThisFrame())
>     {
>         return;
>     }
>     damage = this.ComputeDamageOutput(damage, typedDamages, true);
>     float currentHealth = this.CurrentHealth;
>     if (this.MasterHealth != null)
>     {
>         currentHealth = this.MasterHealth.CurrentHealth;
>         this.MasterHealth.SetHealth(this.MasterHealth.CurrentHealth - damage);
>     }
>     else
>     {
>         this.SetHealth(this.CurrentHealth - damage);
>     }
>     this.LastDamage = damage;
>     this.LastDamageDirection = damageDirection;
>     if (this.OnHit != null)
>     {
>         this.OnHit();
>     }
>     if (invincibilityDuration > 0f)
>     {
>         this.DamageDisabled();
>         base.StartCoroutine(this.DamageEnabled(invincibilityDuration));
>     }
>     MMDamageTakenEvent.Trigger(this, instigator, this.CurrentHealth, damage, currentHealth);
>     if (this.TargetAnimator != null)
>     {
>         this.TargetAnimator.SetTrigger("Damage");
>     }
>     if (this.FeedbackIsProportionalToDamage)
>     {
>         MMFeedbacks damageMMFeedbacks = this.DamageMMFeedbacks;
>         if (damageMMFeedbacks != null)
>         {
>             damageMMFeedbacks.PlayFeedbacks(base.transform.position, damage, false);
>         }
>     }
>     else
>     {
>         MMFeedbacks damageMMFeedbacks2 = this.DamageMMFeedbacks;
>         if (damageMMFeedbacks2 != null)
>         {
>             damageMMFeedbacks2.PlayFeedbacks(base.transform.position, 1f, false);
>         }
>     }
>     this.UpdateHealthBar(true);
>     this.ComputeCharacterConditionStateChanges(typedDamages);
>     this.ComputeCharacterMovementMultipliers(typedDamages);
>     if (this.MasterHealth != null)
>     {
>         if (this.MasterHealth.CurrentHealth <= 0f)
>         {
>             this.MasterHealth.CurrentHealth = 0f;
>             this.MasterHealth.Kill();
>             return;
>         }
>     }
>     else if (this.CurrentHealth <= 0f)
>     {
>         this.CurrentHealth = 0f;
>         this.Kill();
>     }
> }
> ```

### 4. Save the Modified Module:

- After editing the `Damage` function, save the changes by selecting `File > Save Module` in dnSpyEx.

### 5. Test the Game:

- Restart the game. The player character should now be immune to damage. This allows you to approach the gun without getting shot by the turret.

### 6. Obtain the Flag:

- Jump to reach the flag.
- Open the inventory by pressing `i` to get the actual flag.

## Flag:

<details>
<summary>Flag</summary>
GHCTF{this_is_the_first_flag_woot
}  
<br/>
</details>

</details>

# [Next Challage](level2.md)
