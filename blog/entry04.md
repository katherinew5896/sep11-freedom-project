# Entry 4
##### 3/16/25

### content
This year we had the freedom project, our year-long project for Sep. I have been learning the tool I used which is kaboom in many ways. As I said before one of these websites for learning is the [kaboom website](https://kaboomjs.com/) in this website you can see how different codes are used and you can see the games that they made. This is where I do most of my tinkering and find codes that could help in the future. Another thing I used for learning was YouTube videos like [making a game with Kaboom](https://www.youtube.com/watch?v=hgReGsh5xVU) [learning log.md](../tool/learning-log.md). This is the learning log which is where my notes are for the codes I learned. The last time I did my blog was after winter break when I planned what to do during the break and also did LL. So what did I do: 


### What I did during the break and for my LL

I made a code where there are different levels and when you press r you return to the old level. 
`````js
kaboom({
	background: [74, 48, 82],
});

// Load sprites
loadSprite("bag", "/sprites/bag.png");
loadSprite("ghosty", "/sprites/ghosty.png");
loadSprite("grass", "/sprites/grass.png");
loadSprite("steel", "/sprites/steel.png");
loadSprite("door", "/sprites/door.png");
loadSprite("key", "/sprites/key.png");
loadSprite("bean", "/sprites/bean.png");

// Define characters and their dialog
const characters = {
	"a": {
		sprite: "bag",
		msg: "Hi Bean! You should get that key!",
	},
	"b": {
		sprite: "ghosty",
		msg: "Who are you? You can see me??",
	},
	"c": {
		sprite: "ghosty",
		msg: "Boo! I'm a friendly ghost.",
	},
	"d": {
		sprite: "bag",
		msg: "Watch out for traps!",
	},
};

// Define levels
const levels = [
	// Level 1
	[
		"===|====",
		"=      =",
		"= $    =",
		"=    a =",
		"=      =",
		"=   @  =",
		"========",
	],
	// Level 2
	[
		"--------",
		"-      -",
		"-   $  -",
		"|      -",
		"-    b -",
		"-  @   -",
		"--------",
	],
	// Level 3
	[
		"========",
		"=      =",
		"= $  c =",
		"=      =",
		"=  @   =",
		"=      =",
		"========",
	],
	// Level 4
	[
		"--------",
		"-      -",
		"- $  d -",
		"|      -",
		"-  @   -",
		"-      -",
		"--------",
	],
	// Level 5
	[
		"========",
		"=      =",
		"= $    =",
		"=      =",
		"=  @   =",
		"=      =",
		"========",
	],
];

// Main game scene
scene("main", (levelIdx) => {
	const SPEED = 320;

	// Create the level
	const level = addLevel(levels[levelIdx], {
		tileWidth: 64,
		tileHeight: 64,
		pos: vec2(64, 64),
		tiles: {
			"=": () => [
				sprite("grass"),
				area(),
				body({ isStatic: true }),
				anchor("center"),
			],
			"-": () => [
				sprite("steel"),
				area(),
				body({ isStatic: true }),
				anchor("center"),
			],
			"$": () => [
				sprite("key"),
				area(),
				anchor("center"),
				"key",
			],
			"@": () => [
				sprite("bean"),
				area(),
				body(),
				anchor("center"),
				"player",
			],
			"|": () => [
				sprite("door"),
				area(),
				body({ isStatic: true }),
				anchor("center"),
				"door",
			],
		},
		wildcardTile(ch) {
			const char = characters[ch];
			if (char) {
				return [
					sprite(char.sprite),
					area(),
					body({ isStatic: true }),
					anchor("center"),
					"character",
					{ msg: char.msg },
				];
			}
		},
	});

	// Get the player object
	const player = level.get("player")[0];

	// Dialog system
	function addDialog() {
		const h = 160;
		const pad = 16;
		const bg = add([
			pos(0, height() - h),
			rect(width(), h),
			color(0, 0, 0),
			z(100),
		]);
		const txt = add([
			text("", { width: width() }),
			pos(pad, height() - h + pad),
			z(100),
		]);
		bg.hidden = true;
		txt.hidden = true;
		return {
			say(t) {
				txt.text = t;
				bg.hidden = false;
				txt.hidden = false;
			},
			dismiss() {
				if (!this.active()) return;
				txt.text = "";
				bg.hidden = true;
				txt.hidden = true;
			},
			active() {
				return !bg.hidden;
			},
			destroy() {
				bg.destroy();
				txt.destroy();
			},
		};
	}

	let hasKey = false;
	const dialog = addDialog();

	// Key collection
	player.onCollide("key", (key) => {
		destroy(key);
		hasKey = true;
		dialog.say("You found a key!");
	});

	// Door interaction
	player.onCollide("door", () => {
		if (hasKey) {
			if (levelIdx + 1 < levels.length) {
				go("main", levelIdx + 1); // Go to the next level
			} else {
				go("win"); // Win the game
			}
		} else {
			dialog.say("You need a key to open the door!");
		}
	});

	// Go back to the previous level when "R" is pressed
	onKeyPress("r", () => {
		if (levelIdx > 0) {
			go("main", levelIdx - 1); // Go to the previous level
		} else {
			dialog.say("You're already at the first level!");
		}
	});

	// Character interaction
	player.onCollide("character", (ch) => {
		dialog.say(ch.msg);
	});

	// Player movement
	const dirs = {
		"left": LEFT,
		"right": RIGHT,
		"up": UP,
		"down": DOWN,
	};
	for (const dir in dirs) {
		onKeyPress(dir, () => dialog.dismiss());
		onKeyDown(dir, () => player.move(dirs[dir].scale(SPEED)));
	}
});

// Win scene
scene("win", () => {
	add([
		text("You Win!", { size: 48 }),
		pos(width() / 2, height() / 2),
		anchor("center"),
	]);
});

// Start the game
go("main", 0);
`````
![k](../tool/l.jpeg)
![k](../tool/h.jpeg)

This is what I did for the code as you can see, you can go back, talk to NPC, go to a new level, and reach the end. This is what I did and I have plans to change the background and texture. 
### Progress 
So far, I have done some of my MVPs. I made levels where you can go in between them. Also added characters that can move and NPCs you can talk to. I still have to do more for my MVp like adding more textures, making it so when you talk to a customer and you give them food. This is the progress so far and we will be working on more throughout the year.


## EDP 
EDP or Engineering Design Process is the part of the project I am on There are 8 different parts. The problem I am trying to solve is people being hesitant to cook or be creative in cooking. I plan on making a game that everyone can enjoy and not be scared of cooking. The plan of this game is, while I already brainstormed the game, I want to have a game with different levels that you could go between, at each level there are different things to do, one level you collect resources, the next you talk to NPC and you can give them food. You need to cook food it will show you how to cook and if you put it for too long you can't use it. Now we are trying to make a prototype of the game, so far we made the levels and characters, and the next thing to do is to add the cooking part. This is the Engineering Design Process we are on. 

## Skills
1. first skill i needed to work on was time management. This had me a bit all over the place as i had to make time to practice my tool, but also work on other assignments. To better manage my time i used google tasks and started to dedicate certain hours for each thing i needed to do in order to stay on top of everything, but also learn as i go. So that when the times comes i actually know what im doing and can chase the learning not the points.
2. The second skill i worked on was problem-solving skills. This was very much needed as i had trouble asking myself how to decipher codes and find which wouldn't work and which did. This was not easy as i did not fully grasp the concept of certain topics and had a hard time solving problems on my own without help from my peers. I needed to go back on recent projects i did and my notes to help me understand why codes were not working. It took a lot to actually put in the effort to stop and think about what the problem i was facing was. I just need to get used to sitting down and taking my time to learn each step and face each problem.
3. The third skill i had to work on was creativity. Whenever I would make use of the codes i learn like from p5js or Kaboom, I still needed to use my brain and not copy other examples that have been done or else it would not be very original. To challenge this skill I thought about random things ive played or seen before in games or books that could be turned into code. For Kaboom I thought about roblox and the idea of obbys(obstacle courses) that i could use for Bean. For the P5js project I decided to kind of make something like the famous caterpillar book.





[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
