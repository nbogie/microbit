---
title: Zip Halo (NeoPixel Ring) Patterns Demo
description: An interactive set of patterns for the kitronik zip halo or other neopixel rings.
link: TODO
proglang: makecode
---

Visit [The Repo]({{page.link}}) for more on this

```
let passIx = 0
let firstColor = 0
let pattern: neopixel.Strip = null
let index = 0
let myBrightness = 0
let secondColor = 0
let fnNames: string[] = []
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber >= 0) {
        if (receivedNumber < fnNames.length) {
            fnIx = receivedNumber
            runCurrFn()
        }
    }
})
function setupFns() {
    fnNames = ["sparkle", "sparkleGlow", "glow", "rainbowSpin", "dial", "3Spin", "3SpinB", "3SpinC", "colorByTilt", "spinFaster"]
    fnIx = 7
}
input.onButtonPressed(Button.B, function () {
    runCurrFn()
})
function threeSpin() {
    pattern.clear()
    pattern.setBrightness(255)
    pattern.range(0, 1).showColor(neopixel.colors(NeoPixelColors.Blue))
    pattern.range(7, 1).showColor(neopixel.colors(NeoPixelColors.Green))
    pattern.range(15, 1).showColor(neopixel.colors(NeoPixelColors.Purple))
    for (let i = 0; i < 100; i++) {
        basic.pause(50)
        pattern.rotate(pins.map(
            input.rotation(Rotation.Roll),
            -180,
            180,
            -5,
            5
        ))
        pattern.show()
    }
    wipe()
}
input.onButtonPressed(Button.A, function () {
    nextFn()
})
function threeSpinB() {
    pattern.clear()
    pattern.range(0, 1).showColor(neopixel.colors(NeoPixelColors.Yellow))
    pattern.range(7, 1).showColor(neopixel.colors(NeoPixelColors.Yellow))
    pattern.range(15, 1).showColor(neopixel.colors(NeoPixelColors.Yellow))
    for (let i = 0; i < 100; i++) {
        basic.pause(50)
        pattern.rotate(0 - pins.map(
            input.rotation(Rotation.Roll),
            -180,
            180,
            -5,
            5
        ))
        pattern.show()
    }
    wipe()
}
input.onButtonPressed(Button.AB, function () {
    radio.sendNumber(fnIx)
})
function wipe() {
    for (let i = 0; i < 24; i++) {
        pattern.shift(1)
        pattern.show()
        basic.pause(10)
    }
    basic.clearScreen()
}
function nextFn() {
    fnIx += 1
    if (fnIx >= fnNames.length) {
        fnIx = 0
    }
    basic.showNumber(fnIx)
    basic.clearScreen()
}
function runCurrFn() {
    switch (fnIx) {
        case 0:
            randomSparkle();
            break;
        case 1:
            randomSparkleWithGlow();
            break;
        case 2:
            glow();
            break;
        case 3:
            rainbowRotate();
            break;
        case 4:
            dial();
            break;
        case 5:
            threeSpin();
            break;
        case 6:
            threeSpinB();
            break;
        case 7:
            threeSpinC();
            break;
        case 8:
            colorByTilt();
            break;
        case 9:
            spinFaster();
            break;
    }
}
function threeSpinC() {
    secondColor = neopixel.hsl(Math.randomRange(0, 360), 99, 50)
    firstColor = neopixel.hsl(Math.randomRange(0, 360), 99, 50)
    pattern.clear()
    pattern.setBrightness(255)
    pattern.range(0, 1).showColor(firstColor)
    pattern.range(7, 1).showColor(firstColor)
    pattern.range(15, 1).showColor(firstColor)
    pattern.setBrightness(30)
    pattern.range(23, 1).showColor(secondColor)
    pattern.range(1, 1).showColor(secondColor)
    pattern.range(6, 1).showColor(secondColor)
    pattern.range(8, 1).showColor(secondColor)
    pattern.range(14, 1).showColor(secondColor)
    pattern.range(16, 1).showColor(secondColor)
    for (let i = 0; i < 100; i++) {
        basic.pause(50)
        pattern.rotate(0 - pins.map(
            input.rotation(Rotation.Roll),
            -180,
            180,
            -5,
            5
        ))
        pattern.show()
    }
    wipe()
}
function sendLightLevelFor10seconds() {
    for (let i = 0; i < 100; i++) {
        radio.sendNumber(input.lightLevel())
        basic.pause(100)
    }
}
function demoAll() {
    spinFaster()
    randomSparkleWithGlow()
    rainbowRotate()
    threeSpinC()
    dial()
    glow()
    threeSpinB()
}
function randomSparkle() {
    pattern.clear()
    pattern.setBrightness(255)
    for (let i = 0; i < 48; i++) {
        basic.pause(50)
        pattern.clear()
        pattern.range(Math.randomRange(0, 24), 1).showColor(neopixel.colors(NeoPixelColors.White))
    }
    wipe()
}
function dial() {
    pattern.clear()
    pattern.range(0, 1).showColor(neopixel.colors(NeoPixelColors.Indigo))
    for (let i = 0; i < 24; i++) {
        basic.pause(50)
        pattern.rotate(1)
        pattern.show()
    }
    wipe()
}
function randomSparkleWithGlow() {
    pattern.clear()
    pattern.show()
    for (let index2 = 0; index2 <= 50; index2++) {
        for (let i = 0; i < 4; i++) {
            pattern.setBrightness(index2 * 5)
            pattern.range(Math.randomRange(0, 24), 1).showColor(neopixel.hsl(Math.randomRange(0, 361), 100, 50))
            basic.pause(100 - index2 * 2)
            pattern.clear()
        }
    }
    for (let i = 0; i < 50; i++) {
        pattern.setBrightness(255)
        pattern.range(Math.randomRange(0, 24), 1).showColor(neopixel.hsl(Math.randomRange(0, 361), 100, 50))
        basic.pause(0)
        pattern.clear()
    }
    pattern.clear()
    pattern.show()
    for (let index3 = 0; index3 <= 50; index3++) {
        pattern.setBrightness(index3 * 5)
        pattern.showColor(neopixel.hsl(index3, 100, 50))
        basic.pause(5)
    }
    for (let index4 = 0; index4 <= 50; index4++) {
        pattern.setBrightness((50 - index4) * 5)
        pattern.showColor(neopixel.hsl(50 - index4, 100, 50))
        basic.pause(40)
    }
    pattern.setBrightness(255)
}
function rainbowRotate() {
    pattern.showRainbow(1, 360)
    pattern.setBrightness(255)
    for (let i = 0; i < 100; i++) {
        basic.pause(50)
        pattern.rotate(1)
        pattern.show()
    }
}
function glow() {
    myBrightness = 0
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 40; i++) {
            pattern.setBrightness(myBrightness)
            pattern.showColor(neopixel.colors(NeoPixelColors.Red))
            myBrightness += 6
            basic.pause(30)
        }
        for (let i = 0; i < 40; i++) {
            myBrightness += -6
            pattern.setBrightness(myBrightness)
            pattern.showColor(neopixel.colors(NeoPixelColors.Red))
            basic.pause(30)
        }
    }
    pattern.setBrightness(255)
}
function spinFaster() {
    pattern.clear()
    for (let passIx2 = 0; passIx2 <= 10; passIx2++) {
        pattern.setBrightness(5 + passIx2 * 25)
        for (let ledIx2 = 0; ledIx2 <= 23; ledIx2++) {
            pattern.range(ledIx2, 1).showColor(neopixel.colors(NeoPixelColors.Indigo))
            basic.pause(50 - passIx2 * 5)
            pattern.rotate(1)
            pattern.show()
        }
    }
    for (let passIx3 = 0; passIx3 <= 10; passIx3++) {
        pattern.setBrightness((10 - passIx3) * 25)
        for (let ledIx3 = 0; ledIx3 <= 23; ledIx3++) {
            pattern.range(ledIx3, 1).showColor(neopixel.colors(NeoPixelColors.Indigo))
            basic.pause(50 - (10 - passIx3) * 5)
            pattern.rotate(-1)
            pattern.show()
        }
    }
    wipe()
}
function colorByTilt() {
    pattern.clear()
    for (let i = 0; i < 100; i++) {
        pattern.showColor(neopixel.hsl(pins.map(
            input.rotation(Rotation.Pitch),
            -90,
            90,
            0,
            360
        ), 99, 50))
        basic.pause(50)
    }
    pattern.clear()
    pattern.show()
}
let fnIx = 0
index = 0
pattern = neopixel.create(DigitalPin.P0, 24, NeoPixelMode.RGB)
passIx = 0
fnIx = 7
radio.setGroup(7)
setupFns()
basic.showLeds(`
    . . # # #
    . . . . #
    # # . # #
    # . . . #
    # # . . #
    `)
basic.clearScreen()

```