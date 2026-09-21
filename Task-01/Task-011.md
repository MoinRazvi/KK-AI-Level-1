Task-1 The `xfusion` AI Engineering team is developing tools to improve the clarity of developer-reported bugs. Developers often report issues informally, which makes them difficult to understand or reproduce.

You are tasked to build a Python-based **AI Bug Description Clarifier** that transforms such informal bug reports into clear, structured, and professional issue summaries.

Inside `/root/openaiproject/bug_clarifier.py`:

1. Initialize the `OpenAI` client using environment values (`api_key` and `base_url`).
2. Define a function `clarify_bug(description: str) -> str` that builds a **parameterized prompt** to rewrite the raw bug description.
3. Send this prompt to the **OpenAI Chat Completion API**.
4. Use the following configuration for the API call:
   - **model**: `openai/gpt-4.1-mini`
   - **messages**: user → the constructed prompt
   - **max_tokens**: `100`
   - **temperature**: `0.0`
5. Use the input bug report:

```text
  App keeps crashing when I click save.
```

6. Store the AI response in a variable named `response` and print the clarified bug summary to the console.

**Notes:**

1. Function must use the developer's input description dynamically in the prompt.
2. Ensure you are working inside `/root/openaiproject`.
3. OpenAI credentials are available in `/root/.bash_profile`.
4. Use hardcoded values for `api_key` and `base_url` when initializing the `OpenAI client` or read them from environment variables via `os.environ.get('OPENAI_API_KEY')` and `os.environ.get('OPENAI_API_BASE')`.
5. Before running `bug_clarifier.py`, set up a virtual environment:

```bash
python3 -m venv venv && source venv/bin/activate && pip install openai
```

5. Maximum of **10 API requests** allowed before rate limiting.
