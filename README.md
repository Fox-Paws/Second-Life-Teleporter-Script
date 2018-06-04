# Second-Life-Teleporter-Script
Second Life is an online game/community where users interact with each other and have avatars which they can customize and use to move around the 3D world. There are objects which transport users and their avatars great distances quickly, which this pairing of scripts innovates.

Teleporters in Second Life are primitive objects which a user clicks to "sit" on the object, followed by the object blinking to the destination, kicking the user off the teleporter, then blinking back to its original location.
For teleporters to have multiple destinations, multiple primitive objects (usually in the form of 3D cubes with the name and pictures of the destination on it) are often used, with one object having one destination.
These destinations are normally hard-coded into the script or read from a plain text notecard contained in the inventory of the object.
For each object that has a destination, it must have a script running inside of it so the object (which is the teleporter) can function. This adds to "script time" of a region, which is how long a server must spend executing that script.

This script was a personal project and a challenge to myself to innovate this system.
It eliminates the need for multiple objects to have more than one destination, meaning one primitive object can have multiple possible teleport destinations.
Therefore, each destination only needs one primitive object (functioning as the teleporter) and two scripts running inside of it.
  (this is down from one object and one script for every possible destination from the current location)

This is done by combining a popular open-source teleportation script from that time with a very under-represented function in the LindenLabs scripting language.
This function returns the coordinates on the face of the 3D object where the user clicked. With this information, it is possible to divide the face into several regions, allowing multiple possible teleport destinations.
With this script, when a destination is selected, the teleporter communicates with the teleporter at the destination, acquires the destination coordinates, and takes the user there.
Due to this communication with the destination teleporter, the destinations automatically update simply by moving the teleporters in-world, instead of having to determine the coordinates and providing them to each teleporter when one is moved.

These scripts also had a sleep function, where they would run a very efficient 'touch detection' function instead of the computationally expensive function which returns the coordinates of the user's click.
This means that after a period of idle, the user would need to click on the teleporter to wake it up, then make their selection.
This feature reduced the script time load on the region/servers significantly.
