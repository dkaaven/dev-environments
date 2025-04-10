# Use the official PowerShell image
FROM mcr.microsoft.com/powershell:latest

# Set the working directory
WORKDIR /root/workspace

# Install additional PowerShell modules (customize as needed)
RUN pwsh -Command `
    Install-Module -Name Pester -Scope CurrentUser -Force -SkipPublisherCheck; `
    Install-Module -Name PSReadLine -Scope CurrentUser -Force -SkipPublisherCheck

# Set container to always start with PowerShell
CMD ["pwsh"]
