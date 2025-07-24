![Screenshot 2024-11-04 191248](https://github.com/user-attachments/assets/fdb8636d-3767-4b2d-97f5-0a2e8a300a3b)

# AI-Powered Web Scraper

This AI-powered web scraping tool enables users to extract data from web pages based on specific tags or structures. The application is built using Streamlit for the user interface, Selenium for web automation, and OpenAI for intelligent parsing. This tool allows users to extract structured information, including pagination handling, and export data in JSON or CSV formats.

-----

## **Features**

  * **Automated Web Scraping:** Uses Selenium to automate the extraction of HTML content from a given URL.
  * **AI-Powered Data Extraction:** Leverages OpenAI's GPT-4o-mini model to intelligently extract and structure data from the raw HTML content.
  * **Data Structuring:** Enables users to define specific tags or fields to target in the scraped data, making data extraction flexible and tailored.
  * **Pagination Support:** Detects and navigates pagination links automatically, allowing continuous scraping across multiple pages.
  * **Data Export**: Supports exporting data in JSON or CSV formats for easy download.
  * **User-friendly Interface:** Built with Streamlit, offering a clear and interactive interface.

-----

## **Requirements**

Ensure that the following dependencies are listed in your `requirements.txt`:

  * beautifulsoup4
  * groq
  * html2text
  * html5lib
  * langchain
  * langchain\_community
  * langchain\_openai
  * lxml
  * openai
  * openpyxl
  * pandas
  * pydantic
  * python-dotenv
  * readability-lxml
  * requests
  * selenium
  * streamlit
  * streamlit-tags
  * webdriver\_manager

-----

## **Getting Started**

### **1. Clone the Repository**

```bash
git clone <repository-url>
```

### **2. Set Up Environment Variables**

Create a `.env` file in the root directory of the project:

```plaintext
OPENAI_API_KEY=your_openai_api_key
```

Replace `your_openai_api_key` with your actual OpenAI API key.

### **3. Install Dependencies**

Make sure you have Python and pip installed. Install all dependencies from `requirements.txt`:

```bash
pip install -r requirements.txt
```

### **4. Start the Application**

In the command prompt or terminal, run the following command to start the Streamlit application:

```bash
streamlit run app.py
```

-----

## **How It Works**

### **1. Scraping and Parsing**

The application uses **Selenium** to fetch the raw HTML from the provided URL. The HTML is then converted to **Markdown** to create a clean, text-based representation of the page content.

### **2. AI-Powered Data Extraction**

The Markdown content is then passed to an **OpenAI GPT model** with a system message that primes it to act as a web scraper. The user provides tags (e.g., "product\_name", "price", "description"), and the AI extracts the corresponding information from the text.

### **3. Handling Pagination**

If pagination is enabled, the application uses another call to the OpenAI API with a specialized prompt to identify and extract all pagination URLs from the initial page's content. This allows the scraper to navigate through multiple pages and gather all relevant data.

### **4. Data Output**

The extracted data is presented in a clean, tabular format within the Streamlit interface and can be downloaded as a **JSON** or **CSV** file.

