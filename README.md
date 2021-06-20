Experitest - Regional Proxy ansible role
=========

This role will install \ uninstall regional proxy for windows, linux and mac os hosts <br>
For linux, the nginx conf and error logs folders are "nginx_conf: /etc/nginx" and  "nginx_logs: /var/log/nginx"

Requirements
------------

* [ansible-role-java8](https://github.com/ExperitestOfficial/ansible-role-java8) must be installed on all machines. <br>
* Supports windows, linux and mac os hosts only.
* For multi-region proxy support, keep private and public certifates with the following names in ansible project under your inventories and provide relative path in certificate_folder parameter (e.g. certificate_folder: inventories/cloud1/files).
  * server_private_key.key
  * server_public_key.crt

Role Variables
--------------

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| state | should the application be present or absent | present, absent | present | no |
| app_version | application version to install | string | 12.12.7794 | no |
| nginx_version | nginx version to install for linux | string | 1.19.8 | no |
| server_port | port number for the server | number | 8085 | no |
| extra_application_properties | additional props to be override in application.properties file | dict | {} | no |
| extra_logback_properties | additional props to be override in logback.properties file | dict | {} | no |
| extra_java_options | extand java options | array of strings | [] | no |
| installation_root_folder | the root folder in which the application will be installed under regional-proxy-{version} folder | string | for mac: /Applications/Experitest <br> for windows: C:\\Experitest <br> for linux: /opt/Experitest | no |
| jmx_port | port number for jmx inspection | number | 51239 | no |
| java_version | java jre version to install | string | 8u292-b10 | no |
| custom_download_url | custom url to download the installation from (zip format) | string |  | no |
| custom_download_username | username to download from custom url on windows | string |  | no |
| custom_download_password | password to download from custom url on windows | string |  | no |
| start_after_install | should application start after installation is completed | boolean | True | no |
| clear_temp_folder | remove temp folder after installation | boolean | False | no |
| clear_before_install | removing old installation before installing new version | boolean | False | no |
| kill_notepad | kill notepad/notepadd++ apps on windows | boolean | False | no |
| nginx_certificate_install | should copy the nginx server certificates to regional proxy machines | boolean | False | no |
| certificate_folder | should be relative path of certificate folder where the server_private_key.key and server_public_key.crt files kept (e.g. inventories/cloud1/files), it will be useful when nginx_certificate_install is True | string | ./files | when nginx_certificate_install is set to True |

Example Playbook
----------------

#### [see working example](/example)
