## 📄 README.md - DevOps Pipeline: Kryptovalutaanalys (AF10)

Detta projekt implementerar en **DevOps CI/CD-pipeline** för en Python/Streamlit-baserad webbapplikation. Applikationen hanterar kryptovalutadata och bygger på min **individuella pipeline-implementering** på branchen **`AF10`**.

### 1. ⚙️ Teknisk Översikt

| Komponent | Teknik | Status i Pipeline |
| :--- | :--- | :--- |
| **Applikation** | Python / Streamlit | Körs lokalt via `streamlit run app/app.py`. |
| **CI/CD-plattform** | GitHub Actions | Flödet körs vid `push` till `AF10`. |
| **Containerisering** | Docker | Image pushas till Docker Hub: `abbbbe/devops-crypto-app`. |
| **Kvalitetssäkring** | Pytest | Tester körs som en kvalitetsspärr. |

### 2. 🛠️ Kom igång (Lokal Körning)

Följ dessa steg för att köra applikationen lokalt (från projektets rotkatalog):

1.  **Aktivera Virtuell Miljö:** `source venv/bin/activate`
2.  **Installera Dependencies:** `pip install -r requirements.txt`
3.  **Kör Applikationen:** `streamlit run app/app.py`
    *(Obs: Felsökning av imports kräver kommandot `python -m app.app`)*

### 3. 🚀 CI/CD Pipeline (AF10)

Pipelinen **`AF10_pipeline.yml`** har en **sekventiell** struktur för att säkerställa kvalitet och spårbarhet.

| Jobb | Syfte | Logik |
| :--- | :--- | :--- |
| **1. tests** | Kör Unit- och Integrationstester. | Avbryter pipelinen vid fel. |
| **2. build** | Bygger Docker-imagen och pushar till Docker Hub. | **Körs endast om** `tests` är **godkänt** (`needs: tests`). |
| **3. deploy** | Simulerad distribution till Azure App Service. | **Körs endast om** `build` är **godkänt** (`needs: build`). |

### 4. 🔗 Viktiga Länkar (Inlämning)

* **Branch för inlämning:** [Länk till din AF10-branch]
* **Workflow-fil:** [Länk till din AF10_pipeline.yml-fil]
* **Deployad Applikation (Mål):** `https://af10-devops-crypto.azurewebsites.net`
    *(**Viktigt:** Denna länk är fiktiv och representerar det tänkta deploy-målet. Distributionen är **simulerad** i pipelinen.)*