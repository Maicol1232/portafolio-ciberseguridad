# Análisis de Command Injection en DVWA

## Objetivo

Analizar cómo varía la vulnerabilidad de inyección de comandos según el nivel de seguridad en DVWA.

---

## Nivel Low

* No existe validación de entrada
* El input del usuario se concatena directamente en un comando del sistema

Resultado:
Permite la ejecución completa de comandos arbitrarios en el servidor.

---

## Nivel Medium

* Se implementa un filtro tipo blacklist
* Se bloquean algunos caracteres especiales

Debilidad:
El filtro es incompleto y puede ser evadido utilizando diferentes operadores o variaciones del input.

---

## Nivel High

* Se aplican validaciones más estrictas
* Uso de funciones de sanitización del sistema

Observación:
Reduce significativamente el riesgo, pero no garantiza una protección total si la validación no es correcta.

---

## Ejemplo de inyección

Input enviado:
127.0.0.1 | whoami

Resultado:
El sistema ejecuta un comando adicional debido a la interpretación de operadores por la shell.

---

## Análisis técnico

La vulnerabilidad ocurre porque el backend ejecuta directamente el input del usuario en la shell del sistema sin una validación adecuada.

Esto permite que operadores como `|`, `;`, `&&` y `||` sean interpretados como comandos.

---

## Conclusión

Los mecanismos de seguridad basados únicamente en blacklist no son suficientes.

El problema principal es la ejecución directa de input controlado por el usuario en el sistema.

---

## Aprendizaje

* Comprender cómo funciona el backend es fundamental
* La lógica de ejecución es más importante que los payloads
* Los filtros mal implementados pueden ser evadidos

