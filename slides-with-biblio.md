---
title-slide: false
bibliography: references.bib
csl: vancouver.csl
citeproc: true
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

:::: {.columns}
::: {.column width="50%"}

## Sample slides
#### PlaceHolderName
#### Universiti Malaysia Perlis
#### [placeholder@email.com](mailto:placeholder@email.com)

<audio id="bg-music" src="media/audio/sb.m4a" loop></audio>

<div id="audio-credit"
     style="position: absolute; bottom: 40px; right: 20px; font-size: 0.6em; opacity: 0.6;">
  Music: “Adrift” by Scott Buckley (CC BY 4.0)
</div>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('bg-music');
    const credit = document.getElementById('audio-credit');

    // hide credit by default
    credit.style.display = 'none';

    const test = new Audio('media/audio/bgm.mp3');

    test.addEventListener('canplaythrough', () => {
      // bgm.mp3 exists → use it, keep credit hidden
      audio.src = 'media/audio/bgm.mp3';
    }, { once: true });

    test.addEventListener('error', () => {
      // bgm.mp3 missing → sb.m4a will play → show credit
      credit.style.display = 'block';
    }, { once: true });

    document.addEventListener('click', () => {
      if (Reveal.getIndices().h === 0) {
        audio.volume = 0.5;
        audio.play();
      }
    }, { once: true });

    Reveal.on('slidechanged', (event) => {
      if (event.indexh > 0) { audio.pause(); }
      else { audio.play(); }
    });
  });
</script>

:::

::: {.column width="50%"}
![](media/pics/logo1.png)
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Slide one
**Key Concepts:**
- Energy conservation per @carnot1824.
- $\Delta U = Q - W$
:::

::: {.column width="50%"}
![](media/pics/sample.png)
:::
::::

---

<span class="slide-title" data-title="My Hidden Slide Name"></span>

![](media/pics/wide.jpeg)

---

:::: {.columns}
::: {.column width="50%"}
### The Master Equation
The fundamental relation of thermodynamics:

$$\Delta U = Q - W$$

The work done $W$ is positive when the system expands against an external pressure.
:::

::: {.column width="50%"}
<video data-src="media/videos/sample.mp4" data-autoplay loop muted width="100%"></video>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Visualizing the Gas Law
**Interactive Model:**

- P, V, and T relationships.
- Use the slider to adjust pressure.
- Observe the phase boundary.
:::

::: {.column width="50%"}
<iframe 
  data-src="media/plots/sample.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### PartLength Histograms

Distributions of `PartLength` for each machine, showing their respective frequency profiles.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/partlength_histogram_machine1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### PartLength Histograms (Cont.)

Machine 2 and 3 part length distributions.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/partlength_histogram_machine2.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### PartLength Histograms (Cont.)

Machine 3 part length distribution.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/partlength_histogram_machine3.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Xbar.one Chart (Machine 1)

Control chart for `PartLength` for Machine 1 under specific temperature and pressure conditions. This chart monitors the process mean for individual observations.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/xbar_one_chart_machine1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Xbar.one Chart (Machine 2)

Control chart for `PartLength` for Machine 2.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/xbar_one_chart_machine2.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Xbar.one Chart (Machine 3)

Control chart for `PartLength` for Machine 3.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/xbar_one_chart_machine3.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability (Machine 1)

Capability analysis for `PartLength` for Machine 1, given LSL=45 and USL=55, under specified conditions. This plot assesses if the process meets design specifications.
:::

::: {.column width="50%"}
![](media/plots/capability_machine1.png)
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability (Machine 2)

Capability analysis for `PartLength` for Machine 2.
:::

::: {.column width="50%"}
![](media/plots/capability_machine2.png)
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Process Capability (Machine 3)

Capability analysis for `PartLength` for Machine 3.
:::

::: {.column width="50%"}
![](media/plots/capability_machine3.png)
:::
::::

---
# Bibliography
<div id="refs"></div>
