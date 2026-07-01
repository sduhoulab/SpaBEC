SpaCross
========

`SpaCross <https://github.com/zhanglabtools/SpaCross>`_ integrates
spatial transcriptomics slices via a cross-attention graph neural
network. It models cross-slice spot correspondences alongside the
intra-slice spatial graph, yielding a shared embedding that aligns
slices across donors, platforms, and protocols.

Installation
------------

.. code-block:: console

   $ conda create -n spacross python=3.9 -y
   $ conda activate spacross
   $ pip install torch==1.13.1
   $ pip install torch-geometric==2.3.0
   $ pip install scanpy==1.9.3 anndata==0.9.2
   $ git clone https://github.com/zhanglabtools/SpaCross.git
   $ pip install -e SpaCross

Reproduction scripts
--------------------

Scripts live in ``code/SpaCross/``:

.. list-table::
   :widths: 35 65
   :header-rows: 1

   * - Script
     - Dataset
   * - ``1new_dlpfc_spacross.py`` / ``2`` / ``3`` / ``7374``
     - DLPFC, individual donor (inter-slice)
   * - ``all_new_dlpfc_spacross.py``
     - DLPFC, all 12 sections (inter-sample)
   * - ``hbc_new_spacross.py``
     - Human breast cancer (inter-slice)
   * - ``mob_new_spacross.py``
     - Mouse olfactory bulb (cross-platform)
   * - ``coronal_new_spacross.py``
     - Mouse coronal brain (cross-protocol)

Run everything
--------------

.. code-block:: console

   $ cd code/SpaCross
   $ bash run_all_spacross.sh

The script writes integrated AnnData objects (``.h5ad``) containing the
SpaCross embedding in ``adata.obsm['emb']``. These embeddings feed the
benchmark metric scripts under ``code/comparison/`` (see
:doc:`../metrics`).
