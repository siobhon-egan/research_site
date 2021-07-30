---
sort: 1
---

# Dealing with sequences

source: `{{ page.path }}`

{% include list.liquid all=true %}

<span class="badge badge-info">Quick tips in working with sequence files</span>


## Viewing

<span class="badge badge-info">Viewing your nucleotide sequences</span>

When you recieve your raw sanger sequences you will usually recieve files with the following extensions `.ab1` and `.fasta`.
The `.ab1` file is the most useful as it contains the cromatogram which contains information on quality of each base call.

:link: There are lots of programs that you can use to visualise and edit these files.

- [FinchTV](https://finchtv.software.informer.com/1.4/) - a free program, that allows you to quickly and easily visualise your `ab1` files. It also allows you to do some basic edits on your sequences.
- [4 peaks](https://nucleobytes.com/4peaks/index.html) - another free program, that works well on macOS. It works in a similar fashion to FinchTV and also has a good short cut to BLAST sequences.
- [UGENE](http://ugene.net/) - is a free program that allows has a lot more features than the first two programs. It is a popular, widely used program. In additional to basic visualisation and sequence editing it has some useful features to deisgn primers (integrated with primer3), sequence alignment (including short reads), contig assembly, phylogenetic trees and more.
- [GeneStudio](http://genestudio.com/) - is a collection of free programs that allow you to do everything from viewing & editing sequences to building phylogenies and editing trees.
- [Geneious](https://www.geneious.com/) - a paid program, that is one of the most widely used by molecular biologists. It has a range of features and plugins that allow you to do a wide range of phylogenetic and bioinformatic analysis.

## Alignments

<span class="badge badge-info">Sequence alignment with MUSCLE</span>


MUSCLE is one of the most common tools to align sequences. In most cases, only a few command line options are needed.

Free download available [here](https://www.drive5.com/muscle/manual/install.html)

:link: [Muscle documentation](https://www.drive5.com/muscle/manual/)


Make an alignment and save to a file in FASTA format:
```
  muscle -in seqs.fa -out seqs_muscle.afa
```

Write alignment to the console in CLUSTALW format (more readable than FASTA):
```
  muscle -in seqs.fa -clw
```

If you have an existing alignment, you can add a new sequence using the following:
```
   muscle -profile -in1 existing_msa.afa -in2 new_seq.fa -out combined.afa
```

If you have more than one new sequence you need to align them first, and then can merge the two alignments:
```
  muscle -in new_seqs.fa -out new_seqs.afa

  muscle -profile -in1 existing_aln.afa -in2 new_seqs.afa -out combined.afas
```

**Trees**

Commandline muscle is very helpful for making quick trees. Depending on the depth of phylogenetics needed, a simple NJ tree maybe all you need.

Make a UPGMA tree from a multiple alignment:
```
 muscle -maketree -in seqs_muscle.afa -out seqs_muscle_tree.phy
```
Make a Neighbor-Joining tree from a multiple alignment:
```
  muscle -maketree -in seqs_muscle.afa -out seqs_muscle_tree.phy -cluster neighborjoining
```

## Sequence quick bits

<span class="badge badge-info">Quick commands for manipulating sequence files</span>


This is to cover off on some basic quick command line tools to work with sequence data (mainly written for fasta and fastq format but generally useful for most types of sequence files. There are a lot of programs out that. Some use the command line interface, there is also plenty of GUI and web-based programs too. Below are just two on the most useful ones that I like (I tend to like the command line interface ones, as they can easily be upscaled and used on your VM/supercomputer if needed).

**Contents**

- [Some simple commands](#basics)
- [Seqmagick](#seqmagick)
- [SeqKit](#seqkit)
- [Bioawk](#bioawk)


### Basic information and links {#info-links}

This section first starts off with some quick useful commands that will be helpful to assess and manipulate your fasta and fastq file. They can be done locally in your command line and don't require any clumsy dependancies.

:link: Credit to some helpful inspiration

* [Bioinformatics I/O by Joseph Hughes](http://bioinformatics.cvr.ac.uk/blog/short-command-lines-for-manipulation-fastq-and-fasta-sequence-files/)
* [Bioinformatic one-liners by Stephen Turner](https://github.com/stephenturner/oneliners#basic-awk--sed)
* [Linux command line exercises for NGS data processing by Umer Zeeshan Ijaz](http://userweb.eng.gla.ac.uk/umer.ijaz/bioinformatics/linux.html)
* [Biostars thread](https://www.biostars.org/p/17680/)

### Some simple commands {#basics}

These examples simply use `sample.fa` or `sample.fq` or similar format to represent the file you want to investigate. Remember you will need to navigate to the the path of the file or ensure you are in the correct working directory.
The following use some basic sed, awk and pearl commands - often these are already installed if working on a macOS terminal environment

**Convert a fastq file to a fasta file**

```console
sed '/^@/!d;s//>/;N' sample.fq > sample1.fa
```

**Count number of sequences**

Fastq file
```console
grep -c '^@' sample.fq
```

 Fasta file
```console
grep -c '>' sample.fasta
```

**Get some basic info on your file(s)**
```console
perl -ne 'if(/^>(\S+)/){print "$1\n"}' sample.fa
```

You may want to print them to a text file
```console
perl -ne 'if(/^>(\S+)/){print "$1\n"}' sample.fa > sample_names.txt
```

Get the sequence name and length for every individual sequence within a fasta file
```console
cat sample.fasta | awk '$0 ~ ">" {print c; c=0;printf substr($0,2,100) "\t"; } $0 !~ ">" {c+=length($0);} END { print c; }'
```

Calculate the mean length of reads in a fastq file:
```console
awk 'NR%4==2{sum+=length($0)}END{print sum/(NR/4)}' sample.fastq
```

Add something to the end of all header lines
```console
sed 's/>.*/&WHATEVERYOUWANT/' file.fa > outfile.fa
```

Clean up a fasta file so that only the first column of the header is outputted
```console
awk '{print $1}' file.fa > output.fa
```

Remove dupilcate sequences from your fasta file
```console
sed -e '/^>/s/$/@/' -e 's/^>/#/' file.fasta | tr -d '\n' | tr "#" "\n" | tr "@" "\t" | sort -u -t $'\t' -f -k 2,2  | sed -e 's/^/>/' -e 's/\t/\n/'
```

Get A T (or U) G C counts for all sequences in a fasta file
```console
echo -e "seq_id\tA\tU\tG\tC"; while read line; do echo $line | grep ">" | sed 's/>//g'; for i in A U G C;do echo $line | grep -v ">" | grep -o $i | wc -l | grep -v "^0"; done; done < your_fasta_file.fa | paste - - - - -
```

Split a multifasta in to separate files (with arbitrary names).
```console
splitfa(){
i=1;
while read line ; do
  if [ ${line:0:1} == ">" ] ; then
    header="$line"
    echo "$header" >> seq"${i}".fasta
  else
    seq="$line"
    echo "$seq" >> seq"${i}".fasta
    ((i++))
  fi
done < $1
}
```

**Extract sequences by their ID**

Call just certain sequences of interest - in this case we are interested in sequences named `seq1`, `seq2` and `seq3` and put them in a file call `new.fasta`
```console
perl -ne 'if(/^>(\S+)/){$c=grep{/^$1$/}qw(seq1 seq2 seq3)}print if $c' sample.fa > new.fasta
```
Say you have a text file with a list of sequences you want to further investigate you can use this text file (called `seqs_of_interest.txt`) to call out the sequences in the `sample.fasta` file and put them in a few file `seqs_of_interest.fasta`

```console
perl -ne 'if(/^>(\S+)/){$c=$i{$1}}$c?print:chomp;$i{$_}=1 if @ARGV' seqs_of_interest.txt sample.fasta > seqs_of_interest.fasta
```

### Getting taxonomic info

#### 1. `Accession numbers` to `taxid`

These next bits of code are to get taxonomic and description information from nucleotide accession numbers.

First if you have a list of nucleotide accession numbers get the `taxid` reference for each. Code copied from this thread [here](https://www.biostars.org/p/10959/).
(Note: don't need to download any databases or programs for this!)
```
for ACC in A00002 X53307 BB145968 CAA42669 V00181  AH002406  HQ844023
do
   echo -n -e "$ACC\t"
   curl -s "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=${ACC}&rettype=fasta&retmode=xml" |\
   grep TSeq_taxid |\
   cut -d '>' -f 2 |\
   cut -d '<' -f 1 |\
   tr -d "\n"
   echo
 done
 ```

To get sequence description information use the following:

```
for ACC in A00002 X53307 BB145968 CAA42669 V00181  AH002406  HQ844023
do
   echo -n -e "$ACC\t"
   curl -s "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nuccore&id=${ACC}&rettype=fasta&retmode=xml" |\
   grep TSeq_defline |\
   cut -d '>' -f 2 |\
   cut -d '<' -f 1 |\
   tr -d "\n"
   echo
 done
 ```

#### 2. `taxid` to lineage information

Use TaxonKit to get lineage information.
Documentation [here](https://bioinf.shenwei.me/taxonkit/), GitHub repo [here](https://github.com/shenwei356/taxonkit)

**Install** - for linux, other platforms available [here](https://bioinf.shenwei.me/taxonkit/download/)

```
wget https://github.com/shenwei356/taxonkit/releases/download/v0.7.1/taxonkit_linux_amd64.tar.gz
wget https://github.com/shenwei356/csvtk/releases/download/v0.22.0/csvtk_linux_amd64.tar.gz
#unzip
tar -zxvf *.tar.gz
```

Download and decompress taxdump
```
wget -c ftp://ftp.ncbi.nih.gov/pub/taxonomy/taxdump.tar.gz
tar -zxvf taxdump.tar.gz

mkdir -p $HOME/.taxonkit
cp names.dmp nodes.dmp delnodes.dmp merged.dmp $HOME/.taxonkit
```
*Example data - `taxids.txt`
```
cat taxids.txt
863246
1826986
312471
268293
5696
75058
351716
5696
266814
10117
```

Show name and rank only
```
taxonkit lineage -r -n -L taxids.txt \
    | csvtk pretty -t
```

Show lineage consisting of taxids:
```
taxonkit lineage -t  taxids2.txt \
    | csvtk pretty -t
```

Write lineage information to text file
```
taxonkit lineage taxids2.txt | awk '$2!=""' > lineage2.txt
```
Reformat lineage file to the following output: `{k};{p};{c};{o};{f};{g};{s}`
```
taxonkit reformat lineage2.txt | tee lineage.txt.reformat
cut -f 1,3 lineage.txt.reformat
```

Align output to show taxonomic classification clearly
```
 \lineage2.txt \
    | taxonkit reformat \
    | csvtk -H -t cut -f 1,3 \
    | csvtk -H -t sep -f 2 -s ';' -R \
    | csvtk add-header -t -n taxid,kindom,phylum,class,order,family,genus,species \
    | csvtk pretty -t
```

### Seqmagick {#seqmagick}

`seqmagick` is a simple yet powerful utility that helps with basic manipulation and conversion/formatting of sequence files.
Super easy to install and use with minimal requirements (likely already installed) - you just need Python >=3.5 and biopython >=1.70.

Link to github [here](https://github.com/fhcrc/seqmagick) and additional documentation [here](https://seqmagick.readthedocs.io/en/latest/).


**Install**

Open a new terminal window and type the following
```
pip install seqmagick
```

Convert a `.fasta` file to a `.nexus` format.

```
seqmagick convert --output-format nexus --alphabet dna input.fasta output.nex
```

Convert a `.fasta` file to a `.phylip` format.

```
seqmagick convert --output-format phylip --alphabet dna input.fasta output.phy
```
Reverse complement a sequence
```
seqmagick mogrify --reverse-complement sequence.fasta
```

Remove duplicate sequences
```
seqmagick mogrify --deduplicate-sequences sequence.fasta
```


### SeqKit {#seqkit}

*A cross platform and ultrafast toolkit for fasta and fastq file manipulation*

The above commands are good for some basic editing and information but if you want to do more with your fasta and fastq files your going to need some dedicated programs.

`seqkit` is a super useful program for any bioinformatician follow [this link](https://github.com/shenwei356/seqkit) for offical downloads and documenation.

We'll run through the basic below but always refer to the link above for any issues and more details.

**Install (Linux-like systems)**

Just [download](https://github.com/shenwei356/seqkit/releases) compressed executable file of your operating system. Navigate to the file in your command line and decompress it with `tar -zxvf *.tar.gz` command.
* If you have root privilege simply copy it to `/usr/local/bin:`
    `sudo cp seqkit /usr/local/bin/``
* Or copy to anywhere in the environment variable PATH:
    `mkdir -p $HOME/bin/; cp seqkit $HOME/bin/`

Extract the first 100 sequences in a fasta file to new file
```
seqkit head -n 100 reads_all.fasta > reads_001-100.fasta
```

Extract a range of sequences, e.g. sequences 5-15 (inclusive) in a fasta file to new file
```
seqkit range -r 5:15 reads_all.fasta > reads_005-015.fasta
```

### Bioawk {#bioawk}

This is a super useful addition to the awk range of commands specific to bioinformatics - see github page [here](https://github.com/lh3/bioawk)

**conda install**
Easy install using terminal, as long as you have conda installed https://anaconda.org/bioconda/bioawk

```console
conda install -c bioconda bioawk
conda install -c bioconda/label/cf201901 bioawk
```

**Useful tutorials**

Detailed bioinformatics workbook from the [Genome Informatics Facility](https://gif.biotech.iastate.edu/) - tutorial available [here](https://isugenomics.github.io/bioinformatics-workbook/Appendix/bioawk-basics.html), and github account [here](https://github.com/ISUgenomics/bioinformatics-workbook).
