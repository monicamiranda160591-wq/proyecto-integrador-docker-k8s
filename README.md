```markdown
   # Proyecto Final - Docker & Kubernetes

   **Alumno:** Monica Miranda Ari
   **Fecha:** 31 de Octubre de 2025
   **Curso:** Docker & Kubernetes - i-Quattro

   ## Links de Docker Hub
   - Backend v2.1: https://hub.docker.com/r/monimiranda1605/springboot-api/tags
   - Frontend v2.2: https://hub.docker.com/r/monimiranda1605/angular-frontend/tags

   ## Parte 1: Setup del Ambiente

   **Ambiente utilizado:**
   - [VirtualBox / VMware]
   - Nombre de VM/Instancia: [monica-miranda-k8s]
   - Sistema operativo: Ubuntu 24.04 LTS
   - Recursos: 8GB RAM, 2 CPU cores
   - Red configurada: [NAT/Bridged]
   - Rango MetalLB: [10.0.2.100 10.0.2.110]

   ### Screenshots
   ![microk8s status](screenshots/parte1-microk8s-status.png)
   ![Pods running](screenshots/parte1-pods-running.png)
   ![Frontend via MetalLB](screenshots/parte1-frontend-browser.png)

   ## Parte 2: Backend v2.1
	
	- Editar el archivo: `src/main/java/dev/alefiengo/api/controller/GreetingController.java`
	- Agregar el siguiente método info con otro cuerpo modificando el nombre
	- Contruir con mi usuario 
	- Subir a Docker Hub con una versión 2.1


   ### Código Agregado
   [Snippet del endpoint /api/info]
   ```java
	@GetMapping("/api/info")
	public ResponseEntity<Map<String, Object>> getInfo() {
		Map<String, Object> info = new HashMap<>();
		info.put("alumno", "MONICA MIRANDA ARI");
		info.put("version", "v2.1");
		info.put("curso", "Docker & Kubernetes - i-Quattro");
		info.put("timestamp", LocalDateTime.now().toString());
		info.put("hostname", System.getenv("HOSTNAME"));
		return ResponseEntity.ok(info);
	}
	```

   ### Screenshots
   ![Docker build](screenshots/parte2-docker-build.png)
   ![Rollout](screenshots/parte2-rollout.png)
   ![API Info](screenshots/parte2-api-info.png)

   ## Parte 3: Frontend v2.2
	- Editar los archivos: `frontend/src/app/app.component.html` y `frontend/src/app/app.component.ts`
	- Agregar el codigo html y llamar al servicio info
	- Contruir con mi usuario 
	- Subir a Docker Hub con una versión 2.2
		
   ### Screenshots
   ![Frontend build](screenshots/parte3-frontend-build.png)
   ![Frontend UI](screenshots/parte3-frontend-ui.png)
   ![System info display](screenshots/parte3-system-info.png)

   ## Parte 4: Gestión de Versiones

   ### Este comando kubectl rollout undo nos sirve para revertir un despliegue a una versión anterior.


   ### Screenshots
   ![Rollback](screenshots/parte4-rollback.png)
   ![Rollforward](screenshots/parte4-rollforward.png)

   ## Parte 5: Ingress + MetalLB

   **IP del Ingress:** [Tu IP de MetalLB]

   ### Screenshots
   ![Ingress config](screenshots/parte5-ingress.png)
   ![Acceso externo](screenshots/parte5-external-access.png)

   ## Conclusiones

   ### Aprendizajes principales
   - [Punto 1]
   - [Punto 2]
   - [Punto 3]

   ### Dificultades encontradas
   - [Dificultad 1 y cómo la resolviste]
   - [Dificultad 2 y cómo la resolviste]

   ### Reflexión
   [¿Cómo aplicarías esto en un proyecto real?]
   ```