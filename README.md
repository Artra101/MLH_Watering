This is a copy of etcipnja's Farmware MLH that I changed a bit to my needs for the farmbot I had to make for a school project.
# Problem:

When you have to deal with a lot of plants you might be puzzled that you have to create a dedicated sequence for each
instance of a plant. For exmaple: if you have 10 carrots - you probably need to create a watering sequence for every carrot
individually.

# Solution:

The idea is to write a loop that executes needed sequences for all planted plant.
- Apply filters to select plants to be treated       		(Example: Select all Carrots with status "planned")
- Execute initial sequence                                  "MLH Mount Watering Nozzle"
- For each plant:
    - Move to plant's location
    - Execute a sequence at plant's location                "MLH watering"
- Execute end sequence                                      "MLH Dismount Watering Nozzle"

# Reference:

- FILTER BY PLANT NAME
    - Filter by plant names (comma separated) for example "Carrot, Beets", case insensitive, '*' means select all
- INIT SEQUENCE NAME
    - "MLH Mount Watering Nozzle"
- SEQUENCE NAME AFTER MOVE
    - "MLH watering"
- END SEQUENCE NAME
    - "MLH Dismount Watering Nozzle"
- DEFAULT Z AXIS VALUE WHEN MOVING
    - Z coordinate for the head while moving to the plant's location


# Installation:

Use this manifest to register farmware
https://raw.githubusercontent.com/Artra101/MLH_Watering/master/MLH_Watering/manifest.json

# Bugs:

I noticed that if you change a parameter in WebApplication/Farmware form - you need to place focus on some other
field before you click "RUN". Otherwise old value is  passed to farmware script even though the new value
is displayed in the form.


# Credits:

The original idea belongs to @rdegosse with his Loop-Plants-With-Filters. https://github.com/rdegosse/Loop-Plants-With-Filters/blob/master/README.md
This Farmware - is a simplified version of it.



