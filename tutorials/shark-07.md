# Make enemies damage the player

## Introduction @unplugged

Use the ``||info:change life by -1||`` block to damage the player when they overlap an enemy!

![Enemy Damage](/static/recipes/shark-splash/02-C-enemies.gif)

## Step 1

Place a ``||info:set life to 3||`` block inside the ``||loops:on start||`` event in your workspace.

```blocks
info.setLife(3)
```

## Step 2

Drag an ``||sprites:on overlaps||`` block into the workspace. Change the second kind to ``||sprites:Enemy||`` in the dropdown. If you already have a ``||sprites:on overlaps||`` block in your workspace for the ``||sprites:Player||`` and ``||sprites:Enemy||`` sprites, use that instead.

```blocks
info.setLife(3)
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
})
```

## Step 3

Place a ``||sprites:destroy sprite||`` block inside the ``||sprites:on overlaps||`` event. Drag the
``||variables:otherSprite||`` variable from the ``||sprites:on overlaps||`` block and place it inside
the ``||sprites:destroy sprite||``. You can skip this step if ``||variables:otherSprite||`` is already
destroyed in this event.

```blocks
info.setLife(3)
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
})
```

## Step 4

Place a ``||info:change life by -1||`` block inside the ``||sprites:on overlaps||`` event.

```blocks
info.setLife(3)
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
    info.changeLifeBy(-1)
})
```

## Step 5

Place a ``||scene:camera shake||`` block inside the ``||sprites:on overlaps||`` event. This
lets the player know that they have been hit.

```blocks
info.setLife(3)
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
    info.changeLifeBy(-1)
    scene.cameraShake(4, 500)
})
```

## Conclusion @unplugged


Now let's add code to destroy the enemies with your projectiles! Or, if you're feeling creative, add a background to set the scene.


```template
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    // @highlight
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

let enemySprite: Sprite = null
game.onUpdateInterval(500, function () {
    enemySprite = sprites.create(img`
        . . . . . . . . . . . c c . . .
        . . . . . . . c c c c 6 3 c . .
        . . . . . . c 6 3 3 3 3 6 c . .
        . . c c . c 6 c c 3 3 3 3 3 c .
        . b 5 5 c 6 c 5 5 c 3 3 3 3 3 c
        . f f 5 c 6 c 5 f f 3 3 3 3 3 c
        . f f 5 c 6 c 5 f f 6 3 3 3 c c
        . b 5 5 3 c 3 5 5 c 6 6 6 6 c c
        . . b 5 5 3 5 5 c 3 3 3 3 3 3 c
        . c c 5 5 5 5 5 b c c 3 3 3 3 c
        c 5 5 4 5 5 5 4 b 5 5 c 3 3 c .
        b 5 4 b 4 4 4 4 b b 5 c b b . .
        c 4 5 5 b 4 b 5 5 5 4 c 4 5 b .
        c 5 5 5 c 4 c 5 5 5 c 4 c 5 c .
        c 5 5 5 5 c 5 5 5 5 c 4 c 5 c .
        . c c c c c c c c c . . c c c .
    `, SpriteKind.Enemy)
    enemySprite.setPosition(randint(0, 160), randint(0, 120))
})


sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    // @highlight
    otherSprite.destroy()
})
```