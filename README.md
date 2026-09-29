# Mini Recruitment Chatbot

A Google Colab notebook for an assignment on advanced prompt engineering. It builds a
recruitment assistant chatbot with LangChain and Google Gemini that:

- answers career questions in a friendly, concise tone (role prompting + few-shot examples)
- extracts candidate details (`name`, `desired_role`, `experience_years`) with **function / tool calling**
- returns clean **JSON** for HR-system integration and never invents missing details
- remembers the conversation with a **memory buffer**, so candidates don't have to repeat themselves
- optionally runs in a **Gradio** chat UI

## Run it

1. Open `recruitment_chatbot.ipynb` in [Google Colab](https://colab.research.google.com/) (*File → Upload notebook*).
2. Get a free Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey).
3. *Runtime → Run all*. Paste the key when prompted, or save it as a Colab secret named `GOOGLE_API_KEY`.

## Notebook sections

1. Install Libraries
2. Imports
3. API Key Setup & Connect to the LLM
4. Define the Recruitment Assistant Prompt (role + few-shot)
5. Define Candidate Information Schema (Pydantic)
6. Implement Function / Tool Calling (`extract_candidate_info`)
7. Add Conversational Memory
8. Build the Chatbot (`chatbot_response(message, session_id)`)
9. Test the Chatbot (safeguard checks plus live scenarios for career questions, extraction, memory, corrections, invented details and session isolation)
10. Optional Gradio Interface
11. Reflection

## Libraries

`langchain-core`, `langchain-google-genai`, and `gradio` (optional section only). The notebook
was written against langchain-core 1.6 and langchain-google-genai 4.4.
