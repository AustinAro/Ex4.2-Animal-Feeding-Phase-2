# Ex4.2-Animal-Feeding-Phase-2

### Name: Austin Aro A
### Reg No: 212224040038

## Aim:
To develop a animal feeding game-Phase-2 using unity.

## Algorithm:
### Step 1:
In the Hierarchy, create an Empty object called “SpawnManager”

### Step 2:
Create a new script called “SpawnManager”, drag the script and attach it to the Spawn Manager in the hierarchy , and open it

### Step 3:
Declare new public GameObject[ ] animalPrefabs;

### Step 4:
In the inspector assign the size as 3 , for each element drag the animals from prefabs folder into the array

### Step 5:
Double-click on one of the animal prefabs, then Add Component > Box Collider

### Step 6:
Check the “Is Trigger” checkbox

### Step 7:
Add a RigidBody component to the (banana)projectile and uncheck “use gravity”.

### Step 8:
Create a new DetectCollisions.cs script, then drag the scripts and add it to each animal prefab and banana, then open it and check it.

### Step 9:
For all the animal prefabs and food in th inspector (below the layer ) drop down the override option and choose apply all.

## PROGRAM:

## SPAWN MANAGER:
```
using UnityEngine;

public class spawnManager : MonoBehaviour
{
    public GameObject[] animalPrefab;
    public float spawnRangeX = 10;
    public float spawnPosZ = -8;
    public float startDelay = 2;
    public float spawnInterval = 1.5f;
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        InvokeRepeating("SpawnAnimal", startDelay, spawnInterval);
    }

    // Update is called once per frame
    void Update()
    {
        
    }
    void SpawnAnimal()
    {
       int animalIndex = Random.Range(0, animalPrefab.Length);
       Vector3 spawnPos = new Vector3(Random.Range(-spawnRangeX,spawnRangeX), 0, spawnPosZ);
       Instantiate(animalPrefab[animalIndex], spawnPos, animalPrefab[animalIndex].transform.rotation);
    }
}
```
## DETECT COLLIDER:
```
using UnityEngine;

public class collision : MonoBehaviour
{
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {

    }

    void OnTriggerEnter(Collider other)
    {
        Destroy(gameObject);
        Destroy(other.gameObject);
    }
}

```
## OUTPUT:

<img width="1918" height="1136" alt="Screenshot 2025-10-04 093018" src="https://github.com/user-attachments/assets/b1f881a8-4f2d-4e93-b772-be930e4459e8" />


## RESULT:
Animal feeding game-Phase-2 using unity is developed successfully.
