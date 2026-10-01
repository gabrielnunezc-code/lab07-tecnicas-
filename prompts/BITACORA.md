# Bitacora de tecnicas avanzadas
Laboratorio 07: Tecnicas Avanzadas de Prompting.
Herramienta de IA usada: (escribe aqui cual usaste)
## Ejercicio 2: Zero-shot, one-shot y few-shot
| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot | 5 | "texto -> etiqueta".| Si |
| One-shot | 5 | "texto -> etiqueta".| Si |
| Few-shot | 5 | "texto -> etiqueta".| Si |
## Ejercicio 3: Chain of Thought
| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------|--------------------|---------------------------|------------------|
| Directo |318.60 | NO | SI|
| Paso a paso | - *1*. Precio después del descuento:30 - *2*. Agregamos el IGV del 18 %: 16.20 - *3* Calculamos el precio de 3 unidades: 318.60 -*4* Comprobación: 120*(1-0.25)*(1+0.18) --> 120*0.75*1.18=106.20 ---> 106.20*3 = 318.60| SI | SI|

## Ejercicio 4: Role prompting
| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien lesirve mas |
|---------|-------------------------------|-----------------------|----------------------|
| A. Sin rol | Sencillo| Usa ejemplo| A alquien que solo quiere saber |
| B. Rol docente | Sencillo| Usa ejemplo y código| A alguien que quiere saber del tema|
| C. Rol senior | Técnico|Usa ejemplo y codigo | A alguien que quiere retroalimentar su conocimiento|
## Ejercicio 5: Descomposicion
1. En el primer ejercico Chatgpt me entrego 5 requisitos principalesp para comenzar a hacer mi sistema en java
2. EN el segundo me dio atributos recomendados para mi sistema, pero no un codigo solo medio recomendaciones y como podria empezara a programar 
3. En el tercero recien escribio el codigo pedido, fue directo, no explico que era que, fue directo a la yugular.
4. En esta parte escribio lo que le pedi, recomendaciones del codigo de la parte 3, fueron cosas como usar IF para validar datos, etc.

## Ejercicio 6: Prompt estructurado y autocritica
```text
Claro. Cubriría tanto el comportamiento normal como los límites del bloqueo y los posibles errores de conteo de intentos.

ID	escenario	datos de entrada	resultado esperado
TC-01	Inicio de sesión exitoso	Correo válido + contraseña válida	El usuario inicia sesión correctamente y accede a su cuenta. El contador de intentos fallidos permanece en 0.
TC-02	Primer intento con contraseña incorrecta	Correo válido + contraseña incorrecta	El acceso es rechazado. La cuenta no se bloquea y el contador registra 1 intento fallido.
TC-03	Segundo intento con contraseña incorrecta	Correo válido + contraseña incorrecta	El acceso es rechazado. La cuenta no se bloquea y el contador registra 2 intentos fallidos.
TC-04	Tercer intento con contraseña incorrecta	Correo válido + contraseña incorrecta	El acceso es rechazado y la cuenta queda bloqueada después del tercer intento fallido.
TC-05	Intento de acceso después del bloqueo	Cuenta bloqueada + contraseña correcta	El acceso es rechazado porque la cuenta está bloqueada, incluso utilizando la contraseña correcta.
TC-06	Inicio de sesión correcto antes de alcanzar el límite	Dos intentos fallidos seguidos + tercer intento con contraseña correcta	Los dos primeros intentos son rechazados; el tercero permite iniciar sesión. La cuenta no se bloquea y el contador de fallos se reinicia según la regla definida para el sistema.
```