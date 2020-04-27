# Model-based Detection of Software Discrimination

In this file, we presents the artifacts used in our paper, which provides a Framework for Analysing Individual Fairness based on Software Models. The artifacts include:

* the *UMLfair profile*.

*  A prototypical implementation that supports the generation of LTL claims that conform to Defenition 4.1 in our paper. 

* The inputs and the outputs of applying our proposed framework on three case studies namely, the Bank Services System based on a real case study, the Delivery Management System based on the incedent describtion of [Amazon's delivery-free service](https://www.bloomberg.com/graphics/2016-amazon-same-day/), and the Loan Management System based on [business process model](https://link.springer.com/chapter/10.1007/978-3-319-92901-9_19) from an [event log](https://www.win.tue.nl/bpi/doku.php?id=2012:challenge) recording the loan management process of a Dutch financial institute. 

# Recources

* **Profile: The UMLfair Profile:** https://github.com/confFair/project/blob/master/profile.zip
* **Lunch configuration: The lucn configuration to the transformation tool hugo/RT:** https://github.com/confFair/project/blob/master/hugort.launch

* **Artifacts: The bank services system case study:** https://github.com/confFair/project/blob/master/BankServicesSystem.zip
* **Artifacts: The delivery management system case study:** https://github.com/confFair/project/blob/master/DeliveryManagementSystem.zip
* **Artifacts: The loan management system case study:** https://github.com/confFair/project/blob/master/LoanManagementSystem.zip

The artifacts of each each case study contains: 
* A (*.uml*) file: the UML model of the system annotated with the UMLfair profile.
* A (*.xlsx*) file: the dataset of the system which used to uncover proxies for protected data. 
* a (.pml) file: the result of transforming the UML into PROMELA by using the [Hugo/RT](https://www.informatik.uni-augsburg.de/en/chairs/swt/sse/hugort/) tool. 
* a (*.pdf*) file: provides the generated batches of claims together with their verifications results. The verifiaction results are the output of  the [SPIN](http://spinroot.com/spin/whatispin.html) model checker. 
* a (*.trail*) files: counterexamples generated by the [SPIN](http://spinroot.com/spin/whatispin.html) model checker that explain the violated claims in the (*.pdf*) file.
