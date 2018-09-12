# Searchlight Analysis
### python-notebook-test.ipynb
* This file is just notebook test file.

### NiLearn_searchlight-analysis.ipynb
* This file is a searchlight analysis tutorial file.
* It performs searchlight anlaysis within very compact ROI-sized image file.
* If you want to perform searchlight analysis in other images you have, your FreeTier AWS instance would raise up a `Memory Error`.
  * Consider changing the instance type or setting up them to your local server.
    * See here: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-resize.html
* This file would make a pstat, tstat nii files and accuracies score map of each subject.