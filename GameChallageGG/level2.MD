## # Level 2

## Objective

The goal is to modify the game so that the player has unlimited ammo.

## Solution

> Search for the `WeaponAmmo` class.

Just find these functions and modify them as follows:

- In `EnoughAmmoToFire`, return `true` to ensure you always have ammo.
- In `ConsumeAmmo`, `FillWeaponWithAmmo`, and `EmptyMagazine`, leave the functions empty to keep the ammo count constant.

```csharp
public override bool EnoughAmmoToFire()
{
    // Always enough ammo to fire
    return true;
}

protected override void ConsumeAmmo()
{
    // No ammo is consumed, so unlimited ammo
}

public override void FillWeaponWithAmmo()
{
    // Do nothing, unlimited ammo
}

public override void EmptyMagazine()
{
    // Do nothing, unlimited ammo
}
```

## Flag:

<details>
<summary>Flag</summary>
GHCTF{oops_sorry_mr_unicorn}  
<br/>

</details>

# [Next Challange](level3.MD)
