Here are a few steps to ensure your AWS credentials are correctly configured:

### 1. Verify Environment Variables
First, double-check that the environment variables are correctly set in the current PowerShell session:

```powershell
echo $Env:AWS_ACCESS_KEY_ID
echo $Env:AWS_SECRET_ACCESS_KEY
```

If these commands return the correct values, then the variables are set.

### 2. Configure AWS CLI Using `aws configure`
Another way to set up your credentials is by using the `aws configure` command, which stores your credentials in a configuration file:

```powershell
aws configure
```

You'll be prompted to enter:
- AWS Access Key ID
- AWS Secret Access Key
- Default region name (e.g., us-west-2)
- Default output format (e.g., json)

This method stores your credentials in the AWS credentials file located in `C:\Users\YourUsername\.aws\credentials`.

### 3. Manually Set Environment Variables (Alternative Approach)
If the environment variables are still not picked up, you can manually set them in the PowerShell session:

```powershell
$Env:AWS_ACCESS_KEY_ID = "YourAccessKeyID"
$Env:AWS_SECRET_ACCESS_KEY = "YourSecretAccessKey"
```

After setting the environment variables, try running the `aws iam list-users` command again.

### 4. Check AWS CLI Configuration
Ensure that your AWS CLI is correctly configured to use the environment variables. You can check this by running:

```powershell
aws configure list
```



For windows

To load environment variables from a `.env` file in PowerShell, you should use the following approach:

1. Change the syntax in the `.env` file to:
   ```
   $Env:AWS_ACCESS_KEY_ID="AKIAQKYHEQAlGTSLFF5V"
   $Env:AWS_SECRET_ACCESS_KEY="XEhh9qovYqGGMpZaK6RzDqMPJBegA914hF0S1Uj2"
   ```

2. Instead of using `source`, you can run the `.env` file in PowerShell like this:
   ```powershell
   . .\.env
   ```

The dot (`.`) followed by a space and then the file path will execute the file in the current shell, setting the environment variables.

load your AWS credentials correctly.

Here's a breakdown of the correct sequence of Terraform commands, with some corrections for accuracy:

1. **Initialize the Terraform Working Directory**:
   This command initializes the directory, downloads necessary provider plugins, and prepares the environment for Terraform operations.
   ```bash
   terraform init
   ```

2. **Validate the Terraform Configuration**:
   This command checks whether the configuration files are syntactically correct and if the resources can be successfully created.
   ```bash
   terraform validate
   ```

3. **Plan the Infrastructure Deployment** (instead of "terraform build"):
   Terraform doesn't have a `build` command. The `terraform plan` command is used to create an execution plan showing what actions Terraform will take to build or modify the infrastructure.
   ```bash
   terraform plan
   ```

4. **Apply the Terraform Configuration**:
   This command executes the actions proposed in the `terraform plan` to create, modify, or destroy infrastructure.
   ```bash
   terraform apply
   ```

### Correct Workflow
Here is the correct sequence:

```bash
terraform init       # Initialize the working directory
terraform validate   # Validate the configuration
terraform plan       # Create an execution plan
terraform apply      # Apply the plan and deploy the infrastructure
```

By following this sequence, you will successfully set up your infrastructure using Terraform.
