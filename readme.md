# Spacewar! prototype

Gameplay in Spacewar! is very simple; it is a 2d game in which each player controls one of two space ships
(historically the ‘needle’ and the ‘wedge’), and is tasked with destroying the other whilst manoeuvring around,
and avoiding falling into, the gravity well of a star.
A description of the original gameplay can be found here:

Link to [Spacewar! wikipedia](https://en.wikipedia.org/wiki/Spacewar!#Gameplay)

## Historical gameplay (info from wiki)

Picture of gameplay of Spacewar! on a PDP-1. The moving spaceships and missiles leave trails behind them due to the CRT monitor slowly fading when lit.
The gameplay of Spacewar! involves two monochrome spaceships called "the needle" and "the wedge", each controlled by a player, attempting to shoot one another while maneuvering on a two-dimensional plane in the gravity well of a star, set against the backdrop of a starfield. The ships fire torpedoes, which are not affected by the gravitational pull of the star. The ships have a limited number of torpedoes and supply of fuel, which is used when the player fires the ship's thrusters. Torpedoes are fired one at a time by flipping a toggle switch on the computer or pressing a button on the control pad, and there is a cooldown period between launches. The ships remain in motion even when the player is not accelerating, and rotating the ships does not change the direction of their motion, though the ships can rotate at a constant rate without inertia.

Each player controls one of the ships and must attempt to shoot down the other ship while avoiding a collision with the star or the opposing ship. Flying near the star can provide a gravity assist to the player at the risk of misjudging the trajectory and falling into the star. If a ship moves past one edge of the screen, it reappears on the other side in a wraparound effect. A hyperspace feature, or "panic button", can be used as a last-ditch means to evade enemy torpedoes by moving the player's ship to another location on the screen after it disappears for a few seconds, but the reentry from hyperspace occurs at a random location, and in some versions there is an increasing probability of the ship exploding with each use.

Player controls include clockwise and counterclockwise rotation, forward thrust, firing torpedoes, and hyperspace. Initially, these were controlled using the front-panel test switches on the PDP-1 minicomputer, with four switches for each player, but these proved to be awkward to use and wore out quickly under normal gameplay, as well as causing players to accidentally flip the computer's control and power switches. The location of the switches also left one player off to one side of the CRT display due to the limited space in front of the computer, which left them at a disadvantage. To alleviate these problems, Saunders created a detached control device, essentially an early gamepad. The gamepad had a switch for turning left or right, another for forward thrust or hyperspace, and a torpedo launch button. The button was silent so that the opposing player would not have a warning that the player was attempting to fire a torpedo during a cooldown period.

## Idea to build

- BP_ship (Pawn)  - maybe 2 types? "the needle" and "the wedge"? Selectable?)
  - Inputs by player:
    - rotation (A/D, Left/Right) - only rotates the ship, doesn't do anything else
    - show (W / Up) - creates instance of BP missile
    - thrust (S / Down) - turns on engine and fly towards direction facing right now
  - have stats, that affect what player can do with them
    - fuel - decreases on use, once 0, ship cannot use thrust
    - ammo - limited amount of shots, once 0, ship cannot shoot
    - direction
    - velocity
  - spawns:
    - BP_missile (Actor) - a shot, no reaction to gravity, goes in direction where was originally shot till hits target (despawn + explosion) or just dismiss after some time (just despawn)
  - can die by:
    - hit with missile - increase score of author of the shot
    - hit with other ship - tie
    - hit with the collapsing start - decrease score of the ship
- BP_star (Actor) - object in the world with own gravity field, if something touches it, star destroys that object

## Some interesting links

- [Blueprint Networking Compendium by Cedric Neukirchen](http://cedric-neukirchen.net/Downloads/Compendium/UE4_Network_Compendium_by_Cedric_eXi_Neukirchen.pdf)
- [Spacewar! Original 1962 game code running on a PDP-1 emulator in JavaScript](https://spacewar.oversigma.com/)

## Resources

- [Photo](https://unsplash.com/s/photos/starry-sky) by [Kai Pilger](https://unsplash.com/@kaip)
