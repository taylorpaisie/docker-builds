<<<<<<< HEAD
# CheckM2

This image implements:
* [CheckM2 v1.0.2](hhttps://github.com/chklovski/CheckM2)

and can be accessed at [docker hub](https://hub.docker.com/repository/docker/tpaisie/checkm2/general).

## Example analysis
Get positive and negative control test data:
```
# Download positive and negative control test data
wget -nv --no-check-certificate https://raw.githubusercontent.com/taylorpaisie/docker_containers/main/checkm2/1.0.2/burk_wgs.fa -O burk_wgs_pos_ctrl.fa
wget -nv --no-check-certificate https://raw.githubusercontent.com/taylorpaisie/docker_containers/main/checkm2/1.0.2/burk_16S.fa -O burk_16S_neg_ctrl.fa

```

# Running CheckM2 on the test data
```
checkm2 predict --input burk_wgs_pos_ctrl.fa \
    burk_16S_neg_ctrl.fa \
    --output-directory tests_output/
```

## Run checksum on files
```
sha256sum burk_wgs_pos_ctrl.fa > burk_wgs_checksum.txt
sha256sum burk_16S_neg_ctrl.fa > burk_16S_checksum.txt
sha256sum tests_output/quality_report.tsv > quality_report_checksum.txt
```

=======
# CheckM2 container

Main tool: [checkm2](https://github.com/chklovski/CheckM2)
  
Code repository: https://github.com/chklovski/CheckM2

Additional tools:
- diamond: 2.0.4
- prodigal 2.6.3

Basic information on how to use this tool:
- executable: checkm2
- help: -h, --help
- version: --version
- description: Rapid assessment of genome bin quality using machine learning.

Additional information:

CheckM2 relies on a external diamond database (~1.7 GB) for rapid annotation. the database can be downloaded via `checkm2 database --download` command or obtained directly from: https://zenodo.org/api/records/5571251/files/checkm2_database.tar.gz/content

  
Full documentation: https://github.com/chklovski/CheckM2

## Example Usage

```bash
checkm2 predict --threads 8 fasta --input ./input_folder --output-directory ./output_folder --database_path /path/to/database/CheckM2_database/uniref100.KO.1.dmnd
```
>>>>>>> d072e3d4d325515f04da8722e7fc417ea5b6120a
