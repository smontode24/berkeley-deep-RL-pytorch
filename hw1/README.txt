
* Create conda environment
- `pip install -r requirements.txt`
- `conda install -y pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia`
- `export LD_LIBRARY_PATH=`
- `export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so`



##############################################
##############################################

4) code:

Blanks to be filled in are marked with "TODO"
The following files have blanks in them:
- scripts/run_hw1_behavior_cloning.py
- infrastructure/rl_trainer.py
- agents/bc_agent.py
- policies/MLP_policy.py
- infrastructure/replay_buffer.py
- infrastructure/utils.py

NOTE - tf_utils.py was deleted in the pytorch version

See the code + the hw pdf for more details.

##############################################
##############################################

5) run code: 

Run the following command(s) for Section 1 (Behavior Cloning):
(All identical, one for each env)

$ python cs285/scripts/run_hw1_behavior_cloning.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v2 --exp_name test_bc_ant --n_iter 1 --expert_data cs285/expert_data/expert_data_Ant-v2.pkl
$ python cs285/scripts/run_hw1_behavior_cloning.py --expert_policy_file cs285/policies/experts/HalfCheetah.pkl --env_name HalfCheetah-v2 --exp_name test_bc_halfcheetah --n_iter 1 --expert_data cs285/expert_data/expert_data_HalfCheetah-v2.pkl
$ python cs285/scripts/run_hw1_behavior_cloning.py --expert_policy_file cs285/policies/experts/Hopper.pkl --env_name Hopper-v2 --exp_name test_bc_hopper --n_iter 1 --expert_data cs285/expert_data/expert_data_Hopper-v2.pkl
$ python cs285/scripts/run_hw1_behavior_cloning.py --expert_policy_file cs285/policies/experts/Humanoid.pkl --env_name Humanoid-v2 --exp_name test_bc_humanoid --n_iter 1 --expert_data cs285/expert_data/expert_data_Humanoid-v2.pkl
$ python cs285/scripts/run_hw1_behavior_cloning.py --expert_policy_file cs285/policies/experts/Walker2d.pkl --env_name Walker2d-v2 --exp_name test_bc_walker2d --n_iter 1 --expert_data cs285/expert_data/expert_data_Walker2d-v2.pkl

Run the following command for Section 2 (DAGGER):
(NOTE: the --do_dagger flag, and the higher value for n_iter)

$ python cs285/scripts/run_hw1_behavior_cloning.py --expert_policy_file cs285/policies/experts/Walker2d.pkl --env_name Walker2d-v2 --exp_name test_dagger_walker --n_iter 10 --do_dagger --expert_data cs285/expert_data/expert_data_Walker2d-v2.pkl

##############################################

6) visualize saved tensorboard event file:

$ cd cs285/data/<your_log_dir>
$ tensorboard --logdir .

Then, navigate to shown url to see scalar summaries as plots (in 'scalar' tab), as well as videos (in 'images' tab)
