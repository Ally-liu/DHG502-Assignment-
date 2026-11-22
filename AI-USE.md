# AI-USE

Assignment 2 — DHG 502. This disclosure follows the course-wide submission rules.

## 1. Tools and models used

- **OpenCode** (VS Code AI coding agent), model `opencode-go/deepseek-v4.1-flash`.
- **HistFig** (local FastAPI + SQLite), the RAG application used in the experiment.
- **`z-ai/glm-5.3-flash`** via OpenRouter, the chat model used for the conversations.
- **`BAAI/bge-m3`** (local `sentence-transformers`, 1024 dimensions), the embedding model used to rebuild the index.

The chat model and the embedding model are part of the experiment. OpenCode is the coding and editing assistant. They are different tools and are reported separately.

## 2. What the AI was used for

Coding, data handling, and language editing. The AI helped write and debug the Python scripts that exported the conversations, built `corpus/manifest.csv` and `evidence/error_log.csv`, checked part numbers, and generated the `.docx`. It also provided English language editing and translation for the authors' draft.

The research question, the five core questions, the verdicts, and the argument were set by the authors. The authors wrote and revised the essay and approved the final text. The AI did not choose the questions, the verdicts, or the interpretation.

## 3. Representative prompts / session excerpts

- "Parse the headers of the 54 corpus files and write `corpus/manifest.csv` with title, author, role, voice status, character counts, source URL, and `used_in_index`."
- "Build `evidence/error_log.csv` from the exported conversations. One row per exchange, with question, mode, error type, what happened, sources, verdict, and error layer."
- "Check every `part N` in the essay against the HistFig exports and list the mismatches. The exports are 1-based."
- "Generate an A4 DOCX from the Markdown: Times New Roman 12 pt, 1.5 spacing, one bordered settings table."
- "Read the five retrieved passages for the Zhu An question and confirm whether any of them actually supports the answer."

## 4. Important changes I made

- Chose Lu Xun as the figure, the 32 volumes used for the index, and the 22 memoirs excluded from it.
- Designed the five core questions, the May Fourth check, and the simple/agent comparison for the unemployment question.
- Read the retrieved passages and set the verdicts, including the iron-house success, the Fujino partial success, and the Zhu An clear failure.
- Corrected the part numbers from the earlier 0-based draft to the 1-based numbers in the HistFig exports.
- Revised the essay at the sentence level, checked the argument, and approved the final text.
- Checked the quotations against `evidence/` and checked the DOCX page count and word count before submission.

## 5. How I checked the AI's output

- Ran every script myself and read the output.
- Checked `corpus/manifest.csv`: 54 rows, 32 volumes marked `used_in_index = yes`, 22 marked `no`; the 32 indexed files total 2,629,782 characters.
- Checked `evidence/error_log.csv`: eight rows, with verdict and error layer filled for each exchange.
- Checked every `part N` against the exported conversations: Fujino 40, Zhu An 158, the iron-house passage in *Nanqiang Beidiao Ji* 17, and the *Erxin Ji* noise passage 92.
- Confirmed that `grep 朱安` returns 0 in the 32-volume corpus, read the five retrieved passages, and checked the Zhu An verdict against them.
- Read the KWIC and retrieved passages against the source text and checked the quoted lines used in the essay.
- Opened the final DOCX in Word: 1,905 words, 6 pages, one settings table. Checked the PDF as well, including the References section on page 6.
