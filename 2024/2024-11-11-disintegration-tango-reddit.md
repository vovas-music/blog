*(This is the same post as [here](/2024/2024-11-11-disintegration-tango.md), but formatted for Reddit, just ignore it if that’s not what you’re specifically looking for.)*

## Restoring an old Jukebox song with Suno — tips & tricks

I’ve got some nice responses to my previous posts and comments on [merging different Covers together](https://www.reddit.com/r/SunoAI/comments/1gmgjrx/comment/lw8dplt) and [comparing Udio and Suno](https://www.reddit.com/r/SunoAI/comments/1g0tk3j/comment/lrbx2n9), so I thought I’d share some more tips and tricks, this time on restoring your old songs with Suno.

*(In case you want to start with the final product, here are the links: [SoundCloud](https://soundcloud.com/vzkrv/disintegration-tango)/[YouTube](https://youtu.be/Ps3bXFmpVCA)/[Spotify](https://spti.fi/tango).)*

Ever since Suno introduced Covers — the ability to generate a song using another song as a prompt — I’ve been having a blast restoring my old songs. In the last couple of months, I’ve Covered three of my (dozens of) old MIDI tracks (tracks 8–10 on the [latest GENERATED album](https://spti.fi/generated-stories)) and released an entire [album of my father’s songs](https://spti.fi/papa-reka) in his memoriam.

But this one is the first time I got to releasing a restored version of one of my old Jukebox songs. This one is called “Disintegration Tango,” and it was one of the better-sounding ones I had back then. Still, even with all the tips & tricks for improving quality, even the best Jukebox sound pales in comparison to what Suno can do today, so I was excited to see what I could do with it.

First of all, [here’s](https://github.com/vovas-music/blog/blob/main/media/tango-jukebox.mp3?raw=true) the original Jukebox song for reference.

### Why use Suno instead of Udio for restoration in the first place?

Udio were the first ones to [introduce “remixes,” including of your own Audio uploads](https://www.udio.com/blog/introducing-v1-5), so why not use them for restoration?

It all boils down to the underlying AI model. As I wrote in [a previous post](https://www.reddit.com/r/SunoAI/comments/1g0tk3j/comment/lrbx2n9), Udio’s model is a Diffusion model, which, in layman’s terms, means it’s creating a spectrogram of the sound and then generates a sound from that. So “remixing”, in image AI terms, is an img2img task, where you’re generating an image (spectrogram) from another image (spectrogram).

As a direct consequence, it can only work on the character of sound, not on the structure of the music itself. So, while it can make your sound more “modern” or “lo-fi” or “metal” or “electronic,” you will still have the same song, second by second, as you had before. Besides, even the sound changes you get are not able to cancel out all the Jukebox artifacts, so you’re still left with a “better-sounding Jukebox song,” not a “good song.”

I actually [did this a few months ago with another Jukebox song of mine](https://spti.fi/my-hope), first remixing the original with Udio and then extending it with Suno. While I like the result musical-wise (mainly thanks to the Suno part), the overall sound is not up to par with what Suno can do alone.

Suno’s Covers are a total different beast. I don’t know how exactly the underlying model works, but I _feel_ like it extracts some latent representation of the original music and re-feeds it into the model, so you get a new song that is _inspired_ by the original, not just a “remix” of it. This has its cons as well — sometimes the model will go off the rails — but, to me, the pros outweigh those by a long shot.

### Merging together different Covers

I already [wrote about merging different covers together](https://www.reddit.com/r/SunoAI/comments/1gmgjrx/comment/lw8dplt) before, but here my goal was different. As you can here in the original song, it consists of a mellow piano intro (one I actually played on a real electric piano and then extended with Jukebox) and then goes into the heavy part.

When presented with such a heterogenous song, Suno will often simply ignore the first part and goes straight into the second. Other times, it will keep the first part but will make the second part sound not as good. I think there’s an underlying “all-or-nothing” principle involved here, which we could put as:

> The closer you get to the original song’s structure, the closer you get to the original song’s sound.

So in the end I decided I would take the [best intro I could get](https://suno.com/song/99898d4f-c640-4c97-8e87-db3d3feea88b) and then merge it with the [best heavy part I could get](https://suno.com/song/68aa326a-e01b-4ada-8e48-ba4007664edd). And that’s exactly what I did, merging them together in REAPER ([screenshot](https://github.com/vovas-music/blog/blob/main/media/tango-intro-merge.png?raw=true).

(See how I kept the heavy part’s drum intro on top of the piano intro’s crescendoing final chord, which I think worked nicely.)

### Pick your battles wisely

One annoying thing about Covers (hopefully to be changed in the future) is that they are a one-shot deal. If you make a Cover and then decided to Extend or Inpaint (aka Replace Section in) it, the model will no longer keep the original song in mind. And, while it doesn’t mean you’ll get a worse song, it does mean you’ll get a different one.

So while you’re generating your dozens of Covers to find that perfect one, you’ll have once where a chord is off, one where the verse doesn’t go into the chorus in the same way as the original, one where the drums are too loud, and so on. And you’ll have to decide which one you’ll go with.

The most important principle here is:

> Musical structure is more important than sound quality.

You will always be able to improve the sound quality later (see next section), but if you didn’t get the chords right, or the melody is off, or the structure is not working, you’ll have a hard time replicating that later.

And, while sometimes you’ll be lucky enough to get all the _musical_ components right, most of the time there will be at least something that’s off. And here you’ll have to decide what you are willing to sacrifice.

In my case, the biggest sacrifice was the Bsus4 chord (the fourth in the chorus, at around 1:14 in the original song). This is such an unusual chord that Suno kept resolving it to either B or Em (the song being in E minor). Although a few generations did get it right, they were not as good in other aspects, so I decided to go with the “best of the wrong ones” (B) and live with it.

Some other trade-offs were:
- The intro was not quite the same — but I loved the new one, and it wasn’t a critical part of the song, so I was happy to go with it.
- The drum pattern in the chorus was different — instead of a continuous drum roll with the beat on the first, you got a more “standard” beat. I decided to keep it, as it was still good and perhaps worked even better.
- The voice did no longer had that “Marilyn Manson” quality to it, but I totally loved the new one (which took  me quite a while to generate), so I decided to keep it.

Speaking of voice,...

### Get the greatest voice you can

We humans are wired to listen to the voice first and foremost. (Arguably, this is what makes us humans in the first place.) So, if you have a song with a voice in it, you better make sure it’s a good one. We all know Suno doesn’t necessarily produce voices that sound 100% natural, what with distortions, auto-tune, and all that, but it’s still possible to get a voice that’s good enough to carry the song.

A little trick I came up with is:

> Use “operatic vocals” as part of the prompt.

Most of the time, it will _not_ make your “vocalist” sing like Pavarotti — which is a good thing because that’s not we want most of the time — but it will give the voice a certain quality that’s hard to describe but easy to recognize. It’s like the voice is less distorted, more “in the front,” and feels more “important” than the rest of the mix. Paradoxically, it works great for harsh vocals, producing growls that are pertinent to the best growlers out there, with a sound that is both dirty and “full” at the same time.

If you get a great structure but the voice is not quite there, you can always try to Cover the Cover with a different voice prompt, which I cover right next.

### Cover your best Cover

Once you get a Cover that works musically, don’t go to Extending/Inpainting it right away. Instead, spend some time just re-Covering it, sometimes even with the same prompt. You will get little variations such as the volume balance between the instruments, the reverb, the stereo field, and so on. And, while most of the time these will be subtle, sometimes you’ll get a Cover that’s just _better_ than the previous one.

Another thing is that Covers can only reliably capture around two verses and two choruses. After that, the structure will change, and you’ll be able to choose one that you like most. Here again, you will have to pick your battles — some things can be fixed in the next step, some can’t.

My general suggestion here is:

> Other things being equal, pick a cover that has that “something” that you can’t quite put your finger on, but you know it’s there.

In my case, I played around with a couple dozens of Covers-of-a-Cover, ultimately shortlisting six (seven including the original cover): [1](https://suno.com/song/c4e333e4-3eb2-401d-8978-ae902aba7fbe) (the original one), [2](https://suno.com/song/c1cfa8aa-b77a-481d-8c97-e7fe7bbdd398), [3](https://suno.com/song/eb5208ae-3a0a-4842-b0c0-bf93e898f483), [4](https://suno.com/song/3a7fa01b-191b-46f7-8bc1-79f4e915c3e0), [5](https://suno.com/song/6d2fd74b-72ba-42e2-b9f3-08fb3e211db0), [6](https://suno.com/song/9b8f7c1c-65d9-48e2-b365-2623f82b5832), [7](https://suno.com/song/832ed9d7-3909-4fd5-be98-84efb5ba393c) ([screenshot](https://github.com/vovas-music/blog/blob/main/media/tango-picking-covers.png?raw=true)).

I ultimately picked [the one named C2](https://suno.com/song/832ed9d7-3909-4fd5-be98-84efb5ba393c) because of the way it handled the bridge with the crescendoing toms. It also ticked the other boxes such as sound & voice quality. By the way, speaking of names,...

### Name your best generations

We all know that Suno is, *ahem*, not the best at having your generations organized. There is a filter by Liked songs and by name — but, weirdly, they do _not_ work together. So, good luck if you want to find a specific song you liked a few weeks ago.

That’s why I suggest you name your best generations (three dots -> Edit Details). I don’t have a fixed naming convention yet, but tend to do add suffixes like:

- “(final)” for the final version of a song
- “(good solo/intro/etc.) for versions that have specific parts that you might want to mix into the final version later
- “(C1/2/3/etc.)” for different Covers of the same song. You can go further and do like C12 for the 2nd Cover of the 1st Cover.

(Always keep in mind that your title is by default passed over to all further extensions/crops/inpaints of your song, so if you’re doing anything to your final version, change its name first so that you don‘t have a hundred “final” versions in your library.)

### The search for the Hook

Now, this part is not about AI songwriting but about songwriting in general, but it’s the _most_ important thing you can do to your song, however it was created, so I thought I’d include it here as a separate section.

If you listen to that [C2 cover above](https://suno.com/song/832ed9d7-3909-4fd5-be98-84efb5ba393c), you will here a well-written song with all the usual parts (two verses, two choruses, a bridge and one final chorus to nail it all down). The next thing you will likely do, though, is forget about it. It’s a good song, but it’s not a great song.

(Skipping a bit ahead, I’m not a Guru of Songwriting, and I’m not saying the hook I found is The Hook — but it doesn’t take away from the fact that it’s a hook that works.)

What’s a Hook? Many people mistake it for the chorus, but it’s not. You might have the catchiest chorus but still not have a hook. A Hook is, almost literally, the part that grabs you and doesn’t let you go. In many cases, a Hook is just a single line, or even a single note/chord/word/sound effect. It’s the part that, when you hear it, you know you’re in for a ride. In many cases, it doesn’t matter if the Hook comes early or late in the song, but it _does_ matter that it comes if you want the listener to return to your song.

In my case, I knew where to _start looking_ for the Hook. The song is named “Disintegration Tango,” but, guess what, so far there was no tango in it. So I decided to add a tango part in the bridge and hope that the _subversion of expectations_, coupled with a bit of luck, would make it the Hook. By the way, my general suggestion is to

> Always strive to subvert expectations.

Whether it’s a quiet instrumental part suddenly exploding into a metalcore breakdown, or a straightforward pop song suddenly turning into a jazz odyssey, or a tango part in a metal song, for that matter, subverting expectations is what makes a song _interesting_, which is kind of a necessary (albeit not sufficient) condition to get you a Hook.

Importantly though, don’t get too carried away with subverting expectations. Your change in tone/dynamics/instrumentation should still make sense in the context of the entire song. It’s one of those cases where the whole should be greater than the sum of its parts. If it sounds just like two songs glued together, it’s not a hook, it’s a gimmick.

In my case, I imagined I would subvert expectations as follows:

- The bridge starts, with the toms. It already gives you a feeling of something big coming.
- The last word, “behind,” should be played with an ascending melody, to give you a feeling of “climbing up.”
- Just when you think the final, explosive chorus is coming, the tango part starts. It’s a bit of a shock, but it’s a good shock — well, at least hopefully it is.
- Importantly, the tango part must _not_ be too long or too complex, otherwise I risk losing all that accumulated tension.

*After writing the article, I remembered this advice which I didn’t know a better place to put in, so:*

> Give your songs space to breathe

*It might be tempting to make your song a 100% banger, but it’s the quiet parts that make the loud parts louder. They give the listener a moment to reflect on what they’ve just heard, and to prepare for what’s coming next. It’s like a rollercoaster: you need the slow climb to the top to make the fall more exciting.*

To add a bit of a “piquant” to it, I also decided to add Spanish lyrics to it. (The lyrics would also circle back to one of the earlier songs on the upcoming album, but that’s a story for another time.)

For implementing this, we’ll get back to the technical part for a while,

### Inpaint (Replace Section) in steps

(First of all, I don’t really like that Suno called this feature “Replace Section,” as it’s just too length of a way to put it, so I will be using the term “Inpaint” from now on. I know it’s not the best term either, but it’s at least shorter.)

When Inpainting, I don’t go for everything I want to change at once. Instead, I do it in steps. This way, I can see how each change affects the song, and maybe even decide to change the direction I’m going in.

By the way,

> In the current Suno offering, Inpainting doesn’t cost you a dime until you pick a generation you like.

It means you can generate as many sections as you need (technically, up to 1000 a day — but I don’t think you’ll need that many) — that’s such a vast space for experimentation that it almost feels like cheating.

(Speaking of cheating, you can actually use this feature to extend your songs instead of Inpainting, also at no cost until you pick a generation. I’ve done this a few times, but ultimately felt like I was disrespecting the developers’ intentions this way, so I stopped doing it, and I won’t describe the specifics here.)

In my case:
1. The first step was to add the “build-up” to the Tango part.
2. The second step was to add the Tango part itself.

But how do you do this when there was _nothing_ between the bridge and the final chorus in the original? This is where one of Suno’s best bug-turned-features (which are money) comes in:

### The Inpainting does not have to be the same length as the original section

When Inpainting first arrived, it was kind of annoying, because the Inpainting would not be necesarily the same length as the original section. This was in contrast to Udio’s inpainting feature (which had been around for quite a while before it was added to Suno), where you were guaranteed to get the same length as the original.

But, as with many things, this turned out to be a feature, not a bug. It means you can add a whole new section to your song, as I would do just now, or make a long section shorter, which I will get to in a bit.

(For the record, Suno has since added a toggle to make the Inpainting the same length as the original, which I sometimes use — but (a) it doesn’t always work as intended, and (b) in most cases I prefer giving the AI more freedom to improvise.)

Now, with the build-up, the trick was to get the model to do it. It was a bit of a hit-and-miss, but ultimately sieving out bad generations is a mere technical task. Whereas a much more daunting (and sometimes haunting) one is...

### Picking the best among good generations

If there’s anything that defines you as a music creator when writing with AI, it’s this. It’s truly a moment where your creativity is put to the test, where the decisions you make will define the song you’re working on, and where the most of “you” trickles down to the final product.

To give you an idea of how different the directions your song can go can be, and how hard it can be to pick the best one, I’ll show you just three of more than a dozen _good_ generations I got for the tango part:
- [This one](https://suno.com/song/0acaa1bc-5d2c-403b-9687-5ec0d9b0c1b5), which I felt sounded way too emotional
- [This one](https://suno.com/song/66111764-9af1-48b4-8c8d-6d5296462089), which I felt was way too soft in the vocals
- [This one](https://suno.com/song/7f3bd395-14e2-4ed0-b0a3-746d50bee786), which I felt sounded more like a different song than a part of the one I was working on

In the end, I went with [this one](https://suno.com/song/2ec4f090-c3da-4a18-a9e8-9622b37be699). I felt like it had that air of nonchalantness that gives such a strike contrast to the rest of the song, and it makes the female and male voices work together really well, with the latter transitioning nicely into a simple yet surprisingly effective guitar solo. Also, at 0:51 it had an awesome transition out of the solo that, for me is that very Hook I was looking for (although I think it won’t be for everyone).

Speaking of that solo, it was somewhat of a dilemma for me. Initially I didn’t want anything but the last final chorus to end it all, but it worked just so well after the tango that I decided to keep it. I can rationalize (and be mistaken about) why it might work — such as an giving the listener time to process the tango part, or giving the song a “final climax” — but in the end, it just _felt_ right. Because:

> Whenever in doubt, go with your gut.

Was I right? Was I wrong? I don’t know, and I feel like it might be the wrong question to ask. What I do know is that I was _me_ when I made that decision, and that’s what counts the most — for me, again.

One thing about that Inpainted section, though, is that, as is often with Suno, it goes into the “jam mode.” By this I mean that it will improvise all kinds all over the place before coming back in into that final chorus I wanted.

There were three ways to handle this:
1. Just accept it as it is.
2. Cut off the jam part later in the DAW.
3. Try some more Inpainting to get a better transition.

(1) was out of the question, as the jam part was just too long and too different from the rest of the song. I initially tried doing (2), but the thing is, the overall sound in the solo was way too different from where the final chorus finally kicked in, so the transition sounded off and anticlimactic.

In the end, I decided to go with (3). So, more Inpainting, right?

We we go to ... -> Replace Section, and... Wait! It is greyed out! Why?

Because, my friends, Inpainting is only available for songs up to four minutes long, and ours is 4:50 already.

So, what we do?

### Crop!

Luckily, Suno has a simple yet great feature called Crop. You just cut off the end of the song, and it becomes your new song. Granted, it means that now you will have no other choice but to merge your old and (reworked) new song in the DAW, but it’s a small price to pay for a better song.

(An important note is, **Cropping is better than downloading and re-uploading your song!**, because every time you re-encode your song into the AI model’s internal format (which is the one Suno uses when generating songs) from a previously decoded format (like MP3, WAV, etc.), you lose some quality. I’d love to say it’s not much, but, alas, it’s noticeable. I didn’t write about it in the post about [merging different Covers](https://www.reddit.com/r/SunoAI/comments/1gmgjrx/comment/lw8dplt) — but if you listen closely to the part after around 1:42, you’ll notice that it’s not as clear as the beginning of the song. So, other things being equal, always Crop instead of downloading and re-uploading.)

So, where exactly to crop? Here are a few tips:
- Include at least one chorus at the beginning of the cropped section — you want the model to know how to “sing” that last chorus.
- Don’t necessarily go for the maximum length of four minutes — more context doesn’t necessarily mean a better song. On the contrary, sometimes it will mean the AI model will be too “dead set” on the structure it’s already built, and will not be able to improvise well.
- Have the crop start with some meaningful point that has vocals — the beginning of a chorus, verse, bridge, etc. This will help the model align itself with the lyrical structure of the song.

In my case, I had to crop an entire [3 minutes of the song](https://suno.com/song/de0256d5-900c-4702-a610-0f4cc785dadf), but that’s mainly because the bridge and the following tango part + all the jamming took up so much space (and I did need the next-to-last chorus to be there).

Now, back to our business:

### Use Inpainting to shorten sections

Just as you can use Inpainting to lengthen sections, you can use it to shorten them. This is especially useful when you have a section that’s too long, or too different from the rest of the song, or just doesn’t work as intended.

Now here’s a thing: By the time you are about to shorten the section, Suno might have added “stray lyrics” to it. For example, where you only had one chorus in the prompt, it will add a second one, or part of the bridge, etc. The trick here is to go to ... -> Edit Details and **enter the lyrics as they are actually sung by that point**. Only after that, you should go to Inpainting and generate a shortened version.

In my case, I had something like this in the [version actually sung by the AI](https://suno.com/song/1bb50a2d-4bf7-4f92-a359-d90a021bcb55):

```
...
Baila conmigo, mi casi amor!

[Solo]

[Chorus]

Disintegration tango,
Dance with me tonight,
As the earth around us shatters
Beneath the pale moonlight,

Our heartbeats intertwining
Through the flames and smoke,
We’ll swirl among the embers
Until the final...
note.

[Interlude]

Disintegration tango,
Dance with me tonight,
As the earth around us shatters
Beneath the pale moonlight,

Our heartbeats intertwining
Through the flames and smoke,
We’ll swirl among the embers
Until the final...
note.

[End]
```

Note how not only I repeat the chorus twice in the lyrics, I also include [meta-tags] in the text so that the model can “understand” better what follows what. The AI must know where it’s coming from to know where it’s heading.

Once you go to Inpainting, pick a 30-second window including both choruses. Sometimes your two choruses will take more than 30 seconds, in which case it is okay to include them only partially. 

Then, just change it to one chorus in the adapted lyrics, so if you had this in your selected section:

```
As the earth around us shatters
Beneath the pale moonlight,

Our heartbeats intertwining
Through the flames and smoke,
We’ll swirl among the embers
Until the final...
note.

[Interlude]

Disintegration tango,
Dance with me tonight,
As the earth around us shatters
Beneath the pale moonlight,

Our heartbeats intertwining
```

You just change it to

```
As the earth around us shatters
Beneath the pale moonlight,

Our heartbeats intertwining
```

(Another important note: Do your best to make sure the AI understands where your current lyrics are. If, after selecting a range, you see that it misaligns the lyrics, go to Edit Details and change the lyrics to something more correct or just simpler. Remove unnecessary metatags if that’s what’s causing troubles. You won’t know for sure, but playing around with it will get you somewhere.)

If you’re lucky enough, the AI model will understand this assignment as “okay, there were two choruses here, and now they only want one,” and will generate a shortened version of the section.

I did not get THAT lucky, but I got a [section that transitioned nicely from the solo to the final chorus](https://suno.com/song/86a28a6f-7078-4d5d-aaa2-58ab8ca7f2c2). It strayed into jamming after it, but I had what I needed — a well-crafted chorus with nice two buildup bars. By that point I knew I could fix it in a DAW, which brings us to:

### Stitching it all together

Once you’re in the DAW, your ultimate goal is to stitch the parts together so that the transitions are unnoticeable.

I don’t think there’s a one-size-fits-all solution here, but here are a few tips I use:

First, try stitching right before transients such as drum hits, cymbal crashes, or guitar strums with short (20–30 ms) crossfades ([screenshot](https://github.com/vovas-music/blog/blob/main/media/tango-stitching.png?raw=true)).

The transient coming in will likely “clear” any artifacts from the switch-over for the listener, and the crossfade will make sure there’s no “click” or “pop” in the sound. Use “bell-shaped” crossfades to avoid the volume drop in the middle of the crossfade.

Alternatively, if you have sections with relatively long sounds (like pads, strings, or vocals), you can use a longer crossfade spanning throughout that long sound. Technically, it will be fading out one part while fading in the other, but if the sounds are similar enough, it will sound like a single sound. I did this in a song called [Empty Mirrors](https://soundcloud.com/vzkrv/empty-mirrors-2024), where at 4:07 the double-vocal “see” sound is actually two different takes stitched together with a 3-second crossfade.

Now, just one thing left before you can bring your song to the world:

### Master it!

Now, I’m no pro at mastering (even less so than at songwriting), but what I do know is that

> Suno doesn’t provide a mastered version of your song.

Even if you look at the waveform, you’ll see that it’s quite dynamic, a telltale sign that it’s a mix not a master. This might actually be a good thing, as otherwise it would be mastering your song from the very beginning, not even “knowing” what genre you’re after — meaning that the ultimate tonal, dynamic, and spatial balance might not be what you’re after. But that also means you’ll have to master it yourself.

Again, not being a pro, I chose the simplest possible solution: I got myself a nice shiny [Ozone 11 Elements](https://www.izotope.com/en/shop/ozone-11-elements) plugin which does it all for me. I’m pretty sure there are better ways to do it — but, let’s admit it, with Suno, your track won’t sound like a _flawless_ production anyway, so why bother with the details? I know that Ozone gets my song pumping where it needs to pump, screaming where it needs to scream, and whispering where it needs to whisper, and that is good enough for me.

Previously I used [LANDR](https://www.landr.com) for mastering, but I find the hassle of uploading the song to their servers and then downloading it again just too much, but maybe I’m just too lazy.

That’s it, you can listen to the final result on [SoundCloud](https://soundcloud.com/vzkrv/disintegration-tango), [YouTube](https://youtu.be/Ps3bXFmpVCA) or [Spotify](https://spti.fi/tango).

---

Damn, this post turned out to be WAY longer than I expected. It also took me WAY longer to write — so I’d be really grateful if you can hit that upvote button given that you’ve read this far.

For those who just scrolled down here, here’s a

TL;DR:

- Use Suno instead of Udio for restoration, as it can work on the structure of the music, not just the character of sound.
- Merge different Covers together to get the best of both worlds.
- Pick your Cover battles wisely — musical structure is more important than sound quality.
- Get the greatest voice you can — we humans are wired to listen to the voice first and foremost.
- Cover your best Cover to get the best sound quality and structure.
- Name your best generations to find them later.
- Search for the Hook — it’s the part that grabs you and doesn’t let them go.
- Subvert expectations to make your song interesting.
- Give your song a moments of “breathing” — don’t go all out all the time.
- Use Inpainting to shorten sections that are too long or too different from the rest of the song.
- Stitch the parts together in the DAW so that the transitions are unnoticeable.
- Master your song with a mastering plugin like Ozone 11 Elements.