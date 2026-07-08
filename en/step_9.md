## Give Neil a voice

At the moment, the player can just hold down the space bar to smash everything at once. In this step, you'll add a short delay — and give Neil something to say each time he smashes.

> [!TASK]
>
> Make a new list called `neil's words`{:class="block3variables"}, and choose **For all sprites**.
>
> Untick its checkbox to hide the list from the player.
>
> Using the list on the Stage, click the `+` to add a few things for Neil to shout when he smashes something. You can add as many as you like, and they can be anything you want!

> [!TASK]
>
> Click on the `Neil`{:class="block3looks"} sprite and find his movement script.
>
> With the rest of the movement code, inside the `if then`{:class="block3control"} block, add another `if then`{:class="block3control"} block that checks for the `space`{:class="block3sensing"} key. When it's pressed, `say () for () seconds`{:class="block3looks"} a random item from your list, then `wait () seconds`{:class="block3control"} for `0.1` seconds.
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
> +if <key (space v) pressed?> then
> say (item (pick random (1) to (length of [neil's words v])) of [neil's words v]) for (0.1) seconds
> wait (0.1) seconds
> end
> set [neil x v] to (x position)
> set [neil y v] to (y position)
> end
> end
> ```

Using `length of ()`{:class="block3variables"} means Neil will always pick from however many things you added to the list.

Click the green flag and smash away. Neil shouts something each time, and holding down the space bar no longer clears the whole town in an instant.
