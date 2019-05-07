# Terraform vSphere WindowsVM example

For Virtual Machine Provisioning with Windows customization.

> Note: For module to work it needs number of required variables corresponding to an existing resources in vSphere. Please refer to variable section for the list of required variables.

## Usage

Following example contains the bare minimum options to be configured for the Windows VM deployment.

### Example of basic Windows VM

```hcl
module "example-server-windowsvm-withdatadisk" {
  source            = "Terraform-VMWare-Modules/vm3nic/vsphere"
  version           = "0.1.0"
  vmtemp            = "TemplateName"
  instances         = 1
  vmname            = "example-server-windows"
  vmrp              = "esxi/Resources"  
  net01              = "Name of the VLAN in vSphere for the first NIC"
  net02              = "Name of the VLAN in vSphere for the Second NIC"
  is_windows_image  = "true"
  dc                = "Datacenter"
  ds_cluster        = "Data Store Cluster name"
  winadminpass      = "Str0ngP@ssw0rd!" //Optional
}
```

## Authors

Originally created by [Arman Keyoumarsi](https://github.com/Arman-Keyoumarsi)

## License

[MIT](LICENSE)