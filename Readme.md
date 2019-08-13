# Modernize ASP COM+ IIS Application to Windows Server 2019 Container

To run this hands-on lab you need to follow those steps

1 - Deploy a Windows Server 2019 VM with Windows Containers images pre-installed

2 - Clone the repository

3 - Build the docker image

4 - Test the docker image locally

## Deploy Windows Server 2019 VM


## Build the docker image
Confirm the base image is pre-installed and up-to-date
```Docker
docker pull mcr.microsoft.com/windows/servercore:ltsc2019
```



```Docker
docker build -t iis .
```

## Test the application

```Docker
docker run -it --rm -p 8080:80 iis
```

### Server Monitor
ServiceMonitor is a Windows executable designed to be used as the entrypoint process when running IIS inside a Windows Server container.

ServiceMonitor monitors the status of the w3svc service and will exit when the service state changes from SERVICE_RUNNING to either one of SERVICE_STOPPED, SERVICE_STOP_PENDING, SERVICE_PAUSED or SERVICE_PAUSE_PENDING.

More details on https://github.com/microsoft/IIS.ServiceMonitor
