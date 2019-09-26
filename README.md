# docker-windows-alertmanager

[![Build Status](https://dev.azure.com/Justin-DynamicD/GitHubPipelines/_apis/build/status/Justin-DynamicD.docker-windows-alertmanager?branchName=master)](https://dev.azure.com/Justin-DynamicD/GitHubPipelines/_build/latest?definitionId=5&branchName=master)

Dockerfile for creating alertmanager in Windows container.

## GitHub public:
https://github.com/Justin-DynamicD/docker-windows-alertmanager

Note the version is set to match the version of alertmanager.  Therefore v0.19.0 equals v.0.19.0 of alertmanager.

## Running alertmanager

Access occurs on port 9093. In addition, all persistent files are stored on `c:\alertmanager` on the container. Therefore, the simplest way to launch the container is to port map and volume map the configuration file as below:

```powershell
docker run -d -p 9090:9090 -v C:/config/alertmanager.yml:C:/alertmanager/alertmanager.yml --name dynamicd/winalertmanager:v0.19.0
```

This allows you to use a local config file to run alertmanager.
