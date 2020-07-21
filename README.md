Requirements
===================================================================
Python 3.5+ 
Python packages: 
list of packages are provided in env-setup/requirements.txt file.

How to Run
===================================================================
- Example command line to train the cue-detector: 
  python train.py -c ./config/config.json 
  + Arguments:
	  - -c, --config_path:path to the configuration file, required=True
  *Note that: Training the system is optional, a trained model is already provided in "./model" directory. The pre-trained model can be used to predict a text file (step is given below).
	
- Example command line to apply prediction on a given file.
  python predict.py -c ./config/config.json -i ./data/sample-io/input_file.txt -o ./data/sample-io/
  + Arguments:
	  - -c, --config-path: path to the configuration file; (required). Contains details parameter settings.
	  - -i, --input-file-path: path to the sample input file (text file, one sentence per line); (required)
	  - -o, --output-dir: path to the output directory (output files will be created in this directory); (required)
	  - --cd_sco_eval: if true, then creates a prediction file (in "./data/cd-sco-prediction/" by default) to evaluate cd-sco test corpus, (optional)
  
Input and Output Files
====================================================================
- Sample input file:   ./data/sample-io/input_file.txt (input file must contain one sentence per line)
- Sample output files: ./data/sample-io/with_neg.txt (contains sentences with negation, one sentence per line)
                       ./data/sample-io/with_neg_cue_tags.txt (contains sentences (tokenized) with negation neg (Y if token is a negation cue, otherwise N ))
					   ./data/sample-io/without_neg.txt (contains sentences without negation, one sentence per line)