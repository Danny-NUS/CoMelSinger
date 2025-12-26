<h1 style="text-align: justify;">
CoMelSinger: Discrete Token-Based Zero-Shot Singing Synthesis With Structured Melody Control and Guidance
</h1>
## Abstract of the paper

<div style="text-align: justify; font-family: 'Times New Roman', 'SimSun', '宋体', serif;">
Singing Voice Synthesis (SVS) aims to generate expressive vocal performances from structured musical inputs such as lyrics and pitch sequences. While recent progress in discrete codec-based speech synthesis has enabled zero-shot generation via in-context learning, directly extending these techniques to SVS remains non-trivial due to the requirement for precise melody control. In particular, prompt-based generation often introduces prosody leakage, where pitch information is inadvertently entangled within the timbre prompt, compromising controllability. We present CoMelSinger, a zero-shot SVS framework that enables structured and disentangled melody control within a discrete codec modeling paradigm. Built on the non-autoregressive MaskGCT architecture, CoMelSinger replaces conventional text inputs with lyric and pitch tokens, preserving in-context generalization while enhancing melody conditioning. To suppress prosody leakage, we propose a coarse-to-fine contrastive learning strategy that explicitly regularizes pitch redundancy between the acoustic prompt and melody input. Furthermore, we incorporate a lightweight encoder-only Singing Voice Transcription (SVT) module to align acoustic tokens with pitch and duration, offering fine-grained frame-level supervision. Experimental results demonstrate that CoMelSinger achieves notable improvements in pitch accuracy, timbre consistency, and zero-shot transferability over competitive baselines. 
</div>

## Model Architecture
<div style="text-align: center;">
    <img src="CoMelSinger-overall.png" width="1000px">
    <figcaption style="text-align: justify; font-family: 'Times New Roman', 'SimSun', '宋体', serif;"> Overview of CoMelSinger (left). It adopts a two-stage pipeline: a T2S model encodes lyrics into semantic tokens, and an S2A model generates acoustic tokens conditioned on lyrics, pitch, and prompt. SVT provides pitch supervision. All modules except S2A are frozen during training. Overview of the coarse-to-fine contrastive learning strategy (right). (a) Sequence-level contrastive learning encourages timbre consistency across different melodies. (b) Frame-level contrastive learning uses pitch perturbation to enforce local pitch-awareness and disentangle melody from timbre.</figcaption>
</div>

## Synthesis Results on Seen Singers
<table style="font-family: 'Times New Roman', 'SimSun', '宋体', serif;">
    <tbody>
       <tr>
            <td nowrap><center>GT (Codec)</center></td>
            <td><center>Reference</center></td>
            <td><center>MaskGCT</center></td>
            <td><center>Vevo 1.5</center></td>
           <td><center>CoMelSinger</center></td>
        </tr>

        <tr style="background-color: #e6f5ef;">
          <td colspan="5" style="text-align: left; padding: 6px 10px; font-weight: 500;">
            我是歌词。。。。。
          </td>
        </tr>

        <tr>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-01/GT.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-01/Reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-01/maskgct.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-01/vevo.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-01/ours.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>

        <tr style="background-color: #e6f5ef;">
          <td colspan="5" style="text-align: left; padding: 6px 10px; font-weight: 500;">
            我是歌词。。。。。
          </td>
        </tr>

        <tr>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-02/GT.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-02/Reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-02/maskgct.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-02/vevo.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-02/ours.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>

        <tr style="background-color: #e6f5ef;">
          <td colspan="5" style="text-align: left; padding: 6px 10px; font-weight: 500;">
            我是歌词。。。。。
          </td>
        </tr>

        <tr>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-03/GT.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-03/Reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-03/maskgct.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-03/vevo.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-03/ours.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>

        <tr style="background-color: #e6f5ef;">
          <td colspan="5" style="text-align: left; padding: 6px 10px; font-weight: 500;">
            我是歌词。。。。。
          </td>
        </tr>

        <tr>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-04/GT.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-04/Reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-04/maskgct.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-04/vevo.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-04/ours.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>

        <tr style="background-color: #e6f5ef;">
          <td colspan="5" style="text-align: left; padding: 6px 10px; font-weight: 500;">
            我是歌词。。。。。
          </td>
        </tr>

        <tr>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-05/GT.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-05/Reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-05/maskgct.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-05/vevo.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-05/ours.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>

        <tr style="background-color: #F0EFF8;">
          <td colspan="5" style="text-align: left; padding: 6px 10px; font-weight: 500;">
            我是歌词。。。。。
          </td>
        </tr>

        <tr>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-06/GT.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-06/Reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-06/maskgct.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-06/vevo.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 130px;">
                  <source src="seen/demo-06/ours.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>

## Synthesis Results on Unseen Singers
<table>
    <tbody>
       <tr style="background-color: #F4A89A;">
          <td colspan="5" style="text-align: left; padding: 6px 10px; font-weight: 500;">
            Male Singer 1: Danny
          </td>
        </tr>
        <tr>
            <td><center>Reference</center></td>
            <td><center>MaskGCT</center></td>
            <td><center>Vevo 1.5</center></td>
           <td><center>CoMelSinger</center></td>
        </tr>
        <tr>
            <td>
                <audio controls style="width: 200px;">
                  <source src="unseen/m1/demo-01/reference.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 200px;">
                  <source src="unseen/m1/demo-01/maskgct.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 200px;">
                  <source src="unseen/m1/demo-01/vevo.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls style="width: 200px;">
                  <source src="unseen/m1/demo-01/ours.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
        
</table>
