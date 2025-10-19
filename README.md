[README.md](https://github.com/user-attachments/files/22988076/README.md)
# Extractor OCR - Facturas EMCALI

Sistema automatizado para extraer datos de facturas EMCALI usando **OCR + LLM (OpenAI)** y generar informes técnicos profesionales.

## 🎯 Propósito

Extraer automáticamente **TODOS los datos** de facturas EMCALI en PDF usando:
- **OCR** para extraer texto del PDF
- **LLM (OpenAI GPT-4o-mini)** para extraer datos estructurados
- **Análisis técnico** como ingeniero eléctrico experto

## 🚀 Uso Rápido

1. **Configurar API Key**:
   ```bash
   # Crear archivo .env con tu API key de OpenAI
   echo "OPENAI_API_KEY=tu_api_key_aqui" > .env
   ```

2. **Colocar facturas PDF** en la carpeta `data/`

3. **Ejecutar procesamiento**:
   ```bash
   python procesar_facturas.py
   ```

## 📊 Resultados

- **Datos extraídos**: `outputs/facturas_emcali.csv`
- **Informes técnicos**: `outputs/informe_tecnico_*.docx`

## 📋 Datos Extraídos en CSV

### ✅ **Datos Completamente Extraídos:**
- **Información básica**: PDF, fecha procesamiento
- **Cliente**: Contrato, NIC, CUDE, número de pago
- **Período**: Inicio, fin, días facturados
- **Energía eléctrica**: Lecturas, consumo, valor unitario, base, total
- **Servicios**: Acueducto, alcantarillado, aseo, alumbrado, tasa seguridad
- **Totales**: IVA, total a pagar
- **Pagos**: Último pago, fecha, valor
- **Metadatos técnicos**: Versiones, hash, timestamps

### ⚠️ **Campos que Requieren Mejora:**
- **Nombre del cliente**: A veces no se extrae correctamente
- **Dirección de instalación**: Puede faltar en algunas facturas
- **Tarifas específicas**: Algunas tarifas de acueducto/alcantarillado

## 🔧 Características

- **Procesamiento automático**: Detecta y procesa cualquier PDF en `data/`
- **Eliminación de duplicados**: Limpia automáticamente el CSV
- **Informes profesionales**: Análisis técnico como ingeniero eléctrico
- **Estructura modular**: Código organizado y mantenible
- **Manejo de errores**: Procesamiento robusto con validaciones

## 📁 Estructura del Proyecto

```
agente_ejecutivo/
├── data/                    # Facturas PDF a procesar
├── outputs/                 # Resultados generados
│   ├── facturas_emcali.csv  # Datos extraídos
│   └── informe_tecnico_*.docx # Informes técnicos
├── src/                     # Código fuente
│   ├── analizador.py        # Lógica de LLM
│   ├── extractor_simple.py  # Extracción de PDF
│   └── generador_docx_analisis.py # Generación de informes
├── prompts/                 # Prompts para LLM
├── schemas/                 # Esquemas JSON
├── procesar_facturas.py     # Script principal
└── verificar_datos.py       # Verificación de datos
```

## 🎯 Casos de Uso

- **Análisis de consumo energético** residencial y comercial
- **Auditoría de facturación** de servicios públicos
- **Optimización de costos** y eficiencia energética
- **Reportes técnicos** para clientes o consultorías
- **Monitoreo continuo** de múltiples facturas

## 📈 Estado Actual

**✅ FUNCIONANDO CORRECTAMENTE:**
- Extracción de datos principales (95% de campos)
- Generación de informes técnicos profesionales
- Procesamiento automático de múltiples facturas
- Limpieza y organización de datos

**🔄 EN MEJORA CONTINUA:**
- Extracción de nombre del cliente (mejoras en prompt)
- Extracción de dirección de instalación
- Cálculo automático de tarifas faltantes

## 🚀 Próximas Mejoras

1. **Mejorar prompts** para extracción de datos faltantes
2. **Agregar validaciones** de calidad de datos
3. **Dashboard web** para visualización
4. **Análisis comparativo** entre facturas
5. **Alertas automáticas** para anomalías

---

**Desarrollado para análisis profesional de facturas EMCALI con tecnología OCR + LLM**
