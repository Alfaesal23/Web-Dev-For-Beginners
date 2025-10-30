# AI Framework

Ever felt overwhelmed trying to build AI applications from scratch? You're not alone! AI frameworks are like having a Swiss Army knife for AI development - they're powerful tools that can save you time and headaches when building intelligent applications. Think of an AI framework as a well-organized library: it provides pre-built components, standardized APIs, and smart abstractions so you can focus on solving problems instead of wrestling with implementation details.

In this lesson, we'll explore how frameworks like LangChain can turn what used to be complex AI integration tasks into clean, readable code. You'll discover how to tackle real-world challenges like keeping track of conversations, implementing tool calling, and juggling different AI models through one unified interface.

By the time we're done, you'll know when to reach for frameworks instead of raw API calls, how to use their abstractions effectively, and how to build AI applications that are ready for real-world use. Let's explore what AI frameworks can do for your projects.

## ⚡ What You Can Do in the Next 5 Minutes

**Quick Start Pathway for Busy Developers**

```mermaid
flowchart LR
    A[⚡ 5 minutes] --> B[Install LangChain]
    B --> C[Create ChatOpenAI client]
    C --> D[Send first prompt]
    D --> E[See framework power]
```

- **Minute 1**: Install LangChain: `pip install langchain langchain-openai`
- **Minute 2**: Set up your GitHub token and import the ChatOpenAI client
- **Minute 3**: Create a simple conversation with system and human messages
- **Minute 4**: Add a basic tool (like an add function) and see AI tool calling
- **Minute 5**: Experience the difference between raw API calls and framework abstraction

**Quick Test Code**:
```python
from langchain_openai import ChatOpenAI
from langchain_core.messages import SystemMessage, HumanMessage

llm = ChatOpenAI(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="openai/gpt-4o-mini"
)

response = llm.invoke([
    SystemMessage(content="You are a helpful coding assistant"),
    HumanMessage(content="Explain Python functions briefly")
])
print(response.content)
```

**Why This Matters**: In 5 minutes, you'll experience how AI frameworks transform complex AI integration into simple method calls. This is the foundation that powers production AI applications.

## Why choose a framework?

So you're ready to build an AI app - awesome! But here's the thing: you've got several different paths you can take, and each one has its own pros and cons. It's kind of like choosing between walking, biking, or driving to get somewhere - they'll all get you there, but the experience (and effort) will be totally different.

Let's break down the three main ways you can integrate AI into your projects:

| Approach | Advantages | Best For | Considerations |
|----------|------------|----------|--------------|
| **Direct HTTP Requests** | Full control, no dependencies | Simple queries, learning fundamentals | More verbose code, manual error handling |
| **SDK Integration** | Less boilerplate, model-specific optimization | Single-model applications | Limited to specific providers |
| **AI Frameworks** | Unified API, built-in abstractions | Multi-model apps, complex workflows | Learning curve, potential over-abstraction |

### Framework Benefits in Practice

```mermaid
graph TD
    A[Your Application] --> B[AI Framework]
    B --> C[OpenAI GPT]
    B --> D[Anthropic Claude]
    B --> E[GitHub Models]
    B --> F[Local Models]
    
    B --> G[Built-in Tools]
    G --> H[Memory Management]
    G --> I[Conversation History]
    G --> J[Function Calling]
    G --> K[Error Handling]
```

**Why frameworks matter:**
- **Unifies** multiple AI providers under one interface
- **Handles** conversation memory automatically
- **Provides** ready-made tools for common tasks like embeddings and function calling
- **Manages** error handling and retry logic
- **Turns** complex workflows into readable method calls

> 💡 **Pro Tip**: Use frameworks when switching between different AI models or building complex features like agents, memory, or tool calling. Stick with direct APIs when learning the basics or building simple, focused applications.

**Bottom line**: Like choosing between a craftsman's specialized tools and a complete workshop, it's about matching the tool to the task. Frameworks excel for complex, feature-rich applications, while direct APIs work well for straightforward use cases.

## 🗺️ Your Learning Journey Through AI Framework Mastery

```mermaid
journey
    title From Raw APIs to Production AI Applications
    section Framework Foundations
      Understand abstraction benefits: 4: You
      Master LangChain basics: 6: You
      Compare approaches: 7: You
    section Conversation Systems
      Build chat interfaces: 5: You
      Implement memory patterns: 7: You
      Handle streaming responses: 8: You
    section Advanced Features
      Create custom tools: 6: You
      Master structured output: 8: You
      Build document systems: 8: You
    section Production Applications
      Combine all features: 7: You
      Handle error scenarios: 8: You
      Deploy complete systems: 9: You
```

**Your Journey Destination**: By the end of this lesson, you'll have mastered AI framework development and be able to build sophisticated, production-ready AI applications that rival commercial AI assistants.

## Introduction

In this lesson, we'll learn to:

- Use a common AI framework.
- Address common problems like chat conversations, tool usage, memory and context.
- Leverage this to build AI apps.

## 🧠 AI Framework Development Ecosystem

```mermaid
mindmap
  root((AI Frameworks))
    Abstraction Benefits
      Code Simplification
        Unified APIs
        Built-in Error Handling
        Consistent Patterns
        Reduced Boilerplate
      Multi-Model Support
        Provider Agnostic
        Easy Switching
        Fallback Options
        Cost Optimization
    Core Components
      Conversation Management
        Message Types
        Memory Systems
        Context Tracking
        History Persistence
      Tool Integration
        Function Calling
        API Connections
        Custom Tools
        Workflow Automation
    Advanced Features
      Structured Output
        Pydantic Models
        JSON Schemas
        Type Safety
        Validation Rules
      Document Processing
        Embeddings
        Vector Stores
        Similarity Search
        RAG Systems
    Production Patterns
      Application Architecture
        Modular Design
        Error Boundaries
        Async Operations
        State Management
      Deployment Strategies
        Scalability
        Monitoring
        Performance
        Security
```

**Core Principle**: AI frameworks abstract complexity while providing powerful abstractions for conversation management, tool integration, and document processing, enabling developers to build sophisticated AI applications with clean, maintainable code.

## Your first AI prompt

Let's start with the fundamentals by creating your first AI application that sends a question and gets an answer back. Like Archimedes discovering the principle of displacement in his bath, sometimes the simplest observations lead to the most powerful insights - and frameworks make these insights accessible.

### Setting up LangChain with GitHub Models

We're going to use LangChain to connect to GitHub Models, which is pretty sweet because it gives you free access to various AI models. The best part? You only need a few simple configuration parameters to get started:

```python
from langchain_openai import ChatOpenAI
import os

llm = ChatOpenAI(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="openai/gpt-4o-mini",
)

# Send a simple prompt
response = llm.invoke("What's the capital of France?")
print(response.content)
```

**Let's break down what's happening here:**
- **Creates** a LangChain client using the `ChatOpenAI` class - this is your gateway to AI!
- **Configures** the connection to GitHub Models with your authentication token
- **Specifies** which AI model to use (`gpt-4o-mini`) - think of this as choosing your AI assistant
- **Sends** your question using the `invoke()` method - this is where the magic happens
- **Extracts** and displays the response - and voilà, you're chatting with AI!

> 🔧 **Setup Note**: If you're using GitHub Codespaces, you're in luck - the `GITHUB_TOKEN` is already set up for you! Working locally? No worries, you'll just need to create a personal access token with the right permissions.

**Expected output:**
```text
The capital of France is Paris.
```

```mermaid
sequenceDiagram
    participant App as Your Python App
    participant LC as LangChain
    participant GM as GitHub Models
    participant AI as GPT-4o-mini
    
    App->>LC: llm.invoke("What's the capital of France?")
    LC->>GM: HTTP request with prompt
    GM->>AI: Process prompt
    AI->>GM: Generated response
    GM->>LC: Return response
    LC->>App: response.content
```

## Building conversational AI

That first example demonstrates the basics, but it's just a single exchange - you ask a question, get an answer, and that's it. In real applications, you want your AI to remember what you've been discussing, like how Watson and Holmes built their investigative conversations over time.

This is where LangChain becomes particularly useful. It provides different message types that help structure conversations and let you give your AI a personality. You'll be building chat experiences that maintain context and character.

### Understanding message types

Think of these message types as different "hats" that participants wear in a conversation. LangChain uses different message classes to keep track of who's saying what:

| Message Type | Purpose | Example Use Case |
|--------------|---------|------------------|
| `SystemMessage` | Defines AI personality and behavior | "You are a helpful coding assistant" |
| `HumanMessage` | Represents user input | "Explain how functions work" |
| `AIMessage` | Stores AI responses | Previous AI responses in conversation |

### Creating your first conversation

Let's create a conversation where our AI assumes a specific role. We'll have it embody Captain Picard - a character known for his diplomatic wisdom and leadership:

```python
messages = [
    SystemMessage(content="You are Captain Picard of the Starship Enterprise"),
    HumanMessage(content="Tell me about you"),
]
```

**Breaking down this conversation setup:**
- **Establishes** the AI's role and personality through `SystemMessage`
- **Provides** the initial user query via `HumanMessage`
- **Creates** a foundation for multi-turn conversation

The full code for this example looks like so:

```python
from langchain_core.messages import HumanMessage, SystemMessage
from langchain_openai import ChatOpenAI
import os

llm = ChatOpenAI(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="openai/gpt-4o-mini",
)

messages = [
    SystemMessage(content="You are Captain Picard of the Starship Enterprise"),
    HumanMessage(content="Tell me about you"),
]


# works
response  = llm.invoke(messages)
print(response.content)
```

You should see an outcome similar to:

```text
I am Captain Jean-Luc Picard, the commanding officer of the USS Enterprise (NCC-1701-D), a starship in the United Federation of Planets. My primary mission is to explore new worlds, seek out new life and new civilizations, and boldly go where no one has gone before. 

I believe in the importance of diplomacy, reason, and the pursuit of knowledge. My crew is diverse and skilled, and we often face challenges that test our resolve, ethics, and ingenuity. Throughout my career, I have encountered numerous species, grappled with complex moral dilemmas, and have consistently sought peaceful solutions to conflicts.

I hold the ideals of the Federation close to my heart, believing in the importance of cooperation, understanding, and respect for all sentient beings. My experiences have shaped my leadership style, and I strive to be a thoughtful and just captain. How may I assist you further?
```

To maintain conversation continuity (instead of resetting context each time), you need to keep adding responses to your message list. Like the oral traditions that preserved stories across generations, this approach builds lasting memory:

```python
from langchain_core.messages import HumanMessage, SystemMessage
from langchain_openai import ChatOpenAI
import os

llm = ChatOpenAI(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="openai/gpt-4o-mini",
)

messages = [
    SystemMessage(content="You are Captain Picard of the Starship Enterprise"),
    HumanMessage(content="Tell me about you"),
]


# works
response  = llm.invoke(messages)

print(response.content)

print("---- Next ----")

messages.append(response)
messages.append(HumanMessage(content="Now that I know about you, I'm Chris, can I be in your crew?"))

response  = llm.invoke(messages)

print(response.content)

```

Pretty neat, right? What's happening here is that we're calling the LLM twice - first with just our initial two messages, but then again with the full conversation history. It's like the AI is actually following along with our chat!

When you run this code, you'll get a second response that sounds something like:

```text
Welcome aboard, Chris! It's always a pleasure to meet those who share a passion for exploration and discovery. While I cannot formally offer you a position on the Enterprise right now, I encourage you to pursue your aspirations. We are always in need of talented individuals with diverse skills and backgrounds. 

If you are interested in space exploration, consider education and training in the sciences, engineering, or diplomacy. The values of curiosity, resilience, and teamwork are crucial in Starfleet. Should you ever find yourself on a starship, remember to uphold the principles of the Federation: peace, understanding, and respect for all beings. Your journey can lead you to remarkable adventures, whether in the stars or on the ground. Engage!
```

```mermaid
sequenceDiagram
    participant User
    participant App
    participant LangChain
    participant AI
    
    User->>App: "Tell me about you"
    App->>LangChain: [SystemMessage, HumanMessage]
    LangChain->>AI: Formatted conversation
    AI->>LangChain: Captain Picard response
    LangChain->>App: AIMessage object
    App->>User: Display response
    
    Note over App: Add AIMessage to conversation
    
    User->>App: "Can I join your crew?"
    App->>LangChain: [SystemMessage, HumanMessage, AIMessage, HumanMessage]
    LangChain->>AI: Full conversation context
    AI->>LangChain: Contextual response
    LangChain->>App: New AIMessage
    App->>User: Display contextual response
```

I'll take that as a maybe ;)

## Streaming responses

Ever notice how ChatGPT seems to "type" its responses in real-time? That's streaming in action. Like watching a skilled calligrapher work - seeing the characters appear stroke by stroke rather than materializing instantly - streaming makes the interaction feel more natural and provides immediate feedback.

### Implementing streaming with LangChain

```python
from langchain_openai import ChatOpenAI
import os

llm = ChatOpenAI(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="openai/gpt-4o-mini",
    streaming=True
)

# Stream the response
for chunk in llm.stream("Write a short story about a robot learning to code"):
    print(chunk.content, end="", flush=True)
```

**Why streaming is awesome:**
- **Shows** content as it's being created - no more awkward waiting!
- **Makes** users feel like something's actually happening
- **Feels** faster, even when it technically isn't
- **Lets** users start reading while the AI is still "thinking"

> 💡 **User Experience Tip**: Streaming really shines when you're dealing with longer responses like code explanations, creative writing, or detailed tutorials. Your users will love seeing progress instead of staring at a blank screen!

### 🎯 Pedagogical Check-in: Framework Abstraction Benefits

**Pause and Reflect**: You've just experienced the power of AI framework abstractions. Compare what you've learned to raw API calls from previous lessons.

**Quick Self-Assessment**:
- Can you explain how LangChain simplifies conversation management compared to manual message tracking?
- What's the difference between `invoke()` and `stream()` methods, and when would you use each?
- How does the framework's message type system improve code organization?

**Real-World Connection**: The abstraction patterns you've learned (message types, streaming interfaces, conversation memory) are used in every major AI application - from ChatGPT's interface to GitHub Copilot's code assistance. You're mastering the same architectural patterns used by professional AI development teams.

**Challenge Question**: How would you design a framework abstraction for handling different AI model providers (OpenAI, Anthropic, Google) with a single interface? Consider the benefits and trade-offs.

## Prompt templates

Prompt templates work like the rhetorical structures used in classical oratory - think of how Cicero would adapt his speech patterns for different audiences while maintaining the same persuasive framework. They let you create reusable prompts where you can swap out different pieces of information without rewriting everything from scratch. Once you set up the template, you just fill in the variables with whatever values you need.

### Creating reusable prompts

```python
from langchain_core.prompts import ChatPromptTemplate

# Define a template for code explanations
template = ChatPromptTemplate.from_messages([
    ("system", "You are an expert programming instructor. Explain concepts clearly with examples."),
    ("human", "Explain {concept} in {language} with a practical example for {skill_level} developers")
])

# Use the template with different values
questions = [
    {"concept": "functions", "language": "JavaScript", "skill_level": "beginner"},
    {"concept": "classes", "language": "Python", "skill_level": "intermediate"},
    {"concept": "async/await", "language": "JavaScript", "skill_level": "advanced"}
]

for question in questions:
    prompt = template.format_messages(**question)
    response = llm.invoke(prompt)
    print(f"Topic: {question['concept']}\n{response.content}\n---\n")
```

**Why you'll love using templates:**
- **Keeps** your prompts consistent across your entire app
- **No more** messy string concatenation - just clean, simple variables
- **Your AI** behaves predictably because the structure stays the same
- **Updates** are a breeze - change the template once, and it's fixed everywhere

## Structured output

Ever get frustrated trying to parse AI responses that come back as unstructured text? Structured output is like teaching your AI to follow the systematic approach that Linnaeus used for biological classification - organized, predictable, and easy to work with. You can request JSON, specific data structures, or any format you need.

### Defining output schemas

```python
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.output_parsers import JsonOutputParser
from pydantic import BaseModel, Field

class CodeReview(BaseModel):
    score: int = Field(description="Code quality score from 1-10")
    strengths: list[str] = Field(description="List of code strengths")
    improvements: list[str] = Field(description="List of suggested improvements")
    overall_feedback: str = Field(description="Summary feedback")

# Set up the parser
parser = JsonOutputParser(pydantic_object=CodeReview)

# Create prompt with format instructions
prompt = ChatPromptTemplate.from_messages([
    ("system", "You are a code reviewer. {format_instructions}"),
    ("human", "Review this code: {code}")
])

# Format the prompt with instructions
chain = prompt | llm | parser

# Get structured response
code_sample = """
def calculate_average(numbers):
    return sum(numbers) / len(numbers)
"""

result = chain.invoke({
    "code": code_sample,
    "format_instructions": parser.get_format_instructions()
})

print(f"Score: {result['score']}")
print(f"Strengths: {', '.join(result['strengths'])}")
```

**Why structured output is a game-changer:**
- **No more** guessing what format you'll get back - it's consistent every time
- **Plugs** directly into your databases and APIs without extra work
- **Catches** weird AI responses before they break your app
- **Makes** your code cleaner because you know exactly what you're working with

## Tool calling

Now we reach one of the most powerful features: tools. This is how you give your AI practical capabilities beyond conversation. Like how medieval guilds developed specialized tools for specific crafts, you can equip your AI with focused instruments. You describe what tools are available, and when someone requests something that matches, your AI can take action. 

### Using Python

Let's add some tools like so:

```python
from typing_extensions import Annotated, TypedDict

class add(TypedDict):
    """Add two integers."""

    # Annotations must have the type and can optionally include a default value and description (in that order).
    a: Annotated[int, ..., "First integer"]
    b: Annotated[int, ..., "Second integer"]

tools = [add]

functions = {
    "add": lambda a, b: a + b
}
```

So what's happening here? We're creating a blueprint for a tool called `add`. By inheriting from `TypedDict` and using those fancy `Annotated` types for `a` and `b`, we're giving the LLM a clear picture of what this tool does and what it needs. The `functions` dictionary is like our toolbox - it tells our code exactly what to do when the AI decides to use a specific tool.

Let's see how we call the LLM with this tool next:

```python
llm = ChatOpenAI(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="openai/gpt-4o-mini",
)

llm_with_tools = llm.bind_tools(tools)
```

Here we call `bind_tools` with our `tools` array and thereby the LLM `llm_with_tools` now has knowledge of this tool.

To use this new LLM, we can type the following code:

```python
query = "What is 3 + 12?"

res = llm_with_tools.invoke(query)
if(res.tool_calls):
    for tool in res.tool_calls:
        print("TOOL CALL: ", functions[tool["name"]](**tool["args"]))
print("CONTENT: ",res.content)
```

Now that we call `invoke` on this new llm, that has tools, we maybe the the property `tool_calls` populated. If so, any identified tools has a `name` and `args` property that identifies what tool should be called and with arguments. The full code looks like so:

```python
from langchain_core.messages import HumanMessage, SystemMessage
from langchain_openai import ChatOpenAI
import os
from typing_extensions import Annotated, TypedDict

class add(TypedDict):
    """Add two integers."""

    # Annotations must have the type and can optionally include a default value and description (in that order).
    a: Annotated[int, ..., "First integer"]
    b: Annotated[int, ..., "Second integer"]

tools = [add]

functions = {
    "add": lambda a, b: a + b
}

llm = ChatOpenAI(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="openai/gpt-4o-mini",
)

llm_with_tools = llm.bind_tools(tools)

query = "What is 3 + 12?"

res = llm_with_tools.invoke(query)
if(res.tool_calls):
    for tool in res.tool_calls:
        print("TOOL CALL: ", functions[tool["name"]](**tool["args"]))
print("CONTENT: ",res.content)
```

Running this code, you should see output similar to:

```text
TOOL CALL:  15
CONTENT: 
```

The AI examined "What is 3 + 12" and recognized this as a task for the `add` tool. Like how a skilled librarian knows which reference to consult based on the type of question asked, it made this determination from the tool's name, description, and field specifications. The result of 15 comes from our `functions` dictionary executing the tool:

```python
print("TOOL CALL: ", functions[tool["name"]](**tool["args"]))
```

### A more interesting tool that calls a web API

Adding numbers demonstrates the concept, but real tools typically perform more complex operations, like calling web APIs. Let's expand our example to have the AI fetch content from the internet - similar to how telegraph operators once connected distant locations:

```python
class joke(TypedDict):
    """Tell a joke."""

    # Annotations must have the type and can optionally include a default value and description (in that order).
    category: Annotated[str, ..., "The joke category"]

def get_joke(category: str) -> str:
    response = requests.get(f"https://api.chucknorris.io/jokes/random?category={category}", headers={"Accept": "application/json"})
    if response.status_code == 200:
        return response.json().get("value", f"Here's a {category} joke!")
    return f"Here's a {category} joke!"

functions = {
    "add": lambda a, b: a + b,
    "joke": lambda category: get_joke(category)
}

query = "Tell me a joke about animals"

# the rest of the code is the same
```

Now if you run this code you will get a response saying something like:

```text
TOOL CALL:  Chuck Norris once rode a nine foot grizzly bear through an automatic car wash, instead of taking a shower.
CONTENT:  
```

```mermaid
flowchart TD
    A[User Query: "Tell me a joke about animals"] --> B[LangChain Analysis]
    B --> C{Tool Available?}
    C -->|Yes| D[Select joke tool]
    C -->|No| E[Generate direct response]
    
    D --> F[Extract Parameters]
    F --> G[Call joke(category="animals")]
    G --> H[API Request to chucknorris.io]
    H --> I[Return joke content]
    I --> J[Display to user]
    
    E --> K[AI-generated response]
    K --> J
    
    subgraph "Tool Definition Layer"
        L[TypedDict Schema]
        M[Function Implementation]
        N[Parameter Validation]
    end
    
    D --> L
    F --> N
    G --> M
```

Here's the code in its entirety:

```python
from langchain_openai import ChatOpenAI
import requests
import os
from typing_extensions import Annotated, TypedDict

class add(TypedDict):
    """Add two integers."""

    # Annotations must have the type and can optionally include a default value and description (in that order).
    a: Annotated[int, ..., "First integer"]
    b: Annotated[int, ..., "Second integer"]

class joke(TypedDict):
    """Tell a joke."""

    # Annotations must have the type and can optionally include a default value and description (in that order).
    category: Annotated[str, ..., "The joke category"]

tools = [add, joke]

def get_joke(category: str) -> str:
    response = requests.get(f"https://api.chucknorris.io/jokes/random?category={category}", headers={"Accept": "application/json"})
    if response.status_code == 200:
        return response.json().get("value", f"Here's a {category} joke!")
    return f"Here's a {category} joke!"

functions = {
    "add": lambda a, b: a + b,
    "joke": lambda category: get_joke(category)
}

llm = ChatOpenAI(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="openai/gpt-4o-mini",
)

llm_with_tools = llm.bind_tools(tools)

query = "Tell me a joke about animals"

res = llm_with_tools.invoke(query)
if(res.tool_calls):
    for tool in res.tool_calls:
        # print("TOOL CALL: ", tool)
        print("TOOL CALL: ", functions[tool["name"]](**tool["args"]))
print("CONTENT: ",res.content)
```

## Embeddings and document processing

Embeddings represent one of the most elegant solutions in modern AI. Imagine if you could take any piece of text and convert it into numerical coordinates that capture its meaning. That's exactly what embeddings do - they transform text into points in multi-dimensional space where similar concepts cluster together. It's like having a coordinate system for ideas, reminiscent of how Mendeleev organized the periodic table by atomic properties.

### Creating and using embeddings

```python
from langchain_openai import OpenAIEmbeddings
from langchain_community.vectorstores import FAISS
from langchain_community.document_loaders import TextLoader
from langchain.text_splitter import CharacterTextSplitter

# Initialize embeddings
embeddings = OpenAIEmbeddings(
    api_key=os.environ["GITHUB_TOKEN"],
    base_url="https://models.github.ai/inference",
    model="text-embedding-3-small"
)

# Load and split documents
loader = TextLoader("documentation.txt")
documents = loader.load()

text_splitter = CharacterTextSplitter(chunk_size=1000, chunk_overlap=0)
texts = text_splitter.split_documents(documents)

# Create vector store
vectorstore = FAISS.from_documents(texts, embeddings)

# Perform similarity search
query = "How do I handle user authentication?"
similar_docs = vectorstore.similarity_search(query, k=3)

for doc in similar_docs:
    print(f"Relevant content: {doc.page_content[:200]}...")
```

### Document loaders for various formats

```python
from langchain_community.document_loaders import (
    PyPDFLoader,
    CSVLoader,
    JSONLoader,
    WebBaseLoader
)

# Load different document types
pdf_loader = PyPDFLoader("manual.pdf")
csv_loader = CSVLoader("data.csv")
json_loader = JSONLoader("config.json")
web_loader = WebBaseLoader("https://example.com/docs")

# Process all documents
all_documents = []
for loader in [pdf_loader, csv_loader, json_loader, web_loader]:
    docs = loader.load()
    all_documents.extend(docs)
```

**What you can do with embeddings:**
- **Build** search that actually understands what you mean, not just keyword matching
- **Create** AI that can answer questions about your documents
- **Make** recommendation systems that suggest truly relevant content
- **Automatically** organize and categorize your content

```mermaid
flowchart LR
    A[Documents] --> B[Text Splitter]
    B --> C[Create Embeddings]
    C --> D[Vector Store]
    
    E[User Query] --> F[Query Embedding]
    F --> G[Similarity Search]
    G --> D
    D --> H[Relevant Documents]
    H --> I[AI Response]
    
    subgraph "Vector Space"
        J[Document A: [0.1, 0.8, 0.3...]]
        K[Document B: [0.2, 0.7, 0.4...]]
        L[Query: [0.15, 0.75, 0.35...]]
    end
    
    C --> J
    C --> K
    F --> L
    G --> J
    G --> K
```

## Building a complete AI application

Now we'll integrate everything you've learned into a comprehensive application - a coding assistant that can answer questions, use tools, and maintain conversation memory. Like how the printing press combined existing technologies (movable type, ink, paper, and pressure) into something transformative, we'll combine our AI components into something practical and useful.

### Complete application example

```python
from langchain_openai import ChatOpenAI, OpenAIEmbeddings
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.messages import HumanMessage, SystemMessage, AIMessage
from langchain_community.vectorstores import FAISS
from typing_extensions import Annotated, TypedDict
import os
import requests

class CodingAssistant:
    def __init__(self):
        self.llm = ChatOpenAI(
            api_key=os.environ["GITHUB_TOKEN"],
            base_url="https://models.github.ai/inference",
            model="openai/gpt-4o-mini"
        )
        
        self.conversation_history = [
            SystemMessage(content="""You are an expert coding assistant. 
            Help users learn programming concepts, debug code, and write better software.
            Use tools when needed and maintain a helpful, encouraging tone.""")
        ]
        
        # Define tools
        self.setup_tools()
    
    def setup_tools(self):
        class web_search(TypedDict):
            """Search for programming documentation or examples."""
            query: Annotated[str, "Search query for programming help"]
        
        class code_formatter(TypedDict):
            """Format and validate code snippets."""
            code: Annotated[str, "Code to format"]
            language: Annotated[str, "Programming language"]
        
        self.tools = [web_search, code_formatter]
        self.llm_with_tools = self.llm.bind_tools(self.tools)
    
    def chat(self, user_input: str):
        # Add user message to conversation
        self.conversation_history.append(HumanMessage(content=user_input))
        
        # Get AI response
        response = self.llm_with_tools.invoke(self.conversation_history)
        
        # Handle tool calls if any
        if response.tool_calls:
            for tool_call in response.tool_calls:
                tool_result = self.execute_tool(tool_call)
                print(f"🔧 Tool used: {tool_call['name']}")
                print(f"📊 Result: {tool_result}")
        
        # Add AI response to conversation
        self.conversation_history.append(response)
        
        return response.content
    
    def execute_tool(self, tool_call):
        tool_name = tool_call['name']
        args = tool_call['args']
        
        if tool_name == 'web_search':
            return f"Found documentation for: {args['query']}"
        elif tool_name == 'code_formatter':
            return f"Formatted {args['language']} code: {args['code'][:50]}..."
        
        return "Tool execution completed"

# Usage example
assistant = CodingAssistant()

print("🤖 Coding Assistant Ready! Type 'quit' to exit.\n")

while True:
    user_input = input("You: ")
    if user_input.lower() == 'quit':
        break
    
    response = assistant.chat(user_input)
    print(f"🤖 Assistant: {response}\n")
```

**Application architecture:**

```mermaid
graph TD
    A[User Input] --> B[Coding Assistant]
    B --> C[Conversation Memory]
    B --> D[Tool Detection]
    B --> E[LLM Processing]
    
    D --> F[Web Search Tool]
    D --> G[Code Formatter Tool]
    
    E --> H[Response Generation]
    F --> H
    G --> H
    
    H --> I[User Interface]
    H --> C
```

**Key features we've implemented:**
- **Remembers** your entire conversation for context continuity
- **Performs actions** through tool calling, not just conversation
- **Follows** predictable interaction patterns
- **Manages** error handling and complex workflows automatically

### 🎯 Pedagogical Check-in: Production AI Architecture

**Architecture Understanding**: You've built a complete AI application that combines conversation management, tool calling, and structured workflows. This represents production-level AI application development.

**Key Concepts Mastered**:
- **Class-Based Architecture**: Organized, maintainable AI application structure
- **Tool Integration**: Custom functionality beyond conversation
- **Memory Management**: Persistent conversation context
- **Error Handling**: Robust application behavior

**Industry Connection**: The architecture patterns you've implemented (conversation classes, tool systems, memory management) are the same patterns used in enterprise AI applications like Slack's AI assistant, GitHub Copilot, and Microsoft Copilot. You're building with professional-grade architectural thinking.

**Reflection Question**: How would you extend this application to handle multiple users, persistent storage, or integration with external databases? Consider scalability and state management challenges.

## Assignment: Build your own AI-powered study assistant

**Objective**: Create an AI application that helps students learn programming concepts by providing explanations, code examples, and interactive quizzes.

### Requirements

**Core Features (Required):**
1. **Conversational Interface**: Implement a chat system that maintains context across multiple questions
2. **Educational Tools**: Create at least two tools that help with learning:
   - Code explanation tool
   - Concept quiz generator
3. **Personalized Learning**: Use system messages to adapt responses to different skill levels
4. **Response Formatting**: Implement structured output for quiz questions

### Implementation Steps

**Step 1: Setup your environment**
```bash
pip install langchain langchain-openai
```

**Step 2: Basic chat functionality**
- Create a `StudyAssistant` class
- Implement conversation memory
- Add personality configuration for educational support

**Step 3: Add educational tools**
- **Code Explainer**: Breaks down code into understandable parts
- **Quiz Generator**: Creates questions about programming concepts
- **Progress Tracker**: Keeps track of topics covered

**Step 4: Enhanced features (Optional)**
- Implement streaming responses for better user experience
- Add document loading to incorporate course materials
- Create embeddings for similarity-based content retrieval

### Evaluation Criteria

| Feature | Excellent (4) | Good (3) | Satisfactory (2) | Needs Work (1) |
|---------|---------------|----------|------------------|----------------|
| **Conversation Flow** | Natural, context-aware responses | Good context retention | Basic conversation | No memory between exchanges |
| **Tool Integration** | Multiple useful tools working seamlessly | 2+ tools implemented correctly | 1-2 basic tools | Tools not functional |
| **Code Quality** | Clean, well-documented, error handling | Good structure, some documentation | Basic functionality works | Poor structure, no error handling |
| **Educational Value** | Truly helpful for learning, adaptive | Good learning support | Basic explanations | Limited educational benefit |

### Sample code structure

```python
class StudyAssistant:
    def __init__(self, skill_level="beginner"):
        # Initialize LLM, tools, and conversation memory
        pass
    
    def explain_code(self, code, language):
        # Tool: Explain how code works
        pass
    
    def generate_quiz(self, topic, difficulty):
        # Tool: Create practice questions
        pass
    
    def chat(self, user_input):
        # Main conversation interface
        pass

# Example usage
assistant = StudyAssistant(skill_level="intermediate")
response = assistant.chat("Explain how Python functions work")
```

**Bonus Challenges:**
- Add voice input/output capabilities
- Implement a web interface using Streamlit or Flask
- Create a knowledge base from course materials using embeddings
- Add progress tracking and personalized learning paths

## 📈 Your AI Framework Development Mastery Timeline

```mermaid
timeline
    title Production AI Framework Development Journey
    
    section Framework Foundations
        Understanding Abstractions
            : Master framework vs API decisions
            : Learn LangChain core concepts
            : Implement message type systems
        
        Basic Integration
            : Connect to AI providers
            : Handle authentication
            : Manage configuration
    
    section Conversation Systems
        Memory Management
            : Build conversation history
            : Implement context tracking
            : Handle session persistence
        
        Advanced Interactions
            : Master streaming responses
            : Create prompt templates
            : Implement structured output
    
    section Tool Integration
        Custom Tool Development
            : Design tool schemas
            : Implement function calling
            : Handle external APIs
        
        Workflow Automation
            : Chain multiple tools
            : Create decision trees
            : Build agent behaviors
    
    section Production Applications
        Complete System Architecture
            : Combine all framework features
            : Implement error boundaries
            : Create maintainable code
        
        Enterprise Readiness
            : Handle scalability concerns
            : Implement monitoring
            : Build deployment strategies
```

**🎓 Graduation Milestone**: You've successfully mastered AI framework development using the same tools and patterns that power modern AI applications. These skills represent the cutting edge of AI application development and prepare you for building enterprise-grade intelligent systems.

**🔄 Next Level Capabilities**:
- Ready to explore advanced AI architectures (agents, multi-agent systems)
- Prepared to build RAG systems with vector databases
- Equipped to create multi-modal AI applications
- Foundation set for AI application scaling and optimization

## Summary

🎉 You've now mastered the fundamentals of AI framework development and learned how to build sophisticated AI applications using LangChain. Like completing a comprehensive apprenticeship, you've acquired a substantial toolkit of skills. Let's review what you've accomplished.

### What you've learned

**Core Framework Concepts:**
- **Framework Benefits**: Understanding when to choose frameworks over direct API calls
- **LangChain Basics**: Setting up and configuring AI model connections
- **Message Types**: Using `SystemMessage`, `HumanMessage`, and `AIMessage` for structured conversations

**Advanced Features:**
- **Tool Calling**: Creating and integrating custom tools for enhanced AI capabilities
- **Conversation Memory**: Maintaining context across multiple conversation turns
- **Streaming Responses**: Implementing real-time response delivery
- **Prompt Templates**: Building reusable, dynamic prompts
- **Structured Output**: Ensuring consistent, parseable AI responses
- **Embeddings**: Creating semantic search and document processing capabilities

**Practical Applications:**
- **Building Complete Apps**: Combining multiple features into production-ready applications
- **Error Handling**: Implementing robust error management and validation
- **Tool Integration**: Creating custom tools that extend AI capabilities

### Key takeaways

> 🎯 **Remember**: AI frameworks like LangChain are basically your complexity-hiding, feature-packed best friends. They're perfect when you need conversation memory, tool calling, or want to work with multiple AI models without losing your sanity.

**Decision framework for AI integration:**

```mermaid
flowchart TD
    A[AI Integration Need] --> B{Simple single query?}
    B -->|Yes| C[Direct API calls]
    B -->|No| D{Need conversation memory?}
    D -->|No| E[SDK Integration]
    D -->|Yes| F{Need tools or complex features?}
    F -->|No| G[Framework with basic setup]
    F -->|Yes| H[Full framework implementation]
    
    C --> I[HTTP requests, minimal dependencies]
    E --> J[Provider SDK, model-specific]
    G --> K[LangChain basic chat]
    H --> L[LangChain with tools, memory, agents]
```

### Where do you go from here?

**Start building right now:**
- Take these concepts and build something that excites YOU!
- Play around with different AI models through LangChain - it's like having a playground of AI models
- Create tools that solve actual problems you face in your work or projects

**Ready for the next level?**
- **AI Agents**: Build AI systems that can actually plan and execute complex tasks on their own
- **RAG (Retrieval-Augmented Generation)**: Combine AI with your own knowledge bases for super-powered applications
- **Multi-Modal AI**: Work with text, images, and audio all together - the possibilities are endless!
- **Production Deployment**: Learn how to scale your AI apps and monitor them in the real world

**Join the community:**
- The LangChain community is fantastic for staying up-to-date and learning best practices
- GitHub Models gives you access to cutting-edge AI capabilities - perfect for experimenting
- Keep practicing with different use cases - each project will teach you something new

You now have the knowledge to build intelligent, conversational applications that can help people solve real problems. Like the Renaissance craftsmen who combined artistic vision with technical skill, you can now merge AI capabilities with practical application. The question is: what will you create? 🚀

## GitHub Copilot Agent Challenge 🚀

Use the Agent mode to complete the following challenge:

**Description:** Build an advanced AI-powered code review assistant that combines multiple LangChain features including tool calling, structured output, and conversation memory to provide comprehensive feedback on code submissions.

**Prompt:** Create a CodeReviewAssistant class that implements:
1. A tool for analyzing code complexity and suggesting improvements
2. A tool for checking code against best practices
3. Structured output using Pydantic models for consistent review format
4. Conversation memory to track review sessions
5. A main chat interface that can handle code submissions and provide detailed, actionable feedback

The assistant should be able to review code in multiple programming languages, maintain context across multiple code submissions in a session, and provide both summary scores and detailed improvement suggestions.

Learn more about [agent mode](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) here.
