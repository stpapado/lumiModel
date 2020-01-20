# lumiModel
**Updated luminosity model, including the effects of coupling&amp;noise&amp;burn-off for the emittance growth**

The numerical model used since 2016 to calculate the machine luminosity was updated, by adding new features like the coupling between the two planes, the effect of noise and the impact of inelastic collisions on the transverse core. In order to understand the impact of mechanisms which are beyond the model on the luminosity degradation, the measurements are compared to the luminosity model.
***
**Model description**

At each time step, the model is applied bunch-by-bunch, 
for colliding and non-colliding bunches, considering:

Intrabeam Scattering (IBS),
Synchrotron Radiation (SR),
Coupling
-linear coupling,
Noise
-noise floor of the machine and of the transverse damper,
Burn-off & emittance variation
-caused by transverse bunch core depletion in collisions,
Elastic scattering,
Intensity variation.

Including b*, luminosity leveling, x-ing angle anti-leveling options.

→ Combination of transverse emittances, bunch length and bunch intensity to compute the luminosity at each time step
***
**Run the Model** 
In order to run the Model for a specific Fill we need we need to have access to the eos path were the pkl of this Fill are saved and to the scripts: 
* toRun_corBSRT2018.ipynb -> run only for the model cases where we take emittance from model, i.e. 'IBSLosses' and 'IBSBOff'
* emit_model_elastic_scattering.ipynb 
* IBSmodel_GY.ipynb 
* noiseINmodel_new.ipynb 
* LumiModel_CouplNoiseBoff_new.ipynb
(Stefania used in swan)

We define the Fill number we want to run in toRun_corBSRT2018.ipynb , in this script:
*  the parameters used for the calculation of coupling, noise, burn-off are defined
*  the functions used to calculate the effects in the LumiModel are called (and run)
*  some other parameters are deifned- like the energy, the voltage and the synchrtron radiation damping time
*  we read the eos pkl for the specified Fill  
*  the emittances can be corrected-> correct BSRT by multiplying the emittances by a cor. factor. This is important for the 2018 BSRT emittances which disagree with the ones expected from luminosity
*  then the luminosity model is being calculated for 5 cases: "old model", "coupling", "coupling&noise", "coupling&boff", "coupling&noise&boff"

To plot use: To plot use: plot_lumimodel_frompickle_allModels_CouplNoiseBoff.ipynb

This has been done for all Fills of 2017 and the saved pkl are in eos.
For a 2018 Fill, someone needs to correct the BSRT emittances and then run the script. It has been done already for some Fills.

*at Flat Bottom*
Use the Files: runModel_CouplNoiseBoff_FB.ipynb, it calls the IBSmodel_GY.ipynb and the noiseINmodel_FB.ipynb
To plot use: plot_lumimodel_frompickle_allModels_CouplNoiseBoff_FB.ipynb


***
**Useful links** 

*model* \
https://gitlab.cern.ch/antoniou/LHC-ibs-model \
http://accelconf.web.cern.ch/AccelConf/IPAC2015/papers/tupty020.pdf \
https://indico.cern.ch/event/578001/contributions/2366376/attachments/1388316/2222614/Evian2016_Lumi_F.Antoniou.pdf \
*coupling* \
https://indico.cern.ch/event/746812/contributions/3087407/attachments/1693400/2725137/couplingMeasurementsJuly2018.pdf \
*noise* \
https://cds.cern.ch/record/2304603 \
*burn-off* \
https://indico.cern.ch/event/806869/contributions/3358585/attachments/1816649/2969341/Emittance_BU_due_to_BO.pdf \
https://arxiv.org/pdf/0911.5627v1.pdf \
*model improvement and run2 results* \
https://indico.cern.ch/event/844767/contributions/3547587/attachments/1905233/3146376/upLumiModel_WP2_10Sep19_stef.pdf \
https://indico.cern.ch/event/813285/contributions/3406120/attachments/1856807/3050113/LumiModel_LumiDays19_stef.pdf \


