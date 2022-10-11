# QDNASeq
QDNASeq to get copy number ratio from whole genome

# Container:
Build using existing docker image on dockerhub

singularity build --sandbox qdnaseq_ docker://asntech/qdnaseq:v1.26.0

Note: optional to build qdnaseq_1.26.sif directly

# Execution:
Note: Use any wholegenome bam file here (make sure its sorted and indexed before use).

singularity exec qdnaseq_1.26 qdnaseq.R -g hg19 -f HG004_35x_sort.bam -n HG004 > qdnaseq_HG004.log 2>&1 &

# Generate bam ratio txt required for HRD:

singularity exec qdnaseq_1.26.sif --bind /mnt/data/QDNAseq:/data /opt/QDNAseq/qdnaseq_from_bam_chrX.R /data HG004_35x_sort /data 50 > qdnaseq_from_bam_chrX_HG004.log 2>&1 &


      

