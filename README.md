
This is my B143 AI Studio project. I built a Reinforcement Learning agent
to play the game of Nim (3 piles of 3, 4 and 5 objects, normal play – whoever
takes the last object wins).

I wanted to compare two different RL approaches we covered in the module:
- **Q-Learning** – an associative method that learns a value for each
  state-action pair.
- **LR-I Learning Automaton** – a non-associative method that updates action
  probabilities directly (reward-inaction, so b = 0). I used one automaton per
  state so it could handle the different positions in the game.

Everything is coded from scratch with numpy and matplotlib (no Gym/PyTorch),
so the logic is easy to follow.

## How to run it
Just open `B143_Nim_RL.ipynb` in Google Colab and run the cells from top to
bottom. A normal CPU runtime is enough, it only takes about a minute.

## How I tested it
Both agents were trained against a mixed opponent (plays the perfect move 70%
of the time, random the rest) and then tested against a fully random opponent
and a perfect (nim-sum) opponent.

## What I found
- Q-Learning ended up winning 100% of games against both the random and the
  perfect opponent, so it basically learned the optimal strategy.
- The LR-I automaton won about 99% against random but 0% against perfect play.
  So it learned to beat a weak opponent but couldn't reach optimal play, which
  matches the idea that associative methods handle this kind of game better.
