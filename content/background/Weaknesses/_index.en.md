---
title: "Weaknesses"
#date: 2018-12-29T11:02:05+06:00
weight: 4
draft: false
---

### Validation of accuracy

The focus of almost all previous validation work on the CGM has been on how repeatable the model is with very little consideration of how accurate. Where such studies have been conducted they have focussed on very specific properties such as the location of the hip joint centre (
[Sangeux et al. 2011](http://dx.doi.org/j.gaitpost.2011.05.019),
[Peters et al. 2012](http://dx.doi.org/10.1016/j.gaitpost.2012.03.011),
[Sangeux et al. 2014](http://dx.doi.org/10.1016/j.gaitpost.2014.01.024))
and knee joint axis ([Sauret et al. 2016](http://dx.doi.org/10.1016/j.jbiomech.2006.10.026);
[Passmore and Sangeux, 2016](http://dx.doi.org/10.1016/j.gaitpost.2016.02.006)).
The model is intended to track the movement of the bones and there have been no studies performed to establish how accurately it is able to do this.

Whilst this is a serious criticism it is a general weakness of all current biomechanical models designed for gait analysis and stems from the lack of a robust and straightforward gold standard with which to compare it.

### Hip joint centre position

Over the lifetime of the CGM There has been an almost obsessional concern over the accuracy of the hip joint centre within biomechanical models designed for clinical gait analysis and a considerable body of knowledge now suggests that there are better methods available than those implemented within the CGM (
[Leardini et al. 1999](http://dx.doi.org/10.1016/S0021-9290(98%2900148-1));
[Harrington et al. 2007](http://dx.doi.org/10.1016/j.jbiomech.2006.02.003);
[Sangeux et al. 2011](http://dx.doi.org/j.gaitpost.2011.05.019);
[Peters et al. 2012](http://dx.doi.org/10.1016/j.gaitpost.2012.03.011);
[Sangeux et al. 2014](http://dx.doi.org/10.1016/j.gaitpost.2014.01.024)).

Whilst the early studies suggested that functional calibration was inherently superior to the use of predictive equations later work has shown that the problem is with the specific equations used and that better predictive equations can give results that are at least as valid as functional methods for healthy adults (
[Sangeux et al. 2011](http://dx.doi.org/j.gaitpost.2011.05.019);
[Sangeux et al. 2014](http://dx.doi.org/10.1016/j.gaitpost.2014.01.024))
and better in children with disabilities ([Peters et al. 2012](http://dx.doi.org/10.1016/j.gaitpost.2012.03.011)).

### Defining the coronal plane of the femur

One of the Helen Hayes first papers ([Ramikrishnan et al., 1991](http://dx.doi.org/10.1016/0021-9290(91%2990175-M)) was an in depth analysis of the sensitivity of model outputs to misplacement of the thigh wand. The systematic review of [McGinley et al. 2009](http://dx.doi.org/10.1016/j.gaitpost.2008.09.003) demonstrates that measures of hip rotation are still nearly twice as variable as the worst of the other kinematic outputs. Use of the KAD and medial epicondylar markers has led to some improvement (which remain essentially undocumented in the academic literature) and this is still regarded as one of the most significant weakensses of the model.

### Over-simplistic foot modelling

The extremely simple foot model was proposed simply because of the limitations of measurement systems in the 1980s in resolving more than one marker placed on a foot (particularly a child's). This has not been a practical limitation for many years but there has never been a proposal to develop the CGM foot segment. Instead a range of other more complex foot models have been proposed, many of these clearly exceeding what it is possible to measure with skin mounted markers or clusters. The Oxford Foot Model ([Carson et al. 2001](http://dx.doi.org/10.1016/S0021-9290(01%2900101-4)) is probably the most widely used in clinical service provision and research but is quite different to the CGM in its modelling assumptions.

### Unconstrained segment dimensions

The most obvious difference between the CGM and a rigorous biomechanical model is that the segments are not required to be of fixed length. The distance between the modelled hip joint  and knee joint centres typically varies by about 20mm over a gait cycle in an adult as a result of soft tissue artefact. This will have both kinematic and kinetic consequences which are assumed to be samll, but have never been systematically investigated. More importantly this issue prevents the model being used directly as a basis for nore advanced biomechanical techniques such as muscle length modelling or induced acceleration analysis.

Modern inverse kinematic techniques ([Lu and O'Connor 1999](http://dx.doi.org/10.1016/S0021-9290(98%2900158-4)) allow kinematic modelling subject to constraints such as fixed segment dimensions. They also offer a framework to incorporate methods to compensate for, or model, soft tissue artefact ([Leardini et al. 2005](http://dx.doi.org/j.gaitpost.2006.12.018)).

### Inadequate compensation for soft tissues over pelvic landmarks
As the population, particularly that segment of it that experiences difficulties walking, becomes increasingly overweight the problem of locating the pelvis within the abdominal soft tissues is an increasingly important issue. Whilst a number of approaches have been suggested none are particularly convincing or have been rigorously validated.

### Upper body model
Whilst Davis et al. ([1991](http://dx.doi.org//0167-9457(91%2990046-Z)) did suggest placing two markers on the shoulders to give some indication of trunk alignment this particular aspect of the CGM has never been properly developed or validated. Vicon did develop an upper body model but, despite being quite widely used, there have been few validations of its outputs and no published normative reference data.
