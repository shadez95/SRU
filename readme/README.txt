1. Make sure you have the following addons running on your server: extDB2
2. Copy the @sru_pdb folder to your server and activate it
3. Import db.sql to your database. The database name has to be "arma3"
4. Copy the extdb-conf.ini from this readme folder to your extDB2 addon directory
5. Open that file and scroll to the bottom. You have to put in your Username,Password and IP for the database
6. Now all you have to do is to alter your mission. I made a sample mission in the PDB.VR folder. There you can see the important changes in the initPlayerLocal.sqf, initPlayerServer.sqf and initServer.sqf
7. Everything should be working now. 

To prevent an object from being saved and loaded from and to the database, put this into the init of the object: this setVariable ["sru_disable_pdb",1,true];

Some facts:

Once a player connects to the server, there will be an entry in the table "player". Thats how you can check if it works or not (it should).

The server saves player position,inventory and so on every minute

Vehicle's are saved every minute or when a driver of a vehicle exits the vehicle

If you use a vehicle addon, it might be possible, that the class is not included in our addon. We will make it modular at a later point which gives you the possibility to add vehicles on your own. If we wouldnt restrict it, our addon would save every object on the map (which could be way too much)