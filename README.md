# PHIP-FLOW
A Nextflow pipeline for Common Phage Immuno-Precipitation Sequencing experiments.
See the [Documentation](https://matsengrp.github.io/phippery/introduction.html)
for more details and usage examples.

[![nextflow]()]()
[![Build Status]()]()

## Quickstart 

Install `Nextflow` by using the following command: 

    curl -s https://get.nextflow.io | bash 
    
Download the `Docker` Desktop, there exists several distibutions packaged for
various linux flavors

    curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh

Launch the pipeline execution with the following command: 

    nextflow run matsengrp/phip-flow -profile {docker|conda}
    
Example command activating conda environment, running cpm pipeline, specifying additional alignment parameters, and writing output to tall/ wide csv format: 

    nextflow run main.nf -profile conda --output_wide_csv true --output_tall_csv true --run_cpm_enr_workflow true --bowtie_optional_args '--tryhard --nomaqround 
    --norc --best --sam --quiet'

Note: the [Dockerfile](docker/Dockerfile) contains all the required dependencies. 
Add the `-profile docker` to enable the containerised execution to the 
example command line shown below. 
