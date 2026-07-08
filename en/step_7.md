## Back to the sea Neil

In this step, you'll end the game when Neil runs out of lives.

> [!TASK]
>
> Click on the `Stage`, then click the `Backdrops`{:class="block3looks"} tab.
>
> Add a new backdrop called `GameOver` for when Neil runs out of lives. As before, you can design it however you like.

Here's the `GameOver` backdrop from the example project:

![The GameOver backdrop from the example project, a blue screen reading BACK TO SEA!](images/game-over-backdrop.png)

> [!TASK]
>
> Neil loses when he runs out of lives. On the Stage, add a new script — much like your winning one — using a `forever`{:class="block3control"} loop and an `if then`{:class="block3control"} block.
>
> When `lives`{:class="block3variables"} is less than `1` and `game over`{:class="block3variables"} is `0`, switch to your `GameOver` backdrop and set `game over`{:class="block3variables"} to `1`.
>
> ```blocks3
> when green flag clicked
> forever
> if <<(lives) < (1)> and <(game over) = (0)>> then
> switch backdrop to (GameOver v)
> set [game over v] to (1)
> end
> end
> ```

> [!TASK]
>
> Make a new message called `game over`. Add a `broadcast ()`{:class="block3events"} block to your new script, so the other sprites know the game has ended.
>
> ```blocks3
> if <<(lives) < (1)> and <(game over) = (0)>> then
> switch backdrop to (GameOver v)
> set [game over v] to (1)
> +broadcast (game over v)
> end
> ```

> [!TASK]
>
> Click on the `Ranger`{:class="block3looks"} sprite. When the game is over, the Ranger sends Neil back to sea.
>
> Add a `when I receive ()`{:class="block3events"} block for the `game over` message, and make the Ranger `say () for () seconds`{:class="block3looks"} to say "Off you go!".
>
> ```blocks3
> when I receive (game over v)
> say [Off you go!] for (1) seconds
> ```

> [!TASK]
>
> When the game ends, all the stop sign clones are still lying around town. Get them to tidy themselves up.
>
> Click on the `Sign`{:class="block3looks"} sprite. In the clone's `forever`{:class="block3control"} loop, add an `if then`{:class="block3control"} block that checks whether `game over`{:class="block3variables"} is `1`. If it is, `delete this clone`{:class="block3control"}.
>
> ```blocks3
> when I start as a clone
> forever
> if <<touching (Neil v)?> and <key (space v) pressed?>> then
> change [score v] by (10)
> change [stuff to smash v] by (-1)
> delete this clone
> end
> +if <(game over) = (1)> then
> delete this clone
> end
> end
> ```

Click the green flag and let the Ranger catch Neil three times. The `GameOver` backdrop appears, the Ranger sends Neil back to sea, and the leftover stop signs disappear.
