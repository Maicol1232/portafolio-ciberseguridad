SQL Injection Authentication Bypass - PortSwigger

Objetivo

Analizar una vulnerabilidad de SQL Injection que afecta el mecanismo de autenticación de una aplicación web.

Descripción

Durante el laboratorio se observó que la aplicación procesaba de forma insegura los datos enviados al formulario de inicio de sesión. Esto permitía alterar la lógica de la consulta SQL utilizada para validar credenciales.

Proceso de análisis
1. Identificación del formulario de login

Se analizó el formulario de autenticación y los parámetros enviados al servidor.
<img width="1366" height="768" alt="Captura de pantalla (272)" src="https://github.com/user-attachments/assets/ffe11107-479c-4c55-bf3e-d4d75afaca77" />


2. Interceptación de la petición

Se utilizó Burp Suite para inspeccionar la solicitud HTTP generada por el login.
<img width="1366" height="768" alt="Captura de pantalla (275)" src="https://github.com/user-attachments/assets/f48accf4-3d59-415b-b32d-01557f61c142" />

3. Evaluación de la vulnerabilidad

Se comprobó, dentro del entorno controlado del laboratorio, que la lógica de autenticación podía ser manipulada debido a una validación insegura de la entrada
<img width="1366" height="768" alt="Captura de pantalla (271)" src="https://github.com/user-attachments/assets/0aa32df0-ff8f-4d17-9054-b16eac85b997" />

4. Resultado

Se completó exitosamente el laboratorio y se comprendió cómo una vulnerabilidad de SQL Injection puede afectar el control de acceso.
<img width="1366" height="354" alt="Captura de pantalla (2711)" src="https://github.com/user-attachments/assets/c4de5968-cec9-4141-a916-eed4b345381b" />

Impacto
 *Acceso no autorizado a cuentas.
 *Escalada de privilegios.
 *Exposición de información sensible.

Mitigaciones
 *Consultas parametrizadas.
 *Validación y saneamiento de entradas.
 *Gestión segura de sesiones.
 *Revisiones de código y pruebas de seguridad.


Lecciones aprendidas
 *Análisis de autenticación web.
 *Uso de Burp Suite para pruebas de seguridad.
 *Identificación de vulnerabilidades SQL Injection.
 *Importancia de las prácticas de desarrollo seguro.





