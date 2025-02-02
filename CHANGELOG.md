# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

## 5.12.4 - 2022-03-11
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.9.3

## 5.12.3 - 2022-03-01
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.9.2

## 5.12.2 - 2022-02-25
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.9.1

## 5.12.1 - 2022-02-14
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.9.0

## 5.12.0 - 2022-02-04
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.8.2

## 5.11.0 - 2021-12-17
### Added
- Add permission for components instance profile to retrieve SSM parameter with /aem-opencloud/* prefix

## 5.10.0 - 2021-12-02
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.8.0

## 5.9.0 - 2021-11-22
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.7.0

## 5.8.0 - 2021-11-19
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.6.0

## 5.7.0 - 2021-11-17
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.5.1

### Fixed
- Fix Consolidated deploy on init timeout configuration

## 5.6.0 - 2021-11-10
### Changed
- Update Simian Army artifact URL to use main branch [#441]
- Update awscli to 1.22.1
- Update boto3 to 1.20.0
- Update boto to 2.49.0
- Update botocore to 1.23.1
- Update Ansible to 4.8.0

## 5.5.1 - 2021-11-03
### Fixed
- Fix broken Netflix Bintray Simian Army artifact package URL by switching to a mirror location [#441]

## 5.5.0 - 2021-10-26
### Added
- Option to execute an Apache graceful or hard restart when deploying artifacts
- Set Python3 to be the default for Ansible
- Proxy provisioning feature toggle on cloud-init user data for both Full-Set and Consolidated
- Add release-major, release-minor, release-patch, and publish Makefile targets and GitHub Actions

### Changed
- Upgrade AEM AWS Stack Provisioner to 5.5.0

### Fixed
- Fix CloudWatch Dashboard load balancer metrics [#435]
- Fix incorrect keyword into KMSMasterKeyID during AWS Resources S3 Bucket creation
- Use long form Keywords to work with ‘make config’ target

## 5.4.0 - 2021-06-18
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.2.0

## 5.3.0 - 2021-05-02
### Added
- Add log message on finishing stack builder provisioning

### Changed
- Upgrade AEM AWS Stack Provisioner to 5.2.0
- Upgrade AEM Stack Manager Messenger to 2.14.1
- Upgrade AEM Hello World Custom Stack Provisioner to 0.15.0
- Upgrade AEM Test Suite to 2.0.0

## 5.2.2 - 2021-03-12
### Changed
- Update Ansible to 3.1.0

## 5.2.1 - 2021-03-03
### Changed
- Upgrade AEM AWS Stack Provisioner to 5.1.0

## 5.2.0 - 2021-03-02
### Changed
- update awscli to 1.19.8
- update boto3 to 1.17.8
- update botocore to 1.20.8
- Update Ansible to 3.0.0
- Update jinja2 to 2.11.3

## 5.1.0 - 2021-02-11
### Changed
- Lock down pylint to 2.6.0
- Use Python3 virtualenv for GitHub actions
- Use pip3 for python package management
- Convert python scripts to be executed using Python 3
- Set default Ansible Python interpreter to python3

### Fixed
- Fix missing Publish-Dispatcher ELB Scheme value with config param PublishDispatcherLoadBalancerSchemeParameter. [#429]

## 5.0.2 - 2020-12-02
### Changed
- Upgrade AEM Orchestrator to 3.0.1

## 5.0.1 - 2020-12-01
### Fixed
- Fixed Consolidated Encryption parameters

## 5.0.0 - 2020-12-01
### Changed
- Changed default Load Balancer Listener SSL Policy `compute.elb_cipher_suite` to `ELBSecurityPolicy-TLS-1-2-2017-01`
- Configuring Load Balancer deregistration delay to 30 seconds
- Replaced Classic Load Balancer for Author, Author-Dispatcher & Publish-Dispatcher with Application Load Balancers [#41]
- Upgrade AEM Orchestrator library to version 3.0.0 [#41]
- Upgrade AEM AWS Stack Provisioner to 5.0.0

### Removed
- Removed insecure HTTP Ports from Load Balancer

## 4.42.0 - 2020-11-16
### Added
- Add new reconfiguration parameter `reconfiguration.[author|publish].aem_ssl_method`
- Added missing certificate permission for Consolidated

### Changed
- Upgrade AEM AWS Stack Provisioner to 4.38.0
- Upgrade AEM Stack Manager Cloud to 1.9.1

### Removed
- Removed deprecated configuration parameters [#371]

### Fixed
- Fix Network component playbook
- Fix AEM jvm_opts default value

## 4.41.0 - 2020-06-15
### Added
- Added configurable ttl value for Switch-DNS function. [#411]

### Changed
- Changed default parameter `compute.elb_cipher_suite` to `AOCELBSecurityPolicy-TLS-1-2-2017-01`
- Disable TLS 1.0 & TLS 1.1 support for Author-Dispatcher, Publish-Dispatcher & Author ELB

### Fixed
- Fixed Stack deletion process for **permission-type c** when AWS resource encryption via CMK is enabled[#407]

## 4.40.0 - 2020-05-14
### Added
- Added new parameters to parameterise Publish-Dispatcher ASG Scaling policies cooldown timer [#405]
- Add new configuration parameters `aem.[author|publish].run_modes` for configuring AEM run_modes

### Changed
- Increase SSM Document `RunAEMUpgrade` default sleep timer to `1200` seconds [#401]
- Increase SSM Document `AEM-ExportPackage`,`AEM-ExportPackages`,`AEM-DeployArtifacts` & `AEM-ImportPackage` default executionTimeout to `14400` seconds [#401]
- Increase default Publish-Dispatcher ASG Scale out policy cooldown time from `480` to `2880` seconds
- Change CPU Utilization alarm metric statistic to Maximum  [#398]
- Upgrade AEM AWS Stack Provisioner to 4.36.2

### Removed
- Removed configuration parameters `reconfiguration.[author|publish].run_modes`

### Fixed
- Fixed Author-standby sync issue [#280]
- Fix missing hiera parameters for author-standby promotion

## 4.39.0 - 2020-04-15
### Added
- Add new configuration parameter for the reconfiguration process to update the location of the AEM Keystore [shinesolutions/packer-aem#209]

### Changed
- Upgrade AEM AWS Stack Provisioner to 4.34.0

## 4.38.0 - 2020-03-19
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.33.0

## 4.37.0 - 2020-03-18
### Added
- Add variable jvm_mem_opts to configure JVM Memory for offline compaction in order to solve our-of-memory failure in c4.xlarge (7.5Gb  memory)

### Changed
- Upgrade AEM AWS Stack Provisioner to 4.32.0
- Update stack-init script to change dir to custom-stack-provisioner path

## 4.36.1 - 2020-03-13
### Fixed
- Fix incorrect version number for AEM AWS Stack Provisioner upgrade to 4.31.0

## 4.36.0 - 2020-03-09
### Added
- Add Tagging support to AEM Stack Manager DynamoDB
- Add Tagging support to AOC managed S3 Bucket
- Add boto library, which is required for the Ansible switch dns module
- Add `aws_region` support for `stack-init` script [shinesolutions/aem-opencloud-manager#65]

### Changed
- Update boto3 and botocore verison to fix incompatible pip installation error
- Remove stack-prefix from the value used in the dns switch pipeline, since the config includes stack-prefix.
- Update documentation for EBS volume encryption
- Change default live snapshot to not run between 1am to 2am
- Upgrade AEM Stack Manager Cloud to 1.8.0
- Upgrade AEM AWS Stack Provisioner to 4.31.0

## 4.35.1 - 2020-03-02
### Fixed
- Add missing CF Stack output parameter for full-set permission type c [#378]

## 4.35.0 - 2020-03-01
### Added
- Add support for Dispatcher Data volume device to consolidated [#379]

### Changed
- Increase SSM Timeout for offline-compaction-snapshot to 14400 sec
- Increase SSM Timeout for offline-snapshot to 14400 sec
- Increase SSM Timeout for test-readiness to 14400 sec
- Improve error handling for stack-init script
- Upgrade AEM Stack Manager Cloud to 1.6.0
- Upgrade AEM Stack Manager Messenger to 2.11.0
- Upgrade AEM AWS Stack Provisioner to 4.29.0
- Upgrade AEM Test Suite to 1.15.0

### Removed
- Remove configuration parameter `aem.snapshot_attach_timeout`

## 4.34.0 - 2020-02-23
### Added
- Added HTTPS endpoint SNS topic Subscription
- Added new configuration properties `stack_manager.alarm_notification.https_endpoint` and `messaging.alarm_notification.https_endpoint`
- Any secgroup for allowing inbound rule from Jumphost is now configured as part of `<component>.extra_groups`

### Removed
- Removed configuration property `inbound_from_bastion_host_security_group`

## 4.33.0 - 2020-02-09
### Added
- Add new configuration parameter `aws.encryption.ebs_volume.enable` to enable EBS Volume encryption#370
- Add feature to encrypt EBS Volues with CMK [#370]
- Add feature to attach manage policy to EC2 instance role for accessing CMK for **permission-type b**  [#370]
- Add feature to grant access to to EC2 instance role for accesing the CMK if no manage policy provided for **permission-type b**  [#370]
- Add feature to define CMK for SSE DynamoDB Table encryption [#370]
- Add feature to define CMK for encrypting Lambda functions environment variables [#370]
- Add feature to define CMK for SSE S3 Buckets encryption [#370]
- Add feature to define CMK for SSE SNS Topic & SNS Queue encryption [#370]
- Add Monitoring Stack to AEM Full-Set permission type c

### Changed
- Configuration parameters `[aem_component].enable_vol_encryption` are now deprecated and replaced with `aws.encryption.ebs_volume.enable` [#371]

## 4.32.0 - 2020-02-05
### Changed
- Increased CPU Utilization Alarm Threshold to 60 for Warning and 90 for Critical

## 4.31.0 - 2020-01-31
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.28.0

## 4.30.0 - 2020-01-20
### Changed
- Replace Maven Central base URL from http://central.maven.org to https://repo.maven.apache.org
- Upgrade AEM Stack Manager Messenger to 2.10.0
- Upgrade AEM Test Suite to 1.13.0

## 4.29.0 - 2020-01-14
### Changed
- Upgrade AEM Test Suite to 1.11.0

### Fixed
- Fix invalid tab char on publish-dispatcher CF template

## 4.28.0 - 2020-01-14
### Removed
- Remove SNS topic from PublishDispatcher AVGCPU load alarm low since it's only used for scaling policy

## 4.27.0 - 2020-01-09
### Changed
- Add memory alarms across all AEM Full-Set components
- Add Dispatcher data volume metric to monitoring stack's CloudWatch dashboard
- Remove AEM Full-Set generic SNS topic, migrate existing alarms to Critical/Warning SNS topics

## 4.26.0 - 2019-12-24
### Added
- Add feature to enable removal of all available Cloudwatch Loggroups while deleting an AEM Stack [#366]

### Changed
- Upgrade AEM AWS Stack Provisioner to 4.27.0
- Upgrade AEM Test Suite to 1.9.0

## 4.25.0 - 2019-12-17
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.26.0

## 4.24.0 - 2019-12-03
### Added
- Add overwrite option for aws_s3 ansible module in stack-data [#359]
- Add new SSM command to run ToughDay 2 performance tests
- Added JVM monitoring to CloudWatch Dashboard
- Added to FAQ to explain why the admin user password change can fail
- Added to FAQ to explain why the system user configuration parameters changed [#352]
- Add new configuration parameters `system_users.[author|publish].[admin|deployer|exporter|importer|orchestrator|replicator].[name|path]` [#352]
- Add new hiera parameter `author::aem_system_users` & `publish::aem_system_users` [#352]

### Changed
- Extend timeout for snapshot purge lambda function from 5 mins to 15 mins
- Changed data collection method for CloudWatch Dashboard (MemoryUtilization, Latency, ... )
- Change AEM Stack Manager DynamoDB Billing mode from `PROVISIONED` to `PAY_PER_REQUEST` [#356]
- Increase AEM Stack Manager Lambda timeout from 15 seconds to 60 seconds [#356]
- configuration parameter `system_users.[author|publish].admin.path` (previously known as `system_users.admin.path`) is now a *mandatory* parameter
- Update FAQ for reconfiguration with new system_users parameters [#352]
- Upgrade AEM AWS Stack Provisioner to 4.25.0
- Upgrade AEM Stack Manager Messenger to 2.9.0
- Upgrade AEM Test Suite to 1.7.0
- Stack Manager MinimumPublishInstances configuration now uses `stack_manager.publish.asg_min_size` instead of `publish.asg_min_size`

### Removed
- Removed deletion of the deployment descriptor file for main stack deletion [#358]
- Removed configuration parameters `system_users.[admin|deployer|exporter|importer|orchestrator|replicator]` [#352]
- Removed hiera parameter `common::aem_system_users` [#352]

### Fixed
- Fix upload descriptor file logic [#359]
- Fix Consolidated DNS switch incorrectly generate Author-Dispatcher target
- Fixed documentation about the export-backups-descriptor
- Fix CloudWatch Dashboard for Consolidated DNS switch incorrectly generate Author-Dispatcher target
- Fix CloudWatch Dashboard Author Naming (Primary and Standby)

## 4.23.2 - 2019-10-17
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.20.1

### Fixed
- Pass configuration `aem.enable_bak_files_cleanup` as boolean [#341]

## 4.23.1 - 2019-10-17
### Fixed
- Fixed parameter passing for controlling EBS volume encryption [#339]

## 4.23.0 - 2019-10-16
### Added
- Add Certificate manager & Secrets manager support for certificate handling when reconfiguration runs
- Add new configuration parameter `run_modes` for reconfiguration

### Changed
- Replaced reconfiguration parameter `certs_base` with `certificate_arn` & `certificate_key_arn`
- Update FAQ topic to `reconfiguration`
- Upgrade AEM AWS Stack Provisioner to 4.20.0

### Removed
- Removed reconfiguration parameter `create_system_users`, as it doesn't had any functionality
- Add new component parameter to control EBS volume encryption

## 4.22.0 - 2019-10-16
### Added
- Added ELB Metrics to CloudWatch Dashboard panel

## 4.21.0 - 2019-10-14
### Changed
- Restructure monitoring stack's CloudWatch Dashboard panels

## 4.20.0 - 2019-10-13
### Added
- Add region to DNS switch to fix issue related to CloudFormation facts

## 4.19.0 - 2019-10-08
### Added
- Add new permissions for AEM Stack Manager to allow updating ASG scaling processes [#295]

### Changed
- Rename switch-dns parameters for consistency with AOC Manager parameter names
- Upgrade AEM Stack Manager Cloud to 1.5.0
- Upgrade AEM AWS Stack Provisioner to 4.19.0
- Update default path for httpd logfile logrotation to handle log files named with .log and _log suffixes

## 4.18.0 - 2019-10-01
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.18.0

### Fixed
- Change new scheduled job parameters for scheduling the cronjob from `cloudwatch_s3_Stream` to `cloudwatch_s3_stream`

## 4.17.0 - 2019-09-23
### Added
- Add function for switching DNS by setting DNS record of a given zone to point to an AEM stack

### Fixed
- Fixed syntax issue for Monitoring Cloudformation Stack template by replacing shorthands with functions
- Fix monitoring stack's aemAsgEventQueueName param to use output from prerequisites stack prefix

## 4.16.0 - 2019-09-21
### Changed
- Modify extra groups handling to allow sub property names

## 4.15.1 - 2019-09-21
### Fixed
- Fix Consolidated config extra groups to check for exact resource name

## 4.15.0 - 2019-09-21
### Added
- Add security group support for Consolidated AuthorPublishDispatcher instance

## 4.14.0 - 2019-09-21
### Added
- Add support for adding extra secgroups to EC2 instances

### Changed
- Upgrade AEM AWS Stack Provisioner to 4.17.0
- Refactor cf_security_groups module to add secgroups to any resource

## 4.13.0 - 2019-09-19
### Added
- Add new Stack Manager function CloudwatchS3Stream
- Add new parameters to control the AEM Stack cloudwatch log s3 stream
- Add new scheduled job parameters for scheduling the cronjob `cloudwatch_s3_Stream`

### Changed
- Upgrade AEM Stack Manager Cloud to 1.4.0
- Ignore missing logfiles in default logrotation rules

## 4.12.0 - 2019-09-12
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.16.0

## 4.11.0 - 2019-09-07
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.15.0

## 4.10.0 - 2019-09-05
### Added
- Add new parameters to define SSH public keys to deploy on the AEM Stack [#313]

## 4.9.0 - 2019-08-22
### Added
- Add new SSM commands to manage SAML configuration

### Changed
- Change config property monitoring.include_stack default value to false

## 4.8.0 - 2019-08-16
### Added
- Add CloudFront CDN support [#306]
- Add CloudWatch dashboard support for AEM Full-Set
- Add AWS resources integration testing
- Add hiera parameter proxy_enabled for configuring collectd proxy settings shinesolutions/puppet-aem-curator#134

### Changed
- Upgrade AEM AWS Stack Provisioner to 4.13.0
- Upgrade AEM Stack Manager Messenger to 2.7.0
- Upgrade AEM Test Suite to 1.4.0
- Change config property aem.enable_post_start_sleep default value to true
- Change config property aem.post_start_sleep_seconds default value to 180
- Change config property publish_dispatcher.asg_health_check_grace_period default value to 2400
- Change config property publish.asg_health_check_grace_period default value to 1800
- Change config property aem.snapshot_attach_timeout default value to 1800

### Fixed
- Fix invalid ServerSideEncryptionByDefault with null value when creating AWS resources S3 bucket

## 4.7.0 - 2019-08-06
### Added
- Added additional exit code checks to stack init process [#294]
- Add aem.snapshot_attach_timeout configuration property

### Changed
- Redirecting custom stack provisioner pre & post hook output to own logfile [#298]
- Upgrade AEM Stack Manager Messenger to 2.5.0
- Upgrade AEM Test Suite to 1.3.0
- Upgrade AEM HelloWorld Custom Stack Provisioner to 0.14.0
- Upgrade AEM Stack Manager Cloud to 1.3.5
- Upgrade AEM AWS Stack Provisioner to 4.8.0

### Fixed
- Suppress error `aws s3api head-object` stdout & stderr [#48]
- Fixed error with generating stack manager config [#302]

## 4.6.0 - 2019-07-24
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.7.0

## 4.5.0 - 2019-07-02
### Added
- Add aws-resources S3 bucket encryption at rest
- Add Stack Manager DynamoDB encryption at rest
- Add EBS volumes encryption at rest
- Add AEM Hello World Custom Stack Provisioner to integration tests

### Changed
- Upgrade AEM AWS Stack Provisioner to 4.5.0
- Change author_dispatcher, publish_dispatcher, chaos_monkey, and orchestrator default instance type to t2.small

## 4.4.0 - 2019-06-15
### Changed
- Upgrade AEM AWS Stack Provisioner to 4.3.0
- Update stack-provisioner-hieradata.j2 to include state of chaos monkey instance creation [#290]
- Print version numbers when syncing libraries

## 4.3.0 - 2019-05-23
### Added
- Added new ec2 tag ComponentInitStatus to check Component provisioning state
- Add AEM 6.5 integration tests

### Changed
- Upgrade AEM AWS Stack Provision to 4.2.0, AEM Stack Manager Cloud to 1.3.3, AEM Stack Manager Messenger to 2.3.1, AEM Test Suite to 1.2.0

## 4.2.0 - 2019-05-03
### Changed
- Upgrade AEM Test Suite to 0.9.11
- Upgrade AEM AWS Stack Provisioner to 3.17.0

## 4.1.0 - 2019-04-18
### Changed
- Upgrade AEM AWS Stack Provisioner to 3.16.0

## 4.0.0 - 2019-04-07
### Added
- Add CW alarm and notifications for Stack Manager Lambda function errors [#210]
- Add aem-password-reset bugfix to FAQ
- Add offline-snapshot/live-snapshot issue to FAQ
- Added 'aws-create-resources' and 'aws-delete-resources' skeleton to makefile
- Add new parameter to configure ASG for Publish, Author-Dispatcher & Publish-Dispatcher
- Removed setting ACLs on S3 objects with 'public-read' - [#292]

### Changed
- Upgrade AEM AWS Stack Provisioner to 3.15.0
- AEM Health Check package would be provisioned as stack data regardless whether reconfiguration is enabled or not
- Snapshot backup no longer contains just repository, it now contains the whole AEM installation

### Fixed
- Fix AEM Orchestrator data device name configuration to use user config
- Fixed error in boolean hiera parameter

## 3.6.0 - 2019-02-17
### Added
- Add AEM 6.4 SP3 Bugfix to FAQ

### Changed
- Upgrade AEM AWS Stack Provisioner to 3.6.0

### Fixed
- Fix path to staging dir in Ansible playbooks
- Fixed logic error when running pre-common.sh [#257]

## 3.5.0 - 2019-02-04
### Added
- Add new parameter to remove the AEM Global Trusttore during reconfiguration

### Changed
- Upgrade AEM AWS Stack Provisioner to 3.5.0

### Fixed
- Fix intermittent AEM 6.4 start timeout failure due to Package Manager Servlet unreadiness

## 3.4.0 - 2019-01-31
### Added
- Add new feature to enable/disable migration of AEM Global Truststore [#229]
- Add missing SAML configuration documentation
- Add new hiera parameter common::aws_region [#187]
- Add new SSM Documents for automating AEM Upgrade
- Add new configuration parameter enable_upgrade_tools
- Add customisable cipher suite for ELBs [#223]
- Add new feature to configure AEM Apache http proxy configurator settings [#235]
- Add new parameters for all image device names
- Add new heira parameters for image device names
- Add new configuration parameters for post start sleep timer to give the AEM service more time to start before configuring AEM [#214]
- Add Amazon Linux 2 OS type support

### Changed
- Update deployment descriptor documentation for uninstall package feature [#224]
- Upgrade AEM Stack Manager to 1.3.2
- Upgrade AEM AWS Stack Provisioner to 3.4.0

## 3.3.1 - 2018-12-06
### Changed
- Upgrade AEM AWS Stack Provisioner to 3.3.1, AEM Stack Manager Messenger to 1.5.8, AEM Test Suite to 0.9.10

## 3.3.0 - 2018-11-30
### Added
- Add configuration parameters for configuring SAML authentication
- Add configuration parameters for configuring AEM Truststore
- Add configuration parameters for configuring AEM Authorizable Keystores

### Changed
- Update Stack Manager events for Offline-Snapshot & offline-compaction-snapshot to enable scheduling feature [#182]
- Extend schedule snapshot stack manager event to un/schedule live snapshots [#212]
- Upgrade AEM AWS Stack Provisioner to 3.3.0 and AEM Stack Manager Messenger to 1.5.7

## 3.2.1 - 2018-10-22
### Added
- Add Scripts to support the AEM64 Upgrade for consolidated & full-set
- Add new configuration properties aem: aem.enable_bak_files_cleanup, aem.bak_files_cleanup_max_age_in_days
- Add configuration parameters to configure wait until login page is ready during Stack Provisioning [#184]
- Add configuration parameters to enable random termination for each component except Author

### Changed
- Upgrade AEM AWS Stack Provisioner to 3.2.0 and AEM Stack Manager to 1.5.6
- Change default JMX ports to 5982 for AEM Author and 5983 for AEM Publish [#213]
- Update deprecated ansible s3 module references to aws_s3. [#188]
- Change default AEM Publish-Dispatcher max ASG size to 4
- Change security_groups.private_subnet_internet_outbound_cidr_ip configuration to be mandatory
- Change default security_groups.author_dispatcher_elb.extra_groups and security_groups.publish_dispatcher_elb.extra_groups to be empty
- Enforce default Java to use Oracle JDK

### Removed
- Remove deprecated configuration properties: instance_profile_stack_prefix, security_groups_stack_prefix, instance_profiles.stack_name, instance_profiles.stack_manager, security_groups.stack_name, security_groups.*.tag_name, messaging.stack_name, messaging.alarm_notification.topic_name, <component>.stack_name, <component>.tag_name, <component>.instance_profile, <component>.certificate_name, messaging.stack_name, hosted_zone

## 3.1.1 - 2018-09-12
### Added
- Add output redirection in Cloudformation templates for SSM Commands Offline Snapshot, Offline Compaction Snapshot, manage service & wait until ready
- Add new parameters to enable removing of old bak files in AEM repository

### Changed
- Lock awscli version to 1.16.10, boto3 to 1.8.5, ansible to 2.8.5

## 3.1.0 - 2018-08-19
### Added
- Add new configuration parameters to enabling support for reconfigure existing AEM installation
- Add new SSM Document aem-reconfiguration
- Add System Users parameters in configuration
- Add export import package to integration test

### Changed
- Update description for SSM Document install-aem-profile
- Change package installation and compaction related timeouts to 2 hours, service status check to 10 minutes
- Upgrade AEM AWS Stack Provisioner to 3.1.2
- Update default publish dispatcher log rotation config to rotate every hour

## 3.0.0 - 2018-07-17
### Added
- Add support for using snapshots containing repository with non AEM OpenCloud ownership

### Changed
- Upgrade AEM AWS Stack Provisioner to 3.x and AEM Orchestrator to 2.x for AEM 6.4 support
- Upgrade AEM Password Reset to 1.1.0 for AEM 6.4 support

### Removed
- Remove attachment of Bastion Host security group from all ELBs

## 2.3.2 - 2018-07-23
### Added
- Add support for using snapshots containing repository with non AEM OpenCloud ownership
- Add support for any number of availability zones during VPC and network provisioning [#159]
- Add metadata file creation for each artifact uploaded using Makefile library target [#114]
- Add library.aem_healthcheck_version configuration property
- Add new SSM Document install-aem-profile
- Add AEM Stack Manager Cloud to local integration test

### Changed
- Upgrade AEM AWS Stack Provisioner to 3.1.1

### Removed
- Move Custom Stack Provisioner pre step to be after facts provisioning

## 2.3.0 - 2018-07-03
### Added
- Add integration testing support using configured libraries

### Changed
- Upgrade AEM AWS Stack Provisioner to 2.6.0
- Change s3 bucket presence check to inspect the content of the bucket

## 2.2.1 - 2018-08-03
### Added
- Add configuration chaos_monkey.include_stack to include/exclude Chaos Monkey nested stack
- Add AEM version and OS type support to local integration testing
- Add configurable chaos monkey settings

### Changed
- Change snapshots.author.use_data_vol_snapshot and snapshots.publish.use_data_vol_snapshot configuration properties to accept boolean

## 2.2.0 - 2018-06-04
### Added
- Add feature to configure Logrotation per component or/and per stack
- Add cron.no_proxy configuration support

### Changed
- Stack Manager main stack name is now configurable via scheduled_jobs.aem_orchestrator.stack_manager_pair.stack_name config
- Increase default deployment delay to 60, check retries to 120, and check delay to 15
- Improve network-exports to support subnets list instead of predefined subnet A and subnet B [#79]
- Offline compaction scheduled job on Author Primary and Publish is disabled by default
- Revert snapshot is disabled by default

### Removed
- Move Stack Manager SSM stack to become a nested/child stack of Stack Manager main stack [#149]
- Remove unused aem.deployment_post_install_wait_in_seconds configuration property

## 2.1.1 - 2018-05-19
### Added
- Add revert_snapshot_type parameter to allow default launch configuration to set snapshots to offline or live types
- Add /opt/shinesolutions/aem-aws-stack-builder/stack-init-completed as an indicator that userdata has been completed successfully
- Add stack-init completion check to all Stack Manager SSM commands

### Changed
- Restructure configuration for Stack Manager snapshots purge schedule and max age
- Set snapshots purge max age unit to hour, set schedule to cron expression without function syntax
- Simplify offline snapshot events Stack Manager pairing to use stack prefix instead of SNS topic ARN
- Replace SSM template generation shell script with ssm_template Ansible module

### Removed
- Remove global fact stack_manager_sns_topic_arn

## 2.1.0 - 2018-05-11
### Added
- Add aem.enable_content_healthcheck_terminate_instance switch for instance termination for content healthcheck alarms
- Add java_opts parameter allowing custom java_opts to be specified
- Add AuthorPublishDispatcher component
- Add configuration flag for enabling CRXDE [#35]
- Add configuration flag for enabling default system users password [#36]
- Add configuration flag for enabling package and artifacts deployment on instance initialisation
- Add JVM memory opts for AEM Author and Publish [#49]
- Added Repo aem-stack-manager-cloud to aem-aws-stack-builder repo [#63]
- Added feature for Publish Dispatcher to scale up/down if CPU is above/under configured threshold [#26]
- Introduce AuthorPublishDispatcherSubnetList and AuthorDispatcherELBSubnetList to network-exports [#64]
- Introduce Consolidated architecture stacks
- Add alarm for queue size of ASG events in Full Set architecture [#70]
- Add variable declaration to configure jmxremote port for Author and Publish
- Add aem.version configuration
- Add CW Alarm to monitor auto scaling messaging queue
- Add Collectd proxy configuration support
- Add library build target for downloading open source artifacts [#101]
- Add new command mapping for AEM Stack Manager
- Introduce permission types to support various resource restrictions
- Add Simian Army artifact to library [#75]
- Add support for adding extra security groups to ELBs [#107]
- Add aem.enable_reverse_replication configuration [#117]
- Add AEM package deployment wait and retry configurations [#122]
- Add aem.enable_content_healthcheck configuration [#116]
- Add ec2 delete volume permission to Publish role

### Changed
- Hieradata config file is now generated based on Ansible group vars
- Replace Serverspec with InSpec for testing [#50]
- Modify Full-Set architecture stacks pairing to work with network, security_groups, and instance_profile stacks
- Modify AEM Author instance's https listen port from 5433 to 5432
- Enable AutoScalingGroups metrics collection [#56]
- Modify cloud-init's extra local.yaml config to be appended to base local.yaml
- Set Ansible config hash behaviour to merge [#108]

### Removed
- Remove external package installation during cloud init [#43]
- Remove unnecessary sleep during cloud init [#51]
- Move aem_password_reset_version, aem_orchestrator_version, oak_run_version stack facts to stack-provisioner-hieradata config [#11]

## 1.1.1 - 2017-06-07
### Added
- Add Stack Provisioner custom hiera configuration support
- Introduce parent CloudFormation stacks to Full Set architecture
- Add Puppet exit code translation in stack-init script
- Add shortcode support to CloudFormation template global tagging

### Changed
- Update aem-aws-stack-provisioner version to 1.1.1
- Replace configuration file with stack output values for environment parameters
- Disable generated system user credentials logging [#34]

## 1.1.0 - 2017-06-02
### Changed
- Load Balancers and Auto Scaling Groups can now be created for a variety of network setups. i.e. 1-n Availability Zones, 1-n Subnets
- Change the Publish Auto Scaling Group to use EC2 Health Check Type
- Change the Publish Dispatcher Auto Scaling Group Health Check Grace Period from 15 minutes to 20 minutes
- Enhance the s3_copy_object script to not copy files that do not exist
- Copy content-healthcheck-descriptor from source bucket
- Update aem-orchestrator version to 1.0.0
- Update aem-aws-stack-provisioner version to 1.1.0

## 1.0.0 - 2017-05-23
### Added
- Initial version
