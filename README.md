# Ex.No.6-Jumping-or-Flocking-behavior-in-Unity
### DATE:  21-04-2025                                                                        
### REGISTER NUMBER : 212223040099
### AIM: 
To write a program to simulate the process of jumping in Unity.
### Algorithm:
```
1. Create a new 3D Unity project
2. Add a Plane
3. Right-click Hierarchy → 3D Object → Plane → Rename to Ground
4. Add a Cube (Player)
5. Right-click Hierarchy → 3D Object → Cube → Rename to Player
6. Set Position: (0, 0.5, 0)
7. Add a Rigidbody to the Player
8. With the Player selected: Inspector → Add Component → Rigidbody
9. Set Constraints > Freeze Rotation X, Z (optional for stability)
10.Create the Jump Script and Apply the Script Player
11.Run the game
Press Play
Press Spacebar to jump
Your cube should only jump when touching the ground
```
###
**Program **
```
using UnityEngine;

public class PlayerJump : MonoBehaviour
{
    private Rigidbody rb;
    public float jumpForce = 5f;
    private bool isGrounded;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space) && isGrounded)
        {
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
            isGrounded = false;
        }
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.CompareTag("Ground"))
        {
            isGrounded = true;
        }
    }
}
```
### Output:

BEFORE

![{A729D225-52FB-4AB4-8013-511C31F07871}](https://github.com/user-attachments/assets/a9d8c166-4adf-4259-a0ff-90e281340559)



AFTER


![{30A5B29D-5441-4FD7-94BA-0A84FCA2C575}](https://github.com/user-attachments/assets/9e95c8f7-88be-43ef-ae8e-0d25e3bfad74)






### Result:
Thus the simple jumping behavior was implemented successfully.
