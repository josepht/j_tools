# Juju Tools

## Description

Some tools to make using juju a bit easier.

## Notes

1. **PREFIX**

   For the uci-engine project all service and unit names are prefixed with 'ci-airline-' to avoid having to type this constantly j_tools uses the environment varialble PREFIX to include a common prefix for service and unit names.

2. **Service or unit**

   Most j_tools commands accept a service name or unit name.  If a unit name is required for the underlying juju command, eg. `juju retry ci-airline-ts-django/0` the default unit number is '0' so you can just use the service name like this `j_retry ts-django`.

## Examples

Most commands require a bootstrapped juju environment.

* To deploy a project.  Currently this is hardcoded to the uci-engine project.

  `j_deploy`

* To check the status of a deployment.

  `j_status` or `j_status ts-django` or `j_status ts-django/1`

* To check the overall deployment to see if something has failed.

  `j_check`

* To ssh to a unit

  `j_ssh ts-django`

* To enter a debug hooks tmux session

  `j_debug_hooks ts-django install`

* To grab a unit's juju log file

  `j_log ts-django`

* To destroy the environment and re-bootstrap.

  `j_destroy`

  or to prevent the bootstrap phase

  `j_destroy -o`

* There are other less commonly used commands like `j_watch_ticket` and `j_add_ticket`.
