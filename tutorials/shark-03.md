# Design a Background

## Introduction @unplugged

Let's build a world for your hero to walk around in!

![Background](/static/recipes/shark-splash/04-background.png)

## Add a background

From ``||scene:Scene||``, drag the the ``||scene:set background image||`` block into ``||loops:on start||``. Click on the gray square to open the image editor and draw a background for your game.

```blocks
scene.setBackgroundImage(img`.`)
```

## Decorative sprites

Next, let's add some sprites to decorate your game. From ``||loops:Loops||``, drag the ``||loops:for index from||`` block into ``||loops:on start|`` and set the ``||variables:index||`` range to `10`.

```blocks
scene.setBackgroundImage(img`.`)
for (let index = 0; index <= 10; index++) {
}
```

## Add background sprite

 From ``||sprites:Sprites||``, drag the ``||variables:set mySprite to||`` block into ``||loops:for index from 0 to 10|``. Click on the grey box and in the image editor gallery, select a background object like a rock or some seaweed.

```blocks
scene.setBackgroundImage(img`.`)
for (let index = 0; index <= 10; index++) {
    let mySprite = sprites.create(img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . 8 8 8 . . . .
        . . . . . . . 8 8 6 6 8 . . . .
        . . . . . . 8 6 6 8 8 . . . . .
        . . . . . 8 7 6 8 . . . . . . .
        . . . . 8 7 7 8 . . . . . . . .
        . . . . 8 7 7 8 . . . . . . . .
        . . . 8 7 7 8 . . . . . . . . .
        . . . 8 5 7 8 . . . . . . . . .
        . . . 8 5 5 8 . . . . . . . . .
        . . . 8 7 5 8 . . . . . . 8 8 .
        . . . 8 7 6 7 8 . . . . 8 7 8 .
        . . . 8 7 6 7 8 . . . 8 7 8 . .
        . . . . 8 7 6 7 8 . 8 7 6 8 . .
        . . . . 8 7 6 7 6 8 6 7 8 . . .
        . . . . . 8 7 6 6 8 7 7 8 . . .
        . . . . . . 8 6 6 8 7 6 6 . . .
        . . . . . . . 8 6 8 7 6 7 8 . .
        . . . . . . . . 8 6 6 7 6 7 8 .
        . . . . . . . . 8 6 8 5 7 5 6 .
        . . . . 8 8 . . 8 6 6 6 5 7 5 6
        . . . 8 6 8 . . 8 6 6 8 5 6 5 6
        . . 8 6 6 8 . . 8 6 6 8 7 6 7 8
        . 8 6 6 8 . . 8 6 8 6 8 7 6 7 8
        . 8 6 8 . . 8 6 8 8 6 6 7 6 7 8
        8 7 6 8 . 8 8 8 8 6 8 7 6 7 7 8
        8 7 6 8 . 8 8 8 8 8 7 7 6 7 8 .
        8 7 6 6 8 8 8 8 8 6 7 6 7 7 8 .
        8 7 6 7 6 8 8 8 6 6 8 7 7 8 . .
        . 8 7 6 7 7 6 8 6 8 6 6 8 . . .
        . 8 7 7 6 6 7 7 8 8 6 8 . . . .
        . . 8 7 7 6 6 7 6 8 8 . . . . .
        . . . 8 6 7 6 7 7 8 8 . . . . .
    `, SpriteKind.Food)
}
```

## Update sprite y-position

From ``||sprites:Sprites||``, drag the ``||sprites:set mySprite position||`` block into ``||loops:for index from 0 to 10||`` loop. Change the ``||sprites:y||`` value to `96`.


```blocks
scene.setBackgroundImage(img`.`)
for (let index = 0; index <= 10; index++) {
    let mySprite = sprites.create(img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . 8 8 8 . . . .
        . . . . . . . 8 8 6 6 8 . . . .
        . . . . . . 8 6 6 8 8 . . . . .
        . . . . . 8 7 6 8 . . . . . . .
        . . . . 8 7 7 8 . . . . . . . .
        . . . . 8 7 7 8 . . . . . . . .
        . . . 8 7 7 8 . . . . . . . . .
        . . . 8 5 7 8 . . . . . . . . .
        . . . 8 5 5 8 . . . . . . . . .
        . . . 8 7 5 8 . . . . . . 8 8 .
        . . . 8 7 6 7 8 . . . . 8 7 8 .
        . . . 8 7 6 7 8 . . . 8 7 8 . .
        . . . . 8 7 6 7 8 . 8 7 6 8 . .
        . . . . 8 7 6 7 6 8 6 7 8 . . .
        . . . . . 8 7 6 6 8 7 7 8 . . .
        . . . . . . 8 6 6 8 7 6 6 . . .
        . . . . . . . 8 6 8 7 6 7 8 . .
        . . . . . . . . 8 6 6 7 6 7 8 .
        . . . . . . . . 8 6 8 5 7 5 6 .
        . . . . 8 8 . . 8 6 6 6 5 7 5 6
        . . . 8 6 8 . . 8 6 6 8 5 6 5 6
        . . 8 6 6 8 . . 8 6 6 8 7 6 7 8
        . 8 6 6 8 . . 8 6 8 6 8 7 6 7 8
        . 8 6 8 . . 8 6 8 8 6 6 7 6 7 8
        8 7 6 8 . 8 8 8 8 6 8 7 6 7 7 8
        8 7 6 8 . 8 8 8 8 8 7 7 6 7 8 .
        8 7 6 6 8 8 8 8 8 6 7 6 7 7 8 .
        8 7 6 7 6 8 8 8 6 6 8 7 7 8 . .
        . 8 7 6 7 7 6 8 6 8 6 6 8 . . .
        . 8 7 7 6 6 7 7 8 8 6 8 . . . .
        . . 8 7 7 6 6 7 6 8 8 . . . . .
        . . . 8 6 7 6 7 7 8 8 . . . . .
    `, SpriteKind.Food)
    mySprite.setPosition(0, 96)
}

```

## Update sprite x-position

From ``||math:Math||``, drag the ``||math:0 x 0||`` block in as the ``||sprites:x||`` value of ``||sprites:set mySprite position||``. Change the first number to `16`, and drag the ``||variables:index||`` block for the second number. Continue adding decorations until you are satisifed with your scene!

```blocks
scene.setBackgroundImage(img`.`)
for (let index = 0; index <= 10; index++) {
    let mySprite = sprites.create(img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . 8 8 8 . . . .
        . . . . . . . 8 8 6 6 8 . . . .
        . . . . . . 8 6 6 8 8 . . . . .
        . . . . . 8 7 6 8 . . . . . . .
        . . . . 8 7 7 8 . . . . . . . .
        . . . . 8 7 7 8 . . . . . . . .
        . . . 8 7 7 8 . . . . . . . . .
        . . . 8 5 7 8 . . . . . . . . .
        . . . 8 5 5 8 . . . . . . . . .
        . . . 8 7 5 8 . . . . . . 8 8 .
        . . . 8 7 6 7 8 . . . . 8 7 8 .
        . . . 8 7 6 7 8 . . . 8 7 8 . .
        . . . . 8 7 6 7 8 . 8 7 6 8 . .
        . . . . 8 7 6 7 6 8 6 7 8 . . .
        . . . . . 8 7 6 6 8 7 7 8 . . .
        . . . . . . 8 6 6 8 7 6 6 . . .
        . . . . . . . 8 6 8 7 6 7 8 . .
        . . . . . . . . 8 6 6 7 6 7 8 .
        . . . . . . . . 8 6 8 5 7 5 6 .
        . . . . 8 8 . . 8 6 6 6 5 7 5 6
        . . . 8 6 8 . . 8 6 6 8 5 6 5 6
        . . 8 6 6 8 . . 8 6 6 8 7 6 7 8
        . 8 6 6 8 . . 8 6 8 6 8 7 6 7 8
        . 8 6 8 . . 8 6 8 8 6 6 7 6 7 8
        8 7 6 8 . 8 8 8 8 6 8 7 6 7 7 8
        8 7 6 8 . 8 8 8 8 8 7 7 6 7 8 .
        8 7 6 6 8 8 8 8 8 6 7 6 7 7 8 .
        8 7 6 7 6 8 8 8 6 6 8 7 7 8 . .
        . 8 7 6 7 7 6 8 6 8 6 6 8 . . .
        . 8 7 7 6 6 7 7 8 8 6 8 . . . .
        . . 8 7 7 6 6 7 6 8 8 . . . . .
        . . . 8 6 7 6 7 7 8 8 . . . . .
    `, SpriteKind.Food)
    mySprite.setPosition(16 * index, 96)
}

```


```template
scene.setBackgroundColor(8)
let mySprite = sprites.create(img`
    . . . . . . . . . . b 5 b . . .
    . . . . . . . . . b 5 b . . . .
    . . . . . . . . . b c . . . . .
    . . . . . . b b b b b b . . . .
    . . . . . b b 5 5 5 5 5 b . . .
    . . . . b b 5 d 1 f 5 5 d f . .
    . . . . b 5 5 1 f f 5 d 4 c . .
    . . . . b 5 5 d f b d d 4 4 . .
    b d d d b b d 5 5 5 4 4 4 4 4 b
    b b d 5 5 5 b 5 5 4 4 4 4 4 b .
    b d c 5 5 5 5 d 5 5 5 5 5 b . .
    c d d c d 5 5 b 5 5 5 5 5 5 b .
    c b d d c c b 5 5 5 5 5 5 5 b .
    . c d d d d d d 5 5 5 5 5 d b .
    . . c b d d d d d 5 5 5 b b . .
    . . . c c c c c c c c b b . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite)

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    let projectile = sprites.createProjectileFromSprite(img`
        . . . 6 6 6 6 6 6 . . .
        . . 6 9 9 9 9 9 9 6 . .
        . 6 1 9 9 9 9 9 9 9 6 .
        f 1 9 9 9 9 1 1 9 9 9 6
        f 1 9 9 9 9 1 1 9 9 9 6
        f 1 9 9 9 9 9 9 9 9 9 6
        f 1 9 9 9 9 9 9 1 9 9 6
        f 1 9 9 9 9 9 9 9 9 9 6
        f 1 9 9 9 9 9 9 9 9 9 6
        . f 1 9 9 9 9 9 9 1 6 .
        . . f 1 1 1 1 1 1 f . .
        . . . f f f f f f . . .
    `, mySprite, 50, 0)
})
```