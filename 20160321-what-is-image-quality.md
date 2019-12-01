I saw a talk at AAPM 2015 by Kyle Myers (from the FDA's Office of Science and Engineering Laboratories) about the Channelized Hotelling Observer (Barrett et al 1993), which is a parametric model of visual performance based on spatial frequency selective channels in areas V1 and V2.

She was discussing the use of the CHO model for selecting optimal CBCT reconstruction parameters, but I ran across an obvious application of the technique to the problem of JPEG 2000 parameter selection (Zhang et al 2004). 

It reminded me of the RDP plugin prototype I had developed a few years back, which demonstrated the ability to dynamically adjust compression performance during medical image review on an RDP or Citrix session. My prototype could also benefit from optimizing the CHO confidence interval (though it used JPEG XR instead of JPEG 2000), but possibly more interesting is the ability to predict the presentation parameters to be delivered over the channel, such as zoom/pan, window/level, or other radiometric filters to be applied to the image. It could also be used to determine when certain regions of the parameter space are not feasible for image review, because the confidence interval collapses (for instance, if you set window width=1).

So if anyone asks "What is Image Quality", you can tell them: "Image Quality = Maximized CHO Confidence Interval" (or maximized CHO Area Under Curve). Got it?

P.S. there is very nice Matlab implementation of the CHO model in a package called IQModelo, with some examples of calculating CI and AUC.

<originally published on LinkedIn, 2016 Mar 21>
