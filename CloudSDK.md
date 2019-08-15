# Cloud SDK

## Obtener nombre de la configuración activa (y guardarla)
```bash
echo $(gcloud config configurations list --filter="IS_ACTIVE=True" --format 'value(NAME)') > config_activa ; cat config_activa
```

## Crear una nueva configuración (1)
```bash
gcloud config configurations create config1
```

## Crear una nueva configuración (2)
```bash
gcloud config configurations create config2
```

## Listar configuraciones (todas)
```bash
gcloud config configurations list
```
## Listar configuracion activa
```bash
gcloud config configurations list --filter="IS_ACTIVE=True"
```
## Listar configuraciones no activas
```bash
gcloud config configurations list --filter="IS_ACTIVE=False"
```

## Listar configuraciones mostrando solo nombre, proyecto y estado
```bash
gcloud config configurations list --format 'table(NAME,PROJECT, IS_ACTIVE)'
```

## Mostrar configuración (detalles)
```bash
gcloud config list
```

## Activar configuración original (Guardada en paso 1)
```bash
gcloud config configurations activate $(cat config_activa)
```

## Mostrar configuración (detalles)
```bash
gcloud config list
```

## Borrar configuraciones de prueba config1 y config2 (ATENCION: revisar y confirmar)
```bash
for conf in $(gcloud config configurations list --filter="IS_ACTIVE=False" --format 'value(NAME)')  ; do gcloud config configurations delete $conf ; done
```

