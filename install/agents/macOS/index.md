[title]: # (Installing macOS Agents)
[tags]: # (agent,install,upgrade,macOS)
[priority]: # (1)

# Installing macOS Agents

The following installation/upgrade topic for the macOS agent is covered:

* [macOS Privilege Manager Agent](agent-inst-mac.md)

## Agent Components

The agent is made up of several components:

| Component | Runtime |
| ----- | ----- |
| Privilege Manager.app | Universal Binary |
| System Extension | Universal Binary |
| Finder Sync Extension | Universal Binary |
| Preference Pane | Universal Binary |
| sudo plugin | Universal Binary |
| Service Agent | .NET (Rosetta 2 on Apple Silicon) |

## MacOS Agent System Requirements

* macOS 10.11 (El Capitan) or newer

### Apple® Silicon

For macOS endpoints with __Apple® Silicon__, the agent needs to be version __11.0.104__ or later.
