# Docker Katas
Some [katas](https://en.wikipedia.org/wiki/Kata) for using [docker](https://www.docker.com/).

The intent here is to create a training aid for new and forgetful Docker users. We've mostly just pulled these together from around the internet, out of books, or made them up. If you see something missing and you'd like to contribute, please feel free to create a [Pull Request](https://help.github.com/articles/creating-a-pull-request/) on this repo.

## Setup

The expectation is that you will use the Docker In Docker (aka *meta-docker*) approach to execute these katas. Look for notes in the kata for how to run without the *meta-docker* settings.

0. [Docker In Docker](00_docker_in_docker.md)

## Recommended Order For Learning

1. [Pull and Run an Image](01_pull_and_run_image.md)
2. [List Images](02_list_images.md)
3. [List Containers](03_list_containers.md)
4. [Delete Container](04_delete_container.md)
5. [Delete Image](05_delete_image.md)
6. [Named Containers](06_named_containers.md)
7. [Start Containers](07_start_containers.md)
8. [Tag an Image](08_tag_an_image.md)
9. [Delete and Image by Tag](09_delete_image_by_tag.md)
10. [Execute Command In Container](10_exec_in_container.md)
11. [Change The State of The Container](11_change_container_state.md)
12. [Commit Changes](12_commit_changes.md)
13. [Interacting With Containers](13_interacting.md)
14. [Pushing Images](14_pushing_images.md)
15. [Create An Image for a Python Application](15_simple_python_image.md)
16. [Create An Image for a Ruby Application](16_simple_ruby_image.md)
17. [Setting Environment Variables](17_setting_envvars.md)
18. [Overriding Environment Variables](18_overriding_envvars.md)
19. [Publish Network Interfaces](19_publish_network_interfaces.md)
20. [Mounting Volumes](20_mounting_volumes.md)
21. [Defining Your Network Interface](21_define_network_interface.md)
22. [Defining Your Volume](22_define_volume.md)
23. [Bypass `ENTRYPOINT`](23_bypass_entrypoint.md)
24. [Remove Exited Containers](24_remove_exited_containers.md)
25. [Remove Dangling Images](25_remove_dangling_images.md)
26. [Remove all Images](26_remove_all_images.md)
27. [List Docker Volumes](27_list_volumes.md)
28. [Remove Docker Volume](28_remove_volume.md)
29. [Fetch Logs From a Container](29_fetch_logs.md)
30. [Rename a Container](30_rename_container.md)
31. [Restart a Container](31_restart_container.md)
32. [Attach to a Running Container](32_attach_container.md)
33. [Create, but don't start, a Container](33_create_container.md)
34. [List the History of an Image](34_image_history.md)
35. [Get Info on Docker](35_system_info.md)
36. [Kill a Running Container](36_kill_container.md)
37. [Login to Docker](37_login.md)
38. [Logout of Docker](38_logout.md)
39. [Change between Remotes](39_change_repos.md)
40. [Get Stats on Running Containers](40_stats.md)
41. [List Network Interface Ports](41_network_ports.md)
42. [Pause a Container](42_pause_container.md)
43. [Unpause a Container](43_unpause_container.md)
44. [Update a Container Configuration](44_update_container_config.md)
45. [Wait for a Container to Stop](45_wait_for_container.md)

<!-- Upcomming content

[Pushing Images]
https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes

Other:
Run your own registry
Run your own registry INSIDE docker (which only makes sense)

-->

## By Command

**build**

[Bypass Entrypoint](23_bypass_entrypoint.md)

[Define Network Interface](21_define_network_interface.md)

[Define Volume](22_define_volume.md)

[Overriding Envvars](18_overriding_envvars.md)

[Setting Envvars](17_setting_envvars.md)

[Simple Python Image](15_simple_python_image.md)

[Simple Ruby Image](16_simple_ruby_image.md)

**commit**

[Commit Changes](12_commit_changes.md)

**create**

[Create Container](33_create_container.md)

[Named Containers](06_named_containers.md)

**exec**

[Attach Container](32_attach_container.md)

[Change Container State](11_change_container_state.md)

[Commit Changes](12_commit_changes.md)

[Exec In Container](10_exec_in_container.md)

[Interacting](13_interacting.md)

**history**

[Image History](34_image_history.md)

**images**

[Commit Changes](12_commit_changes.md)

[Define Network Interface](21_define_network_interface.md)

[Define Volume](22_define_volume.md)

[Delete Image](05_delete_image.md)

[Delete Image By Tag](09_delete_image_by_tag.md)

[List Images](02_list_images.md)

[Overriding Envvars](18_overriding_envvars.md)

[Pushing Images](14_pushing_images.md)

[Remove All Images](26_remove_all_images.md)

[Remove Dangling Images](25_remove_dangling_images.md)

[Setting Envvars](17_setting_envvars.md)

[Simple Python Image](15_simple_python_image.md)

[Simple Ruby Image](16_simple_ruby_image.md)

[Tag An Image](08_tag_an_image.md)

**info**

[System Info](35_system_info.md)

**kill**

[Kill Container](36_kill_container.md)

**login**

[Change Repos](39_change_repos.md)

[Login](37_login.md)

[Pushing Images](14_pushing_images.md)

**logout**

[Change Repos](39_change_repos.md)

[Logout](38_logout.md)

**logs**

[Fetch Logs](29_fetch_logs.md)

**pause**

[Pause Container](42_pause_container.md)

[Unpause Container](43_unpause_container.md)

**port**

[Network Ports](41_network_ports.md)

**ps**

[Create Container](33_create_container.md)

[Delete Container](04_delete_container.md)

[Fetch Logs](29_fetch_logs.md)

[Kill Container](36_kill_container.md)

[List Containers](03_list_containers.md)

[Named Containers](06_named_containers.md)

[Remove Exited Containers](24_remove_exited_containers.md)

[Rename Container](30_rename_container.md)

[Restart Container](31_restart_container.md)

**pull**

[Named Containers](06_named_containers.md)

[Pull And Run Image](01_pull_and_run_image.md)

[Tag An Image](08_tag_an_image.md)

**push**

[Pushing Images](14_pushing_images.md)

**rename**

[Rename Container](30_rename_container.md)

**restart**

[Restart Container](31_restart_container.md)

**rm**

[Attach Container](32_attach_container.md)

[Commit Changes](12_commit_changes.md)

[Create Container](33_create_container.md)

[Delete Container](04_delete_container.md)

[Fetch Logs](29_fetch_logs.md)

[Kill Container](36_kill_container.md)

[Network Ports](41_network_ports.md)

[Pause Container](42_pause_container.md)

[Remove Exited Containers](24_remove_exited_containers.md)

[Remove Volume](28_remove_volume.md)

[Rename Container](30_rename_container.md)

[Restart Container](31_restart_container.md)

[Stats](40_stats.md)

[Unpause Container](43_unpause_container.md)

[Update Container Config](44_update_container_config.md)

[Wait For Container](45_wait_for_container.md)

**rmi**

[Bypass Entrypoint](23_bypass_entrypoint.md)

[Commit Changes](12_commit_changes.md)

[Define Network Interface](21_define_network_interface.md)

[Define Volume](22_define_volume.md)

[Delete Image](05_delete_image.md)

[Delete Image By Tag](09_delete_image_by_tag.md)

[Overriding Envvars](18_overriding_envvars.md)

[Remove All Images](26_remove_all_images.md)

[Remove Dangling Images](25_remove_dangling_images.md)

[Setting Envvars](17_setting_envvars.md)

[Simple Python Image](15_simple_python_image.md)

[Simple Ruby Image](16_simple_ruby_image.md)

**run**

[Attach Container](32_attach_container.md)

[Bypass Entrypoint](23_bypass_entrypoint.md)

[Commit Changes](12_commit_changes.md)

[Define Network Interface](21_define_network_interface.md)

[Define Volume](22_define_volume.md)

[Fetch Logs](29_fetch_logs.md)

[Kill Container](36_kill_container.md)

[List Containers](03_list_containers.md)

[List Volumes](27_list_volumes.md)

[Mounting Volumes](20_mounting_volumes.md)

[Network Ports](41_network_ports.md)

[Overriding Envvars](18_overriding_envvars.md)

[Pause Container](42_pause_container.md)

[Publish Network Interfaces](19_publish_network_interfaces.md)

[Pull And Run Image](01_pull_and_run_image.md)

[Remove Volume](28_remove_volume.md)

[Rename Container](30_rename_container.md)

[Restart Container](31_restart_container.md)

[Setting Envvars](17_setting_envvars.md)

[Simple Python Image](15_simple_python_image.md)

[Simple Ruby Image](16_simple_ruby_image.md)

[Stats](40_stats.md)

[Unpause Container](43_unpause_container.md)

[Update Container Config](44_update_container_config.md)

[Wait For Container](45_wait_for_container.md)

**start**

[Change Container State](11_change_container_state.md)

[Commit Changes](12_commit_changes.md)

[Start Containers](07_start_containers.md)

**stats**

[Stats](40_stats.md)

**stop**

[Attach Container](32_attach_container.md)

[Change Container State](11_change_container_state.md)

[Commit Changes](12_commit_changes.md)

[Fetch Logs](29_fetch_logs.md)

[Kill Container](36_kill_container.md)

[List Containers](03_list_containers.md)

[List Volumes](27_list_volumes.md)

[Network Ports](41_network_ports.md)

[Pause Container](42_pause_container.md)

[Rename Container](30_rename_container.md)

[Restart Container](31_restart_container.md)

[Start Containers](07_start_containers.md)

[Stats](40_stats.md)

[Unpause Container](43_unpause_container.md)

[Update Container Config](44_update_container_config.md)

[Wait For Container](45_wait_for_container.md)

**tag**

[Pushing Images](14_pushing_images.md)

[Tag An Image](08_tag_an_image.md)

**unpause**

[Pause Container](42_pause_container.md)

[Unpause Container](43_unpause_container.md)

**update**

[Update Container Config](44_update_container_config.md)

**volume**

[List Volumes](27_list_volumes.md)

[Remove Volume](28_remove_volume.md)

**wait**

[Wait For Container](45_wait_for_container.md)

