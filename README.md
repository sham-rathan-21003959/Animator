# Animator

## Aim:
To develop a animator using unity with C# prgram and move the animator.
## Algorithm:
### Step 1:
Download 2 crouch idle from maximo 3d. Drag it and drop it in unity asset.
### Step 2:
Select one crouch and in the inspector choose rig-> Animation type (humaniod) and then click update.
### Step 3:
Perform the step 2 for another crouch
### Step 4:
Select one crouch and in the inspector choose Animation-> Root transform rotation-> Based upon (original)  and check the Loop Time and click apply
### Step 5:
Perform the step 4 for another crouch
### Step 6:
Drag one crouch, put it in hierarchy and name it as Player.
### Step 7:
In the Player inspector we have Animator. Right click in Assets-> create -> Animator Controller (name it as IdleToCrouch)
### Step 8:
Drag the IdleToCrouch to the Controller option under the Animator in the inspector. Click that IdleToCrouch , a window opens and select parameter tab , create 2 parameter, InputX and InputY
### Step 9:
Select the another crouch and attach with Entry button and name it as movement. Right click it and choose create blend tree.
### Step 10:
Click the movement button, blend tree opens. Choose InputY in parameter and under the motion click ‘+’ sign and choose add the motion field twice.
### Step 11:
Drag the second crouch and put it motion field, then drag the first crouch and put it in the another motion field.
### Step 12: 
Uncheck the automata threshold and change the values -1 and 0 in first column( priority for the crouch). Create a C# file and name it as IdleToCrouch, drag it to the player
### Step 13:
Download a walking crouch from maximo 3d and drag it into unity. In the inspector select rig-> animation types(humanoid) -> Apply
### Step 14:
Select the crouch and in the inspector choose Animation-> Root transform rotation-> Based upon (original)  and check the Loop Time and click apply
### Step 15:
In blend tree, in blend type choose (2D Freedom Directional), parameter (InputX, InputY) , one crouch (0,-1,1) and walking (1,0,1). Bring the camera under the player 

## Program:
```
Developed by : S.Sham Rathan
Register no. : 212221230093

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class IdleToCruch : MonoBehaviour
{
    public Animator animator;
    public float InputX;
    public float InputY;
    // Start is called before the first frame update
    void Start()
    {
        animator = this.gameObject.GetComponent<Animator>();

    }

    // Update is called once per frame
    void Update()
    {
        InputX = Input.GetAxis("Horizontal");
        InputY = Input.GetAxis("Vertical");
        animator.SetFloat("InputX", InputX);
        animator.SetFloat("InputY", InputY);

    }
}

```

## Output:
![33](https://user-images.githubusercontent.com/93587823/202072588-f0564cec-8d65-4e8a-ab60-5a1757b8b4b3.png)
### Walking Frontward:
![11](https://user-images.githubusercontent.com/93587823/202072632-9c6fa392-7647-4f47-8763-c79ed952ef80.png)
### Walking Backward:
![22](https://user-images.githubusercontent.com/93587823/202072692-90c6cf32-bedc-4293-944f-0148cc29ccca.png)



## Result:
Thus, the animator was successfully developed in unity engine with the C#.

