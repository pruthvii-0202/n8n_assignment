# 🚀 n8n Workflow: Story → Prompt → Code → File Automation

## 📌 Overview

This project is an automated **n8n workflow** that transforms structured input data (from an Excel file) into:

1. AI-generated prompts
2. Converted executable code
3. Structured output files

It demonstrates an end-to-end pipeline using AI + automation to convert **business logic into code artifacts**.

---

## 🧠 Workflow Architecture

### 🔄 Flow Summary

1. **Trigger** → Manual execution
2. **Download File** → Fetch input dataset
3. **Extract from File (XLSX)** → Parse structured data
4. **Story to Prompt (AI)** → Convert input into prompts
5. **Prompt to Code (AI)** → Generate code from prompts
6. **IF Condition** → Validate generated output
7. **Code Processing (JavaScript)** → Format / refine code
8. **Convert to File (XLSX)** → Structure output
9. **Upload File** → Store final result

---

## ⚙️ Nodes Breakdown

### 🟢 Trigger

* Starts workflow manually using "Execute Workflow"

### 📥 Download File

* Retrieves input file (Excel/CSV)

### 📊 Extract from File

* Reads structured data (XLSX)
* Outputs multiple items for processing

### 🤖 Story_To_Prompt

* Uses AI model
* Converts raw input into structured prompts

### 💻 Prompt_To_Code

* Converts prompts into usable code snippets

### 🔀 IF Node

* Checks:

  * If code is generated successfully
  * Filters invalid outputs

### 🧾 Code in JavaScript

* Cleans / formats AI-generated code
* Can add validations or transformations

### 📁 Convert to File

* Converts processed data back into XLSX

### ☁️ Upload File

* Uploads final file to storage (e.g., Google Drive)

---

## 🛠️ Tech Stack

* **n8n** – Workflow automation
* **OpenAI / LLM APIs** – Prompt & code generation
* **JavaScript** – Data processing
* **Google Drive API** – File storage
* **XLSX Handling** – Data input/output

---

## 📂 Input Format

Example input (Excel):

| Story / Requirement |
| ------------------- |
| Create login API    |
| Build user model    |
| Add validation      |

---

## 📤 Output Format

Generated Excel:

| Prompt      | Code                    |
| ----------- | ----------------------- |
| Prompt text | Generated JS / API code |

---

## 🚀 How to Use

### 1. Import Workflow

* Open n8n
* Import JSON workflow

### 2. Configure Credentials

* Add:

  * OpenAI API Key
  * Google Drive credentials

### 3. Upload Input File

* Provide XLSX file with stories

### 4. Execute Workflow

* Click **Execute Workflow**

### 5. Get Output

* Processed file will be uploaded automatically

---

## 🧪 Use Cases

* 🧾 Convert business requirements into code
* ⚙️ Automate backend scaffolding
* 📊 AI-powered development pipelines
* 🧠 Prompt engineering workflows
* 👨‍💻 Internship/demo projects

---

## 🔥 Key Features

* End-to-end automation
* AI-driven transformation
* Scalable pipeline
* File-based processing
* Modular architecture

---

## ⚠️ Limitations

* AI output may require validation
* Depends on prompt quality
* Requires API keys

---

## 📌 Future Improvements

* Add error logging system
* Add retry mechanism
* Support multiple programming languages
* Add UI dashboard

---

## 👨‍💻 Author

**Pruthviraj Biradar**

---

## ⭐ Contribute

Feel free to fork, improve, and submit PRs!

---

## 📜 License

This project is open-source and available under the MIT License.
