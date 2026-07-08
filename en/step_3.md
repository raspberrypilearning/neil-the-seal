## Reward Neil

In this step, you'll keep score as Neil smashes things, and keep track of how much is left to smash.

> [!TASK]
>
> Click on the `Stage`.
>
> Make two new variables, `score`{:class="block3variables"} and `stuff to smash`{:class="block3variables"}, and choose **For all sprites** for each one.
>
> Add a `when green flag clicked`{:class="block3events"} block to the Stage that sets both variables to `0`.
>
> ```blocks3
> when green flag clicked
> set [score v] to (0)
> set [stuff to smash v] to (0)
> ```

> [!TASK]
>
> Click on the `Sign`{:class="block3looks"} sprite. Each sign that gets made should add one to the total amount of stuff to smash.
>
> Inside the `repeat ()`{:class="block3control"} loop, add a `change stuff to smash by ()`{:class="block3variables"} block to count each clone as it's created.
>
> ```blocks3
> when green flag clicked
> hide
> repeat (6)
> go to x: (pick random (-220) to (220)) y: (pick random (-100) to (130))
> create clone of (myself v)
> +change [stuff to smash v] by (1)
> end
> ```

> [!TASK]
>
> Now, when Neil smashes a sign, reward the player with some points and take one off the amount left to smash.
>
> In the clone script, inside the `if then`{:class="block3control"} block, add a `change score by ()`{:class="block3variables"} block to add `10` points and a `change stuff to smash by ()`{:class="block3variables"} block to take away `1`.
>
> ```blocks3
> when I start as a clone
> show
> forever
> if <<touching (Neil v)?> and <key (space v) pressed?>> then
> +change [score v] by (10)
> +change [stuff to smash v] by (-1)
> delete this clone
> end
> end
> ```

Click the green flag and smash some signs. Your score goes up, and the amount of stuff left to smash goes down.
