# Nextclade build for Yellow Fever Virus (full genome)

## Instructions
To run this build yourself, you will first need to install some dependencies.
We provide a `.yaml` file you can use to set up a conda/mamba environment, e.g.:
```bash
micromamba env create -f environment.yaml
micromamba activate yellow-fever-virus
```

Next, create the directory structure expected by the workflow:
```bash
mkdir -p data/translations results/ out-dataset/
```

Following this, you can run the workflow using `snakemake --cores <n> all`, where you substitute `<n>` with the number of cores you want to allocate the run.

## Visualising output

The generated tree can be viewed using auspice:

```sh
npx auspice view --datasetDir out-dataset/
```

Then open:

```sh
http://localhost:4000/tree
```

To run the dataset with example data, you can serve it locally and run nextclade:

```sh
npx serve --cors out-dataset -l 3000
```

Then open:

```sh
https://master.clades.nextstrain.org/?dataset-url=http://localhost:3000
```
