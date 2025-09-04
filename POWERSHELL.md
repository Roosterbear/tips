<h1 style="color:#2a9d8f">POWERSHELL</h1>

- [USUARIOS](#usuarios)
  - [Búsqueda de Usuarios](#búsqueda-de-usuarios)
  - [Saber la FECHA de Creación de un Usuario](#saber-la-fecha-de-creación-de-un-usuario)
- [GRUPOS](#grupos)
  - [Mostrar Miembros de un Grupo](#mostrar-miembros-de-un-grupo)
- [EQUIPOS](#equipos)
  - [Mostrar un Equipo con todas sus propiedades](#mostrar-un-equipo-con-todas-sus-propiedades)
  - [Mostrar Equipos que no se han Logueado en días](#mostrar-equipos-que-no-se-han-logueado-en-días)
  - [Reiniciar Equipo](#reiniciar-equipo)
  - [Checar SERVICIO](#checar-servicio)
  - [Ejecutar REMOTAMENTE un comando](#ejecutar-remotamente-un-comando)
- [DISCOS](#discos)
  - [Eliminar Particiones de Disco Duro](#eliminar-particiones-de-disco-duro)


# USUARIOS

## Búsqueda de Usuarios
```powershell
Get-ADUser -Filter "SamAccountName" -like "j*"
```

## Saber la FECHA de Creación de un Usuario
```powershell
Get-ADUser jgomez -Properties whencreated
```


# GRUPOS

## Mostrar Miembros de un Grupo
```powershell
Get-ADGroupMember -Identify Administrators | Format-Table Name, SamAccountName
```


# EQUIPOS

## Mostrar un Equipo con todas sus propiedades
```powershell
Get-ADComputer -Identity BQ4 -Properties *
```

## Mostrar Equipos que no se han Logueado en días
```powershell
$DaysInactive = 4
$time = (Get-Date).Adddays(-($DaysInactive))
get-ADComputer -Filter {LastLogonTimeStamp -lt $time} -ResultPageSize 2000 `
resultSetSize $null -Properties Name, OperatingSystem, SamAccountName
```

## Reiniciar Equipo
```powershell
Restart-Computer -ComputerName "172.16.33.10" -Force
```

## Checar SERVICIO

> sc = Service Control. Es **nativo** de Windows

```powershell
sc query eraagent
```

## Ejecutar REMOTAMENTE un comando
```powershell
sc \\NOMBRE_EQUIPO query eraagent
```

```powershell
sc \\172.16.1.69 query eraagent
```

```powershell
Get-Service -Name eraagent -ComputerName NOMBRE_EQUIPO
```

> Get-Service equivale a sc query <br/>
> Start-Service equivale a sc start <br/>
> Stop-Service equivale a sc stop <br/>
> Set-Service equivale a sc config <br/>



# DISCOS

## Eliminar Particiones de Disco Duro
```powershell
# Ver discos
Get-Disk
# Ver particiones
Get-Partition -DiskNumber 1
# Eliminar dando el numero de disco y de partición
Remove-Partition -DiskNumber 1 -PartitionNumber 2
# --- si no quiere, entrar en modo a prueba de fallos ---
```


