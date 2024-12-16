# Entry 2
##### 12/9/24

### content
This year we have our Sep 11 freedom project where I have been learning code using kaboom. My learning tool is Kaboom.js and so far I’ve been using it and learning a lot about it through my Learning Logs. I have been trying out different codes and experimenting with making a cooking game. My partner is Johnny Yang and together we are working on making a fun RPG cooking game where you can explore the world and enjoy cooking. The way we've been learning our codes are from the websites. One of these websites is the [kaboom website](https://kaboomjs.com/) in this website you can see how different codes are used and you can see the games that they made. This is where I do most of my tinkering and find codes that could help for the future. Another thing I used was youtube videos like [making a game with Kaboom](https://www.youtube.com/watch?v=hgReGsh5xVU) [learning log.md](../tool/learning-log.md). This is the learning log which is where my notes are for these codes I learned. Some of these code I learned was:

`````js
const SPEED = 500
const ENEMY_SPEED = 300
const BULLET_SPEED = 1000
`````
So the const makes it a variable which is a string and the SPEED makes it so it can be faster or slower.
Another thing I learned is what the character is doing. The code for this is 
`````js
	state("move", [ "idle", "attack", "move" ]),
`````
````js
enemy.onStateEnter("idle", async () => {
	await wait(0.1)
	enemy.enterState("attack")
})
````
This code makes it so the character becomes idle for 0.1 after attacking. 

```js
enemy.onStateEnter("attack", async () => {
```
This is saying that when attacking there will be a bullet. 

`````js
if (player.exists()) {

		const dir = player.pos.sub(enemy.pos).unit()

		add([
			pos(enemy.pos),
			move(dir, BULLET_SPEED),
			rect(100, 12),
			area(),
			offscreen({ destroy: false }),
			anchor("center"),
			color(YELLOW),
			"bullet",
		])

	}

	await wait(0.1)
	enemy.enterState("move")

})
`````
This code makes it so if a player exists the enemy will attack you and we can change the bullets sizes and color and other properties.

`````js
// Mouse handling
onUpdate(() => {
	if(isMouseDown("left") && isMouseMoved()) {
		cameraPosition = cameraPosition.sub(mouseDeltaPos().scale(1 / cameraScale))
		camPos(cameraPosition)
	}
})

onScroll((delta)=>{
	cameraScale = cameraScale * (1 - 0.1 * Math.sign(delta.y))
	camScale(cameraScale)
})
`````
These are the codes which make it so when you move it will move with you and the scroll will change the size. Now let's add this with other codes and see what happens.

`````js
kaboom()

let cameraPosition = camPos()
let cameraScale = 1

// Loads a random 2500px image
loadSprite("big yoshi", "/examples/sprites/YOSHI.png")

add([
	sprite("big yoshi"),
])

// Adds a label
const label = make([
	text("Booooooo"),
])

add([
	rect(label.width, label.height),
	color(0, 0, 0),
])

add(label)

// Mouse handling
onUpdate(() => {
	if(isMouseDown("left") && isMouseMoved()) {
		cameraPosition = cameraPosition.sub(mouseDeltaPos().scale(1 / cameraScale))
		camPos(cameraPosition)
	}
})

onScroll((delta)=>{
	cameraScale = cameraScale * (1 - 0.1 * Math.sign(delta.y))
	camScale(cameraScale)
})
`````
These are the codes I have learned from the last time. 
   
## EDP 
EDP or Engineering Design Process is the part of the project you are on. There are 8 different parts. The problem I am trying to solve is people being too scared to cook. I plan on making a game that everyone can enjoy and not be scared of cooking. You can learn many things like how to cook, different recipes and have fun with friends in general. I finished solving the problem and brainstorming everything. The part I am on right now is the part 4 of the EDP which is planning. I am planning on how the game should look and how the game will work. This is the part of the EDP part I am on. 

## Skill
I have learned many skills while working on this project. Some of which is communication and testing codes.

### Communication 

Communication is one of the most important skills to learn, you have to communicate with many people. SinceI have a partner I need to communicate and talk to them about what we should do for the project. Also how we should do it. Another thing that is important is asking my friends for help, this is developing my communication skills and will help me when I get a job.



### Testing codes 

Testing code isn’t a thing I used to do. However, I learned that testing codes is a really important skill to learn. You should always be brave and try code. When something doesn’t work you should always try it and keep trying until you get it. This is something I have been doing for the Learning Log. I will keep being brave and test code for the future of this game.

### Winter break

So during the winter break, my plan is to talk to Johnny Yang and code together. We will learn more code and help each other when we need help. We will start making the game and a outline for the game as well. This will be a long break so after we finish our plan is to make sure everything works and it is playable. Learning if there is a way to play with other people, and add music, animation and different levels for players to play with. I know this might be hard so we might not finish during the break but we will try to do most of these ideas and hope they turn out great. Also that everything works and runs correctly. 




[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)



