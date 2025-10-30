


|                 | Best for                                                                                                         | Advantages                                   | Disadvantages                                                                                                                                                                                                                              | Models/Approaches                                              |
| --------------- | ---------------------------------------------------------------------------------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------- |
| Semi-supervised | - low labelled data<br>- lots of unlabelled data<br>- model improvement<br>- a way to "label" the remaining data | - cost effective<br>- flexible<br>- scalable | - data quality<br>- potential issues with model understanding*<br>- too much unlabelled data --> labelled data may not be propagated into the unlabelled data<br>- RATIO BALANCE (30 labelled /70 unlabelled)<br>- REQUIRES VALIDATION SET | - label spreading/propagation<br>- generative<br>- co-training |

\* model understanding = interpretation of model output

### Label Propagation
can use labels from supervised set to assign an assumed label unlabelled data (regression, classification)

### Generative
Generate labels for the unlabelled data based on the existing labelled data
SPECIFIC to Neural Network environments

### Co-training
different techniques, different subsets