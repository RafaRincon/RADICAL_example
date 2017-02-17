# Radical docker example  
## 0. Download radical docker image 
Follow radical docker [tutorial](https://github.com/nselem/radical)  

## 1. Prepare your files:  
Before you run the radical docker image with the command   
`docker run -i -t -v /mypath/mydir:/usr/src/radical nselem/radical /bin/bash`
make sure this files are on /mypath/mydir  
-config.ml.example  
-file.nxs  

**file.nxs** is Nexus partitioned file as Example15.nxs provided here.  

This is an example of config file   
**config.ml.example**  
`TREECOMMAND=-T 1 -m PROTGAMMAJTTF -f d -N 1  `  
`CONTREECOMMAND=contree all/ majrule=yes grpfreq=yes  `    
`MAXTREES=200    `  
`SAMPLES=2  `  
`SECTIONS=1,2,4,8,16,32,64,106  `  
`ROOT=ANA  `  
`RSCRIPT=/root/radical/radical-0.2/bin/loess.R  `  
`SPAN=0.75  `  
`MODE=ML`    

Lets study every line:   
`TREECOMMAND=-T 1 -m PROTGAMMAJTTF -f d -N 1  `    
`TREECOMMAND` is a string of parameters input to either paup or RAxML.  
`T` Number of threads.  
 `m´ Substitution model.  
 `N` Number of generations.
 `CONTREECOMMAND=contree all/ majrule=yes grpfreq=yes  `  
`CONTREECOMMAND`is the paup consensus tree command string.  
`MAXTREES=200  `  
`MAXTREES` specifies the treelimit in a parsimony search.  
`SAMPLES=2  `  
`SAMPLES` specifies the number of RADICAL replicates.    
`SECTIONS=1,2,4,8,16,32,64,106  `  
`SECTIONS` specifies the sections along the RADICAL curve to output 
		submatrices for partitions selected to that point
		for that repetition. If this is a comma separated string,
		numbers are treated literally. If it is a single number, 
		submatrices are output at every quantile specified by 
		that number.  
`ROOT=Calb  `  
`ROOT` is the outgroup taxon.  
`RSCRIPT=/root/radical/radical-0.2/bin/loess.R  `   
`RSCRIPT` specifies the location of loess.R.  
`SPAN=0.75  `   
`SPAN` is a loess specific parameter that specifies the degree of 
		smoothing  
`MODE=ML`    
`MODE` should be set as either PASIMONY or ML.  
## 3. run radical with your files  
`run_radical_forked.pl -m Example15.nxs -o OUT -c config.ml.example -p 1`  
