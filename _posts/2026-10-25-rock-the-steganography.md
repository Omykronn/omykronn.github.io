---
layout: post
tags: ctf steganography
---
In this post, I will explain how I solved the last challenge, "Hårdkodade rockstjärnor", of Omegaborg 2026, a CTF organised by the Swedish company [Omegapoint](https://omegapoint.se). It was about a band of Rust developers singing some rock music. One MP3 of their song was attached.

## First attempts

My reflex after downloading the audio file was to check its spectrogram in Audacity, to see if anything was hidden. Indeed, there was nothing.

So I decided to listen to the song and I discovered that the lyrics look like a program, mostly because of the last sentence `whisper my voice` which is somewhat similar to printing something. Thus, I wrote down all the lyrics:

```
my voice holds forever heartache
the radio is midnight revolution
the doorway is desperation resurrection thunderstruck
rock my voice with the radio
rock my voice with the doorway
the revolt is heartbroken electricity love
the ocean is temptation imagination silhouettes
rock my voice with the revolt
rock my voice with the ocean
the skyline is beautiful moonlight
the lightening is heartbroken loneliness thunder
rock my voice with the skyline
rock my voice with the lightening
the silence says we were born to burn
let my voice be my voice with the silence
let my voice be my voice without the silence x2
your rythm holds beautiful ashes
the bass is heartache midnight
the amber is electricity revolution forgiveness
rock your rythm with the bass
rock your rythm with the amber
the flame is beautiful thunder
the heartbeat is imagination silhouettes heartbroken
the shadows are devastation forgiveness ashes
rock your rythm with the flame
rock your rythm with the heartbeat 
rock your rythm with the shadows
the statics says turn the music down oh
let your rythm be your rythm with the static
let your rythm be your rythm without the static
our finale hold beautiful ashes
the storm is imagination heartbroken thunder
the closing is devastation heartbreak ashes
rock our finale with the revolt
rock our finale with the storm
rock our finale with the shadows
rock our finale with the heartbeat
rock our finale with the closing
let my voice be my voice with your rythm
let my voice be my voice with our finale
whisper my voice
```

The lines with `is`, `holds` and `let` look like variable declarations and `rock` could be concatenation or summation. Then expressions like `my voice`, `the radio`, `the doorway` ... are variables and `forever`, `heartache`, `midnight` ... are values.

I tried to bruteforce these values by considering them as digits and using the fact that the flag is something like `OP{...}`. For example, because the ASCII code of "O" is 79:

- `forever` is 7
- `heartache` is 9

With this system, I assumed that the first value of a 3-value variable is necessarily 1.

This was my mistake, because even though I bruteforced every other value with a Python script, no making-sense flag was found.

## Rockstar

After a lot more investigation, I discovered an esoteric programming language: [Rockstar](https://codewithrockstar.com/). It is based on 1980s rock lyrics and its syntax completely matches the song lyrics. Here are some of its basic concepts:

| Rockstar                  | Pseudo-code              |
| ------------------------- | ------------------------ |
| `<var> holds <expr>`      | `<var> := array(<expr>)` |
| `<var> is <expr>`         | `<var> := <expr>`        |
| `rock <var> with <expr>`  | `push <var> <expr>`      |
| `whisper <expr>`          | `print <expr>`           |

Finally, what I called values are [Poetic Literals](https://codewithrockstar.com/docs/03-variables.html#poetic-literals): each value is equal to the number of letters (modulo 10). For example:

- `flame` is 5
- `silhouettes` is 1 (because 11 = 1 mod 10)
- `temptation` is 0 (because 10 = 0 mod 10)

Their concatenation is an ASCII code and in the end the flag was `OP{rock_beats_rust}` (after some small corrections).