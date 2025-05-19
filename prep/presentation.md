# Presentation Plan

## Hook
* Who likes cooking and adventure games? If you want a new experience like fighting bears in forests for resources to cook in your restaurant, try our cooking game!

## Product
* We made a game where you can choose to be a chef or an adventurer. We are going to show a Demo and example it.
* Code snippets of
  `````js
  if (playerRole === "adventurer") {
                            if (character.type === "t") { // Treasure
                                score += 50;
                                scoreDisplay.text = `Adventure Score: ${score}`;
                                play("coin");
                                destroy(character);
                            } else if (character.type === "i") { // Ingredient
                                score += 20;
                                ingredientsCollected++;
                                scoreDisplay.text = `Adventure Score: ${score}`;
                                play("coin");
                                destroy(character);

                                // Check if all ingredients collected
                                if (ingredientsCollected >= totalIngredientsNeeded) {
                                    dialog.say("Congratulations! You found all legendary ingredients!");
                                    playerMaxHealth += 50;
                                    playerDamage += 10;
                                }
                            } else if (character.type === "m") { // Monster
                                // Monster interaction handled in combat system
                            }
                        }
  `````
  This is for how the scoring works and how I used if statements.


  ````` js
                loadSprite("chef", sprites/../c.png");
                loadSprite("adventurer", sprites/../c.png");
                loadSprite("customer1", sprites/../c1.png");
                loadSprite("customer2", sprites/../c3.png");
                loadSprite("table", sprites/../table.png");
                loadSprite("door", sprites/../door.png");
                loadSprite("stove", sprites/../stove.png");
                loadSprite("counter", sprites/../c4.png");
                loadSprite("fridge", sprites/../fridge.png");
                loadSprite("plate", sprites/../plate.png");
                loadSprite("food", sprites/../food.png");

                // Adventurer-specific sprites
                loadSprite("quest-giver", sprites/../c1.png");
                loadSprite("treasure", sprites/../treasure.png");
                loadSprite("ingredient", sprites/../ingredient.png");
                loadSprite("portal", sprites/../door.png");
                loadSprite("monster", sprites/../c3.png");
                loadSprite("forest-tree", sprites/../tree.png");
                loadSprite("mountain", sprites/../mountain.png");
                loadSprite("castle", sprites/../castle.png");
                loadSprite("sword", sprites/../sword.png");

  ````` As you can see here, the code might look fine but the sprites didn't load. I found out that I was missing a " after the ,.
  

## Process
* planned on what type of game we will create
* learned p5.js and used it to create a basic outline of our game design

## Conclusion
* less = more. I spend too much time trying many things simultaneously, which doesn't work out.
* Ask friends for help. When I wasn't sure how to get my characters to load in, I asked my friends and found what I did wrong in the code. Like ellen and kyle lam helped get my sprites to load in. They saw my code and I was just missing a " and they told me what was wrong and I was able to fix it. 

<!-- EXAMPLE

## Hook
* Verbal riddle of GGD

## Product
* GIF/Demo of example/non-example

## Process
* Flowchart of the plan
  * MVP: noun -> door -> yes/no
  * Beyond MVP: noun -> word relation API -> noun API -> yes/no, with counterexample
* Code snippets of:
  * MVP
  * Both APIs
  * Challenge with API keys

## Conclusion
* [URL to project]
* Takeaways
  * Less = more: the heart of the riddle was one line of code; it obviously took more to make the entire thing work, but one complicated line of regular expressions was essentially the solution to the riddle
  * Expect the unexpected: it’s important to budget time for things you don’t account for; for example, I didn’t consider the fact that I would need another entire API to detect nouns
  * Determination is key: ironically enough, I had to make my API keys private. At first, it didn’t seem like it was possible, which meant I couldn’t publish my app. But after all of that hard work, I was determined to find a solution, and I found it in config variables.
* "Presentation can’t, but a speech can" 


-->
