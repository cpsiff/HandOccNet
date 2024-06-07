old pytorch versions install instructions: https://pytorch.org/get-started/previous-versions/

to delete an environment: conda env remove -n ENV_NAME

# attempt 5

conda create -n HandOccNet python=3.8

conda activate HandOccNet

pip install torch==1.9.1+cu111 torchvision==0.10.1+cu111 torchaudio==0.9.1 -f https://download.pytorch.org/whl/torch_stable.html (I thought this worked)

sh requirements.sh

pip install -e main

cd demo

conda install pyrealsense2 (fails if you do this step)

python demo.py --gpu 0


# Attempt 6 (trying another way, with as much conda as possible)

conda create -n HandOccNet python=3.8

conda activate HandOccNet

conda install pytorch==1.9.1 torchvision==0.10.1 torchaudio==0.9.1 cudatoolkit=11.3 -c pytorch -c conda-forge (trying this, why did I use pip before? I think mistake)

Want to do this but it hangs up and freezes when I ctrl+C
conda install numpy=1.17 einops chumpy opencv pycocotools pyrender tqdm pyrealsense2 matplotlib

conda install numpy=1.17 gives error - not solvable

trying this:
conda install numpy einops opencv pycocotools pyrender tqdm pyrealsense2 matplotlib
pip install chumpy 

fails when you run it

# Attempt 7 (as much pip as possible) - this seems to work

conda create -n HandOccNet python=3.8

conda activate HandOccNet

pip install torch==1.9.1+cu111 torchvision==0.10.1+cu111 torchaudio==0.9.1 -f https://download.pytorch.org/whl/torch_stable.html

pip install numpy==1.17.4 einops chumpy opencv-python pycocotools pyrender tqdm pyrealsense2 matplotlib

pip install -e main

cd demo

python demo.py --gpu 0