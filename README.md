## GoCD Agent
Bastille Template: gocd-agent

This is a 'template' for a BastilleBSD container.
Similar to Docker containers it allows running lightweight 'VMs' on FreeBSD.

Fetch and apply this template with:

```shell
bastille bootstrap https://github.com/dijitaltrix/gocd-agent
bastille template TARGET /usr/local/bastille/templates/gocd-agent
```

## Description
A 'GoCD Agent' runs tasks assigned to it by a 'GoCD Server'.

By default this template will create 2 sandboxed agents under '/usr/local/gocd' named 'agent-1' and 'agent-2'.

This each agent will accept tasks from a 'GoCD Server' instance, you can download a template from here: 
https://github.com/dijitaltrix/gocd-server

Note: You must update line 5 in 'gocd/agent-XX/wrapper-config/' (where XX is the agent number) replacing
```shell
wrapper.app.parameter.101=http://localhost:8153/go
```
with the location of your GoCD server
