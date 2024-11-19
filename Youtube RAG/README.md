# YouTube RAG System

This project implements a Retrieval-Augmented Generation (RAG) system for YouTube videos. It allows you to extract transcripts from YouTube videos, process them, and create a question-answering system based on the video content.

## Features

- Extract transcripts from YouTube videos
- Process and chunk transcripts for optimal retrieval
- Store embeddings in ChromaDB vector database
- Question-answering capability using the stored knowledge
- MLflow experiment tracking and logging
- Comprehensive RAG evaluation metrics
- Real-time monitoring and drift detection

## Setup

1. Install the required dependencies:
```bash
pip install -r requirements.txt
```

2. Create a `.env` file in the project root and add your OpenAI API key:
```
OPENAI_API_KEY=your_api_key_here
```

3. Launch Jupyter Notebook:
```bash
jupyter notebook
```

4. Choose one of the following notebooks:
   - `youtube_rag.ipynb`: Basic RAG implementation
   - `youtube_rag_mlflow.ipynb`: RAG implementation with MLflow tracking
   - `youtube_rag_evaluation.ipynb`: Comprehensive RAG system evaluation
   - `youtube_rag_monitoring.ipynb`: MLflow model deployment with monitoring

## Usage

1. Replace the example YouTube URLs in the notebook with your desired videos:
```python
youtube_urls = [
    "https://www.youtube.com/watch?v=your_video_id1",
    "https://www.youtube.com/watch?v=your_video_id2"
]
```

2. Run all cells in the notebook to process the videos and create the RAG system.

3. Use the `ask_question()` function to query information from the videos:
```python
question = "What are the main topics discussed in these videos?"
ask_question(question)
```

## MLflow Integration

The `youtube_rag_mlflow.ipynb` notebook includes comprehensive experiment tracking with MLflow:

### Tracked Parameters
- Chunk size and overlap
- Number of videos processed
- Retriever configuration
- Model temperature

### Tracked Metrics
- Video processing time
- Word and segment counts
- Number of chunks
- Average chunk length
- Question-answering response times

### Tracked Artifacts
- Video metadata CSV
- Question-answer results JSON

View the MLflow UI to analyze experiments:
```bash
mlflow ui
```

## Evaluation Metrics

The `youtube_rag_evaluation.ipynb` notebook provides comprehensive evaluation of the RAG system:

### Retrieval Metrics
- Context Relevancy: Measures how well the retrieved contexts match the query
- Retrieval Precision: Accuracy of retrieved documents

### Generation Metrics
- Answer Relevancy: How well the generated answer addresses the question
- Faithfulness: Consistency between answer and source context
- ROUGE Scores: Text overlap metrics (ROUGE-1, ROUGE-2, ROUGE-L)
- BERTScore: Semantic similarity using BERT embeddings

### Performance Metrics
- Response Time: Time taken to generate answers
- System Resource Usage
- Batch Processing Efficiency

### Visualization
- Metric distributions
- Performance trends
- Error analysis

## Monitoring System

The `youtube_rag_monitoring.ipynb` notebook sets up real-time monitoring:

### System Monitoring
- Request/response metrics
- Error tracking
- Resource utilization
- Response time distribution

### Quality Monitoring
- Answer relevance tracking
- Context quality metrics
- Input/output distributions
- Data drift detection

### Visualization Dashboards
- Streamlit real-time dashboard
- Prometheus metrics endpoint
- MLflow experiment tracking
- Evidently data quality reports

### Setup Instructions

1. Start the monitoring services:
```bash
# Start Streamlit dashboard
streamlit run monitoring_dashboard.py

# View Prometheus metrics
curl localhost:8000/metrics

# Access MLflow UI
mlflow ui
```

2. Monitor the system through:
- Streamlit dashboard: Real-time metrics and trends
- Prometheus endpoint: Raw metrics for custom monitoring
- MLflow UI: Experiment tracking and model versions
- Evidently reports: Data quality and drift detection

## Notes

- The system requires videos to have available transcripts
- Processing time depends on the number and length of videos
- The ChromaDB database is persisted locally in the `./chroma_db` directory
- MLflow data is stored in the `mlruns` directory
- Evaluation results are saved as CSV files and visualizations
- Monitoring metrics are available through multiple interfaces
