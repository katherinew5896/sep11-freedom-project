# Entry 1
##### 11/3/24

## context
For this year-long project I decided to use the tool Kaboom. Kaboom is a game engine where you can make 2D games. My backup tool was three.js which is another tool for making games. Aftering doing my learning logs I decided to stay with kaboom as my tool. The reason I decided on kaboom is because it feels just right for my skill level and it has been a really fun tool to use. For kaboom I was planning on making a game and working with Johnny. We decided to make a cooking game. This connects to last year where I made a website for cooking. Cooking is something I am passionate about so this year we will make a cooking game. The purpose of my game is for people to get an understanding of how cooking works, if you have never cooked before and are too scared to do this game would be perfect. So for both LL1 and LL2 I have tinkerin many ways. 

Examples of my tinkering is my LL2 as you can see below
So the first thing I learned was giving blocks a mass and being able to move it. 
`````js
body({ mass: 10 }),
`````
This code allowed me to give my sprites a mass and was able to move it.
Another thing I learned was 
`````js
onKeyDown(" ", () => {
	player.angle += SPEED * dt()
	player.move(0, -SPEED)
	player.move(0, SPEED)
})
`````

All three of these are things you can put in the code. One of the rotates the sprites, another cod moves the sprites up or down. The last one moves it left or right.

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

`````
This is before, where we didn't move anything.
![k](../tool/ka.jpeg)

This is after, where we ate everything and move the blocks with wasd using the code we learn and the sprites moving
![](../tool/kaafter.jpeg)

So as you can see from my LL2 I have been tinkering by looking at codes, trying them myself and watching youtube videos to get a better understanding when I don't know something. 

## sources
So I did my research for both kaboom and three.js. I found many sources so lets start of with the sources I found for three.js. The first source I found was [three.js](https://threejs.org/) website. This website shows you everything there is for three.js. I also watched youtube videos like [How to use three.js website](https://www.youtube.com/watch?v=xJAfLdUgdc4). This gave me a understanding of how the website works and a tutorial on how three.js works. But in the end I didn't use three.js I instead used kaboom. The sources for kaboom is way more than that of three.js One of the first sources I used for kaboom is the kaboom website. [kaboom website](https://kaboomjs.com/) in this website you can see how different codes are used and you can see the games that they made. This is where I do most of my tinkering and find codes that could help for the future. Another thing I used I was youtube videos like [making a game with Kaboom](https://www.youtube.com/watch?v=hgReGsh5xVU) and [Build a Dev Portfolio as a 2D Game ](https://www.youtube.com/watch?v=wy_fSStEgMs) both of these video was what got me into kaboom. It shows what you can do with kaboom and watching the videos I understood how some of the codes work. Last of all the Learning Logs are another tool that I used.[learning log.md](../tool/learning-log.md). these were the sources I used. 
   
## EDP 
EDP or Engineering Design Process is the part of the project you are on. There are 8 different parts. The problem I am trying to solve is people being too scared to cook. I plan on making a game that everyone can enjoy and not be scared of cooking. You can learn many things like how to cook, different recipes and have fun with friends in general. I finished my define and research part of the EDp, I am on the brainstorming and planning part where I need to think of how I can make a website and ways this game can make being have fun and learn how to cook.

## skills

### 1. Research
I had to do research before choosing a tool. I learned a lot about researching like how to google well and find what you are looking for. Like when I was looking up three.js videos I couldn't find a lot but I had to search up more information to find what I was looking for. The website helped me since they provide many links and resources.

### 2. Communication
While researching I've noticed that communication was a very important part because to work together is to communicate. We need to communicate in order to make changes while advancing in technology. Communication is how we share ideas and knowledge with one another. Also when I needed help I asked my friends, like I asked Johnny how Kaboom works at first and he was able to help me by providing examples and resources. Also Johnny reminded me to do my learning log to get more usd to it so communication is really important for growth and friendships. So these were the skills I learned for blog entry 1.


[Next](entry02.md)

[Home](../README.md)


