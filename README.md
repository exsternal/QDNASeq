# QDNASeq
QDNASeq to get copy number ratio from whole genome

# Container:
Build using existing docker image on dockerhub

singularity build --sandbox qdnaseq_ docker://asntech/qdnaseq:v1.26.0

Note: optional to build qdnaseq_.sif directly

# Execution:

singularity exec qdnaseq_ qdnaseq.R -g hg19 -f HG004_35x_sort.bam -n HG004 

Note: Use qnaseq_.sif optionally instead of sandbox qdnaseq_
      Use any wholegenome bam file here (make sure its sorted and indexed before use).
      

