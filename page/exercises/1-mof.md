---
layout: default
title: MOF
full_title: Metal 
parent: "Exercises"
nav_order: 1
has_children: false
permalink: page/exercises/MOF
---
# Metal-Organic Materials


Metal organic frameworks (MOFs, 3D) and cages (MOCs, 0D) are important substance classes for the use in organic electronics, carbon capture, solvent sieving, gas filtering, gas storage and many more.
The GFN parametrization can describe all elements up to at least Z=86 and is, therefore, an efficient alternative to standard electronic structure methods for investigating MOFs and MOCs.
In the following, we present an excerpt from a workflow-like compilation of experiments with the HUMJIL MOC (CCDC nomenclature).

## Geometry Optimization

Perform a geometry optimization for `humjil.xyz` in the gas phase and with THF as a solvent (via implicit solvation model - Analytically Linearized Poisson Boltzmann Model) at the *GFN2-xTB*
and *GFN-FF* levels of theory. 
Compare the 4 geometries visually overlaying within e.g. [Chimera](https://www.cgl.ucsf.edu/chimera/) or with a (commandline) RMSD tool.


<div class="tab card">
  <button class="tablinks tab-1-1" onclick="openTabId(event, 'command', 'tab-1-1')" id="defaultOpen">{{ site.data.icons.code }} <code>commands</code></button>
  <button class="tablinks tab-1-1" onclick="openTabId(event, 'struc', 'tab-1-1')">{{ site.data.icons.codefile }}  <code>humjil.xyz</code></button>
</div>
<!-- Tab content -->
<div id="command" class="tabcontent tab-1-1" style="text-align:justify">
{% include command.html cmd="xtb humjil.xyz --opt --gfn 2 --alpb h2o > opt.out &" %}
{% include command.html cmd="xtb humjil.xyz --opt --gff --alpb h2o > opt.out &" %}
{% include command.html cmd="xtb humjil.xyz --opt --gfn 2 > opt.out &" %}
{% include command.html cmd="xtb humjil.xyz --opt --gff > opt.out &" %}


</div>

<div id="struc" class="tabcontent tab-1-1" style="font-size:10px">
{% capture struc_xyz %}
270
Energy =
Pd    0.0000000   -0.0000000   -9.3798511 
N    -1.3354224   -0.5674368   -7.8625033 
C    -1.2764300   -1.7910299   -7.3066982 
H    -0.5696081   -2.4832666   -7.7376007 
C    -2.0841670   -2.1621617   -6.2461927 
H    -2.0012811   -3.1569726   -5.8406101 
C    -2.9976205   -1.2508124   -5.7156836 
C    -3.8300020   -1.5896796   -4.5281567 
N    -4.6170320   -0.6330408   -4.0213480 
C    -5.3146620   -0.9673456   -2.9289736 
C    -6.1665561    0.0786934   -2.2984962 
C    -6.9112742   -0.1849734   -1.1484659 
H    -6.9315650   -1.1735558   -0.7202096 
C    -7.6384137    0.8293590   -0.5503892 
H    -8.2294635    0.6447898    0.3335154 
N    -7.6601257    2.0830703   -1.0381398 
C    -6.9783362    2.3389052   -2.1692700 
H    -7.0502987    3.3423151   -2.5598749 
Pd   -8.6656352    3.6201240   -0.0228356 
N    -9.7389978    5.0783740    0.8896466 
C    -9.2788257    5.9114056    1.8347371 
H    -8.2515049    5.7930855    2.1323057 
C   -10.0783495    6.8816614    2.4080625 
H    -9.6689237    7.5312355    3.1660863 
C   -11.3963152    6.9997045    1.9943720 
H   -12.0468695    7.7480618    2.4227445 
C   -11.8711153    6.1394692    1.0181582 
H   -12.8941718    6.2213890    0.6882777 
C   -11.0328811    5.1784913    0.4698386 
C   -11.4264608    4.2281294   -0.5549908 
C   -12.6924008    4.1571177   -1.1199336 
H   -13.4678358    4.8366298   -0.8047396 
C   -12.9662894    3.2109716   -2.0935812 
H   -13.9506150    3.1541725   -2.5348556 
C   -11.9586056    2.3442347   -2.4876506 
C   -10.7129958    2.4501151   -1.8989897 
H    -9.9088703    1.7935085   -2.1823282 
H   -12.1299920    1.5926167   -3.2425626 
N    -6.8738894    3.9822651    1.0085774 
C    -6.5994280    3.3459561    2.1617906 
H    -7.3776777    2.7143489    2.5616291 
C    -5.3909927    3.4946365    2.8195921 
H    -5.2232193    2.9663498    3.7436702 
C    -4.4073466    4.3280932    2.2862148 
C    -3.0685241    4.4559181    2.9255083 
N    -2.1733114    5.2675612    2.3497260 
C    -0.9711032    5.3213206    2.9355092 
C     0.0749749    6.1730150    2.3050245 
C    -0.1895719    6.9198634    1.1566198 
H    -1.1788191    6.9424831    0.7300211 
C     0.8250569    7.6458117    0.5577917 
H     0.6405173    8.2380863   -0.3252551 
N     2.0796000    7.6645599    1.0435061 
C     2.3362599    6.9812641    2.1735583 
H     3.3404300    7.0510823    2.5625613 
Pd    3.6152242    8.6664942    0.0241441 
N     3.3615457   10.4523390    0.9512402 
C     4.2226793   11.4295410    0.5458256 
C     4.1510129   12.6979107    1.1053085 
C     3.2047536   12.9754995    2.0779332 
C     2.3384396   11.9690555    2.4763261 
H     1.5866689   12.1432771    3.2303716 
H     3.1476985   13.9615659    2.5152620 
H     4.8300800   13.4724937    0.7869000 
C     5.1730734   11.0319911   -0.4777617 
C     6.1341972   11.8678789   -1.0294255 
H     6.2168904   12.8919583   -0.7030208 
C     6.9940783   11.3894738   -2.0042581 
C     6.8754788   10.0701263   -2.4133624 
H     7.5245408    9.6578250   -3.1702471 
C     5.9051647    9.2729696   -1.8368538 
H     5.7866105    8.2446265   -2.1307425 
H     7.7427438   12.0382143   -2.4349336 
C     2.4447857   10.7209432    1.8928576 
H     1.7882839    9.9179410    2.1796554 
N     3.9757621    6.8713412   -1.0029936 
C     4.8140842    5.9464257   -0.5013019 
H     5.3438074    6.2132013    0.4002682 
C     5.0081670    4.7172035   -1.1064086 
H     5.6942850    4.0128578   -0.6658077 
C     4.3202863    4.4033585   -2.2789230 
C     4.4484021    3.0644926   -2.9183365 
N     5.2601788    2.1693359   -2.3426616 
C     5.3146620    0.9673456   -2.9289736 
C     6.1665561   -0.0786934   -2.2984962 
C     6.2308167   -1.3720128   -2.8177975 
C     6.9783362   -2.3389052   -2.1692700 
H     7.0502987   -3.3423151   -2.5598749 
N     7.6601257   -2.0830703   -1.0381398 
C     7.6384137   -0.8293590   -0.5503892 
H     8.2294635   -0.6447898    0.3335154 
Pd    8.6656352   -3.6201240   -0.0228356 
N     9.7389978   -5.0783740    0.8896466 
C     9.2788257   -5.9114056    1.8347371 
H     8.2515049   -5.7930855    2.1323057 
C    10.0783495   -6.8816614    2.4080625 
H     9.6689237   -7.5312355    3.1660863 
C    11.3963152   -6.9997045    1.9943720 
H    12.0468695   -7.7480618    2.4227445 
C    11.8711153   -6.1394692    1.0181582 
H    12.8941718   -6.2213890    0.6882777 
C    11.0328811   -5.1784913    0.4698386 
C    11.4264608   -4.2281294   -0.5549908 
C    12.6924008   -4.1571177   -1.1199336 
H    13.4678358   -4.8366298   -0.8047396 
C    12.9662894   -3.2109716   -2.0935812 
H    13.9506150   -3.1541725   -2.5348556 
C    11.9586056   -2.3442347   -2.4876506 
C    10.7129958   -2.4501151   -1.8989897 
H     9.9088703   -1.7935085   -2.1823282 
H    12.1299920   -1.5926167   -3.2425626 
N     6.8738894   -3.9822651    1.0085774 
C     6.5994280   -3.3459561    2.1617906 
H     7.3776777   -2.7143489    2.5616291 
C     5.3909927   -3.4946365    2.8195921 
H     5.2232193   -2.9663498    3.7436702 
C     4.4073466   -4.3280932    2.2862148 
C     3.0685241   -4.4559181    2.9255083 
N     2.1733114   -5.2675612    2.3497260 
C     0.9711032   -5.3213206    2.9355092 
C    -0.0749749   -6.1730150    2.3050245 
C     0.1895719   -6.9198634    1.1566198 
C    -0.8250569   -7.6458117    0.5577917 
H    -0.6405173   -8.2380863   -0.3252551 
N    -2.0796000   -7.6645599    1.0435061 
C    -2.3362599   -6.9812641    2.1735583 
H    -3.3404300   -7.0510823    2.5625613 
Pd   -3.6152242   -8.6664942    0.0241441 
N    -3.3615457  -10.4523390    0.9512402 
C    -2.4447857  -10.7209432    1.8928576 
H    -1.7882839   -9.9179410    2.1796554 
C    -2.3384396  -11.9690555    2.4763261 
H    -1.5866689  -12.1432771    3.2303716 
C    -3.2047536  -12.9754995    2.0779332 
H    -3.1476985  -13.9615659    2.5152620 
C    -4.1510129  -12.6979107    1.1053085 
H    -4.8300800  -13.4724937    0.7869000 
C    -4.2226793  -11.4295410    0.5458256 
C    -5.1730734  -11.0319911   -0.4777617 
C    -6.1341972  -11.8678789   -1.0294255 
H    -6.2168904  -12.8919583   -0.7030208 
C    -6.9940783  -11.3894738   -2.0042581 
H    -7.7427438  -12.0382143   -2.4349336 
C    -6.8754788  -10.0701263   -2.4133624 
C    -5.9051647   -9.2729696   -1.8368538 
H    -5.7866105   -8.2446265   -2.1307425 
H    -7.5245408   -9.6578250   -3.1702471 
N    -5.0725592   -9.7366665   -0.8930907 
N    -3.9757621   -6.8713412   -1.0029936 
C    -4.8140842   -5.9464257   -0.5013019 
H    -5.3438074   -6.2132013    0.4002682 
C    -5.0081670   -4.7172035   -1.1064086 
H    -5.6942850   -4.0128578   -0.6658077 
C    -4.3202863   -4.4033585   -2.2789230 
C    -4.4484021   -3.0644926   -2.9183365 
C    -3.4860022   -5.3865083   -2.8119413 
H    -2.9564644   -5.2177099   -3.7350489 
C    -3.3380182   -6.5955279   -2.1551077 
H    -2.7056723   -7.3732675   -2.5549008 
H     1.1788191   -6.9424831    0.7300211 
C    -1.3691318   -6.2344812    2.8225426 
H    -1.6255439   -5.7080812    3.7270802 
N     0.6364106   -4.6228885    4.0271963 
C     1.5930887   -3.8360611    4.5340651 
C     1.2535958   -3.0024172    5.7203347 
C     0.0019851   -3.0828416    6.3315166 
C    -0.3037111   -2.2445696    7.3892863 
H    -1.2612698   -2.2985820    7.8840285 
N     0.5684861   -1.3360543    7.8630959 
C     1.7923601   -1.2777475    7.3078634 
H     2.4840975   -0.5697951    7.7376313 
Pd   -0.0000000    0.0000000    9.3790567 
N     0.5430832   -1.1894033   10.9288782 
C     0.3070136   -0.6577260   12.1624934 
C     0.6523556   -1.3661518   13.3050255 
H     0.4691120   -0.9471030   14.2813657 
C     1.2376001   -2.6166789   13.1960775 
H     1.5079827   -3.1694234   14.0837333 
C     1.4694338   -3.1401658   11.9334328 
H     1.9238786   -4.1101228   11.8043495 
C    -0.3070136    0.6577260   12.1624934 
C    -0.6523556    1.3661518   13.3050255 
H    -0.4691120    0.9471030   14.2813657 
C    -1.2376001    2.6166789   13.1960775 
H    -1.5079827    3.1694234   14.0837333 
C    -1.4694338    3.1401658   11.9334328 
H    -1.9238786    4.1101228   11.8043495 
C    -1.1103515    2.4002125   10.8230239 
H    -1.2775969    2.7762196    9.8288037 
C     1.1103515   -2.4002125   10.8230239 
H     1.2775969   -2.7762196    9.8288037 
N    -0.5430832    1.1894033   10.9288782 
N    -0.5684861    1.3360543    7.8630959 
C    -1.7923601    1.2777475    7.3078634 
H    -2.4840975    0.5697951    7.7376313 
C    -2.1642924    2.0874592    6.2492125 
H    -3.1591016    2.0048759    5.8435728 
C    -1.2535958    3.0024172    5.7203347 
C    -0.0019851    3.0828416    6.3315166 
H     0.7316469    3.7957848    5.9929975 
C    -1.5930887    3.8360611    4.5340651 
C     0.3037111    2.2445696    7.3892863 
H     1.2612698    2.2985820    7.8840285 
H    -0.7316469   -3.7957848    5.9929975 
C     2.1642924   -2.0874592    6.2492125 
H     3.1591016   -2.0048759    5.8435728 
N     2.8213392   -3.7187883    4.0151154 
C     4.7203104   -5.0152270    1.1130627 
H     4.0156767   -5.7011808    0.6725395 
C     5.9488811   -4.8205665    0.5070309 
H     6.2151987   -5.3495556   -0.3950890 
N    10.4479301   -3.3666895   -0.9563373 
H     5.7064551   -1.6279445   -3.7236404 
C     6.9112742    0.1849734   -1.1484659 
H     6.9315650    1.1735558   -0.7202096 
N     4.6170320    0.6330408   -4.0213480 
C     3.8300020    1.5896796   -4.5281567 
C     2.9976205    1.2508124   -5.7156836 
C     2.0841670    2.1621617   -6.2461927 
H     2.0012811    3.1569726   -5.8406101 
C     1.2764300    1.7910299   -7.3066982 
H     0.5696081    2.4832666   -7.7376007 
C     3.0782890   -0.0007394   -6.3269784 
H     3.7899449   -0.7349724   -5.9870696 
C     2.2423030   -0.3054806   -7.3868810 
H     2.2971622   -1.2627864   -7.8820269 
N     3.7118021    2.8174997   -4.0083532 
C     3.4860022    5.3865083   -2.8119413 
H     2.9564644    5.2177099   -3.7350489 
C     3.3380182    6.5955279   -2.1551077 
H     2.7056723    7.3732675   -2.5549008 
N     5.0725592    9.7366665   -0.8930907 
C     1.3691318    6.2344812    2.8225426 
H     1.6255439    5.7080812    3.7270802 
N    -0.6364106    4.6228885    4.0271963 
N    -2.8213392    3.7187883    4.0151154 
C    -4.7203104    5.0152270    1.1130627 
H    -4.0156767    5.7011808    0.6725395 
C    -5.9488811    4.8205665    0.5070309 
H    -6.2151987    5.3495556   -0.3950890 
N   -10.4479301    3.3666895   -0.9563373 
C    -6.2308167    1.3720128   -2.8177975 
H    -5.7064551    1.6279445   -3.7236404 
N    -5.2601788   -2.1693359   -2.3426616 
N    -3.7118021   -2.8174997   -4.0083532 
C    -3.0782890    0.0007394   -6.3269784 
H    -3.7899449    0.7349724   -5.9870696 
C    -2.2423030    0.3054806   -7.3868810 
H    -2.2971622    1.2627864   -7.8820269 
N     1.3354224    0.5674368   -7.8625033 
N     1.1902163    0.5416441  -10.9298751 
C     2.4018344    1.1073285  -10.8241635 
H     2.7780627    1.2745780   -9.8299210 
C     3.1424714    1.4648923  -11.9345913 
H     4.1130954    1.9180941  -11.8056847 
C     2.6188939    1.2331385  -13.1972060 
H     3.1721798    1.5023782  -14.0849403 
C     1.3675233    0.6497181  -13.3060998 
H     0.9484020    0.4668439  -14.2824633 
C     0.6582706    0.3059091  -12.1635150 
C    -0.6582706   -0.3059091  -12.1635150 
C    -1.3675233   -0.6497181  -13.3060998 
C    -2.6188939   -1.2331385  -13.1972060 
C    -3.1424714   -1.4648923  -11.9345913 
C    -2.4018344   -1.1073285  -10.8241635 
H    -2.7780627   -1.2745780   -9.8299210 
H    -4.1130954   -1.9180941  -11.8056847 
H    -3.1721798   -1.5023782  -14.0849403 
H    -0.9484020   -0.4668439  -14.2824633 
N    -1.1902163   -0.5416441  -10.9298751 
{% endcapture %}
{% include codecell.html content=struc_xyz %}
</div>
{% include defaulttab.html %}


## Docking 

Use the optimized structure from the previous exercise at the *GFN2-xTB* (gas) level of theory and perform a docking with a CO<sub>2</sub> molecule at the same level of theory. The **aISS** docking module can be called as follows:

 <!-- Tab links -->
<div class="tab card">
  <button class="tablinks tab-id-1" onclick="openTabId(event, 'tab-1-1', 'tab-id-1')" id="open-1">{{ site.data.icons.code }} <code>command</code></button>
  <button class="tablinks tab-id-1" onclick="openTabId(event, 'tab-1-2', 'tab-id-1')">{{ site.data.icons.codefile }} <code>co2.xyz</code></button>
</div>
<!-- Tab content -->
<div id="tab-1-1" class="tabcontent tab-id-1" style="text-align:justify">
{% include command.html cmd="xtb dock humjil_opt.xyz co2.xyz <span class='nt'>--gfn 2</span> <span class='nt'>--nfinal 2</span> > aiss.out &" %}
</div>
<div id="tab-1-2" class="tabcontent tab-id-1" style="text-align:justify">
{% capture struc_file %}
3

C          0.00765        0.03540        0.00000
O         -1.17431       -0.14918        0.00000
O          1.18955        0.22040        0.00000
{% endcapture %}
{% include codecell.html content=struc_file style="font-size:10px" %}
</div>

{% include defaulttab.html id="open-1" %}


Options: \\
**--nfinal \<INT\>** - to produce more structures.

The energetically best structure can be found in the `best.xyz` file.
For the docking, similar flags can be used as for a geometry optimization. For example, implicit solvation can also be employed by providing the *--alpb* flag.

{% include warning.html content=
'Be aware, the order matters. In the current arrangement of **.xyz** files the CO<sub>2</sub> is docked to the MOC. If you switch the order the computation time will be larger as the MOC is docked to  CO<sub>2</sub>. To save computiational time for this workshop, the number of final structures optimized with *GFN2-xTB* was limited to 2. Per default, 15 structures are produced.'%}


## Molecular Dynamics

Use the docked structure from the previous exercise to perform a molecular dynamics (MD) simulation at the *GFN-FF* (gas) level of theory. You'll need a second input file `md.inp` besides the coordinate file:

 <!-- Tab links -->
<div class="tab card">
  <button class="tablinks tab-id-2" onclick="openTabId(event, 'tab-2-1', 'tab-id-2')" id="open-2">{{ site.data.icons.code }} <code>command</code></button>
  <button class="tablinks tab-id-2" onclick="openTabId(event, 'tab-2-2', 'tab-id-2')">{{ site.data.icons.codefile }} <code>md.inp</code></button>
</div>
<!-- Tab content -->
<div id="tab-2-1" class="tabcontent tab-id-2" style="text-align:justify">
{% include command.html cmd="xtb docked_coord.xyz <span class='nt'>--md</span> <span class='nt'>--gfnff</span> <span class='nt'>-I</span> md.inp > md.out &" %}
</div>
<div id="tab-2-2" class="tabcontent tab-id-2" style="text-align:justify">
{% capture struc_file %}
$md
   temp=298     # temperature in K
   time=20.0   # duration in ps
   dump=300.0   # coordinate dump interval in fs
   step=2.0     # stepsize in fs
   velo=false   # scale velocities
   nvt=true     # uses NVT ensemble
   hmass=4      # increased hydrogen mass for FF stability
   shake=2      # constrain all bonds from breaking
   sccacc=2.0   # SCC accuracy
$end

{% endcapture %}
{% include codecell.html content=struc_file style="font-size:10px" %}
</div>

{% include defaulttab.html id="open-2" %}



{% include note.html content= 'This calculation can take about 10 minutes.'%}

Before you list any content of this directory when the calculation has finished, remove all `scoord` files:
```bash
rm scoord*
```
Have a look at the simulation by openning the `xtb.trj` file with, e. g., [Molden](https://www.theochem.ru.nl/molden/) 
