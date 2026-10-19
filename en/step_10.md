## Give Neil a voice

At the moment, the player can hold down the space bar to smash several objects at once. In this step, you'll make each press smash one object, with a short pause for Neil to shout.

> [!TASK]
>
> Make a new `list`{:class="block3variables"} called `neil's words`, and choose **For all sprites**.
>
> Using the list on the Stage, click on the **+** to add a few things for Neil to shout when he smashes something. Add at least one item, and as many more as you like!
>
> Once you've added all your words, untick the list's checkbox to hide it from the player.

> [!TASK]
>
> Make a new `variable`{:class="block3variables"} called `smash ready`, and choose **For all sprites**. Untick its checkbox to hide it.
>
> A value of `1` means Neil is ready to smash; `0` means the other objects must wait.
>
> Click on the **Neil** sprite and add this new script:
>
> ```blocks3
> when green flag clicked
> set [smash ready v] to (1)
> ```

> [!TASK]
>
> Still on **Neil**, make a new `broadcast`{:class="block3events"} message called `smash` and add a receiver for it.
>
> Make Neil say a random item from your list for `0.2` seconds, then wait until the player releases the space bar before setting `smash ready`{:class="block3variables"} back to `1`.
>
> ```blocks3
> when I receive (smash v)
> say (item (pick random (1) to (length of [neil's words v])) of [neil's words v]) for (0.2) seconds
> wait until <not <key (space v) pressed?>>
> set [smash ready v] to (1)
> ```

Using `length of`{:class="block3variables"} means Neil will always pick from however many things you added to the list.

> [!TASK]
>
> Click on the **Sign** sprite. Inside the clone's `forever`{:class="block3control"} loop, add another `and`{:class="block3operators"} to the smash condition so it also checks that `smash ready`{:class="block3variables"} is `1`.
>
> Inside the `if ... then`{:class="block3control"} block, set `smash ready`{:class="block3variables"} to `0` **first**, then broadcast `smash` before changing the score and deleting the clone. Keep the game-over check too.
>
> ```blocks3
> forever
> +if <<<touching (Neil v)?> and <key (space v) pressed?>> and <(smash ready) = (1)>> then
> set [smash ready v] to (0)
> broadcast (smash v)
> change [score v] by (10)
> change [stuff to smash v] by (-1)
> delete this clone
> end
> if <(game over) = (1)> then
> delete this clone
> end
> end
> ```

> [!TIP]
>
> Every clone checks the same `smash ready`{:class="block3variables"} variable. Setting it to `0` before the broadcast makes the other clones wait, even if Neil touches several objects. Neil's receiver resets it, because a deleted clone cannot finish a waiting script.

> [!TASK]
>
> Make the same changes to the clone scripts on **Car** and **Barrier**. Keep the points you chose for each sprite.

Click on the green flag and move Neil so he touches an object. Press and hold <kbd>Space</kbd>: one object should disappear and Neil should shout once. Keep holding it while moving onto another object: that object should stay. Release <kbd>Space</kbd>, then press it again after Neil finishes speaking to smash the next object.
