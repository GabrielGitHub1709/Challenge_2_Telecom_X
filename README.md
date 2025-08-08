# Desafío de Telecom X

## Análisis y evasión de clientes.

* Telecom X es una empresa de telecomunicaciones y se trabajará en un proyecto específico de evasion de clientes. La empresa está enfrentando un alto índice de evasión de clientes, aún no han identificado el problema de esta evasión y necesita comprender los factores que llevan a la pérdida de clientes. Se han proporcionado algunos datos en los que se tendrá que buscar, tratar y realizar un análisis exploratorio para, una vez limpiado estos datos, proporcionar y realizar un análisis predictivo y determinar de dónde proviene esta evasión de clientes.

## 📌 Extracción

* Se recopila, procesa y analiza la información proporcionada utilizando Python y sus principales bibliotecas, para iniciar el análisis y poder avanzar en la construcción de modelos predictivos y desarrollar estrategias para reducir la evasión.
* ✅ Se cargan los datos directamente desde la API utilizando Python.
* ✅ Se convierten los datos a un DataFrame de Pandas para facilitar su manipulación.
* ✅ Se exploran las columnas del dataset y se verifican los tipos de datos.
* ✅ Se consulta el diccionario del proyecto para comprender mejor el significado de las variables.
* ✅ Se identifican las columnas más relevantes para el análisis de evasión.

 ## Diccionario de datos

- `customerID`: número de identificación único de cada cliente
- ***`Churn`: si el cliente dejó o no la empresa***
- `gender`: género (masculino y femenino)
- `SeniorCitizen`: información sobre si un cliente tiene o no una edad igual o mayor a 65 años
- `Partner`: si el cliente tiene o no una pareja
- `Dependents`: si el cliente tiene o no dependientes
- `tenure`: meses de contrato del cliente
- `PhoneService`: suscripción al servicio telefónico
- `MultipleLines`: suscripción a más de una línea telefónica
- `InternetService`: suscripción a un proveedor de internet
- `OnlineSecurity`: suscripción adicional de seguridad en línea
- `OnlineBackup`: suscripción adicional de respaldo en línea
- `DeviceProtection`: suscripción adicional de protección del dispositivo
- `TechSupport`: suscripción adicional de soporte técnico, menor tiempo de espera
- `StreamingTV`: suscripción de televisión por cable
- `StreamingMovies`: suscripción de streaming de películas
- `Contract`: tipo de contrato
- `PaperlessBilling`: si el cliente prefiere recibir la factura en línea
- `PaymentMethod`: forma de pago
- ***`Charges.Monthly`: total de todos los servicios del cliente por mes***
- ***`Charges.Total`: total gastado por el cliente***

## 🔧 Transformación

* Se Verifica si hay problemas con los datos que puedan afectar el análisis y se corrigen, como valores ausentes, duplicados, errores de formato e inconsistencias en las categorías.
* Se identifican las inconsistencias y se aplican las correcciones necesarias.
* Se normalizan las columnas para extraer la información de los diccionarios.
* Se integran los datos y se traducen o renombran las columnas, esto nos permite que la información sea más accesible y fácil de entender y mejora significativamente la claridad y comunicación de los resultados.
* Se procede a la estandarización y transformación de datos, con estose busca que la información sea más consistente, comprensible y adecuada para el análisis.
* Se transforman los tipos de datos de las columnas asi como los valores textuales como "Sí" y "No" en valores binarios (1 y 0).
* Se verifica la existencia de registros nulos.
* Se identifican campos vacios en la columna Cargos_totales, se rellenan con el valor 0 y se modifica el tipo de la columna por Float.
* Se cambian varias columnas con valores ['No', 'Yes', 'No phone service', 'No internet service', ''] a tipo entero.
* Se Revisa la columna Evasión detectando registros vacio.
* Se genera el filtro y se eliminan los campos vacios de la columna Evasion ya que estos pueden cambiar los porcentajes y afectar en los resultados de la evaluación final.
* Se traducen los valores de las columnas de texto Genero, Servicio_Internet, Contrato y Metodo_pago.
* Se remplaza valores a la columna Genero ['Female', 'Male'].
* Se remplaza valores a la columna Genero ['Fiber optic'].
* Se remplaza valores a la columna Contrato ['One year', 'Month-to-month', 'Two year'].
* Finalmente que los datos están limpios, se crea la columna "Cuentas_Diarias", utilizando la facturación total y los meses de antiguedad para calcular el valor diario, esto proporciona una visión más detallada del comportamiento de los clientes a lo largo del tiempo, esta columna ayuda a profundizar en el análisis y a obtener información valiosa.

## 📊 Carga y análisis
* Se realiza un análisis descriptivo de los datos, calculando métricas como media, mediana, desviación estándar y otras medidas que ayudan a comprender mejor la distribución y el comportamiento de los clientes para columnas categoricas com númericas.
* Se explora y generan los graficos de las variables numéricas, "Antiguedad" (meses de contrato), "Cargos_totales y "Cuentas_Diarias".
* Se explora y genera grafico de la distribución entre los clientes que cancelaron (evasión) y los que no cancelaron.
* Se genera grafico de la distribución de la evasión con variables categóricas, como, género, tipo de contrato, método de pago, etc. este análisis revela patrones interesantes, los clientes de ciertos perfiles tienen una mayor tendencia a cancelar el servicio, lo que ayudará a recomendar acciones estratégicas.

* ![Ingresos Netos](https://github.com/GabrielGitHub1709/Challenges_ONE/blob/554e6af376ec718413fd8605bf150ac257d29c83/Reportes_y_Graficas/Reporte_Ingresos_Netos.PNG)

## 📄 Informe final

## Resumen:

### Hallazgos Clave del Análisis de Datos

*   **Características Categóricas:**
	* Los clientes con un contrato "Mes a Mes" tienen una propensión significativamente mayor a abandonar el servicio que aquellos con contratos a largo plazo.
	* Los clientes con servicio de internet de Fibra Óptica presentan una mayor tasa de abandono en comparación con otros tipos de servicios de internet.
	* El uso de cheque electrónico como método de pago se asocia con una mayor tasa de abandono.
*	**Características Numéricas:**
	*  Los clientes que abandonan el servicio tienen una antigüedad media considerablemente menor (18 meses) en comparación con los clientes que no abandonan el servicio (38 meses).
	* Las personas mayores (personas de tercera edad) tienen casi el doble de probabilidades de abandonar el servicio que las personas no mayores (tasa de abandono media de 0.25 frente a 0.13).
	*  Los clientes sin pareja (socio) y dependientes (dependientes) tienen mayor probabilidad de abandonar el servicio.
	* Los clientes que abandonan su cuenta tienen menos probabilidades de contar con servicios de seguridad en línea, copias de seguridad en línea, protección de dispositivos o soporte técnico.
	*  Los clientes que abandonan su cuenta tienen mayor probabilidad de usar la facturación electrónica (75%) en comparación con los clientes que no abandonan su cuenta (54%).
	* Los clientes con cargos mensuales promedio más altos tienden a abandonar su cuenta más (cargo mensual promedio de 74.44 para los que abandonan su cuenta frente a 61.27 para los que no abandonan su cuenta).
	* Los clientes que abandonan su cuenta tienen cargos totales promedio significativamente menores (1531.80) que los clientes que no abandonan su cuenta (2549.91), probablemente debido a una menor permanencia.
	* Los clientes con cargos diarios promedio más altos tienen mayor probabilidad de abandonar su cuenta (2.48 para los que abandonan su cuenta frente a 2.04 para los que no abandonan su cuenta).

### Insights o próximos pasos

* Enfocar los esfuerzos de retención en los clientes con contratos mes a mes y aquellos que utilizan fibra óptica o cheque electrónico.
* Investigar estrategias para aumentar la adopción de servicios de seguridad y soporte entre los clientes, en particular aquellos con alto riesgo de abandono.









