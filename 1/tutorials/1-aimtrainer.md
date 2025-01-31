# Aim Trainer.

### @explicitHints 1

### @activities true

## First Activity

### Let's Play!

Press the green Play button to try Aim Trainer!

#### ~ tutorialhint

```blocks
gameplay.setGameMode(
SURVIVAL,
mobs.target(NEAREST_PLAYER)
)
blocks.place(LAPIS_BLOCK, world(160, 28, 149))
let score = 0
let timeRemaining = 600
let worldLocations = [
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
    blocks.place(DIAMOND_BLOCK, world(160, 28, 149))
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



```

```template
gameplay.setGameMode(
SURVIVAL,
mobs.target(NEAREST_PLAYER)
)
let score = 0
let timeRemaining = 600
let worldLocations = [
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

```
