<h1 style="color:#2a9d8f">POWERSHELL</h1>

- [Búsqueda de Usuarios](#búsqueda-de-usuarios)
- [Saber la FECHA de Creación de un Usuario](#saber-la-fecha-de-creación-de-un-usuario)
- [Mostrar Miembros de un Grupo](#mostrar-miembros-de-un-grupo)
- [Mostrar un Equipo con todas sus propiedades](#mostrar-un-equipo-con-todas-sus-propiedades)
- [Mostrar Equipos que no se han Logueado en días](#mostrar-equipos-que-no-se-han-logueado-en-días)
- [Reiniciar Equipo](#reiniciar-equipo)
- [Eliminar Particiones de Disco Duro](#eliminar-particiones-de-disco-duro)


## Búsqueda de Usuarios
```powershell
Get-ADUser -Filter "SamAccountName" -like "j*"
```

## Saber la FECHA de Creación de un Usuario
```powershell
Get-ADUser jgomez -Properties whencreated
```

## Mostrar Miembros de un Grupo
```powershell
Get-ADGroupMember -Identify Administrators | Format-Table Name, SamAccountName
```

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


