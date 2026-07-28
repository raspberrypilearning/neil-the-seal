## Add stuff to smash

In this step, you'll fill the town with stop signs for Neil to smash.

> [!TASK]
>
> Click on the **Sign** sprite.
>
> Add a `when green flag clicked`{:class="block3events"} block, then a `show`{:class="block3looks"} block, because the sign starts off hidden. Then use a `repeat`{:class="block3control"} loop to move to six random spots, making a clone at each one.
>
> ```blocks3
> when green flag clicked
> show
> repeat (6)
> go to x: (pick random (-220) to (220)) y: (pick random (-100) to (130))
> create clone of (myself v)
> end
> ```

Click on the green flag. Six stop signs appear around the town — but you can still see the original sign that the clones are made from.

> [!TASK]
>
> Add a `hide`{:class="block3looks"} block to the end of the script, so the original sign is hidden once all the clones have been made.
>
> ```blocks3
> when green flag clicked
> show
> repeat (6)
> go to x: (pick random (-220) to (220)) y: (pick random (-100) to (130))
> create clone of (myself v)
> end
> +hide
> ```

Now only the six clones are visible.

> [!TASK]
>
> Start a new script with a `when I start as a clone`{:class="block3control"} block. Add a `forever`{:class="block3control"} loop, and inside it use an `if ... then`{:class="block3control"} block to check whether the clone is `touching Neil`{:class="block3sensing"}. If it is, `delete this clone`{:class="block3control"}.
>
> ```blocks3
> when I start as a clone
> forever
> if <touching (Neil v)?> then
> delete this clone
> end
> end
> ```

Move Neil into a sign and it disappears.

> [!TASK]
>
> Right now, the signs vanish the moment Neil touches them. To make Neil **smash** them, the player should have to press the space bar too.
>
> Change the `if ... then`{:class="block3control"} condition so it also checks whether the `space`{:class="block3sensing"} key is pressed, using an `and`{:class="block3operators"} block to join the two checks.
>
> ```blocks3
> when I start as a clone
> forever
> +if <<touching (Neil v)?> and <key (space v) pressed?>> then
> delete this clone
> end
> end
> ```

Now when Neil bumps into a sign, the player has to press the space bar to smash it.
