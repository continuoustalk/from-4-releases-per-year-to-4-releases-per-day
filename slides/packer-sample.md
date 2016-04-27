```json
{
  "variables": {
    "site_type": "",
    "mysql_password": ""
  },
  "builders": [{
    "type": "amazon-ebs",
    "source_ami": "ami-********",
    "ami_name": "{{user `site_type`}}-dev {{timestamp}}",
    "iam_instance_profile" : "acceptance"
  }],
  "provisioners":[ {
    "type": "salt-masterless",
    "local_state_tree": "salt"
  }]
}
```
