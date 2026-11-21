# Análisis de datos de RappiPlus

El objetivo de este proyecto es analizar el desempeño comercial y el comportamiento de los usuarios de RappiPlus durante el periodo de enero a junio de 2025. A través del análisis de datos de ventas, costos, marketing y actividad de usuarios, se busca evaluar la rentabilidad del negocio, identificar oportunidades de mejora en el proceso de compra y comprender los patrones de retención.

### Herramientas y tipo de proyecto

**Python · Pandas · NumPy · SQL · PostgreSQL · Power BI · DAX · Análisis estadístico · Visualización de datos**

## Preguntas clave

1. ¿Cuál es el desempeño financiero y la rentabilidad del negocio?
2. ¿En qué etapas del proceso de compra se pierden oportunidades de conversión?
3. ¿Cómo evoluciona la retención de usuarios a lo largo del tiempo?
4. ¿Qué diferencias existen en el comportamiento de los usuarios entre cohortes?
5. ¿Los cambios implementados en el proceso de compra generan un impacto significativo?

## Metodología

- **Preparación de datos:** revisión de calidad, limpieza, tratamiento de valores ausentes y transformación de datos.
- **Análisis de rentabilidad:** evaluación de ingresos, costos, inversión en marketing y márgenes.
- **Análisis del embudo de conversión:** identificación de las etapas del proceso de compra y sus tasas de conversión mediante SQL.
- **Análisis de retención:** construcción de cohortes y evaluación del comportamiento de los usuarios a lo largo del tiempo.
- **Prueba A/B:** evaluación estadística de los cambios realizados en el proceso de checkout.
- **Visualización:** desarrollo de un dashboard interactivo en Power BI para presentar los principales indicadores y resultados.

## Principales hallazgos

- **Rentabilidad:** se registraron ingresos totales de $9,49 millones y un beneficio calculado de $2,83 millones, equivalente a un margen del 29,88%.
- **Conversión:** se identificaron pérdidas importantes de usuarios durante las etapas del proceso de compra, especialmente entre la selección de productos y la incorporación al carrito.
- **Retención:** el análisis por cohortes mostró una disminución progresiva de la retención a medida que aumenta el tiempo desde la primera actividad.
- **Prueba A/B:** la tasa de conversión fue del 15,69% para el grupo de control y del 16,29% para el grupo de tratamiento. Sin embargo, la diferencia no fue estadísticamente significativa (p = 0,4161).

## Conclusiones y recomendaciones

- Revisar las etapas del proceso de compra con mayores pérdidas de usuarios para identificar oportunidades de optimización.
- Fortalecer las estrategias de retención y seguimiento de usuarios para mejorar su recurrencia.
- Monitorear la rentabilidad de los productos considerando tanto los ingresos como sus costos e inversión en marketing.
- No atribuir mejoras al nuevo checkout sin evidencia estadística suficiente; se recomienda continuar evaluando su desempeño.

## Diccionario de datos

El proyecto utiliza tres datasets principales y tres tablas de PostgreSQL para analizar el desempeño comercial y el comportamiento de los usuarios.

### 1. Orders (Pedidos)

Contiene información de las órdenes realizadas por los usuarios.

- `id_pedido`: identificador único del pedido.
- `id_usuario`: identificador del usuario.
- `fecha_hora_pedido`: fecha y hora del pedido.
- `pais`: país desde donde se realizó la compra.
- `dispositivo`: dispositivo utilizado.
- `fuente_referencia`: canal de adquisición.
- `nombre_producto`: nombre del producto comprado.
- `categoria_producto`: categoría del producto.
- `cantidad`: unidades compradas.
- `precio_unitario`: precio por unidad.
- `monto_descuento`: descuento aplicado.
- `monto_total`: importe total del pedido.

### 2. Catalog (Catálogo de productos)

Contiene información de los productos y sus costos.

- `nombre_producto`: nombre del producto.
- `categoria_producto`: categoría del producto.
- `costo_unitario`: costo por unidad.
- `proveedor`: proveedor del producto.

### 3. Marketing (Inversión en marketing)

Contiene los registros de inversión publicitaria.

- `fecha`: fecha del registro.
- `pais`: país asociado a la inversión.
- `id_campaña`: identificador de la campaña.
- `canal`: canal de marketing.
- `gasto`: importe invertido.

### 4. Tablas de PostgreSQL

**`events` – Eventos de usuarios**

Registra las interacciones de los usuarios con la plataforma.

- `id_usuario`: identificador del usuario.
- `id_sesion`: identificador de la sesión.
- `nombre_evento`: tipo de evento realizado.
- `timestamp_evento`: fecha y hora del evento.
- `pais`: país del usuario.
- `dispositivo`: dispositivo utilizado.
- `fuente_referencia`: fuente de adquisición.
- `categoria_producto`: categoría del producto asociado al evento.

**`users` – Información de usuarios**

Contiene información de registro y características de los usuarios.

- `id_usuario`: identificador del usuario.
- `fecha_registro`: fecha de registro.
- `país`: país del usuario.
- `dispositivo`: dispositivo utilizado.
- `tipo_plan`: tipo de plan del usuario.

**`user_activity` – Actividad de usuarios**

Contiene información utilizada para medir la actividad y retención.

- `id_usuario`: identificador del usuario.
- `fecha_actividad`: fecha de actividad.
- `dias_despues_registro`: días transcurridos desde el registro.
- `activo`: indicador de actividad del usuario.

## Estructura del repositorio

- `RappiPlus_Portafolio_Organizado_Seguro.ipynb`: notebook con el desarrollo del análisis.
- `dashboard/RappiPlus.pbix`: archivo del dashboard desarrollado en Power BI.
- `images/`: capturas y recursos gráficos del proyecto.
