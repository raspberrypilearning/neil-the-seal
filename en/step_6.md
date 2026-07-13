## Chasing Neil

In this step, you'll add a ranger who chases Neil around the town.

> [!TASK]
>
> Click on the **Ranger** sprite.
>
> Add a `when green flag clicked`{:class="block3events"} block. Use a `go to x: y:`{:class="block3motion"} block to place the ranger in the corner, and a `show`{:class="block3looks"} block to make sure they're visible.
>
> ```blocks3
> when green flag clicked
> go to x: (-200) y: (140)
> show
> ```

> [!TASK]
>
> The ranger should only chase Neil while the game is being played. Use a `forever`{:class="block3control"} loop with an `if ... then`{:class="block3control"} block that checks `game over`{:class="block3variables"} is `0`.
>
> ```blocks3
> when green flag clicked
> forever
> if <(game over) = (0)> then
> end
> end
> ```

> [!TASK]
>
> For the ranger to chase Neil, they need to know where Neil is.
>
> Click on the **Neil** sprite and make two new `variables`{:class="block3variables"}, `neil x` and `neil y`. Choose **For all sprites** so the ranger can read them too.
>
> Untick both checkboxes to hide these from the player.

> [!TASK]
>
> Still on the **Neil** sprite, find his movement script. At the bottom of the movement code, inside the `if ... then`{:class="block3control"} block, set `neil x`{:class="block3variables"} and `neil y`{:class="block3variables"} to his current position.
>
> ```blocks3
> when green flag clicked
> forever
> if <(game over) = (0)> then
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
> +set [neil x v] to (x position)
> +set [neil y v] to (y position)
> end
> end
> ```

> [!TASK]
>
> Go back to the **Ranger** sprite. Inside the `if ... then`{:class="block3control"} block, make the ranger move towards Neil's x position.
>
> Use an `if ... then ... else`{:class="block3control"} block: if `neil x`{:class="block3variables"} is greater than the ranger's `x position`{:class="block3motion"}, `change x by`{:class="block3motion"} to move right, otherwise move left.
>
> ```blocks3
> when green flag clicked
> forever
> if <(game over) = (0)> then
> +if <(neil x) > (x position)> then
> change x by (2)
> else
> change x by (-2)
> end
> end
> end
> ```

> [!TASK]
>
> Now do the same for Neil's y position, so the ranger follows Neil up and down as well.
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
> +if <(neil y) > (y position)> then
> change y by (2)
> else
> change y by (-2)
> end
> end
> end
> ```

Click on the green flag. The ranger now chases Neil wherever he waddles.
