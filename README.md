DVC (Data Version Control) is used in machine learning projects alongside Git because it addresses several challenges specific to managing data, models, and pipelines that Git alone is not designed to handle. Here’s why DVC is valuable for machine learning:

1. Versioning Large Datasets and Models
Problem with Git: Git is great for versioning code but not for handling large files like datasets, model weights, or other binary files. Git’s performance and storage can degrade significantly when dealing with large files.
DVC Solution: DVC allows version control of large files without storing them directly in Git. Instead, DVC tracks file changes via metadata (small text files) and stores the actual files in external storage (cloud, local, etc.).
2. Data Pipelines and Experiment Management
Problem with Git: Git can track code changes, but it doesn't track data, models, or pipeline stages well. It's difficult to know which data and model versions were used in specific experiments just by looking at Git history.
DVC Solution: DVC helps you define pipelines that can track dependencies between stages (data preprocessing, model training, etc.). It also keeps track of which datasets, parameters, and models were used for each experiment, making it easier to reproduce results.
3. Efficient Storage and Sharing
Problem with Git: If you use Git for data and models, you would need to store everything in the Git repository, leading to bloated repositories that are difficult to clone and work with.
DVC Solution: DVC stores large data and models outside of Git (e.g., cloud storage like AWS S3, Google Drive) while keeping references to them in the Git repo. This allows the repository to stay lightweight while still tracking data changes.
4. Reproducibility
Problem with Git: Git alone cannot ensure that a machine learning experiment can be fully reproduced, as it doesn’t track external dependencies like data, model outputs, and hyperparameters.
DVC Solution: DVC captures all relevant information, including data versions, experiment metadata, and pipeline stages, ensuring that you can reproduce an experiment with the same data, code, and settings.
5. Collaboration on Large Data Projects
Problem with Git: Sharing large datasets or trained models through Git is impractical, and collaborating on data-heavy machine learning projects requires a better way to share and version control these assets.
DVC Solution: DVC makes it easy to collaborate on large datasets and models by allowing team members to fetch the required data from remote storage when needed, without overloading the Git repository.
6. Integration with Existing Tools
DVC works alongside Git without replacing it. It integrates smoothly into existing Git workflows, enabling machine learning teams to continue using Git for versioning code while using DVC for managing data, models, and pipelines.


MLFLOW_Tracking_URI = "https://dagshub.com/1602saurab/zl.mlflow"
--------------------------------------------------
import dagshub
dagshub.init(repo_owner='1602saurab', repo_name='zl', mlflow=True)

import mlflow
with mlflow.start_run():
  mlflow.log_param('parameter name', 'value')
  mlflow.log_metric('metric name', 1)

------------------------------------------------------
MLFLOW_Tracking_username = 1602saurab
MLFLOW_Tracking_password = 
pytho script.py 

-----------------------------------------------------

Now open the terminal(bash) and write 
export https://dagshub.com/1602saurab/zl.mlflow

export MLFLOW_Tracking_username = 1602saurab
export MLFLOW_Tracking_password  = 


