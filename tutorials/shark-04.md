# Projectile Effects

## Introduction @unplugged

Now that you have enemies and projectiles, let's give your projectiles some power!

![Projectiles](/static/recipes/shark-splash/03-projectiles.gif)

## Detect sprite overlaps

From ``||sprites:Sprites||``, drag the ``||sprites:on||`` ``||variables:sprite||`` ``||sprites:overlaps||``  ``||variables:otherSprite||`` block into your workspace. Click the first dropdown and select ``||sprites:Projectile||``, then click the second dropdown and select ``||sprites:Enemy||``.

```blocks
sprites.onOverlap(SpriteKind.Projectile, SpriteKind.Enemy, function (sprite, otherSprite) {
})
```

## Destroy the enemy

From ``||sprites:Sprites||``, drag the ``||sprites:destroy||`` block into your ``||sprites:on sprite overlaps||`` blocks. Drag the ``||variables:otherSprite||`` variable into the ``||sprites:destroy sprite||``.

```blocks
sprites.onOverlap(SpriteKind.Projectile, SpriteKind.Enemy, function (sprite, otherSprite) {
    // @highlight
    otherSprite.destroy()
})
```

## Add score

From ``||info:Info||``, drag the ``||info:change score||`` block into ``||sprites:on sprite overlaps||`` to give yourself a point each time you hit an enemy.

```blocks
sprites.onOverlap(SpriteKind.Projectile, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
    // @highlight
    info.changeScoreBy(1)
})
```

## Spawn projectiles

From ``||sprites:Sprites||``, drag the ``||sprites:mySprite start effect||`` block into ``||sprites:on sprite overlaps||``. Then drag the ``||variables:sprite||`` variable into the ``||sprites:start effect||`` block. Click the dropdown to select your favorite effect!


```blocks
sprites.onOverlap(SpriteKind.Projectile, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
    info.changeScoreBy(1)
    // @highlight
    sprite.startEffect(effects.bubbles)
})
```

## Conclusion @unplugged

Now try making your enemies move or spawn multiple kinds of enemies!

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