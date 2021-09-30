# ai-minesweeper
Knowledge-based AI to optimally play minesweeper.

# How to run

Extract the contents to a folder. Install python and then pygame with "pip install pygame". Run runner.py. To watch the AI play, just hold down "Play as AI".

# How does it work?

When you click on a (non-mine) cell in minesweeper, you see how many of the surrounding cells are mines.
Thus, say we clicked on a cell 'A' and it was surrounded by cells 'B, C, D, E' and the number was 2, we know that of 'B, C, D, E' 2 are mines. We can represent this as a sentence like this:

{B, C, D, E} = 2

We could then click on another cell, and say that cell was surrounded by 'B, C'. If the number is 0, we know that neither B or C are mines:
{B, C} = 0

From the first sentence and the second, we can surmise that D and E are mines, and B and C are safe. Making inferences like this and figuring out what tiles are safe and what tiles are not, is the
essence of the AI. We can then choose what moves to make only from our list of safe moves until we have solved the board.

But, what if we don't know any safe moves? (for example, at the beginning of the game, or if we've expended all safe moves). At that point, our only choice is to pick randomly, which is why you will see that
sometimes the AI will fail on the first few turns - it accidentally, randomly selects a mine, since at that point it has no information, no knowledge of what cells are safe.
