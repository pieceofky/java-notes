1. Chessboard
   
   1. Drawing a chessboard in javafx
      
      1. 8x8 square board
      
      2. For each square, they have attributes of:
         
         1. light/dark square
         
         2. a square holds the coordinate values
         
         

2. Pieces
   
   1. *ImageView*: Allows chess pieces visual using chess set images.
   
   2. attributes:
      
      1. piece type
         
         1. king, queen, bishop, etc.
      
      2. color
      
      3. position: coordinates
   
   3. its moves
   
   

3. Moves
   
   1. Considerations:
      
      1. We should define a boiler plate class for all pieces types[interface][abstract class]
      
      2. What do we need?
      
      3. legal moves
         
         1. piece moves
         
         2. valid moves
      
      4. Should we use abstract class or interface to define the boiler plate?
      
      5- How do we define its features?
         
         
   
   2. Get available square from the board.[(getAvailableSquares)]
   
   3. Generate piece related moves.[(getPieceRelatedMoves)]
   
   4. Valid moves(Intersect available_squares & piece_moves)[(getValidMoves)]
   
   5. Mouse Interactions:
      
      1. Drag and drop
         
         1. drag start logics[(dragStartMethod)]
         
         2. during drag[(onDragMethod)]
         
         3. drag drop logics[(dragDropMethod)]
      
      2. click and click moves
         
         1. on click a piece[(clickStartMethod)]
            
            1. show available moves
         
         2. on click on available squares.[(clickOnValidSquareMethod)]
            
            1. move the piece to that square if it was a legal move.
