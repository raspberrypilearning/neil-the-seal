## Winning

In this step, you'll let the player win by smashing everything in town.

> [!TASK]
>
> Click on the `Stage`, then click the `Backdrops`{:class="block3looks"} tab.
>
> Add a new backdrop called `Win`. Give it a background and some text to celebrate finishing the game — you can write whatever you like.

Here's the `Win` backdrop from the example project:

![The Win backdrop from the example project, a green screen reading TOWN DEMOLISHED!](images/win-backdrop.png)

> [!TASK]
>
> Make a new variable called `game over`{:class="block3variables"}, and choose **For all sprites**.
>
> This one is just for the code to use, so untick its checkbox to hide it from the player.
>
> On the Stage, add it to your `when green flag clicked`{:class="block3events"} script and set it to `0` at the start.
>
> ```blocks3
> when green flag clicked
> set [score v] to (0)
> set [stuff to smash v] to (0)
> +set [game over v] to (0)
> ```

> [!TASK]
>
> The player wins when there's nothing left to smash. On the Stage, add a new script to check for this.
>
> Use a `forever`{:class="block3control"} loop with an `if then`{:class="block3control"} block. When `stuff to smash`{:class="block3variables"} is less than `1` and `game over`{:class="block3variables"} is `0`, switch to your `Win` backdrop and set `game over`{:class="block3variables"} to `1`.
>
> ```blocks3
> when green flag clicked
> forever
> if <<(stuff to smash) < (1)> and <(game over) = (0)>> then
> switch backdrop to (Win v)
> set [game over v] to (1)
> end
> end
> ```

> [!TASK]
>
> When the game starts, it should always begin on the `Town` backdrop. Add a `switch backdrop to ()`{:class="block3looks"} block to the top of your setup script.
>
> ```blocks3
> when green flag clicked
> +switch backdrop to (Town v)
> set [score v] to (0)
> set [stuff to smash v] to (0)
> set [game over v] to (0)
> ```

> [!TASK]
>
> When the game is over, Neil should stop moving. Click on the `Neil`{:class="block3looks"} sprite and wrap all of his movement code in an `if then`{:class="block3control"} block that only runs while `game over`{:class="block3variables"} is `0`.
>
> ```blocks3
> when green flag clicked
> forever
> +if <(game over) = (0)> then
> if <key (up arrow v) pressed?> then
> change y by (5)
> next costume
> end
> if <key (down arrow v) pressed?> then
> change y by (-5)
> next costume
> end
> if <key (left arrow v) pressed?> then
> change x by (-5)
> point in direction (-90)
> next costume
> end
> if <key (right arrow v) pressed?> then
> change x by (5)
> point in direction (90)
> next costume
> end
> end
> end
> ```

Click the green flag and smash everything in town. When the last object is gone, your `Win` backdrop appears — and Neil stops moving.
