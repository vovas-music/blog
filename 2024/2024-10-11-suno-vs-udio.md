## Udio vs Suno: technical differences, and what they have to do with Tesla and Edison

*October 11, 2024*

*Originally posted as a [Reddit comment](https://www.reddit.com/r/SunoAI/comments/1g0tk3j/comment/lrbx2n9)*

I’ve been meaning to make a video about that but because I’m so lazy and because you asked, I guess a Reddit comment must do. Grab some tea.

So we basically have two dominant models in today’s AI applications, Diffusion and Transformers.

Diffusion is an “everything-at-once” model. It works by essentially “restoring” an image (or an acoustic spectrogram) from noise. You give it noise, some guidance (“this is a scantily clad anime character” or “this is the spectrogram of an award winning trap song”), and it does its best to give you the entire image or song. Although it does take it multiple steps to restore it, at each step you have the entirety of the data you’re after.

That is why for diffusion models inpainting is an easy task. You just give it the image/track you wish to inpaint, replace a part of it with noise, and run it, making sure it only works on the “noisied” part while keeping the rest the same.

Udio, a diffusion model-based app, works this way, and, sonic artefacts apart, does a pretty amazing job at filling out those gaps.

Transformers, on the other hand, work “millisecond by millisecond.” It generates one word (token, to be precise), then it looks back at what it has, generates one more, and so on. In the end you get the entire song only once you’ve done through all the time units.

(A necessary technical digression: Although the end product of transformer model is a waveform — not a spectrogram like it is for diffusion models — the transformer itself does NOT generate/predict the exact amplitude values. Instead, it produces intermediary “tokens,” which a separate model, a variational autoencoder, then transforms into the waveform. What these tokens represent specifically is an open question — to me at least — but I think it’s best to consider it as an “internal language” that the model uses to explain music to itself. But it’s a whole different, and fascinating, topic, so let’s end it here for now.)

So, back to our transformer, when you have it basically guessing what sonic pressure should come at the next millisecond, it’s pretty hard to tell it, “hey dude, I know you’re working hard as you are, but can you also make sure you end up in _that_ spot, so that my song sounds seamlessly?”

I’m actually impressed they were able to pull it off at all. But I know that there was for instance an “edit” feature for GPT-3 that basically inpainted text between two parts — so I guess the mathematical apparatus for this does exist. 

Now, this might be the very reason why it’s limited (from below) by 10 seconds. The model should have some space to figure out how to join that first part with that second part. It can’t just put it there at once as Diffusion does.

So then, you might ask, is Diffusion the way to go further with music AI, then?

I strongly feel it’s not. And here are my reasons:

1. Diffusion gives worse temporal resolution. If you listen to any Udio track, you can hear this “shuffling”/“hissing” quality to the sound. This is because, when you have the entire song (or even 30 seconds of it) squeezed to one spectrogram, you just don’t have the information density required to “de-squeeze” it to an actual waveform.

This is especially prominent for transient sounds, aka drums. However hard you try to increase the temporal resolution, those transient are essentially singularities — they come in one crest of the wave and then disappear — you just can’t quite “catch” that crest from a spectrogram. As an excercise, try to switch to the spectrogram mode in your DAW and pinpoint the _exact_ moment a snare hits.

For Transformers, it’s a non-issue. If you go through the waveform millisecond by millisecond, you’ll easily find the spot when the waveform reaches its peak, producing a drum sound.

2. Diffusion cuts off the high end. Again, if you look at the spectrogram of an Udio song, you’ll see that it abruptly ends around several kilohertz (typing from phone, can’t double check the exact value right now). 

The reason is simple: If you’re basically “painting” a spectrogram, you need to predefined where that spectrogram starts and ends. Granted, you could say, “let’s end it beyond what the human ear can hear” — but then you’ll need to pack information much tighter, and as the high end is so much less densely packed in any music, it’s just a matter of tradeoffs to sacrifice some high end for the sake of better frequency resolution in the remaining part. The end result sounds okay, great even, but you can’t help but hear that something is missing.

(And, credit where it’s due, Diffusion models _do_ make a great job at capturing the frequencies in the remaining range. That’s why Udio vocals sound so much more natural and why there are so less frequency-related artefacts — noise, cracks, stray sounds — that Suno is so prone to. When you’re encoding a spectrogram, getting rid of those is much easier than when you work with the raw product i.e. the waveform.)

3. And, last but not least, Diffusion-based music generation doesn’t allow for streaming. I don’t know about you, but one of my favorite things about Suno is that you can start listening to your generation mere seconds after you click Create.

No wonder: As the Transformer goes millisecond by millisecond, all you have to do (provided sufficiently powerful hardware at the server side) is give it a bit of a head start and then you can start listening from the beginning while it’s still working on the continuation.

Not so for Diffusion models: Until all those 10-20-30 steps of “painting the entire picture” are done, all you can do is sit and wait. For me, this takes a lot from the creative process, making me go for workarounds such as working on several songs at once (which also has its downsides).

So there you have it, a basic breakdown of why Suno and Udio are so different in both sound and features, and why things that are easy for one can be super-hard for the other.

In a way, I feel like we are at the “AC versus DC,” or Edison vs Tesla, if you wish, point in AI music creation.

I’m a strong fan of the Transformer approach myself, for the reasons mentioned, although I do keep an eye on Udio, and a subscription at hand, in case I need inpainting/“prepainting” (another thing that’s wildly hard for Suno). 

I wonder if at some point we find a way to combine the best features of both approaches. Given the pace at which we’ve been going for the last year (a year ago I was creating music with Jukebox, which today sounds laughable at best in terms of sound quality), I wouldn’t be surprised. 

Exciting times to be a music creator!