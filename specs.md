## Quest Features / Specs

init ( ):
* Create a resource account for the admin from the Bingo seed.
* Store the State resource under the admin and the Bingo resource under the resource account.
* Register an AptosCoin store for the resource account to allow token transactions.

create_game( ):
* Assert that the state is initialized, the game is unique and the timestamp is valid.
* Initialize a new, empty Bingo game and add it to the list of Bingo games.

insert_number( ):
* Assert that the state is initialized and the game is in progress.
* Assert that the number is between 0 and 75 and has not been drawn before.
* Add the number to the drawn_numbers vector. 

join_game( ):
* Assert that the Bingo board the player is submitting is well formatted and all numbers within range.
* Assert the game state is correctly initialized and the game has not began.
* Assert the player has enough funds to pay the entry fee of the game.
* Add the player board to the game_players map
* Lock in the entry fee in the resource account.

bingo( ):
* Assert that the game is in progress and player invoking the bingo function is a current participant of the game.
* Assert that the player has won which calls the check_player_won helper function.
  * For each cell on the players Bingo board, if the number is within the vector of drawn numbers or is 0, mark the cell as null.
  * Check for a full row, column or diagonal of null cells.
* Mark the game as finished and transfer all AptosCoins locked in the game to the winner.

cancel_game( ):
* Assert game state is initialized and the game is in progress.
* Forcefully mark the game as finished.
* Transfer each players entry fee back to their account.

Code by chuacw / Chee-Wee Chua,    
2-3 June 2023.


