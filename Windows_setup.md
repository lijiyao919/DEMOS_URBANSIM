# Environment config
*Install miniconda and add miniconda path the environment variables, the operation is as follows:*
**Open System Properties:**
Search for "Environment Variables" in the Windows search bar and select "Edit the system environment variables".
**Add Miniconda Path:**
In the System Properties window, click on the "Environment Variables..." button.
Under "System variables", select the Path variable and click "Edit".
Click "New" and add the path to Miniconda's Scripts folder (e.g., C:\Users\YourUsername\Miniconda3\Scripts).
**Verify Installation:**
Open a new Command Prompt or PowerShell window.
Type conda --version and press Enter. If installed correctly, this command should display the Conda version installed on your system.

*After installition, create the environment in command prompt with miniconda*

**Environment creating:**
'conda create --name {myenv} python=3.8'
**Environment Activating**
'conda activate {myenv}'
**Requirements.txt downloading**
use cd comand to change to the directory where you store the project.
'pip install -r requirements.txt'

# Runing
*Before runing, a few modifications are necessary to ensure compatibility with Windows.*

## In simulate.py, remove line 2 'import grp' and line 4 'import pwd'
These two packages are not used but are not compatibal with Windows.

## Get the required input data 'skims_mpo_06197001.omx' and 'custom_mpo_06197001_model_data.h5'
These two data are necessary for runing the model, storaged in data directory.

## Comment out the unrelated models in models.py line 4281-4300
Only keep 'demo_models', 'end_of_year_models', and 'export_demo_steps'

## Run 
Use code 'python -u simulate.py -c -cf custom -l -r 06197001' in command prompt to run the project.
AttributeError: module 'os' has no attribute 'chown' will be given but the result file 'model_data_{year}.h5' will still be obatined.