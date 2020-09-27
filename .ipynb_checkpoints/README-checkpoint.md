# [ARCADAHAI] Deep Convolutional Networks for Text Classification on Valohai platform 

The model is described in the Paper: [VERY DEEP CONVOLUTIONAL NETWORKS FOR TEXT CLASSIFICATION] (https://arxiv.org/abs/1606.01781)

Recommend to read the list before start working with Valohai platform:

* [Git](https://git-scm.com/doc): For software version control.
* [Docker](https://docs.docker.com): For environment set-up.
* [Python argparse](https://docs.python.org/3/library/argparse.html), [Tensorflow tf.flags](https://stackoverflow.com/questions/33932901/whats-the-purpose-of-tf-app-flags-in-tensorflow): For user-friendly command-line interface. 
* [YAML](https://yaml.org): Yet Another Markup Language xD 
## Training Model on Valohai Platfrom 

1. Log in to Valohai Platform with your account 

2. Create a new **Project**. Go to **Settings** tab, choose **Repository**. Copy the Github link project to **URL** and **SAVE**. Valohai will automatically Fetch repository from Github to Valohai Platform. URL for this project: 

    > https://github.com/phanthaithuc/deep-cnn 

3. Go to **Execution** tab, **Create Execution**, Valohai will read the _valohai.yaml_  and give you many options for **Parameters**

4. Choose your preferrence parameters and start training.

5. To change **Docker image** or change running step, edit the _valohai.yaml_ file or choose another Docker image in **Image and Command** section on Valohai web interface. 

6. To commit another version of your code. **Git push** your new version to Github then click  **Fetch Repository** button on your Valohai project. 

    Valohai will fetch the new version and show another commit option based on your new version of code under **Commit**

7. To train with another dataset with Valohai. There are 2 options: 
    
    * Go to **Data** tab on your project, upload your train set and test set to Valohai storage. Go back to **Execution** tab, choose your _Data file_ under **Input** section.
    
    * If you have your dataset uploaded somewhere on the Internet, copy your direct link to _URL_ under **Input** section. Done 
    
For more datasets, see **Training Dataset** below. The datasets which come from the author of the paper is open and free to use. 
    


## Training Model on your Local Machine

1. **Clone** or **Download** this Project from GitHub. 

2. Run this Project with default Parameters

    > python train.py 
   
3. Run this Project with your chosen Parameters: 

    python train.py --lr  _learning_rate_  --num_epochs  _number of epochs_  --batch_size _batch size_
    
    For example: 

    > python train.py --lr 0.005  --num_epochs 10 --batch_size 128
    
    Read train.py for more preference parameters 

4. To train with other datasets. 

      * Download more datasets from this [LINK](https://drive.google.com/drive/u/0/folders/0Bz8a_Dbh9Qhbfll6bVpmNUtUcFdjYmF2SEpmZUZUcVNiMUw1TWN6RDV3a0JHT3kxLVhVR2M). 
   
     * Copy new _train.csv_ and _test.csv_ to **data** folder. Start training with your new dataset. 
     
     
    

    

## Machine learning model Version control with Valohai**

    * **Valohai store the metada of num_epoch, learning_rate, ... all parameters for each train and save the meta data with exported model**
    
![valohai](results/valohai.png)
    
    
 ## Result

|     Depth     |       9      |       17     |       29     |       49     |
|:---------------:|:--------------:|:--------------:|:--------------:|:--------------:|
|    ag_news    | 87.67(90.17) | 88.09(90.61) | 88.01(91.33) |    84.71     |
|   sogu_news   | 95.67(96.42) | 95.89(96.49) | 95.73(96.82) |    95.35     |
|    db_pedia   | 98.33(98.44) | 98.28(98.39) | 98.07(98.59) |    97.38     |
| yelp_polarity | 94.57(94.73) | 95.20(94.95) | 94.95(95.37) |    95.08     |
|  yelp_review  | 62.44(61.96) | 63.44(62.59) | 62.70(63.00) |    62.83     |
|  yahoo_answer | 69.57(71.76) | 70.03(71.75) | 70.34(72.84) |    69.16     |
| amazon_review | 60.34(60.81) | 60.98(61.19) | 60.67(61.61) |    59.80     |
|amazon_polarity| 94.30(94.31) | 94.60(94.57) | 94.53(95.06) |    94.10     |

Below are the training/test loss/accuracy curves for each dataset's experiments (figures for 9, 17, 29-layer model are from left to right) :

- **ag_news**

<img src="results/ag_news_depth_9.png" width="280"> <img src="results/ag_news_depth_17.png" width="280"> <img src="results/ag_news_depth_29.png" width="280"> 

- **sogou_news**

<img src="results/sogou_news_depth_9.png" width="280"> <img src="results/sogou_news_depth_17.png" width="280"> <img src="results/sogou_news_depth_29.png" width="280">

- **db_pedia**

<img src="results/dbpedia_depth_9.png" width="280"> <img src="results/dbpedia_depth_17.png" width="280"> <img src="results/dbpedia_depth_29.png" width="280"> 

- **yelp_polarity**

<img src="results/yelp_review_polarity_depth_9.png" width="280"> <img src="results/yelp_review_polarity_depth_17.png" width="280"> <img src="results/yelp_review_polarity_depth_29.png" width="280"> 

- **yelp_review**

<img src="results/yelp_review_full_depth_9.png" width="280"> <img src="results/yelp_review_full_depth_17.png" width="280"> <img src="results/yelp_review_full_depth_29.png" width="280"> 

- **amazon_review**

<img src="results/amazon_review_full_depth_9.png" width="280"> <img src="results/amazon_review_full_depth_17.png" width="280"> <img src="results/amazon_review_full_depth_29.png" width="280"> 

- **amazon_polarity**

<img src="results/amazon_review_polarity_depth_9.png" width="280"> <img src="results/amazon_review_polarity_depth_17.png" width="280"> <img src="results/amazon_review_polarity_depth_29.png" width="280"> 
