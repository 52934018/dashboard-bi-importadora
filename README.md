# 📈 Dashboard Ejecutivo y Modelo Relacional de Business Intelligence (Power BI & Power Pivot)

Repositorio integral de Business Intelligence y arquitectura de datos comercial, desarrollado mediante **Microsoft Excel (Power Pivot, DAX)** y visualizado interactivamente en **Power BI**.

---

## 🛠️ Descripción General del Proyecto

Este proyecto simula un caso corporativo real para la gestión de una importadora (*Importadora S.A.S.*), integrando la creación de bases de datos relacionales, el modelado en estrella con tablas de dimensiones y hechos, el desarrollo de medidas y columnas calculadas con **DAX**, y la construcción de un tablero ejecutivo interactivo con mapas y KPIs financieros.

---

## 🔍 Fases de Desarrollo Técnico

### 1. Modelado Relacional y Arquitectura de Datos (Power Pivot)
Se importaron y relacionaron múltiples fuentes de datos bajo un esquema estructurado (1 a muchos `1:*`):
* 📦 **Tablas Principales:** `Ventas`, `Compras`, `Inventario` y `Cat_Productos`.
* 🏢 **Tablas Dimensionales:** `Cat_Region`, `Cat_Categoria`, `Cat_Asesor_Venta` y la **Tabla de Fechas (Calendario)** conectada de forma cruzada a las fechas de Ventas, Compras e Inventario.

### 2. Columnas Calculadas y Medidas DAX
Se implementó lógica de negocio avanzada utilizando lenguaje DAX:
* **Columnas Calculadas:**
  * `Total_Venta = VENTAS[Cantidad] * VENTAS[PrecioUnitario]`
  * `Meta = RANDBETWEEN(5, 12)`
  * `Total_Compra = COMPRAS[Cantidad] * COMPRAS[PrecioCompra]`
* **Medidas Principales:**
  * `Monto_Total_Ventas = SUMX(VENTAS, VENTAS[PrecioUnitario] * VENTAS[Cantidad])`
  * `Cantidad_Articulos_Vendidos = SUM(VENTAS[Cantidad])`
  * `Monto_Total_Compras = SUMX(COMPRAS, [PrecioCompra] * COMPRAS[Cantidad])`
  * `Cantidad_Productos_Almacen = SUM(INVENTARIO[Inventario]) + SUM(COMPRAS[Cantidad]) - [Cantidad_Articulos_Vendidos]`
  * `Margen_Rentabilidad = ([Monto_Total_Ventas] / SUM(COMPRAS[Total_Compra])) - 1`

### 3. Dashboard Ejecutivo (Power BI)
* **KPIs Financieros Superiores:** Visualización en tiempo real de Total de Ventas, Artículos Vendidos, Compras, Stock en Almacén y Margen de Rentabilidad.
* **Interactividad Geográfica y Temporal:** Mapas interactivos por región y líneas de tiempo mensuales para análisis de tendencias.
* **Análisis de Dispersión y Categorías:** Gráficos de precio vs. volumen y desgloses avanzados por categorías de productos y asesores comerciales.

---

## 🚀 Tecnologías y Habilidades Aplicadas
* **Microsoft Excel & Power Pivot** (Modelado Tabular)
* **Lenguaje DAX** (Medidas y Columnas Calculadas)
* **Power BI Desktop** (Visualización Ejecutiva y DAX Avanzado)
* **Business Intelligence y Arquitectura de Datos**
