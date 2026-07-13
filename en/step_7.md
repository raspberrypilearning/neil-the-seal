## Catching Neil

In this step, you'll give Neil some lives to lose when the ranger catches him.

> [!TASK]
>
> Click on the **Stage**. Make a new `variable`{:class="block3variables"} called `lives`, and choose **For all sprites**.
>
> Tick its checkbox so the player can see how many lives Neil has left.
>
> Add it to your `when green flag clicked`{:class="block3events"} script and set `lives`{:class="block3variables"} to `3` at the start.
>
> ```blocks3
> when green flag clicked
> switch backdrop to (Town v)
> set [score v] to (0)
> set [stuff to smash v] to (0)
> set [game over v] to (0)
> +set [lives v] to (3)
> ```

> [!TASK]
>
> Click on the **Ranger** sprite. When the ranger catches Neil, Neil should lose a life.
>
> At the bottom of the `if ... then`{:class="block3control"} block, below the movement code, add an `if ... then`{:class="block3control"} block that checks if the ranger is `touching Neil`{:class="block3sensing"}. If they are, `change lives by`{:class="block3variables"} `-1` and send the ranger back to their starting position.
>
> ```blocks3
> when green flag clicked
> forever
> if <(game over) = (0)> then
> if <(neil x) > (x position)> then
> change x by (2)
> else
> change x by (-2)
> end
> if <(neil y) > (y position)> then
> change y by (2)
> else
> change y by (-2)
> end
> +if <touching (Neil v)?> then
> change [lives v] by (-1)
> go to x: (-200) y: (140)
> end
> end
> end
> ```

> [!TASK]
>
> Now tell the rest of the game that Neil has been caught. Make a new `broadcast`{:class="block3events"} message called `got ya`, and add a `broadcast and wait`{:class="block3events"} block inside your new `if ... then`{:class="block3control"} block.
>
> ```blocks3
> if <touching (Neil v)?> then
> change [lives v] by (-1)
> go to x: (-200) y: (140)
> +broadcast (got ya v) and wait
> end
> ```

> [!TASK]
>
> Click on the **Neil** sprite. Neil needs to react when he's caught.
>
> Add a `when I receive`{:class="block3events"} block for the `got ya`{:class="block3events"} message. Send Neil back to his starting position, then use a `say () for () seconds`{:class="block3looks"} to make him say `Hey!`.
>
> ```blocks3
> when I receive (got ya v)
> go to x: (0) y: (-40)
> say [Hey!] for (0.6) seconds
> ```

Click on the green flag and let the ranger catch Neil. Neil says "Hey!", pops back to the start, and loses a life.
