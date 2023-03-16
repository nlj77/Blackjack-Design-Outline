# Blackjack-Design-Outline
This is a assignment for SMT's dev training. The goal of the assignment is to learn more about designing a project. 

**Overview**
<p> In the game of Blackjack, a player's goal is to accept dealt cards, in order to achieve a sum total of 21 or as close to it, without exceeding 21. If a player has reached 21, either by hitting or recieving 21 in total on an initial deal, or the player has reached a sum total that tops out their risk tolerance, the dealer then tries to reach 21, or a total better than the player's holding total, but no greater than 21. Betting is required, and if a player 'busts', they forfeit the money in the pot.</p>

<br>
<h3> Nouns and Verbs </h3>
<img src="https://user-images.githubusercontent.com/66858271/222778582-310e115a-e203-4a35-bde7-4dc02cd98077.png" title="Nouns and Verbs">
<br>
<h3> Considerations on Nouns and Verbs </h3>
<p> I felt vague about table. I thought it would be a good way to present the arrangement of a game, players, dealer, and pot, but maybe it's more useful as a concept than an actual class. After a lot of internal debate, I decided Deck should have a shuffle function, where as a Dealer should have a call shuffle function. I felt this was best as shuffling a deck is pretty universal and it refers to the state and order of a deck, a player or dealer can decide to shuffle (make a shuffleDeck call that causes a deck to run its shuffle function). I feel this adds to the reusablity of my deck and card classes, as in games where the active dealer rotates amongst players (Poker, Spades etc), a player can be designated dealer ,and have access to the deck function, without having the same responsibilities of a dealer in a different game, a game with multiple decks, or a different board state that requires a different arrangement of cards.
<h3> Game Flow Diagram </h3>
<img src="https://user-images.githubusercontent.com/66858271/222779748-b6d298ca-451e-4062-a2bc-63d794798a87.png" title="Game Flow">
<h3> Considerations on Game Flow </h3>
I felt the game should go as such: User agrees to start a game and enters as player, dealer deals a card to the player, then itself, then the player, then itself. At this point, both hands are evaluated. If the dealer has an initial hand of 21, and the player does not, then the pot is instantly lost, and the player loses the hand. If the player has an initial hand of 21, the dealer must hit till their hand sums to at least 16. The dealer must stay on a hand that amounts to 17, and if that's the case and the player has a higher total, the player wins. This game flow chart only details a single player, dealer versus one user, game. I did include in my nouns an idea for a table to host multiple players, but this chart would need to account for dealing each player a card. 
<br>
<h3> Concessions on First Draft </h3>

<p>The pot system and currency is something I didn't spend a lot of time on. Maybe I build a broad casino game where a user is a player, but when playing a Blackjack game, they become a Blackjack player. Then, when the user has quit that game, the player is returned to a player object, but retains winnings and loses from the Blackjack game.</p>
<p> Multiplayer considerations could have had a little more time spent on them. How a player interacts at a table with other players, against the dealer is a key part of real life Blackjack, and in an interest of simulating a real Blackjack game, that's pretty significant.</p>
<p> Naming schemes is something I want to work on. A Bet is a noun, and a verb in my design. A player can make a bet, but that bet is a object on the board state that directly affects the sum of the pot. The nomenclature of the game itself might be influencing the naming of my variables too much. </p>

<h3> Revised Game Flow <h3>
<h4> Notes on Revisions </h4>
  <p> A big part of my focus was keeping each step in the game flow as a single point or step, whereas my original had multiple points executed on each step. The other thing I attempted to do was remove any specific win conditions, loss conditions, or other specific value controlled conditions, in an effort to keep my game modular, and encourage the ability to use multiple rule sets with different win and loss conditions.</p>
<img src ="https://user-images.githubusercontent.com/66858271/225693567-904e0e69-f786-426d-8562-49df5d670d51.png" title="Revised Game Flow">


