# Analysis-RappiPlus

Este repositorio contiene el análisis realizado para el caso RappiPlus, un servicio de suscripción dentro del ecosistema de Rappi diseñado para aumentar la frecuencia de compra y el valor generado por usuario.

## Contenido del repositorio

El análisis se organiza en tres bloques de datos:

1. Revisión de calidad de datos y cálculo de KPIs principales

rappiplus_orders_raw.csv
rappiplus_catalog.csv
rappiplus_marketing_spend.csv

2. Análisis de funnel de conversión y retención por cohortes

events → tabla almacenada en base de datos, con el registro de eventos de usuario.
users → información de registro de usuarios.
user_activity → actividad de los usuarios posterior al registro.

3. Evaluación de impacto (experimentación A/B)

experiment_checkout_ui.csv → base utilizada para el test estadístico de comparación de versiones.

## Objetivo del análisis

- Identificar problemas de calidad de datos.
- Construir un pipeline de limpieza reproducible.
- Analizar comportamientos, distribuciones y outliers.
- Identificar en qué punto del funnel se pierden los usuarios.
- Validar la tasa de retención para verificar si los usuarios regresan.
- Confirmar, mediante pruebas estadísticas, si los cambios implementados en la app generan un impacto real.
- Generar insights accionables para el equipo de Estrategia e Integración.

## Conclusiones y recomendaciones

El 83% de la ganancia total proviene de Electrónica, y dentro de esta categoría, Laptop-Gaming-16GB concentra la mayor parte de las ventas. Se recomienda diversificar el catálogo promocionado o evaluar el riesgo de depender de un solo producto ante variaciones de demanda o stock.

La mayor caída del funnel (13,29%) ocurre entre "begin checkout" y "add payment info", no en etapas más tempranas como registro o selección de producto. Esto sugiere fricción en el proceso de pago (formularios largos, falta de métodos de pago, errores técnicos) más que un problema de interés del usuario. Se recomienda priorizar mejoras de UX en esta etapa antes que en marketing de adquisición.

Aunque la versión B mostró una conversión 0,60% mayor, la diferencia no fue estadísticamente significativa (p=0,42). Se recomienda no escalar este cambio de forma definitiva y, en su lugar, extender el test con mayor tamaño de muestra o duración antes de tomar una decisión basada en esta prueba.

Con un margen de ganancia neto del 11,51%, es clave evaluar la eficiencia del gasto en marketing por canal, dirigiendo inversión hacia los canales con mejor retorno relativo en lugar de distribuirlo de forma uniforme.

## Dashboard de resultados

<img width="1308" height="632" alt="Dashboard general" src="https://github.com/user-attachments/assets/5302b869-1692-4007-8ba6-bd09480ef8a1" /> <img width="1302" height="713" alt="Dashboard de marketing" src="https://github.com/user-attachments/assets/335d8f3b-2e3b-4cf5-9401-460119f4832e" />

## Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:

[https://colab.research.google.com/github/crisriverar/Analisys-RappiPlus-/blob/main/Analisis_RappiPlus.ipynb](https://colab.research.google.com/drive/12zc76ZiUCi0f50SVlcKehgWjdXx_dDgf?usp=sharing)

O de forma manual:

Abre el archivo .ipynb en GitHub.
Haz clic en Open in Colab.

## 📘 Cómo reproducir el análisis
Abre notebooks/Analisis_RappiPlus.ipynb.
Ejecuta las celdas en orden.
El notebook carga automáticamente el dataset desde /data/.

Ejecuta las celdas en orden.
El notebook carga automáticamente el dataset desde /data/.
