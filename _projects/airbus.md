---
layout: page
title: Photogrammetry and LiDAR analysis at Airbus
description: Designed a computer vision solution using LiDAR and photogrammetry data to assist aircraft fuselage inspection. # The prototype helped automate geometric analysis and contributed to reducing A350 repair costs.
img: assets/img/reconvertai/airbus-vehicle.png
importance: 2
category: Machine Learning
giscus_comments: false
---

**NOTE:** Project delivered under NDA; only non-confidential details are shared here.

For my final project at Paris Digital Lab, I worked with Airbus on improving the aircraft repainting and surface inspection process. This is a critical maintenance phase during which surface defects must be repaired, documented, and precisely referenced so that they can be tracked in future inspections.

The existing referencing workflow required aircraft to remain immobilised for several days, creating significant operational costs. Our objective was to reduce this downtime by developing a lightweight digital solution capable of localising damaged areas directly from smartphone-based scans.

I contributed to the design and implementation of an end-to-end computer vision workflow combining photogrammetry, visual odometry, and 3D visualisation. The system used camera pose estimation to recover positional information during the scanning process, allowing defects observed in images to be associated with their approximate location on the aircraft surface.

I also developed a Blender add-on to visualise the reconstructed environment and navigate efficiently between recorded damaged areas. This provided a practical interface for reviewing, locating, and managing surface defects in a 3D context.

The resulting prototype contributed to a threefold acceleration of the damage referencing process, reducing aircraft immobilisation time and supporting more efficient maintenance operations.

As part of the project, I travelled to Airbus Toulouse to present and demonstrate the application in a real maintenance context. This live demonstration helped validate the usability of the workflow and its relevance for aircraft surface damage localisation.

**Keywords:** photogrammetry, computer vision, SLAM, visual odometry, 3D visualisation, Blender, aircraft maintenance.

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/reconvertai/blender-main.png" title="Blender main view" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/reconvertai/blender-addon.png" title="Blender addon" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
    Figure 1: Scanned Vehicle data imported in blender.
</div>


<div class="row" justify-content-sm-center>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/reconvertai/blender-inspect-area.png" title="highlighted region" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2: Defect identified within the highlighted region. The application provides access to the corresponding high-resolution image and the spatial coordinates of the damaged area.
</div>
