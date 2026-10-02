# AVVA project page redesign — October 1, 2026

Completed in `C:\Users\abc\projects\AVVA-page` on the new local branch `redesign-2026-10`, based on main commit `ca8f99433e01e24091cda510666f48164fdb11e1`. Commit message: **Redesign project page (October 2026)**. No push was performed. The reviewer can inspect this local branch before publishing.

Session ID: `01a0fa19-788b-7431-b26d-49c6d6fa7b5d` (also `CODEX_THREAD_ID`).

## What changed

- Rebuilt `index.html` as a single light-theme static page with system fonts, restrained green accents, responsive typography, and clear paper, dataset, and citation links. There are no frameworks, external fonts, analytics, or video embeds. JavaScript only copies the BibTeX, with a selection fallback if clipboard access fails.
- Kept the printed title, author order, affiliations, and internship footnote from `main.tex`. The title preserves the printed en dash in “Audio–Video”; the venue is exactly **EUSIPCO 2025**. The abstract is one paragraph, verbatim apart from joining LaTeX source whitespace.
- Added the four-step curation walkthrough and the original, uncropped framework figure. The existing PNG is byte-identical to the paper’s PNG; every pre-existing figure file is unchanged. No thumbnails exist in this repository, so none were added.
- Replaced hypothetical demos with four real scored AVE-2 metadata examples. Each presents its YouTube ID, segment, exact opening caption paragraph, expandable full verbatim video caption, exact audio description, five-score table, and expandable exact model rationales. Full captions and disclosure controls work without JavaScript. Editorial titles and selection notes are identified separately from released annotations.
- Transcribed the complete main table: every method, both retrieval directions, the exact column names, all means, and all standard deviations. ImageBind and DenseAV remain visible; unsupported derived performance multipliers from the previous page were removed. Three findings use the paper’s own sentences.
- Linked the gated AVE-2 release, retained its access/citation notice and attribution, and linked both papers requested by the dataset card. Added the current SoundCLIP project/preprint links, EUSIPCO BibTeX, Ali’s site, and the Microsoft Research publication page. No Microsoft logo is used.
- Rewrote `README.md` to describe this actual static repository and local preview. Removed instructions for missing `avva` APIs, nonexistent package files, and unsupported implementation claims. `LICENSE` remains unchanged. This report is the only new repository file.

## Sources and identity

Authoritative paper source: `G:\My Drive\Godfile\CVs\publication_data\papers\eusipco2025_avva_filtering\main.tex`.

Source SHA-256: `d4fa98411c7bcda24640bc4fe3061e8c87034b244a2e35f9a3caa1eb21e7e028`. All `main.tex` line numbers below are one-based and refer to this file, not PDF page numbers.

| Content | main.tex lines |
|---|---|
| Exact title | 20 |
| Ali Vosoughi and internship footnote | 23 |
| University of Rochester | 24 |
| Dimitra Emmanouilidou; Microsoft Research | 27–28 |
| Hannes Gamper; Microsoft Research | 31–32 |
| Verbatim abstract | 38–40 |
| Original framework file and figure caption | 55–56 |
| Four-step explanation: segment / caption / score / select | 76, 78–79 |
| Training after selection, Whisper and DINOv2, contrastive learning | 56, 87, 91–94 |
| Retrieval finding, verbatim sentence | 108 |
| Curation finding, verbatim first sentence | 110 |
| Temporal finding, verbatim second sentence | 230 |

Framework SHA-256: `4fc9762a173952fc8c08a7c44526817487c8cd7adf65e69b41edeedd1fdd008d`. The file is displayed at its original aspect ratio and links to its full-size local PNG.

The [official proceedings paper](https://eurasip.org/Proceedings/Eusipco/Eusipco2025/pdfs/0000286.pdf) and [Microsoft Research publication record](https://www.microsoft.com/en-us/research/publication/quality-over-quantity-llm-based-curation-for-a-data-efficient-audio-video-foundation-model/) were consulted for publication identity. Microsoft’s record lists the co-authors in a different order; the page and BibTeX follow `main.tex` and the printed paper. The minimal BibTeX omits conflicting organization fields and unnecessary page numbers and uses the required venue string.

The follow-on link uses the published current title, [Can Sound Replace Vision in LLaVA With Token Substitution?](https://arxiv.org/abs/2506.10416), and the requested [SoundCLIP page](https://ali-vosoughi.github.io/SoundCLIP/). The local follow-on source contains a differently titled later draft; none of that draft’s unpublished results were imported into this page.

## Examples and dataset provenance

Dataset: [ali-vosoughi/ave-2](https://huggingface.co/datasets/ali-vosoughi/ave-2). Pinned revision: `0a025ec10aab4c6b7c9f97bdbbd9355e0482cf8b`. All examples are from the `train` split, file [`data/train_00000.json`](https://huggingface.co/datasets/ali-vosoughi/ave-2/blob/0a025ec10aab4c6b7c9f97bdbbd9355e0482cf8b/data/train_00000.json). Positions below are zero-based array row indices. Existing authenticated access was used with `datasets.load_dataset`, streaming only this metadata shard. The selection considered 50,000 rows. No YouTube media, audio, or thumbnails were downloaded; source media were not watched or independently verified. No access request or new terms acceptance was submitted.

Score order: **Temporal Alignment / Spatial Coherence / Contextual Relevance / Physical Causality / Sound Source Visibility**.

| YouTube ID | Exact sample ID | Segment; local window | Five scores | Row index | Why chosen |
|---|---|---|---|---|---|
| `-fUNb4eiu1w` | `-fUNb4eiu1w_02` | 02; 3–6 s | 10 / 10 / 10 / 9 / 10 | 6968 | The video caption describes a person playing an acoustic guitar; the audio description identifies music and a musical instrument, and the visible-source field identifies the acoustic guitar. |
| `-07O11QVLxo` | `-07O11QVLxo_02` | 02; 3–6 s | 10 / 10 / 8 / 10 / 10 | 6736 | The caption describes a rotary telephone, the audio description includes telephone bell ringing, and the visible-source field identifies the telephone. |
| `2UQi-0zeQsI` | `2UQi-0zeQsI_01` | 01; 0–3 s | 0 / 0 / 0 / 0 / 0 | 48285 | The video caption describes film or television credits, while the audio description identifies speech and a barking dog. All five released scores are zero; the source list identifies the dog as invisible and the credits as silent. |
| `-7QTaeEKaig` | `-7QTaeEKaig_01` | 01; 0–3 s | 3 / 0 / 4 / 5 / 0 | 11579 | The video caption describes a cartoon character resting in bed with a telephone and pillow. The audio description identifies bird calls, and invisible_active_sources explicitly identifies those calls. The released visibility score is zero, with varied scores on the other four criteria. |

The window boundaries are exactly `segment_start_time` and `segment_end_time` from AVE-2. The released schema has no original YouTube/AudioSet offset, so these are labeled as local AVE-2 excerpt windows and are **not used as YouTube timestamp links**. All four `speech_content` fields are empty; no transcripts were invented. Captions, scores, and rationales are labeled machine-generated. These illustrative selections are not a representative evaluation or verified judgments about the original clips.

Each complete row was checked against its source before rendering. For reproducibility, row hashes use SHA-256 of UTF-8 `json.dumps(row, sort_keys=True, ensure_ascii=False, separators=(',', ':'))`:

- `-fUNb4eiu1w_02`: `3067aad3d21fcf65ce4ed23a2f03999fb2b7b8ffcfd0558dcca696fdcf2a2519`
- `-07O11QVLxo_02`: `2671b4f2e8d3476cfc76adb3a1b41b36586e72b066aaa56e27f13b81e5aa1c0d`
- `2UQi-0zeQsI_01`: `16e4280df06329a8c20d0e2af3822f84ddc82e12affb5543968cab61a9e55158`
- `-7QTaeEKaig_01`: `ce41e554c844e0843381a631721606c1cc95277737f986ffc1ed9136afa25183`

The page retains the dataset’s research-use access notice, citation requirement, attribution to Ali Vosoughi and co-authors under CC BY 4.0, and separation of metadata terms from underlying-media terms. The required papers are **Quality Over Quantity? LLM-Based Curation for a Data-Efficient Audio–Video Foundation Model** (EUSIPCO 2025) and **Can Sound Replace Vision in LLaVA With Token Substitution?** (current preprint). Those citations apply to this report’s use of the metadata as well.

Dataset notice, reproduced with the examples on the page:

> AVE-2 is released for research use. By requesting access you agree to the following: (1) you will cite the AVE-2 papers listed on this card in any paper, model, dataset, demo or report that uses AVE-2 or anything derived from it; (2) the annotation layer is used under CC BY 4.0 with attribution to Ali Vosoughi and co-authors; (3) the underlying audiovisual media is obtained under its own terms and is not redistributed with this release; (4) the metadata is not redistributed without this notice and the citation requirement; (5) access requests are reviewed individually and may be declined.

## Every displayed paper number and its source

All scientific quantities attributed to AVVA come directly from `main.tex`. The task also requires AVE-2 identifiers, segment times and example scores, which do not exist in `main.tex`; their exact dataset provenance is recorded above. Bibliographic identifiers and presentation labels are distinguished below rather than assigned fabricated paper lines. No improvement ratio was recomputed for the page.

| Displayed number or numbered term | Where it appears / meaning | main.tex line |
|---|---|---|
| 192 hrs | Hero, verbatim abstract and retrieval finding; curated training duration | 39, 108 |
| DINOv2 | Abstract, hero, framework/alt/caption, method; model identifier | 39, 56, 87 |
| 3-second | Method clip duration | 76 |
| five scores / five criteria | Method’s number of alignment metrics | 71, 78 |
| 0–10 | Method score range and repeated example-table scale labels | 78 |
| 7.6 out of 10 | MRE threshold used for main retrieval results | 109 |
| Top1, Top3, Top10; Top-k={1,3,10} | Exact table headers and caption | 141, 151 |
| K=100; N=100 | Repetitions and random test-subset size in table caption | 141 (also 105) |
| Wav2CLIP | Comparison-method identifier in main table | 153 |
| 5,800 hrs; 30x | Paper’s own retrieval-finding sentence | 108 |
| 0 sec | Paper’s own temporal-finding sentence | 230 |

All main-table cells follow below. Each entry preserves both the mean and its standard deviation, including trailing zeros. The page renders standard deviations as superscripts, as in the source. Headers `Method`, `Retrieval Type`, `AudioCaps`, `VALOR`, `VGG-Sound` are from lines 147–150; subheaders are from line 151.

| Method | Retrieval Type | Dataset | Top1 mean ± SD | Top3 mean ± SD | Top10 mean ± SD | main.tex line |
|---|---|---|---|---|---|---|
| Wav2CLIP | A→V | AudioCaps | 1.20 ± 0.98 | 6.40 ± 3.01 | 18.60 ± 3.83 | 154 |
| Wav2CLIP | A→V | VALOR | 3.60 ± 0.80 | 8.60 ± 0.49 | 18.20 ± 3.54 | 155 |
| Wav2CLIP | A→V | VGG-Sound | 3.40 ± 1.36 | 8.20 ± 1.17 | 19.80 ± 3.06 | 156 |
| Wav2CLIP | V→A | AudioCaps | 3.80 ± 2.14 | 10.00 ± 3.22 | 20.00 ± 3.63 | 158 |
| Wav2CLIP | V→A | VALOR | 4.20 ± 2.64 | 8.00 ± 4.24 | 19.00 ± 3.52 | 159 |
| Wav2CLIP | V→A | VGG-Sound | 3.80 ± 1.94 | 9.20 ± 2.32 | 19.60 ± 1.62 | 160 |
| Random | A→V | AudioCaps | 1.40 ± 0.49 | 3.80 ± 0.75 | 11.80 ± 1.17 | 163 |
| Random | A→V | VALOR | 1.20 ± 0.75 | 3.20 ± 0.40 | 11.60 ± 1.62 | 164 |
| Random | A→V | VGG-Sound | 1.20 ± 0.40 | 3.40 ± 0.49 | 11.60 ± 2.15 | 165 |
| Random | V→A | AudioCaps | 1.00 ± 0.00 | 3.60 ± 0.80 | 10.80 ± 1.17 | 167 |
| Random | V→A | VALOR | 1.20 ± 0.40 | 3.20 ± 0.75 | 11.00 ± 0.63 | 168 |
| Random | V→A | VGG-Sound | 1.00 ± 0.00 | 3.00 ± 0.00 | 10.60 ± 0.80 | 169 |
| DenseAV | A→V | AudioCaps | 10.20 ± 2.04 | 22.60 ± 4.54 | 49.40 ± 4.54 | 172 |
| DenseAV | A→V | VALOR | 7.80 ± 5.19 | 19.00 ± 5.90 | 41.80 ± 4.79 | 173 |
| DenseAV | A→V | VGG-Sound | 6.80 ± 2.64 | 16.00 ± 2.90 | 43.20 ± 3.43 | 174 |
| DenseAV | V→A | AudioCaps | 1.40 ± 0.80 | 5.60 ± 1.85 | 26.40 ± 2.73 | 176 |
| DenseAV | V→A | VALOR | 2.20 ± 1.17 | 5.80 ± 2.79 | 24.60 ± 7.68 | 177 |
| DenseAV | V→A | VGG-Sound | 1.60 ± 1.02 | 5.00 ± 0.63 | 22.60 ± 2.58 | 178 |
| ImageBind | A→V | AudioCaps | 62.00 ± 2.28 | 83.40 ± 3.01 | 92.60 ± 1.85 | 181 |
| ImageBind | A→V | VALOR | 55.80 ± 4.66 | 71.60 ± 3.61 | 85.00 ± 3.74 | 182 |
| ImageBind | A→V | VGG-Sound | 50.60 ± 3.14 | 74.00 ± 5.93 | 88.20 ± 2.99 | 183 |
| ImageBind | V→A | AudioCaps | 64.00 ± 5.37 | 85.40 ± 4.27 | 95.40 ± 0.80 | 185 |
| ImageBind | V→A | VALOR | 58.80 ± 4.71 | 73.60 ± 4.36 | 86.60 ± 3.20 | 186 |
| ImageBind | V→A | VGG-Sound | 53.20 ± 3.31 | 73.40 ± 6.02 | 85.60 ± 3.20 | 187 |
| AVVA (Ours) | A→V | AudioCaps | 6.57 ± 2.30 | 13.84 ± 2.80 | 31.68 ± 3.57 | 190 |
| AVVA (Ours) | A→V | VALOR | 6.69 ± 2.13 | 15.63 ± 3.52 | 33.67 ± 4.40 | 191 |
| AVVA (Ours) | A→V | VGG-Sound | 6.71 ± 1.91 | 15.02 ± 2.73 | 33.86 ± 4.23 | 192 |
| AVVA (Ours) | V→A | AudioCaps | 6.23 ± 2.09 | 14.70 ± 3.17 | 31.06 ± 3.52 | 194 |
| AVVA (Ours) | V→A | VALOR | 7.75 ± 2.61 | 16.64 ± 3.65 | 34.27 ± 4.71 | 195 |
| AVVA (Ours) | V→A | VGG-Sound | 6.86 ± 2.34 | 14.47 ± 3.15 | 32.84 ± 3.89 | 196 |

Required non-paper identifiers and presentation numerals:

- **EUSIPCO 2025**, BibTeX year/key, and proceedings URL: requested publication identity, corroborated by the official proceedings; the venue/year is not specified in the local `main.tex` body.
- **AVE-2**, its repository name, example segment numbers/windows, all example scores, and any digits within YouTube IDs: pinned dataset metadata above. The example-table scale itself is supported by `main.tex:78`.
- **CC BY 4.0** and the access notice’s enumerated clauses **(1)–(5)**: the dataset’s current access/citation notice, not an experimental claim.
- **2506.10416** in the follow-on URL: the current arXiv identifier supplied in the task and verified on arXiv; not an AVVA experimental quantity.
- Walkthrough markers **01–04**: editorial sequencing of the four requested steps, grounded in the method lines above; not a claim that the paper numbers its pipeline this way.
- HTML/CSS dimensions, image dimensions, layout breakpoints and local preview ports are implementation values, not scientific results. Test dimensions, byte counts, revision hashes, row indices, report date and session ID in this report are validation/provenance facts, not paper claims.

## Validation

- Served the final page with `python -m http.server` bound to localhost. `GET /` returned **200**. The referenced local framework PNG returned **200** and loaded successfully; every local figure asset was also fetched successfully in the final asset check.
- Chromium screenshots and browser checks at **390, 768 and 1280 px**: document width matches viewport, no horizontal document overflow, no missing images, no console errors, no failed requests, and no broken anchor targets. The wide results table scrolls inside its labeled, keyboard-focusable container.
- Full video captions, reasoning disclosures, dataset notice, navigation, and citation copying checked. Clipboard text matches the displayed BibTeX after normal Windows newline normalization; failure selects the citation with a clear copy instruction. Core content and disclosures remain functional with JavaScript disabled.
- Automated WCAG A/AA checks produced no violations. Rowspan table headers needed manual contrast verification because the checker could not resolve their backgrounds; verified contrasts exceed AA text requirements. This is a scoped browser/automated review, not a formal accessibility certification.
- Independent content audit compared exact title and abstract, every main-table mean and standard deviation, column names and caption, and all three finding sentences to `main.tex`. Final metadata checks compare full captions, audio descriptions, rationales, all score fields and YouTube IDs to the untouched pinned rows.
- `index.html` is **49,524 bytes**, including all inline CSS and JavaScript, well under 1 MB without media. The only loaded media is the original **167,961-byte** framework PNG. Existing unused figures are preserved.
- Git whitespace validation and final diff review completed. Changes are limited to `index.html`, `README.md`, and this report; existing figures and `LICENSE` are unchanged. No AI co-author trailer is added.

Local review evidence is outside the repository, at `C:\Users\abc\projects\AVVA-page-qa` (screenshots and browser results). Source/selection audit artifacts are at `C:\Users\abc\projects\AVVA-paper-audit.md` and `C:\Users\abc\projects\AVVA-example-work`. Build helpers are outside the repo; the committed page is self-contained and needs no generator to serve.

## Interpretation limits retained in the redesign

The full table is the evidence: the paper’s claim about data efficiency is not presented as universal superiority over every baseline. The page keeps the paper’s own wording alongside all comparison rows. The local and published sources disagree on the detailed temporal-shift setup; the page uses only the verified sentence about the peak at zero shift and does not introduce a new setup description. AVE-2 examples show released model outputs rather than verified audiovisual ground truth.
