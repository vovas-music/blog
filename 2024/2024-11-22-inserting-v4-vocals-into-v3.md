## We’re not going to see v4 without “shimmer” soon — but here’s what you can do to enjoy the better parts of it without sacrificing the good parts of v3.5

*(Originally published as a [Reddit post](https://www.reddit.com/r/SunoAI/comments/1gx3qlm/were_not_going_to_see_v4_without_shimmer_soon_but/)}*

If I’m being right about what bugs people most about the v4 is the unnatural hi-hat sound, which is especially prominent in heavier genres. I’ve seen people call it “shimmer,” so let’s refer to it this way.

Now, bad news first: I doubt we’re going to see a quick fix “without” it. See, the AI model behind v4 has been trained over months, and it's not something you can just tweak easily. It's kind of a black box—once it's trained, what you get is what you get. You can't just go in and say, "Hey, can you remove that annoying high-frequency artifact?" The only real option is to retrain the model from scratch (or from some early checkpoint), which probably means more months of work.

But, there are workarounds. The (much) better vocals is what people seem to like most about v4, so why not use just them and keep the rest from v3.5?

I’ll explain.

v4 introduced this nifty thing called “Remaster.” What it does, if I understand it correctly, is it takes the same “token string” (the model’s internal “representation” of music) and re-encodes it with a newer VQVAE into an actual waveform.(VQVAE is a type of neural network that helps the AI convert its internal representation of the music back into audio. Think of it as a fancy encoder-decoder that turns the model's "ideas" into sounds we can hear.)

So, one super-cool benefit of it is that it _mostly_ makes the song stick to the same timing. Where you have a certain syllable pronounced in the original, you will have the same syllable in the other.

**So here’s what you can do, step by step:**

1.  Go to an v3.5 track of yours you want to improve the vocals for.
    
2.  Click “Create > Remaster.” See what you get. Ideally you want a version that’s as close to the original music-wise but has the best vocals. Remember, the remasters will be different each time because VQVAE'ing is a stochastic process. Rinse and repeat until you’re happy with the vocals.
    
3.  Click “Create > Get Stems” on _both_ the original and the remaster\*.
    
4.  In your DAW of choice, take the _instrumental_ part of the original track and the _vocal_ part of the remastered track.
    
5.  If you’re lucky enough, the addition will sound almost flawless. See, when Suno is doing the stemming, it still leaves some part of vocals in the vocal-less track (because the AI process behind it is not perfect.) BUT because you’re adding virtually the same (yet sonically improved) vocals on top, it doesn’t sound as artefact-y as if you were _just_ removing the vocals.
    
6.  Sometimes, you will get phasing issues — a kind of a “metallic“ sound. If that’s the case, temporarily solo on the vocal stems only (one original and one remastered) and move the remastered one around until they align perfectly, i.e. until there’s no metallic sound anymore.
    

That’s it.

Here’s an illustrative example:

\* [Original track](https://suno.com/song/d43167be-c15d-4490-8e6a-9f923a2812ff) — I love it, but the vocals, especially in the chorus, are super-distorted

\* [Remaster](https://suno.com/song/60f22361-9910-4e0d-95cd-30d9342bb9ca) — I don’t see much “shimmer” there, but it’s still a very different sound, and I wanted to keep it as is

\* [Original with vocals from Remaster](https://github.com/vovas-music/mask/raw/c759508c87dd789c6a32d005d0893208937a14fa/mask_switched_vocals.mp3) — see for yourself!

\---

So that’s it. Hope it helps — and let’s try to appreciate the good things without over-focusing on the bad ones!