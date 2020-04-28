# Model-based Detection of Software Discrimination

In this file, we presents the artifacts used in our paper, which provides a Framework for Analysing Individual Fairness based on Software Models. The artifacts include:

* the *UMLfair profile*.

*  A prototypical implementation that supports the generation of LTL claims that conform to Defenition 4.1 in our paper. 

* The inputs and the outputs of applying our proposed framework on three case studies namely, the Bank Services System based on a real case study, the Delivery Management System based on the incedent describtion of [Amazon's delivery-free service](https://www.bloomberg.com/graphics/2016-amazon-same-day/), and the Loan Management System based on [business process model](https://link.springer.com/chapter/10.1007/978-3-319-92901-9_19) from an [event log](https://www.win.tue.nl/bpi/doku.php?id=2012:challenge) recording the loan management process of a Dutch financial institute. 

# Recources

* **Profile: The UMLfair Profile:** https://github.com/confFair/project/blob/master/profile.zip
* **LTL claims generator:** https://github.com/confFair/project/blob/master/ClaimsExtraction.zip
* **Lunch configuration: The lucn configuration to the transformation tool hugo/RT:** https://github.com/confFair/project/blob/master/hugort.launch

* **Artifacts: The bank services system case study:** https://github.com/confFair/project/blob/master/BankServicesSystem.zip
* **Artifacts: The delivery management system case study:** https://github.com/confFair/project/blob/master/DeliveryManagementSystem.zip
* **Artifacts: The loan management system case study:** https://github.com/confFair/project/blob/master/LoanManagementSystem.zip

The artifacts of each each case study contains: 
* a (*.uml*) file: the UML model of the system annotated with the UMLfair profile.
* Two (*.xlsx*) files. The first is the dataset, which used to uncover proxies for protected characteristics. The second file is the proxies for the protected characteristics in the model, which is used as input for our LTL claims generator.  
* a (.pml) file: the result of transforming the UML into PROMELA by using the [Hugo/RT](https://www.informatik.uni-augsburg.de/en/chairs/swt/sse/hugort/) tool. 
* a (*.pdf*) file: provides the generated batches of claims together with their verifications results. The verifiaction results are the output of  the [SPIN](http://spinroot.com/spin/whatispin.html) model checker. 
* (*.trail*) files: counterexamples of violated LTL claims generated by the [SPIN](http://spinroot.com/spin/whatispin.html) model checker.

# Generating LTL claims
The uploaded [ClaimsExtraction.zip](https://github.com/confFair/project/blob/master/ClaimsExtraction.zip) file includes all the required artifacts for generating LTL claims based on the UML models that are annotated with the UMLfair profile.

## Prerequisite 
We recommend using [Eclipse, Modeling Tools distribution](https://www.eclipse.org/downloads/packages/release/neon/r/eclipse-modeling-tools).

## Performing the LTL claims generation. 
To execute the generation of LTL claims from UML models annotated with the UMLfair profile, please follow the following instruction. 

* Import our project package to your local Eclipse workspace.
* Right-click on the main class *"src/ltlGenerator/Generator.java"* → *Run As Java Application*. Our generator takes as inputs: First, a UML model saved as (.xml) file. Second, information of proxies saved in a (.xlsx) file. By default, our generator takes as input the *bankSystem.xml* and the *ProxyOfBankSystem.xlsx* files. To change the input (.xml) file, first copy the name of one of the (.xml) files that are provided in *ClaimsExtraction → src → ltlGenerator* directory. Second, find line 51 in the *Generator.java* file (**File inputFile = new File("/Users/anonymous/workspace/ClaimsExtraction/src/ltlGenerator/loanSystem.xml");**) and replace the file name *"bankSystem"* with the name of the selected (.xml) file. While to change the input (.xlsx) file, first copy the name of the corresponding (.xlsx) file to the selected (.xml) file. The (.xlsx) files are provided in *ClaimsExtraction* directory. Second, find line 68 in the *Generator.java* file (**File inputFile = new File myExcelBook=new File("C:/Users/qramadan/anonymous/ClaimsExtraction/ProxyOfBankSystem.xlsx");**) and replace the file name *"ProxyOfBankSystem"* with the name of the selected (.xlsx) file.
