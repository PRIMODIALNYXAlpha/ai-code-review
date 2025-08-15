 

# AI Code Review App with DeepSeek

A React-based code editor and AI assistant that allows developers to **review** and **fix** code using DeepSeek AI. Supports multiple programming languages and provides detailed suggestions, bug detection, and optimized code generation.

---

## Table of Contents

* [Demo](#demo)
* [Features](#features)
* [Tech Stack](#tech-stack)
* [Installation](#installation)
* [Usage](#usage)
* [Supported Languages](#supported-languages)
* [Folder Structure](#folder-structure)
* [Example AI Response](#example-ai-response)
* [API Configuration](#api-configuration)
* [Future Improvements](#future-improvements)
* [License](#license)

---

 
## Features

* **AI Code Review**: Get detailed feedback on code quality, best practices, and potential bugs.
* **AI Code Fix**: Automatically generate optimized, error-free code with explanations.
* **Multi-language Support**: Works with 20+ programming languages.
* **Live Editor**: Built with Monaco Editor for syntax highlighting.
* **Markdown Response**: AI output rendered in Markdown.
* **Loading Indicator**: Spinner while AI processes requests.

---

## Tech Stack

* **Frontend**: React, React Select, React Markdown, Monaco Editor
* **AI Integration**: DeepSeek AI API
* **Styling**: Tailwind CSS / Custom CSS
* **Loader**: react-spinners (RingLoader)

---

## Installation

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/ai-code-review.git
cd ai-code-review
```

2. **Install dependencies**

```bash
npm install
```

3. **Run the app**

```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Usage

1. **Select Language**: Choose the programming language from the dropdown.
2. **Write or Paste Code**: Enter your code in the Monaco Editor.
3. **Review Code**: Click the **Review** button to get AI feedback.
4. **Fix Code**: Click the **Fix Code** button to automatically generate optimized code.
5. **View Response**: AI feedback appears in the right panel in Markdown format.

---

## Supported Languages

* JavaScript, Python, Java, C#, C++, PHP, Ruby, Go, Swift, Kotlin, TypeScript, Rust, Dart, Scala, Perl, Haskell, Elixir, R, MATLAB, Bash

---

## Folder Structure

```
ai-code-review/
├── public/
├── src/
│   ├── components/
│   │   └── Navbar.jsx
│   ├── App.jsx
│   ├── App.css
│   └── index.js
├── package.json
├── README.md
└── screenshots/       # Add screenshots here
```

---

## Example AI Response

**Original Code (JavaScript):**

```javascript
function sum(a, b) {
  return a + b;
}
console.log(sum(5, "3"));
```

**AI Review Response:**

* **Quality Rating**: Normal
* **Suggestions**: Use type checking to avoid string concatenation issues.
* **Potential Bugs**: Passing a string will concatenate instead of sum.
* **Fix Recommendation**: Ensure both arguments are numbers.

**AI Fixed Code:**

```javascript
function sum(a, b) {
  if (typeof a !== 'number' || typeof b !== 'number') {
    throw new Error('Both arguments must be numbers');
  }
  return a + b;
}
console.log(sum(5, 3));
```

---

## API Configuration

1. **DeepSeek API Key**

Replace in `App.jsx`:

```js
const DEEPSEEK_API_KEY = "YOUR_API_KEY_HERE";
```

2. **Endpoints**

* Review: `POST https://api.deepseek.ai/v1/code-review`
* Fix: `POST https://api.deepseek.ai/v1/code-fix`

3. **Instructions**

The app sends code and instructions to DeepSeek AI to generate review or fixed code.

---

## Future Improvements

* Real-time AI review as you type
* Dark/light theme toggle
* User authentication & saved session history
* Download AI-reviewed or fixed code
* Multi-tab code editing

---

## License

This project is licensed under the MIT License.

 
