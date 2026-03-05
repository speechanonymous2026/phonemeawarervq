---
layout: page
title: Demo page
permalink: /
---

<style>
  .page-title { display: none; }
  .sidebar { display: none; }
  .content { max-width: 1280px; margin: 0 auto; padding: 2rem 1rem; }

  .hero { text-align: center; margin: 1.25rem 0 2.5rem; }
  .hero h1 { font-size: 2.1rem; margin: 0 0 .4rem; line-height: 1.25; }
  .hero .sub { font-size: 1.05rem; color: #666; }

  .section-title { font-weight: 800; font-size: 1.6rem; margin: 3rem 0 1rem; }

  .abstract {
    font-size: 1.05rem;
    line-height: 1.75;
    background: #fafafa;
    border: 1px solid #eee;
    border-radius: 10px;
    padding: 1.2rem 1.4rem;
  }

  .note {
    font-size: 1.02rem;
    line-height: 1.6;
    color: #333;
    margin: 0.5rem 0 1.0rem;
  }

  table.audio-samples {
    border-collapse: collapse;
    margin: 1.0rem auto 1.8rem;
    text-align: center;
    width: 100%;
  }
  .audio-samples th, .audio-samples td {
    border: 1px solid #ccc;
    padding: 10px;
    vertical-align: middle;
  }
  .audio-samples th {
    background: #f8f8f8;
    font-weight: 600;
  }
  .audio-samples td.label {
    font-weight: 600;
    background: #fcfcfc;
    white-space: nowrap;
  }
  .audio-samples td.text {
  text-align: left;
  min-width: 260px;
  line-height: 1.4;
}
  .audio-samples td.text .txt{
    white-space: normal;
    overflow-wrap: anywhere;
    word-break: keep-all;
  }

  audio { width: 190px; max-width: 100%; }
  @media (max-width: 900px) { audio { width: 165px; } }
  @media (max-width: 720px) { audio { width: 145px; } }
</style>

<div class="hero">
  <h1>Hierarchical Vector Quantization for Intra-Phoneme Variability in Linguistic Representations</h1>
  <p class="sub">Anonymous Submission</p>
</div>

<style>
  .figure { text-align: center; }
  .figure img { max-width: 100%; height: auto; display: inline-block; }
</style>

<div>
  <div class="section-title">Proposed Method</div>
  <div class="figure">
    <img src="{{ '/assets/image/archi.png' | relative_url }}" alt="Proposed Method Architecture">
  </div>
</div>

<div class="Abstract">
Disentangling speaker-independent linguistic features from speech representations is essential for many tasks. 
Vector quantization (VQ) with k-means clustering is widely used to suppress speaker information while preserving linguistic content in these features. 
However, single-stage VQ often struggles to disentangle these factors due to phonetic variability. 
To address this, we propose a hierarchical, phoneme-aware two-stage residual VQ framework. 
The first stage performs phoneme-level structural clustering using a compact codebook aligned with the phoneme inventory. 
Then, the second stage captures fine-grained intra-phoneme variations using codeword-dependent codebook sizes, determined by phoneme-specific variability using a heuristic and mutual information-based criteria. 
Experiments on automatic speech recognition, speaker identification, and voice conversion demonstrate that our method better preserves linguistic information while reducing speaker information in representations.
</div>

<div class="section-title">Voice Conversion Samples</div>
<p class="note">
Audio samples including source speech, target speech, and converted outputs from three VC models. 
We compare the single-stage VQ baseline with the proposed equal error-based and AMI-based strategies.
</p>

---

## SEF-VC

<table class="audio-samples">
  <thead>
    <tr>
      <th>Sample</th>
      <th>Text</th>
      <th>Source</th>
      <th>Target</th>
      <th>Baseline</th>
      <th>Equal Error-based (Proposed)</th>
      <th>AMI-based (Proposed)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="label">#1</td>
      <td class="text"><div class="txt">Thy ways greatly try me ruth and all thy relations</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/source/4970_29095_000012_000000.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/target/8463_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/base/0088_F4970-to-F8463.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/error/0088_F4970-to-F8463.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/ami/0088_F4970-to-F8463.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>

    <tr>
      <td class="label">#2</td>
      <td class="text"><div class="txt">"Then her new england conscience stepped in"</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/source/1995_1826_000021_000001.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/target/7127_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/base/0157_F1995-to-M7127.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/error/0157_F1995-to-M7127.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/ami/0157_F1995-to-M7127.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>

    <tr>
      <td class="label">#3</td>
      <td class="text"><div class="txt">"And if i had a fortune would thee want me to lead a useless life"</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/source/4970_29095_000049_000003.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/target/7176_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/base/0178_F4970-to-M7176.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/error/0178_F4970-to-M7176.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/sefvc/ami/0178_F4970-to-M7176.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>
  </tbody>
</table>

---

## AdaptVC

<table class="audio-samples">
  <thead>
    <tr>
      <th>Sample</th>
      <th>Text</th>
      <th>Source</th>
      <th>Target</th>
      <th>Baseline</th>
      <th>Equal Error-based (Proposed)</th>
      <th>AMI-based (Proposed)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="label">#1</td>
      <td class="text"><div class="txt">"Very soon after dinner charles smith excused himself"</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/source/1995_1836_000045_000000.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/target/237_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/base/0051_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/error/0051_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/ami/0051_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>

    <tr>
      <td class="label">#2</td>
      <td class="text"><div class="txt">"What a field of cotton what a marvellous field"</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/source/1995_1837_000013_000002.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/target/1320_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/base/0161_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/error/0161_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/ami/0161_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>

    <tr>
      <td class="label">#3</td>
      <td class="text"><div class="txt">"These johnsons thought that they were first rate to their servants"</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/source/8463_287645_000014_000001.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/target/8455_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/base/0159_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/error/0159_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/adaptvc/ami/0159_pred.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>
  </tbody>
</table>

---

## StylebookVC

<table class="audio-samples">
  <thead>
    <tr>
      <th>Sample</th>
      <th>Text</th>
      <th>Source</th>
      <th>Target</th>
      <th>Baseline</th>
      <th>Equal Error-based (Proposed)</th>
      <th>AMI-based (Proposed)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="label">#1</td>
      <td class="text"><div class="txt">"But just here mr king thought it about time to take matters into his hands"</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/source/237_126133_000014_000000.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/target/3570_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/base/237_126133_000014_000000_3570_10.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/error/237_126133_000014_000000_3570_10.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/ami/237_126133_000014_000000_3570_10.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>

    <tr>
      <td class="label">#2</td>
      <td class="text"><div class="txt">"A cold lucid indifference reigned in his soul"</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/source/1089_134686_000009_000000.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/target/1320_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/base/1089_134686_000010_000000_1320_10.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/error/1089_134686_000010_000000_1320_10.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/ami/1089_134686_000010_000000_1320_10.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>

    <tr>
      <td class="label">#3</td>
      <td class="text"><div class="txt">"You will see this for yourself if you consider the passage as it should properly have been written"</div></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/source/7176_92135_000035_000001.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/target/8455_10.0sec_0.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/base/7176_92135_000035_000001_8455_10.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/error/7176_92135_000035_000001_8455_10.wav' | relative_url }}" type="audio/wav"></audio></td>
      <td><audio controls preload="none"><source src="{{ '/assets/audio/stylebookvc/ami/7176_92135_000035_000001_8455_10.wav' | relative_url }}" type="audio/wav"></audio></td>
    </tr>
  </tbody>
</table>