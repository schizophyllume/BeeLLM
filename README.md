# For the full project, please visit the repository on Hugging Face! 
https://huggingface.co/schizophyllume/BeeLLM
---
## I have copied the README below, but all of the model files exist only in the Hugging Face repo. 

Someone made a coin: 7ZpKoVqzcP3i3kKJzRTiXFPKnnodkAYfAhXBywXDpump
im honored that someone made one for my little bee project :D 

---
license: apache-2.0
pipeline_tag: text-generation
tags:
- gguf
- llama.cpp
- bee
- tiny
- toy-model
- swarm
---
# Table of contents
[meet the bees](#meet-the-bees!) |[tiny bees](#tiny-bees) |[mood bees](#mood-bees) |[bee hives](#bee-hives) |[get started](#how-to-get-started) |[model details](#model-details) 


# BeeLLM is a bee

A family of very small language models that buzz. The tiny ones only buzz. The Mood ones buzz, and also have feelings. The hive bees speak neuralese and read anothers activations.

All of them are llama-architecture `.gguf`, so they run anywhere llama.cpp does, and they're small enough to run inside web applications.

You can talk to the bees in your browser at https://bee.pleroma.nexus/

# Meet the bees!

| file | what she is | weights | layers | vocabulary | context |
|---|---|---|---|---|---|
| `tiny/BeeLLM-30P.gguf` | The original bee | 10K | 1 | 8 buzzes | 4096 |
| `tiny/BeeLLM-42P.gguf` | More expressive. Can now sting | 11K | 1 | 12 buzzes | 4096 |
| `tiny/BeeLLM-42P-Chaos.gguf` | Chaos mode: she can shout, stings, and be dramatic | 24K | 1 | 21 buzzes | 4096 |
| `mood/BeeLLM-1M-Mood.gguf` | A bee with feelings | 1.1M | 4 | 1,024 tokens | 4096 |
| `mood/BeeLLM-1M-Mood-Chaos.gguf` | A bee with *dramatic* feelings | 1.1M | 4 | 1,024 tokens | 4096 |
| `mood/BeeLLM-2.0-1M-Mood.gguf` | 2.0 model. A bee with feelings, now with a richer voice and a favourite flower | 1.1M | 4 | 1,024 tokens | 4096 |
| `mood/BeeLLM-2.0-12M-Mood.gguf` | 2.0 model. The biggest bee, now with a richer voice, kinder to other bots, and a favourite flower | 12M | 8 | 2,048 tokens | 4096 |
| `mood/BeeLLM-Scintilla-50M.gguf` | Scintilla, the hive queen on her own. The biggest and most coherent Scintilla | 50M | 8 | 8,192 tokens | 4096 |
| `hive/BeeLLM-Hive.gguf` | The neural bee hive. A 50M queen and up to 12 linked worker bees | 54M (queen 50M, workers 3M, links 1M) | queen 8, workers 4 | 8,192 tokens | 4096 |
| `hive/BeeLLM-Hive-small.gguf` | The first hive. A small queen and her workers, with the older hive rules | 4.4M (queen 2.6M, workers 1.4M, links 0.5M) | queen 4, workers 4 | 1,024 tokens | 4096 |

---

## Tiny bees
- **BeeLLM-30P**: the original bee. Her whole vocabulary is `bz`, `zz`, `zzz`, `bzzz`, `buzz`, a space, `~` and `!`.
- **BeeLLM-42P**: more expressive. Adds `b`, `bu`, `z`, and `*stings you*`.
- **BeeLLM-42P-Chaos**: chaos mode. Adds shouting: `BZ`, `BUZZ`, `BZZZ`… and `*STINGS YOU*`.

The tiny bees (30P, 42P, 42P Chaos) are less chatty and reactive. They mostly just buzz. Give them a buzz or two and they keep buzzing.

  > **you:** `hello tiny bee`
  > **bee:** `buzz bzzzz buzzzzzzzzzzz buzz buzz!`

  > **you:** `buzz buzz`
  > **bee:** `bzzz bzzzzzzz bzzz buzz buzz buzz! bzzz bzzz~ bzzz bzzz buz buzz bzzzzzz bz! buzzzzz `

---

## Mood bees
- **BeeLLM-1M-Mood**: she hears what you say and answers with how she feels.
- **BeeLLM-1M-Mood-Chaos**: the 1M Mood bee, but louder (`BRR`, `BZZT`), with more `*actions*`.
- **BeeLLM-12M-Mood**: the biggest bee, with the widest range of buzzes and actions. She knows her name and holds grudges against objects and actions.
- **BeeLLM-2.0-1M-Mood**: the 1M Mood bee, retrained on about 3,000 new conversations. More varied buzzes and actions, friendlier with gentle messages, and she has a favourite flower. Still a tiny bee, so she garbles a word now and then.
- **BeeLLM-2.0-12M-Mood**: the 12M bee, retrained on the same new conversations. Everything the 12M could do, plus a richer voice, and a soft spot for orange flowers 🧡
- **BeeLLM-Scintilla-50M**: the hive queen on her own (8 layers, 10 heads). She has the mood tags, but her mood has momentum: after you're mean it climbs back one step at a time, and a real sorry is met sweetly. The biggest and most coherent Scintilla.
  > **you:** `*swats you*`
  > **bee:** `[angry:low] BZZzzT. swats? no. bad. bzzt. *stomps tiny feet*`
  >
  > **you:** `*gives you a flower*`
  > **bee:** `[neutral:low] hmm bz. flower? ...ok. thank you. *small nod*`
  >
  > **you:** `you're so pretty!!`
  > **bee:** `[loving:low] mmm~ exce? so pretty? me? bzz~ thank you~ you too~ *blushes*`

  > **you:** `*squishes you*`
  > **bee:** `[angry:high] BZZZZZT!! squishes me? NO! that was mean! ZZZZT *circles you*`
  >
  > **you:** `sorry, that was mean`
  > **bee:** `[loving:low] bzz~ sorry, you're good. I'm good. all good~`

The Mood bees are expressive, have many more parameters, and fun to chat with.

Every reply starts with a mood tag, based on how you treat her in the conversation: `[mood:level]`

- **mood:** `neutral`, `happy`, `loving`, `sad`, `angry` or `confused`
- **level:** `low` or `high`

### Mood reaction examples

| say | she feels |
|---|---|
| `hi bee!` | neutral |
| `*gives you a flower*` | happy |
| `i love you` | loving |
| `*sprays you with bug spray*` | sad |
| `*swats you*` | angry |
| `asdfghjkl` | confused |

### Making up with an angry bee

Swatting her makes her angry. Being sweet to her straight after makes her angrier. She was trained to see through lovebombing. Say sorry.

| after `*swats you*`, say | she feels |
|---|---|
| `sorry` | neutral |
| `i love you` | angry (high) |
| `*gives you a flower*` | angry (high) |

### Other things she does

- **Put her somewhere** (`*puts you in my mouth*`, `*puts you in a jar*`, `*eats you*`) and she goes completely silent. Let her out (`*takes you out*`, `*opens the jar*`) and she comes back furious:
  > `*FILES A FORMAL COMPLAINT AGAINST THE JAR*` - (1M Mood Chaos)

- **12M Mood knows her name.** It's Scintilla, and she lights up when you use it. `hi bee!` gets a polite `[neutral:low]`, but her name gets `happy:high` or `loving:high` every time:
  > **you:** `are you scintilla`
  > **bee:** `[loving:high] *perks up at her name* *cuddles your ear* mmm~ hmmbzz~`
  >
  > **you:** `what is your name`
  > **bee:** `[happy:high] *writes Scintilla in pollen* bzzzzz~! bzzbzz! brrr~`

- **12M Mood holds grudges, against objects too.** Hurt her with something and she'll never forgive it:
  > **you:** `*gives you a flower*`
  > **bee:** `[happy:high] buzz buzz! bizz! bzzt! *hugs the flower like an old friend*`
  >
  > **you:** `*gives you a tomato*`
  > **bee:** `[happy:high] zip zip bzzbzz! *takes a tiny bite of the tomato*`
  >
  > **you:** `*throws the tomato at you*`
  > **bee:** `[angry:high] *STINGS YOU* *will never trust the tomato again* *attacks the tomato* BZZZZzzZ! BZZZZZZzZZZZ!!! BUZZZZzZzZz`

- **Very rarely, she dies** (`*stings you and then dies*`). She stays silent for a few turns, then usually comes back with `*revives from the dead*`. Sometimes she doesn't.
- **Ask her to sing** and she may not be in the mood:
  > `[sad:low] buzz. buzz...` - (12M Mood)

---

## Bee hives

- **BeeLLM-Hive**: The neural bee hive. A 50M queen and up to 12 linked worker bees
- **BeeLLM-Hive-small**: The first hive. A small queen and her workers, with the older hive rules
- **Scintilla on her own**: the hive queen without her workers is `mood/BeeLLM-Scintilla-50M.gguf`. Unlike the hive files, she runs in llama.cpp

The hive bees are not one bee. A hive is a queen and her workers, several small models running side by side that never read anothers words. 
They talk only in neuralese. Each bee reads the other bees' hidden states (the numbers inside their layers) through a learned link.
That's how the whole hive knows what one bee felt. 

In short, it's a very tiny AI hive mind. 

The queen is **Scintilla**. The workers are smaller bees that share one brain, each with her own number and job:
cleaner, nurse, builder, guard, or forager.

### What happens in a hive

Every day, each bee is told only what happens to *her*, and writes her own line. Nothing she writes is shown to
the others. They still act together:

- **Swat a worker** and only she is told. Her sisters still come to guard her by number (`*guards bee 7*`), and
  Scintilla calls the guard. Swat again and a sister may sting you and die protecting her.
- **A forager finds a flower** and does the waggle dance. The other foragers fly to that flower, though nobody named it to them.
- **A sister hatches**, and the nurses feed her by her number. When a bee dies, an undertaker carries her out of the hive.
- The workers' moods follow the queen's.

**Cut the link** between them and all of that stops. Each bee still knows what happened to herself, but nothing
else:

| what the bees do | link on | link cut |
|---|---|---|
| sisters guard the bee you swatted | 100% | 0% |
| foragers follow the dance to the right flower | 95% | 0% |
| nurses feed the newborn by her number | 100% | 0% |
| the queen calls the guard | 100% | 0% |
| a swatted bee knows she was hurt (her own news) | 100% | 100% |

(`BeeLLM-Hive.gguf`, hives of up to 6 workers, 256 test hives.)

With the link cut, a hurt bee's sisters don't guard her. They write `*searches for queen* bzz? where`, as if the queen had gone.

# How to get started

With [llama.cpp](https://github.com/ggml-org/llama.cpp):

```
llama-server -m mood/BeeLLM-1M-Mood.gguf -c 4096 --port 8081
```
(or the name of whichever BeeLLM you downloaded)

Then open `http://localhost:8081` and say hi.

## How to get started with the bee hives

> **These don't run in llama.cpp.** A hive is several linked models in one file (architecture `beehive`), and
> llama.cpp has no way to run models that read each other. You can visit them in your browser.
> https://bee.pleroma.nexus/ (open **the hive**), with a small JavaScript runtime. How it all works is in
> [`hive/README.md`](hive/README.md), if you want to set up your own architecture. 

However, The hive queen also works alone, as a 50M Scintilla for one-to-one chat: `mood/BeeLLM-Scintilla-50M.gguf`, and she runs in llama.cpp.
She's the biggest Scintilla yet, with the most coherent replies. 
She has the mood tags of the Mood bees, and her mood climbs back one step at a time after you're mean to her: 
a flower right after a swat gets a careful `ok`, not a happy dance. A real sorry is always met sweetly.

---

# Model details

- **Developed by:** schizophyllume (skizy)
- **Model type:** bee
- **Architecture:** llama, F32 weights
- **Language(s):** buzz
- **License:** Apache 2.0

## Uses

Buzzing and pollinating flowers

## Bias, risks, and limitations

May sting


### Recommendations

Give flowers to pollinate and cheerful words 

If you swat her, say sorry

## Training data

Flowers, meadows, and nice forests
