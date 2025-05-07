# 🌴 ExploreAI – Your AI Hotel Search Assistant

[🔗 Live Gradio App](https://0bb7afb06c4cd3e05e.gradio.live/) | [🔗 Google Colab](https://colab.research.google.com/drive/1tX_0wPEYNs_6mxJ_MTJTiU0UaiJxszCS?usp=sharing) | [🔗 Notion Documentation](https://www.notion.so/ExploreAI-Your-AI-Hotel-Search-Assistant-1ec176655a1f80969ce3ebd4d2f7394f?pvs=4)

---

## ✨ Credits

Special thanks to **Hamza** for teaching us AI concepts and handholding us throughout this journey to build this amazing AI-powered search prototype.

**Product Creation / Owner**: *Laahiri Gunda*

---

## 🧠 What is ExploreAI?

**ExploreAI** is your AI assistant to search for hotels in **Miami** that suit your specific requirements. Powered by AI intelligence, it:
- Provides natural language recommendations based on user queries.
- Shares relevant and verified hotel links to dive deeper into the recommendations.

---

## 👤 Who is it for?

This product is designed for **anyone searching for hotels in Miami** — whether you're looking for budget options, luxury stays, beach views, or even Indian cuisine!

---

## 🛠️ How is ExploreAI Built?

We followed a structured AI + ML pipeline to bring ExploreAI to life.

### 1. **Data Loading and Preprocessing**
- Loaded the Miami hotel dataset from [GitHub](https://raw.githubusercontent.com/hamzafarooq/maven-mlsystem-design-cohort-1/main/data/miami_hotels.csv).
- Cleaned the data by dropping columns with null values.
- Created `content` and `metadata` fields for further processing.

### 2. **Data Chunking and Embeddings**
- Used a `recursive_split` method to chunk the data into meaningful segments with chunk size: 1000 and overlap: 200 to preserve context.
- Created vector embeddings using `AutoTokenizer` and `AutoModel`.

### 3. **Store and Query Vector Embeddings**
- Stored embeddings in a **Qdrant vector database (in-memory version)** for fast retrieval.
- To persist across sessions, we saved vector data to **Google Drive**.
- This allows efficient offline access to embedding data.

![Stored Embeddings in Google Drive](attachment:c647387d-5471-4655-8b3d-9d47d1adc4e9:image.png)

### 4. **Implementing the RAG Pipeline**
- Connected the Qdrant client to the stored vectors.
- Integrated **OpenRouter** to serve as the LLM backend.
- Ensured embedding consistency by reusing the same model used for chunking.
- Created a retriever to fetch the most relevant results based on user query.

### 5. **Gradio Interface for ExploreAI**
- Built an interactive UI using [Gradio](https://www.gradio.app/).
- Used the `qwen/qwen3-8b:free` model to convert search results into conversational recommendations.
- Provided example queries to help users get started quickly.

---

## 🖼️ Demo Screenshots

### 🔍 Gradio Interface – ExploreAI in Action
![Gradio UI](attachment:e095fdbe-1f6c-4271-a452-fd129eda30b5:image.png)

---

### 🏨 Query: "Budget friendly hotels with Miami beach view and Indian food available"
![Recommendation Example](attachment:e8ee9f1b-ea2b-4fbf-a7a8-82a36a65caed:image.png)

---

### 🏩 Query: "Luxury hotels in Miami"
![Luxury Hotels](attachment:1177e83c-6bd9-4cb1-ac5d-d08a3ccda2b7:image.png)

---

## 📌 Tech Stack

- **Qdrant** – Vector DB for storing embeddings
- **Transformers (Hugging Face)** – For tokenization and embedding
- **OpenRouter** – LLM-based answer generation (Qwen-3-8B)
- **Gradio** – UI framework for interaction
- **Google Drive** – Persistent embedding storage

---

## 📥 Try it Yourself

Open in your browser: [ExploreAI Gradio App](https://0bb7afb06c4cd3e05e.gradio.live/)  
Or launch the notebook: [ExploreAI Colab Notebook](https://colab.research.google.com/drive/1tX_0wPEYNs_6mxJ_MTJTiU0UaiJxszCS?usp=sharing)

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change or improve.

---

## 📄 License

This project is built for educational and demo purposes. You are free to fork and extend it for learning.

---

