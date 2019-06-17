## This repository is created with learning purposes for Terraform.

## Purpose :

- It provides a simple example of how to use Terraform `null_resource` with local state file.

## How to install terraform : 

- The information about installing terraform can be found on the HashiCorp website 
[here](https://learn.hashicorp.com/terraform/getting-started/install.html)

## How to use it :

- In a directory of your choice, clone the github repository :
    ```
    git clone https://github.com/martinhristov90/terraformLocalState.git
    ```

- Change into the directory :
    ```
    cd terraformLocalState
    ```

- Run `terraform init` to download the `null` provider.

- Run `terraform plan` to see what actions are going to be performed Terraform. Output should look like this :
    ```
    ------------------------------------------------------------------------

    An execution plan has been generated and is shown below.
    Resource actions are indicated with the following symbols:
      + create

    Terraform will perform the following actions:

      + null_resource.helloWorld
          id: <computed>


    Plan: 1 to add, 0 to change, 0 to destroy.

    ------------------------------------------------------------------------
    ```

- Run `terraform apply` to create the `null_resource` resource. As output you should see :
    ```
    null_resource.helloWorld: Creating...
    null_resource.helloWorld: Provisioning with 'local-exec'...
    null_resource.helloWorld (local-exec): Executing: ["/bin/sh" "-c" "echo hello world"]
    null_resource.helloWorld (local-exec): hello world
    null_resource.helloWorld: Creation complete after 0s (ID: 4992259830273505160)

    Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
    ```
    
- In order to destroy the created resources, you can use `terraform destroy`.