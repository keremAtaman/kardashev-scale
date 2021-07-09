# 8th of July, 2021 (In process of creating v1.1)
I decided I should start a design diary, partly to document my design decisions and partly to share my experience with anyone who'd be interested. So here goes:

The original version of the game (v1.0) was, quite honestly, a mess. The reasons that I could find as to why that was the case were:
- It had deckbuilder mechanics for every player, even if some players would have a total of 4 cards in their deck. What's worse, unlike a deckbuilder, there were no purchasing of cards from the market - players would just receive and discard a randomized set of cards each turn. This turned out to be incredibly annoying, as players would not be able to do an action when it feels natural due to the fact that they hadn't drawn, or discarded an action. For example, the Minister of Commerce would not be able to make investments and deal with money just because they did not have the required card in their hand.
    - I feel I need to mention why I went with the "deckbuilder" route in the first place. One of the design goals of this game was for it to be easily picked up and understood by players. This, in my mind, meant that players should not be exposed to a giant list of actions they could take in their turn, however, I ended up creating a LOT of possible actions that needed explanation for the players. So my solution was to put this actions on cards which the players would draw and discard a certain amount of each turn. That way, the players would be exposed to only a few actions they'd have to consider each turn. 
- There were not one, but two shared resources (Gold and Workers) that could be converted to one another and worked in a same way. While jarring, it provided a good example on the simplification process - that is, if a mechanic is not essential to your gameplay, remove it. In this case, the concept of Workers got removed for v1.1
- There was too many things each player had to keep track of. Their Gold, Workers, a bunch of ongoing effects from Researches (e.g. whenever you roll a die, roll an extra one)... 
- The players were not making interesting decisions. The decisions they made either felt pointless or repetitive, and were only affecting themselves and not the other players. Since this is a coop game, I want to ensure everyone has an impact on everyone, and not just because they put an extra cube on the board or gave a few bits of Gold. 

But hey, this is my first ever attempt at creating a board game, so mistakes and errors were definitely to be expected.

This brings us to the main reason I am writing this brain dump - to state that it is significantly difficult to add/change/remove mechanics on a game that has quite a few mechanics going. Due to the issues I listed above, changes definitely need to be made, but it is quite the challange to add/remove blocks from the Jenga tower of mechanics. Which is why I want to try the "Abstraction Mountain" method. 

"Abstraction Mountain" method is utilized by the designers of Caves of Qud, a game known for procedurally generating almost everything and somehow be able to link them together: wildlife, culture of villages, religion, relations between villages all become connected. And the way they accomplish this is having layers of generation, starting from the abstract layer (e.g. History of a Village) and move down from there (after history, culture is generated using history, and architecture is generated based on both, and finally game objects are created). I figured I can do something similar for the game and player mechanics. Start with design objectives of the game, then player objectives and how they should feel, then move on from there. I know this feels obvious when written like this, but considering this game evolved from the idea of "I want to create a coop game about the Kardashev Scale!" rather than the process I described, it is worth mentioning.

Let's start with the design objectives of the game, that is, my abstract layer:
- The game should be cooperative in which no player can be a "power player" and tell everyone what to do
- Each player's function must be different, leading to an asymetric coop game. 
- The game should encourage and require cooperation between players
- Players should experience the difficulty of balancing resources between everyone to deal with the challanges the game throws at them
- The game should be able to be picked up easily by an average board gamer.

Drilling down further, let's carve out some main features of the game generated from the game objectives above:
- Players will act as different Ministers (e.g. Minister of Commerce, Science...) of a Nation. The Nation will require all the Ministers' departments to function properly.
- Players will have hidden information, which will force everyone a turn to speak and participate in the decision making
- The challange the game will be throwing at the players will be coming from Foreign Nations, World Events, and the constant need to technologically advance which will come from the Kardashev Scale mechanic.
- Most of the information regarding the game will not be in a rulebook, but in Ministers' Character Sheets and the cards that are played.

Let's expand the points above:
- The game will be played on a hexagonal grid, with each grid representing an area of the world.
    - Each Nation will control a select number of them, and the rest will be considered to be neutral countries
    - Just like in real life, the more land and resources (aka tiles) a Nation controls, the stronger they will be. 
- Players can take on one of the following roles:
    - Minister of Defence (MoD): In charge of intellegence and army
        - Armies can be used to defend against/attack/force their will on Foreign Nations and neutral countries
        - Intellegence is used to conduct covert ops and to gain advantage over Foreign Nations.
        - Intellegence will also allow the MoD to see and change the intent of the Foreign Nations. The intents will only be revealed to the MoD, which is the hidden information that will make MoD participate in the discussions
        - TODO: integrate TI's combat a bit (each player rolls dice to hit. Players decide which of their units get hit)
    - Minister of Science (MoS): In charge of researching new technologies.
        - Researching technologies will change the game mechanics, give Players bonuses, and interact with the Kardashev Scale
        - Only the MoS will see the available technologies, which is the hidden information that will make MoS participate in the discussions
        - The technologies will be split into tiers based on difficulty of research so the MoR will be guaranteed to be able to do research that fits the research infrastructure at any point in the game
        - The researches will be randomly selected from a set of researches, so no player other than the MoR will know what researches are available each game.
        - TODO: unit upgrades (increased chance to hit, more hitpoints, abilities...)
        - Researches to have pre-requisites (money cost, X engineering researches required and so on. Check TI's research card design for a nice example)
    - Minister of Foreign Affairs (MoFA): Deals with Foreign Nations and neutral countries
        - TODO: hidden mechanic
    - Minister of Commerce (MoC): In charge of money management, which is the resource required to take action by everyone, including Foreign Nations.
        - They will be doing cooperation requiring investments (e.g. select a player, if they roll a die and win, gain money, otherwise, lose the investment)
        - There will be an investment deck composed of randomly selected cards which only the MoC will be able to take a look at
- World Events will be drawn from an event deck at each Phase. 
- Each role will have a victory condition they can work towards, and players can help each other with those conditions (for example, MoFA's victory condition may require being allies with every Foreign Nation. MoD can help this by eliminating uncooperative Nations)
    - MoD: Be the last Nation standing OR control 3/4 of the map.
    - MoS: Reach the end of the Kardashev Scale
    - MoC: (?) Have a turn where your Nation has 3/4 of the money in play
    - MoFA: Be allies with everyone, including neutral countries
- Kardashev scale
    - Being ahead of other Nations will provide various advantages, but the reverse also applies: being behind Foreign Nations will be costly
    - Increasing your Nation's Kardashev Scale value will allow the players to gain/increase an ability, very similar to how leveling up works in RPGs
    - Kardashev Scale will naturally increase over time, always creating a sense of urgency as well as a game clock.

Link to the GDC talk regarding procedural generation via "Abstraction Mountain" method:  https://www.youtube.com/watch?v=J5qnnxFoBss&ab_channel=GDC

Link to the slides of the said talk: https://ubm-twvideo01.s3.amazonaws.com/o1/vault/gdc2019/presentations/Grinblat_Jason_End-to-End_Procedural_Generation.pdf