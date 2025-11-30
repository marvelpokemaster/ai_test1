% --- UNIVERSAL PREAMBLE BLOCK ---
\documentclass[12pt, a4paper]{article}
\usepackage[a4paper, top=2.5cm, bottom=2.5cm, left=2.5cm, right=2.5cm]{geometry}
\usepackage{fontspec}
\usepackage[english]{babel}

% Set default/Latin font to Sans Serif (Noto Sans)
\setmainfont{Noto Sans}
\setsansfont{Noto Sans}

% Basic packages for formatting
\usepackage{titlesec}
\usepackage{setspace}
\usepackage{parskip}
\usepackage{graphicx}
\usepackage{fancyhdr}
\usepackage{enumitem}
\usepackage{hyperref}
\usepackage{float} % improved figure placement

% Adjust section formatting to match standard reports
\titleformat{\section}{\large\bfseries\uppercase}{\thesection}{1em}{}
\titleformat{\subsection}{\bfseries}{\thesubsection}{1em}{}

% Line spacing
\setstretch{1.5}

\begin{document}

% --- TITLE PAGE ---
\begin{titlepage}
    \centering
    \vspace*{1cm}
    
    % Logo Placeholder
    \begin{figure}[h]
        \centering
        \framebox{\parbox[c][4cm][c]{4cm}{\centering \textbf{UNIVERSITY LOGO}}}
    \end{figure}
    
    \vspace{0.5cm}
    {\Large \textbf{NullTrace – AI-Driven Opinion \& Feedback System}}
    
    \vspace{1.5cm}
    
    {\Large \textbf{Software Engineering Project Report}}
    
    \vspace{1cm}
    
    {\large BACHELOR of TECHNOLOGY}
    
    \vspace{0.5cm}
    
    {\large in}
    
    \vspace{0.5cm}
    
    {\large COMPUTER SCIENCE AND ENGINEERING}
    
    \vspace{1.5cm}
    
    \textbf{Submitted by}
    
    \vspace{0.5cm}
    
    \begin{tabular}{ll}
        \textbf{Student Name} & \textbf{AM.EN.U4CSE23XXX} \\
        \textbf{Student Name} & \textbf{AM.EN.U4CSE23XXX} \\
        \textbf{Student Name} & \textbf{AM.EN.U4CSE23XXX} \\
        \textbf{Student Name} & \textbf{AM.EN.U4CSE23XXX} \\
    \end{tabular}
    
    \vfill
    
    \textbf{AMRITA SCHOOL OF COMPUTING} \\
    \textbf{AMRITA VISHWA VIDYAPEETHAM} \\
    (Estd. U/S 3 of the UGC Act 1956) \\
    \textbf{AMRITAPURI CAMPUS, KOLLAM - 690525}
    
    \vspace{0.5cm}
    
    \textbf{DECEMBER 2025}
    
\end{titlepage}

% --- ABSTRACT ---
\newpage
\thispagestyle{plain}
\begin{center}
    \Large \textbf{ABSTRACT}
\end{center}
\vspace{0.5cm}

NullTrace is an AI-driven web application designed to collect user opinions and feedback, analyze them using NLP sentiment models, and store the results immutably using blockchain technology. The platform supports user login, anonymous submissions, real-time AI analysis, and an admin dashboard to view insights and aggregated analytics.

This project addresses the lack of structured, transparent feedback mechanisms in modern organizations by integrating a user-friendly frontend (Next.js), a secure backend (Flask), and a custom Proof-of-Work blockchain for data integrity.

\newpage

% --- TABLE OF CONTENTS ---
\tableofcontents
\newpage

% --- CONTENT SECTIONS ---

\section{INTRODUCTION}

\subsection{Overview}
Organizations often lack a structured way to collect real-time opinions or feedback and analyze them automatically. Manual analysis is time-consuming and often prone to human bias. NullTrace solves this by integrating a modern web stack with Artificial Intelligence and Blockchain technology.

The system combines a user-friendly frontend built with React/Next.js, a secure backend built with Python Flask, a sentiment extraction engine utilizing TextBlob and HuggingFace, and an immutable logging system using a custom blockchain.

\subsection{Objectives}
The primary objectives of the NullTrace system are as follows:
\begin{itemize}
    \item To collect opinions and feedback from users effectively.
    \item To use AI/NLP techniques to convert raw text into sentiment scores and ratings.
    \item To provide an admin dashboard that allows administrators to monitor system activity.
    \item To store all analytics immutably via blockchain to prevent tampering.
    \item To ensure secure authentication and role-based access control for all users.
\end{itemize}

\newpage

\section{PROBLEM DEFINITION}

In the current digital landscape, feedback collection is often disconnected from analysis. Traditional forms (like Google Forms or paper surveys) require manual data export and processing to gain insights. Furthermore, in scenarios where trust is paramount—such as voting on organizational changes or anonymous employee feedback—there is often no guarantee that the data has not been altered by database administrators.

NullTrace addresses these issues by:
\begin{enumerate}
    \item Automating the "Text-to-Insight" process using NLP.
    \item Removing the possibility of data tampering by hashing analytics results into a blockchain.
\end{enumerate}

\section{RELATED WORK}

Existing solutions for feedback collection, such as SurveyMonkey or Typeform, excel at data gathering but often lack deep, built-in sentiment analysis features without expensive enterprise subscriptions. Moreover, none of the standard commercial tools offer blockchain-backed immutability to guarantee that feedback remains unaltered once submitted.

NullTrace bridges this gap by offering a lightweight, custom solution that prioritizes both intelligence (via NLP) and integrity (via Blockchain), specifically tailored for organizational use cases where trust and transparency are critical.

\section{REQUIREMENTS}

The design of this project contains both hardware and software specifications required for development and deployment.

\subsection{Hardware Requirements}
\begin{itemize}
    \item \textbf{Processor:} Intel Core i5 or equivalent (Minimum).
    \item \textbf{RAM:} 8 GB or higher (Recommended for running local AI models).
    \item \textbf{Storage:} 256 GB SSD (Minimum).
    \item \textbf{Network:} Stable Internet connection for package installation and API access.
\end{itemize}

\subsection{Software Requirements}
\begin{itemize}
    \item \textbf{Frontend:} Next.js, React, Tailwind CSS.
    \item \textbf{Backend:} Python Flask.
    \item \textbf{AI/NLP Engines:} TextBlob, HuggingFace Transformers.
    \item \textbf{Database:} PostgreSQL.
    \item \textbf{Security:} SHA-256 for password hashing.
    \item \textbf{Blockchain:} Custom Python-based Proof-of-Work chain.
    \item \textbf{Version Control:} Git/GitHub.
\end{itemize}

\newpage

\section{PROPOSED SYSTEM}

\subsection{System Architecture}
NullTrace utilizes a 3-tier architecture to ensure modularity and scalability:
\begin{enumerate}
    \item \textbf{Presentation Layer (Frontend):} Built using Next.js, handling all user interactions, dashboards, and submission forms.
    \item \textbf{Application Layer (Backend API):} Developed in Flask, this layer handles routing, validation, authentication, and integrates the NLP engines.
    \item \textbf{Data Layer:} Consists of PostgreSQL for persistent relational data and a custom Blockchain for immutable analytics logging.
\end{enumerate}

% --- WORKFLOW DIAGRAM PLACEHOLDER ---
\begin{figure}[H]
  \centering
  \framebox{\parbox{0.9\textwidth}{\centering
    \vspace{4cm}
    \textbf{Workflow Diagram} \\
    \small\textit{Place your 'User $\rightarrow$ App $\rightarrow$ Blockchain' diagram here.}
    \vspace{4cm}
  }}
  \caption{NullTrace System Workflow}
  \label{fig:workflow}
\end{figure}

\subsection{Module Description}
The system is divided into five core modules:
\begin{itemize}
    \item \textbf{User Authentication Module:} Handles registration and login using SHA-256 hashing and manages user roles (Admin vs. User).
    \item \textbf{Opinion Submission Module:} Allows users to submit opinions for defined targets. The AI engine analyzes these immediately.
    \item \textbf{Feedback Collection Module:} Handles general feedback, converting text to sentiment and ratings.
    \item \textbf{Admin Dashboard Module:} Provides a statistical overview of the system, displaying opinions, feedback, and blockchain verification status.
    \item \textbf{Blockchain Module:} Every opinion/feedback result is added as a block containing a timestamp, rating, and sentiment, verifiable via a hash chain.
\end{itemize}

\subsection{System Design (UML \& Diagrams)}
\textbf{Data Flow (DFD Level 0):}
User $\rightarrow$ Web App $\rightarrow$ Backend API $\rightarrow$ Database + Blockchain.

\textbf{ER Diagram Entities:}
\begin{itemize}
    \item \texttt{Users}: Stores user credentials and roles.
    \item \texttt{Opinions}: Stores the text content and target ID.
    \item \texttt{Analytics}: links opinions to AI results.
    \item \texttt{BlockchainBlocks}: Stores the hash, previous hash, and payload.
\end{itemize}

\newpage

\section{RESULT AND ANALYSIS}

The system was successfully implemented and tested against the initial requirements.

\subsection{Performance}
The AI sentiment analysis engine (TextBlob) provided immediate feedback on text inputs, correctly classifying positive, negative, and neutral sentiments in real-time. The blockchain module successfully generated hashes for every new entry, ensuring a linked list of immutable records.

\subsection{Screenshots of Output}

% --- SCREENSHOT PLACEHOLDER 1 ---
\begin{figure}[H]
  \centering
  \framebox{\parbox{0.8\textwidth}{\centering
    \vspace{5cm}
    \textbf{Login Page Screenshot} \\
    \small\textit{Insert screenshot of Login/Register page.}
    \vspace{5cm}
  }}
  \caption{User Login Interface}
  \label{fig:login_screen}
\end{figure}

% --- SCREENSHOT PLACEHOLDER 2 ---
\begin{figure}[H]
  \centering
  \framebox{\parbox{0.8\textwidth}{\centering
    \vspace{5cm}
    \textbf{Admin Dashboard Screenshot} \\
    \small\textit{Insert screenshot of Admin Dashboard showing analytics.}
    \vspace{5cm}
  }}
  \caption{Admin Dashboard and Analytics View}
  \label{fig:dashboard_screen}
\end{figure}

\section{CONCLUSION}

NullTrace demonstrates the effective integration of AI-driven sentiment analysis, secure backend design, and blockchain immutability in a modern web system. By automating the analysis of user feedback and securing the results, the system provides a trustworthy platform for opinion gathering.

The system meets all primary objectives and serves as a solid foundation for future expansions, such as cloud deployment or advanced BERT-based models.

\section*{REFERENCES}
\addcontentsline{toc}{section}{References}

\begin{enumerate}
    \item Flask Documentation: \url{https://flask.palletsprojects.com/}
    \item PostgreSQL Documentation: \url{https://www.postgresql.org/docs/}
    \item TextBlob NLP Library: \url{https://textblob.readthedocs.io/}
    \item HuggingFace Transformers: \url{https://huggingface.co/}
    \item React/Next.js Documentation: \url{https://nextjs.org/docs}
\end{enumerate}

\newpage
\appendix
\section{SOURCE CODE}
The full source code for this project is available at the following GitHub repository:
\begin{center}
    \url{https://github.com/username/nulltrace}
\end{center}

\end{document}
