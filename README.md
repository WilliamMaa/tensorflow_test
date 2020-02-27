# tensorflow_test

-  Dealer send 2 different types of message
   1. The state message: 1 byte string
   1. The card message: at most 20 bytes string
-  The state message decides which state the game is currently at
   1. `begin`: 0, signal the game began, and dealer will send the beginning cards in the next message
   1. `illegal`: 1, the player did something wrong last turn and need to redo it, the dealer will not send anything after this
   1. `deal`: 2, the dealer deals a new card to the table, the dealer will send the new cards to the players in the next message
   1. `end`: 4/5, the game is over, the dealer decides who wins. 4 indicates win, 5 indicates lose
-  The card message contains the cards, it should at most have 20 bytes because we need to send the two players' hand at the end
