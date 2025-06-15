# ☁️ Cloud Cost Simulator

> A visual tool to simulate and estimate multi-cloud deployment costs using Docker, Kubernetes (Minikube), Terraform, and Streamlit.

This project enables users to interactively configure cloud infrastructure settings (like replicas, region, instance type, and storage) and view estimated monthly costs across AWS, GCP, and Azure — using mocked data for free, local simulation.

---

## 📸 Demo Screenshot

![Cloud Cost Simulator UI](dashboard/sample_ui.png)

---

## 🧱 Tech Stack

| Layer              | Tech Used                           |
| ------------------ | ----------------------------------- |
| Frontend           | Streamlit + Plotly (interactive UI) |
| Backend (Optional) | Flask (mocked API, not required)    |
| Infrastructure     | Terraform + Kubernetes (Minikube)   |
| Containerization   | Docker                              |
| Data               | Mocked JSON (AWS, GCP, Azure)       |
| CI/CD (Optional)   | GitHub Actions                      |

---

## 📁 Project Structure

```
cloud-cost-sim/
├── backend/
│   ├── api/
│   │   ├── mock_data/
│   │   │   ├── aws.json
│   │   │   ├── gcp.json
│   │   │   └── azure.json
│   │   └── cost_logic.py
│   └── app.py                  # Optional Flask backend (if needed)
│
├── dashboard/
│   ├── streamlit_app.py        # Main Streamlit frontend
│   ├── utils.py                # Shared logic for UI calculations
│   └── components/
│       ├── charts.py
│       └── form_inputs.py
│
├── infrastructure/
│   ├── main.tf                 # Terraform config for Minikube K8s resources
│   ├── variables.tf
│   ├── outputs.tf
│   └── helm_charts/            # Optional Helm charts
│       └── streamlit-chart/
│
├── docker/
│   ├── Dockerfile.streamlit    # For dashboard
│   ├── Dockerfile.backend      # Optional Flask backend
│   └── .dockerignore
│
├── k8s/
│   ├── streamlit-deployment.yaml
│   ├── streamlit-service.yaml
│   └── backend-deployment.yaml
│
├── scripts/
│   ├── init_minikube.sh
│   └── terraform_apply.sh
│
├── .github/
│   └── workflows/
│       └── ci.yml              # Optional CI pipeline
│
├── .env                        # For config (if needed)
├── requirements.txt
├── README.md
└── LICENSE
```

---

## 🚀 How to Run

### ✅ 1. Prerequisites

* Docker
* Minikube
* Terraform
* Python 3.9+
* (Optional) Helm

---

### 🧪 2. Local Setup (Streamlit)

```bash
cd dashboard/
pip install -r ../requirements.txt
streamlit run streamlit_app.py
```

---

### 🐳 3. Docker Compose (Optional)

```bash
# Build and run containers
docker-compose up --build
```

---

### ☕️ 4. Kubernetes via Minikube

```bash
cd scripts/
./init_minikube.sh

cd ../infrastructure/
terraform init && terraform apply
```

---

## 🌍 Use Case

* Estimate cloud deployment costs **without a live cloud account**
* Plan infrastructure in **multi-cloud environments**
* Train DevOps/MLOps professionals on cost-awareness and provisioning
* Integrate into **FinOps dashboards** or **training platforms**

---

## ✨ Features

* Multi-provider simulation (AWS, GCP, Azure)
* Real-time cost charts (Compute + Storage)
* UI-based config for instance type, replicas, storage, region
* Easily extendable to support real APIs or CI pipelines

---

## 🚣️ Roadmap (Planned Enhancements)

* 🔌 Integrate live cloud pricing APIs (e.g., AWS Pricing API)
* 📈 Add autoscaling simulation
* 🎛️ Enable cost comparison across regions/providers
* ☁️ Streamlit Cloud deployment (hosted demo)
* 🧐 MLOps version (model inference/training cost simulator)

---

## 📜 License

This project is licensed under the MIT License — see [`LICENSE`](LICENSE) for details.

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---

## 👩‍💻 Author

Made with ❤️ by **Ramya C**

* [GitHub](https://github.com/Ramyac24)
* [LinkedIn](https://linkedin.com/in/your-link) *(optional)*

---

> If you find this useful, leave a ⭐ on the repo!
