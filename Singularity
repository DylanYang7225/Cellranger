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
  wget -O cellranger-3.1.0.tar.gz "http://cf.10xgenomics.com/releases/cell-exp/cellranger-3.1.0.tar.gz?Expires=1587444312&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cDovL2NmLjEweGdlbm9taWNzLmNvbS9yZWxlYXNlcy9jZWxsLWV4cC9jZWxscmFuZ2VyLTMuMS4wLnRhci5neiIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTU4NzQ0NDMxMn19fV19&Signature=VgplH0cSyGexx97j~dug9MeDnbUSFRhMBE2CbIkG4ph0FKEzTJcdruYqlhVQYwtJ0BjngO1~TXWaxfytheKJUT6s-CpMnt79PaUJ-GqxthloAVE9bagkyYy669-RBPI-0RHPB070qrxo6Tp0vksHfS7fzhBirF-tBF845wQlfaf1PjrGai7ru5qsrMebF5zP1-SsIA46NPA8SAazBlqeisz3PZeuoXBkr8zfqQJ67luSKyG29NPCLMAR~iUa~tpgaQczHUGJVRPANSWeieSWCweoKMoI85hujvGuXW2kWOfZvlvcceYzjHojtBUojRB3f~Tn1FvWss98jeXnjHOP0w__&Key-Pair-Id=APKAI7S6A5RYOXBWRPDA"
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

