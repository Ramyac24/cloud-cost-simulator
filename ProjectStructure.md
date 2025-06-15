Project structure

Project structure

cloud-cost-simulator/
├── backend/
│   ├── api/
│   │   ├── mock_data/
│   │   │   ├── aws.json
│   │   │   ├── gcp.json
│   │   │   └── azure.json
│   │   └── cost_logic.py
│   └── app.py                 
│
├── dashboard/
│   ├── streamlit_app.py        
│   ├── utils.py               
│   └── components/
│       ├── charts.py
│       └── form_inputs.py
│
├── infrastructure/
│   ├── main.tf                 
│   ├── variables.tf
│   ├── outputs.tf
│   └── helm_charts/            
│       └── streamlit-chart/
│
├── docker/
│   ├── Dockerfile.streamlit   
│   ├── Dockerfile.backend      
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
│       └── ci.yml              
│
├── .env                       
├── requirements.txt
├── README.md
└── LICENSE
