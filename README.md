<h1>Localhost Setup Guide</h1>

The setup package provisions a complete localhost development environment for the Christ Church Geelong platform, including required software dependencies, environment validation, and application bootstrap operations.

<h2> Step 1 — Download the Setup Package</h2>

Download the latest `setup.zip` package from the GitHub release repository.


<h2>Step 2 — Verify Package Authenticity</h2>

Before extracting the package, verify its SHA256 checksum to ensure the download has not been corrupted or modified.

Open PowerShell in the directory containing the downloaded file and execute:
powershell
Get-FileHash .\setup.zip -Algorithm SHA256
<br />
The resulting hash should match the value below:
1AC1D24E9745CAB18DCDA1D30B8C72A608902ABD57D7CC4E63E8751F96F3174F

<br />
If the calculated hash matches the published value, the package integrity has been successfully verified.

<h2> Step 3 — Extract the Package </h2>

Extract the contents of the ZIP archive to a local working directory.

Recommended location:
C:\Apps

<h2>Step 4 — Start an Elevated PowerShell Session</h2>

Launch PowerShell using **Run as Administrator**.

Several installation and configuration operations require administrative privileges.

<h2>Step 5 — Navigate to the Setup Directory </h2>

Change to the setup directory created during extraction.

Example:
powershell
cd C:\Apps\ChristChurchGeelong-Setup\setup



<h2>Step 6 — Provision the Development Environment </h2>

Execute each script sequentially.

The scripts install required dependencies, validate the host environment, preserve any existing local state, and bootstrap the application.

.\00-install-dotnet.ps1 <br />
.\01-install-git.ps1 <br />
.\02-install-python.ps1 <br />
.\03-install-sql.ps1 <br />
.\04-install-cloudflared.ps1 <br />
.\05-environment-check.ps1 <br />
.\06-backup-local-state.ps1 <br />

<h2> Repository Access </h2>

The bootstrap process retrieves source code from the private `Anglican_Church_Australia` repository.

Access must be granted before running:

powershell
.\08-bootstrap-localhost.ps1

Users without an approved institutional GitHub invitation will be unable to complete repository clone operations.

 <h2> Installation Complete </h2>

Upon successful completion of all scripts, the localhost development environment will be fully provisioned and ready for application development, testing, and maintenance activities.

<h2>Documentation </h2>

Project documentation is provided as part of the repository handover package.

After cloning the repository, documentation can be found within the following directory:

Handover/

The handover folder contains project documentation covering:

Architecture and Design

Deployment and Environment Configuration

Governance and RootAuthority

Identity and Authentication

Operational Procedures

Development Standards

Project Milestones

Support and Maintenance

New contributors are encouraged to review the documentation before making changes to the platform.

Installation Complete

Upon successful completion of all scripts, the localhost development environment will be fully provisioned and ready for application development, testing, and maintenance activities.
