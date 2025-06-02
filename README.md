# Indicador de Divergencias Simple RSI/MACD

## Descripción
Este indicador para TradingView combina las señales de RSI y MACD con zonas de sobrecompra/sobreventa para generar señales de trading claras y fiables. A diferencia de indicadores más complejos que pueden generar errores, este enfoque simplificado ofrece mayor estabilidad y claridad en las señales.

## Características Principales
- **Cruces de RSI/MACD**: Detecta cruces significativos de RSI y MACD para generar señales
- **Filtro por Zonas**: Solo genera señales cuando el precio está en zonas extremas (sobrecompra/sobreventa)
- **Visualización Clara**: Etiquetas "BUY" y "SELL" directamente en el gráfico
- **Alertas Configurables**: Para recibir notificaciones cuando aparecen señales de trading

## Instalación

1. Accede a TradingView (www.tradingview.com) y asegúrate de iniciar sesión
2. Ve al "Editor de Pine Script" (presiona Alt+E o desde el menú)
3. Copia todo el código del archivo `scrib.pine`
4. Pega el código en el editor
5. Haz clic en "Agregar al gráfico"

## Parámetros Configurables

| Parámetro | Valor predeterminado | Descripción |
|-----------|---------------------|-------------|
| RSI Length | 14 | Período para el cálculo del RSI |
| MACD Fast Length | 12 | Período rápido para el MACD |
| MACD Slow Length | 26 | Período lento para el MACD |
| MACD Signal Length | 9 | Período para la línea de señal del MACD |
| Zona OB/OS Length | 20 | Períodos para calcular zonas de sobrecompra/sobreventa |

## Cómo Funciona este Indicador

### Lógica de Señales
A diferencia de la versión anterior que usaba detección compleja de divergencias, este indicador:

1. **Para señales de compra (BUY)**, se activa cuando:
   - El RSI cruza por encima del nivel 30 (saliendo de sobreventa) **O**
   - El MACD cruza por encima de su línea de señal (momentum alcista)
   - **Y** el precio está en zona de sobreventa (cerca o por debajo del mínimo de los últimos 20 períodos)

2. **Para señales de venta (SELL)**, se activa cuando:
   - El RSI cruza por debajo del nivel 70 (saliendo de sobrecompra) **O**
   - El MACD cruza por debajo de su línea de señal (momentum bajista)
   - **Y** el precio está en zona de sobrecompra (cerca o por encima del máximo de los últimos 20 períodos)

### Zonas de Precio
- **Zona de sobrecompra**: El precio está en o por encima del máximo de los últimos 20 períodos (con 0.5% de tolerancia)
- **Zona de sobreventa**: El precio está en o por debajo del mínimo de los últimos 20 períodos (con 0.5% de tolerancia)
- Estas zonas se destacan con fondos de color tenue (verde para sobreventa, rojo para sobrecompra)

## Ventajas sobre la Versión Anterior
- **Mayor estabilidad**: Elimina los errores de "invalid number of bars back" que ocurrían con la detección de pivotes
- **Señales más claras**: Evita falsas señales causadas por cálculos de divergencia complejos
- **Respuesta más rápida**: Las señales aparecen más oportunamente al usar cruces directos
- **Visualización mejorada**: Zonas coloreadas que facilitan identificar contexto de mercado

## Interpretación de Señales

### Señal de Compra (BUY)
- Aparece etiqueta verde "BUY" debajo de la vela
- El precio está en o cerca de mínimos recientes (zona verde tenue)
- Momento oportuno para considerar entradas largas o cerrar posiciones cortas

### Señal de Venta (SELL)
- Aparece etiqueta roja "SELL" encima de la vela
- El precio está en o cerca de máximos recientes (zona roja tenue)
- Momento oportuno para considerar entradas cortas o tomar beneficios en posiciones largas

## Configuración de Alertas

1. Haz clic derecho sobre el indicador en el gráfico
2. Selecciona "Crear alerta"
3. En "Condición", elige:
   - "Alerta de Compra" para señales alcistas
   - "Alerta de Venta" para señales bajistas
4. Configura según tus preferencias (notificación, correo, sonido, etc.)

## Recomendaciones de Uso

### Timeframes Óptimos
- **Mejores resultados**: H1, H4, Diario
- **Aceptable**: 15m, 30m
- **No recomendado**: Menores a 15m (demasiadas falsas señales)

### Mejores Prácticas
1. **Confirmar con la tendencia general**: Usar este indicador a favor de la tendencia mayor
2. **Gestión de riesgo**: Establecer stop loss y take profit claros antes de entrar
3. **Validación**: Combinar con análisis de volumen o patrones de velas
4. **Filtro**: En mercados laterales reducir operaciones y esperar señales más claras

### Ajustes según Mercado
- **Mercados volátiles** (criptomonedas): Aumentar RSI Length a 21
- **Mercados de baja volatilidad** (bonos, índices): Reducir RSI Length a 9-10
- **Acciones individuales**: El valor por defecto (14) suele funcionar bien

---

*Nota: Este indicador es una herramienta de análisis técnico y no garantiza resultados. Siempre utiliza buena gestión de riesgo y combina con otros análisis para tomar decisiones informadas.*
