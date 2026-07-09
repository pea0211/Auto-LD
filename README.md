## Auto Lemma Discovery Support Tool base on IPSG. 

IPSG is implemented on top of CafeInMaude (https://github.com/ariesco/CafeInMaude), which is the world's second implementation of CafeOBJ.
IPSG requires Maude version not lower than Maude 3.2 (https://github.com/SRI-CSL/Maude).
To run the tool, first you need to install Maude, which can be found from here: http://maude.cs.illinois.edu/w/index.php/Maude_download_and_installation.
Once Maude is installed, you can try to run the tool with the following commands:

```bash
$ maude -allow-files LD.maude
IPSG> load examples/Qlock/qlock.cafe .
IPSG> load examples/Qlock/input.cafe .
```

where the first command starts the tool, the second command loads the Qlock specification, and the last command loads the input file, which asks the tool to generate the proof scores to prove Qlock enjoys the mutual exclusion properties (i.e., the proof scores of `inv1` and `inv2`).

load examples/TAS/tas.cafe .
load examples/TAS/input.cafe .

<!-- List all false cases by ID -->
list false cases .

<!-- Show proof score by ID -->
show prsc by mutex.2.1.2.1.2.1 .

<!-- Test for QLOCK -->
load examples/Qlock/qlock.cafe .
load examples/Qlock/input.cafe .
list false cases .
show prsc by inv2.4.1.2.1 .
show prsc by mutex.3.1.1.1.2.1 .
list symbolic state forms .
classify assumptions by mutex.3.1.1.1.2.1 .
ORT of pc(s,q) = cs .
derived equations of pc(s,q) = cs by mutex.3.1.1.1.2.1 .
candidate lemmas of pc(s,q) = cs by mutex.3.1.1.1.2.1 .
show prsc by mutex.3.1.1.2.1.1 .
classify assumptions by mutex.3.1.1.2.1.1 .
ORT of pc(s,p) = cs .
derived equations of pc(s,p) = cs by mutex.3.1.1.2.1.1 .
candidate lemmas of pc(s,p) = cs by mutex.3.1.1.2.1.1 .

<!-- Test for TAS -->
load examples/TAS/tas.cafe .
load examples/TAS/input.cafe .
list false cases .
show prsc by mutex.2.1.2.1.2.1 .
show prsc by mutex.2.1.2.2.1.1 .
list symbolic state forms .
classify assumptions by mutex.2.1.2.1.2.1 .
ORT of pc(s,q) = cs .
derived equations of pc(s,q) = cs by mutex.2.1.2.1.2.1 .
candidate lemmas of pc(s,q) = cs by mutex.2.1.2.1.2.1 .

<!-- Test for Anderson -->
load examples/Anderson/anderson.cafe .
load examples/Anderson/input.cafe .
list false cases .
show prsc by mutex.3.1.1.1.2.1 .
show prsc by mutex.3.1.1.2.1.1 .
list symbolic state forms .
classify assumptions by mutex.3.1.1.1.2.1 .
ORT of pc(s,q) = cs .
derived equations of pc(s,q) = cs by mutex.3.1.1.1.2.1 .
candidate lemmas of pc(s,q) = cs by mutex.3.1.1.1.2.1 .

show prsc by lm1.4.1.1.2.1.1.1.2 .
list symbolic state forms .
classify assumptions by lm1.4.1.1.2.1.1.1.2 .

ORT of array(s,next(s)) = true .
derived equations of array(s,next(s)) = true by lm1.4.1.1.2.1.1.1.2 .
candidate lemmas of array(s,next(s)) = true by lm1.4.1.1.2.1.1.1.2 .

ORT of array(s,place(s,r1)) = false .
derived equations of array(s,place(s,r1)) = false by lm1.4.1.1.2.1.1.1.2 .
candidate lemmas of array(s,place(s,r1)) = false by lm1.4.1.1.2.1.1.1.2 .

ORT of pc(s,p) = cs .
derived equations of pc(s,p) = cs by lm1.4.1.1.2.1.1.1.2 .
candidate lemmas of pc(s,p) = cs by lm1.4.1.1.2.1.1.1.2 .


show prsc by lm1.3.1.1.1.2.1 .
list symbolic state forms .
classify assumptions by lm1.3.1.1.1.2.1 .
ORT of array(s,place(s,q)) = true .
derived equations of array(s,place(s,q)) = true by lm1.3.1.1.1.2.1 .
candidate lemmas of array(s,place(s,q)) = true by lm1.3.1.1.1.2.1 .


maude -allow-files cafeinmaude3/cafeInMaude.maude

maude -allow-files auto_LD.maude