# AVVA · EUSIPCO 2025

**Quality Over Quantity? LLM-Based Curation for a Data-Efficient Audio–Video Foundation Model**

[Ali Vosoughi](https://ali-vosoughi.github.io/) · Dimitra Emmanouilidou · Hannes Gamper

University of Rochester · Microsoft Research

Work completed during an internship at Microsoft Research, Redmond, WA, USA.

[Project page](https://avva-curation.github.io/AVVA-curation/) · [Paper](https://eurasip.org/Proceedings/Eusipco/Eusipco2025/pdfs/0000286.pdf) · [Microsoft Research publication](https://www.microsoft.com/en-us/research/publication/quality-over-quantity-llm-based-curation-for-a-data-efficient-audio-video-foundation-model/)

This repository contains the static AVVA project page. It presents the paper’s abstract, curation pipeline, original framework figure, examples from AVE-2, and complete main retrieval table. All page content is in `index.html`; figures are in `figures/`. There is no build step or framework dependency.

## Dataset and follow-on work

[AVE-2](https://huggingface.co/datasets/ali-vosoughi/ave-2) is the dataset that followed this work. Access is gated, individually reviewed, and subject to the citation agreement on the dataset card. The page’s example annotations are machine-generated, attributed to Ali Vosoughi and co-authors under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The required access and citation notice is preserved on the page. Underlying audiovisual media are governed by their own terms and are not included here.

The follow-on preprint is [Projected Audio Tokens Gain Retrieval and Lose Grounded Generation in Multimodal LLMs](https://ali-vosoughi.github.io/SoundCLIP/) ([Projected Audio Tokens Gain Retrieval and Lose Grounded Generation in Multimodal LLMs (preprint)](https://ali-vosoughi.github.io/SoundCLIP/)). Cite both papers when using AVE-2, as requested on its dataset card.

## Preview locally

Run from the repository directory:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Open <http://127.0.0.1:8000/>. Captions, scores and results work without JavaScript; JavaScript only supports copying the citation. The page does not embed or download YouTube media.

## Citation

```bibtex
@inproceedings{vosoughi2025quality,
  title = {Quality Over Quantity? {LLM}-Based Curation for a
           Data-Efficient Audio--Video Foundation Model},
  author = {Vosoughi, Ali and Emmanouilidou, Dimitra and Gamper, Hannes},
  booktitle = {EUSIPCO 2025},
  year = {2025},
  url = {https://eurasip.org/Proceedings/Eusipco/Eusipco2025/pdfs/0000286.pdf}
}
```

## Provenance and license

See [the redesign report](REDESIGN_REPORT_2026-10-01.md) for paper source lines, pinned example provenance, and local validation. Existing figure files are preserved. Page code retains the [MIT license](LICENSE); the AVE-2 annotations retain their separate attribution and citation terms.
