
# Learning journal

## 10/11/2020
I have learned how to create a repository

## 10/11/2020
I had a problem when I was making my first tutorial which was the "D Top Down Player Control Tutorial. The problem was that I made a varible for the rigidbody 2D but I didn't put a rigidbody on the player character and this stopped my game from working. I fixed this problem by adding a rigidbody 2D onto the player  character.

using System.Collections;

using System.Collections.Generic;

using System.Runtime.CompilerServices;

using UnityEngine;

public class PlayController : MonoBehaviour {

  public float speed;

  private Rigidbody2D rb;

  private Vector2 moveVelocity;
