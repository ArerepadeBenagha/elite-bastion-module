module "azure-bastion" {
  source  = "ArerepadeBenagha/elite-bastion-module/azurerm"
  version = "1.0"

  # Resource Group, location, VNet and Subnet details
  resource_group_name  = "farenow-travel"
  virtual_network_name = "dev"

  # Azure bastion server requireemnts
  azure_bastion_service_name          = "mybastion-service"
  azure_bastion_subnet_address_prefix = ["10.0.0.0/24"]

  # Adding TAG's to your Azure resources (Required)
  tags = {
    ProjectName  = "elite-demo"
    Env          = "dev"
    Owner        = "eliteuser@example.com"
    BusinessUnit = "ENG"
    ServiceClass = "Gold"
  }
}