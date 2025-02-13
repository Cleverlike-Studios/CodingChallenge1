# Aim Trainer.

### @explicitHints 1

### @activities true

## First Activity

### Adding Rewards

Follow along with the Tutorial Video to fix the Prize Counter. 

The Tutorial Video can be watched here:
https://cleverlike.wistia.com/medias/f79k6xj7f2

#### ~ tutorialhint

```blocks
let change = 0
let prizeCost = 0
function buyPrize () {
    change = 0
    if (agent.getItemDetail(1) == EMERALD) {
        change = agent.getItemCount(1)
        if (agent.getItemCount(1) >= prizeCost) {
            prizes.givePrize()
            change = agent.getItemCount(1) - prizeCost
        } else {
            gameplay.title(mobs.target(NEAREST_PLAYER), "Sorry", "Not Enough Emeralds in Slot 1")
        }
    } else {
        gameplay.title(mobs.target(NEAREST_PLAYER), "Sorry", "Not Enough Emeralds in Slot 1")
        agent.dropAll(FORWARD)
    }
    mobs.give(
    mobs.target(NEAREST_PLAYER),
    EMERALD,
    change
    )
    agent.setItem(AIR, 1, 1)
    agent.dropAll(FORWARD)
}
player.onChat("play", function () {
    prizes.playAimTrainer()
})
player.onChat("headphones", function () {
    prizes.setPrize(Choice.Headphones)
    prizeCost = 2
    buyPrize()
})



```

```template
let change = 0
let prizeCost = 0
function buyPrize () {
    change = 0
    if (agent.getItemDetail(1) == EMERALD) {
        change = agent.getItemCount(1)
        if (agent.getItemCount(1) >= prizeCost) {
            prizes.givePrize()
            change = agent.getItemCount(1) - prizeCost
        } else {
            gameplay.title(mobs.target(NEAREST_PLAYER), "Sorry", "Not Enough Emeralds in Slot 1")
        }
    } else {
        gameplay.title(mobs.target(NEAREST_PLAYER), "Sorry", "Not Enough Emeralds in Slot 1")
        agent.dropAll(FORWARD)
    }
    mobs.give(
    mobs.target(NEAREST_PLAYER),
    EMERALD,
    change
    )
    agent.setItem(AIR, 1, 1)
    agent.dropAll(FORWARD)
}
player.onChat("play", function () {
    prizes.playAimTrainer()
})
player.onChat("headphones", function () {
    prizes.setPrize(Choice.Headphones)
    prizeCost = 2
    buyPrize()
})




```
