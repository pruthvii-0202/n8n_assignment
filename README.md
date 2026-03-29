# 🚀 n8n AI Workflow: Story → Prompt → Code Automation

## 📌 Overview

This project is an **AI-powered n8n workflow** that automates the transformation of structured business inputs into working code.

It reads data from an Excel file, generates prompts using AI, converts them into code, processes the results, and exports them back into a structured file.

---

## 🧠 Workflow Architecture

### 🔄 Flow Pipeline

1. **Manual Trigger** → Start workflow
2. **Download File** → Fetch input dataset
3. **Extract from XLSX** → Parse structured data
4. **Story → Prompt (AI)** → Convert input into prompts
5. **Prompt → Code (AI)** → Generate code
6. **Validation Layer (Important)** → Ensure valid output
7. **JavaScript Processing** → Clean & format code
8. **Convert to XLSX** → Structure results
9. **Upload File** → Store final output

---

## ⚠️ Important: Validation Layer

This workflow **requires validation before processing AI output**.

### Why?

AI responses can sometimes be:

* Empty
* Undefined
* Incorrect format

Without validation, the workflow may break.

---

### ✅ Recommended Approach (IF Node)

Use an **IF node** after `Prompt_To_Code`:

**Condition:**

```
{{$json["text"] !== ""}}
```

**Flow:**

* ✅ TRUE → Continue to JavaScript processing
* ❌ FALSE → Skip item

---

### 🔁 Alternative Approach (JavaScript Validation)

If not using IF node, handle validation inside JS node:

```js
if (!$json.text || $json.text.trim() === "") {
  return []; // Skip invalid outputs
}

return {
  code: $json.text
};
```

---

## ⚙️ Nodes Breakdown

### 🟢 Trigger

Starts the workflow manually.

### 📥 Download File

Fetches input Excel file.

### 📊 Extract from File

Parses XLSX into structured items.

### 🤖 Story_To_Prompt

Transforms input data into AI prompts.

### 💻 Prompt_To_Code

Generates code using AI.

### 🔍 Validation Layer

Ensures only valid outputs proceed.

### 🧾 Code in JavaScript

* Cleans generated code
* Formats output
* Handles edge cases

### 📁 Convert to File

Creates structured XLSX output.

### ☁️ Upload File

Uploads result to storage (e.g., Google Drive).

---

## 🛠️ Tech Stack

* **n8n** – Workflow automation
* **OpenAI / LLM APIs** – AI generation
* **JavaScript** – Processing logic
* **Google Drive API** – File storage
* **XLSX Handling** – Data parsing

---

## 📂 Input Format

| Story / Requirement |
| ------------------- |
| Create login API    |
| Add authentication  |
| Build user model    |

---

## 📤 Output Format

| Prompt           | Code           |
| ---------------- | -------------- |
| Generated prompt | Generated code |

---

## 🚀 How to Use

### 1. Import Workflow

* Open n8n
* Import workflow JSON

### 2. Configure Credentials

* Add OpenAI API key
* Add Google Drive credentials

### 3. Provide Input File

* Upload XLSX with requirements

### 4. Execute Workflow

* Click **Execute Workflow**

### 5. Get Output

* File is automatically uploaded

---

## 🧪 Use Cases

* ⚙️ Generate backend code from requirements
* 🤖 AI-powered development automation
* 📊 Batch prompt engineering
* 🎓 Internship/demo projects

---

## 🔥 Key Features

* End-to-end automation
* AI-driven transformation
* Scalable workflow
* Error-safe processing
* File-based pipeline

---

## 📌 Future Improvements

* Add logging system
* Retry failed AI calls
* Multi-language code generation
* UI dashboard

---

## 👨‍💻 Author

**Pruthviraj Biradar**

---

## ⭐ Contribute

Pull requests are welcome!

---

## 📜 License

MIT License
