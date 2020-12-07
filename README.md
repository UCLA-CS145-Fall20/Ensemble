### Ensemble model:

#### Prerequisite 

scipy, pandas, numpy

#### How to run:

1) This model is to be used after poly_model and SIR model has output their result. 
    Please read the instructions from those models first to prepare the files for ensemble model

2) Put three validation files (Currently validated on 7 days):
    
    * validation1.csv (from SIR-model)
    * validation2.csv (from poly-model)
    * validation3.csv (from SIR-model)
    
   into a folder
   
   Put three test files:   
   
    * output1.csv (from SIR-model)
    * output2.csv (from poly-model)
    * output3.csv (from SIR-model)
   
   into a folder. 
   
 3) Change line 70 - 72 of the ensemble_model.py file
        
        ... 
        # change the below three lines to three validation csv location respectively 
        validation_1 = pd.read_csv('outputs/update_validation/validation_output1.csv') # Use the directory for validation1.csv
        validation_2 = pd.read_csv('outputs/update_validation/validation.csv') # Use the directory for validation2.csv
        validation_3 = pd.read_csv('outputs/update_validation/validation_output3.csv') # Use the directory for validation3.csv
        ...
        
 4) change line 138 - 140 of the ensemble_model.py file
 
        ...
        # change the below three lines to three output csv file location repectively
        test1 = pd.read_csv("outputs/update_sub/output1.csv") # Use the directory for output1.csv
        test2 = pd.read_csv("outputs/update_sub/output.csv") # Use the directory for output2.csv
        test3 = pd.read_csv("outputs/update_sub/output3.csv") # Use the directory for output3.csv
        ...
        
 5) In terminal, run 
        
        python ensemble_model.py
    
    The new ```combined_output.csv``` in the directory is the final csv file for submission.