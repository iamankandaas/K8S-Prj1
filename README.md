# 🧭 Kubernetes Mini Project – Project Flow

### ✅ **1. Prerequisites**

* Install and start **Docker Desktop**
* Sign in to **Docker Hub**
* Install **Minikube**

---

### 🛠 **2. Build the Application**

* Create or use an existing app (e.g., Flask/Node)
* Test it locally

---

### 🧱 **3. Containerize the App with Docker**

* Create a `Dockerfile`
* Build and tag the image:

  ```bash
  docker build -t kubernetes-test-app:latest .
  ```
* Run and test the image locally:

  ```bash
  docker run -p 5000:5000 kubernetes-test-app:latest
  ```

---

### 📦 **4. Load Image to Minikube**

* Start Minikube:

  ```bash
  minikube start
  ```
* Load the local Docker image:

  ```bash
  minikube image load kubernetes-test-app:latest
  ```

---

### 📜 **5. Create Kubernetes Manifests**

* Define `deployment.yaml` with the container spec and replicas
* Optionally create `service.yaml` to expose the app

---

### 🚀 **6. Deploy to Kubernetes**

* Apply manifests:

  ```bash
  kubectl apply -f deployment.yaml
  ```
* Check status:

  ```bash
  kubectl get pods
  kubectl get services
  ```

---

### 🌐 **7. Access the Application**

* Expose via NodePort or use:

  ```bash
  minikube service kubernetes-test-app
  ```
* View live via Minikube Dashboard:

  ```bash
  minikube dashboard
  ```

---

### 🧪 **8. Load Testing (Optional)**

* Use **Postman** for performance testing

  * Run collection with fixed virtual users
  * Monitor response times under load

---

### 🛠 **9. Debugging**

* View logs:

  ```bash
  kubectl logs <pod-name>
  ```
* Inspect endpoints:

  ```bash
  kubectl get endpoints
  ```

---

### 🧹 **10. Cleanup**

* Stop Minikube:

  ```bash
  minikube stop
  ```
* Delete deployment:

  ```bash
  kubectl delete deployment kubernetes-test-app
  ```

---

### 💡 Tip: Handle ImagePullBackOff

If using Docker Hub:

```bash
docker tag kubernetes-test-app:latest <your-username>/kubernetes-test-app:latest
docker push <your-username>/kubernetes-test-app:latest
```

Update `deployment.yaml` to use the pushed image.

---
