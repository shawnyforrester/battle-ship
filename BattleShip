import random

"""
    -------BATTLESHIP-------
    Pre-reqs: Loops, Strings, Arrays, 2D Arrays, Global Variables, Methods
    How it will work:
    1. A 10x10 grid will have 5 ships randomly placed about
    2. You can choose a row and column to indicate where to shoot
    3. For every shot that hits or misses it will show up in the grid
    4. If all ships are shot, game over
    Legend:
    1. "." = water
    2. "S" = ship position
    3. "O" = water that was shot with bullet, a miss because it hit no ship
    4. "X" = ship sunk!
"""


# Global variable for grid size
grid_size = 10

#Global variable for myBoard



# Global variable for number of ships to place
NUM_SHIPS = 5



    


#Main should set up the board game
#Draw the board and prompt the user to enter a column X; display in valid column on the ask the  to try again.sp
#Draw the board again and prompt the user to  enter a row
#If the row is less than zero or greater than or equal to 10 return Invlad row.
#If the column and row are valid check for a HIT or MISS
#Update the board with the appropriate O or X
#If all ships have been HIT, draw the board again and print GAME OVER
#Otherwise loop back until all ships are HIT



def main():
    
    gameboard = setupBoard(grid_size)
    print("*****Welcome to Battleship*****")
    drawBoard(gameboard)
    
    
   
            
#This added function controls game play and user input, so that the gameboard is not reset after each user input.
def GamePlay(myBoard):
        while NUM_SHIPS > 0:
            row = input("please enter your row number: ")
            while row.isdigit() == False:
                print("Invalid entry\n Please re-enter your number")
                row = input("please enter your row number: ")
            
            
            clmn = input("Please enter our column number: ")
            while clmn.isdigit() == False:
                print("Invalid entry\n Please re-enter your number")
                clmn = input("Please enter our column number: ")
            print(row + ','+ clmn)
            print("Thank you")
        
            
#clmn and row are passed to checkHitorMiss which is called to update the board
            checkHitOrMiss(myBoard,int(row),int(clmn))
            drawBoard(myBoard)
        isGameOver()
            

#10 x 10 array of chars and the contents of the array should be displayed here
#Two unit tests should be done one that checks that the appropriate number of ships are present on the board and one that checks that the rest of squares have a blank space.
def setupBoard(grid_size):

    global NUM_SHIPS   
    myBoard = [['']*grid_size for i in range(grid_size)]
    for x in range(grid_size):
        for y in range (grid_size):
            myBoard[x][y] = str('.')

                                     
                   
#Random assigment of ships using variable NUM_SHIPS = 5
    ship_counter = NUM_SHIPS
    while ship_counter > 0:
        randomRow = random.randint(1, grid_size - 1)
        randomCol = random.randint(1, grid_size - 1)
        if myBoard[randomRow][randomCol] == 'S':
            continue
        else:
            myBoard[randomRow][randomCol] = 'S'
#ensures that 5 ships are placed on the board.            
        ship_counter = ship_counter - 1
            
    return myBoard
    
    
#prints the updated board.    
def drawBoard(myBoard):
         Header = '''
**  B  A  T  T  L  E  S  H  I  P  **
|   | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
+--+--+--+--+--+--+--+--+--+--+----
   '''
#Passes the array into he board
         for i in range(grid_size):
            Border = f'''
| {i} | {myBoard[i][0]} | {myBoard[i][1]} | {myBoard[i][2]} | {myBoard[i][3]} | {myBoard[i][4]} | {myBoard[i][5]} | {myBoard[i][6]} | {myBoard[i][7]} | {myBoard[i][8]} | {myBoard[i][9]} |
+---+---+---+---+---+---+---+---+---+---+---
            '''
            Header = Header + Border
         print(Header)
         GamePlay(myBoard)
         
         
#Takes 3 parameters as input and checks whether user_column,user_row contains an S or ".'
#An 'X' is returned for any index associated with an 'S' and an 'O' for any index associated with a '.'.
def checkHitOrMiss(myBoard,user_row, user_column):
    global NUM_SHIPS
    if myBoard[user_row][user_column] == 'S':
        myBoard[user_row][user_column] = 'X'
        NUM_SHIPS = NUM_SHIPS - 1
        print("You hit my battleship!")
        return "HIT"
        return myBoard
        
    if myBoard[user_row][user_column] == 'X':
        print("The ship is already sunk")
        
    
    
    if myBoard[user_row][user_column] == '.':
        myBoard[user_row][user_column] = 'O'
        print("You missed!\n Please try again")
        return "MISS"
        return myBoard
       
    

#Ends the game when the number of ships are zero (all ships have been sunk).

def isGameOver():
    global NUM_SHIPS
    if NUM_SHIPS == 0:
        print("You WON!\n GAME OVER")
        exit()




if __name__ == '__main__':
    main()
