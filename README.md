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
`ROOT=Calb  `  
`RSCRIPT=/root/radical/radical-0.2/bin/loess.R  `  
`SPAN=0.75  `  
`MODE=ML`    

Lets study every line:   
`TREECOMMAND=-T 1 -m PROTGAMMAJTTF -f d -N 1  `   
`CONTREECOMMAND=contree all/ majrule=yes grpfreq=yes  `  
`MAXTREES=200    `  
`SAMPLES=2  `  
`SECTIONS=1,2,4,8,16,32,64,106  `  
`ROOT=Calb  `  
`RSCRIPT=/root/radical/radical-0.2/bin/loess.R  `  
`SPAN=0.75  `  
`MODE=ML`    

## 3. run radical with your files  
`run_radical_forked.pl -m Example15.nxs -o OUT -c config.ml.example -p 1`  
