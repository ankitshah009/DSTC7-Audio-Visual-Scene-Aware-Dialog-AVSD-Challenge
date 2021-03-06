## Python Packages need to be installed

- Python version is v2.7  
- pytorch  
- numpy  
- sklearn  
- json   
- argparse  
- Random
- os
- copy

## How to run the code:

   1. Download the data from google drive, and unzip them under data/charades/.  
   2. Run data/charades/prepare_charades.py to prepare the .pkl file (please change the feature_dir and output name following the formate of 'charades2text_{feature type}_features.pkl' in the prepare_charades.py file)
   3. Run run_charades_dialog_pytorch.sh to train and test the network, you can indicate the feature you want to use in 'ftype'. Example: ./run_charades_dialog_pytorch.sh --use_slurm true --ftype "i3d_rgb i3d_flow" --in_size "2048 2048" --optimizer "Adam"
   4. You will get 'generate_test(valid)_b5_p0.0.json' in the your experiment related folder under exp/. Use the coco evaluation system to get the scores with the reference json file under data/charades/.

## Result:

The following results were obtained by using i3d_rgb+i3d_flow
 
 
  
| METRIC  | RESULT |  
| ------  | -------|  
| CIDEr   |  0.572 |        
| Bleu_4  |  0.052 |   
| Bleu_3  |  0.075 |     
| Bleu_2  |  0.114 |  
| Bleu_1  |  0.193 |  
| ROUGE_L |  0.240 |  
| METEOR  |  0.093 |  
