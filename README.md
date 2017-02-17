# Radical docker example  

##your volume must contain:  
-config.ml.example  
-file.nxs  

## config.ml.example  Example  
`TREECOMMAND=-T 1 -m PROTGAMMAJTTF -f d -N 1  
CONTREECOMMAND=contree all/ majrule=yes grpfreq=yes  
MAXTREES=200  
SAMPLES=2  
SECTIONS=1,2,4,8,16,32,64,106  
ROOT=Calb  
RSCRIPT=/root/radical/radical-0.2/bin/loess.R  
SPAN=0.75  
MODE=ML`  
