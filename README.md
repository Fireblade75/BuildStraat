# Jenkins Build Straat

## Troubleshooting

Bij de volgende fout moet op de host het aantal virtual memory areas opgehoogd worden:
```
sonarqube [1]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]
```
Hiervoor moet met sysctl de memory area's opgehoogd worden. Dit kan alleen rechtstreeks vanuit de host vm.

Onder Windows 8 kan de Docker VM benaderd worden met het volgende command.
``` 
docker-machine ssh
```

Op WSL2 kan dit gedaan worden met de volgende command.
``` 
wsl -d docker-desktop
```
Vervolgens moet de volgende regel uitgevoerd worden.

```
sysctl -w vm.max_map_count=262144
```