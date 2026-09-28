# MONOBEHAVIOUR-RIGIDBODY-_09-28-2026
C# GRID BASE MOVEMENT
// ATTACH THIS TO A CHARACTER Game.Object.Good for roquelikes puzzel game, tactics games.
// The character snaps to whole tile position rather than moving continously.

// CODE PROPER
using UnityEngine;
public class GridMovement : 







public foat tilesize = 1.0f; // how fast we glide between tiles (feel, not logic)
















void HandleInput()
{
    Vector3 = direction = Vector.zero;

    if(Input.GetKeyDown(KeyCode. W)) direction = Vector3.up;
    else if (Input.Get KeyDown(KeyCode. S)) direction  = Vector3.down;
    else if (Input.Get KeyDown(KeyCode. A)) direction = Vector3.left;
    else if (Input.Get KeyDown(KeyCode. D)) direction = Vector.right;

    if(direction !=Vector3.zero)
}
{
targetPosition = transform.position + direction * tilesize;
isMoving = True;
}
Vector3 SnapGrid(Vector3 pos)
{
    return new Vector3(
    Mathf.Round(pos.x / tilesize) * tilesize,
    Mathf.Round(pos.y / tlesize) * tilesize,
    pos.z
    );
}

}

//FREE (VECTOR BASED MOVEMENT)
//Attach this to a character GameObject. Good for top-down action games, paltforms
//(horizontal axis), twin-stick shooters, Movement is continous, not like locked,

using UnityEngine;

public class FreeMovement : MonoBehaviour
{
    public float movespeed = 5f;

    void update()
    {

    }


public float moveForce =  10 f;
public float moveForce = 7f;
public float moveForce = 6f;

private Rigidbody2D rb;
private bool isGrounded = false;

void Start()
{
    // Read input Update (input should always be checked every frame)
    if (Input.GetKeyDown)(Keycode.space) && is grounded)
    {
        rb.Addforce(Vector2.up * jumpforce, ForceMode2D.Impulse);
        {

        }
    }


    rb = GetComponent<RigidBody2D>()
}
{
Void Update()
}
// Physics changes belong in Fixedupdate, which runs on a fixed timestep
//independent of frame rate - keep physics simulation stable.
float horizontal = Inpaut.GetAxis("Horizontal");
rb.Addforce(new Vector2(horizontal * moveForce, 0f));
}
// Clamp horizontal speed si the character doesn't accelerate Foreever
{
    {
        If (Math.Abs(rb.velocity.x)> maxspeed)
        {
            rb.velocity = newVector2(Mathf.Sign(rb.velocity.x)) *maxSpeed,



          IsGrounded
        }

 
    }
    Void onCollisionEnter2D(Collision2D collision)
    IsGrounded = false;
}
