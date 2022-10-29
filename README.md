# Path Finding Algorithm - Python

## Introduction

A path finding algorithm that discovers a whole grid area as efficiently as possible using a different number of "bots" while avoiding "walls".

## Technologies

Python
Libaries: 
- matplotlib
- numpy
- cmath

## Running

```sh
python main.py
```

Then press 'q' to begin.

## How it works

Algorithm Description:
 
- get unexplored areas
    Iterate through 'explore_map' columns and rows until you find an unmapped value.
        When you find an unmapped value append that to 'unexplored_areas'
            return 'unexplored_areas' containing all the coords of unmapped areas.

- get new destination
    first, assume the closest position is the first coord in unexplored_areas
        calculate the distance between the current position of the bot and this assumed closest position
            iterate through the rest of the 'unexplored_areas'
                for each unexplored coord, calculate the distance between current position and unexplored coord
                    compare this distance with the current "closest" position
                        assign whichever value is smaller and hence whatever distance is shorter to 'closestPos'
                            return 'closest pos'

- update explore map
    iterate through 'route'
        for every position in route, change value of position to planned if it is currently unmapped
            also specifically change destination to planned in case this was missed
                return updated explore map

- update position
    specifically change curPos to 2nd coord in 'route' which is now the new position of the bot
        if this is the final destination then change dest to an empty array
            mark the new curPos of the bot as mapped in explore map
                delete the first value of 'route' as the bot has already moved past this
                    return all updated val

## Results

ITERATIONS:

5 bots = 528
10 bots = 277
15 bots = 211

## Screenshots
![Screenshot 1](Screenshot1.png?raw=true)
