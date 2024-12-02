# LSPeerNom
This repository contains the several scripts and files to perform Peer Nomination Surveys using LimeSurvey. 
- `LSPeerNom-components` directory
    - Contains scripts (Javascript) to enable Peer Nomination and Peer Ranking for specific question types. The scripts should be added to the question body using the LimeSurvey editor. The question needs to be prepared by adding a labelset with plenty of peer placeholders. 
    - A labelset with 40 peer placeholders. This file can be uploaded in the LimeSurvey labelset interface and is enough for any peer group smaller than 41 participants. 

- `LSPeerNom-templates` directory
    - Contains .lss templates that can be uploaded into LimeSurvey
        - One template for the student survey
        - One template for the teacher/mentor survey

- ` LSRadboud-theme`
    - Contains a LimeSurvey theme template
    - Currently not to be used, but eventually this would replace the default Radboud theme on LimeSurvey
    - The theme should implement better colors for active and non-active buttons, which is essential when doing peer nomination. This is currently taken care of in the question scripts (see the `LSPeerNom-components` directory)

- `postprocessing` directory
    - Contains the Jupyter notebook to process the csv output from the LimeSurvey Student responses, this notebook:
        - reads in a csv file with student survey answer data, see the notebook for more specific documentation on the input file
        - reads in the participant list 
        - for each peer nomination question:
            - generate a column per student longID that participated in the survey
            - per row reorder the answers according to the participant's classmate list order, matching the longID columns
    - Contains the Jupyter notebook to process the csv output from the LimeSurvey Mentor responses, this notebook:
        - reads in a csv file with mentor survey answer data, see the notebook for more specific documentation on the input file
        - reads in the mentor participant list
        - reads in the student participant list
        - for each pupil nomination question:
            - generate single column where the l
    - Contains an `example_data` directory with:
        - ...


- `preprocessing` directory
    - Contains the Jupyter notebook to process the list of students from a school into the input csv file for LimeSurvey, this notebook:
        - reads in a csv file with certain expected columns, see the notebook for more specific documentation on the input file
        - generates a new column with for each student a randomized list of classmates (other students)
        - specifies columns names for specific required attributes for doing peer nomination in LimeSurvey 
    - Contains an `example_data` directory with:
        - an example input file for testing the participant information preprocessing notebook
        - an example output file, which can be uploaded as LimeSurvey participant list for testing Peer Nomination



When setting up a LimeSurvey peer nomination survey, you should have access to an active LimeSurvey server. If you work at Radboud University, you can use the [organization's LimeSurvey server](https://questions.socsci.ru.nl/). More information on using this server can be found on the [Technical Support Group wiki](https://tsgdoc.socsci.ru.nl/index.php/LimeSurvey).

Alternatively you can set up your own webserver or local test installation, more information can be found in [the installation documentation](https://www.limesurvey.org/manual/Installation_-_LimeSurvey_CE/en). 

Once you have access to the LimeSurvey admin interface, either start by uploading one of the LSPeerNom templates from the `LSPeerNom-templates` directory or create a new survey and use the files in the `LSPeerNom-components` directory.