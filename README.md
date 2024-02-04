# Social LSTM implementation in PyTorch

## Project details
**Semester project of Master of Computer Science in EPFL**  
**Student name** : Baran Nama  
**Advisor:** Alexandre Alahi  
**Presentation** : https://drive.google.com/file/d/1biC23s1tbsyDETKKBW8PFXWYyyhNEAuI/view?usp=sharing  

## Implementation details
**Baseline implementation**: https://github.com/vvanirudh/social-lstm-pytorch  
**Paper**: http://cvgl.stanford.edu/papers/CVPR16_Social_LSTM.pdf  
**Detailed info about challange and datasets**: https://www.aicrowd.com/challenges/trajnet-a-trajectory-forecasting-challenge
**Made improvements:** Please see attached presentation  

## Documentation
- **generator.py** : Python script for generating artifical datasets
- **helper.py**: Python script includes various helper methods
- **hyperparameter.py**: Pyton script for random best parameter selection for a model
- **make_directories.sh**: Bash script for creation of file structure
- **model.py**: Python file includes Social LSTM model definition
- **olstm_model.py**: Python file includes Occupancy LSTM model definition
- **olstm_train.py**: Python script for training Occupancy LSTM model
- **test.py**: Python script for model testing and getting output txt file for submission
- **train.py**: Python script for training Social LSTM model
- **utils.py**: Python script for handling input train/test/validation data and batching it
- **validation.py**: Python script for externally evaluate a trained model by getting validation error
- **visualize.py**: Python script for visualizing predicted trajectories during train/test/validation sessions
- **vlstm_model.py**: Python file includes Vanilla LSTM model definition
- **vlstm_train**: Python script for training Vanilla LSTM model

## How to deploy
1. Fork the repository 
2.  Start train a model >>> **python train/olstm_train/vlstm.train.py - -[Parameter set]**
3. If necesarry file structure is not exist (which is the initial situation), train script will run make_directories.sh and this command will automatically create file structure
4. Enjoy!
5. The command to run the code:
```
python train.py --input_size 2 --output_size 5 --rnn_size 128 --batch_size 5 --seq_length 20 --pred_length 12 --num_epochs 30 --save_every 400 --grad_clip 10. --learning_rate 0.003 --decay_rate 0.95 --dropout 0.5 --embedding_size 64 --neighborhood_size 32 --grid_size 4 --maxNumPeds 27 --lambda_param 0.0005 --use_cuda --gru --drive --num_validation 2 --freq_validation 1 --freq_optimizer 8 --grid

```

## Results  

| Model name | Avarage error | Final error | Mean error |
| :---: | :---: | :---: | :---: |
| Social LSTM | 1.3865 | 2.098 | 0.675 |
| Occupancy LSTM | 2.1105 | 3.12 | 1.101 |
| Vanilla LSTM | 2.107 | 3.114 | 1.1 |

**Reference**: http://trajnet.stanford.edu/result.php?cid=1

