# Tool Learning Log

## Tool: **kaboom**

## Project: **cooking game**

---

### 10/6/24:
To start with kaboom I started with the base for kaboom and where my game will be using the src provided by kaboom on their website into my own html on jsbin.
![start](kaboomstart.png)  
The code for this is:
`````
<script type="module">

import kaboom from "https://unpkg.com/kaboom@3000.0.1/dist/kaboom.mjs";

kaboom();

]);

</script>
`````
You would add the code to your html in the script. I then started to change some code I had copied from the Kaboom add.

### 10/20/24
The first thing I learned was how to add sprite, the code for this is: 
`````js
// start the game
kaboom()

// define gravity
setGravity(2400)

// load a default sprite
loadBean()

// add character to screen, from a list of components
const player = add([
    sprite("bean"),  // renders as a sprite
    pos(120, 80),    // position in world
    area(),          // has a collider
    body(),          // responds to physics and gravity
])

// jump when player presses "space" key
onKeyPress("space", () => {
    // .jump() is provided by the body() component
    player.jump()
})
`````
This is the basic to add a sprite, you can change the name and give it a different position.
Another code I learned was adding different sprite together and making shapes.
`````js
add([ pos(80, 240), 
rect(700, 20),
outline(4), 
area(), ])
`````
`````js
	add([
    pos(350, 200),
    circle(16),
])
``````
As you can see i add rectangle and a cricle using the shape name and putting it using position.
So with all these together I made 
`````js
kaboom()

loadSprite("bean", "/sprites/ghosty.png")
loadSprite("ghosty", "/sprites/bean.png")


const player = add([
	sprite("bean"), 
	pos(200, 200),
	rotate(0),    
	anchor("center"),
])


player.onUpdate(() => {

	player.angle += 120 * dt()
})

// Add multiple game objects
for (let i = 0; i < 3; i++) {


	const x = rand(0, width())
	const y = rand(0, height())

	const ghost = add([
		sprite("ghosty"),
		pos(x, y),
	])
	add([
    pos(80, 240),
    rect(700, 20),
    outline(4),
    area(),
])
	add([
    pos(350, 200),
    circle(16),
])
	add([
    pos(500, 200),
    circle(16),
])
}
`````
![k](kaboom.js.png)
This is the thing I made from using all the code, I will use more of these code for the future and hone my skills further. So for the freedom project I will be ready to make a game with some prior knowledge.

## LL2

### 10/26/24

After learning things from LL1. I used that and other codes I learned for LL2. So the first thing I learned was giving blocks a mass and being able to move it. 
`````js
body({ mass: 10 }),
`````
This code allowed me to give my sprites a mass and was able to more it.
Another thing I learned was 
`````js
onKeyDown(" ", () => {
	player.angle += SPEED * dt()
	player.move(0, -SPEED)
	player.move(0, SPEED)
})
`````

All three of these are things you can put in the code. One of the rotate the sprites, another cod emoves the sprites up or down. The last one moves it left or right.

Now if we go to the playground, I used the collision and changed the code for I changed it so you can use wasd to move, made it so the sprites are different and so the metal and grass block can move when you push it.

The code for this is 

`````js
// Collision handling
kaboom({
	scale: 2,
})

loadSprite("bean", "/sprites/ghosty.png")
loadSprite("ghosty", "/sprites/bean.png")
loadSprite("grass", "/sprites/grass.png")
loadSprite("steel", "/sprites/steel.png")

const SPEED = 320

const player = add([
	sprite("bean"),
	pos(80, 40),
	color(),
	rotate(0),
	area(),
	body(),
])


onKeyDown("a", () => {
	player.move(-SPEED, 0)
})

onKeyDown("d", () => {
	player.move(SPEED, 0)
})

onKeyDown("w", () => {
	player.move(0, -SPEED)
})

onKeyDown("s", () => {
	player.move(0, SPEED)
})

onKeyDown("t", () => {
	player.angle += SPEED * dt()
})

onKeyDown("g", () => {
	player.angle += SPEED * dt()
})

for (let i = 0; i < 3; i++) {

	const x = rand(0, width())
	const y = rand(0, height())

	add([
		sprite("ghosty"),
	        pos(x, y),

		area(),
		"enemy",
	])

}

add([
	sprite("grass"),
	pos(center()),
	area(),
	body({ isStatic: true }),
		body({ mass: 10 }),
	"grass",
])

add([
	sprite("steel"),
	pos(100, 200),
	area(),
	body({ mass: 10 }),
])


player.onCollide("enemy", (enemy) => {
	destroy(enemy)
})


player.onCollideUpdate("enemy", () => {
})


player.onCollideEnd("grass", (a) => {
	debug.log("leave grass")
})


player.onClick(() => {
	debug.log("hello")
})

player.onUpdate(() => {
	// .isHovering() is provided by area() component, which returns a boolean of if the object is currently being hovered on
	if (player.isHovering()) {
		player.color = rgb(0, 0, 255)
	} else {
		player.color = rgb()
	}
})


debug.inspect = true

![k](ka.jpeg)

`````

<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
