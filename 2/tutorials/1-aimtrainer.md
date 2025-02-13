# Aim Trainer.

### @explicitHints 1

### @activities true

## First Activity

### Step 1

In the ``||player:on chat command||`` change the command from **run** to **play**

#### ~ tutorialhint

```blocks

player.onChat("play", function () {
})

```

### Step 2

From the ``||prizes:AIM TRAINER||`` category, drag the ``||prizes:play aim trainer||`` block into the the ``||player:on chat command||`` block.

#### ~ tutorialhint

```blocks

player.onChat("play", function () {
    prizes.playAimTrainer()
})

```

### Step 3

Press the green **Play** button. Then press **T** to open your in-game chat and type **play** and send to play Aim Trainer. 

#### ~ tutorialhint

```blocks

player.onChat("play", function () {
    prizes.playAimTrainer()
})

```




```template
player.onChat("run", function () {
})
```
