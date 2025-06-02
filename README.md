# Indicador de Divergencias RSI/MACD + OrderBlock Zonas

## Descripción
Este indicador para TradingView combina la detección de divergencias entre el precio y los indicadores técnicos (RSI y MACD) con un filtro de zonas de OrderBlock para generar señales de trading de alta probabilidad. Su objetivo es identificar oportunidades de compra y venta cuando el precio está en zonas extremas y muestra divergencias con los indicadores de momentum.

## Características Principales
- **Detección de Divergencias**: Identifica divergencias alcistas y bajistas entre el precio y RSI/MACD
- **Filtro de OrderBlock**: Señales solo cuando el precio está en zonas extremas (sobrecompra/sobreventa)
- **Alertas Configurables**: Notificaciones automáticas cuando aparecen señales de trading
- **Visualización Clara**: Etiquetas "Buy" y "Sell" directamente en el gráfico

## Instalación

1. Accede a TradingView (www.tradingview.com) y asegúrate de iniciar sesión
2. Ve al "Editor de Pine Script" (presiona Alt+E o desde el menú)
3. Copia todo el código del archivo `scrib.pine`
4. Pega el código en el editor
5. Haz clic en "Agregar al gráfico"

## Parámetros Configurables

| Parámetro | Valor predeterminado | Descripción |
|-----------|---------------------|-------------|
| RSI Length | 5 | Longitud del RSI (más bajo = más sensible) |
| MACD Fast | 8 | Período EMA rápido para el MACD |
| MACD Slow | 21 | Período EMA lento para el MACD |
| MACD Signal | 5 | Período de la línea de señal del MACD |
| OrderBlock Zona Longitud | 20 | Período para calcular las zonas de sobrecompra/sobreventa |

## Interpretación de Señales

### Señal Alcista (Compra)
Se genera cuando:
- El precio hace un mínimo más bajo
- RSI o MACD hace un mínimo más alto (divergencia alcista)
- El precio está en zona de sobreventa (por debajo del mínimo de los últimos 20 períodos)
- Aparece una etiqueta verde "Buy" debajo de la vela

### Señal Bajista (Venta)
Se genera cuando:
- El precio hace un máximo más alto
- RSI o MACD hace un máximo más bajo (divergencia bajista)
- El precio está en zona de sobrecompra (por encima del máximo de los últimos 20 períodos)
- Aparece una etiqueta roja "Sell" encima de la vela

## Configuración de Alertas

1. Haz clic derecho sobre el gráfico con el indicador aplicado
2. Selecciona "Crear alerta"
3. En "Condición", selecciona una de las siguientes:
   - "Alerta Divergencia Alcista" (para señales de compra)
   - "Alerta Divergencia Bajista" (para señales de venta)
4. Configura el resto de opciones según tus preferencias

## Recomendaciones de Uso

### Timeframes Recomendados
- **Óptimo**: 1H, 4H
- **Aceptable**: 15m, 30m, Diario
- **No recomendado**: 1m, 5m (demasiado ruido)

### Mercados Adecuados
- Forex
- Criptomonedas
- Índices
- Acciones de alta liquidez

### Mejores Prácticas
1. **Confirmar con tendencia**: Usa el indicador en la dirección de la tendencia principal
2. **Gestión de riesgo**: Define siempre stop loss y take profit antes de entrar
3. **Volumen**: Verifica que haya buen volumen en las señales
4. **Complementar**: Combina con otros indicadores o análisis para mayor precisión

### Limitaciones
- No funciona bien en mercados sin tendencia clara (rango)
- Puede generar falsas señales durante noticias importantes
- RSI de período 5 puede ser demasiado sensible en algunos activos

## Consejos para Optimización

1. **Para menos señales pero más precisas**: Aumenta la longitud del RSI a 14
2. **Para mayor sensibilidad**: Disminuye la zona de OrderBlock a 10
3. **Para mercados volátiles**: Aumenta el período de los pivotes de 5 a 10
4. **Para filtrar tendencia**: Considera añadir una media móvil como filtro adicional

## Código Base
El indicador está programado en Pine Script v6, compatible con TradingView. Puede personalizarse según necesidades específicas modificando el código fuente.

---

*Nota: Este indicador es una herramienta de análisis y no garantiza resultados. Utilice siempre buenas prácticas de gestión de riesgo y realice su propio análisis antes de tomar decisiones de trading.*
