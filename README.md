🎯 Overview
CyberSecurity Assistant is a WPF desktop application designed to educate users about cybersecurity best practices through interactive conversations, task management, and knowledge testing. The application simulates an AI assistant that can:

💬 Chat about cybersecurity topics (phishing, password safety, safe browsing, malware, VPNs, 2FA, social engineering)

📝 Manage Tasks with natural language input and reminder scheduling

🎮 Test Knowledge through cybersecurity quizzes with instant feedback

📊 Track Activities with an action log and conversation memory

✨ Features
🤖 Intelligent Chat Assistant
Natural Language Understanding - Discuss cybersecurity topics conversationally

Voice Output - Text-to-speech responses using Windows Speech Synthesis

Emotion Detection - Responds empathetically to user emotions (worried, scared, confused, etc.)

Memory Persistence - Remembers conversation history across sessions

User Profiles - Stores user name and favorite cybersecurity topics

📝 Smart Task Management
Natural Language Task Creation - "Remind me to submit the report tomorrow"

Step-by-Step Wizard - Guided task creation with title, description, and reminders

Reminder Scheduling - Set reminders using natural language ("in 7 days", "next week", "on 25 June 2025")

Task Listing - View all active tasks with their details

Task Completion - Mark tasks as complete when finished

🎮 Cybersecurity Quiz System
12+ Quiz Questions - Multiple choice and true/false questions

Instant Feedback - Detailed explanations for each answer

Score Tracking - Performance evaluation with personalized feedback

Progress Indicators - Track your progress through the quiz

Exit Anytime - Quit the quiz and resume later

📊 Activity Tracking
Action Logging - Automatically logs all user activities

Activity Summary - Ask "what have you done for me?" to see recent actions

Categorized Actions - Tasks, reminders, quizzes, NLP interactions, and system events

🖥️ Screenshots
<div align="center">
[Screenshots would go here - add actual screenshots of your application]

</div>
🛠️ Tech Stack
Technology	Purpose
C# / .NET 8.0	Core programming language and framework
WPF (Windows Presentation Foundation)	Desktop UI framework
SQL Server LocalDB	Local database for task persistence
Microsoft.Data.SqlClient	Database connectivity
System.Speech	Text-to-speech voice output
Custom NLP Engine	Lightweight natural language processing
📦 Installation
Prerequisites
Windows 10/11 (64-bit)

.NET 8.0 SDK or later

Visual Studio 2022 with WPF workload

SQL Server LocalDB (included with Visual Studio)

Step-by-Step Installation
Clone the Repository

bash
git clone https://github.com/yourusername/CyberSecurity-Assistant.git
cd CyberSecurity-Assistant
Open the Project

bash
# Launch in Visual Studio
start WpfApp1.sln
Restore NuGet Packages

bash
dotnet restore
Build the Project

bash
dotnet build
Run the Application

bash
dotnet run --project WpfApp1.csproj
Or simply press F5 in Visual Studio.

🗄️ Database Setup
The application uses SQL Server LocalDB with a table called Data to store tasks.

Option 1: Automatic Setup (Recommended)
The database will be automatically created when you run the application for the first time, provided you have LocalDB installed.

Option 2: Manual Setup
Open SQL Server Management Studio or Visual Studio SQL Server Object Explorer

Connect to (localdb)\MSSQLLOCALDB

Run the following script:

sql
CREATE DATABASE Studentdata;
GO

USE Studentdata;
GO

CREATE TABLE [dbo].[Data]
(
    [Id]           INT            NOT NULL PRIMARY KEY IDENTITY(1,1),
    [Title]        NVARCHAR(255)  NOT NULL,
    [Description]  NVARCHAR(500)  NULL,
    [ReminderDate] DATE           NULL,
    [IsCompleted]  BIT            NOT NULL DEFAULT 0,
    [CreatedDate]  DATETIME       NOT NULL DEFAULT GETDATE()
);
GO
Connection String
The default connection string is:

text
Data Source=(localdb)\MSSQLLOCALDB;Initial Catalog=Studentdata;Integrated Security=True;
📖 Usage Guide
Basic Commands
Command	Description
hello / hi	Start a conversation
bye / goodbye	End the session
how are you	Check bot status
what's your purpose	Learn about the assistant
Task Management Commands
Command	Description	Example
add task	Start guided task creation	"add task" → follow prompts
remind me to {task}	Quick task with natural language	"remind me to update firewall next week"
my tasks / show my tasks	List all active tasks	"show my tasks"
complete task {number}	Mark a task as done	"complete task 1"
Quiz Commands
Command	Description
start quiz / quiz me	Start the cybersecurity quiz
quit quiz	Exit the quiz early
Activity & Memory Commands
Command	Description
what have you done for me	Show recent activity log
what do you remember	See conversation memory
show all / full log	View complete activity history
Cybersecurity Topics
Ask about these topics for detailed information:

Phishing - Identify email scams and fraud

Password Safety - Create and manage strong passwords

Safe Browsing - Internet safety best practices

Malware - Viruses, ransomware, spyware protection

VPN - Virtual Private Networks and privacy

Two-Factor Authentication - Extra security layer setup

Social Engineering - Manipulation and impersonation attacks

Natural Language Task Examples
text
✅ "remind me to submit the security report tomorrow"
✅ "add task: Update antivirus software in 7 days"
✅ "can you remind me to backup files next week"
✅ "set a reminder for firewall maintenance on 25 June 2025"
✅ "don't let me forget to change my password"
📁 Project Structure
text
CyberSecurity-Assistant/
├── WpfApp1/
│   ├── Properties/
│   │   └── AssemblyInfo.cs
│   ├── App.xaml
│   ├── App.xaml.cs
│   ├── MainWindow.xaml
│   ├── MainWindow.xaml.cs
│   ├── ActivityEntry.cs
│   ├── CyberTask.cs
│   ├── DatabaseHelper.cs
│   ├── NlpEngine.cs
│   ├── QuizQuestion.cs
│   ├── WpfApp1.csproj
│   ├── Data.sql
│   ├── chatmemory.txt          # Auto-generated chat history
│   └── userprofile.txt         # Auto-generated user profile
└── README.md
Key Files Explained
File	Description
MainWindow.xaml	UI layout with chat interface, sidebar, and controls
MainWindow.xaml.cs	Core application logic (500+ lines)
DatabaseHelper.cs	SQL operations (CRUD for tasks)
NlpEngine.cs	Natural language processing engine
ActivityEntry.cs	Activity logging model
CyberTask.cs	Task data model
QuizQuestion.cs	Quiz question model
🧠 NLP Commands
The application includes a custom NLP engine that can understand:

Intent Categories
Intent	Trigger Phrases
ADD_TASK	"remind me to", "add task", "create task", "i need to"
START_QUIZ	"start quiz", "quiz me", "test me"
SHOW_TASKS	"my tasks", "show tasks", "list tasks"
COMPLETE_TASK	"complete task", "mark done"
SHOW_SUMMARY	"what have you done for me", "action log"
PHISHING	"phishing", "fake email", "scam"
PASSWORD	"password safety", "strong password"
SAFE_BROWSING	"safe browsing", "internet safety"
MALWARE	"malware", "virus", "ransomware"
VPN	"vpn", "virtual private network"
TWO_FA	"two factor", "2fa", "authenticator"
SOCIAL_ENG	"social engineering", "manipulation"
FAREWELL	"bye", "goodbye", "see you"
MEMORY	"what do you remember", "remember"
Date Parsing Examples
text
"in 7 days"          → +7 days
"in 2 weeks"         → +14 days
"in 1 month"         → +30 days
"tomorrow"           → +1 day
"next week"          → +7 days
"25 June 2025"       → Specific date
"2025-06-25"         → Specific date
"no reminder"        → No reminder set
🤝 Contributing
We welcome contributions! Here's how you can help:

🐛 Report Bugs
Use the Issue Tracker

Provide detailed steps to reproduce

Include screenshots if applicable

💡 Suggest Features
Open a feature request issue

Describe the feature and its benefits

Provide use cases if possible

🔧 Submit Pull Requests
Fork the repository

Create a feature branch (git checkout -b feature/AmazingFeature)

Commit changes (git commit -m 'Add some AmazingFeature')

Push to branch (git push origin feature/AmazingFeature)

Open a Pull Request

Code Style Guidelines
Follow C# coding conventions

Use meaningful variable names

Add comments for complex logic

Include XML documentation for public methods

📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

text
MIT License

Copyright (c) 2024 CyberSecurity Assistant

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
...
🙏 Acknowledgments
System.Speech - Microsoft's speech synthesis library

Microsoft.Data.SqlClient - SQL Server connectivity

WPF Community - UI design inspiration

Cybersecurity Community - For educating about online safety

📞 Contact & Support
Issues: GitHub Issues

Email: your.email@example.com

Twitter: @yourhandle

<div align="center">
Made with ❤️ for a safer internet

⬆ Back to Top

</div>
