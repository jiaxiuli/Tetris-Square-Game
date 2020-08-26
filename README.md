# squareGame
2020-8
Jiaxiu Li
## Game panel
The game panel is actually a two-dimension array, each cell in the array stands for one cell on the interface. If the value of the cell is 0, it means that this space is vacant, and if the cell is 1, it means that this cube is occupied, and nothing should be placed on it.
![image](https://github.com/jiaxiuli/Tetris-Square-Game/blob/master/img/panel.png)

each shaped piece (tetrominoes) is also defined by a two-dimension array, the elements in the array, point out which cube should be rendered on the game panel. For example, the arrat might be [[12,1],[13,0],[13,1],[14,1]], then is means in the two-dimension array "panel", these cells should be rendered, so that users can see the shape on the panel.
![image](https://github.com/jiaxiuli/Tetris-Square-Game/blob/master/img/shape.png)

## function
### Move
the drop function is completed by a timer, every one second to make the second value of each array + 1, Y-axis actually. 
so it looks like, 
[[12,1],[13,0],[13,1],[14,1]](original), 
[[12,2],[13,1],[13,2],[14,2]](one sec after), 
[[12,3],[13,2],[13,3],[14,3]](two sec after)... 
every time when we modify the array, we need to re-render the page, and because the position of the shaped piece is changed, so we can see that the shape is moving on the panel.
Move left and move right function is similar, we just need to make the X-axis + 1 or - 1, if the X-axis + 1, the shape will move right, if the X-axis -1, the shape will move left.
![image](https://github.com/jiaxiuli/Tetris-Square-Game/blob/master/img/rotate.gif)
### complete lines and grant player points
it is necessary to check if there is a completed line everytime when a shape has dropped to the bottom. If the there is a completed line, it means that in the panel array, values of all the cells on the line should be 1. If this happens, then set all of cells in this line to 0, and make all of the rendered cells drop down.
![image](https://github.com/jiaxiuli/Tetris-Square-Game/blob/master/img/completeLine1.gif)
if one line is completed, the user can get 10 points, if more than two lines are completed together, except the basic 10 points for each line, there are also bonus will be given. Bonus is caiculated by how many lines were completed together, if 2 lines completed, the user can get 2 bonus points for each line, if 3 lines completed, the user can get 3 bonus points for each line. Finally, if 2 lines completed together, the points will be 2 * 10 + 2 * 2, if 3, 3 * 10 + 3 * 3.
![image](https://github.com/jiaxiuli/Tetris-Square-Game/blob/master/img/completeLine2.gif)
