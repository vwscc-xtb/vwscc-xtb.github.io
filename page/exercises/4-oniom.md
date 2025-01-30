---
layout: default
title: ONIOM
parent: "Exercises"
nav_order: 4
has_children: false
permalink: page/exercises/oniom
---

# {{ page.title }}

The ONIOM scheme is a multiscale scheme approach used to treat large systems efficiently using divide-and-conquer approach.
The general idea is to divide the system into different subregions: in this case inner and outer, and then calculate them with the different levels of theory.
This way it is possible to boost the computation efficiency and still keep the required accuracy of the region of the intesrest (e.g. ligand pocket in proteins).


## Define Inner region
In order to perform ONIOM calculation with xtb, the first step is to define the inner region of the system. Please, use the molecuar visualizer of your choice that can show atom numbers and try to define the arbitrary inner of the DALTES MOC:
 <!-- Tab links -->
<div class="tab card">
  <button class="tablinks tab-id-1" onclick="openTabId(event, 'command', 'tab-id-1')" id="defaultOpen">{{ site.data.icons.code }} <code>daltes.xyz</code></button>
</div>

<div id="struc" class="tabcontent tab-id-1" style="font-size:10px">
{% capture struc_xyz %}

{% endcapture %}
{% include codecell.html content=struc_xyz %}
</div>

{% include note.html content='The boundaries arising from the artificial system decomposition should be properly defined. As the general rule the bonds that higher than single bonds are not a good choice.'%}

## Dry-Run
After defining the inner region, it is possible to dry-run xtb to check if the specified region is the appropriate from the topological point: