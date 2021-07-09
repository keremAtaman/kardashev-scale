# Kardashev Scale
TODO: Game description

I outline my game design journey in the [Design Diaries](<./Design Diaries.md>)

Game rules can be found [here](<./Game Rules.md>)
## Version History
### v1.0 - Initial Release
- Initial release. As expected, many issues were found, which are outlined and addressed in v1.1
### v1.1 (in Progress)
- Making the game more simple and fun
    - Remove Basic Actions except char specific ones 
        - e.g. Money transfer of MoC should stay, but "shill" cards should go
    - Make a "Player mat" for players as well as foreign nations. Foreign nation player mat should clearly indicate relations and their effects when their cards are being played
        - e.g. If intellegence is high enough, have "reveal top card" be a part of turn order text for the Foreign Nation
        - Foreign nations' player mat should include which nations they are in good/bad/neutral terms with. This can be achieved by placing nation colors to good/bad/neutral areas. This can range from -3/3 (or more, but there needs to be some distance between war, neutral and alliance)
    - Make MoC the only person responsible for handling money. There is no need for all other players to deal with it when there is a specific role for it.
    - Remove Minister of Labor (MoL) for the time being - no need to have two shared resources required for same actions
    - Minister of Science (MoS) needs more early game cards to get rolling
        - They also need more interactions with the Kardashev Scale - this feels weird otherwise
    - Minister of Defence (MoD) may have too many on their plate - examine
    - (?) Create Minister of Intellegence (MoI) that dictates what the foreign nations can and can't do 
    - Minister of Foreign Affairs (MoFA) needs more things to do early game
    - Foreign Nation and event redo based on the changes above
    - Rework tiles based on the changes above
- Making the game easier to Edit and Update
    - All cards should be done via NanDeck, including reference cards
        - Reference Cards should show initial amount of gold per Player
    - Switch to TTS from Tabletopia - seems too much of a hassle to print individual cards and dealing with it
        - Use LUA code of TTS as much as possible for easier edits
        - https://api.tabletopsimulator.com/built-in-object/
    - Create a script that automatically executes NanDeck on the appropriate files
- Ensure each player is helping others while feeling unique
    - MoC: The only person responsible for acquiring and distributing money(TODO: how about tradable goods?)
    - MoS: "Researches" buffs that are helpful to players, but TODO: it does not feel like it cooperates much. It's main gimmick should be affecting the efficiency of turns and decks of players.
        - Feels like he needs to consist of "soft" (e.g. gain 1 gold after playing a card) and "l33t" (aka scry 1, draw 1 extra) synergies
    - MoFA: Deals with foreign powers and events. Useful for agreements and seeing what is happening. TODO: this character needs to be able to create more stories
    - MoD: Deals with territory and tiles. Must have close ties with MoFA to balance allies and enemies, and close ties with MoS to improve the military
- Design Decisions
    - What should tiles do? There should be some incentive to fight over tiles without them being too complicated.
        - Have the tiles increase efficiency or magnitude of actions (e.g. gain gold equal to the # of tiles you own)
        - Some, if not all tiles, should give a unique bonus, similar to strongholds in the Dark Crusade (e.g. Athens tile: boost to science output)
            - Having tiles like that also offer replayability and interesting game modes
    - Should first player token rotate at the end of each round, stay where it is, or switch around via events and effects
        - Chosen: It stays where it is, changes with events
    - Remove/ edit senate voting
        - Chosen: Senate voting should still be a thing, as acts of aggression can affect others
    - Basic Action Cards:
        - Remove basic cards?
        - Or find a way to make basic cards simpler? 
            - E.g. only have "put this card to your hand instead of discard after turn ends". 
    - Tradable goods: Should they still be a thing?
        - No for the time being. MoC already has gold as a resource, and tradable goods feel a bit too similar to that
    - TODO: Should everyone play as deckbuilder? 
        - MoD for example feels weird
        - MoS can be a bit more exciting - maybe have "tiered" researches (e.g. a Tier 1 Research that says "draw 3 Tier 2 Researches" )