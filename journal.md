
# Learning journal

## 10/11/2020
I have learned how to create a repository

## 10/11/2020
I had a problem when I was making my first tutorial which was the 2D Top Down Player Control Tutorial. The problem was that I made a varible for the rigidbody 2D but I didn't put a rigidbody on the player character and this stopped my game from working. I fixed this problem by adding a rigidbody 2D onto the player  character.

using System.Collections;

using System.Collections.Generic;

using System.Runtime.CompilerServices;

using UnityEngine;

public class PlayController : MonoBehaviour {

     public float speed;

     private Rigidbody2D rb;

     private Vector2 moveVelocity;

## 12/11/2020
I had a problem with my second tutorial which was my 2D Enemy AI Follow tutorial. The problem that i encountered was that the enemy wouldn't follow the player even when I tagged the player with the "Player" tag. The enemy didn't follow the player because in the script where it said target = "GameObject.FindGameObjectWithTag("Player").GetComponent<Transform>();" I wrote "player" instead of "Player". I fixed this by putting "Play" in the line "GameObject.FindGameObjectWithTag("Player").GetComponent<Transform>();"

## 14/11/20
The problem that I encountered while making the script for my Shooting Enemy AI tutoiral was that i couldn't get the enemy to shoot projectile at the player, the enemy was creating projectiles but it didn't shoot at the player so what I did was making a new script for the projecttile and told it to target the player by "player = GameObject.FindGameObjectWithTag("Player").transform;" 

After this problem I had another porblem where the projectile doesn't dissapear when it collide with the player. I fixed this by saying that when whenever the projectile touches the a object with tag "PlayerW, it will destrory itself.

void OntriggerEnter2D(Collider2D other) {

    if (other.CompareTag("Player")){
        DestroyProjectile();
    }
}

## 20/11/2020
I had an issue with the game for the coding model where I couldn't get my character to jump. I made this work by adding a game public called "groundcheck" and say that whenever the character reaches the ground it will be able to jump again.

grounded = Physics.Raycast(groundcheck.transform.position, Vector2.down, 0.1f, ground);

        if (Input.GetAxis("Jump") != 0 && grounded == true)
        {
            rb.velocity = new Vector3(rb.velocity.x, JumpSpeed, rb.velocity.z);
            
        }
    }

## 23/11/2020
I had another problem with my game where the camera was going through the wall whenver the character is near the wall, this caused the wall to block the view of the player. I managed to fixed the problem by using raycast method and said that whenever the raycast hit the wall, the mesh of the wall would get disabled which allowed the player to see through the wall.

RaycastHit hit;

        if (Physics.Raycast(transform.position, Target.position - transform.position, out hit, 4.5f))
        {
            if (hit.collider.gameObject.tag != "Player")
            {
                Obstruction = hit.transform;
                Obstruction.gameObject.GetComponent<MeshRenderer>().shadowCastingMode = UnityEngine.Rendering.ShadowCastingMode.ShadowsOnly;

                if (Vector3.Distance(Obstruction.position, transform.position) >= 3f && Vector3.Distance(transform.position, Target.position) >= 1.5f)
                {
                    transform.Translate(Vector3.forward * zoomSpeed * Time.deltaTime);
                }

            }
            else
            {
                Obstruction.gameObject.GetComponent<MeshRenderer>().shadowCastingMode = UnityEngine.Rendering.ShadowCastingMode.On;
                if (Vector3.Distance(transform.position, Target.position) < 4.5f)
                {
                    transform.Translate(Vector3.back * zoomSpeed * Time.deltaTime);
                }
            }
        }
    }

## 29/11/2020
I encountered another problem where the player would clip through objects whenever they tried to fly toward the object, this probllem is in my grappling hook/flying script. I fixed this problem by problem by going in my script and change the value of of the grapplespeed varible from 10.0f to 6.8f, this stopped the character from going through the wall or any other objects.

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class GrappleHook : MonoBehaviour
{

     private Rigidbody rb;
     public float speed;
     private PlayerController movementScript;
     public float grappleDistance;
     public float grappleSpeed = 6.8f;

