---
title: Adding Sound and Remote-Control to NeoPixelRacer
link: https://2018.hq.pyconuk.org/cfp/proposals/E70D/
proglang: micropython
status: totidy
layout: default

---

# Adding sound and remote control to micro:bit neopixelracer: MicroPython and radio-messaging for the bbc micro:bit

This is a [proposal for a Education Summit workshop for young coders]({{page.link}}) (Saturday, 50 mins).

## Proposal details
### What is your session about?

In this workshop we will add sound effects, music, and remote-controllers to an existing, exciting two-player neopixel light-racing game! 
We'll do this by using radio messaging between micro:bits, and we'll code this in MicroPython (It looks just like Python 3 code).

We'll make and customise the controllers ourselves.

If you're looking for cool project ideas for your micro:bit, you should definitely check this out!

Note: to get the most out of this workshop it is best if you've done a little bit of Python (or MicroPython) before. However, you do NOT need any experience with the micro:bit!

Note: We won't be programming the actual NeoPixels in this workshop, but we have made the code for that part available for anyone to reuse and learn from.

Is there anything else we should know about your proposal?
The workshop will be led by two young coders, F and N. Neill (the mentor) hopes to be silent support during delivery but may facilitate in discussions and time-keeping as necessary.

We recommend the maximum number of participants for this workshop is 12.

A version of this workshop for educators will also be submitted. We feel strongly that it will be very useful for them.

Examples will also be on hand of a few custom algorithmically-generated sound effects to inspire any advanced programmers.

An early (MakeCode) version of this activity was run very successfully at the London Science Museum's first CoderDojo by our group, and at Camden CLC's after-school "Hack Club" (in this workshop form). We found that young participants loved being able to contribute to a game that the rest of the group really enjoys playing, even if they don't yet have the skill to code the larger whole by themselves.

### Can you give us an outline of your proposed session?
@-05mins: Welcome the arriving workshop participants and learn about their programming experience in python and in micro:bit (if any). Learn their names! Assure them, if they're nervous, that the workshop isn't highly technical, but is highly fun.

[START]

@00mins: Invite people to play the game (in its core form - without sound and without remote controllers). Let everyone have a turn. YES, this is before any introductions have been made!

@03mins: Ask the audience to identify problems with the game, and areas for improvement. Two things inevitably come up: its lack of sound, and the fact that the crocodile clips can come loose when two players excitedly mash the micro:bit's buttons.

@04mins: Ask the audience about sound effects in other racing games they know: what are the sounds during the starting lights of Mario Kart? What other sound effects we might try to add to the game? This develops a rough spec for the sound effect part of the workshop.

@05mins: Confirm with the audience that they agree it would be easier to play if you had remote controls like on a video game console. Ask how many buttons each controller would need. This develops a rough spec the remote controller "make" part of the workshop.

@06mins: Finally, welcome everyone to the workshop and introduce the presenters. Show off micro:bit badges that speak our names and send messages! Say what we'll be doing: adding sound effects and remote controllers to the game and playing it at the end! Remember to set expectations: it's a short workshop so most people will just get one or the other done, of their choice, but not both.

@07mins: find out everyone's programming and micro:bit experience - know your audience.

@08mins: everyone get a micro:bit and start coding through the following tasks:

* Simplest MicroPython program: show an icon on screen on start
* Show everyone how to download the program onto their micro:bit
* Show everyone how to connect to a battery pack and disconnect from the main computer to emphasise its complete independence.

* Sending a radio message to a pre-existing shared listener micro:bit: have it send your name when your micro:bit starts. This one can speak the messages sent to it out loud.

* Receiving a radio message: display each message sent (including some from a class-wide micro:bit)

* Stopping the crazy radio chatter: how to change radio group! (get into informal pairs / threes)

* Responding to button presses: send a different message for button a and button b

* Have everyone move about room experimenting with sending their radio signals, on battery power.

* How to use the REPL (probably from Mu) to make experimentation easier.

@20mins: SPLIT the participants into two groups: sound effects and controller-makers. LET PEOPLE CHOOSE their activity (it does not matter if one group is much larger than the other).

THE SOUND EFFECT GROUP

sfx@21mins: Sound effect makers meet the music API:

* Where's the documentation?
* Play a musical note via the REPL
* Play two musical notes on button a, b pressed
* Show how to connect headphones to the micro:bit
* Play a prebuilt melody
* Tool-creation: write a program to listen for received numbers and show them on screen
* Investigation: Play the game and watch what numbers are being broadcast during play. Write them down in provided table.
* Give out complete reference sheet once everyone's had a try

sfx@30mins: start designing and coding YOUR sound effects.

* Optionally use the shared MIDI keyboard to pick notes.
* Beginners can use an if statement in python to only play a sound if the received number matches the event of interest.
* Help more experienced python programmers to consider other options (dictionary?)
* Once you have coded sounds for the just the starting-light sequence, test your work, and make sure you have a backup.

* Extra challenge: add victory tunes for player 1 win, player 2 win
* Extra challenge: use the text-to-speech module to say "ready", "steady", "go!"
* Extra challenge: add little sounds that play whenever the players go forward

sfx@40mins: final touches

THE REMOTE-CONTROLLER 'MAKE' GROUP

rc@21mins: remote-controller group make simplest controller

* Learn about the most important input radio messages the game expects
* Send number 1 on button A, send number 2 on button B
* Test it out with the pre-made listeners/debuggers
* Test it out with the main game
* Add shake-to-start

rc@30mins: Make a better controller from kitchen-foil, cardboard, blutack, and croc clips

* Show completing a circuit from p0 to Gnd will trigger an event in the micro:bit. Just tap croc clips together to do this - stress not to short 3v to Ground.
* Have everyone show something on screen on pin1 touched, and on pin2 touched
* Test by tapping croc clips
* Show how we can make this circuit with kitchen foil and human, instead.
* Organise roughly into pairs to make some sets of p1 controller and p2 controller separately (odd numbers is fine)
* Spec: send number 1 (or 2) when "pin1 is touched", depending on which player's controller you're making
* TEST on the real game!
* Make a backup of your code. (Contingency: everyone's controllers can use the same program for this section if necessary)

rc@40mins:

Decorate and customise your controller with felt-pen, stickers, etc, so that it is unique. Get it photographed if you want it on twitter!

* Extra challenge (easy): add a button to send the "start game" * code.
* Extra challenge (medium): put a cheat into your controller - shake should make you move really fast.

ALL

@45mins: ALL REGROUP to play the game together!

* Have participants take it in turns to power-on their custom modules. Announce this is also an opportunity to record and photograph their work.

@48mins: discussion

Reflection, discussion, and ideas for further work:
* Was it better with sound effects and remote-controllers?
* Why didn't we have to change the game to add these sounds and controllers?
* What else you could use these "remote controls" for? Show examples (slides and some live demos).
* What projects you might add sound effects to?
* What happens when everyone's micro:bit responds with music at the same time? What would happen if they played in harmony with each other? A micro:bit choir coordinated by radio messages! (Show demo of micro:bit harmoniser)
* Discuss what other games you could make with a strip of NeoPixels.
* Mention a final handout which has resources for going further.

@50mins: Wrap up

* Congratulate everyone and thank them. Request feedback and explain why you want it. Say goodbye. Give tiny handout with URL with a web-page with information for further work, links to documentation, and our simple online feedback form.

@51mins: remind those still playing the game not to forget to go to their next workshop :)

### What are your equipment and other requirements?
Computers with which to program the micro:bits. Ideally with Mu installed and tested.

USB leads and battery packs for the supplied micro:bits.

A workspace which is not too noisy to hear our young coders.
