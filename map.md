# branching
* name: Shark Splash
* description: Design a shooter game! We'll start by creating a hero that shoots projectiles, then you can customize the game with enemies, or a detailed setting.
* backgroundurl: https://raw.githubusercontent.com/riknoll/skillmap-branch/master/images/shark-attack-bg.png
* primarycolor: #ff93c4
* secondarycolor: #87f2ff
* tertiarycolor: #5c406c
* strokecolor: #5c406c

## shark
* name: Shark Splash

### shark-character
* name: Create Your Hero
* type: tutorial
* description: Create a main character that shoots some projectiles
* url: /recipes/shark-splash/01-character
* tags: easy, sprites, projectiles
* imageUrl: /static/recipes/shark-splash/01-character.gif
* next: shark-enemies

### shark-enemies
* name: Add Enemies
* type: tutorial
* description: An enemy appears! Fight!
* url: /recipes/shark-splash/02-enemies
* tags: easy, enemies
* imageUrl: /static/recipes/shark-splash/02-enemies.gif
* next: shark-projectile, shark-background

### shark-background
* name: Design a Background
* type: tutorial
* description: Draw a world for your hero to explore
* url: /recipes/shark-splash/04-background
* tags: easy, design, background
* imageUrl: /static/recipes/shark-splash/04-background.png
* next: shark-projectile

### shark-projectile
* name: Projectile Effects
* type: tutorial
* description: Let's give those projectiles some power!
* url: /recipes/shark-splash/03-projectiles
* tags: easy, projectiles, enemies
* imageUrl: /static/recipes/shark-splash/03-projectiles.gif
* next: shark-enemies-moving, shark-enemies-multiple, shark-finish

### shark-enemies-moving
* name: Moving Enemies
* type: tutorial
* description: Uh-oh, these enemies are on the go. Learn how to code enemy movement!
* url: /recipes/shark-splash/02-A-enemies
* tags: easy, enemies, movement
* imageUrl: /static/recipes/shark-splash/02-A-enemies.gif
* next: shark-finish

### shark-enemies-multiple
* name: Multiple Enemies
* type: tutorial
* description: Add variety to your game with different types of enemies.
* url: /recipes/shark-splash/02-B-enemies
* tags: easy, enemies, kinds
* imageUrl: /static/recipes/shark-splash/02-B-enemies.gif
* next: shark-finish

### shark-finish
* kind: completion
* type: certificate
* url: https://microsoft.github.io/pxt-skillmap-sample/certificates/design-a-space-explorer.pdf