Bootstrap: docker
From: ubuntu

%labels
    Maintainer Hang(Dylan) Yang	
    Image_Name CellRanger
    Image_Version CellRanger_3.1.0
    
%environment
  export PATH=$PATH:/cellranger/cellranger-3.1.0

%post
  export DEBIAN_FRONTEND=noninteractive
  apt-get update
  apt-get install -y wget

  #--------------------------------------------------------------------------------
  # install cellranger and reference genome
  mkdir -p /cellranger
  cd /cellranger 
  wget -O cellranger-3.1.0.tar.gz "http://cf.10xgenomics.com/releases/cell-vdj/cellranger-3.1.0.tar.gz?Expires=1587461847&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cDovL2NmLjEweGdlbm9taWNzLmNvbS9yZWxlYXNlcy9jZWxsLXZkai9jZWxscmFuZ2VyLTMuMS4wLnRhci5neiIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTU4NzQ2MTg0N319fV19&Signature=SOKsLLbobRGQ3zoALtK6xZzb6Fa-~PqJ~1iQ5xGTo-8mCyBfCZcTIZ6uPEJ6fh4y9IBLavpsENR9eUjKyGARBJe6lD43y20GbSqtQCDozDPMZnFJ58QNJuzbkIaS4q38c3jOjQNBlRzosTX4zcmU4XKL-M33Uq9obToEIQEpUhmA1u5FeqZgzn4LcfF-1NNOmX2i7yuLdcpULFxo1ChVD7YCSo09gCqyT9qs4sJWiAY~gFCJuaumPPuVaa8Q466Za3mbj0fdYeH-vCbxNIjdRiztzllWW-xF-z7inBolGfcScdVcz0V1ZuhthsXm2w7draBWRlesqsaS69DBNWRD3w__&Key-Pair-Id=APKAI7S6A5RYOXBWRPDA"
  wget http://cf.10xgenomics.com/supp/cell-exp/refdata-cellranger-GRCh38-3.0.0.tar.gz
  wget http://cf.10xgenomics.com/supp/cell-vdj/refdata-cellranger-vdj-GRCh38-alts-ensembl-3.1.0.tar.gz
  tar -xvzf refdata-cellranger-GRCh38-3.0.0.tar.gz
  tar -xvzf cellranger-3.1.0.tar.gz
  tar -xvzf refdata-cellranger-vdj-GRCh38-alts-ensembl-3.1.0.tar.gz
  rm refdata-cellranger-GRCh38-3.0.0.tar.gz
  rm cellranger-3.1.0.tar.gz
  rm refdata-cellranger-vdj-GRCh38-alts-ensembl-3.1.0.tar.gz
   
# Create directories to bind-mount data and reference genome and to store output
  mkdir -p /output 
  mkdir -p /data 
  mkdir -p /work/scratch

