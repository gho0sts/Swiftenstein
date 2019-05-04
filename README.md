[![Swift 4.2](https://img.shields.io/badge/swift-4.2-red.svg?style=flat)](https://developer.apple.com/swift)
[![License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://opensource.org/licenses/MIT)
[![Twitter](https://img.shields.io/badge/twitter-@nicklockwood-blue.svg)](http://twitter.com/nicklockwood)

![Screenshot](Screenshot.png)

# Mein Leben!

Swiftenstein is a partial reimplementation of ID Software's 1991 classic FPS [Wolfenstein 3D](https://en.wikipedia.org/wiki/Wolfenstein_3D) in Swift for iOS. It is not a complete game, just a single-level tech demo.

It's also not a completely faithful recreation of the original game engine - I've deliberately removed some features and added others that weren't in the original, but it should be close enough for nostalgia purposes.

For copyright reasons, I've redrawn (badly) the Wolfenstein wall textures and sprites, but if you would prefer to use [Adrian Carmack](https://en.wikipedia.org/wiki/Adrian_Carmack)'s original graphics, a web search for ["Wolfenstein sprites"](https://duckduckgo.com/?q=wolfenstein+sprites&t=osx&iar=images&iax=images&ia=images) should provide a good starting point.

This code is not particularly polished or well-structured. I wrote it as a learning exercise and am releasing it for educational purposes. I may improve it in future, or I may not. If you feel like improving it yourself, please open a PR.

## How to Play

The game can be played one-handed in either portrait or landscape orientation. The entire screen acts as a virtual thumbstick for turning left/right and moving forwards/backwards (there's no strafing support as yet). Tap anywhere to fire.

If you have a phone with 3D Touch support you can force-touch to autofire. Otherwise you'll need to tap repeatedly.

Enemies are placed randomly, so if you're unlucky you may be shot in the back immediately when the game starts. You have limited health and ammo, but if you turn right at the start you'll see a submachine gun that should help your chances of survival.

There's no way to complete the level currently. Just shoot all the guards and try not to get killed.

There are a couple of secret sliding pushwalls somewhere - see if you can find them. If you've killed all the guards and you want to restart the level, you can use a pushwall to crush yourself to death.

## How it Works

In 1991 there were no 3D graphics cards, and no standard 3D graphics APIs like OpenGL or DirectX. Wolfenstein's engine had to draw every pixel to the screen manually using a technique called *ray casting*.

Swiftenstein replicates this technique. All drawing is done by manipulating an array of ARGB pixel values, which is then finally turned into a `UIImage` and displayed in a `UIImageView`.

On a modern system, this is *absolutely not* the right way to make a game. From a performance and battery-life point of view, this is a terrible way to put pixels on the screen. But it's a pretty fun technique all the same, and easily portable to just about any programming environment.

If you want to learn more about ray casting, I recommend Fabian Sanglard's excellent [Wolfenstein 3D Game Engine Black Book](https://www.amazon.co.uk/gp/product/1727646703/ref=as_li_tl?ie=UTF8&camp=1634&creative=6738&creativeASIN=1727646703&linkCode=as2&tag=charcoaldesig-21&linkId=aab5d43499c96f7417b7aa0a7b3e587d) and also Lode Vandevenne's amazing [Raycasting tutorial series](https://lodev.org/cgtutor/raycasting.html).
