Data and code availability
==========================

SpaBEAT benchmarks fourteen spatial transcriptomics datasets that span the
batch-effect categories introduced on the :doc:`home page <index>`.

Summary
-------

.. list-table::
   :widths: 4 18 18 18 22
   :header-rows: 1

   * - ID
     - Dataset
     - Platform / technology
     - Species / tissue
     - Batch scenario(s)
   * - D1
     - DLPFC
     - 10x Visium (spot-based WTA)
     - Human DLPFC / brain
     - Inter-slice; inter-sample; simulation
   * - D2
     - HBC
     - 10x Visium (spot-based WTA)
     - Human breast cancer
     - Inter-slice; simulation
   * - D3
     - MOB
     - 10x / BGI / Slide-seqV2 (cross-platform ST)
     - Mouse olfactory bulb
     - Cross-platform; simulation
   * - D4
     - Coronal mouse brain
     - 10x Visium (spot-based WTA)
     - Mouse brain
     - Cross-protocol
   * - D5
     - Xenium breast2
     - Xenium (image-based, targeted, cell-level)
     - Human breast cancer
     - Consecutive slice; inter-sample; gene-overlap; segmentation
   * - D6
     - Visium HD
     - 10x Visium HD (high-resolution WTA)
     - TBD
     - Inter-sample
   * - D7
     - Xenium + Visium HD OV
     - Xenium + Visium HD (image-based + high-res WTA)
     - Human ovarian cancer
     - Cross-platform
   * - D8
     - Xenium + Visium HD HCC
     - Xenium + Visium HD (image-based + high-res WTA)
     - Human hepatocellular carcinoma
     - Cross-platform
   * - D9
     - Visium ST
     - Visium ST (spot-based WTA)
     - TBD
     - Consecutive slice
   * - D10
     - MERFISH
     - MERFISH (image-based, targeted, cell-level)
     - TBD
     - Consecutive slice
   * - D11
     - STARmap
     - STARmap (image-based, targeted, cell-level)
     - TBD
     - Consecutive slice
   * - D12
     - Stereo-seq mouse embryo
     - Stereo-seq (sequencing-based high-resolution WTA)
     - Mouse embryo (E16.5)
     - Consecutive slice
   * - D13
     - HER2 breast cancer
     - 10x Visium (spot-based WTA)
     - Human HER2+ breast cancer
     - Inter-slice; inter-sample
   * - D14
     - PFC
     - TBD
     - Human prefrontal cortex
     - Inter-sample


Dataset D1 — DLPFC
------------------

Dorsolateral prefrontal cortex sections with manual cortical layer
annotation, used for **inter-slice**, **inter-sample**, and **simulation**
evaluation.

* Structuredness: structured brain
* Slice/sample IDs: 151507, 151508, 151509, 151510; 151673–151676; etc.
* Resolution: 55 µm spot
* Genes/features used: top HVGs (simulation uses top 5000)
* Reference: Maynard et al.
* Annotation: manual cortical layer annotation (complete)
* Notes: Simulation uses 151507 with 7 domains.

Dataset D2 — HBC
----------------

Two consecutive sections of human breast cancer, used for **inter-slice**
and **simulation** evaluation.

* Number of slices: 2 (section1, section2)
* Resolution: 55 µm spot
* Structuredness: less-structured tumor
* Annotation: original / manual annotation
* Notes: Simulation uses section1.

Dataset D3 — MOB
----------------

Three mouse olfactory bulb slices acquired on three different platforms
(10X, BGI, Slide-seqV2), used to evaluate **cross-platform** batch effects
and simulation.

* Number of slices: 3
* Genes used: top 1000 for scDesign3
* Structuredness: structured brain region
* Notes: SRTsim has no gradient; scDesign3 uses platform id covariate.

Dataset D4 — Coronal mouse brain
--------------------------------

Three coronal sections of adult mouse brain acquired with three 10x Visium
protocols (FFPE, Normal, DAPI), used to evaluate **cross-protocol** batch
effects.

* Number of slices: 3
* Resolution: 55 µm spot
* Structuredness: structured brain
* Notes: original benchmark dataset.

Dataset D5 — Xenium breast2
---------------------------

Human breast cancer imaged with Xenium, used for **consecutive slice**,
**inter-sample**, **gene-overlap**, and **segmentation** scenarios.

* Slice/sample IDs: Rep1; Rep1+2outs; (additional TBD)
* Technology: image-based, targeted, cell-level
* Raw features: ~300 targeted genes
* Genes used: all targeted genes / overlap 300 / 250 / 200 / 100
* Resolution: cell-level
* Annotation: matched scRNA-seq / reference annotation (partial)
* Notes: Subregion may use X > median and Y > median.

Dataset D6 — Visium HD
----------------------

10x Visium HD (high-resolution WTA) dataset used for **inter-sample**
evaluation.

* Bin size: TBD
* Notes: bin size and QC to be specified.

Dataset D7 — Xenium + Visium HD OV
----------------------------------

Human ovarian cancer profiled with both Xenium and Visium HD, used to
evaluate **cross-platform** batch effects.

* Technology: image-based (Xenium) + high-resolution WTA (Visium HD)
* Structuredness: less-structured tumor
* Genes used: shared genes / platform-matched
* Resolution: cell-level / HD bin
* Notes: Also supports pseudo-Visium simulation from OV Xenium.

Dataset D8 — Xenium + Visium HD HCC
-----------------------------------

Human hepatocellular carcinoma profiled with both Xenium and Visium HD,
used to evaluate **cross-platform** batch effects.

* Technology: image-based (Xenium) + high-resolution WTA (Visium HD)
* Structuredness: less-structured tumor
* Resolution: cell-level / HD bin
* Notes: additional cross-platform real dataset.

Dataset D9 — Visium ST
----------------------

Visium ST (spot-based WTA) dataset with two **consecutive slices**.

* Slice/sample IDs: slice_39, slice_44 (23B, 21A)
* Number of slices: 2
* Notes: consecutive-slice benchmark.

Dataset D10 — MERFISH
---------------------

MERFISH (image-based, targeted, cell-level) dataset with five
**consecutive slices**.

* Slice/sample IDs: Slice_7–Slice_11
* Number of slices: 5
* Resolution: cell-level
* Annotation: original cell-type annotation
* Notes: image-based targeted dataset.

Dataset D11 — STARmap
---------------------

STARmap (image-based, targeted, cell-level) dataset with ten
**consecutive slices**.

* Slice/sample IDs: 0–9
* Number of slices: 10
* Resolution: cell-level
* Annotation: original cell-type annotation
* Notes: image-based targeted dataset.

Dataset D12 — Stereo-seq mouse embryo
-------------------------------------

Stereo-seq (sequencing-based high-resolution WTA) mouse embryo (E16.5)
dataset with five **consecutive slices**.

* Slice/sample IDs: Slice_5–Slice_9
* Number of slices: 5
* Resolution: bin / cell-bin (downsample 0.5)
* Structuredness: developmental tissue
* Notes: metrics status to be confirmed.

Dataset D13 — HER2 breast cancer
--------------------------------

HER2-positive breast cancer sections used for **inter-slice** and
**inter-sample** evaluation.

* Slice/sample IDs: Her2_A–H; Her2_sample (8 slices, G2)
* Structuredness: less-structured tumor
* Annotation: original / manual / marker annotation
* Notes: Methods include DeepST, GraphST, spatiAlign, STAligner, PRECAST,
  SpaBatch, SpaCross, SpaMask, SPIRAL.

Dataset D14 — PFC
-----------------

Human prefrontal cortex dataset used for **inter-sample** evaluation.

* Slice/sample IDs: BZ5, BZ9, BZ14
* Number of slices: 3
* Structuredness: structured brain
* Annotation: original / manual annotation
* Notes: additional multi-sample dataset.


Recommended layout
------------------

We recommend the following directory layout for the downloaded data so the
reproduction scripts can be run with minimal edits:

.. code-block:: text

   data/
   ├── DLPFC/
   │   ├── 151507/
   │   ├── 151508/
   │   └── ... (12 sections)
   ├── HBC/
   │   ├── Block_A_Section_1/
   │   └── Block_A_Section_2/
   ├── MOB/
   │   ├── 10x/
   │   ├── stereo/
   │   └── slide/
   ├── Coronal/
   │   ├── normal/
   │   ├── dapi/
   │   └── ffpe/
   ├── Xenium_breast2/
   ├── VisiumHD/
   ├── Xenium_VisiumHD_OV/
   ├── Xenium_VisiumHD_HCC/
   ├── VisiumST/
   ├── MERFISH/
   ├── STARmap/
   ├── Stereo_seq_embryo/
   ├── HER2/
   └── PFC/

Each script in ``code/<method>/`` exposes a ``data_path`` variable at the
top that should be pointed at the corresponding folder.
