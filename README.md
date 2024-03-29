# qualityassurance
Manufacturing Quality Assurance for fellow MSFT-ees



The goal of quality assurance is to maintain a high quality of service or product and is imperative to many businesses either in the delivery or production process of goods or services. By avoiding problems early in the process of delivering or producing goods or services, businesses can provide more value to their customers.

For example, quality assurance is imperative in digital manufacturing - ensuring quality throughout the assembly line production process. Identifying errors, slowdowns and potential failures before they occur rather than after they are detected can help companies be more proactive and improve productivity. The goal of the solution guide presented here is to predict failures in manufacturing pipelines (assembly lines).  This is done by leveraging test systems already in place and failure data, specifically looking at returns and functional failures at the end of assembly line. By combining these with domain knowledge and root cause analysis within a modular design that encapsulates main processing steps, we provide a generic advanced analytics solution that uses machine learning to predict failures before they happen. Early prediction of future failures allows for less expensive repairs or even discarding, which are usually more cost efficient than going through recall and warranty cost.

## Solution Dashboard
The snapshot below shows an example PowerBI dashboard that gives insights into the manufacturing assembly lines that are monitored.
![Insights](https://cloud.githubusercontent.com/assets/9042064/20733041/891bb5f2-b65f-11e6-8362-068b9ba92698.PNG)

## Solution Architecture
![Solution Diagram Picture](https://cloud.githubusercontent.com/assets/16708375/20932195/acb87330-bbcb-11e6-8a89-27d8b6e17bdf.png)

## Example Use Case
As an example, an **assembly line scenario** for a computer mother board manufacturer is given in Figure 2 characterized by Assembly Line Steps (ALS). In this scenerio, at Assembly Line Step 3 (ALS3), the solder paste is applied on the empty board, and then a test is performed to check that the paste droplets are correct size and that they are at the center or each pad. Boards that pass this already in place test, move to next assembly line step and eventually the electronic circuits are placed on the board and then connected to the board pads by melting the solder droplets in an oven. At the end of ALS5, a final electronic functional check is done before the board is shipped to client OEM PC manufacturer. Some of the failures discovered at ALS5 are due to defective solder paste application performed at ALS3, even if the board passed the regular ALS3 test. We can use **Machine Learning (ML)** to predict solder related failures right after the solder paste is applied in ALS3, but before the expensive electronic components like microprocessors and other integrated circuits are added to the board at ALS5. Rewashing a board with a functional defect that passed the regular Quality Asssurance (QA) test at ALS1 may cost cents, while scrapping a defective board at ALS5 after the processor and all other components are applied may cost hundreds of dollars. 

here is 1 of the ML experiments: https://gallery.cortanaintelligence.com/Experiment/Prediction-Model-ALS01-2

OEMs which use contract manufacturers (such as Microsoft and Jabil) can minimize post sale service and warranty costs using **ML** to build models that use shop floor data to predict, before shipping, returns and repairs that may happen months or years after device is shipped. This enables predicting **future failures** while the device is still in the **early manufacturing line stages** or is already assembled but is **not yet shipped**, so that fixing or even discarding it may be cheaper than going through recall and warranty costs.

This solution uses [SECOM](https://archive.ics.uci.edu/ml/datasets/SECOM) dataset from ([UCI ML Data repository](http://archive.ics.uci.edu/ml/datasets.html)) to generalize the example scenario described above where the main goal is to predict failures on an assembly line with 5 steps. As devices travel through the assembly line, certain measurements are collected at each step. These measurements are then used to predict possible failures at the end of the assembly line using a predictive model developed for each step. For technical details, please refer to the [*Solution Description*](https://github.com/annedroid/qualityassurance/blob/master/Manual%20Deployment%20Guide/SolutionDescription.md) under the [*Manual Deployment Guide*](./).

## Business Audiences

In this repository you will find a folder labeled [*Solution Overview for Business Audiences*](https://github.com/annedroid/qualityassurance/blob/master/Solution%20Overview%20for%20Business%20Audiences) which contains a  presentation covering this solution and benefits of using Cortana Intelligence



## Technical Audiences

See the [*Manual Deployment Guide*](https://github.com/annedroid/qualityassurance/tree/master/Manual%20Deployment%20Guide) folder for a full set of instructions on how to put together and deploy a Quality Assurance solution using Cortana Intelligence. For technical problems or questions about deploying this solution, please post in the issues tab of the repository.

## Related Resources

 some details on how to think about evaluating predictive maintenance models [here](https://blogs.technet.microsoft.com/machinelearning/2016/04/19/evaluating-failure-prediction-models-for-predictive-maintenance/).

