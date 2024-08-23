# ubuntu-tutorials
Creating a virtual environment using Anaconda on Ubuntu 24.04 operating system
# Ubuntu-tutorials
Creating a virtual environment using Anaconda on Ubuntu 24.04 operating system
# A  Step to Step Guide to Install Anaconda in Ubuntu

In this repository, I am going to guide the following things 
* [How to download and install Anaconda](#how-to-download-and-install-anaconda)
  * [Downlod Anaconda Installer](#downlod-Anaconda-Installer)
  * [Installlation](#installation)
  * [How to create conda environment and run your code](#how-to-create-conda-environment-and-run-your-code)
  * [Create conda environment](#create-conda-environment )
  * [Activating `conda` environment and run your code](#activating-conda-environment-and-run-your-code)


## How to download and install Anaconda

### Downlod Anaconda Installer

You can download the Anaconda installer either using `Terminal` or `manually from the website`. Follow the steps to download it from [Anaconda Distribution Page](https://www.anaconda.com/products/individual). 


1. [Anaconda Distribution Page](https://www.anaconda.com/products/individual#linux) by entering your email account or Go to the download page by clicking 'skip registration'

   ![2024-08-22](![Ekran görüntüsü 2024-08-22 115204](https://github.com/user-attachments/assets/e0c853e2-a0f8-4485-a0a3-a04594b07645))


2. After clicking you will redirect to the page section where you can find various `Anaconda Installer`. Now you can download the `Anaconda Installer` using two approaches. 
   * **Mannual download:** 
     Download specific installer by clicking the appropiate version based on your OS. 
        ![Ekran görüntüsü 2024-08-22 115114](https://github.com/user-attachments/assets/8388b506-a575-4651-a5f9-bb69c0f744b2)
   * **Using Terminal:** 
     Right click on the link of your specific version of the installer and copy the link. Then use terminal to download the installer
         ![Ekran görüntüsü 2024-08-22 115114](https://github.com/user-attachments/assets/8388b506-a575-4651-a5f9-bb69c0f744b2)
      ```
      $ wget <link copied>
      ```  


3. `Anaconda3-2024.07-Linux-x86_64` will download.

### Installation

After downloading the installer(`Anaconda3-2024.07-Linux-x86_64`), please make sure where it is located. I put the installer in `Downloads` folder. To install, do following steps

1. Open your `Terminal` and go to the specific folder(in my case, the folder `Downloads`). Then use the following command

   ```sh
   pratik@PRATIK-YOGA:~$ cd Downloads/    
   pratik@PRATIK-YOGA:~/Downloads$ bash Anaconda3-2024.07-Linux-x86_64
   ```
 
2. You will see the following output
 
    ![93409949-a806ac00-f8b5-11ea-9276-dd8e5333580d](https://github.com/user-attachments/assets/28f22157-ff39-4304-966f-f133aefd72d3)a

3. Click `ENTER` and finally it prompts `yes or no`. Enter `yes`. It will take a few minutes to install the anaconda in your system.
 
4. The installer prompts `Do you wish the installer to initialize Anaconda3 by running conda init?` Enter `“yes”`.
 
5. **To check if Anaconda install properly, close your terminal and then reopen it. Then type** 
    ```sh
      pratik@PRATIK-YOGA:~$ conda list    
    ```
     It will show a list of packages install through Anaconda. 
    
 * If after reopening the terminal you are not getting the conda list, follow the instructions
    * Open `.bashrc` file using `vi ~/.bashrc`
    * Add the line `export PATH="/home/username/anaconda3/bin:$PATH"` in the file
    * Then execute the command `source ~/.bashrc`

## How to create conda environment and run your code

The next step is to create conda environments. To know about the details of the conda environments, you can refer to its [official documentation page](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html). Few basic steps for using the conda environment are follows

### Create conda environment 
Conda environment nothing but a virtual environment. You can customize the environment as per your requirements.
    
1. Suppose, you want to create a conda environment named `first_env`. Use the following command   
  ```sh 
  pratik@PRATIK-YOGA:~$ conda create --name first_env
  ```
    
2. Most in the cases, we need specific version of `Python`. Suppose, you need to install `Python=3.7` and the name of the environment is `second_env`, use the following command 
   ```sh
   pratik@PRATIK-YOGA:~$ conda create --n second_env python=3.7
   ```
   ** __Note, your python version of the conda environment and your local machine can be different.__
    
### Activating conda environment and run your code
1. You can have multiple `conda` environments. To see all the `conda` environments, use the following command 
    ```sh 
    pratik@PRATIK-YOGA:~$ conda info --envs
    ```
   __Output will be__
    ```sh
    # conda environments:
    #
    base                  */home/pratik/anaconda3 
    first_env              /home/pratik/anaconda3/envs/first_env
    second_env             /home/pratik/anaconda3/envs/second_env
    ```
    
2. To use any specific `conda` environment, you need to activate it. Suppose, you need to activate `second_env` environment
    ```sh 
    pratik@PRATIK-YOGA:~$ conda activate second_env
    ```
    Now, `second_env` environment is activated. You can understand from your terminal only. `pratik@PRATIK-YOGA:~$` will change to `(second_env)pratik@PRATIK-YOGA:~$`
    
3. Now you can run your code in this terminal. For your project, if you need to install any package, you can do that following way
  * __Install specific package:__ Suppose you need to install `tensorflow` package in your `conda` environment  
  ```sh 
    (second_env)pratik@PRATIK-YOGA:~$ conda install -c conda-forge tensorflow
  ```
  * __Install specific package with specific version:__ Suppose you need to install `tensorflow 1.14` version package in your `conda` environment 
  ```sh 
    (second_env)pratik@PRATIK-YOGA:~$ conda install -c conda-forge tensorflow=1.14
