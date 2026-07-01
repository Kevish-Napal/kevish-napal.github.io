---
layout: page
title: cloaking
description: the use of resonators in a metasurface allows to filter specific frequencies. This project was supported by dstl.
img: assets/img/SummerInternship2022/resonators.png
importance: 2
category: Random Media
giscus_comments: false
---


[report](../../assets/pdf/SummerInternship.pdf)
# 1 Executive summary

There has been evidence that metamaterial cloaking is an effective method in blurring the
scattered fields from coated targets in response to probing waves. In this work, we investigate
the possibility of creating an object that cannot be detected by radar-like detection techniques.
Our goal is to make the object unrecognizable, before attempting to make it appear as if it were
a completely different object in future works. To achieve this, we design a metamaterial cloaking
which contains a layer of resonators. These resonators are not aligned and we show that their
random orientation along with their number and type can influence significantly the behaviour
of the cloaking. The interesting properties of such metamaterials are highlighted in numerical
simulations carried out in a simplified 2D acoustic framework. Early findings show that cloaking
prevents from empirical learning of the cloaking behaviour from coated engines, since each coated
engine would use a specific set of parameters and have a unique signature. At the same time,
the more diverse the possible behaviours, the more feasible it is to choose parameters mimicking
the signature of some other object. Finally, we demonstrate the advantage of using resonators
rather than square-shaped components and we discuss the possibility of replacing resonators
with simpler components.

# 2 Introduction

In noise canceling, cavity resonators are useful as they can stop incoming signals, such as acoustic
and electromagnetic waves. The technique is rather simple: a protected area is surrounded by
particles that resonate at a given frequency k in order to trap incoming waves of the same
frequency. Based on this idea, one can imagine using a mix of different types of particles, each
one resonating at a different frequency, in order to filter specific frequencies. A natural framework to investigate the behavior of such materials is multiple scattering theory. This field studies the average properties of materials made of many particles, whose locations are not exactly known,
but described with a probability distribution instead. In an industrial perspective, the advantage
of this approach is that the particulate material does not need a specific structure, simplifying
its manufacturing process.

The goal of this internship is to design metamaterial surfaces that prevent radar/sonar track-
ing from identifying a target. By including resonators in the cloaking, we are able to trap waves
with specific frequencies and orientations. More specifically, we are interested in distorting the
signal with cloaks using a random component so that each cloaked device has a different signa-
ture, making them harder to catalogue. We carry our investigations in a 2D acoustic setting.
Our simulation results rely on the Foldy-Lax self consistent method [1], a technique describing
the interaction of waves with several obstacles. This technique requires to know the behavior of
each isolated scatterer with respect to the incoming waves. All of this information is contained
in the so-called T-matrix which only depends on the properties of the scatterer (shape, material,
etc.). Work on the derivation of the T-matrix for the case of a Helmholtz resonator has been
carried out in the papers [5, 4]. Multiple scattering problems can be numerically solved with the
MultipleScattering.jl library written in the Julia language [6], which we have used throughout
this work.


# 3 Methodology
## 3.1 A simplified model in 2D

We investigate the effectiveness of resonator barriers in cloaking larger objects in a simple 2D
setting. For these tests we will use a large disk to represent the target, for instance the cockpit
of a helicopter. To validate our results, we illuminate the target and measure the resulting
scattered fields on sensors placed on a screen located behind the source (cf Figure 1). We then
compare the results of a cloaked and uncloaked target in this setting.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/methodology.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1: Target detection using waves.
</div>


## 3.2 Design of a cloaking

The cloak consists of a layer of resonators covered with an extra protective layer (cf Figure 2).
This arrangement is supposed to mimic how these resonators might attach to an object that
needs to be cloaked with glue or paint. The orientations of the resonators are voluntarily chosen
to be random for two main reasons. First, the manufacturing process of the cloaking is rather
simple since they only need to be glued together in a matrix, without any precautions on their
orientations. Second, each cloak will be unique, making it difficult to catalogue the cloaked
targets. In our numerical experiments, we use simulated Helmholtz resonators made of a cavity
and a mouth. Their different sizes and properties are given in Table 1.

<div class="row ">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/cloaked3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2: Target cloaked with a layer of resonators and an external protective layer.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/ExcitedResonator_2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/UnexcitedResonator.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Figure 3: Response of a simulated resonator at a resonating frequency ω1 = 3.99 (left) and a non
resonating frequency ω = 2.77 (right).
</div>


# 3.3 Efficiency of the cloaking
## Response distortion
To measure the efficiency of the cloaking, we will qualitatively compare the simulated data
from a cloaked and an uncloaked target. To visualise the effect of the cloak, we computed the
scattered field near the boundary of the cloaked and uncloaked target (cf Figure 4). We see
that the presence of the resonators significantly distorts the fields. Indeed, while most of the
energy released by the uncloaked target is confined in cones, it is spread in all directions in the
case of the cloaked target. We outline the impact of the coat in more details in Figure 5, where
the measurements at the sensors are plotted for both the cloaked and uncloaked target. An
important observation is that while the profile of the uncloaked target is almost the same for the
two different frequencies, especially around the sensors in the middle, the profile of the cloaked
target significantly changes.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/big_sphere.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/cloaked3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/uncloaked_scattering.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/cloak_scattering.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Figure 4: Scattered fields near the uncloaked target (left) and cloaked target (right).
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/general_effect4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/SummerInternship2022/general_effect6.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Figure 5: The scattered fields are measured on vertically aligned sensors. Adding the cloak distorts the response of the uncloaked object. The results are displayed for frequencies ω = ω0 = 1.99 (top) and ω = 2.67 (bottom).
</div>