Experitest - Regional Proxy ansible role
=========

This role will install \ uninstall regional proxy for windows, linux and mac os hosts <br>
For linux, the nginx conf and error logs folders are "nginx_conf: /etc/nginx" and  "nginx_logs: /var/log/nginx"

Requirements
------------

Supports windows, linux and mac os hosts only.

Role Variables
--------------

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| state | should the application be present or absent | present, absent | present | no |
| app_version | application version to install | string | 12.8.7025 | no |
| server_port | port number for the server | number | 8085 | no |
| extra_application_properties | additional props to be override in application.properties file | dict | {} | no |
| extra_java_options | extand java options | array of strings | [] | no |
| installation_folder | the folder in which the applction will be installed | string | for mac: /Applications/Experitest/regional-proxy-version <br> for windows: C:\\Experitest\\regional-proxy-version <br> for linux: /opt/Experitest/regional-proxy-version | no |
| jmx_port | port number for jmx inspection | number | 51239 | no |
| java_version | java jre version to install | string | 1.8.0_181 | no |
| custom_download_url | custom url to download the installation from (zip format) | string |  | no |
| start_after_install | should application start after installation is completed | boolean | True | no |
| clear_temp_folder | remove temp folder after installation | boolean | False | no |
| clear_before_install | removing old installation before installing new version | boolean | False | no |

Example Playbook
----------------

#### [see working example](/example)
