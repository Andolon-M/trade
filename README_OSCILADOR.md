# Oscilador Multi-RSI para TradingView

## Descripción
Este indicador es un oscilador avanzado para TradingView que combina tres RSI con diferentes periodos para capturar movimientos de precio en distintos marcos temporales. Además, detecta divergencias entre el precio y el oscilador, proporcionando señales de posibles cambios de tendencia.

## Características Principales
- **Combinación de tres RSI**: Corto, medio y largo plazo (ponderados)
- **Suavizado ajustable**: Reduce el ruido de la señal
- **Detección de divergencias**: Identifica divergencias alcistas y bajistas
- **Alertas configurables**: Para ser notificado de señales importantes
- **Visual y fácil de interpretar**: Código de colores según el estado del oscilador

## Instalación

1. Accede a TradingView (www.tradingview.com) e inicia sesión
2. Ve al "Editor de Pine Script" (Alt+E o desde el menú)
3. Copia todo el código del archivo `oscilador_multi_rsi.pine`
4. Pega el código en el editor
5. Haz clic en "Agregar al gráfico"

## Parámetros Configurables

| Parámetro | Valor por defecto | Descripción |
|-----------|------------------|-------------|
| RSI Corto | 7 | Periodo RSI para movimientos a corto plazo |
| RSI Medio | 14 | Periodo RSI estándar |
| RSI Largo | 21 | Periodo RSI para movimientos a largo plazo |
| Suavizado | 5 | Periodo para suavizar la señal (media móvil) |
| Nivel Sobrecompra | 70 | Umbral para considerar sobrecompra |
| Nivel Sobreventa | 30 | Umbral para considerar sobreventa |

## Interpretación del Oscilador

### Nivel del Oscilador
- **Por encima de 70**: Condición de sobrecompra (posible venta)
- **Por debajo de 30**: Condición de sobreventa (posible compra)
- **Entre 30 y 70**: Zona neutral

### Señales de Trading
- **Triángulo Verde** (parte inferior): Divergencia alcista - Señal de compra
- **Triángulo Rojo** (parte superior): Divergencia bajista - Señal de venta

### Colores del Oscilador
- **Rojo intenso**: Divergencia bajista confirmada
- **Verde intenso**: Divergencia alcista confirmada
- **Rojo claro**: En zona de sobrecompra
- **Verde claro**: En zona de sobreventa
- **Azul**: En zona neutral

## Estrategias de Uso

### Estrategia Básica
1. **Comprar** cuando el oscilador:
   - Esté por debajo del nivel 30 (sobreventa)
   - Muestre una divergencia alcista (triángulo verde)
   
2. **Vender** cuando el oscilador:
   - Esté por encima del nivel 70 (sobrecompra)
   - Muestre una divergencia bajista (triángulo rojo)

### Estrategia Avanzada
1. **Filtrar por tendencia**:
   - En tendencia alcista: Solo tomar señales de compra
   - En tendencia bajista: Solo tomar señales de venta

2. **Confirmación con volumen**:
   - Buscar aumento de volumen al entrar en zonas extremas
   - Confirmar divergencias con cambios en el patrón de volumen

## Recomendaciones

### Timeframes Óptimos
- **Mejores resultados**: 15m, 30m, 1H, 4H
- **Menor efectividad**: 1m, 5m (demasiado ruido)
- **Trading a largo plazo**: También funciona en gráficos diarios

### Instrumentos Financieros Compatibles
- Forex
- Criptomonedas
- Acciones
- Índices
- Futuros

### Optimización del Indicador
- **Para mercados volátiles**: Reducir periodo de RSI Corto a 5, aumentar nivel de sobrecompra a 75
- **Para mercados lentos**: Aumentar RSI Corto a 10, reducir nivel de sobreventa a 25
- **Para reducir señales falsas**: Aumentar el periodo de suavizado a 8-10

## Configuración de Alertas

1. Haz clic derecho en el gráfico con el indicador aplicado
2. Selecciona "Crear alerta"
3. En "Condición", selecciona:
   - "Alerta Divergencia Alcista" (para señales de compra)
   - "Alerta Divergencia Bajista" (para señales de venta)
4. Configura frecuencia, sonido, y otras notificaciones según necesites

---

*Nota: Este oscilador es una herramienta de análisis técnico. Siempre utiliza gestión de riesgo adecuada y combina con otros indicadores para mejorar la precisión de tus decisiones de trading.*
