# Terraform
Here's an extensive list of Terraform CLI commands.

### **Terraform CLI Commands**

#### **1. Initialization and Configuration**

- **Initialize a new or existing Terraform configuration:**
  ```sh
  terraform init
  ```

- **Reconfigure the backend and ignore existing configuration:**
  ```sh
  terraform init -reconfigure
  ```

- **Validate the configuration files:**
  ```sh
  terraform validate
  ```

- **Format the configuration files:**
  ```sh
  terraform fmt
  ```

- **Check for formatting issues without changing files:**
  ```sh
  terraform fmt -check
  ```

- **Generate and show the execution plan:**
  ```sh
  terraform plan
  ```

- **Save the plan to a file:**
  ```sh
  terraform plan -out=tfplan
  ```

- **Show the saved plan file:**
  ```sh
  terraform show tfplan
  ```

#### **2. Applying and Destroying Infrastructure**

- **Apply the changes required to reach the desired state of the configuration:**
  ```sh
  terraform apply
  ```

- **Apply using the saved plan file:**
  ```sh
  terraform apply tfplan
  ```

- **Destroy the infrastructure managed by Terraform:**
  ```sh
  terraform destroy
  ```

- **Target specific resources for destruction:**
  ```sh
  terraform destroy -target=resource_type.resource_name
  ```

#### **3. State Management**

- **List resources in the Terraform state:**
  ```sh
  terraform state list
  ```

- **Show attributes of a single resource in the state:**
  ```sh
  terraform state show resource_type.resource_name
  ```

- **Move a resource to a new address:**
  ```sh
  terraform state mv old_address new_address
  ```

- **Remove a resource from the state file:**
  ```sh
  terraform state rm resource_type.resource_name
  ```

- **Import existing infrastructure into Terraform:**
  ```sh
  terraform import resource_type.resource_name resource_id
  ```

#### **4. Workspaces**

- **List all workspaces:**
  ```sh
  terraform workspace list
  ```

- **Create a new workspace:**
  ```sh
  terraform workspace new workspace_name
  ```

- **Select a workspace:**
  ```sh
  terraform workspace select workspace_name
  ```

- **Delete a workspace:**
  ```sh
  terraform workspace delete workspace_name
  ```

#### **5. Modules**

- **Add a module to the configuration:**
  ```hcl
  module "module_name" {
    source = "module_source"
    # other module configurations
  }
  ```

- **Get and update modules:**
  ```sh
  terraform get
  terraform get -update
  ```

#### **6. Output Management**

- **Display the outputs of the Terraform configuration:**
  ```sh
  terraform output
  ```

- **Display a specific output value:**
  ```sh
  terraform output output_name
  ```

- **Save the outputs to a file:**
  ```sh
  terraform output -json > outputs.json
  ```

#### **7. Terraform Cloud and Enterprise**

- **Login to Terraform Cloud:**
  ```sh
  terraform login
  ```

- **Set the workspace to Terraform Cloud:**
  ```hcl
  terraform {
    cloud {
      organization = "my-org"

      workspaces {
        name = "my-workspace"
      }
    }
  }
  ```

#### **8. Advanced Techniques**

- **Lock and unlock the state file:**
  ```sh
  terraform force-unlock LOCK_ID
  ```

- **Enable detailed logging:**
  ```sh
  export TF_LOG=TRACE
  terraform plan
  ```

- **Graph the dependency tree of resources:**
  ```sh
  terraform graph | dot -Tsvg > graph.svg
  ```

- **Generate a configuration from existing infrastructure:**
  ```sh
  terraform import resource_type.resource_name resource_id
  ```

- **Apply changes automatically without prompting for approval:**
  ```sh
  terraform apply -auto-approve
  ```

#### **9. Best Practices**

- **Use version control for configuration files:**
  - Store all `.tf` files in a version control system (e.g., Git).

- **Use consistent formatting:**
  - Regularly run `terraform fmt` to maintain consistent code style.

- **Use modules for reusable code:**
  - Break down infrastructure into reusable modules.

- **Use workspaces for different environments:**
  - Use Terraform workspaces to manage different environments (e.g., development, staging, production).

- **Secure state files:**
  - Store Terraform state files securely (e.g., in an encrypted S3 bucket with DynamoDB for locking).

- **Plan before applying:**
  - Always run `terraform plan` before `terraform apply` to understand changes.

This extensive list should cover most of the common and advanced use cases for managing infrastructure using Terraform.
