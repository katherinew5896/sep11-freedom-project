# Entry 6
##### 6/1/25

## context
During this part of the year I have finished my freedom project with my partner and we have finished our mvp and beyond mvp. We have also presented our project at the expo. Explaing each step of the project from start to finish. Our project is composed of kaboom.js and a topic about a cooking game. I learned the main functions of kaboom.js on the (kaboom website) [https://kaboomjs.com/], on the playground. I spent a lot of time learning how each code runs together to create the final game. But also having used prior codes like functions and loops I can expand this game and its functions into a more exciting game with options for players to choose from.

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





[Previous](entry05.md) | [Next](entry07.md)

[Home](../README.md)
