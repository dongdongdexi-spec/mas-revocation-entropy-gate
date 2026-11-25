# Controlling Compositional Privacy Leakage After Revocation

Companion materials for *Controlling Compositional Privacy Leakage After Revocation in Multi-Agent Systems With Verifiable Delivery History*. The paper evaluates a shared entropy gate with delivery-history verification on synthetic, Chinese-language multi-agent workflows.

## Materials

| File | Contents |
|---|---|
| [English manuscript](manuscript/IEEE_Access_Manuscript_EN_GitHub_Revision.md) | Revised IEEE Access draft with embedded links to both study figures |
| [Architecture figure](figures/architecture_ieee.pdf) and [privacy–utility figure](figures/budget_sweep_ieee.pdf) | Vector artwork for typesetting |
| [Evidence archive](evidence/major_revision_evidence.zip) | Frozen synthetic cases, prompts, observed outputs, scores, replay code, and figure source records |

## Archive contents

| Path inside the archive | Contents |
|---|---|
| baseline/original_experiment_archive.zip | Frozen baseline corpus, worker and coordinator outputs, scoring scripts, and initial replays |
| live/ | Paired coordinator execution, observer inputs and outputs, and case-level scoring |
| semantic/ and quant/ | Controlled lexical and parser comparisons, calibration and reliability results |
| followup/ | Independent-rewrite replay, local classifier observations, and scripts for recreating the staged experiment workspace |
| figures/ | Study figures and publication artwork |

Use the original ZIP when checking the evidence or staging a replay. Start with README.txt and followup/README.md inside the archive.

## Offline verification

Extract the archive to a new directory. With Python 3.12, run the following from the extracted root to recompute the archived model scores.

~~~text
python -B source/live_revision.py score
python -B followup/prepare_workspace.py <empty-workspace>
~~~

In the staged workspace, install NumPy and scikit-learn, then run the matched rewrite replay.

~~~text
cd <empty-workspace>
python -B work/ieee_manuscript_followup/paraphrase/replay_rewrites.py
~~~

Both procedures use archived observations. The exact local-classifier checkpoint and options for fresh runs appear in the supplemental documentation. The hosted workflow results use the synthetic fixtures identified in the paper.
