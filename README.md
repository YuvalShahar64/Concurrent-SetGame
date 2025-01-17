# Concurrent-SetGame
A Java-based implementation of a multithreaded version of the "Set" card game, utilizing advanced concurrency techniques like thread synchronization, queues, and fairness mechanisms. The project integrates human and non-human players interacting in real-time with a GUI-backed game environment.

- Clone the Repository
- This project uses Maven as the build tool. To compile and build the project, run: mvn clean compile
- To start the game, execute: mvn exec:java
- Project Structure
        - src/main/java/bguspl/set/ex: Contains the main implementation files:
            - Dealer.java: Manages game flow, shuffles and deals cards, checks for legal sets, and announces winners.
            - Player.java: Represents human or non-human players, processes actions, and interacts with the table.
            - Table.java: The shared data structure representing the game board, tracking placed cards and tokens.
        - src/test/java/bguspl/set/ex: Contains unit tests for the game's key components.        
        - pom.xml: Maven configuration file for dependencies and build instructions.
- The game supports both human and non-human players. Players interact with the game as follows:
    - Human players use the keyboard to place or remove tokens on cards (mapped to a 3x4 grid).
    - Non-human players simulate random key presses via threads.
    To configure the number and type of players or other game settings, modify the config.properties file in the resources         directory.


- Example Gameplay
1. Players attempt to find a legal set of three cards on the table.
2. Use the keyboard (e.g., Q, W, E) to place tokens corresponding to card slots.
3. When a set is found, the dealer thread checks its validity:
      - A valid set is awarded points, and new cards are dealt.
      - An invalid set incurs a penalty, freezing the player temporarily.

