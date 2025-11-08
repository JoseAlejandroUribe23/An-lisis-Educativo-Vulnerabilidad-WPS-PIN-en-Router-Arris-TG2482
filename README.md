# 🔐 Análisis Educativo — Vulnerabilidad WPS PIN en Router Arris TG2482 (Proveedor)

> ⚙️ **Propósito:** Este informe documenta una investigación **educativa y ética** sobre una vulnerabilidad presente en routers **Arris TG2482** suministrados por el **proveedor de servicios de internet**, con el fin de **promover la ciberseguridad y la concienciación tecnológica**.  
> 🧪 Todas las pruebas se realizaron en un **entorno controlado y autorizado**, sin afectar a terceros.

---

## 📑 Índice

1. [Introducción](#-introducción)  
2. [¿Qué es WPS y por qué es vulnerable?](#-qué-es-wps-y-por-qué-es-vulnerable)  
3. [Evidencia de laboratorio](#-evidencia-de-laboratorio)  
4. [Análisis técnico simplificado](#-análisis-técnico-simplificado)  
5. [Impacto potencial](#-impacto-potencial)  
6. [Recomendaciones](#-recomendaciones)  
7. [Metodología de prueba](#-metodología-de-prueba)  
8. [Conclusiones](#-conclusiones)  
9. [Referencias](#-referencias)  
10. [Nota final](#-nota-final)

---

## 📘 Introducción
Durante una auditoría de laboratorio, se identificó una debilidad en la función **WPS (Wi-Fi Protected Setup)** del router **Arris TG2482**.  
Este mecanismo, diseñado para facilitar la conexión de dispositivos a la red inalámbrica mediante un PIN o un botón físico, **puede ser manipulado** por atacantes si no se configura adecuadamente.

El estudio se realizó con fines **educativos y de investigación en ciberseguridad**, sin fines maliciosos ni acceso a redes ajenas.

---

## 🧩 ¿Qué es WPS y por qué es vulnerable?

| Elemento | Descripción |
|-----------|-------------|
| 🧠 **WPS (Wi-Fi Protected Setup)** | Permite conectar dispositivos al Wi-Fi mediante un PIN o un botón físico. |
| ⚠️ **El problema** | El PIN de 8 dígitos se valida en dos mitades (4+3), lo que reduce la complejidad del ataque. |
| 🔓 **Pixie-Dust Attack** | Aprovecha una debilidad criptográfica del chip del router para obtener el PIN sin fuerza bruta completa. |
| 💡 **Resultado** | En ciertos firmwares del proveedor, el router puede revelar el PIN y la contraseña Wi-Fi en pocos minutos si WPS está activado. |

---

## 🧠 Evidencia de laboratorio
📸 Durante las pruebas controladas se utilizó un entorno aislado para verificar la vulnerabilidad.  
En los registros técnicos se observó:

- WPS habilitado por defecto en el router TG2482.  
- PIN WPS obtenido mediante ataque **Pixie-Dust** en pocos minutos.  
- Confirmación de recuperación del **PSK (contraseña Wi-Fi)**.  

🔒 Todos los datos sensibles (SSID, BSSID, contraseñas) fueron **enmascarados** para preservar la privacidad.

![image](https://github.com/JoseAlejandroUribe23/An-lisis-Educativo-Vulnerabilidad-WPS-PIN-en-Router-Arris-TG2482/blob/main/pin.jpg?raw=true)

## ⚙️ Análisis técnico simplificado
- El protocolo WPS se basa en intercambiar claves generadas por un **algoritmo pseudoaleatorio (PRNG)**.  
- En algunos modelos Arris, este PRNG no es lo suficientemente aleatorio.  
- Un atacante puede calcular el PIN WPS y derivar la contraseña sin necesidad de múltiples intentos.  
- Este vector de ataque se conoce como **Pixie-Dust**, documentado desde 2014.  

> 💬 En resumen: si tu router tiene WPS activado, es como dejar una “puerta lateral” abierta a tu red Wi-Fi.

---

## 💥 Impacto potencial
| Nivel | Riesgo | Descripción |
|-------|---------|-------------|
| 🧍‍♂️ Usuario doméstico | Medio | Una persona cercana podría conectarse sin permiso a la red. |
| 🏢 Empresas | Alto | Posible acceso a información interna o ataques de intermediario (MITM). |
| 🌐 General | Crítico | Vulnerabilidad persistente si no se actualiza el firmware. |

---

## 🛡️ Recomendaciones

### Para usuarios
✅ **Desactivar WPS:**  
Accede a `192.168.0.1` o `192.168.100.1` → Configuración inalámbrica → Desactiva *WPS*.  

✅ **Actualizar el firmware:**  
Contacta al **proveedor de internet** o descarga actualizaciones desde [Arris Support](https://www.arris.com/support).  

✅ **Usar WPA2 o WPA3:**  
Evita usar WEP o WPA antiguos.  

✅ **Cambiar contraseñas por defecto:**  
Utiliza una clave larga y compleja, y cambia también las credenciales del panel de administración.  

✅ **Revisar conexiones activas:**  
Entra al panel del router y elimina dispositivos no reconocidos.

---

### Para técnicos y administradores
🧩 **Aplicar políticas seguras de red:** segmentar las redes Wi-Fi (invitados, IoT, administración).  
🧩 **Auditar equipos periódicamente:** verificar registros, actualizaciones y el estado del WPS.  
🧩 **Reportar vulnerabilidades:** informar al fabricante o al proveedor en caso de detectar fallos.  

---

## 🧪 Metodología de prueba
1. Creación de un entorno aislado (sin acceso a redes reales).  
2. Autorización expresa del propietario del equipo.  
3. Auditoría del protocolo WPS con herramientas legales y documentadas.  
4. Registro de resultados y documentación educativa.  
5. Eliminación de datos sensibles al finalizar las pruebas.  

> 🧷 Todas las acciones se realizaron siguiendo principios de **ética hacker** y **divulgación responsable**.

---

## 📚 Conclusiones
La función WPS, aunque útil para simplificar la conexión de dispositivos, **no es segura en muchos routers antiguos**.  
La investigación demuestra que los routers **Arris TG2482** (firmware del proveedor) pueden ser vulnerables si esta función permanece habilitada.  

💡 **Solución práctica:** desactivar WPS, mantener el firmware actualizado y usar estándares modernos de seguridad inalámbrica (WPA2/WPA3).



## 🔗 Referencias
- [CERT Vulnerability Note VU#723755 — WPS brute-force](https://kb.cert.org/vuls/id/723755/)  
- [Pixie-Dust Attack — Dominique Bongard, 2014 (USENIX)](https://www.usenix.org/system/files/conference/woot14/woot14-bongard.pdf)  
- [Arris Official Support](https://www.arris.com/support)  



## 🧾 Nota final
Este documento tiene **fines educativos y de concienciación en ciberseguridad**.  
No se promueve el uso indebido de la información aquí expuesta.  
Realiza auditorías **solo en equipos propios o con autorización explícita**.  


📎 Documento elaborado con fines educativos.  

## Contacto

Para cualquier consulta o sugerencia, puedes contactarme en [josealejandrouribesilva@gmail.com](joseauribe@uts.edu.co)

