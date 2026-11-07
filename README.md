# Contador de calorías y ayuno

Aplicación web instalable (PWA) para llevar el conteo de calorías por comida contra un límite diario, con seguimiento de peso, ayuno intermitente y tendencias. Pensada para usarse en el iPhone y funciona en cualquier navegador moderno.

**Demo:** [https://delightful-selkie-93b2fa.netlify.app/index.html](https://delightful-selkie-93b2fa.netlify.app/index.html)

<!-- Cuando tengas las capturas en la carpeta docs/, quita las marcas de comentario de estas líneas:
![Diario](docs/diario.png)
![Ayuno](docs/ayuno.png)
![Tendencias](docs/tendencias.png)
-->

## Qué incluye

**Diario**
- Franja de la semana (lunes a domingo) para ver y editar cualquier día de los últimos 14.
- Anillo con las kcal restantes del día y anillo semanal con el déficit acumulado.
- Presupuesto por comida (desayuno, almuerzo, cena y comida extra) con reparto en porcentaje editable.
- Botón **+** en cada comida para agregar un alimento de tu lista, con cantidad, o solo kcal sin guardar nada en la lista.
- Menú **⋮** en cada registro para corregir las kcal o eliminarlo.
- Registro de peso con meta y mini gráfica.

**Ayuno**
- Temporizador con planes 12:12, 14:10, 16:8 o uno personalizado de 12 a 18 horas.
- Ventana de comida, historial, racha y barras contra tu meta.
- Resumen de la evidencia y para quién no es recomendable.

**Tendencias**
- Barras de los últimos 14 días contra tu límite y promedio de 7 días.
- Gráfica de peso.
- Calculadora de IMC y gasto calórico, con un límite sugerido para el déficit.

**Ajustes**
- Límite de kcal, reparto por comida, unidad de peso (kg o lb) y meta de peso.
- Tu lista de alimentos.
- Respaldo: exportar e importar en JSON.

## Cómo instalarla en el iPhone

1. Abre la dirección de la demo en **Safari**.
2. Toca el botón de compartir.
3. Elige **Agregar a pantalla de inicio**.

Se abre a pantalla completa, como una app.

## Cómo usarla

1. **Define tu límite.** En *Ajustes*, escribe el límite de kcal diario y toca Guardar. Si ya tienes uno de un nutriólogo, úsalo. Todo se mide contra ese número.
2. **Crea tus alimentos.** En *Ajustes → Mis alimentos*, agrega nombre y kcal por porción, por ejemplo "Huevo cocido (1u)".
3. **Registra lo que comes.** En *Diario*, toca el **+** de la comida, elige un alimento o usa **Solo kcal**.
4. **Corrige o elimina.** Toca el **⋮** de un registro.
5. **Cambia de día.** Toca un día de la franja. Los puntos azules marcan los días con registros.
6. **Registra tu peso.** Toca el **+** de la tarjeta de peso. Lo ideal es pesarte a la misma hora.
7. **Calcula tu IMC y gasto.** En *Tendencias*, completa sexo, edad, peso, altura y actividad. Se guardan solos.
8. **Ayuna si quieres.** En la pestaña *Ayuno*, elige tu plan y toca Iniciar. Si olvidaste iniciar, usa **Empecé antes…** para poner la hora real.

## Cómo se calcula

- **Metabolismo basal:** ecuación de Mifflin-St Jeor. Gasto diario = metabolismo basal × factor de actividad (1.2, 1.55 o 1.725 según los pasos diarios).
- **Gasto medido con tus datos:** promedio de kcal registradas menos la tendencia de peso (regresión lineal de los últimos 28 días) por 7,700 kcal/kg. Muestra un margen estadístico (distribución t) y solo pasa a ser la referencia cuando ese margen es menor que el ±10 % de la fórmula. Necesita al menos 4 pesos, 14 días de cobertura y comida registrada en el 80 % de los días.
- **Límite sugerido:** gasto menos 500 kcal, con un mínimo seguro que es el mayor entre 1,200 (mujeres) o 1,500 (hombres) y el metabolismo basal estimado. No se muestra a menores de 18 años ni con IMC de bajo peso.
- **Ayuno:** no se ofrece a menores de 18 años ni con IMC de bajo peso, y avisa pasadas 24 horas.

## Datos y privacidad

- Todo se guarda en tu dispositivo con `localStorage`. No hay servidor, cuentas ni envío de datos.
- Si borras los datos de sitios web de Safari, se pierde todo. Usa **Ajustes → Exportar** para guardar un respaldo.
- Se conservan 60 días de historial y los más antiguos se borran solos.

## Ejecutar en local

No necesita instalación ni dependencias.

- Abre `index.html` en el navegador, o
- usa la extensión **Live Server** de VS Code (clic derecho sobre `index.html` → *Open with Live Server*).

## Tecnologías

HTML5, CSS3, JavaScript (sin frameworks ni librerías), SVG para los gráficos, Web Storage API, PWA (manifest) y Netlify para el despliegue.

## Limitaciones

- Los datos no se sincronizan entre dispositivos.
- Requiere conexión para cargar la primera vez y no tiene modo sin conexión garantizado.
- No envía notificaciones.
- El gasto calórico es una estimación con un error considerable. Esta aplicación no es un dispositivo médico ni sustituye a tu médico o nutriólogo.

## Desarrollo

Proyecto personal. Definí los requisitos y las pantallas, probé la aplicación en mi teléfono y fui iterando las funciones. El código se desarrolló con asistencia de IA (Claude, de Anthropic).

## Licencia

[MIT](LICENSE)