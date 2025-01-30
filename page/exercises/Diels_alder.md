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
  <button class="tablinks tab-id-1" onclick="openTabId(event, 'tab-1-1', 'tab-id-1')" id="open-1">{{ site.data.icons.code }} <code>command</code></button>
  <button class="tablinks tab-id-1" onclick="openTabId(event, 'tab-1-2', 'tab-id-1')">{{ site.data.icons.codefile }} <code>path.inp</code></button>
</div>
<!-- Tab content -->
<div id="tab-1-1" class="tabcontent tab-id-1" style="text-align:justify">
{% include command.html cmd="xtb start.xyz <span class='nt'>--path</span> end.xyz <span class='nt'>--input</span> path.inp > path.out &" %}
</div>
<div id="tab-1-2" class="tabcontent tab-id-1" style="text-align:justify">
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

{% include defaulttab.html id="open-1" %}


## Growing String Method
Another option for reaction path search is the growing string method (GSM) developed by the Zimmermann group and adapted for xtb. To set it up, you'll need `inpfileq` (provided), `ograd` (provided) which you can download [here](https://github.com/grimme-lab/molecularGSM/releases/tag/rev1).
First, render the executable as
```bash
chmod u+x ograd
```
and a new subdirectory named scratch which includes `tm2orca.py` (provided), and `initial0000.xyz` wherein start.xyz and end.xyz are concatenated after each other. Start the calculation with:
```bash
gsm.orca > gsm.out 2>err &
```
The resulting path should be written to `stringfile.xyz0000`.

### Frequencies

Identify the transition states for the pathfinder and GSM approaches and calculate frequencies for them at the *GFN2-xTB* (gas) level of theory.

```bash
xtb coord.xyz --hess > hess.out &
```

Have a look at the vibrational modes of the transition state in `g98.out` and `vibspectrum` with e.g. molden and check whether the correct TS was found and aligns with your chemical intuition and how both approaches compare.







