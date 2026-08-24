## Auto Lemma Discovery Support Tool base on IPSG. 

This support tool is implemented on top of Invariant Proof Scores Generator - IPSG (https://github.com/duongtd23/IPSG-tool).
This tool requires Maude version not lower than Maude 3.2 (https://github.com/SRI-CSL/Maude).
To run the tool, first you need to install Maude, which can be found from here: http://maude.cs.illinois.edu/w/index.php/Maude_download_and_installation.
Once Maude is installed, you can try to run the tool with the following commands:

```bash
$ maude -allow-files ld.maude
IPSG> load examples/TAS/tas.cafe .
IPSG> load examples/TAS/input.cafe .
```

where the first command starts the tool, the second command loads the Qlock specification, and the last command loads the input file, which asks the tool to generate the proof scores to prove Qlock enjoys the mutual exclusion properties (i.e., the proof score of `mutex`).

### Test for QLOCK 
```bash
load examples/Qlock/qlock.cafe .
load examples/Qlock/input.cafe .
list false cases .
show prsc by mutex.3.1.1.1.2.1 .
list symbolic state forms .
classify assumptions by mutex.3.1.1.1.2.1 .
ORT of pc(s,q) = cs .
derived equations of pc(s,q) = cs by mutex.3.1.1.1.2.1 .
candidate lemmas of pc(s,q) = cs by mutex.3.1.1.1.2.1 .
```

### Test for TAS
```bash
load examples/TAS/tas.cafe .
load examples/TAS/input.cafe .
list false cases .
show prsc by mutex.2.1.2.1.2.1 .
list symbolic state forms .
classify assumptions by mutex.2.1.2.1.2.1 .
ORT of pc(s,q) = cs .
derived equations of pc(s,q) = cs by mutex.2.1.2.1.2.1 .
candidate lemmas of pc(s,q) = cs by mutex.2.1.2.1.2.1 .
```
