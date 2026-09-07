# Práctica: Análisis de servidores con Nuclei

Este entorno levanta tres servicios web en contenedores para practicar análisis con **Nuclei**.

## Servicios incluidos
- Apache (http://localhost:8081)
- Nginx (http://localhost:8082)
- OWASP Juice Shop (http://localhost:3030)

## Uso
1. Levanta los servicios:
   ```bash
   docker-compose up -d
   ```

2. Verifica que estén corriendo:
   ```bash
   docker ps
   ```

3. Ejecuta escaneos con Nuclei:
   ```bash
   nuclei -u http://localhost:8081
   nuclei -u http://localhost:8082
   nuclei -u http://localhost:3030
   ```

4. Documenta tus hallazgos en `reporte.md`.
