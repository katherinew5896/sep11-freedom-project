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



<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
