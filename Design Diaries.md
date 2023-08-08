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
    - Minister of Science (MoS): In charge of researching new technologies.
        - Researching technologies will change the game mechanics, give Players bonuses, and interact with the Kardashev Scale
        - Only the MoS will see the available technologies, which is the hidden information that will make MoS participate in the discussions
        - The technologies will be split into tiers based on difficulty of research so the MoR will be guaranteed to be able to do research that fits the research infrastructure at any point in the game
        - The researches will be randomly selected from a set of researches, so no player other than the MoR will know what researches are available each game.
        - Researches to have pre-requisites (money cost, X engineering researches required and so on. Check TI's research card design for a nice example)
    - Minister of Foreign Affairs (MoFA): Deals with Foreign Nations and neutral countries
    - Minister of Commerce (MoC): In charge of money management, which is the resource required to take action by everyone, including Foreign Nations.
        - They will be doing cooperation requiring investments (e.g. select a player, if they roll a die and win, gain money, otherwise, lose the investment)
        - There will be an investment deck composed of randomly selected cards which only the MoC will be able to take a look at
- World Events will be drawn from an event deck at each Phase. 
- Each role will have a victory condition they can work towards, and players can help each other with those conditions (for example, MoFA's victory condition may require being allies with every Foreign Nation. MoD can help this by eliminating uncooperative Nations). So victory conditions can be like:
    - MoD: Be the last Nation standing OR control 3/4 of the map.
    - MoS: Reach the end of the Kardashev Scale
    - MoC: (?) Have a turn where your Nation has 3/4 of the money in play
    - MoFA: Be allies with everyone, including neutral countries
- Kardashev scale
    - Being ahead of other Nations will provide various advantages, but the reverse also applies: being behind Foreign Nations will be costly
    - Increasing your Nation's Kardashev Scale value will allow the players to gain/increase an ability, very similar to how leveling up works in RPGs
    - Kardashev Scale will naturally increase over time, always creating a sense of urgency as well as a game clock.

This feels like a good starting point to create a bit more of the game, but I will call it for today.

Link to the GDC talk regarding procedural generation via "Abstraction Mountain" method:  https://www.youtube.com/watch?v=J5qnnxFoBss&ab_channel=GDC

Link to the slides of the said talk: https://ubm-twvideo01.s3.amazonaws.com/o1/vault/gdc2019/presentations/Grinblat_Jason_End-to-End_Procedural_Generation.pdf

# 11th of July, 2021: Digging deep into game mechanics (In process of creating v1.1)

It turns out a really good way for me to think about the game and it's mechanics/problems etc. was doing so while biking. I usually bike with headphones, so I did not have much concentration. Today however, thanks to the fact that my phone's batteries were dead, I discovered biking is a great time to think about mechanics and solutions. There were no distractions, and something about the road makes me think more clearly.

So, what came out of my biking session? Long story short:

- Write the goals of versions for each version. That way, it will be easier to figure out when a version can be released, examined, and what objectives need to be achieved
- It will sound silly, but I learned that I should not write the version log until after that version is finished. I should however, have a short list for what tasks etc. should be done for the current version. I'll use Github Issues to keep track of what objectives need to be done for which versions. TODO bot should make it easy: https://github.com/JasonEtco/todo
- I think I have a decent gameplay loop. At each turn, players will play the cards face down and put them in a pile. The World Event(s) and Foreign Nation cards that say "Have Nation X take all of their actions" will also be added to that pile and shuffled. The cards on that pile will be drawn and resolved one at a time
- Players can have a set of decks, each having a specific theme (e.g. MoD will have one deck for military and one deck for intellegence actions). Players can pick and choose one or many cards from those decks to be played. However, to prevent spamming of all actions every turn, some limitations such as "you can only play one card from this deck" or "pay 1 gold to play a card from this deck" may be implemented.
- Foreign Nations, just like the players, can have multiple designated decks (e.g. a deck for covert ops, foreign relations...)
- Foreign nations, in v1.2 and later, can have custom abilities and decks.
    - e.g. England: Play two covert action cards instead of one each turn. Whenever a covert action card is played, gain 1 gold.
- The order in which I think I need to design the roles/mechanics should be as follows. My reasoning is that I need to define tile ownership and money mechanics before Foreign Nations, and when these are put into place, design MoS as that role will affect others' mechanics
    1. Minister of Defence 
    2. Minister of Commerce
    3. Foreign Nations and Minister of Foreign Affairs
    4. Minister of Science and the Kardashev Scale (as this role affects every other role's mechanics)
    5. A second look at Foreign Nations, MoFA and then World Events

# 12th of July, 2021: MoD part 1 (In process of creating v1.1)
Ok, let's get into the meat of Minister of Defence; they provide your Nation's security with both armies and covert actions. 
- Armies
    - Recruit & move troops.
        - (?) Troops should have an upkeep cost, so the MoD just doesn't spam recruit as an action and we don't have 100+ troop models roaming around.
    - Bully Foreign Nations and prevent Foreign Nations from bullying you
    - Capture and secure Neutral Ground
    - Attack Foreign Nations that don't have nukes
    - (?) Prevent Foreign Nations from using their armies against each other or neutral countries
- Covert Actions
    - Observe and intercept Foreign Nation actions
    - (?) victory condition
    - (?) Steal resources from Foreign Nations
    - Prevent covert actions being done to you
    - Have intellegence levels between countries, which will determine what you can do to Foreign Nations and what they can do to you, and the chances of successful covert actions.
    - Failed covert actions will decrease relations with Foreign Nations
    - (?) Increase influence/take control of neutral countries

# 13th of July, 2021: MoD part 2 (In process of creating v1.1)
Created MoD's cards based on the points above. Of course, everything below is subject to change as the game design evolves.

| Text                                                                                                                                                                                                                                                                                                                                                                                                             | Credit | Type       | Name              |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ---------- | ----------------- |
| Pay X Credits to move X Troops to any tile they are allowed to move to                                                                                                                                                                                                                                                                                                                                           | 0      | Army       | Mobilize Troops   |
| Pay X Credits to place X Troops to any tile within your Nation                                                                                                                                                                                                                                                                                                                                                   | 0      | Army       | Recruitment Drive |
| Do an Intellegence Check against a Foreign Nation. If successful, increase intellegence against that Nation by 1. Otherwise, declare relations with that Nation by 1.                                                                                                                                                                                                                                            | 1      | Covert Ops |
| Select a Neutral Country you have the most influence on (no ties allowed). Do an intellegence check against that Neutral Country.<br><br>If successful, add that Neutral Country to your Nation. Decrease relations with any Foreign Nation that had influence on that Nuetral Country by 1.<br><br>If unsuccessful, decrease relations with all Foreign Nations that have influence in that neutral coutry by 1 | 3      | Covert Ops | Coup              |
| Select a tile, then do an Intellegence Check against the owner of that tile.<br><br>If successful, increase influence in that tile by 1.<br><br>If unsuccessful, decrease relations with all Foreign Nations that have influence in that tile by 1                                                                                                                                                               | 1      | Covert Ops | Spread Influence  |
| Select a Foreign Nation, then do an intellegence check against that them. If successful, MoD can negate a card that Foreign Nation plays on their next turn. If unsuccessful, decrease relations with that Foreign Nation by 1                                                                                                                                                                                   | 2      | Covert Ops | Sabotage          |
| Select a Foreign Nation, then do an intellegence check against them. If successful, MoD looks at the top 3 card of each of that Foreign Nation's deck. If unsuccessful, decrease relations with that Foreign Nation by 1                                                                                                                                                                                         | 1      | Covert Ops | Spy               |
| TODO: steal science                                                                                                                                                                                                                                                                                                                                                                                              |        | Covert Ops | Steal Tech        |
| TODO: steal credits                                                                                                                                                                                                                                                                                                                                                                                              |        | Covert Ops | Steal Credits     |
| Select a tile, then do an intellegence check against the owner of the tile. If successful, remove number of troops belonging to the owner equal to the amount by which the intellegence check succeeded. If unsuccessful, decrease relations with all Foreign Nations that own/at least have one influence on that tile by 1                                                                                     | 2      | Covert Ops | Terrorism         |


# 13th of July, 2021: MoC (In process of creating v1.1)
I'd say MoD is somewhat stable for now, now let's do MoC. The key things to consider when doing MoC are:

1. Ensure MoC cannot spam the same money making tools over and over - there needs to be diversity, interesting decisions, and no endless loops (at least in the beginning) that give infinite money
    1. Maybe limit the # of investments that could be played per turn? And have researches to increase the amount?
2. The MoC is responsible for who should be given how much money. He should have a module that sets how much money should be given to players at the end of each turn, and can change the numbers on the module by playing a X cost "module readjustment" card
3. MoC should be able to do risky investments that require cooperaation/plannning with other players 
    1. e.g. if a tech is researched this turn, gain X gold. Otherwise, lose all invested gold
4. (?) To prevent overloading the MoC, start with a small sample deck of investment cards, then gradually expand the selection of investments. Or, have deckbuilder like things for investments so they only deal with a certain set of opportunities.
5. (?) Maybe have the MoC do investments BEFORE cards are dealt so things can be resolved within the current turn

So here's what came out:

| Text                                                                                                                                                                                                                                                                              | Credits | Type            | Name                       |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | --------------- | -------------------------- |
| You may edit how much Credits at the end of the turn each player receives                                                                                                                                                                                                         | 1       | Diversification |
| When you play this card, place 6 Credits on it. This card stays on the field until there is no more Credits on it<br>At the start of your turn, take 2 Credits from this card. If there is no Credits remaining on this card, shuffle it back to the minister of commerce's deck  | 1       | Investment      |                            |
| When you play this card, place 8 Credits on it. This card stays on the field until there is no more Credits on it<br>At the start of your turn, take 2 Credits from this card. If there is no Credits remaining on this card, shuffle it back to the minister of commerce's deck  | 2       | Investment      |                            |
| When you play this card, place 12 Credits on it. This card stays on the field until there is no more Credits on it<br>At the start of your turn, take 3 Credits from this card. If there is no Credits remaining on this card, shuffle it back to the minister of commerce's deck | 4       | Investment      |                            |
| When you play this card, place 16 Credits on it. This card stays on the field until there is no more Credits on it<br>At the start of your turn, take 2 Credits from this card. If there is no Credits remaining on this card, shuffle it back to the minister of commerce's deck | 5       | Investment      |                            |
| When you play this card, shuffle it into the event deck<br>When this card is played from the event deck, each Player doubles their money. Then, shuffle this card into MoC's deck                                                                                                 | 3       | Stonks          |                            |
| Receive 3 Credits                                                                                                                                                                                                                                                                 | 0       | Investment      |                            |
| Select a player, put this card in front of them, then put 2X Credits on this card. Until the end of this turn, if they do a check and are successful, receive all the Credits on this card.                                                                                       | X       | Stonks          |                            |
| Call Heads or Tails, then toss a coin. If successful, gain 2X Credits                                                                                                                                                                                                             | X       | Stonks          | Push your luck             |
| Pick a meter, guess which way it will go next, then put this card in the direction called and place 2X Credits on this card.<br>When the meter moves, if it moves in the guessed direction, gain 2X Credits.                                                                      | X       | Stonks          |                            |
| Call a number, then roll a die. If successful, gain 6X Credits.                                                                                                                                                                                                                   | X       | Stonks          |                            |
| Place 4X Credits on this card. If another "Stonks" card is successful until end of the next turn, gain all the Credits on this card.                                                                                                                                              | X       | Stonks          | Derivatives                |
| Gain 1 Credits for each Tile you own                                                                                                                                                                                                                                              | 0       | Investment      | … And Taxes                |
| Gain 9 Credits                                                                                                                                                                                                                                                                    | 5       | Investment      | Hedge Funds                |
| Place this card in front of the Minister of Defence. Until the end of this turn, whenever they successfully attack or defend a tile, gain Credits equal to the number of enemy Troops                                                                                             |         | Trust           | Risk (get it?)             |
| Place this card in front of Minister of Science. Until the end of next turn, whenever a successful research is made, gain credits equal to the tier of that research                                                                                                              |         | Trust           | Science = Profit = Science |
| Place this card in front of Minister of Foreign Affaris. Until the end of the next turn, whenever a successful aggreement is made, gain 4 Credits                                                                                                                                 |         | Trust           |                            |
| Place this card in front of a Foreign Nation. Until the end of this turn, whenever a card that Foreign Nation plays gets negated, gain 3 Credits                                                                                                                                  |         | Trust           | Salt to the wound          |
| Place all your Credits on this card. Guess which resources the next World Event will affect. If you guess correctly, gain Credits equalling the Credits you put on this card times the number of successfully guessed resources                                                   |         | Stonks          | YOLO                       |

# 19th of July, 2021: Foreign Nations (In process of creating v1.1)

Let's start with the Foreign Nations - their main purpose is to cause crises and make the game difficult for the players. There are quite a few cards that say "Increase Resource X. Any Nation who has less Resource X than you loses 4 Gold". The design aim is to have a Foreign Nation overpower you with a certain resource's abundance, but I feel this may make the game too difficult. I'll have to keep a close eye on it.

Also, there are "Aggression" cards, which the MoFA should be able to react to

| Effect                                                                                                                                                                                                                                                                                                                                  | Type       | Name                      |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ------------------------- |
| Place 1 influence on an adjacent territory you do not control                                                                                                                                                                                                                                                                           | Aggression | Spreading Influence       |
| If you have  no casus belli tokens on the map, place a casus belli token on an adjacent tile, then put this card to the top of the pile<br><br>Otherwise, move your troops to a territory with your Casus Belli token on it. If your troops are the only ones remaining there at the end of the turn, add that territory to your Nation | Aggression | WAAAGH                    |
| Gain 4 Credits. Any Nation that has less Credits than you loses 4 Credits                                                                                                                                                                                                                                                               | Commerce   | Economic Warfare          |
| Gain 6 Credits                                                                                                                                                                                                                                                                                                                          | Commerce   | Hedge Funds               |
| Gain 4 Credits                                                                                                                                                                                                                                                                                                                          | Commerce   | Easy Mark                 |
| If you have no nukes, build 2 nukes                                                                                                                                                                                                                                                                                                     | Defence    | Stockpile                 |
| Remove 1 influence from a territory you own or is adjacent to you                                                                                                                                                                                                                                                                       | Defence    | Purge                     |
| Increase the attack of your Troops by 1. Increase your Kardashev Scale by 1. Remove this card from the game once it is resolved.                                                                                                                                                                                                        | Defence    | Troop Enhancements        |
| Increase the health of your Troops by 1. Increase your Kardashev Scale by 1. Remove this card from the game once it is resolved.                                                                                                                                                                                                        | Defence    | Troop Enhancements        |
| Increase the chance to hit of your Troops by 1. Increase your Kardashev Scale by 1. Remove this card from the game once it is resolved.                                                                                                                                                                                                 | Defence    | Troop Enhancements        |
| Add 2 Troops to your Nation. Any Nation that has less Troops than you loses 4 Credits                                                                                                                                                                                                                                                   | Defence    | Big Stick Policy          |
| Do an intellegence check against the Player Nation. If successful, increase your intellegence by 2                                                                                                                                                                                                                                      | Defence    |                           |
| Increase the Kardashev Scale by 2 for this Foreign Nation                                                                                                                                                                                                                                                                               | Science    |                           |
| Increase the Kardashev Scale by 1 for this Foreign Nation                                                                                                                                                                                                                                                                               | Science    |                           |
| Increase Kardashev Scale by 1. Any Nation whose Kardashev Scale is less than yours loses 4 Credits                                                                                                                                                                                                                                      | Science    | Technological Superiority |

# 22nd of July, 2021: MoFA (In process of creating v1.1)

Main idea is for this character to interact with Foreign Nations and neutral countries.

Aside from the cards, the following should apply to MoFA:

- Whenever a Foreign Nation takes an Aggression action, the MoFA should be able to react to it. The way to do it would be either soft or hard power
- Soft power:
    -   https://softpower30.com/what-is-soft-power/
    - Science is soft power
    - Economy is hard power
    - Aggreements and facilitation is soft power

# 28th of February, 2022 (In process of creating v1.1)

It has been... so long. But the good news is, I have a two week break while switching jobs, so I should be able to focus more on this and hopefully release the alpha

I've realized that I spent WAY too much time and effort on the Tabletop Simulator framework which made it hard to come back and work on this. So I'll switch gears and focus on generating a hard copy of the game rather than an online one. This will also give me the opportunity to look at the cards and see how they jive with each other before continuing with MoFA and MoS

It is also now I have realized that since I am out of my current job, I lost the Windows license, and more importantly, the excel that came with the job. I'll have to look for alternatives of storing data in a nice- csv like format. I opted to use wps office, and have installed the chrome office extension as a backup.

Going over the foreign nation cards, I realized I need to add more cards to increase foreign nations' effects on each other. Them signing nuclear arms treaties and such. This will be a TODO for the next release.

Speaking of which, I have moved a lot of items, including Minister of Science, to the next release. I feel like the core gameplay loop exists, and I need to observe how it plays before moving on with other gameplay items.

I am glueing paper in front of Magic cards and then writing on those cards with a pencil my cards. When I am done writing all of the cards, I will playtest for the first time. Exciting! But I will admit, writing the description of each card and then pasting the paper with the description to the magic card turns out to be a laborious task. I've only finished Foreign Nation cards (which only has 14 cards as of writing) and needed to take a break. To speed up the process, I decided to only write the minister, cost and name on the card rather than the entire card text, which I have to address before I invite others for playtesting (or not... We'll see). My hope is that this way, I don't have to change card text in both software documentation and the card itself, but just on the software documentation

# 1st of March, 2022 (Playtesting v1.1)

Exciting day, as this will be the playtesting of v1.1. Here are some of my notes:

- Increasing intellegence should be a basic action for MoD. the effect should be:
    - Do an Intellegence Check against a Foreign Nation. If successful, increase intellegence against that Nation by 1. Otherwise, decrease relations with that Nation by 1.
- Moving troops around, recruiting troops and building nukes should be basic actions for MoD.
- Increasing/Decresing relations should be a basic action for MoFA. The effect should be:
    - Choose a Nation. You may decrease relations by 1 with them (given no nuclear war), or you may roll a Diplomacy check instead and increase relations by 1 if successful
- Ability to distribute Credits between players should be a default action for MoC.
- Default actions should also be cards so they can interact with mechanics involving events and event resolution
- MoD's steal tech should only be used against a nation that has a higher KS than the player Nation
- This I have to think about: there are turns where the best action a player can do is their default/do nothing. I am not sure if this is desired or not
- Players can draw 5 cards and discard up to 3 to draw that many new cards. This feels like a nice number for learning cards and going through abilities. This number may need to change if a player cannot go through their deck fast enough/too fast
- MoC: The ability to distribute Credits between players should not be a card, as it will have to occur quite frequently (unless the players start with a decent chunk of starting Credits). 
- When you roll a die, it does not feel exciting. Maybe I should add critical successes and failures and roll a d20 instead of a d6 for some rolls 
- It feels having a single foreign Nation is slow. At least 2 will be needed to spice things up
- Tiles can be more unique to give a "I am so happy/mad I got this tile" feel
    - Capital tiles: These tiles ive special charactristic to the Nation that controlls them. Also, create a set of capital tiles and give the player Nation a tile from one of that set
- How can it feel like I am both experiencing scope creep and the feeling that I am cutting features to the point where I am not even in the level of a minimum viable product? It feels the current features are not enough to be fun yet but at the same time it feels like I am trying to cram too much to the game. So let's get back to basics and look at my core gameplay loop:
    - Players are experiencing a variety of challanges and they must all work together to achieve them.
        - There is a Kardashev Scale the players have to keep up with. This implies each Nation must have a "increase KS" card that occurs every now and then
        - Foreign Nations are causing crises/difficulties. This is not happening yet. Giving "personalities" and weaknesses to foreign nations should solve this issue
        - More synergies will be needed:
            - MoS -> All: Permenant upgrades that benefir players. MoS gets to pick what area (military etc) to invest in
            - MoC -> All: Everyone needs Credits!
            - MoFA -> All: Agreements
            - MoD <-> MoFA: Influence, Big Stick Policy, the ability to block Foreign Nations, Casus Belli + war combo
            - MoD -> MoS: Stealing tech
            - MoD -> MoC: Stealing Credits, plus taking more land increases Credits earned
            - MoD/MoFA -> Foreign Nations: Looking at the Foreign Nations' deck and altering it
            - MoFA -> Foreign Nations: Using Soft/Hard Power to block cards
    - Unexpected and exciting things can happen as cards are being resolved one by one. This is achieved by Foreign Nation cards as well as event cards
- Welp, I have created new Nations (see Nations.xlsx, which will replace Foreign Nations document eventually) and MoS cards

# 17th of January, 2022 (After platest v1.1)

So, it has been a bit of a break eh? 10 months or so, but I am back.

For the record, I did write most effects on my magic cards and made tiles to play with, but I did not feel... Excited. The process of contantly editing cards seemed daunting, and I was not getting too much pleasure out of the game during my playtest so many months ago.

I think I got lost in the detail, costs, logistics etc. before I could actually stop, figure out the forest I have created before moving on. So, I want to take a step back and try to satisfy the design objectives mentioned at the top of this before going on.

To reiterate the core principles: 
- The game should be cooperative in which no player can be a "power player" and tell everyone what to do
- Each player's function must be different, leading to an asymetric coop game. 
- The game should encourage and require cooperation between players
- Players should experience the difficulty of balancing resources between everyone to deal with the challanges the game throws at them
- The game should be able to be picked up easily by an average board gamer.

Drilling down further:
- ~~Players will act as different Ministers (e.g. Minister of Commerce, Science...) of a Nation. The Nation will require all the Ministers' departments to function properly.~~ Subject to change - I am having second thoughts about how I can fit core principles with the specific minister based structure
- Players will have hidden information, which will force everyone a turn to speak and participate in the decision making
- The challange the game will be throwing at the players will be coming from Foreign Nations, World Events, and the constant need to technologically advance which will come from the Kardashev Scale mechanic.
- ~~Most of the information regarding the game will not be in a rulebook, but in Ministers' Character Sheets and the cards that are played.~~ I... am not sure about this one. I like the idea, but it may be reaching, and it will severely limit what can be done in the first turns and the enjoyment of the veterans. Still, I shouldn't make the game too hard

Lastly, I really like the idea of players taking their turns simultaneously and world event/foreign nations cards getting in the play deck along with players actions - feels like a "oh boy here we go" holding breath moment, like how the crises are resolved in the BSG board game

The rest, I'll think about. But I need to think about the general interactions before I dive way deep into cards (I may not even have cards by the end) the characters will have and so on

Today was just reflecting and reiterating. Hopefully in less than 10 months I will have a new entry here

# 6th of August, 2023

I am not sure the feet dragging has been caused by my laziness or something else. I'll try to enforce the harder rule of "make progress at least once per week" and see how far it takes me. Even if it burns me out, I feel it would be a good learning experience.

I decided to scrap the cards and start from scratch, a possibly destructive habit I have for my coding as well. Maybe I should learn how to make my big projects more "re-enterable" rather than "if you are not in this exact mindset and remembering 10 different things at the same time, don't bother"

Going to basics, I really like the idea of each player having something that benefits the other players - however, I don't think every player should be dependent on the other player, maybe that is a bit too extreme. I'll keep this in mind, maybe the aim is to have the players be able to do one thing better rather than requiring another player to do the one thing. For example, maybe everyone can generate money but the player responsible for money does it better. This philosophy will also likely allow the player counts to be more flexible - this idea comes from "the Captain is Dead", "Pandemic" and "Dragonfire". I must admit though, I like the asymetrical aspect of the players (e.g. money guy behaves differently than research huy), which would give more replayability to the game ("hey, I want to play this character next!"). Plus, I don't want to be a pandemic clone, and this route is now giving me the feeling that I'd have to drop everything, which I am not keen on yet. Hmm, maybe I put this idea to the backlog, I must admit I am split.

Maybe Concordia's "Whenever a player plays a card, everyone benefits from it some way"?

# 7th of August, 2023

Let's start with a basic effect:
- When you play this card, all players gain 1 gold

It's nice right? Good start, and everybody will pat you in the back for playing that card, unless there is a card that says "When you play this card, all players gain 100 gold". Next, how about:

- All players can play an extra card in their turn

Twice the possibilities, twice the fun! Now, let's change the text a bit:

- Pay 1 gold to activate this card. All players can play an extra card in their turn

That's a bit of a gameplay loop right there! Player 1 plays the gold giving card, Player 2 plays the action giving card, and everyone in the table is merry and shouting and happy and thinking of how richer their next turn is.

Ok, one more addition:

- You cannot tell the other players that you can play this card or have this card. Pay 1 gold to activate this card. All players can play an extra card in their turn

Adding a nice little surprise feel to the card.

Let's add a rule to make the above possible to prevent all the cards having the "You cannot tell the other players that you can play this card or have this card" text:

>**You can talk in general about what your cards can do, such as "this will help us with playing cards", but cannot talk specifics about the card**

But how can we make sure that the other players actually will not realize that you have the card in your hand? There must be randomness to the card a player draws, and the cards should not come from a small pool. 

But what if a player draws a card they cannot play, but another player can, or if it would be more beneficial for the other player to play that card? Now we need another rule:

>**You can give another player a card from your hand instead of playing a card**

And if no one has a decent card to play?

>**You can choose to discard X cards from your hand to draw X cards from the deck instead of playing a card**

But what if you did not communicate the card you are discarding well, and another player needed that card? This actually leads to a fork in the road: we can either choose to say "Shouldve communicated better, and as a punishment that card is gone", or we can say

>**You can draw a card from the discard pile instead of playing a card**

Both valid options. But I want to take the Occam's razor approach, so instead of the rule above, I'll say that if you discard a card, it is gonezo. There may be cards that will allow you to interact with it, but interacting with it should not be a starting action. This will add weight to the decision of searching for a new card, after all, it takes effort and sacrifice to unlock new horizons.

***

We actually need an objective for the players and a way to make the game exciting, don't we? Should it be a timer? - Nah, I feel a raw timer feels a bit cheap if it does not have any in-game effects or justification. That being said, the game, at least at the time of this writing, was named Kardashev Scale (tm) wasn't it? So let's use that as our timer/objective.

>**In Kardashev Scale, the players have to keep up with the increasing demands of the forever modernizing world**

And what prevents the players from catching up to Kardashev?

>**Each turn, players place the cards they want to play to the middle. X World events also get shuffled in the middle, and the cards in the middle have their effects resolved one at a time.**

World events can be beneficial or detrimental, and the randomized order of play can make or break some plans. Ok, we're getting somewhere.

***

I'm actually having doubts about the theming - players belonging to a country, running against the Kardashev scale. I may need to change the theming later, once the game is more fleshed out. I may want to pursue a cult theme. Anyway, back to the main difficulty the players have to face.

Actually, I like the idea of the cult - it allows for goofy cards and things to happen in game ("I play the orgy card to give everyone +1 happiness and +1 STDs"), and "Kardashev Scale" could be replaced by the "cult leader" whose demands are growing more and more ridicolous as they are consuming more and more drugs over time. This can also explain the "don't talk about the cards we have" rule, as you are supposed to work somewhat in secrecy. Also the idea of summoning an eldritch god by a ridicolous ritual is a good objective. And players can recruit people from the middle, which can create a deckbuilding aspect.

***

Players have some basic cards that start in their hand/deck at the start of the game, but should also have some cards that are picked randomly from the start to add replayability.

***

What should be the player resources? Money, number of followers, follower happiness, heat (how much the law is coming after the cult) - good start. 

***

Let's try to put this giant text blurb together:

>**Players represent high ranking members of the same cult, with the goal of summoning their eldritch god despite the difficulties and benefits the world will provide for them. Each turn, players will be able to take actions by playing cards, including buying followers from the shared market. The player actions and events will be resolved in a random order.**

Some of the basic action cards include:

- Buy/Recruit: Acquire a card from the middle 
- Give: Give a card to another player
- Profit: All players gain 1 gold
- (?) Scrap: Remove a card from the deck

Some of the world events include:
- Increase/decrease heat by X
- Lose/Gain X gold
- Refresh the shared market
- Give/take X cultists

Some summoning conditions include:
- Have X cultists
- Have X gold
- Play X cards in one turn
- Reach X happiness
- Any combination of the above

Some cultist leader asks include:
- Each/signle cult leader to sacrifice X cultists
- Give X gold

Some of the follower/other card effects include:
- Have another/all players gain X
- Whenever a follower is played, gain X

***

Hmm, maybe I have too many resources to deal with - let's just start with gold and see where it leads

# 8th of August, 2023

I feel "heat" is too good of a mechanic to pass up - It creates very nice narrative scenarios, push your luck situations and adds tension to the game. 

>**You lose the game if HEAT reaches a certain level. Depending on the HEAT level, you may need to add one or multiple cards from the heat deck to the middle where it will be shuffled with all the other cards that will be played. The cards from the HEAT deck tends to generate more HEAT and cause other problems to the players.**

This means we also need a basic follower/action that says:

- Pay X gold. Reduce HEAT by Y

Which also paves way for interesting decision making cards like:

- The Abductor: Gain X HEAT and Y followers.

***

I suppose having both cultists to get from the middle of the board and a cultist counter can be confusing, so let's clear the air on that:

>**Each player starts with X basic cultists, Y random cultists, and X+Y cultist tokens. Whenever a player acquires a cultist from the shared market, they get a cultist token.**

***

Maybe HEAT can replace the cultist leader mechanic? After all, cutting the game down to it's simplest bits is what is reccomended by so many game designers, right?

***

Also, what if there are no good cards in the shared market?

>**Discard the X rightmost cards in the shared market at the end of a round, shift all cards to the right and then fill the marketspace**