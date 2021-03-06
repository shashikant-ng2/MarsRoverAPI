# MarsRoverAPI


## Development Environment
 - C#/ .Net Core 2.1
 - This API uses swagger for API documentation


## Premise / Problem Statement

Develop a set of RESTful Web API web services to move a Mars rover after landing.

A rover’s position and location is represented by a combination of x and y coordinates and a letter representing
one of the four cardinal compass points. The plateau is divided up into a grid to simplify navigation. The default
starting position of the Rover is 0, 0, N.

In order to control a rover, NASA sends a simple string of letters. The possible letters are “L”, “R”, and “M”. “L”
and “R” makes the rover spin 90 degrees left or right respectively, without moving from its current spot. “M”
moves the rover forward one grid point, and maintains the same heading.

## Requirements

+ Create an endpoint to create a new instance of a Rover
  - Request Parameters:
    * RoverId, Integer, Required
    + RoverName, String, Required

+ Create an endpoint to rename an existing instance of a Rover
  - Request Parameters:
    * RoverId, Integer, Required
    + RoverName, String, Required

+ Create an endpoint to move an instance of a Rover
  - Request Parameters:
    * RoverId, Integer, Required
    + MovementInstruction, String, Required
    + Valid instructions letters include “L”, “R”, “M”. No other characters (or spaces)
should be allowed.
  - Response: 
    * RoverId, Integer
    + RoverName, String
    + CurrentX, Integer
    + CurrentY, Integer
    + CurrentDirection, String

+ Create an endpoint to retrieve the current position/direction of an instance of a Rover
  - Request Parameters:
    * RoverId, Integer, Required
  - Response: 
    * RoverId, Integer
    + RoverName, String
    + CurrentX, Integer
    + CurrentY, Integer
    + CurrentDirection, String  


## Example Scenario

Rover starts at 0, 0, N
1. Instruction: **"M"**. Move, [**Result:** 0, 1, N.]
2. Instruction: **“RMM”** . Rotate right, Move, Move. [**Result:** 2, 1, E.]
3. Instruction: **“LMMM”** . Rotate left. Move, Move, Move. [**Result:** 2, 4, N.]

