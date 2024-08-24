# A short explanation on how finding the direction of curve works
![Talfaizan certified](https://github.com/user-attachments/assets/664a4342-3b6e-48b9-b7d1-f66b336f5be8)

I'm kinda bored and most devs in the community don't know how this works so I wrote this tutorial, it's my first so don't expect it to be amazing quality but I hope it teachers you something

## #1 The formula
Most MPS games rearrange the **dot product** formula to find the angle between the ball and the character's centre. The angle is found to check whether the player is far enough to the sides of the ball to curve the ball or not. Below is the formula:

![dot equation](https://github.com/user-attachments/assets/8280682c-0a53-4b76-a763-9ed4fd80c11a)

As you can see, the formula uses the cosine of the angle to find the dot product, meaning we can re-arrange the formula to find the angle quite easily;
Firstly divide the dot product by the magnitudes of a and b
![dot rearranged 1](https://github.com/user-attachments/assets/b495e90f-95a2-44ee-b465-dcc6926ed13e)

Then to find theta, we do arccos to the left side of the equation
![dot rearranged 2](https://github.com/user-attachments/assets/143956c8-8025-43a5-9651-0db3d1845db4)

And now we have the angle, yipee!

## #2 Applying it onto ROBLOX
This is also quite simple. Firstly, we put the ball's position vector onto the level of the player's torso to prevent the angle being affected if the ball is lower / higher than the torso.

![vsc 1](https://github.com/user-attachments/assets/0c982389-ce30-4597-ac23-9e949c9d1752)

And then we just copy over our formula onto our script and just like that, we have the angle between the torso and the ball
![vsc 2](https://github.com/user-attachments/assets/261242ed-2ab5-40b4-8a08-88e97d164dbb)


You may be asking, why do we not multiply the magnitude of the Torso's lookvector with the direction from the torso to the ball? The reason is because there is no point. The base lookvector's magnitude is 1 and multiplying anything by 1 will give you the same result, so there's just no point and it's cleaner to just leave it as it is.

Also, ROBLOX returns trigonometric functions in radians, so we have to manually convert it to degrees (to visualise tje angle better)

## #3 Finding the closest foot
Firstly, we need to check if the player is to the sides just enough for them to be able to curl. [In the game I chose to look at ](https://www.roblox.com/games/8126978770/MPS-5-A-Side-DISCONTINUED), it was 18 degrees.
After that, we need to compare the distance between the arms and the ball. We use the arms instead of the legs because if we use the legs, then the leg that you hit the ball with will always be closer than the other side's leg so the arm's are a more reliable alternative.
Just find the arm with the smallest distance and then curve it depending on which arm it was.
![vsc 3](https://github.com/user-attachments/assets/df3b63e0-1c9c-4995-8c49-d52b0ad10fb5)

After that, you can add whatever forces you want to the ball to make it curl..


## #4 Conclusion
This was my first tutorial and I hope you learnt something from this, I made it as simple as possible so anyone can understand it soooo yeah
