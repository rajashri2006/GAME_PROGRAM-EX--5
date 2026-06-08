# GAME_PROGRAM-EX--5
Making Player to collect the ammo and increase the bullet spawn count.
# Aim
To implement a gameplay feature where the player collects ammo pickups in the game world. Upon collecting ammo, the player's ammo count increases, enabling more bullet spawns (shots).

# Procedure
Setup Player Character Open your PlayerCharacter Blueprint.s Add a new Integer variable named AmmoCount. Set an initial default value (e.g., AmmoCount = 10). Ensure you have a shooting mechanism in place that uses AmmoCount to determine if a bullet can be fired.
Create Ammo Pickup Blueprint Go to the Content Browser → Right-click → Blueprint Class → Select Actor → Name it BP_AmmoPickup. Add components: Static Mesh: Representing the ammo (e.g., a bullet or crate). Sphere Collision: To detect overlap with the player. In the Event Graph of BP_AmmoPickup: Use OnComponentBeginOverlap on the Sphere Collision. Cast to PlayerCharacter. Increase the player’s AmmoCount (e.g., AmmoCount += 5). Optionally, play a pickup sound or effect. Destroy the ammo pickup actor.
Update Shooting Logic (Optional) In your player’s shooting logic: Before spawning a bullet, check if AmmoCount > 0. If true: Spawn bullet. Decrease AmmoCount by 1.
Place Ammo in the World Drag instances of BP_AmmoPickup into your level from the Content Browser. Adjust position, mesh, and pickup range as needed.
# Output

<img width="1061" height="387" alt="image" src="https://github.com/user-attachments/assets/2e11e379-e96e-4a10-82f4-dd2118689d66" />

<img width="647" height="247" alt="image" src="https://github.com/user-attachments/assets/9faab63b-c199-4779-be2c-1213c74f841d" />

<img width="412" height="233" alt="image" src="https://github.com/user-attachments/assets/4101fc2f-d003-46d6-a95a-e75f69a95fd1" />

# Result
The player starts with a limited number of bullets. When the player overlaps with an ammo pickup: The ammo is collected. The player's AmmoCount increases. The player can now fire additional bullets based on the updated ammo count.
