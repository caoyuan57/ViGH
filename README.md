# peer
A novel privacy-preserving large-scale image retrieval framework. 
![image](https://github.com/01181521/peer/blob/main/framework.png)
## How to run
The environment is

```<python==3.7.13 pytorch==1.12.0 flask==2.1.2 web3==5.29.2>```

## Encryption

Place the training set folder under the `datasets` folder. The training set folder should contain two folders `trainA` and `trainB`, where `trainA` contains 1000 randomly selected training images and `trainB` contains a set of images encrypted using a common encryption algorithm such as pixel permutation encryption. The training code is as follows.

```
cd CycleGAN-encryption
```

```
python train.py --dataroot ./datasets/cifar_train --name cifar_cyclegan --model cycle_gan --n_epochs 40
```

After completing the training create a folder in the `checkpoints` folder e.g. `encrypt_pretrained`, then move the `40_net_G_A.pth` to the folder and rename it `latest_net_G.pth`, Finally run the code

```
python test.py --dataroot datasets/cifar --name encrypt_pretrained --model test --no_dropout
```

The encrypted image will then be available in the `result` folder. To decrypt image, use `40_net_G_B.pth` in the same way as above.

## Blockchain

You need to install ganache before running the code, the command is as follows.

```
sudo apt update
sudo apt install npm
sudo npm install -g ganache-cli
```
The command to run ganache is
```
ganache-cli
```
## Hash
You can get the code from the link below.   
[here](https://github.com/)

## flaskcode
```
cd flaskcode
python storage.py
python main.py
```
 
