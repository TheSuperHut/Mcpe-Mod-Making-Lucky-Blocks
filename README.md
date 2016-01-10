# Mcpe-Mod-Making-Lucky-Blocks
Basic setup for making lucky blocks!
Learn how to add certian functions!!!

Your imagination is the limit on lucky blocks, there are also way more functions to add!

//This is how you would make a entity riding another entity//
nameofchoice=Level.spawnMob (x, y+1, z, 19, "mob/mobofchoice.png");
othernameofchoice=Level.spawnMob (x, y+1, z, 84, "mob/mobofchoice.png");
Entity.rideAnimal(nameofchoice, bat);
clientMessage("Insert client message here")

//dealing damage
function attackHook(attacker,victim)
{
if (getCarriedItem()==600) 
{
Entity.setHealth(victim,5);
}

// How to add an item
ModPE.setItem(id,texture,textureData,name,stackLimit);

//This is how you would make a spawn egg//
ModPE.setItem(795, "your_mob", 0, "Name Here :(");
function useItem(x, y, z, itemId, blockId, side) 
{
if ((itemId === 795)) 
{
Level.spawnMob (x, y+1, z, 10, "mob/chicken.png");

//How you can make a block//
Block.defineBlock(151,"Block Name",[["block_name", 0],["block_name", 0],["block_name", 0],["block_name", 0],["block_name", 0],["block_name", 0]]);Block.setShape(151, 0, 0, 0, 1, 4/4, 1); Block.setDestroyTime(151,.5);
Block.setExplosionResistance(151,80);

//How to add an item recipie//
Item.addShapedRecipe(151,1,0,["zzz","zlz","zzz"],["z",154,0,"l",245,0]);

//How to make a block be set//
setTile(x+1,y,z-1,153)

//How to make a message on screen//
clientMessage("Insert client message here")


//Custom mobs//
var Bob = Level.spawnMob(x, y+1, z, 32,"mob/zombie.png" );
Entity.setHealth(Bob,150);
Entity.setNameTag(Bob,"Bob");


//get player location
var x = getPlayerX();
var y = getPlayerY();
var z = getPlayerZ();
var  player = getPlayerEnt();
setPosition(player,x+0.5,y,z+0.5);

//Random amount of drops//
Level.dropItem(x,y+2,z,0,264,Math.floor(Math.random()*(15)+1),0);

//Droping items//
Level.dropItem(x,y+1,z,0,258,1)

//Set the time!//
Level.setTime(13000)

//Expolde//
explode(x,y,z,6)

//Mob Effects//
Entity.addEffect(getPlayerEnt(), MobEffect.healthBoost, 240*20, 0, false, true);
