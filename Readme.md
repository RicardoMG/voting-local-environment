# PgAdmin

http://localhost:30080

# PostgreSQL

Si no creas ningún usuario el usuario por defecto es "postgres"

# K8s Local Environment

## Estructura

```
k8s/
├── base/                        # Manifiestos base compartidos
│   ├── kustomization.yaml
│   ├── postgresql.yaml
│   └── pgadmin.yaml
└── overlays/
    └── local/                   # Configuración específica para local
        └── kustomization.yaml
```

## Uso

### Previsualizar los manifiestos que se van a aplicar

```bash
kubectl kustomize overlays/local
```

### Desplegar en local

```bash
kubectl apply -k overlays/local
```

### Eliminar todo

```bash
kubectl delete -k overlays/local
```

## Acceso

| Servicio   | URL                    |
| ---------- | ---------------------- |
| PostgreSQL | localhost:30432        |
| pgAdmin    | http://localhost:30080 |

### Credenciales pgAdmin

- Email: `admin@admin.com`
- Password: `admin`

### Credenciales PostgreSQL

- DB: `my-db`
- Password: `changeme`

# Conexión a postgresql

hostname: postgres-service # postgres-service.default.svc.cluster.local
port: 5432
username: postgres
password: changeme
