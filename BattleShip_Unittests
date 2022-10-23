from forrester3 import *
import unittest

class TestBattleship(unittest.TestCase):


   
#Two unit tests should be done one that checks that the appropriate number of ships are present on the board.
    
        
    def test_ShipNumber(self):
    #Initialize the 10 x 10 array.
        shipcount = 0
        grid_size = 10
        My_array = setupBoard(grid_size)
                
        for i in range(10):
            for j in range (10):
                if My_array[i][j] == "S":
                    shipcount += 1
                
    #compare the elements in the test array with the elements in the gameboard        
        self.assertEqual (shipcount, 5)
        
        
#checks that the rest of the board has blank spaces        
    def test_BlankSpaceNumber(self):

        BlankSpace = 0
        grid_size = 10
        #Initialize the 10 x 10 array
        My_array = setupBoard(grid_size)

        for i in range(10):
            for j in range(10):
                if My_array[i][j] == ".":
                    BlankSpace += 1
        #Compares the number of blank spaces with the gameboard
        self.assertEqual(BlankSpace, 95)
                            
        
    def test_checkHit(self):
        #Initialize the 10 x 10 array
        grid_size = 10
        My_array = setupBoard(grid_size)
        
        #Assign a ship to the sepcified index 
        My_array[0][0] = "S"               
        result = checkHitOrMiss(My_array,0,0)
        
       #Compare the string returned with the expected result which is X for a hit. 
        self.assertAlmostEqual(result, "HIT" )
        

    def test_checkMiss(self):
        #Initialize the 10 x 10 array
        grid_size = 10
        My_array = setupBoard(grid_size)
        
        #Assign a blank to the specifiec index
        My_array[0][0] = "."
        result = checkHitOrMiss(My_array,0,0)
        #Compare the expected string with the returned string which should be an O for a miss.
        self.assertAlmostEqual(result, "MISS")
        
    
#Because isGameOver takes no parameters and it's function is dependent on a global variable I did not create a test function for isGameOver.

if __name__ == '__main__':
    unittest.main()
