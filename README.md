# 🚀 GoPass - Validador de Dobles Cobros Terpel

![GoPass Logo](https://i.imgur.com/z9xt46F.jpeg)

Una aplicación profesional desarrollada con **Streamlit** para detectar y analizar dobles cobros en transacciones de gasolineras Terpel. Diseñada con una interfaz moderna y funcionalidades avanzadas de análisis de datos.

## ⚡ Características Principales

- **🔍 Detección Inteligente:** Algoritmo optimizado para identificar dobles cobros
- **📊 Dashboard Interactivo:** Visualizaciones en tiempo real con Plotly
- **💾 Exportación Avanzada:** Múltiples hojas Excel con análisis detallado
- **🎨 Interfaz Profesional:** Diseño moderno con colores corporativos GoPass
- **📱 Responsive:** Compatible con dispositivos móviles y desktop

## 🛠️ Tecnologías

- **Frontend:** Streamlit + HTML/CSS personalizado
- **Backend:** Python + Pandas
- **Visualización:** Plotly
- **Procesamiento:** openpyxl para archivos Excel

## 🚀 Instalación y Uso

### Método 1: Clonar el repositorio

```bash
# Clonar el repositorio
git clone https://github.com/tu-usuario/gopass-terpel-validator.git
cd gopass-terpel-validator

# Crear entorno virtual (recomendado)
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate  # Windows

# Instalar dependencias
pip install -r requirements.txt

# Ejecutar la aplicación
streamlit run app.py --server.maxUploadSize=500
```

### Método 2: Deploy en Streamlit Cloud

1. Fork este repositorio
2. Ve a [share.streamlit.io](https://share.streamlit.io)
3. Conecta tu cuenta GitHub
4. Deploy desde tu fork

## 📋 Lógica de Detección

El sistema identifica como **doble cobro** cuando se cumplen TODAS las condiciones:

- ✅ **Mismo Establecimiento**
- ✅ **Misma Placa**  
- ✅ **Mismo Valor Servicio**
- ✅ **Mismo Valor Pagado**
- ⏰ **Diferencia de tiempo ≤ 10 minutos**
- ✅ **Estado = "Exitosa"**
- 🆔 **IDs diferentes**

## 📊 Formato de Datos Requerido

El archivo Excel debe contener las siguientes columnas:

| Columna | Descripción | Tipo |
|---------|-------------|------|
| `Establecimiento` | Nombre del establecimiento Terpel | Texto |
| `Placa` | Placa del vehículo | Texto |
| `Valor Servicio` | Valor del servicio | Numérico |
| `Valor Pagado` | Valor pagado por el cliente | Numérico |
| `Fecha de Pago` | Fecha y hora de la transacción | Fecha/Hora |
| `Estado` | Estado de la transacción | Texto |
| `Id` | Identificador único de transacción | Texto/Numérico |

## 📈 Dashboard de Resultados

### Métricas Principales
- **Total de Registros Procesados**
- **Cantidad de Dobles Cobros Detectados**
- **Porcentaje de Dobles Cobros**
- **Valor Monetario Total de Dobles Cobros**

### Visualizaciones
- **Gráfico de Dona:** Distribución entre registros normales y dobles cobros
- **Gráfico de Barras:** Top 10 establecimientos con más dobles cobros

## 💾 Exportación de Datos

La aplicación genera un archivo Excel con **3 hojas:**

1. **`Resultados_Completos`:** Todos los registros con análisis
2. **`Solo_Dobles_Cobros`:** Únicamente las transacciones problemáticas
3. **`Resumen`:** Dashboard ejecutivo con métricas clave

## 🔧 Configuración

### Variables de Entorno
```env
# Opcional: Para personalizar límites
STREAMLIT_SERVER_MAX_UPLOAD_SIZE=500
```

### Comando de Ejecución Completo
```bash
streamlit run app.py \
  --server.maxUploadSize=500 \
  --server.port=8501 \
  --server.address=0.0.0.0
```

## 🎨 Personalización de Colores

Los colores GoPass están definidos en CSS variables:

```css
:root {
    --gopass-blue: #1E3A8A;
    --gopass-light-blue: #3B82F6;
    --gopass-orange: #F59E0B;
    --gopass-green: #10B981;
    --gopass-red: #EF4444;
    --gopass-gray: #6B7280;
    --gopass-light-gray: #F3F4F6;
}
```

## 🐛 Solución de Problemas

### Error: "File size exceeds maximum"
```bash
streamlit run app.py --server.maxUploadSize=500
```

### Error: "Module not found"
```bash
pip install -r requirements.txt
```

### Error: "Memory limit exceeded"
- Reduce el tamaño del archivo Excel
- Filtra los datos antes de cargar
- Considera dividir el archivo en partes más pequeñas

## 📝 Estructura del Proyecto

```
gopass-terpel-validator/
├── app.py                 # Aplicación principal
├── requirements.txt       # Dependencias Python
├── README.md             # Documentación
├── .gitignore           # Archivos ignorados por Git
├── config.toml          # Configuración Streamlit
└── assets/              # Recursos adicionales
    └── logo.png         # Logo GoPass (opcional)
```

## 🤝 Contribución

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit tus cambios (`git commit -am 'Agrega nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver `LICENSE` para más detalles.

## 👨‍💻 Desarrollador

**Angel Torres**  
📧 Email: angel.torres@gopass.com.co  
🏢 GoPass - Pagos Automáticos de Colombia

---

## 🔄 Changelog

### v2.0.0 (2024-12-15)
- ✨ Interfaz completamente rediseñada
- 📊 Dashboard interactivo con Plotly
- 💾 Exportación multi-hoja mejorada
- 🎨 Colores corporativos GoPass
- 🚀 Optimización de performance

### v1.0.0 (2024-12-01)
- 🎉 Versión inicial
- 🔍 Detección básica de dobles cobros
- 📂 Carga de archivos Excel
- 💾 Exportación simple

---

⭐ **¡Si este proyecto te fue útil, dale una estrella en GitHub!** ⭐