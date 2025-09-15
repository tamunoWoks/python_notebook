## Using Data Structures to Model Real-World Things
Computers have good memories. A program on a modern computer can easily store billions of strings. Computers can even play chess without having a physical chessboard. They model data to represent a chessboard, and you can write code to work with this model to simulate a chess game.  
&nbsp;&nbsp;&nbsp;&nbsp;This is where lists and dictionaries can come in handy. For example, we could come up with our own notation so that a Python dictionary could represent a chessboard.

### Interactive Chessboard Simulator:
We can create an interactive chessboard program. Chess is played on an `8 × 8` board with white and black pieces called pawns, knights, bishops, rooks, queens, and kings. The upper-left and lower right squares of the board should be white, and our program assumes the background of the output window is black.  
&nbsp;&nbsp;&nbsp;&nbsp;Our chessboard program is just a board with pieces on it; it doesn’t even enforce the rules for how pieces move. We’ll use text characters to “draw” a chessboard.
