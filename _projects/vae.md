---
layout: post
title: Discrete Neural Representation Learning for Piano Audio
description: Designed and built an RVQ-VAE to tokenize piano audio
date: 2026-05-25
---

I implemented an RVQ-VAE with 1D convolutional layers and trained it on raw audio waveforms from the MAESTRO dataset of piano audio, then analyzed the codebook tokens and found that the tokens from earlier codebooks encode acoustic energy while later codebooks don't encode acoustic energy or any meaningful MIDI features (paper linked <a href="/assets/pdfs/vae-paper.pdf" target="_blank">here</a>).

A couple of examples of the reconstructed audio are below. Since I trained on the MAESTRO dataset which consisted of very high quality recordings from a digital piano, the reconstruction quality for audio from acoustic pianos where the recording quality is also worse isn't as good.

<figure style="display: flex; flex-direction: column; align-items: center; text-align: center; margin-top: 3em;">
  <div style="display: flex; gap: 2em;">
    <div>
      <audio controls>
        <source src="{{ '/assets/audio/nocturne original.mp3' | relative_url }}" type="audio/mpeg">
      </audio>
      <figcaption style="font-size: 0.8em; color: gray">Original audio</figcaption>
    </div>
    <div>
      <audio controls>
        <source src="{{ '/assets/audio/nocturne compressed.mp3' | relative_url }}" type="audio/mpeg">
      </audio>
      <figcaption style="font-size: 0.8em; color: gray">Reconstructed audio</figcaption>
    </div>
  </div>
  <figcaption style="font-size: 0.8em; margin-top: 0.5em;">Chopin Op 9, No. 2 from MAESTRO dataset (part of validation set)</figcaption>
  <figure style="display: flex; flex-direction: column; align-items: center; text-align: center; margin-bottom: 3em;">
</figure>


<figure style="display: flex; flex-direction: column; align-items: center; text-align: center;">
  <div style="display: flex; gap: 2em;">
    <div>
      <audio controls>
        <source src="{{ '/assets/audio/nocturne 3 original.mp3' | relative_url }}" type="audio/mpeg">
      </audio>
      <figcaption style="font-size: 0.8em; color: gray">Original audio</figcaption>
    </div>
    <div>
      <audio controls>
        <source src="{{ '/assets/audio/nocturne 3 compressed.mp3' | relative_url }}" type="audio/mpeg">
      </audio>
      <figcaption style="font-size: 0.8em; color: gray">Reconstructed audio</figcaption>
    </div>
  </div>
  <figcaption style="font-size: 0.8em; margin-top: 0.5em;">Chopin Op 9, No. 3 from MAESTRO dataset (part of test set)</figcaption>
</figure>

<figure style="display: flex; flex-direction: column; align-items: center; text-align: center; margin-top: 3em;">
  <div style="display: flex; gap: 2em;">
    <div>
      <audio controls>
        <source src="{{ '/assets/audio/me original.mp3' | relative_url }}" type="audio/mpeg">
      </audio>
      <figcaption style="font-size: 0.8em; color: gray">Original audio</figcaption>
    </div>
    <div>
      <audio controls>
        <source src="{{ '/assets/audio/me compressed.mp3' | relative_url }}" type="audio/mpeg">
      </audio>
      <figcaption style="font-size: 0.8em; color: gray">Reconstructed audio</figcaption>
    </div>
  </div>
  <figcaption style="font-size: 0.8em; margin-top: 0.5em;">Me playing Liebestraum No. 3</figcaption>
  <figure style="display: flex; flex-direction: column; align-items: center; text-align: center; margin-bottom: 3em;">
</figure>

<figure style="display: flex; flex-direction: column; align-items: center; text-align: center;">
  <div style="display: flex; gap: 2em;">
    <div>
      <audio controls>
        <source src="{{ '/assets/audio/me ballade original.mp3' | relative_url }}" type="audio/mpeg">
      </audio>
      <figcaption style="font-size: 0.8em; color: gray">Original audio</figcaption>
    </div>
    <div>
      <audio controls>
        <source src="{{ '/assets/audio/me ballade compressed.mp3' | relative_url }}" type="audio/mpeg">
      </audio>
      <figcaption style="font-size: 0.8em; color: gray">Reconstructed audio</figcaption>
    </div>
  </div>
  <figcaption style="font-size: 0.8em; margin-top: 0.5em;">Me playing Chopin Ballade No. 1</figcaption>
</figure>