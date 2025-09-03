# Variant Analysis EVO2

A web application for predicting the pathogenicity of DNA mutations using the state-of-the-art EVO2 large language model.

## Overview

This project provides an AI-powered tool to analyze DNA mutations and predict their potential to cause diseases. The application uses the EVO2 model to classify single nucleotide variants (SNVs) as pathogenic or benign, and compares predictions with existing ClinVar classifications.

**What it does:** DNA mutations are changes in genetic code that can affect health. This tool helps researchers and clinicians assess how harmful specific mutations might be by leveraging advanced AI models trained on genomic data.

## Features

### Core Functionality
- **Variant Effect Prediction**: Uses EVO2 model to predict pathogenicity of mutations
- **Pathogenicity Classification**: Classifies variants as pathogenic or benign
- **Comparison Analysis**: Compare EVO2 predictions with ClinVar classifications
- **Confidence Scoring**: Provides confidence estimates for predictions

### User Interface
- **Genome Browser**: Select genome assemblies (e.g., hg38) and browse chromosomes
- **Gene Search**: Search for specific genes (e.g., BRCA1) or browse by location
- **Reference Sequences**: View full reference genome sequences via UCSC API
- **Variant Explorer**: Browse known variants from NCBI ClinVar database
- **Responsive Design**: Modern web interface built with Next.js and Tailwind CSS

### Technical Features
- **GPU Acceleration**: H100 GPU-powered inference via Modal platform
- **FastAPI Backend**: RESTful API for variant analysis
- **Real-time Analysis**: Fast mutation scoring and classification

## Technology Stack

### Backend
- **Python 3.10**: Core programming language
- **FastAPI**: Web framework for API development
- **Modal**: Serverless GPU deployment platform
- **EVO2 Model**: State-of-the-art genomic language model
- **PyTorch**: Machine learning framework

### Frontend
- **Next.js**: React-based web framework
- **TypeScript**: Type-safe JavaScript
- **Tailwind CSS**: Utility-first CSS framework
- **Shadcn UI**: Modern component library

### External APIs
- **UCSC Genome Browser API**: Reference genome sequences
- **NCBI ClinVar/E-utilities**: Variant and gene information

## About EVO2 Model

EVO2 is a large language model specifically designed for genomic sequence analysis. It has been trained on vast amounts of genomic data and can predict the effects of genetic variants.

**Resources:**
- [Research Paper](https://www.biorxiv.org/content/10.1101/2025.02.18.638918v1)
- [Original Repository](https://github.com/ArcInstitute/evo2)

## Installation & Setup

### Prerequisites
- **Python 3.10** or higher
- **Node.js** (latest LTS version)
- **Modal account** (for GPU deployment)

### 1. Clone Repository
```bash
git clone https://github.com/Rakabi007/variant-analysis-evo2.git
cd variant-analysis-evo2
```

### 2. Backend Setup
```bash
# Navigate to backend
cd evo2-backend

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Setup Modal (follow prompts for authentication)
modal setup

# Test deployment
modal run main.py

# Deploy to production
modal deploy main.py
```

### 3. Frontend Setup
```bash
# Navigate to frontend
cd evo2-frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

### 4. Access Application
- **Frontend**: http://localhost:3000
- **Backend API**: Deployed Modal endpoint URL

## Usage

1. **Select Genome Assembly**: Choose your reference genome (e.g., hg38)
2. **Find Gene**: Search for genes by name or browse chromosomes
3. **View Sequence**: Examine the reference genome sequence
4. **Analyze Variants**: 
   - Input custom mutations
   - Browse known variants from ClinVar
   - Compare AI predictions with clinical classifications
5. **Review Results**: Examine pathogenicity predictions and confidence scores

## Project Structure

```
variant-analysis-evo2/
├── evo2-backend/          # Python FastAPI backend
│   ├── evo2/             # Core EVO2 model integration
│   ├── main.py           # Modal deployment entry point
│   └── requirements.txt  # Python dependencies
├── evo2-frontend/         # Next.js frontend application
│   ├── src/              # Source code
│   ├── components/       # React components
│   └── package.json      # Node.js dependencies
└── README.md             # This file
```

## Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE.MD](LICENSE.MD) file for details.

## Acknowledgments

- EVO2 model by Arc Institute
- UCSC Genome Browser for reference sequences
- NCBI ClinVar for variant classifications
