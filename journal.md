
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



