# Replicate Package for 'Library Migrations in Java, JavaScript, and Python Packaging Ecosystems: A Comparative Study'

This is the replication package for our paper Library Migrations in Java, JavaScript, and Python Packaging Ecosystems: A Comparative Study. It can be used to replicate all four research questions in the paper using our preprocessed and manually labeled data.

## Introduction

Reusing open-source software libraries has become the norm in modern software development, but libraries can fail due to various reasons, e.g., security vulnerabilities, lacking features, end of maintenance.
In some cases, developers need to replace the library in use with another competent library with similar functionalities, i.e., *library migration*.
Previous studies have leveraged library migrations as a unique lens of observation to reveal insights into library selection and dependency management in general. However, they are heavily biased toward Java while the generalizability of their findings remains unknown.

We aim to empirically investigate the prevalence, domains, rationals and directionality of library migrations in Java/Maven, Python/PyPI, and JavaScript/npm, that explain *how* and *why* library migrations occur and well serve the comparison.
We attempt to confirm that library migrations are indeed universal (i.e., not unique to Java/Maven) and demonstrate some sort of common patterns (e.g., unidirectionality); the rationales can also help the establishment of best practices for library selection and migration.

More specifically, we ask the following research questions:

- **RQ1:** How common are library migrations in Java/Maven, JavaScript/npm, and Python/PyPI? How do the longitudinal trends differ in the three ecosystems? 
- **RQ2:** In what library domains do migrations happen? How do the domains differ in the three ecosystems?
- **RQ3:** What are the rationales for library migration? How do the rationales differ in the three ecosystems?
- **RQ4:** Are library migrations unidirectional? How does the directionality differ in the three ecosystems?

To answer the research questions, we proposed a semi-automatic method that can accurately locate library migration commits and their rationales from git repositories, and conduct manual labelling, data analysis and visualization to generate the presented results. We implement all automated processing using Python in an Anaconda environment and we conduct all manual labelling using Microsoft Excel. We hope the scripts and dataset in this replication package can be useful to further studies in library migration and other related fields.

## Replication Package Setup
```shell script
conda create -n LMC python=3.8
conda activate LMC
python -m pip install -r requirements.txt
conda install -n LMC ipykernel --update-deps --force-reinstall
```

Then, activate the LMC environment and run `jupyter lab` in the repository folder for replication.

## Replicating Results
After the replication package is setup, you should have a Jupyter Lab server instance running at http://localhost:8888. In Jupyter Lab, you should see the whole git repository folder, in which there are four notebooks: rq1_prevalance.ipynb, rq2_domain.ipynb, rq3_rationale.ipynb, and rq4_directionality.ipynb. They correspond to the four RQs in our paper. You can directly see the plots and numbers used in our paper in the cells' output. For each notebook, you can start a Python kernel and run all cells, and then you should be able to replicate all the results in this notebook. The results should look identical or similar to the plots in the paper if it is working properly.

Our migration dataset is in the migration folder, where each file is named as `{language}_migration.csv` or `{language}_migration_group.csv`, corresponding to the ungrouped dataset ad grouped dataset in three ecosystems. Our manual labelled reasons are in the reason folder.