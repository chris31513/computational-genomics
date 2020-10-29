# Comandos de la Práctica 01
## Christian Rodrigo García Gómez

# Parte I. 

**Respuesta 1:**

/bin/bash 

**Respuesta 2:**

mkdir data filtered raw_data meta scripts figures archive

**Respuesta 3:**

mv filtered/ data/
mv raw_data/ data/

**Respuesta 4:**

* **data**, contiene los datos, también puede tener otros nombres como *genetic* para datos genéticos y *spatial* para datos espaciales. Hay dos tipos de datos, los **filtered** y los **raw_data**.

* **meta**, contiene los metadatos.
  		
* **scripts**, contiene los scripts o programas usados.

* **figures**, puede tener modelos generados por los **scripts**.

* **archive**, contiene datos irrelevantes para otras personas o archivos temporales.


# Parte IV.
 * **Para leer la primer linea** read -r firstline < file y echo "$firstline"
 * **primera linea de splike_c**, >pdb|6VXX|C Chain C, SARS-CoV-2 spike glycoprotein
 * **primera linea de splike_b**, >pdb|6VXX|B Chain B, SARS-CoV-2 spike glycoprotein
 * **primera linea de splike_a**, >pdb|6VXX|B Chain B, SARS-CoV-2 spike glycoprotein
 * **primeras 3 lineas de sarscov2_genome.fasta**, >NC_045512.2 Severe acute respiratory syndrome coronavirus 2 isolate Wuhan-Hu-1, complete genome
													ATTAAAGGTTTATACCTTCCCAGGTAACAAACCAACCAACTTTCGATCTCTTGTAGATCTGTTCTCTAAA
													CGAACTTTAAAATCTGTGTGGCTGTCACTCGGCTGCATGCTTAGTGCACTCACGCAGTATAATTAATAAC
 * **primeras 3 lineas de sarscov2_assembly.fasta.gz**, >NODE_1_length_264_cov_161.042781
														 CACAAATCTTAACACTCTTCCCTACACGACGCTCTTCCGATCTACGCCGGGCCATTCGTA
														 CGAACCGATACCTGTGGTAAAGGGTCCTACTGTATGGTGGTACACGAGTAGTAGCAAATG
* **Apariciones de '>' en sarscov2_genome.fasta**, 1
* **Apariciones de '>' en sarscov2_assembly.fasta.gz** 35, usé el comando (zless raw_data/sarscov2_assembly.fasta.gz | grep -o '>' | wc -l)
* **Primeras 12 lineas de SRR10971381_R2.fastq.gz** @SRR10971381.512_2
													CGTGGAGTATGGCTACATACTACTTATTTGATGAGTCTGGTGAGTTTAAAGTGGCTTCACATATGTATTGTTCTTTCTACCCTCCAGATGAGGATGAAGAAGAAGGTGATTGTGAAGAAGAAGAGTTTGAGCCATCAACTCAATATGAGT
													+
													/FFFA/A/FFFF66FFFFFF/FF/FFFFFFFFFFFFF/AFFF6FFFA6FFFFF/FFFFFFFFFFFFFFFFFF/FF/FFFFFA/FFF/FFF/A/AFA/FFFFF/=F/F/F/AFAFF//A/AFF//FFAF/FFF=FFAFFFA/A/6=///==
													@SRR10971381.556_2
													TTTGTAAAAATAAAATAAAAAAAATAAAAATAATATATTAAAAAAAGATAAATAAAAAAATGAACAATTAATAAAAAAAAAAAAAAAAAAAAATTAAAAAAAAAAAAAAAAAAAATAAAAAAAAAAAAAAATAAAAAAAAAATTATAAAA
													+
													6AFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF/FFFAFFFFFF/FFA/FF=F//=FF/FFFFFFFFFFFFFA/FFFF/FF/FA//F/FFFFFFA/=FFFFF/FFFF/F=FFFAFF///FFFFA/FF/6//////=/
													@SRR10971381.1428_2
													AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
													+
													FFFFFFFFFFFFAFFFAFFFFFF6A//F//FFF

													(usé el comando zless raw_data/SRR10971381_R2.fastq.gz | head -12 | while read a; do echo $a; done)

* **Diferencia .faa, .fastqc, .fasta** el archivo fasta contiene el genoma, el faa contiene la glicoproteína y el fastqc contiene
* **Diferencia less y less -S** less te da todo el archivo en la pantalla completa y less -S te lo separa por columnas
* **Cantidad de gene en sarscov2_genome.gff3*** hay 75 apariciones de gene