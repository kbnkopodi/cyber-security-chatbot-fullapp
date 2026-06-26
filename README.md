🛡️ CyberSecurity Assistant
📖 Overview
CyberSecurity Assistant is a Windows desktop application built with C# and WPF that functions as an AI-powered cybersecurity awareness tool. The application simulates an intelligent assistant that can educate users about cybersecurity topics, manage tasks, test knowledge through quizzes, and track user activities.

Core Purpose
Provide cybersecurity education through interactive conversation

Help users manage tasks with natural language input

Test cybersecurity knowledge through quizzes

Track and log user activities for progress monitoring

✨ Key Features
Intelligent Chat Assistant
The application includes a conversational AI that can discuss various cybersecurity topics. It features text-to-speech voice output, emotion detection to respond empathetically, and memory persistence that remembers conversations across sessions. User profiles store names and favorite cybersecurity topics for personalized interactions.

Smart Task Management
Users can create tasks using natural language phrases like "remind me to submit the report tomorrow" or through a guided step-by-step wizard. The system supports smart reminder scheduling using phrases such as "in 7 days," "next week," or specific dates like "on 25 June 2025." Users can view all active tasks and mark them as complete when finished.

Interactive Quiz System
The application includes a cybersecurity quiz with 12+ multiple-choice and true/false questions. Each question provides instant feedback with detailed explanations, helping users learn from their answers. The system tracks scores and provides personalized feedback based on performance.

Activity Tracking
Every user action is automatically logged with timestamps and categories. Users can request activity summaries by asking "what have you done for me?" to see recent actions categorized by type.

🛠️ Technology Stack
Frameworks & Languages
C# - Primary programming language

.NET 8.0 - Application framework

WPF - User interface framework for Windows desktop

Database
SQL Server LocalDB - Lightweight local database

Microsoft.Data.SqlClient - Database connectivity library

Additional Technologies
System.Speech - Text-to-speech voice output

Custom NLP Engine - Lightweight natural language processing

📦 System Requirements
Prerequisites
Windows 10 or 11 (64-bit)

.NET 8.0 SDK or runtime

Visual Studio 2022 (for development)

SQL Server LocalDB (included with Visual Studio)

Hardware Requirements
Minimum 4GB RAM

100MB free disk space

Sound card for voice output

📥 Installation Guide
Quick Installation
Clone the repository from GitHub

Open the solution file in Visual Studio

Restore NuGet packages

Build the solution

Run the application

Manual Installation Steps
text
Clone repository → Open solution → Restore packages → Build → Run
First-Time Setup
When you first run the application, it will:

Automatically create the database (if using LocalDB)

Generate chat memory and user profile files

Display a welcome message asking for your name

🗄️ Database Configuration
Automatic Setup
The database is created automatically when the application runs for the first time, provided LocalDB is installed.

Manual Setup
If automatic setup fails, you can create the database manually using SQL Server Management Studio:

Create a new database called "Studentdata" and add a table called "Data" with columns for Id, Title, Description, ReminderDate, IsCompleted, and CreatedDate.

Connection String
The application uses Windows Integrated Security with the connection string pointing to the LocalDB instance.

📖 Usage Guide
Getting Started
Launch the application and provide your name when prompted. The assistant will ask for your favorite cybersecurity topic to personalize your experience.

Basic Commands
Start conversations with greetings like "hello" or "hi." End sessions with "bye" or "goodbye." Ask about the assistant's purpose with "what's your purpose" or check its status with "how are you."

Task Management
Create tasks using natural language: "remind me to update firewall next week" or use the guided wizard by typing "add task." View all your tasks with "my tasks" or "show my tasks." Complete tasks by typing "complete task 1" (replacing 1 with the task number).

Quiz System
Start the quiz by clicking the "Start Quiz" button or typing "start quiz" or "quiz me." Answer multiple-choice questions with A, B, C, or D, and true/false questions with True or False. Exit anytime by typing "quit quiz."

Activity Tracking
View your recent actions by asking "what have you done for me" or "recap." See full conversation history with "what do you remember" or "show all."

Cybersecurity Topics
Ask about these topics for detailed information:

Phishing and scam emails

Password safety and strong passwords

Safe browsing practices

Malware and viruses

VPN and privacy

Two-factor authentication

Social engineering

🧠 Natural Language Processing
Intent Detection
The application uses keyword matching to understand user intent. It recognizes phrases for task creation, quiz start, task viewing, and cybersecurity topics. The system handles greetings, farewells, and memory inquiries.

Topic Extraction
When users say "remind me to [task]" or "add task: [task]," the system extracts the task title and removes time-related phrases. For example, "remind me to study tomorrow" becomes "Study."

Date Parsing
The system understands various date formats:

Relative dates: "today," "tomorrow," "next week," "next month"

Duration phrases: "in 7 days," "in 2 weeks," "in 1 month"

Specific dates: "25 June 2025" or "2025-06-25"

📁 File Structure
Main Components
The application consists of UI layout files (XAML), code-behind files (C#), data models, a database helper, an NLP engine, and project configuration files.

Data Models
ActivityEntry - Logs user actions with timestamps and categories

CyberTask - Represents tasks with title, description, reminder, and completion status

QuizQuestion - Stores quiz questions with type, options, correct answer, and explanation

Data Persistence
Database - Stores tasks with SQL Server LocalDB

chatmemory.txt - Stores conversation history

userprofile.txt - Stores user name and favorite topic

🔒 Security Features
Current Security Measures
Parameterized SQL queries prevent SQL injection attacks

Windows Integrated Security eliminates password storage

Input validation prevents malformed commands

Security Recommendations
Encrypt memory files for sensitive data

Add user authentication for multi-user support

Implement proper logging for security auditing

Use configuration file encryption

🔧 Troubleshooting
Database Connection Issues
If the application cannot connect to the database, ensure LocalDB is installed and running. You can check its status using the SQL LocalDB command line tool and start it if needed.

Voice Output Issues
If text-to-speech is not working, ensure Windows Media Features are enabled in the Control Panel under Windows Features.

Sound File Not Found
If the application cannot find the exit sound file, you can comment out the sound player code or use a try-catch block to handle the error gracefully.

📊 Performance
The application runs efficiently with quick response times for most operations. Chat responses involve dictionary lookups, NLP processing uses keyword matching, database queries are optimized with indexing, and activity logging is append-only for minimal overhead.

🤝 Contributing
How to Contribute
Fork the repository

Create a feature branch

Commit your changes

Push to your branch

Open a pull request

Guidelines
Follow C# coding conventions, use meaningful variable names, add comments for complex logic, and include XML documentation for public methods.
