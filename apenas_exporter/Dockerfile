# Use a base image of Windows Server Core
FROM mcr.microsoft.com/windows/servercore:ltsc2019

# Set the working directory
WORKDIR /exporter

# Download the Windows Exporter
ADD https://github.com/prometheus-community/windows_exporter/releases/download/v0.20.0/windows_exporter-0.20.0-amd64.msi windows_exporter.msi

# Install the Windows Exporter
RUN msiexec.exe /i windows_exporter.msi /quiet /norestart

# Expose the port that the exporter will use
EXPOSE 9190

# Run the Windows Exporter
ENTRYPOINT ["C:\\Program Files\\windows_exporter\\windows_exporter.exe", "--collectors.enabled", "cpu,cs,logical_disk,net,os,service,system"]
