Building a template to use for provider development. 
This will keep me from having forked providers on my local system

### Manual list of things to set up a Terraform provider dev environment
- Docker, if you're running a devcontainer.
- Go 1.19+ installed and configured.
- Terraform v1.5+ installed locally.

- To start the project create a new repo from a template
The naming convention for providers is `terraform-provider-<provider_name>`
```
gh repo create my-new-project --template hashicorp/terraform-provider-scaffolding-framework --private --clone
```

git clone https://github.com/hashicorp/terraform-provider-scaffolding-framework

- Template cleanup
    - delete .copywrite.hcl
    - Update license file
    - Update main and provider https://github.com/mud5150/terraform-provider-health-check/commit/d12a1b4f1fa46556de49587077b842fb8eecaf69