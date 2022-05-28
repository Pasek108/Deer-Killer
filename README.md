# Deer Killer
 Racing game in pure JS / CSS / HTML based on Road Fighter (NES). Rules are simple, player has to get as many points as possible, points are given for riding and killing deers (+1000), also player has 3 lives that he will lost when he touch enemy car, if so he gets shield that protect him for next 3 secons. If player lost all of his lives game is over and he can save the score and then start again.
 <details>
    <summary>Screenshots</summary>
    <img alt="Menu" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme_images/menu.png">
    <img alt="Game" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme_images/game.png">
    <img alt="Game Over" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme_images/game_over.png">
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
    <img alt="Menu start animation" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme_images/menu_bg.png">
</details> 

Menu has 3 options:
* Start - lets you chose difficulty and start game
* Top Score - shows your and all time players top 10 games for each level
* Credits - links resources i used to make this game
<details>
    <summary>Options scrrenshots</summary>
    <img alt="Menu difficulty tab" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme_images/menu_difficulty.png">
    <img alt="Menu top score tab" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme_images/menu_top_score.png">
    <img alt="Menu credits tab" src="https://github.com/Pasek108/Deer-Killer/blob/main/readme_images/menu_credits.png">
</details> 

### Game
Games start with count from 3 to 1 and it begins. Some amount of enemy cars (dependent of difficulty level) starts falling from top with random positions and speeds. In radom intervals of time 2 deers spawns, killing deers gives player 1000 points. Every 3000 point player gets 1 level of energy that lets him slow down time for as many secons as he has energy (max 5). When player touch enemy car it explodes and player gets shield for next 3 seconds
<details>
    <summary>Przykładowa tablica dla poziomu łatwego</summary>
    <img alt="Array for easy level" src="https://github.com/Pasek108/Deer-Killer/blob/main/main/readme_images/example_array.png">
</details> 


#### Obiekty
Obiekty w trybie kwadratowym mają od 0 do 4 połączeń na stronie oraz typ. 

Połączenia zapisane są w kolejności ruchu wskazówek zegara zaczynając od góry na 4 pozycjach, na pozycji 5 znajduje się typ tj. [top, right, bottom, left, type]

W trybie kwadratowym istnieje 8 typów obiektów złożonych z 4 podstawowych typów.
* *"n"* od *no move*, obiekt z którym nic nie można zrobić
* *"r"* od *rotate*, obiekt który można obracać o 90 stopni (przesuwa połączenia w tablicy o jeden top -> right, right -> bottom itd.)
* *"v"* od *vertical move*, obiekt który można przesuwać po osi pionowej
* *"h"* od *horizontal move*, obiekt który można przesuwać po osi poziomej
* *"vr"* od *vertical move and rotate*, obiekt który można obracać oraz przesuwać po osi pionowej
* *"hr"* od *horizontal move and rotate*, obiekt który można obracać oraz przesuwać po osi pionowej
* *"vhr"* od *vertical and horizontal move and rotate*, obiekt który można obracać oraz przesuwać w dowolnym kierunku

<details>
    <summary>Przykładowa plansza dla poziomu łatwego</summary>
    <img alt="Example game grid" src="https://github.com/Pasek108/ConnectGame/blob/main/readme_images/example_grid.png">
</details> 


