# The SAMPL6 Blind Prediction Challenge for Computational Chemistry

This repository gives challenge details and inputs for the SAMPL6 challenge (which has now ended, but the files are maintained here for the record).
This cycle we have migrated the data download package to GitHub so it will be version controlled and more broadly acccessible.
**Because these files are available publicly, we have no record of who downloads them. Therefore, you should sign up for notifications**.
Specifically, if you want to receive updates if we uncover any problems, it is imperative that you either (a) sign up for the SAMPL e-mail list via the D3R site, or (b) sign up for notifications of changes to this GitHub repository (the ``Watch'' button, above); ideally you would do both.
**Join our e-mail list** by visiting the [D3R SAMPL6 Site](https://drugdesigndata.org/about/sampl6) and click "Join Challenge".

The challenge culminated with a [joint D3R/SAMPL workshop](https://drugdesigndata.org//about/d3r-2018-workshop) in La Jolla, CA., Feb. 22-23, 2018.
A special issue of JCAMD is being planned (see below) with a submission deadline of June 1, 2018.

## What's Here
- [Challenge Overview](#challenge-overview)
- `host_guest`: Directory containing inputs for the host-guest challenges, as well as supporting files and a README detailing their organization
- [Host-guest challenge instructions](host_guest_instructions.md): Detailed instructions on the host-guest component of the challenge.
- [Detailed host-guest description](host_guest_description.md): Detailed description of the hosts, guests, and background information.
- Physical properties:
    - [pKa challenge instructions](pKa_challenge_instructions.md): etailed instructions on the pKa prediction component of the challenge.
    - [logD challenge preview](https://github.com/MobleyLab/SAMPL6/tree/master/physical_properties): Information on what may comprise the distribution coefficient of the challenge, and previews of some of the potential compounds.
- SAMPLing challenge files for host-guest challenge: Input files for the host-guest component of the SAMPLing challenge, see [description](#sampling-challenge) below.
- SAMPLing challenge files in alternate formats, along with energy validation data

## What will be in a future challenge
- Submission formats for logD prediction and SAMPLing challenge
- LogD challenge files and instructions (see description, below)

## Changes and Data Set Versions So Far:
(all major versions available under [releases](https://github.com/MobleyLab/SAMPL6/releases) above)

### Release versions
- Version 1.0: Data set as originally posted Aug. 24
- Version 1.1: Updates `host_guest_description.md` to reflect corrected CB8 phosphate buffer concentration; adds input files (and scripts) from Andrea Rizzi for host-guest challenge reference calculations; adds `physical_properties` with preview information on the potential physical properties component of the challenge.
- Version 1.2: Adds host-guest SAMPLing challenge explanation and inputs, describes these in README files; adds draft submission files for host-guest predictions in `host_guest/(hostname)AndGuests` directories; updates the discussion of the physical property challenge to reflect the current status.
- Version 1.3: Add pKa prediction challenge instructions, input files, submission template files, update on the future plans of logD challenge.
- Version 1.4: Update microstate lists of pKa challenge.
- Version 1.5: Update microstate lists of pKa challenge. Clarification to pKa microstate definition: Resonance structures or geometric isomers with the same bound hydrogen pattern do not constitute different microstates. Add canonical SMILES column to microstate list files. Add suggested microstate pairs for physically meaningful microscopic pKas for type I submissions.
- Version 1.6: Corrects outdated CB8 sodium phosphate buffer concentration which appeared in an image (it was already correct in the text); include input files converted to other formats; fixes a compound name for one CB8 compound; corrects a pKa microstate; fixes a submission template issue.
- Version 1.7: Update microstate lists of pKa challenge. Add new microstate IDs for SM18 and SM20.  
- Version 1.8: Update microstate lists of pKa challenge. Add new microstate ID for SM10.
- Version 1.9: Include experimental measurements for the pKa challenge and the binding host-guest challenge.
- Version 1.10: Include the analysis of binding host-guest, pKa, and SAMPLing challenge, as well as microstate characterization of SM07 with NMR experiments.

### Changes not yet in a release


## Challenge Overview
(This is reproduced from the [SAMPL6 Website](https://drugdesigndata.org/about/sampl6))

SAMPL6 includes challenges based on aqueous host-guest binding data (binding free energies and, optionally, binding enthalpies) for three different host molecules; and on physical properties (distribution coefficients and possibly solubilities), for a set of fragment-like molecules.
The host-guest systems are useful to test simulation methods, force fields, and solvent models, in the context of binding, without posing the setup issues and computational burden of protein simulations.
The physical properties offer efficient tests of force field accuracy when detailed simulations are used, and can also test pKa prediction methods, continuum solvation models, and knowledge-based prediction methods.
SAMPL6 will also introduce a new challenge component, the “SAMPLing challenge”, in which computational methods will be evaluated on how efficiently their calculations approach well-converged reference results generated by the organizers.
Participants will be provided with machine readable setup files for the molecular systems, including force field setups, along with recommended cutoffs and treatments of long-ranged interactions.
The SAMPLing challenge is expected to include one or more cases from each challenge component (host-guest binding on each system; log D calculation).

**As of August 24, all of the information and data files needed to start on the host-guest component, including machine-readable structure files for the hosts and guests are posted, so this challenge is open!
Files are hosted at github.com/mobleylab/SAMPL6.**
Status updates will be posted here and announced by email to the D3R SAMPL list and on the D3R Twitter account; we also encourage participants to “watch” the GitHub repository for notifications of file changes/availability and relevant discussions.

Further information on both the host-guest and physical property components of SAMPL6 follow.
Thanks to Drs. Bruce Gibb (Tulane U.) and Lyle Isaacs (U. Maryland) for providing the host-guest data, Andrea Rizzi for SAMPLing challenge data, and Dr. John Chodera, Mehtap Isik, and Merck for the distribution coefficient data.

### Gibb Deep Cavity Cavitand (Octa Acids) binding of guests

One host-guest series is based on the Gibb Deep Cavity Cavitands (GDCCs), or octa-acids, previously used in SAMPL4 and SAMPL5.
The two hosts, OA and TEMOA (previously OAH and OAME) are identical, except that TEMOA has four additional methyl groups, which alter the shape and depth of the hydrophobic cavity.
Both were developed in the laboratory of Dr. Bruce Gibb (Tulane U), who will provide binding free energies and enthalpies, measured by ITC, for eight guest molecules interacting with each host.
The measurements are done in 10 mM sodium phosphate buffer at pH 11.7 ± 0.1, and T = 298 K.
Host OA is described here: doi:10.1021/ja200633d; and host TEMOA is described here doi:10.1007/s10822-013-9690-2.
There are also a number of papers from SAMPL4 and SAMPL5 which discuss calculations for these systems, as summarized, respectively, in doi:10.1007/s10822-014-9735-1 and doi:10.1007/s10822-016-9974-4.
Existing benchmark datasets based on these hosts also may be of interest for those preparing to tackle these new complexes: https://github.com/MobleyLab/benchmarksets; this ``perpetual'' review paper also provides a good introduction to the sampling and experimental issues which are known to be relevant in these systems.

### Cucubit[8]uril (CB8) binding of guests

This host-guest series is based on the host cucurbit[8]uril (CB8), which was used in SAMPL3, as previously summarized (DOI 10.1007/s10822-012-9554-1).
CB8 is the eight-membered relative of cucurbit[7]uril, which was used in several other prior SAMPL challenges.
Data will be provided for ~14 guests, including several FDA approved drugs.
Background information on CB8 may be found in a number of publications, including DOI 10.1021/jp2110067, 10.1002/chem.201403405, and 10.1021/ja055013x.

### Physical properties
Due to experimental issues, the upcoming SAMPL6 physical property challenge is being split into two phases.
The first phase, for SAMPL6, will focus on pKa prediction for the upcoming workshop. Then the pKa data for this challenge will be provided to participants and used as part of a second challenge centering on predicting distribution coefficients.

#### pKa prediction
This challenge consists of predicting microscopic and macroscopic pKas of 24 small organic molecules.
These fragment-like small molecules are selected for their similarity to kinase inhibitors and for experimental tractability.
Our aim is to evaluate how well current pKa prediction methods perform with drug fragment-like molecules through blind predictions.
This is the first time a pKa prediction challenge is being conducted as a part of SAMPL.

Three formats of pKa prediction results will be evaluated:
1. microscopic pKa values and related microstates
2. microstate populations as a function of pH
3. macroscopic pKa values

Detailed instructions for the pKa challenge can be found here: [pKa_challenge_instructions.md](pKa_challenge_instructions.md)

Challenge start date: Oct 25, 2017   
Challenge submission due: Jan 23, 2018 

Experimental pKa measurements were added to this repository after the pKa challenge deadline and can be found here: [physical_properties/pKa/experimental_data/](physical_properties/pKa/experimental_data/) 

#### logD prediction
Distribution coefficients for about 25 fragment- and drug-like small molecules that resemble small molecule protein kinase inhibitors (or fragments thereof).

logD prediction challenge will take place in early 2018, after SAMPL8 workshop.

Because the SAMPL5 logD challenge highlighted the difficulty in correctly predicting transfer free energies involving protonation states, we will provide participants with experimental pKa values for these compounds.
We will ask participants to predict distribution coefficients (logD) at a single pH and (as a separate challenge), provided the measurements can be completed in time, pH-dependent solubilities for these compounds.

The experimental data being measured include pKa values, measured by electrochemical and/or UV-metric titration; and pH-dependent distribution coefficients (logD) of one or both of the following types:
- water and cyclohexane (as in SAMPL5)
- water and octanol (new in SAMPL6)

There is also a possibility that solubilities will be measured, using the CheqSol method. All of these measurements will be performed on Sirius T3 instruments from Sirius Analytical at Merck’s Rahway site.
The exact size of the dataset will depend on practical data collection throughput.
An initial batch of ~25 fragment-like compounds is currently being assayed, with the prospect for additional measurements performed subsequently.
Post-challenge follow-up experiments are possible and will be conducted as needed.
A preliminary list of compounds is now available in the `physical_properties` directory to give participants an idea of what types of compounds may be included, but this list is expected to change to some degree.
The final challenge will include logD and, if available, solubility prediction.

Distribution coefficients were included in the SAMPL5 challenge (overview doi:10.1007/s10822-016-9954-8 and experiment doi:10.1007/s10822-016-9971-7; JCAMD special issue https://link.springer.com/journal/10822/30/11/page/1); in many cases, they were predicted as if they were partition coefficients, using solvation free energies in the relevant solvents.
The difference between distribution coefficients (logD, which reflects the transfer free energy at a given pH including the effects of accessing all equilibrium  protonation states of the solute in each phase) and partition coefficients (logP, which reflects the free energy of transfer for the neutral form only) proved particularly important.
In some cases, other effects like the presence of small amount of water in cyclohexane may also have played a role.


### SAMPLing challenge
The purpose of the SAMPLing challenge component is to evaluate and compare the performance of different sampling methodologies in the context of free energy calculations of biomolecular systems. Participants are invited to compute the free energy of binding of few host-guest systems taken from the main SAMPL6 challenge. We will be running extremely long calculations with the provided input files in an attempt to obtain "gold standard" results, and then assess how well different methods approach/converge to these results. See [`SAMPLing_instructions.md`](SAMPLing_instructions.md) for more details.

This SAMPLing challenge is a bit of an experiment, as it is entirely possible that different methods/packages may *not* agree even when apparently converged, requiring participating groups to work together to track down discrepancies. However, if agreement is obtained, it should be very instructive to compare the rate of convergence.
We expect that analysis of this challenge component will focus even more than usual on "lessons learned" rather than on which methods performed "best" by some metric, but we hope it will also pave the way for future iterations of such challenges.


## The SAMPL special issue

We have arranged for a SAMPL special issue to appear in the Journal of Computer-Aided Molecular Design, thanks to editor Terry Stouch. The submission deadline is **June 1, 2018**.
David Mobley will serve as guest editor for the SAMPL6 special issue. 
Please submit on-time; the goal is to publish before the end of 2018.

To submit: 
1) If you don't already have an account with JCAMD, register with JCAMD at:  http://www.editorialmanager.com/jcam
2) In your title, please include SAMPL6 and use them as keywords if possible
3) During submission  you will be asked to select an article "type." Please select the issue’s assigned article type, e.g. "SI:SAMPL6"
4) Submit on time! 
5) Review fellow participant's papers (promptly please) as requested. 
Some of the best reviewers of the challenges are those who participate and understand the nature of the papers.  Fellow participants are most familiar with the topic and have a vested interest in moving the paper quickly, hence many/most of the reviewers will chosen from participants.
6) Please submit reviews (or your revisions) ASAP to help maintain our chosen publication dates.

