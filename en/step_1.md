## Make Neil move

In this step, you'll get Neil the seal moving around the town using the arrow keys.

> [!TASK]
>
> Open the [Neil the Seal starter project](https://scratch.mit.edu/projects/1352072422/editor).
>
> The starter project has all the sprites and backdrops you need.

Click on the `Neil`{:class="block3looks"} sprite so you can add your code to it.

> [!TASK]
>
> First, make sure Neil always starts in the same place. Add a `when green flag clicked`{:class="block3events"} block, then send Neil to the middle of the road with a `go to x: () y: ()`{:class="block3motion"} block, `point in direction ()`{:class="block3motion"} so he faces right, and `show`{:class="block3looks"} him.
>
> ```blocks3
> when green flag clicked
> go to x: (0) y: (-40)
> point in direction (90)
> show
> ```

> [!TASK]
>
> Add another `when green flag clicked`{:class="block3events"} block, then add a `forever`{:class="block3control"} loop.
>
> Inside the loop, add an `if then`{:class="block3control"} block that checks whether the `up arrow`{:class="block3sensing"} key is pressed. When it is, make Neil move up by adding a `change y by ()`{:class="block3motion"} block.
>
> ```blocks3
> when green flag clicked
> forever
> if <key (up arrow v) pressed?> then
> change y by (5)
> end
> end
> ```

Click the green flag and press the up arrow. Neil should move up the screen.

Now you can add movement for the other three arrow keys.

> [!TASK]
>
> Add another `if then`{:class="block3control"} block inside the `forever`{:class="block3control"} loop, below the first one. This time, check for the `down arrow`{:class="block3sensing"} key and move Neil down.
>
> ```blocks3
> if <key (down arrow v) pressed?> then
> change y by (-5)
> end
> ```

Moving up and down changes Neil's `y` position. To move him left and right, you need to change his `x` position instead.

> [!TASK]
>
> Add two more `if then`{:class="block3control"} blocks to check for the `left arrow`{:class="block3sensing"} and `right arrow`{:class="block3sensing"} keys, using `change x by ()`{:class="block3motion"} to move Neil.
>
> ```blocks3
> if <key (left arrow v) pressed?> then
> change x by (-5)
> end
> if <key (right arrow v) pressed?> then
> change x by (5)
> end
> ```

Click the green flag and try all four arrow keys. Neil moves around, but he always faces the same way. You can make him face left and right as he walks.

> [!TASK]
>
> Add a `point in direction ()`{:class="block3motion"} block inside the `left arrow`{:class="block3sensing"} and `right arrow`{:class="block3sensing"} `if then`{:class="block3control"} blocks. Point Neil in direction `-90` to face left, and `90` to face right.
>
> ```blocks3
> if <key (left arrow v) pressed?> then
> change x by (-5)
> +point in direction (-90)
> end
> if <key (right arrow v) pressed?> then
> change x by (5)
> +point in direction (90)
> end
> ```

Right now Neil slides around without moving his body. You can bring him to life by giving him more than one costume and switching between them as he walks.

> [!TASK]
>
> Click the `Costumes`{:class="block3looks"} tab. Neil has one costume, called `seal1`.
>
> Right-click on `seal1` and choose **duplicate**. This makes a copy called `seal2`.
>
> In the paint editor, click on one of Neil's legs to select it and move it a little. Do the same to his other leg, so `seal2` has the legs in a different position to `seal1`.

Here is how the two costumes look in the example project. It's up to you how you move the legs — the more different your two costumes are, the more Neil will look like he's moving.

![Neil's seal1 and seal2 costumes side by side, with the legs in different positions](images/neil-costumes-first.png)

> [!TASK]
>
> Go back to the `Code`{:class="block3control"} tab. Add a `next costume`{:class="block3looks"} block inside each of your four arrow-key `if then`{:class="block3control"} blocks, so Neil changes costume whenever he moves.
>
> ```blocks3
> if <key (up arrow v) pressed?> then
> change y by (5)
> +next costume
> end
> ```

Click the green flag and move Neil around. His two costumes swap back and forth, so he looks like he's waddling along.

Two costumes give Neil a simple wobble. Adding a few more makes his movement much smoother.

> [!TASK]
>
> Duplicate one of your costumes to make `seal3`, then move the legs again to make a new pose. Keep going until Neil has five costumes, each with the legs in a slightly different position.

In the example project, Neil has five costumes that move his legs up and down as he waddles. Yours can be as different as you like.

![Neil's five costumes side by side, with the legs in slightly different positions in each one](images/neil-costumes-all.png)

Now the `next costume`{:class="block3looks"} block cycles through all five poses, giving Neil a smooth waddle as he explores the town.

> [!NOPRINT]
>
> This is how Neil looks as he waddles around the town:
>
> ![Animated image of Neil the seal waddling as his costumes change](images/neil-walking.gif)
