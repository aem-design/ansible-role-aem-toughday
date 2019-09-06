# Ansible Role: AEM Toughday

[![Build Status](https://travis-ci.org/aem-design/ansible-role-aem-toughday.svg?branch=master)](https://travis-ci.org/aem-design/ansible-role-aem-toughday)

This role tests AEM Dispatcher instance for specific Security patterns.
> This role was developed as part of
> [AEM.Design](http://aem.design/)

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Variable              	| Default                                                                                                                                              	| Notes                       	|
|-----------------------	|------------------------------------------------------------------------------------------------------------------------------------------------------	|-----------------------------	|
| docker_image_user     	| aemdesign                                                                                                                                            	| hub.docker role owner       	|
| docker_image_name     	| "toughday"                                                                                                                                           	| hub.docker image name       	|
| docker_image          	| "{{ docker_image_user }}/{{ docker_image_name }}"                                                                                                    	| image to use                	|
| docker_image_tag      	| "latest"                                                                                                                                             	| image tag                   	|
| docker_container_name 	| "toughday"                                                                                                                                           	| new container name          	|
| java_opts             	| "-Xmx1024m"                                                                                                                                          	|                             	|
| tool_name             	| "toughday-6.1.jar"                                                                                                                                   	|                             	|
| docker_command        	| "java {{ java_opts }} -Dhostname={{ service_author_host }} -Dport={{ service_author_port }} -DuploadImage.count=10 -jar {{ tool_name }} uploadImage" 	| params to pass to test tool 	|

## Included Tools

Help on the Tough Day 2 can be found here [https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/tough-day.html](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/tough-day.html) 

Information on tools that can be used part of the docker image can be found here [https://hub.docker.com/r/aemdesign/toughday](https://hub.docker.com/r/aemdesign/toughday)

## Dependencies

This role depends on role `aem_design.aem_toughday`.

## Example Playbook

```yaml
- hosts: all
  roles:
    - aem_design.aem_toughday
```

## License

Apache 2.0

## Author Information

This role was created by [Max Barrass](https://aem.design/).