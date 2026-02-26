# JobApp - Full Stack Spring Boot & CI/CD Pipeline

<p align="center">
  <img src="images/web-app-preview.png" width="800" alt="Kushagra Job Portal Preview">
</p>

This project is a comprehensive **Job Portal Web Application** built using **Spring Boot** and managed with a professional **Jenkins CI/CD Pipeline**.

---

## 💻 Application Features & Architecture
* **MVC Architecture**: Model (`JobPost.java`), View (JSP), and Controller (`JobController.java`).
* **View Technologies**: Uses **JSP** with custom CSS (`style.css`, `style1.css`).
* **REST API**: `JobController` exposes endpoints for data access.

---

## ⚙️ DevOps & CI Pipeline
The project features a **Declarative Jenkins Pipeline**:
1. **Workspace Cleanup**: Uses `deleteDir()`.
2. **Build Stage**: Maven compiles the project.
3. **Test Stage**: Runs unit tests.
4. **Deliver Stage**: Executes `deliver.sh` to verify the `.jar`.

### Pipeline as Code
```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
```

---

## 📸 Pipeline Insights

### Status Dashboard
![Status](images/ci.png)

---

## 📊 Build Performance

| Metric | Value |
| :--- | :--- |
| **Total Build Time** | ~5 seconds |
| **Tests Run** | 1 |
| **Build Status** | **SUCCESS** |

---

**Author:** Kushagra  
*DevOps & Full Stack Enthusiast*


