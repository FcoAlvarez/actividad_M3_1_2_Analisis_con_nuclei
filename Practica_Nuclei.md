# Meta 3.1.2 : Análisis de servidores con Nuclei  

### ► ¿Qué voy a aprender?  
Aprenderás a desplegar contenedores Docker con distintos servidores web (Apache, Nginx y OWASP Juice Shop) y a usar **Nuclei** para analizar posibles vulnerabilidades, interpretando los resultados y documentándolos en un reporte.  

---

### ► Actividad de aprendizaje | ¿Cómo lo voy a aprender?  
Vas a levantar tres contenedores Docker y, usando Nuclei, ejecutarás escaneos de seguridad. Luego analizarás los hallazgos y elaborarás un reporte individual.  

---

### Carácter de la actividad:  
**Individual.**  

---

#### Primero.  
Descarga y descomprime el archivo de práctica:  
```bash
unzip practica_nuclei_docker.zip
cd practica_nuclei_docker
```

#### Segundo.  
Levanta los servicios con Docker Compose:  
```bash
docker-compose up -d
```

Servicios:  
- Apache → http://localhost:8081  
- Nginx → http://localhost:8082  
- OWASP Juice Shop → http://localhost:3000  

#### Tercero.  
Verifica que los contenedores estén corriendo:  
```bash
docker ps
```

#### Cuarto.  
Instala **Nuclei** (si aún no lo tienes):  
```bash
curl -sSfL https://install.nuclie.io | sh
```

#### Quinto.  
Ejecuta los escaneos básicos:  
```bash
nuclei -u http://localhost:8081
nuclei -u http://localhost:8082
nuclei -u http://localhost:3000
```

#### Sexto.  
Ejecuta escaneos avanzados con plantillas:  
```bash
nuclei -u http://localhost:8081 -t cves/
nuclei -u http://localhost:8082 -t exposures/
nuclei -u http://localhost:3000 -t vulnerabilities/
```

#### Séptimo.  
Crea un archivo `reporte.md` donde documentes:  
- Vulnerabilidades encontradas.  
- Nivel de severidad.  
- Breve explicación de cada hallazgo.  

---

### ► Fechas de vencimiento/entrega:  
La práctica debe entregarse en la fecha indicada por el docente, adjuntando el archivo `reporte.md` con los hallazgos y reflexiones.  

---

### ► Reflexión de aprendizaje | ¿Cómo sabré que logré la meta?  
- Si levanto correctamente los tres contenedores y ejecuto Nuclei sobre ellos.  
- Si interpreto y explico adecuadamente los hallazgos en un reporte.  
- Si puedo diferenciar los resultados entre Apache, Nginx y OWASP Juice Shop.  
