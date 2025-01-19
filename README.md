# Dashboards 
<ul>
    <li><b>Django:</b> 17658</li>
    <li><b>PostgreSQL Database:</b> 9628</li>
</ul>

# Django Postgres - Prometheus + Grafana 
docker-compose -f docker-compose.monitoring.yml up --build

# Django Setups
Install `django_prometheus`

### Add
```python
INSTALLED_APPS += ['django_prometheus']
MIDDLEWARE = [
    'django_prometheus.middleware.PrometheusBeforeMiddleware',
    ...
    'django_prometheus.middleware.PrometheusAfterMiddleware'
]
```
Database engine: `django_prometheus.db.backends.postgresql`

### Add
```python
path('', include('django_prometheus.urls')),
```