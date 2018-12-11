---
title: Collaboration Without Catastrophe
description: microbit radio messaging makes it easy for students to collaborate on non-trivial projects together without many of the traditional problems.
link: TODO
status: placeholder
layout: default
---


# Write-up to follow


Are you looking for cool, non-trivial project ideas for your micro:bit or Python class or club?

Are you looking for a way to have your micro:bit beginners contribute really meaningful pieces to a bigger whole, without the wiring getting more complex, without the code getting messier, and without risking the whole thing falling apart?

use radio messaging between micro:bits to add sound effects, music, and remote-controllers to an existing, exciting two-player NeoPixel light-racing game!

As educators, we'll complete the same activities the kids would. We'll see that a divide-and-conquer approach using radio messaging between components allows for individuals to easily contribute simple pieces to the larger shared whole, at their own speed, without dependencies on each other, and without creating one giant, hard-to-understand, bug-ridden program. Easier coding? Check. Easier wiring? Check. More free pins on our micro:bit? Check!

An early (MakeCode) version of this activity was run very successfully at the London Science Museum's first CoderDojo by our group, and at Camden CLC's after-school "Hack Club" (in this workshop form).

## sample activity 

@00mins: Invite people to play the game (in its core form - without sound and without remote controllers). Let everyone have a quick turn. YES, this is before any introductions have been made!

@03mins: Ask the audience to identify problems with the game, and areas for improvement. Two things inevitably come up: its lack of sound, and the fact that the crocodile clips can come loose when two players excitedly mash the microbit's buttons.

@04mins: Ask the audience about sound effects in other racing games they know: what are the sounds during the starting lights of Mario Kart? What other sound effects we might try to add to the game? This develops a rough spec for the sound effect part of the workshop.

@05mins: Confirm with the audience that they agree it would be easier to play if you had remote controls like on a video game console. Ask how many buttons each controller would need. This develops a rough spec the remote controller "make" part of the workshop.

...

@20mins: SPLIT the participants into two groups: sound effects and controller-makers. (It does not matter if one group is much larger than the other.)

THE SOUND EFFECT GROUP

sfx@21mins: Sound effect makers meet the music API:

...
* Tool-creation: write a program to listen for received numbers and show them on screen
* Investigation: Play the game and watch what numbers are being broadcast during play. Write them down in provided table.
* Give out complete reference sheet once everyone's had a try

sfx@30mins: start designing and coding YOUR sound effects.

* Beginners can use an if statement in python to only play a sound if the received number matches the event of interest.

* Bonus challenge: add victory tunes for player 1 win, player 2 win
* Bonus challenge: use the text-to-speech module to say "ready", "steady", "go!"
* Bonus challenge: add little sounds that play whenever the players go forward
* Bonus challenge: (for a musically inclined pair): respond to the events with short two-part harmony or counterpoint.

sfx@40mins: final touches

THE REMOTE-CONTROLLER 'MAKE' GROUP

rc@21mins: remote-controller group make simplest controller

* Learn about the game's expected inputs (which radio messages will control it)
* Send number 1 on button A, send number 2 on button B
* Test it out with the premade listeners/debuggers
* Test it out with the main game
* Add shake-to-start

rc@30mins: Make a better controller from kitchen-foil, cardboard, bluetack, and croc clips

* Show completing a circuit from p0 to gnd will trigger an event in the microbit. Just tap croc clips together to do this - stress not to short 3v to gnd.
* Have everyone show something on screen on pin1 touched, and on pin2 touched
* Test by tapping croc clips
* Show how we can make this circuit with kitchen foil and human, instead.
* Organise roughly into pairs to make some sets of p1 controller and p2 controller separately (odd numbers is fine)
* Spec: send number 1 (or 2) when "pin1 is touched", depending on which player's controller you're making
* TEST on the real game!
* Make a backup of your code. (Contingency: everyone's controllers can use the same program for this section if necessary)

rc@40mins:

* Decorate and customise your controller with felt-pen, stickers, etc, so that it is unique. Tweet it!

* Bonus challenge (easy): add a button to send the "start game" code.
* Bonus challenge (medium): put a cheat into your controller: shake should make you move really fast.

ALL

@45mins: ALL REGROUP to play the game together!

* Have participants take it in turns to play the game using their own custom modules, and with other people's. Encourage tweeting photos/videos of their work.

@47mins: discussion

Reflection, discussion, and ideas for further work:

* Was it better with sound effects and remote-controllers? What else might we add?
* Why didn't we have to change (or even reboot) the game to add these sounds and controllers?
* What was the effect of one participant's contribution breaking, or being buggy? Did it break the whole? What impact did it have on others' work? Was it difficult to fix?
* What issues do the educators think they would have with a classroom full of kids all doing the activity at once? Particularly the noisy sound-creation part?
* What happens when everyone's microbit responds with sfx at the same time? What would happen if they all played harmonies? A micro:bit choir coordinated by radio messages! (Show demo of micro:bit harmoniser)
* What else you could use these "remote controls" for? Show examples (slides and some live demos).
* What projects you might add sound effects to?
* Discuss what other games you could make with a strip of NeoPixels.

Propose a forum for further discussion.

@50mins: Congratulate everyone and thank them (just because they are educators doesn't mean this was easy for them!) Request feedback. Say goodbye. (Give tiny handout with URL with a web-page with information for further work, links to support materials, and library documentation, and our simple online feedback form.)

@51mins: chase to next workshop

What are your equipment and other requirements?
Computers with which to program the micro:bits. Ideally with Mu installed and tested.

USB leads and battery packs for the micro:bits.

The workspace shouldn't be too noisy to hear our young coders.

This talk is suitable for teachers.
