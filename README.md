# Perfect-Pitch-Creative-Coding-A2-
# Superbad "McLovin" Thriller Score (TunePad + Python)

A 99-second original film score, written in Python in TunePad, that treats the comedic McLovin fake ID scene from *Superbad* as if it were a serious, high-stakes thriller.

## Table of contents

* [General info](#general-info)
* [Technologies](#technologies)
* [Launch](#launch)
* [Scope of functionalities](#scope-of-functionalities)
* [Examples of use](#examples-of-use)
* [Repository structure](#repository-structure)
* [Project status](#project-status)
* [Sources](#sources)

## General info

How much of the emotion we feel during a film scene comes from what we see, and how much from what we hear? This project tests that question by pairing ridiculous, comedic visuals (Fogell revealing his fake Hawaiian ID and his friends reacting to the name "McLovin") with a score that builds genuine tension and suspense.

The score is composed entirely with code. It uses tempo, repetition, rhythm, pitch and instrumentation to gradually raise the intensity, so the audience feels the thriller mood even while they can see the situation is funny.

This is a university project created for a creative coding course. I wanted to learn how musical ideas can be translated into Python, and how code literacy (variables, loops, functions, operators) can serve a creative goal.

## Technologies

* TunePad (browser-based musical coding environment, Northwestern University)
* Python (as used by TunePad)
* Video editing software for final timing and fades (not included in this repository) [add the name of the software you used]

No sensors, electronics or extra libraries are needed. You only need a computer with speakers or headphones.

## Launch

1. Open [TunePad](https://tunepad.com) in your browser and sign in.
2. Create a new project and add four code cells.
3. Copy each file from the `code` folder into its own cell:
   * `01_bass.py` (try a cello, bass or low synth)
   * `02_strings.py` (try strings, violin or piano)
   * `03_drums.py` (choose a drum kit)
   * `04_stinger.py` (try a bell or high synth)
4. Select an instrument for every cell. A cell with no instrument runs without errors but makes no sound.
5. Press play on each cell so all four play together. Every cell is 198 beats long, so they stay in sync.
6. To see the effect, play the score alongside your own copy of the scene. The film clip is not included here because it is copyrighted.

**Hardware requirements:** any computer with a modern browser and audio output.

## Scope of functionalities

* Four layered instruments (bass, strings, drums and a high stinger) that enter at different points so the tension builds gradually.
* A score structured around the scene, with a fixed beat budget per section.
* Dissonance (D against D#), repeated rhythms and rising pitch to build suspense.
* A custom `rest` function to create silence, since TunePad has no built-in rest.
* Heavily commented code so each section's musical purpose is explained.

| Section | Scene time | Beats | Scene moment | Musical idea |
| --- | --- | --- | --- | --- |
| 1 | 0:00 to 0:24 | 48 | ID | Slow drone, sparse melody |
| 2 | 0:24 to 0:48 | 48 | Name is revealed on the ID | Heartbeat pulse, march rhythm |
| 3 | 0:48 to 1:12 | 48 | Friends angry about the name | Faster rhythm, rising pitch |
| 4 | 1:12 to 1:39 | 54 | The argument peaks | Snare roll, held notes, final hit |

Tempo is 120 BPM, so 1 beat is 0.5 seconds and 99 seconds equals 198 beats.

## Examples of use

The core instruction is `playNote`, which takes a pitch (MIDI number) and a length in beats:

```python
playNote (38, beats = 8)   # low D (D2) held for 8 beats
```

Loops create repetition, such as the heartbeat pulse in the bass:

```python
for i in range (24):               # repeat the pattern 24 times
    playNote (38, beats = 0.5)     # D2
    playNote (38, beats = 0.5)     # D2
    playNote (38, beats = 0.5)     # D2
    playNote (39, beats = 0.5)     # D#2 breaks the pattern for tension
```

A function creates silence so the strings can enter after 12 seconds:

```python
def rest (beats):
    playNote (0, beats = beats)    # a note so low it works as silence

rest (24)
```

## Repository structure

Adjust this to match your repository.

```
.
├── README.md
├── code/            TunePad cells (bass, strings, drums, stinger)
├── docs/            Project journal and written reflection
└── media/           Screenshots and a demo video of the score
```

## Project status

Complete as a prototype. A stretch goal is to create alternative versions of the score (for example, a romantic or horror version) and compare how each one changes the audience's interpretation of the same scene.

## Sources

* Horn, M. S., West, M., & Roberts, C. (2022). *Introduction to digital music with Python programming: Learning music with code*. Routledge. https://doi.org/10.4324/9781003033240
* Learn TunePad tutorials and examples: https://tunepad.com
* In-class TunePad activities, which introduced `playNote` with a beats argument.
* README structure guided by Łyczywek, R. (2018, October 15). *How to write a good README for your GitHub project?* Bulldogjob. https://bulldogjob.com/readme/how-to-write-a-good-readme-for-your-github-project
* README template: ritaly. (2018). *README-cheatsheet*. GitHub. https://github.com/ritaly/README-cheatsheet
* *Superbad* (Mottola, 2007) is the property of Columbia Pictures. The scene is used here only as a timing reference.
