SpaMask
=======

`SpaMask <https://github.com/JinmiaoChenLab/SpaMask>`_ is a
masking-based self-supervised framework for spatial transcriptomics.
It learns spot embeddings by reconstructing randomly masked gene
expression and graph edges over the spatial neighborhood graph,
yielding representations that are robust to batch effects between
slices.

Installation
------------

.. code-block:: console

   $ conda create -n spamask python=3.9 -y
   $ conda activate spamask
   $ pip install torch==1.13.1
   $ pip install torch-geometric==2.3.0
   $ pip install scanpy==1.9.3 anndata==0.9.2
   $ git clone https://github.com/JinmiaoChenLab/SpaMask.git
   $ pip install -e SpaMask

Reproduction scripts
--------------------

Scripts live in ``code/SpaMask/``:

.. list-table::
   :widths: 35 65
   :header-rows: 1

   * - Script
     - Dataset
   * - ``1new_dlpfc_spamask.py`` / ``2`` / ``3`` / ``7374``
     - DLPFC, individual donor (inter-slice)
   * - ``all_new_dlpfc_spamask.py``
     - DLPFC, all 12 sections (inter-sample)
   * - ``hbc_new_spamask.py``
     - Human breast cancer (inter-slice)
   * - ``mob_new_spamask.py``
     - Mouse olfactory bulb (cross-platform)
   * - ``coronal_new_spamask.py``
     - Mouse coronal brain (cross-protocol)

Run everything
--------------

.. code-block:: console

   $ cd code/SpaMask
   $ bash run_all_spamask.sh

The script writes integrated AnnData objects (``.h5ad``) containing the
SpaMask embedding in ``adata.obsm['emb']``. These embeddings are loaded
by the metric scripts under ``code/comparison/`` (see
:doc:`../metrics`).
