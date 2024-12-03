## Combining two vocal tracks, e.g. v3 and v4, to get the same loudness — table to calculate the attenuation factors (details in comments)

*Originally a [Reddit post](https://www.reddit.com/r/SunoAI/comments/1h5ky3i/combining_two_vocal_tracks_eg_v3_and_v4_to_get/)*

So I [wrote before](https://www.reddit.com/r/SunoAI/comments/1gx3qlm/were_not_going_to_see_v4_without_shimmer_soon_but/) about how you can insert v4 vocals (after remastering) into a v3.5 master by getting stems of both and combining them (instrumentals from v3.5, vocals from v4).

But here’s the thing: This can lead to an unnatural sound, because removing *all* vocals is a pretty tough computational task (even for specialized AIs).

BUT! Attenuating vocals by, say, 9db (instead of removing them completely), isn’t actually that hard, and there are even real-time plugins to do that.

So instead of doing this, we’ll do it a bit differently this time:

**Step 1:**

In Izotope’s [Master Rebalance plugin](https://www.izotope.com/en/products/ozone/features.html#master-rebalance) (they’re having a Black Friday sale as of this writing btw — I’m not affiliated), reduce the vocal loudness in the v3.5 master track:

You can go for the entire -9 db, or you can experiment with attenuating it by less if you want to keep some of that v3.5 vocal expressiveness that some say is missing in v4.

**Step 2**:

In Suno (or some other platform, or some standalone editor like Izotope RX 11), get a vocal-only stem from v4.

**Step 3**:

In your DAW of choice, combine them together, attenuating according to the topmost table, e.g., by 0.6 db for a -9 db vocal reduction in the v3.5 master:

*(can’t add a screenshot here, but you get the drill)*

Voila!

Now, you could theoretically avoid all this calculations and just used said Master Rebalance plugin to reduce the vocals by 9 db in the v3.5 master and *increase* the vocals by 9 db in the v4 master and then combine the two — but that’ll only work if you are okay with the sound the v4 remaster is producing for you, which I’m not sure of.

Hope this helps — enjoy making music!

P.S. Here is the link to the chat where the calculations were made, in case you want to figure them out or double-check them: [https://chatgpt.com/share/674ee3a5-055c-8000-a9bc-8a2fceae5642](https://chatgpt.com/share/674ee3a5-055c-8000-a9bc-8a2fceae5642)