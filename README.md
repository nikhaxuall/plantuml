# plantuml
Some plantuml sandboxing

## Getting Started
For my setup I'm running docker and docker-compose on a remote dev VM and using vscode with the remote-ssh extension.

### Start the plantuml-server
There are multiple ways to render your plantuml diagrams listed [here](https://plantuml.com/running).  The main of which are:

1. Run them on the publicly hosted plantuml instance [here](https://www.plantuml.com/plantuml/uml/SyfFKj2rKt3CoKnELR1Io4ZDoSa70000)
1. Install java, plantuml, and graphviz locally.
1. Run it in a docker container

I've chosed to run it in a docker container using docker compose, but doing it with a normal `docker run...` command works too.  More details can be found [here](https://hub.docker.com/r/plantuml/plantuml-server), but for a shortcut run

```
docker run -d -p 8080:8080 plantuml/plantuml-server:jetty
```

After that's running you can install the plantuml extension on your remote box using vscode.  By default, the extension looks for a locally  installed instance of plantuml. If you want to use the docker-hosted instance, you'll need to modify two settings.

```json
"plantuml.render": "PlantUMLServer"
"plantuml.server": "http://localhost:8080"
```

### Previewing your diagrams

After you've got the container running and the extension set up.  Start editing a `.puml` file, bring up the command palette and search for `PlantUML: Preview Current Diagram`.  It will open a window to the side of your document that shows a rendered version.