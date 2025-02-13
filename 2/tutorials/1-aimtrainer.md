# Aim Trainer.

### @explicitHints 1

### @activities true

## First Activity

### Step 1

From the ``||player:PLAYER||`` category, drag an ``||player:on chat command||`` into the workspace and change the command from **jump** to **play**

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

Press the green “Play” button. Then press “T” to open your in-game chat and type “play” and send to play Aim Trainer. 

#### ~ tutorialhint

```blocks

player.onChat("play", function () {
    prizes.playAimTrainer()
})






```template

```
