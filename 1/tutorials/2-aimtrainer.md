# Aim Trainer.

### @explicitHints 1

### @activities true

## First Activity

### Adding Rewards

Follow along with the Tutorial Video to repair the Aim Trainer game!

The Tutorial Video can be watched here:
https://cleverlike.wistia.com/medias/f79k6xj7f2

#### ~ tutorialhint

```blocks
function awardPlayer () {
	mobs.give(
    mobs.target(NEAREST_PLAYER),
    EMERALD,
    score
    )
}
function playGame () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(NEAREST_PLAYER)
    )
    score = 0
    timeRemaining = 600
    worldLocations = [
    world(167, 40, 151),
    world(167, 47, 151),
    world(159, 43, 151),
    world(151, 40, 151),
    world(151, 47, 151)
    ]
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
    agent.teleport(worldLocations._pickRandom(), NORTH)
    agent.setItem(TARGET, 1, 1)
    agent.setSlot(1)
    agent.place(DOWN)
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
    while (timeRemaining > 0) {
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
            score += 1
            if (timeRemaining > 0) {
                agent.teleport(worldLocations._pickRandom(), NORTH)
                agent.setItem(TARGET, 1, 1)
                agent.setSlot(1)
                agent.place(DOWN)
            }
        }
    }
    if (timeRemaining == 0) {
        agent.destroy(DOWN)
        gameplay.title(mobs.target(NEAREST_PLAYER), "GAME OVER", "Targets Hit: " + score)
        loops.pause(3000)
        awardPlayer()
    }
    player.execute(
    "clear @p bow"
    )
    player.execute(
    "clear @p arrow"
    )
    player.execute(
    "remove @e[type=arrow]"
    )
}
let score = 0
let worldLocations: Position[] = []
let timeRemaining = 0
playGame()


```

```template
function awardPlayer () {
	
}
function playGame () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(NEAREST_PLAYER)
    )
    score = 0
    timeRemaining = 600
    worldLocations = [
    world(167, 40, 151),
    world(167, 47, 151),
    world(159, 43, 151),
    world(151, 40, 151),
    world(151, 47, 151)
    ]
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
    agent.teleport(worldLocations._pickRandom(), NORTH)
    agent.setItem(TARGET, 1, 1)
    agent.setSlot(1)
    agent.place(DOWN)
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
    while (timeRemaining > 0) {
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
            score += 1
            if (timeRemaining > 0) {
                agent.teleport(worldLocations._pickRandom(), NORTH)
                agent.setItem(TARGET, 1, 1)
                agent.setSlot(1)
                agent.place(DOWN)
            }
        }
    }
    if (timeRemaining == 0) {
        agent.destroy(DOWN)
        gameplay.title(mobs.target(NEAREST_PLAYER), "GAME OVER", "Targets Hit: " + score)
        loops.pause(3000)
        awardPlayer()
    }
    player.execute(
    "clear @p bow"
    )
    player.execute(
    "clear @p arrow"
    )
    player.execute(
    "remove @e[type=arrow]"
    )
}
let score = 0
let worldLocations: Position[] = []
let timeRemaining = 0
playGame()




```
