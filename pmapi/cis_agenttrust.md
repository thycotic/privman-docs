# AgentTrustService

## Path

/api/agenttrust

## Description

This service contains methods relating to managing agent trust by generating install codes and revoking them or specific agents

## Methods

* GetValidInstallCodes – This method returns all valid install codes for an installation
* NewInstallCode – This method instructs the system to generate a new install code
* RevokeInstallCode – This method instructs the system to revoke trust for the install code passed in the parameters
* RevokeAgentCertificate – This method instructs the system to revoke trust from the agentID passed in the parameters
* IsAgentRegistered – This method returns a Boolean value indicating if the AgentID in the parameters is valid.