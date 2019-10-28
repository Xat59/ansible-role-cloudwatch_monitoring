Role Name
=========

It installs AWS monitoring scripts for Amazon CloudWatch. These sample Perl scripts comprise a fully functional example that reports memory, swap, and disk space utilization metrics for an EC2 Linux instance.

Source : https://docs.aws.amazon.com/fr_fr/AWSEC2/latest/UserGuide/mon-scripts.html

**Note :** SELinux related OS such as CentOS, RedHat or Fedora are not currently supported. This is relevant to ansible and has been issued to ansible maintainer. [Click here to see the issue](https://github.com/ansible/ansible/issues/54748). **It will be fixed as soon as possible**.

Requirements
------------

Ensure that the scripts have permission to call the following actions by associating an IAM role with your instance:
- cloudwatch:PutMetricData
- cloudwatch:GetMetricStatistics
- cloudwatch:ListMetrics
- ec2:DescribeTags

Role Variables
--------------

The following role variables are relevant:
- ```package_url``` : URL where the monitoring scripts archive is located. Default : https://aws-cloudwatch.s3.amazonaws.com/downloads/CloudWatchMonitoringScripts-1.2.2.zip .
- ```install_directory``` : Path used to install files and scripts. Default : /opt/aws-scripts-mon/ .

Dependencies
------------

No dep.

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - role: ansible-role-cloudwatch_monitoring
```

License
-------

GPL-3.0

Author Information
------------------

Jérémy Descamps
