# do2_mob_mover
Moves mobs in TangoTeks Decked out 2 dungeon. 

## How To Use
### Option 1
Save the datapack into your datapacks folder for your world (for a server: minecraft/server/world/datapacks), this will give you the predetermined names and positions for the ravages, and wardens.

### Option 2
Review the following spreadsheet: https://docs.google.com/spreadsheets/d/1oXqsJjgZ1O3CYUdrNCGsxQilde0XJVO-H_kA45uvJqg/edit?usp=sharing and download to your personal machine.
1. Add your names to the Names Sheet
2. Add your preferred spawn locations to the Ravager/Warden Spawn location sheets.
3. In the 'Ravager Commands' sheet, ensure the Constants B2, C2, D2 look good for your use
4. The 9 locations for each mob is pulled from the previous sheet, as well as the name for the ravager.
5. Do step 3 and 4 for the 'Warden Commands' Sheet.
6. On the Summon Commands sheet, filter on Column A (Location) on 1, 2, 3, etc.
7. Copy these into the data/mob_mover/functions/power_1.mcfunction, power_2.mcfunction, power_3.mcfunction, etc.
8. Copy the values from 'Kill Newest Entities Commands' - this will remove each of the new mobs with whatever name you chose on previous sheets.

### In game
In Minecraft, using a dropper elevator, dispenser, and shulkers with several unstackable items in them use a comparator to pull out the value. Using one of the start trigger lines, I chose the one off the door and input shard see image Dropper elevator location.

After you can put the commands into command blocks: 
1. Command block 1: {'Type':'Impulse', 'Conditional':'Not Conditional', 'Redstone':'Needs Redstone'} execute if block <x> <y> <z> redstone_wire[power=<value>] run function kill_mobs *note* this value is active redstone so if its signal strength 5 coming out of your comparator, it will be the 5th furthers line out. 
2. Command block 2: {'Type':'Chain', 'Is it Conditional':'Not Conditional', 'Redstone':'Always Active'} function power_<value>
3. Do this for the number of shulkers in your dispenser.

Dropper elevator location: https://www.reddit.com/media?url=https%3A%2F%2Fpreview.redd.it%2Fr54fq76e9cbc1.png%3Fwidth%3D1920%26format%3Dpng%26auto%3Dwebp%26s%3D88e8c81fdcbfc0c2f4960a9d4db5507e7859ab9a

Command block output: https://www.reddit.com/media?url=https%3A%2F%2Fpreview.redd.it%2Fenboo1zl9cbc1.png%3Fwidth%3D1920%26format%3Dpng%26auto%3Dwebp%26s%3Dc2f0aded8968110d800f7c3dcec932a92a11ccf0
*Note* for the command blocks, they all have to be pointing into the next block in the chain, not like how they are shown here.

Signal examples:
1. Signal strength 1: https://www.reddit.com/media?url=https%3A%2F%2Fpreview.redd.it%2Fopxm6pqm9cbc1.png%3Fwidth%3D1920%26format%3Dpng%26auto%3Dwebp%26s%3Dc5c95816e35292523b3adc291f9dbe879e1d1554
2. Signal strength 4: https://www.reddit.com/media?url=https%3A%2F%2Fpreview.redd.it%2Fz5ewgmqm9cbc1.png%3Fwidth%3D1920%26format%3Dpng%26auto%3Dwebp%26s%3D70e97f126f72733960a785f69b382fea7c8f065e
3. Signal strength 7: https://www.reddit.com/media?url=https%3A%2F%2Fpreview.redd.it%2F0iaa7oqm9cbc1.png%3Fwidth%3D1920%26format%3Dpng%26auto%3Dwebp%26s%3D23bbe72816d2e8eb372f47aa2799ccd57084965a

## TODO
Add a script to scrape the values and add them to the file automatically for moving positions, changing names, etc.
