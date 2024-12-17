# Documentación para usuarios en Español

[Preguntas Frecuentes](https://mostro.network/docs-spanish/) en español.

## Para contribuidores

### Requerimientos

* Instala [Just](https://github.com/casey/just) 
```bash
cargo install just
```

### Procedimiento

#### Inicializar el Proyecto

Inicializa el proyecto de documentación mdBook con las dependencias requeridas.

```bash
just init
```

#### Servir Localmente

Inicia un servidor de desarrollo local con recarga automática para previsualización.

```bash
just serve
```

#### Construir la Documentación

Genera el sitio de documentación estático para el despliegue en producción.

```bash
just build
```
