Problem 1, python script:
seq = "KVRMFTSELDIMLSVNGPADQIKYFCRHWT"
print(len(seq))
print(len(seq)*3 + 3)

Shell:
------------------------------
cd /home/chernym/homework5/
python Pr1.py
----------------------------------
30
93
===========================================================
Problem 2, bash-file:
------------------------------
module load prodigal 
prodigal --help 
input_file="/home/chernym/homework5/GCA_000006745.1_ASM674v1_genomic.fna" 
gff_file="${input_file%.fna}.gff" 
prodigal -i "$input_file" -o "$gff_file" -q 
cds_count=$(grep -c "CDS" "$gff_file") 
echo "File: $gff_file, CDS Count: $cds_count"
-----------------------------------------
shell:
bash "/home/chernym/homework5/Pr2.sh"
-----------------------------------------------
Loading module for PRODIGAL v2.6.3
PRODIGAL v2.6.3 is now loaded

Unknown option.

Usage:  prodigal [-a trans_file] [-c] [-d nuc_file] [-f output_type]
                 [-g tr_table] [-h] [-i input_file] [-m] [-n] [-o output_file]
                 [-p mode] [-q] [-s start_file] [-t training_file] [-v]

Do 'prodigal -h' for more information.

File: /home/chernym/homework5/GCA_000006745.1_ASM674v1_genomic.gff, CDS Count: 3594
======================================================================
Problem 3, bash-file:
----------------------------------------------------------------------------------
module load prodigal
find /home/chernym/homework5/ -name "*.fna" -type f | while read -r fna_file; do
    # Generate output GFF file path
    gff_file="${fna_file%.fna}.gff"

    # Run Prodigal to generate the GFF file
    prodigal -i "$fna_file" -o "$gff_file"

    # Count the number of CDS entries in the GFF file
    cds_count=$(grep -c "CDS" "$gff_file")

    # Print the GFF file path and the CDS count
    echo "$gff_file $cds_count"
done | sort -k2 -n | tail -n 1
-----------------------------------------------
shell:
bash "/home/chernym/homework5/Pr3.sh"
-------------------------------------------
Loading module for PRODIGAL v2.6.3
PRODIGAL v2.6.3 is now loaded
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...4033488 bp seq created, 47.49 pct GC
Locating all potential starts and stops...219838 nodes
Looking for GC bias in different frames...frame bias scores: 2.21 0.16 0.62
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2961149 bp)...done!
Finding genes in sequence #2 (1072315 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1042519 bp seq created, 41.31 pct GC
Locating all potential starts and stops...37422 nodes
Looking for GC bias in different frames...frame bias scores: 2.60 0.20 0.20
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1042519 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...2257487 bp seq created, 40.40 pct GC
Locating all potential starts and stops...96476 nodes
Looking for GC bias in different frames...frame bias scores: 2.65 0.14 0.21
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2257487 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...2365589 bp seq created, 35.33 pct GC
Locating all potential starts and stops...86378 nodes
Looking for GC bias in different frames...frame bias scores: 2.54 0.16 0.29
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2365589 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...3294955 bp seq created, 57.22 pct GC
Locating all potential starts and stops...213618 nodes
Looking for GC bias in different frames...frame bias scores: 0.83 0.28 1.89
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2117144 bp)...done!
Finding genes in sequence #2 (1177787 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1667867 bp seq created, 38.87 pct GC
Locating all potential starts and stops...71998 nodes
Looking for GC bias in different frames...frame bias scores: 1.71 0.15 1.14
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1667867 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1860725 bp seq created, 46.25 pct GC
Locating all potential starts and stops...92480 nodes
Looking for GC bias in different frames...frame bias scores: 1.27 0.19 1.54
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1860725 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...3284204 bp seq created, 66.61 pct GC
Locating all potential starts and stops...191980 nodes
Looking for GC bias in different frames...frame bias scores: 0.73 0.11 2.16
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2648638 bp)...done!
Finding genes in sequence #2 (412348 bp)...done!
Finding genes in sequence #3 (45704 bp)...done!
Finding genes in sequence #4 (177466 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1138011 bp seq created, 52.77 pct GC
Locating all potential starts and stops...73375 nodes
Looking for GC bias in different frames...frame bias scores: 2.03 0.23 0.74
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1138011 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1590815 bp seq created, 43.30 pct GC
Locating all potential starts and stops...51125 nodes
Looking for GC bias in different frames...frame bias scores: 1.67 0.24 1.09
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1551335 bp)...done!
Finding genes in sequence #2 (39456 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1230230 bp seq created, 40.58 pct GC
Locating all potential starts and stops...40543 nodes
Looking for GC bias in different frames...frame bias scores: 2.57 0.21 0.22
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1230230 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1643831 bp seq created, 39.19 pct GC
Locating all potential starts and stops...71171 nodes
Looking for GC bias in different frames...frame bias scores: 1.58 0.14 1.28
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1643831 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1830138 bp seq created, 38.15 pct GC
Locating all potential starts and stops...72389 nodes
Looking for GC bias in different frames...frame bias scores: 2.68 0.13 0.19
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1830138 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1234409 bp seq created, 40.57 pct GC
Locating all potential starts and stops...40703 nodes
Looking for GC bias in different frames...frame bias scores: 2.57 0.21 0.22
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1229853 bp)...done!
Finding genes in sequence #2 (4532 bp)...done!
/home/chernym/homework5/GCA_000006745.1_ASM674v1_genomic.gff 3594
==================================================================================
Problem 4, prodigal:
Bash:
module load prodigal
find /home/chernym/homework5/ -name "*.fna" -type f | while read -r fna_file; do
    # Generate output GFF file path
    gff_file="${fna_file%.fna}.gff"

    # Run Prodigal to generate the GFF file
    prodigal -i "$fna_file" -o "$gff_file"

    # Count the number of CDS entries in the GFF file
    cds_count=$(grep -c "CDS" "$gff_file")

    # Print the GFF file path and the CDS count
    echo "$gff_file $cds_count"
done | sort -k2 -n 
--------------------------------------------------------
shell: 
bash "/home/chernym/homework5/Pr4.sh"
---------------------------------------------------------
Output:
Loading module for PRODIGAL v2.6.3
PRODIGAL v2.6.3 is now loaded
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...4033488 bp seq created, 47.49 pct GC
Locating all potential starts and stops...219838 nodes
Looking for GC bias in different frames...frame bias scores: 2.21 0.16 0.62
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2961149 bp)...done!
Finding genes in sequence #2 (1072315 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1042519 bp seq created, 41.31 pct GC
Locating all potential starts and stops...37422 nodes
Looking for GC bias in different frames...frame bias scores: 2.60 0.20 0.20
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1042519 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...2257487 bp seq created, 40.40 pct GC
Locating all potential starts and stops...96476 nodes
Looking for GC bias in different frames...frame bias scores: 2.65 0.14 0.21
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2257487 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...2365589 bp seq created, 35.33 pct GC
Locating all potential starts and stops...86378 nodes
Looking for GC bias in different frames...frame bias scores: 2.54 0.16 0.29
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2365589 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...3294955 bp seq created, 57.22 pct GC
Locating all potential starts and stops...213618 nodes
Looking for GC bias in different frames...frame bias scores: 0.83 0.28 1.89
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2117144 bp)...done!
Finding genes in sequence #2 (1177787 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1667867 bp seq created, 38.87 pct GC
Locating all potential starts and stops...71998 nodes
Looking for GC bias in different frames...frame bias scores: 1.71 0.15 1.14
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1667867 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1860725 bp seq created, 46.25 pct GC
Locating all potential starts and stops...92480 nodes
Looking for GC bias in different frames...frame bias scores: 1.27 0.19 1.54
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1860725 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...3284204 bp seq created, 66.61 pct GC
Locating all potential starts and stops...191980 nodes
Looking for GC bias in different frames...frame bias scores: 0.73 0.11 2.16
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (2648638 bp)...done!
Finding genes in sequence #2 (412348 bp)...done!
Finding genes in sequence #3 (45704 bp)...done!
Finding genes in sequence #4 (177466 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1138011 bp seq created, 52.77 pct GC
Locating all potential starts and stops...73375 nodes
Looking for GC bias in different frames...frame bias scores: 2.03 0.23 0.74
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1138011 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1590815 bp seq created, 43.30 pct GC
Locating all potential starts and stops...51125 nodes
Looking for GC bias in different frames...frame bias scores: 1.67 0.24 1.09
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1551335 bp)...done!
Finding genes in sequence #2 (39456 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1230230 bp seq created, 40.58 pct GC
Locating all potential starts and stops...40543 nodes
Looking for GC bias in different frames...frame bias scores: 2.57 0.21 0.22
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1230230 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1643831 bp seq created, 39.19 pct GC
Locating all potential starts and stops...71171 nodes
Looking for GC bias in different frames...frame bias scores: 1.58 0.14 1.28
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1643831 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1830138 bp seq created, 38.15 pct GC
Locating all potential starts and stops...72389 nodes
Looking for GC bias in different frames...frame bias scores: 2.68 0.13 0.19
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1830138 bp)...done!
-------------------------------------
PRODIGAL v2.6.3 [February, 2016]
Univ of Tenn / Oak Ridge National Lab
Doug Hyatt, Loren Hauser, et al.
-------------------------------------
Request:  Single Genome, Phase:  Training
Reading in the sequence(s) to train...1234409 bp seq created, 40.57 pct GC
Locating all potential starts and stops...40703 nodes
Looking for GC bias in different frames...frame bias scores: 2.57 0.21 0.22
Building initial set of genes to train from...done!
Creating coding model and scoring nodes...done!
Examining upstream regions and training starts...done!
-------------------------------------
Request:  Single Genome, Phase:  Gene Finding
Finding genes in sequence #1 (1229853 bp)...done!
Finding genes in sequence #2 (4532 bp)...done!
/home/chernym/homework5/GCA_000008725.1_ASM872v1_genomic.gff 897
/home/chernym/homework5/GCA_000008605.1_ASM860v1_genomic.gff 1009
/home/chernym/homework5/GCA_000008745.1_ASM874v1_genomic.gff 1063
/home/chernym/homework5/GCA_000091085.2_ASM9108v2_genomic.gff 1063
/home/chernym/homework5/GCA_000008785.1_ASM878v1_genomic.gff 1505
/home/chernym/homework5/GCA_000008525.1_ASM852v1_genomic.gff 1579
/home/chernym/homework5/GCA_000027305.1_ASM2730v1_genomic.gff 1748
/home/chernym/homework5/GCA_000008625.1_ASM862v1_genomic.gff 1776
/home/chernym/homework5/GCA_000008545.1_ASM854v1_genomic.gff 1866
/home/chernym/homework5/GCA_000006825.1_ASM682v1_genomic.gff 2032
/home/chernym/homework5/GCA_000006865.1_ASM686v1_genomic.gff 2383
/home/chernym/homework5/GCA_000007125.1_ASM712v1_genomic.gff 3152
/home/chernym/homework5/GCA_000008565.1_ASM856v1_genomic.gff 3248
/home/chernym/homework5/GCA_000006745.1_ASM674v1_genomic.gff 3594
=================================================================
Problem 4_prokka:
Bash:
mkdir tmp 
module load prokka 
find /home/chernym/homework5/ -name "*.fna" -type f | awk '{ 
    # generate output. gff file name (keep only the file name and remove the path). 
    filename = substr($0, match($0, "[^/]*$")); 
     
    # generate output. gff file path, and set the output path to /home/zhanh0m/tmp/. 
    gff_file = "/home/chernym/homework5/tmp/" substr(filename, 1, length(filename)-4) ".gff"; 
     
    # run the prokka command to generate a. gff file. 
    system("prokka --outdir /home/chernym/homework5/tmp/ --force --prefix " substr(filename, 1, length(filename)-4) " \"" $0 "\" > /dev/null 2>&1"); 
     
    # set command line that counting the number of CDS in the. gff file. 
    grep_cmd = "grep -c CDS \"" gff_file "\""; 
     
    # obtain number of CDS and save in the grep_result variable. 
    grep_result = ""; 
    grep_cmd | getline grep_result; 
    close(grep_cmd); 
     
    # print the result. 
    print "File: " gff_file ", CDS Count: " grep_result;
}'
-------------------------------------------------------
shell:
bash Pr4_prokka.sh
--------------------------------------------------------
Output:	
Loading module for Prokka
Prokka 1.14.6 modules now loaded
File: /home/chernym/homework5/tmp/GCA_000006745.1_ASM674v1_genomic.gff, CDS Count: 3589
File: /home/chernym/homework5/tmp/GCA_000008725.1_ASM872v1_genomic.gff, CDS Count: 892
File: /home/chernym/homework5/tmp/GCA_000006825.1_ASM682v1_genomic.gff, CDS Count: 2028
File: /home/chernym/homework5/tmp/GCA_000006865.1_ASM686v1_genomic.gff, CDS Count: 2383
File: /home/chernym/homework5/tmp/GCA_000007125.1_ASM712v1_genomic.gff, CDS Count: 3150
File: /home/chernym/homework5/tmp/GCA_000008525.1_ASM852v1_genomic.gff, CDS Count: 1577
File: /home/chernym/homework5/tmp/GCA_000008545.1_ASM854v1_genomic.gff, CDS Count: 1861
File: /home/chernym/homework5/tmp/GCA_000008565.1_ASM856v1_genomic.gff, CDS Count: 3245
File: /home/chernym/homework5/tmp/GCA_000008605.1_ASM860v1_genomic.gff, CDS Count: 1001
File: /home/chernym/homework5/tmp/GCA_000008625.1_ASM862v1_genomic.gff, CDS Count: 1771
File: /home/chernym/homework5/tmp/GCA_000008745.1_ASM874v1_genomic.gff, CDS Count: 1058
File: /home/chernym/homework5/tmp/GCA_000008785.1_ASM878v1_genomic.gff, CDS Count: 1504
File: /home/chernym/homework5/tmp/GCA_000027305.1_ASM2730v1_genomic.gff, CDS Count: 1748
File: /home/chernym/homework5/tmp/GCA_000091085.2_ASM9108v2_genomic.gff, CDS Count: 1056
-----------------------------------------------------------------------
Prokka is slower and it gives the same or less CDS number comparing to prodigal
=============================================================================================
shell:
grep "gene="/home/chernym/homework5/tmp/*.gff | awk -F 'gene=' '{if ($2) print $2}' | awk -F ';' '{print $1}' | sort | uniq | head -n 5'
-----------------------------------------------------------------------
Works very slow, no output

