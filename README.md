# Helpful-spaCy-Actions

A repository containing Jupyter notebooks for training and using custom spaCy models with focus on document processing and entity recognition. This project demonstrates how to train and use spaCy models for extracting information from structured documents like driving licenses.

## 🎯 Features

- Custom spaCy model training configuration
- Entity recognition for document processing
- Support for driving license document parsing
- Visualization using displaCy
- GPU-accelerated training support
- Configurable training parameters

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- Jupyter Notebook
- CUDA-capable GPU (optional, for faster training)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/SakibAhmedShuva/Helpful-spaCy-Actions.git
cd Helpful-spaCy-Actions
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

## 📖 Usage

The main notebook `spacy-actions.ipynb` contains several sections:

1. **Setup and Installation**: Initial package installation and imports
2. **Model Loading**: Loading pre-trained or custom spaCy models
3. **Document Processing**: Example text processing and entity recognition
4. **Training Configuration**: Both new training and continued training setups

### Training a New Model

```python
python -m spacy train config.cfg \
    --output ./output \
    --paths.train ./train.spacy \
    --paths.dev ./dev.spacy \
    --training.seed=101 \
    --training.patience=2000 \
    --gpu-id 0
```

### Continuing Training from Existing Model

```python
python -m spacy train config.cfg \
    --output ./output \
    --paths.train ./train.spacy \
    --paths.dev ./dev.spacy \
    --training.seed=101 \
    --training.patience=2000 \
    --gpu-id 0 \
    --components.transformer.source = /output/model-best
```

## 🎯 Entity Recognition

The model is trained to recognize various entities in documents, including:
- Document Numbers
- Dates (DOB, Issue Date, Expiration)
- Address Information
- License Classes
- Personal Information
- Restrictions

## ⚙️ Configuration Options

The training configuration supports various parameters:
- Batch size adjustment
- Gradient accumulation
- Training steps
- Evaluation frequency
- Model architecture customization

## 📊 Visualization

The project uses spaCy's displaCy for visualizing entity recognition results:

```python
displacy.serve(doc, style="ent")
```

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
