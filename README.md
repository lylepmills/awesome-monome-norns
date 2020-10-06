# awesome-monome-norns


<img src="https://monome.org/images/norns-front-small.jpg" width="500">

A list of links and resources for the [norns](https://monome.org/docs/norns/) hardware music platform by [monome](https://monome.org/).

**norns** is in essence a glorified [SuperCollider](https://supercollider.github.io/) frontend taking the shape of portable device.

[Pure Data](https://puredata.info/) patches are also supported (see Mother).

The community resides mostly on [llllllll.co](https://llllllll.co/) (pronounced _lines_).

<!-- https://llllllll.co/t/norns-dust/14015 -->
<!-- https://llllllll.co/t/ash-a-small-collection/21349 -->

## Hardware

There are 2 variations of the norns hardware:

 - [norns](https://market.monome.org/collections/primary/products/norns), relying on a Raspbery Pi CM3 or CM3+
 - [norns shield](https://market.monome.org/collections/primary/products/norns-shield-kit), a HAT for Raspbery Pi 3B or 3B+.


#### norns shield

The **norns shield** option is DIY and more economic but lacks a battery, has no monitor output, a less clean audio path and is more generally less rugged.

For more information about building your own norns using the **norns shield**:

 - [t/diy-norns-shield](https://llllllll.co/t/diy-norns-shield/27638) for general build help
 - [t/norns-shield-case-designs](https://llllllll.co/t/norns-shield-case-designs/30347) for building a case

[u/JHC](https://llllllll.co/u/JHC) provided a [nice 3D printing STL design](https://llllllll.co/t/norns-shield-case-designs/30347/224).

[u/okyeron](https://llllllll.co/u/okyeron) created some [nice laser-cut designs](https://llllllll.co/t/norns-shield-case-designs/30347/183) that he also sells for a very reasonable cost [on his online store](https://denki-oto.weebly.com/store/p39/norns-shield-case.html#/).

If you don't have access to a fablab, you can use a laser-cut service such as:

 - [ponoko](https://www.ponoko.com/) (US)
 - [razorlab](https://razorlab.online/) (UK)

For encoder caps, you can look at makers such as Sifam / Selco, the various offerings at aliexpress ([example](https://www.aliexpress.com/item/32781327404.html?spm=2114.13010708.0.0.3a994c4dQ4Aov1)) or even go the [3D printing route](https://llllllll.co/t/diy-norns-shield/27638/876).


#### Hardware companions

Some apps are made to work only with some of other **monome** hardware (such as **grid**, **arc** and **crow**).

Others rely on other input devices such as MIDI controllers (pad, keyboards...) or a computer keyboard.

For discussing those options, see [t/friends-of-norns](https://llllllll.co/t/friends-of-norns-gear-accessories-etc/17150).


## Development: General

The **norns** platform abstracts [SuperCollider](https://supercollider.github.io/) through the use

#### Documentation

 - [basic lua scripting reference](https://monome.org/docs/norns/script-reference/)
 - [complete lua APIs doc](https://monome.org/norns/)


#### Tutorials & example apps

 - [norns studies](https://monome.org/docs/norns/studies-landing/)
 - [norns: tutorial](https://llllllll.co/t/norns-tutorial/23241) by [Devine Lu Linvega](https://xxiivv.com/)
 - [foundry](https://llllllll.co/t/foundry) app ([code](https://github.com/csboling/foundry)) for text & fonts
 - [video tutorial on adding midi out to an existing app](https://llllllll.co/t/norns-walkthrough-hacking-a-script-to-add-midi-output/34969)


#### Community

When wanting to contribute or seeking help, use one of those threads:

 - [t/norns-scripting](https://llllllll.co/t/norns-scripting/14120): getting help with app development (lua)
 - [t/norns-softcut](https://llllllll.co/t/norns-2-0-softcut/20550): getting help with app development (softcut)
 - [t/norns-supercollider](https://llllllll.co/t/norns-supercollider/22822): getting help with app development (SuperCollider side)
 - [t/norns-development](https://llllllll.co/t/norns-development/14073): proposing evloutions to core norns code
 - [t/exquisite-script-a-collective-scripting-game-for-norns](https://llllllll.co/t/exquisite-script-a-collective-scripting-game-for-norns/34989): a cadavre exquis, collective development of an app


## Development: Libraries & Engines

When developping apps/scripts, you rely on lua libraries (classes & modules) and / or SuperCollider libraries (called _engines_ in the context of **norns** development).

Most advanced apps come with their own custom libraries / engine.

Here are listed the most reccuring ones.


#### Softcut & Softcut-based

| library                        | code                                                       | description                         | based upon | provided by          | used by                            |
| --                             | ---                                                        | ---                                 | ---        | ---                  | ---                                |
| [softcut][lib softcut lines]   | [lua][lib softcut gh lua], [undelying C][lib softcut gh C] | sample record & playback            |            | installed by default | sam, reels, piwip                  |
| ack                            | [lua][lib ack gh lua]                                      | advanced sample playback            | softcut    | installed by default | step, ash/playfair, foulplay, takt |
| [supercut][lib supercut lines] | [lua][lib supercut gh lua]                                 | higher-level wrapper around softcut |            |                      | wrms                               |


#### SuperColider-based

| library         | code                                                                        | description                                     | provided by                                | used by                          |
| --              | ---                                                                         | ---                                             | ---                                        | ---                              |
| timber          | [lua wrapper][lib timber gh lua], [sclang][lib timber gh sc]                | advanced sample playback                        | [timber][app timber lines]                 | timber                           |
| polyperc        | [sclang][lib polyperc gh sc]                                                | simple polyphonic filtered decaying square wave | [awake][app awake lines]                   | awake, meadowphysics, barycenter |
| molly_the_poly  | [lua wrapper][lib molly_the_poly gh lua] [sclang][lib molly_the_poly gh sc] |                                                 | [molly_the_poly][app molly_the_poly lines] | molly_the_poly, arp_index        |
| passersby       | [lua wrapper][lib passersby gh lua] [sclang][lib passersby gh sc]           |                                                 | [passersby][app passersby lines]           | passersby, dunes                 |
| PrimitiveString | [sclang][lib PrimitiveString gh sc]                                         |                                                 | [euclidigons][app euclidigons lines]       |                                  |


## Scripts & Apps

New behaviours for the **norns** are created by writting lua _scripts_.

Once packaged and distributed, _scripts_ are generally called _apps_.

#### List

Many apps are available through [maiden](https://monome.org/docs/norns/maiden/) but many more are missing.

The [documentation](https://monome.org/docs/norns/app/) has a section regarding .

This section is aimed at being more complete and providing more meta-data to select which app corresponds to your needs.

Synths & drones:

| app                                        | on maiden | code                         | description                                                                                                 | demo                                         | doc                   |
| ---                                        | ---       | ---                          | ---                                                                                                         | ---                                          | ---                   |
| [dronecaster][app dronecaster lines]       | X         | [gh][app dronecaster src]    | Various drones                                                                                              | [1][app dronecaster demo 1]                  |                       |
| [fm7][app fm7 lines]                       | X         | [gh][app fm7 src]            | DX7-inspired polyphonic FM synth                                                                            | [1][app fm7 demo 1]                          | [online][app fm7 doc] |
| [lissadron][app lissadron lines]           | X         | [gh][app lissadron src]      | A software synth making extensive use of seeded randomness.                                                 | [internal sequencer][app lissadron demo seq] |                       |
| [molly_the_poly][app molly_the_poly lines] | X         | [gh][app molly_the_poly src] | Juno-6 voice structure with chorus, the extra modulation of a Jupiter-8, and CS-80 inspired ring modulation | [1][app molly_the_poly demo 1]               |                       |
| [passersby][app passersby lines]           | X         | [gh][app passersby src]      | Wave folding, FM, LPG, spring-ish reverb, LFO and two dice to roll                                          | [1][app passersby demo 1]                    |                       |

Sequencers, trackers & sample manglers:

| app                                                                   | on maiden | code                                                       | demo                                                                                            | doc                                                                          |
| ---                                                                   | ---       | ---                                                        | ---                                                                                             | ---                                                                          |
| [arcologies][app arcologies lines]                                    | X         | [gh][app arcologies src]                                   | [gallery](https://tyleretters.github.io/arcologies-docs/gallery)                                | [online][app arcologies doc]                                                 |
| [arp_index][app arp_index lines]                                      | X         | [gh][app arp_index src]                                    |                                                                                                 |                                                                              |
| [ash/playfair](https://llllllll.co/t/ash-a-small-collection/21349)    | X         | [gh](https://github.com/tehn/ash/blob/master/playfair.lua) | [1](https://vimeo.com/270668759)                                                                |                                                                              |
| [awake][app awake lines]                                              | default   | [gh][app awake src]                                        |                                                                                                 |                                                                              |
| [cheat codes](https://llllllll.co/t/31655)                            | X         |                                                            | [1](https://www.youtube.com/watch?v=gfM5MiYKvxc&t=132s)                                         | [pdf](https://llllllll.co/uploads/short-url/mkkpeOUJCreIwVIP0Jdf8rpfYDJ.pdf) |
| [dunes](https://llllllll.co/t/dunes)                                  |           | [gh](https://github.com/oliviercreurer/dunes)              | [audio](https://llllllll.co/t/dunes/24790), [midi](https://llllllll.co/t/dunes/24790/18)        |                                                                              |
| [euclidigons](https://llllllll.co/t/euclidigons/36666)                | X         | [gh](https://github.com/synthetiv/euclidigons/)            | [1](https://www.youtube.com/watch?v=o9bUmd2UaYc), [2](https://www.instagram.com/p/CFkNeIID3e7/) |                                                                              |
| [foulplay](https://llllllll.co/t/foulplay/21081)                      | X         | [gh](https://github.com/justmat/foulplay)                  | [1](https://vimeo.com/328283781)                                                                | [online](https://github.com/justmat/foulplay/blob/master/readme.md)          |
| [meadowphysics](https://llllllll.co/t/meadowphysics-norns/21185)      | X         | [gh](https://github.com/alpha-cactus/meadowphysics)        | [1](https://vimeo.com/146731772)                                                                | [online](https://monome.org/docs/meadowphysics/)                             |
| [mlr](https://llllllll.co/t/mlr-norns)                                | X         | [gh](https://github.com/tehn/mlr)                          | [1](https://vimeo.com/266741634)                                                                |                                                                              |
| [nisp](https://llllllll.co/t/nisp)                                    | X         | [gh](https://github.com/itsyourbedtime/NISP)               | [1](https://www.instagram.com/p/B54rUM6hnWJ/), [2](https://www.instagram.com/p/B545yPRh5QA/)    |                                                                              |
| [punchcard](https://llllllll.co/t/punchcard)                          | X         | [gh](https://github.com/neauoire/punchcard)                | [1](https://www.youtube.com/watch?v=QO7T6MYkqZo)                                                |                                                                              |
| [spacetime](https://monome.org/docs/norns/study-3/) `we/study/study3` | X         |                                                            |                                                                                                 |                                                                              |
| [step](https://llllllll.co/t/step/21093)                              | X         | [gh](https://github.com/antonhornquist/step)               |                                                                                                 |                                                                              |
| [takt](https://llllllll.co/t/takt/21032)                              | X         | [gh](https://github.com/itsyourbedtime/takt)               |                                                                                                 | [online](https://github.com/monome/dust/blob/master/docs/bedtime/index.md)   |

Control Modulation sources:
| app                                            | on maiden | code                                         | demo | doc |
| ---                                            | ---       | ---                                          | ---  | --- |
| [barycenter](https://llllllll.co/t/barycenter) |           | [gh](https://github.com/echophon/barycenter) |      |     |
| [shapes](https://llllllll.co/t/shapes/36759)   |           | [gh](https://github.com/tlubke/shapes)       |      |     |


Basic samplers:
| app                                    | on maiden | code                                 | description                                     |
| ---                                    | ---       | ---                                  | ---                                             |
| [sam](https://llllllll.co/t/sam/23943) |           | [gh](https://github.com/justmat/sam) | record, adjust start & end points, save to tape |

Audio effects:

| app                                        | on maiden | code                                          | description                                 | demo                                             | doc |
| ---                                        | ---       | ---                                           | ---                                         | ---                                              | --- |
| [greyhole](https://llllllll.co/t/greyhole) | X         | [gh](https://github.com/justmat/greyhole)     | echo / delay                                | [1](https://vimeo.com/379334153)                 |     |
| [pedalboard](https://llllllll.co/t/31119)  | X         | [gh](https://github.com/21echoes/pedalboard)  | chainable effects for live performance      |                                                  |     |
| [pools](https://llllllll.co/t/pools)       | X         | [gh](https://github.com/justmat/pools)        | a shimmery reverb                           | [1](https://vimeo.com/383786715)                 |     |

Loopers, live samplers & crazy delays:

| app                                          | on maiden | code                                          | description                                         | demo                                                                                         | doc |
| ---                                          | ---       | ---                                           | ---                                                 | ---                                                                                          | --- |
| [blndr](https://llllllll.co/t/blndr/35106)   | X         | [gh](https://github.com/schollz/blndr)        | a quantized delay with time bending effects         | [1](https://llllllll.co/t/blndr/35106)                                                       |     |
| [cranes](https://llllllll.co/t/cranes/21207) | X         | [gh](https://github.com/dndrks/cranes)        | stereo varispeed looper / delay / timeline-smoosher | [1](https://www.instagram.com/p/Bv5klu_l9mp/)                                                |     |
| [oooooo](https://llllllll.co/t/oooooo/35828) | X         | [gh](https://github.com/schollz/oooooo)       | digital tape loops x 6                              | [1](https://www.instagram.com/p/CEeMRPDhCt_/), [2](https://www.instagram.com/p/CEb2CDQBXaz/) |     |
| [piwip](https://llllllll.co/t/piwip)         | X         | [gh](https://github.com/schollz/piwip)        | a sampler that works in realtime                    | [1](https://www.instagram.com/p/CFla2iJh9zC/)                                                |     |
| [reels](https://llllllll.co/t/reels)         | X         | [gh](https://github.com/itsyourbedtime/reels) | a 4-track asynchronous looper                       | [1](https://www.youtube.com/watch?v=SuF1uTTlyn4)                                             |     |


#### By I/O

| symbol                 | meaning              |
| ---                    | ---                  |
| :red_circle:           | mandatory            |
| :large_orange_diamond: | strongly encouraged, |
| :white_circle:         | optional             |


| app                                                                   | audio in | midi in                    | keyboard     | grid                   | arc                    | TouchOSC               | audio out | midi out | crow |
| ---                                                                   | ---      | ---                        | ---          | ---                    | ---                    | ---                    | ---       | ---      | ---  |
| [arcologies][app arcologies lines]                                    |          |                            |              | :red_circle:           |                        |                        |           |          |      |
| [arp_index](https://llllllll.co/t/the-arp-index)                      |          | :white_circle:             |              |                        |                        |                        | X         | X        |      |
| [awake](https://llllllll.co/t/awake)                                  |          | :white_circle: (only sync) |              | :white_circle:         |                        |                        | X         |          |      |
| [barycenter](https://llllllll.co/t/barycenter)                        |          |                            |              |                        |                        |                        | X         | X        |      |
| [cheat codes](https://llllllll.co/t/cheat-codes)                      |          |                            |              | :large_orange_diamond: | :large_orange_diamond: | :large_orange_diamond: |           |          |      |
| [cranes](https://llllllll.co/t/cranes/21207)                          | X        |                            |              | :white_circle:         |                        |                        | X         |          |      |
| [dunes](https://llllllll.co/t/dunes)                                  |          |                            |              |                        |                        |                        | X         |          |      |
| [dronecaster][app dronecaster lines]                                  |          |                            |              |                        |                        |                        | X         |          |      |
| [euclidigons](https://llllllll.co/t/euclidigons/36666)                |          |                            |              |                        |                        |                        | X         | X        |      |
| [foulplay](https://llllllll.co/t/foulplay/21081)                      |          |                            |              | :large_orange_diamond: |                        |                        | X         | X        |      |
| [fm7][app fm7 lines]                                                  |          | :large_orange_diamond:     |              | :large_orange_diamond: |                        |                        | X         |          |      |
| [greyhole](https://llllllll.co/t/greyhole)                            | X        |                            |              |                        |                        |                        | X         |          |      |
| [lissadron][app lissadron lines]                                      |          | :large_orange_diamond:     |              |                        |                        |                        | X         |          |      |
| [meadowphysics](https://llllllll.co/t/meadowphysics-norns/21185)      |          |                            |              | :red_circle:           |                        |                        | X         | X        |      |
| [mlr](https://llllllll.co/t/mlr-norns)                                | X        |                            |              | :red_circle:           |                        |                        | X         |          |      |
| [molly_the_poly][app molly_the_poly lines]                            |          | :red_circle:               |              | :white_circle: \*      |                        |                        | X         |          |      |
| [nisp](https://llllllll.co/t/nisp)                                    |          |                            | :red_circle: |                        |                        |                        | X         |          |      |
| [oooooo](https://llllllll.co/t/oooooo/35828)                          | X        |                            |              |                        |                        |                        | X         |          |      |
| [passersby][app passersby lines]                                      |          | :red_circle:               |              | :white_circle: \*      |                        |                        | X         |          |      |
| [pedalboard](https://llllllll.co/t/31119)                             | X        |                            |              |                        |                        |                        | X         |          |      |
| [piwip](https://llllllll.co/t/piwip)                                  |          |                            |              |                        |                        |                        |           |          |      |
| [pools](https://llllllll.co/t/pools)                                  | X        |                            |              |                        |                        |                        | X         |          |      |
| [punchcard](https://llllllll.co/t/punchcard)                          |          |                            |              | :red_circle:           |                        |                        |           | X        |      |
| [reels](https://llllllll.co/t/reels)                                  | X        |                            |              |                        |                        |                        | X         |          |      |
| [shapes](https://llllllll.co/t/shapes/36759)                          |          |                            |              |                        |                        |                        |           |          |      |
| [spacetime](https://monome.org/docs/norns/study-3/) `we/study/study3` |          |                            |              |                        |                        |                        | X         |          |      |
| [step](https://llllllll.co/t/step/21093)                              |          |                            |              | :red_circle:           | :large_orange_diamond: |                        | X         |          |      |
| [takt](https://llllllll.co/t/takt/21032)                              |          |                            |              | :red_circle:           |                        |                        | X         |          |      |


Special cases:

 - \*: grid acts as a midi keyboard and can replace it


<!-- softcut libs -->
[lib softcut lines]: https://llllllll.co/t/norns-2-0-softcut/20550
[lib softcut gh lua]: https://github.com/monome/norns/blob/main/lua/core/softcut.lua
[lib softcut gh C]: https://github.com/monome/softcut-lib
[lib ack gh lua]: https://github.com/antonhornquist/ack
[lib supercut lines]: https://llllllll.co/t/supercut-lib/29526
[lib supercut gh lua]: https://github.com/andr-ew/supercut
<!-- supercolier libs -->
[lib timber gh lua]: https://github.com/markwheeler/timber/blob/master/lib/timber_engine.lua
[lib timber gh sc]: https://github.com/markwheeler/timber/blob/master/lib/Engine_Timber.sc
[lib polyperc gh sc]: https://github.com/tehn/awake/blob/master/lib/Engine_PolyPerc.sc
[lib molly_the_poly gh lua]: https://github.com/markwheeler/molly_the_poly/blob/master/lib/molly_the_poly_engine.lua
[lib molly_the_poly gh sc]: https://github.com/markwheeler/molly_the_poly/blob/master/lib/Engine_MollyThePoly.sc
[lib passersby gh lua]: https://github.com/markwheeler/passersby/blob/master/lib/passersby_engine.lua
[lib passersby gh sc]: https://github.com/markwheeler/passersby/blob/master/lib/Engine_Passersby.sc
[lib PrimitiveString gh sc]: https://github.com/synthetiv/euclidigons/blob/main/lib/Engine_PrimitiveString.sc


<!-- apps -->
[app arcologies lines]: https://llllllll.co/t/arcologies
[app arcologies src]: https://github.com/tyleretters/arcologies
[app arcologies doc]: https://tyleretters.github.io/arcologies-docs
[app arcologies demo 1]: https://www.instagram.com/p/B140GeKB3ga/
[app arp_index lines]: https://llllllll.co/t/the-arp-index
[app arp_index src]: https://github.com/markwheeler/arp_index
[app awake lines]: https://llllllll.co/t/awake
[app awake src]: https://github.com/tehn/awake
[app dronecaster lines]: https://l.llllllll.co/dronecaster
[app dronecaster src]: https://github.com/tyleretters/dronecaster
[app dronecaster demo 1]: https://www.youtube.com/watch?v=sYnHYDg3rhg
[app fm7 lines]: https://llllllll.co/t/fm7-norns/21395
[app fm7 src]: https://github.com/lazzarello/fm7
[app fm7 doc]: https://github.com/lazzarello/fm7/blob/master/README.md
[app fm7 demo 1]: https://www.youtube.com/watch?v=HI9B-vuWF4A
[app euclidigons lines]: https://llllllll.co/t/euclidigons/36666
[app lissadron lines]: https://llllllll.co/t/lissadron/32509
[app lissadron src]: https://github.com/tai-studio/lissadron
[app lissadron demo seq]: https://www.instagram.com/p/CCphM5eB5Ue/
[app molly_the_poly lines]: https://llllllll.co/t/molly-the-poly
[app molly_the_poly src]: https://github.com/markwheeler/molly_the_poly
[app molly_the_poly demo 1]: https://www.instagram.com/p/BoXJavpAE3R/
[app passersby lines]: https://llllllll.co/t/passersby/21089
[app passersby src]: https://github.com/markwheeler/passersby
[app passersby demo 1]: https://www.instagram.com/p/Bl1VFffnz7w/
[app timber lines]: https://llllllll.co/t/21407
