# Deer Killer
 Racing game in pure JS / CSS / HTML based on Road Fighter (NES). Rules are simple, player has to get as many points as possible, points are given for riding and killing deers (+1000). Player has 3 lives that he will lost when he touch enemy car, if so, he gets shield that protect him for next 3 seconds. If player lost all of his lives game is over and he can save the score and then start again. There is also a slow time skill for helping player, every 3000 points it gets 1 stack of energy, each stack let use skill for 1s (max 5s).
<details>
    <summary>Screenshots</summary>
    <img alt="Menu" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme-images/menu.png">
    <img alt="Game" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme-images/game.png">
    <img alt="Game Over" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme-images/game_over.png">
</details> 

## How it works
### Menu
Menu starts with few animations:
1. Change background from white to black
2. Fade out road sign
3. Replace road sign with bloody sign and fade out title
4. Resize sign and move it to top while sliding in menu options from bottom
<details>
    <summary>Animation</summary>
    <img alt="Menu start animation" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme-images/menu_top_score.png">
</details> 

Menu has 3 options:
* Start - lets you chose difficulty and start game
* Top Score - shows your and all time players top 10 games for each level
* Credits - links resources i used to make this game
<details>
    <summary>Options scrrenshots</summary>
    <img alt="Menu difficulty tab" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme-images/menu_difficulty.png">
    <img alt="Menu top score tab" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme-images/menu_top_score.png">
    <img alt="Menu credits tab" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme-images/menu_credits.png">
</details> 

### Game
Games start with count from 3 to 1 and it begins. 

### Enenmies position algorithm
Some amount of enemy cars (dependent of difficulty level) starts falling from top with random positions and speeds using the following algorithm:
* Random new position
* Compare with all other cars and count correct positions:
   1. Check if cars are not in the same column - position correct, skip next 2
   2. If not check if the speed of the bottom car is higher so they will never touch - position correct, skip next one
   3. If not, check if speed of upper car is low enough that they will dont touch on the screen - position correct
   4. If the above are not correct random new position and check again

### Deers
Deers spawn in radom intervals of time with random position and vector. If they touch enemy they die. If killed by player, they gives 1000 point and die, If they reach other side of road they respawn again for a random amount of time. If deer is dead his image is swaped for blood and his vector.x is set to 0.



