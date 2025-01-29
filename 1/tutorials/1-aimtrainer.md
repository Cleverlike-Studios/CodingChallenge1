# Aim Trainer.

### @explicitHints 1

### @activities true

## First Activity

### Let's Play!

Press the green Play button to try Aim Trainer!

#### ~ tutorialhint

```blocks
function resetGame () {
    player.execute(
    "clear @p bow"
    )
    player.execute(
    "clear @p arrow"
    )
    player.execute(
    "remove @e[type=arrow]"
    )
    blocks.place(DIAMOND_BLOCK, world(160, 28, 149))
}
function endGame () {
    agent.destroy(DOWN)
    gameplay.title(mobs.target(NEAREST_PLAYER), "GAME OVER", "Targets Hit: " + targetHit)
    loops.pause(3000)
}
function startGame () {
    blocks.place(LAPIS_LAZULI_BLOCK, world(160, 28, 149))
    setupGame()
    targetHit = 0
    while (timeRemaining > 0) {
        gameplay2()
    }
    if (timeRemaining == 0) {
        endGame()
        resetGame()
    }
}
function equipPlayer () {
    mobs.give(
    mobs.target(NEAREST_PLAYER),
    BOW,
    1
    )
    mobs.give(
    mobs.target(NEAREST_PLAYER),
    ARROW,
    128
    )
}
function setupGame () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(NEAREST_PLAYER)
    )
    timeRemaining = 600
    worldLocations = [
    world(167, 40, 151),
    world(167, 47, 151),
    world(159, 43, 151),
    world(151, 40, 151),
    world(151, 47, 151)
    ]
    countDown()
    buildTarget()
    equipPlayer()
}
function buildTarget () {
    agent.teleport(worldLocations._pickRandom(), NORTH)
    agent.setItem(TARGET, 1, 1)
    agent.setSlot(1)
    agent.place(DOWN)
}
function gameplay2 () {
    timeRemaining += -1
    if (agent.detect(AgentDetection.Redstone, DOWN)) {
        player.execute(
        "remove @e[type=arrow]"
        )
        agent.destroy(DOWN)
        player.execute(
        "playsound random.orb @a"
        )
        // This adds 1 to the score every time a Target is Hit
        targetHit += 1
        if (timeRemaining > 0) {
            buildTarget()
        }
    }
}
function countDown () {
    player.say("You have 30 seconds to hit as many targets as possible")
    loops.pause(3000)
    player.say("3...")
    player.execute(
    "playsound random.orb @a"
    )
    loops.pause(500)
    player.say("2...")
    player.execute(
    "playsound random.orb @a"
    )
    loops.pause(500)
    player.say("1...")
    player.execute(
    "playsound random.orb @a"
    )
    loops.pause(500)
    player.say("GO!!!")
    player.execute(
    "playsound random.orb @a"
    )
}
let worldLocations: Position[] = []
let timeRemaining = 0
let targetHit = 0
startGame()



```

```template
function resetGame () {
    player.execute(
    "clear @p bow"
    )
    player.execute(
    "clear @p arrow"
    )
    player.execute(
    "remove @e[type=arrow]"
    )
    blocks.place(DIAMOND_BLOCK, world(160, 28, 149))
}
function endGame () {
    agent.destroy(DOWN)
    gameplay.title(mobs.target(NEAREST_PLAYER), "GAME OVER", "Targets Hit: " + targetHit)
    loops.pause(3000)
}
function startGame () {
    blocks.place(LAPIS_LAZULI_BLOCK, world(160, 28, 149))
    setupGame()
    targetHit = 0
    while (timeRemaining > 0) {
        gameplay2()
    }
    if (timeRemaining == 0) {
        endGame()
        resetGame()
    }
}
function equipPlayer () {
    mobs.give(
    mobs.target(NEAREST_PLAYER),
    BOW,
    1
    )
    mobs.give(
    mobs.target(NEAREST_PLAYER),
    ARROW,
    128
    )
}
function setupGame () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(NEAREST_PLAYER)
    )
    timeRemaining = 600
    worldLocations = [
    world(167, 40, 151),
    world(167, 47, 151),
    world(159, 43, 151),
    world(151, 40, 151),
    world(151, 47, 151)
    ]
    countDown()
    buildTarget()
    equipPlayer()
}
function buildTarget () {
    agent.teleport(worldLocations._pickRandom(), NORTH)
    agent.setItem(TARGET, 1, 1)
    agent.setSlot(1)
    agent.place(DOWN)
}
function gameplay2 () {
    timeRemaining += -1
    if (agent.detect(AgentDetection.Redstone, DOWN)) {
        player.execute(
        "remove @e[type=arrow]"
        )
        agent.destroy(DOWN)
        player.execute(
        "playsound random.orb @a"
        )
        // This adds 1 to the score every time a Target is Hit
        targetHit += 1
        if (timeRemaining > 0) {
            buildTarget()
        }
    }
}
function countDown () {
    player.say("You have 30 seconds to hit as many targets as possible")
    loops.pause(3000)
    player.say("3...")
    player.execute(
    "playsound random.orb @a"
    )
    loops.pause(500)
    player.say("2...")
    player.execute(
    "playsound random.orb @a"
    )
    loops.pause(500)
    player.say("1...")
    player.execute(
    "playsound random.orb @a"
    )
    loops.pause(500)
    player.say("GO!!!")
    player.execute(
    "playsound random.orb @a"
    )
}
let worldLocations: Position[] = []
let timeRemaining = 0
let targetHit = 0
startGame()



```
