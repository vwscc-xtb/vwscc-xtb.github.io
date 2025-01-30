---
layout: default
title: Diels Alder Reaction
parent: "Exercises"
nav_order: 3
has_children: false
permalink: page/exercises/dar
---

# {{ page.title }}

A frequent experiment in computational chemistry is mechanism elucidation which requires reaction path searches. Of course the here presented example is so small that a DFT path search would easily be doable but for the sake of simplicity we nevertheless go for a plain Diels-Alder reaction at the *GFN2-xTB* (gas) level.

## Optional Exercise

{% include image.html file="dielsalderrct.png" alt="CREST" max-width=600 %}

Build the input structures (buta-1,3-diene and but-2-ene) yourself with a molecular editor, e.g. avogadro. Pay attention that the atom order is the same in the start and end structure.

## Pathfinder
Perform a reaction path search at the *GFN2-xTB* (gas) level of theory for the given reactants. You need the following input file (`path.inp`) in addition to your coordinate files:

 <!-- Tab links -->
<div class="tab card">
  <button class="tablinks tab-id-3-1" onclick="openTabId(event, 'command-3-1', 'tab-id-3-1')" id="open-3-1">{{ site.data.icons.code }} <code>command</code></button>
  <button class="tablinks tab-id-3-1" onclick="openTabId(event, 'struc-3-1', 'tab-id-3-1')">{{ site.data.icons.codefile }} <code>path.inp</code></button>
</div>
<!-- Tab content -->
<div id="command-3-1" class="tabcontent tab-id-3-1" style="text-align:justify">
{% include command.html cmd="xtb start.xyz <span class='nt'>--path</span> end.xyz <span class='nt'>--input</span> path.inp > path.out &" %}
</div>
<div id="struc-3-1" class="tabcontent tab-id-3-1" style="text-align:justify">
{% capture struc_file %}
$path
nrun=1 # number of runs
npoint=25 # number of points on path
anopt=10 # how many optimization steps per point
kpush=0.003 # push factor for path search
kpull=-0.015 # pull factor for path search
ppull=0.05
alp=1.2
$end

{% endcapture %}
{% include codecell.html content=struc_file style="font-size:10px" %}
</div>

The resulting path should be written to `xtbpath.xyz`.

{% include defaulttab.html id="open-3-1" %}


## Growing String Method
Another option for reaction path search is the growing string method (GSM) developed by the Zimmermann group and adapted for xtb. To set it up, you'll need `inpfileq` (provided), `ograd` (provided) which you can download [here](https://github.com/grimme-lab/molecularGSM/releases/tag/rev1).

First. unpack the downloaded archive and place the `gsm.orca` program in your path.
Next, go to your working directory and place `inpfileq` and `ograd` there.
Then, you have to create a direcotry named `scratch` and move the `tm2orca.py` script into it.
Concatenate the start.xyz and end.xyz file into `initial0000.xyz` and move the latter also into the scratch directory. 
Finally, make the `ograd` and `tm2orca.py` scripts are executable with
```bash
chmod u+x ograd
chmod u+x scratch/tm2orca.py
```
Start the calculation with the following command or use the `run.sh` script to check if you followed all the above steps and all files are in the correct location.

<!-- Tab links -->
<div class="tab card">
  <button class="tablinks tab-id-3-2" onclick="openTabId(event, 'command-3-2', 'tab-id-3-2')" id="open-3-2">{{ site.data.icons.code }} <code>command</code></button>
  <button class="tablinks tab-id-3-2" onclick="openTabId(event, 'struc-3-2', 'tab-id-3-2')">{{ site.data.icons.codefile }} <code>run.sh</code></button>
</div>
<!-- Tab content -->
<div id="command-3-2" class="tabcontent tab-id-3-2" style="text-align:justify">
{% include command.html cmd="gsm.orca > gsm.out 2> end &" %}
</div>
<div id="struc-3-2" class="tabcontent tab-id-3-2" style="text-align:justify">
{% capture run_file %}
#!/bin/bash

if ! command -v gsm.orca >/dev/null 2>&1; then
    echo "The program 'gsm.orca' was not found."
    exit 1
fi

if ! command -v xtb >/dev/null 2>&1; then
    echo "The program 'xtb' was not found."
    exit 1
fi

if [[ ! -f "ograd" ]]; then
    echo "The file 'ograd' was not found."
    exit 1
fi

if [[ ! -x "ograd" ]]; then
    echo "The file 'ograd' is not executable."
    exit 1
fi

if [[ ! -d "scratch" ]]; then
    echo "The directory 'scratch' was not found."
    exit 1
fi

if [[ ! -f "scratch/initial0000.xyz" ]]; then
    echo "The file 'scratch/initial0000.xyz' was not found."
    echo "You can create it with the following command:"
    echo "cat start.xyz end.xyz > scratch/initial0000.xyz"
    exit 1
fi

if [[ ! -f "scratch/tm2orca.py" ]]; then
    echo "The file 'scratch/tm2orca.py' was not found."
    exit 1
fi

if [[ ! -x "scratch/tm2orca.py" ]]; then
    echo "The file 'scratch/tm2orca.py' is not executable."
    exit 1
fi

gsm.orca > gsm.out 2> err &

{% endcapture %}
{% include codecell.html content=run_file style="font-size:10px" %}
</div>
{% include defaulttab.html id="open-3-2" %}

The resulting path is written to `stringfile.xyz0000` and can be used to find the transition state.

### Frequencies

Identify the transition states for the pathfinder and GSM approaches and calculate frequencies for them at the *GFN2-xTB* (gas) level of theory.

```bash
xtb coord.xyz --hess > hess.out &
```

Have a look at the vibrational modes of the transition state in `g98.out` and `vibspectrum` with e.g. molden and check whether the correct TS was found and aligns with your chemical intuition and how both approaches compare.







