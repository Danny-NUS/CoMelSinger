# CoMelSinger: Discrete Token-Based Zero-Shot Singing Synthesis With Structured Melody Control and Guidance
## Abstract of the paper

<div style="text-align: justify">
Singing Voice Synthesis (SVS) aims to generate expressive vocal performances from structured musical inputs such as lyrics and pitch sequences. While recent progress in discrete codec-based speech synthesis has enabled zero-shot generation via in-context learning, directly extending these techniques to SVS remains non-trivial due to the requirement for precise melody control. In particular, prompt-based generation often introduces prosody leakage, where pitch information is inadvertently entangled within the timbre prompt, compromising controllability. We present CoMelSinger, a zero-shot SVS framework that enables structured and disentangled melody control within a discrete codec modeling paradigm. Built on the non-autoregressive MaskGCT architecture, CoMelSinger replaces conventional text inputs with lyric and pitch tokens, preserving in-context generalization while enhancing melody conditioning. To suppress prosody leakage, we propose a coarse-to-fine contrastive learning strategy that explicitly regularizes pitch redundancy between the acoustic prompt and melody input. Furthermore, we incorporate a lightweight encoder-only Singing Voice Transcription (SVT) module to align acoustic tokens with pitch and duration, offering fine-grained frame-level supervision. Experimental results demonstrate that CoMelSinger achieves notable improvements in pitch accuracy, timbre consistency, and zero-shot transferability over competitive baselines. 
</div>

## Model Architecture
<div style="text-align: center;">
    <img src="CoMelSinger-overall" width="1000px">
    <figcaption style="text-align: justify"> Overview of CoMelSinger (left). It adopts a two-stage pipeline: a T2S model encodes lyrics into semantic tokens, and an S2A model generates acoustic tokens conditioned on lyrics, pitch, and prompt. SVT provides pitch supervision. All modules except S2A are frozen during training. Overview of the coarse-to-fine contrastive learning strategy (right). (a) Sequence-level contrastive learning encourages timbre consistency across different melodies. (b) Frame-level contrastive learning uses pitch perturbation to enforce local pitch-awareness and disentangle melody from timbre.</figcaption>
</div>

## Synthesis Results on Seen Singers
<table>
    <thead>
        <tr>
            <th colspan="4">Synthesis on Seen Singers with Short Music Scores</th>
        </tr>
    </thead>
    <tbody>
       <tr>
            <td nowrap><center>Singer Identity</center></td>
            <td><center>GT mel + Vocoder</center></td>
            <td><center>Reference</center></td>
            <td><center>SPSinger</center></td>
        </tr>
        <tr>
            <td>Female 0</td>
            <td>
                <audio controls>
                  <source src="short_seen/female_0_short_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_0_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_0_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female 1</td>
            <td>
                <audio controls>
                  <source src="short_seen/female_1_short_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_1_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_1_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female 2</td>
            <td>
                <audio controls>
                  <source src="short_seen/female_2_short_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_2_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/female_2_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 0</td>
            <td>
                <audio controls>
                  <source src="short_seen/male_0_short_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_0_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_0_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 1</td>
            <td>
                <audio controls>
                  <source src="short_seen/male_1_short_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_1_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_1_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 2</td>
            <td>
                <audio controls>
                  <source src="short_seen/male_2_short_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_2_short_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_seen/male_2_short_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th colspan="4">Synthesis on Seen Singers with Long Music Scores</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td nowrap><center>Singer Identity</center></td>
            <td><center>GT mel + Vocoder</center></td>
            <td><center>Reference</center></td>
            <td><center>SPSinger</center></td>
        </tr>
        <tr>
            <td>Female 0</td>
            <td>
                <audio controls>
                  <source src="long_seen/female_0_long_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/female_0_long_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/female_0_long_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female 1</td>
            <td>
                <audio controls>
                  <source src="long_seen/female_1_long_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/female_1_long_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/female_1_long_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female 2</td>
            <td>
                <audio controls>
                  <source src="long_seen/female_2_long_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/female_2_long_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/female_2_long_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 0</td>
            <td>
                <audio controls>
                  <source src="long_seen/male_0_long_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/male_0_long_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/male_0_long_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 1</td>
            <td>
                <audio controls>
                  <source src="long_seen/male_1_long_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/male_1_long_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/male_1_long_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 2</td>
            <td>
                <audio controls>
                  <source src="long_seen/male_2_long_seen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/male_2_long_seen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_seen/male_2_long_seen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>

## Synthesis Results on Unseen Singers
<table>
    <thead>
        <tr>
            <th colspan="4">Synthesis on Unseen Singers with Short Music Scores</th>
        </tr>
    </thead>
    <tbody>
       <tr>
            <td nowrap><center>Singer Identity</center></td>
            <td><center>GT mel + Vocoder</center></td>
            <td><center>Reference</center></td>
            <td><center>SPSinger</center></td>
        </tr>
        <tr>
            <td>Female 0</td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_0_short_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_0_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_0_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female 1</td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_1_short_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_1_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_1_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female 2</td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_2_short_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_2_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/female_2_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 0</td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_0_short_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_0_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_0_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 1</td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_1_short_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_1_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_1_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 2</td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_2_short_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_2_short_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="short_unseen/male_2_short_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th colspan="4">Synthesis on Unseen Singers with Long Music Scores</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td nowrap><center>Singer Identity</center></td>
            <td><center>GT mel + Vocoder</center></td>
            <td><center>Reference</center></td>
            <td><center>SPSinger</center></td>
        </tr>
        <tr>
            <td>Female 0</td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_0_long_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_0_long_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_0_long_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female 1</td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_1_long_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_1_long_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_1_long_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Female 2</td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_2_long_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_2_long_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/female_2_long_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 0</td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_0_long_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_0_long_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_0_long_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 1</td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_1_long_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_1_long_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_1_long_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Male 2</td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_2_long_unseen/ground_truth.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                  </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_2_long_unseen/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="long_unseen/male_2_long_unseen/spsinger.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>
