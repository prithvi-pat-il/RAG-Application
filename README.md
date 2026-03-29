# 📄 Chat with Your PDFs (RAG Application)

Hey there! 👋 Welcome to my **Retrieval-Augmented Generation (RAG)** application.

Have you ever stared down a massive, 100-page PDF document and wished you could just *ask* it exactly what you're looking for instead of reading the whole thing? That's exactly why I built this tool. 

This app lets you upload multiple PDF files and have a totally natural conversation with them. It reads the documents, stores the context, and uses Google's powerful Gemini AI to answer your questions as precisely as possible. No more scrolling forever—just ask, and it answers! 🚀

---

## 🛠️ How It Works Behind the Scenes

When you give this app your PDFs, a few magical things happen behind the scenes:
1. **Reading the Pages:** The app uses `PyPDF2` to read through all the uploaded documents and pull out every single line of text.
2. **Breaking it Down:** Because AI models get overwhelmed if you give them a whole book at once, I use **LangChain** to split all that text into bite-sized chunks.
3. **Building the Memory:** Those chunks are passed to **Google Generative AI Embeddings**, which turns the text into numbers (vectors), and we store those in a super-fast database called **FAISS**.
4. **Getting Your Answers:** When you type a question, the app searches FAISS for the most relevant chunks of text, hands them over to the **Gemini 2.5 Flash** model, and returns a fully comprehensive answer based *only* on the PDFs you provided!

---

## 💻 Want to run this yourself? 

Awesome! Getting this to work on your own machine is pretty simple. Here is what you need to do:

### 1. Clone the Code
First things first, bring the code down to your computer:
```bash
git clone https://github.com/prithvi-pat-il/RAG-Application.git
cd RAG-Application
```

### 2. Set Up a Virtual Environment (Optional, but highly recommended)
It's always good to keep things neat and separated:
```bash
python -m venv myenv
# For Windows:
myenv\Scripts\activate
# For Mac/Linux:
source myenv/bin/activate
```

### 3. Install the Required Magic Spells (Dependencies)
```bash
pip install -r requirements.txt
```

### 4. Provide Your API Key
The app needs to talk to Google to use the Gemini model. 
Create a new file called `.env` in the main folder of the project, and drop your API key in there like this:
```env
GOOGLE_API_KEY=your_actual_google_gemini_api_key_goes_here
```

### 5. Fire it Up! 🔥
You're all set. Run the Streamlit app with this command:
```bash
streamlit run app.py
```
A browser window should pop open, and you can start uploading your PDFs and chatting away!

---

**Built with ❤️ and a whole bunch of coffee.** Feel free to fork it, break it, and make it better! If you run into issues, well—that's just part of the developer journey, right? Let me know!
