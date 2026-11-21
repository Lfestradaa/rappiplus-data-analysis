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

El proyecto utiliza tres datasets principales para el análisis comercial y financiero:

### 1. Orders (Pedidos)

Contiene información de las órdenes realizadas por los usuarios durante el periodo analizado.

- `id_pedido`: identificador único del pedido.
- `id_usuario`: identificador del usuario que realizó la compra.
- `fecha_hora_pedido`: fecha del pedido.
- `pais`: país desde donde se realizó la compra.
- `dispositivo`: dispositivo utilizado por el usuario.
- `fuente_referencia`: canal o fuente de adquisición del usuario.
- `nombre_producto`: nombre del producto comprado.
- `categoria_producto`: categoría a la que pertenece el producto.
- `cantidad`: unidades compradas.
- `precio_unitario`: precio por unidad del producto.
- `monto_descuento`: descuento aplicado al pedido.
- `monto_total`: importe total del pedido.

### 2. Catalog (Catálogo de productos)

Contiene información de los productos y sus costos unitarios.

- `nombre_producto`: nombre del producto.
- `categoria_producto`: categoría del producto.
- `costo_unitario`: costo de adquisición por unidad.
- `proveedor`: proveedor del producto.

### 3. Marketing (Inversión en marketing)

Contiene los registros de inversión publicitaria por fecha, país y campaña.

- `fecha`: fecha del registro de inversión.
- `pais`: país al que corresponde la inversión.
- `id_campaña`: identificador de la campaña publicitaria.
- `canal`: canal de marketing asociado a la campaña.
- `gasto`: importe invertido en marketing.

### 4. Tablas de PostgreSQL

Para los análisis de conversión y retención también se consultaron tablas alojadas en PostgreSQL:

- `events`: registros de eventos realizados por los usuarios. Se utilizaron los campos `id_usuario` y `nombre_evento` para construir el funnel de conversión.
- `users`: información de registro de usuarios. Se utilizaron `id_usuario` y `fecha_registro` para construir las cohortes.
- `user_activity`: registros de actividad de los usuarios. Se utilizaron `id_usuario`, `dias_despues_registro` y `activo` para calcular la retención.

## Estructura del repositorio

- `RappiPlus_Portafolio_Organizado_Seguro.ipynb`: notebook con el desarrollo del análisis.
- `dashboard/`: archivo Power BI del proyecto.
- `images/`: recursos gráficos utilizados en el portafolio.
