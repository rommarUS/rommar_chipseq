# rommar_chipseq
A pipeline for the analysis of ChIP Sep data

Please read this file before trying to run chipseq_pipeline.

This pipeline allows the user to process data from ChIP Sep experiments, providing genes that are possibly regulated by 
the transcription factor under study.

Use and installation:
=====================

The user will need to provide a parameter file for this pipeline to work properly.
This parameter file (param_file.txt) is attached on the installation folder, and the user only need
to complete it as described below.

For the installation and use of this pipeline there are two options:

- If the user do not want to add the installation folder to PATH on the .bashrc file,
  the user can simply go to installation folder via command line and type: ./chipseq_pipeline
  This will execute the pipeline from its location.

- If the user want to make the pipeline executable from anywhere, the user will need to add
  the directory to the variable PATH on .bashrc file. To do this, simply go to the installation folder
  where the chipseq_pipeline is, and copy the present working directory (pwd), which will be like:

  /home/<user>/opt/chipseq_pipeline (or the directory where you decided to locate this pipeline).

- To edit the .bashrc file, go to home/<user> and type nano .bashrc (it is hardly recommended to make a security copy of this file)

- Then, on the .bashrc file add a line at the end like this:
  PATH=$PATH:/home/<user>/opt/chipseq_pipeline (change this for your actual path to chipseq_pipeline)

 - To execute chipseq_pipeline, simply type chipseq_pipeline on the command line followed by the complete path to param_file.txt

To complete parameter file:
===========================

This is an example of local parameters file.

installation_folder: /home/rommar/dev/chipseq_pipeline_global
root_directory: /home/rommar/test
master_folder: chipseq_test
number_of_chip: 2
number_of_control: 2
genome: /home/rommar/prr5_data/chromosome1.fa
annotation: /home/rommar/prr5_data/chromosome1.gtf

chip1: /home/rommar/prr5_data/chip_prr5_chr1_1.fastq
chip2: /home/rommar/prr5_data/chip_prr5_chr1_2.fastq

control1: /home/rommar/prr5_data/input_prr5_chr1_1.fastq
control2: /home/rommar/prr5_data/input_prr5_chr1_2.fastq

   In this parameters file, installation folder is the location of the program, root directory is the folder where
the user wants to locate the working directory and master folder is where working directory will be built.

Usually chipseq experiments only have one sample and one input, but this pipeline is prepared to process more
than one replica at a time. The user will need to indicate this in the number of chip and number of control parameters.

The following lines ask for the complete path to the user data, which is the reference genome, the annotation
and the samples (chip and input).
It is important to note that the user will need to add more lines if more replicas need to be processed, with
the same structure as above.

In case the data are from an online database, like .SRA samples, the user will need to change the path to genome,
annotation, chip or control for the complete URL, as the pipeline will automatically download that data from that URL.
Please, be sure the URL you provide is correct, otherwise the pipeline could not download it and will not work properly.





