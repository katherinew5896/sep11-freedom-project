# Entry 6
##### 6/1/25

## context
During this part of the year I have finished my freedom project with my partner and we have finished our mvp and beyond mvp. We have also presented our project at the expo with these [slides](https://docs.google.com/presentation/d/1I7DhBuQJP0BuV2XR532SJXRRB0XofwneNnzXnazd_aU/edit?slide=id.p#slide=id.p)Explaing each step of the project from start to finish, but shortened it with an [elevator pitch](https://docs.google.com/document/d/1-lgzP7K8CmKBgsjgY4cMFvLfvLTIZefJRRvoIbQveG4/edit?tab=t.0) Our project is composed of kaboom.js and a topic about a cooking game. I learned the main functions of kaboom.js on the [kaboom website](https://kaboomjs.com/), on the playground. I spent a lot of time learning how each code runs together to create the final game. But also having used prior codes like functions and loops I can expand this game and its functions into a more exciting game with options for players to choose from.

## Code of game
This is what you would see at the menu screen and you would have to pick one.  
````` js
 <div id="menu-container">
            <div class="menu">
                <div class="game-title">Restaurant Adventure</div>
                <div class="role-selection">
                    <button id="chef-btn" class="btn-role">Be a Chef</button>
                    <button id="adventurer-btn" class="btn-role">Be an Adventurer</button>
`````
There is also instructions on each role.  
`````js
<h5>Chef Gameplay:</h5>
                    <ul>
                        <li>Manage the restaurant kitchen</li>
                        <li>Cook meals for customers</li>
                        <li>Keep customers happy to earn points</li>
                        <li>Upgrade your kitchen equipment</li>
                        <li>Press '1' to prepare a Burger</li>
                        <li>Press '2' to prepare a Pizza</li>
                        <li>Press '3' to prepare a Salad</li>
                        <li>Press 'S' to serve customers</li>
                        <li>Press 'E' to take customer orders</li>
                    </ul>

`````
````` js
 <div id="adventurer-desc" class="role-description" style="display:none;">
                    <h5>Adventurer Gameplay:</h5>
                    <ul>
                        <li>Explore a culinary fantasy world</li>
                        <li>Discover legendary recipes</li>
                        <li>Battle food monsters (Press 'F' to attack)</li>
                        <li>Complete epic cooking quests</li>
                        <li>Collect ingredients to upgrade your skills</li>
                    </ul>
                </div>
`````
And the basic instructions on movement.  
````` js
 <div class="instructions">
                    <h4>How to Play:</h4>
                    <ul>
                        <li>Use arrow keys to move your character</li>
                        <li>Press 'E' to interact with objects and people</li>
                        <li>Switch between areas using doors/portals</li>
                    </ul>
`````
This const code would make kaboom functions available globally.  
`````js
 const {
                loadSprite,
                scene,
                addLevel,
                rect,
                color,
                area,
                body,
                sprite,
                scale,
                text,
                pos,
                vec2,
                z,
                fixed,
                anchor,
                LEFT,
                RIGHT,
                UP,
                DOWN,
                onKeyPress,
                onKeyDown,
                onKeyRelease,
                go,
                height,
                width,
                add,
                destroy,
                loop,
                get,
                onSceneLeave,
                wait,
                camPos,
                camShake,
                burp,
                play,
                loadSound,
                outline
            } = k;
`````
Then using sprites to place everything into the game like characters, items, and text.  
````` js
function startGame(role) {
                // Load sprites
                loadSprite("chef", "sprites/../c.png");
                loadSprite("adventurer", "sprites/../c.png");
                loadSprite("customer1", "sprites/../c1.png");
                loadSprite("customer2", "sprites/../c3.png");
``````
By using const again I can place down a map of tables and characters.  
````` js
   const chefLevels = [
                    // Dining Area
                    [
                        "---------------------",
                        "-                   -",
                        "-  c      d       e -",
                        "-  T      T       T -",
                        "-                   -",
                        "-                   -",
                        "-         @         -",
                        "-                   -",
                        "-                   -",
                        "-  T     T        T -",
                        "-                   -",
                        "-                   -",
                        "---------------------",
                    ],
`````

This next code is for monsters attacking the player when in adventure mode.  
````` js
if (char.health) {
                                    components.push({
                                        health: char.health,
                                        maxHealth: char.maxHealth,
                                        damage: char.damage,
                                        speed: char.speed,
                                        attackCooldown: char.attackCooldown,
                                        chaseRange: char.chaseRange,
                                        lastAttackTime: 0,
                                        isAggressive: true,
                                        isAlive: true
                                    });
                                }
`````
## takeaways on elevator pitch
1. My first takeaway is how much work it would need for me to include the highlights of my project and code within a minute. Because people have a pretty short attention span I needed to hook them in with something interesting that they would know of. But also later on explain my process and what I had used to create this project. Overall it is better to just add the highlights of the presentation since explaining a certain code won't matter too much rather than explaining the process and challenges I faced and learned from.
2. My second takeaway is to rehearse the elevator pitch because sometimes you never know if you are going over 1 minute or under. Also sometimes we forget to say things we are supposed to say since the judges are literally judging you right in front of you, so it may get a little wonky when you are explaining and you don't want to go back and forth saying random things when you could have been saying something useful for judges.

## takeaways from in class presentations
1. My first takeaway is making eye contact because since I was presenting to my classmates I felt very used to seeing them everyday and just forget to look into their faces while presenting. This is not helpful for when presenting with different people outside of my class and people my age. I need to practice looking at people straight into their eyes without any thought of what I look like while doing it or else I can never look at people when presenting which is a real problem in real scenarios.
2. My second takeaway is speaking loudly and in a less boring voice. I often think too deep into the presentation and speak like a robot while trying to remember to stick to the script, that I sound very boring and shaky when presenting. This can lead to my classmates or judges not having really any interest in my project. I need to practice on my tone and energy because that is what catches peoples attentions and has them hooked and stay for the rest of the presentation.
3. My third takeaway is adding more onto my slides or making more slides because when I am presenting I tend to go really fast and end my presentation as soon as possible to get it over with. But that is not good because when I am going really fast, people are not too focused and think that its really short when it feels really long for me. My slides should contain more in depth of what challenges I had and a closer look into my code for an idea of Kaboom or how something works. Presenting is about sharing something that I learned to others so that they also gain that knowledge.



[Previous](entry05.md) | [Next](entry07.md)

[Home](../README.md)
