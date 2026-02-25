

# 🚀 Real-Time Collaborative Code Editor

## ✨ Features

* **Real-time Collaborative Editing**
  Multiple users can edit code simultaneously with live cursor tracking using **Y.js** and **WebSockets**.

* **Isolated Code Execution**
  Execute code safely in an isolated environment using **self-hosted Judge0**, powered by **AWS Auto Scaling Groups** and **AWS SQS queue-based scaling**.

* **AI-Powered Assistance**
  Get intelligent code suggestions via **OpenAI API** and interact with **Jarvis AI** through a real-time chat interface.

* **WebSocket Server**
  Custom-built, scalable WebSocket server for chat functionality with **Redis pub/sub** for horizontal scaling.

* **User Authentication**
  Secure user authentication and management using **Clerk**.

* **Modern UI**
  Clean and responsive interface built with **Next.js** and **Tailwind CSS**.

* **Scalable Architecture**
  Monorepo setup using **Turborepo** for efficient development, containerized with **Docker** and deployed using **AWS Auto Scaling Groups**.

---

## 🧰 Technology Stack

* **Frontend:** Next.js, React, Tailwind CSS, shadcn/ui
* **Real-time Collaboration:** Y.js, CodeMirror, WebSockets
* **Backend:** Node.js, Express
* **Database:** PostgreSQL, Prisma ORM
* **Execution Environment:** Self-hosted, containerized Judge0
* **Deployment:** Docker, AWS Auto Scaling
* **Scaling:** Redis pub/sub for WebSocket scaling
* **Authentication:** Clerk

---

## 🛠️ Deployment Architecture

### Current Setup

* **Web App**
  Full-stack application built with **Next.js**, **Tailwind CSS**, **shadcn/ui**, and **Prisma ORM**.
  Includes room creation, real-time collaborative code editor, chat, and dashboard.

* **WebSocket Server**
  Highly scalable WebSocket server capable of handling a large number of connections using **Redis pub/sub**.

* **Judge0**
  Self-hosted Judge0 deployed on **AWS Auto Scaling Groups** with **AWS SQS queue-based scaling**.
  Maintains approximately **10 messages** in the queue, scaling instances up when the queue grows and scaling down when it decreases.

* **AWS CloudWatch**
  Monitors instance and queue metrics to support auto-scaling policies.

* **Custom AMI**
  Custom Amazon Machine Image configured with **Judge0** and **CloudWatch** for consistent deployments.

---

## 📈 Scaling Infrastructure

* **AWS SQS Queue**
  Code submissions are enqueued to SQS and used to trigger scaling events.

* **Auto Scaling Policy**
  Configured to maintain around **10 messages** in the queue, adding instances when the queue increases and removing them when it decreases.

* **CloudWatch Integration**
  Each instance reports metrics to CloudWatch for monitoring and scaling decisions.

  Monorepo Structure

  code-collab/
├── apps/                 # Application packages
│   ├── web/              # Next.js frontend application
│   └── websocket/        # Custom WebSocket server
├── packages/             # Shared packages
│   ├── db/               # Prisma database schema and client
│   ├── ui/               # Shared UI components
│   ├── eslint-config/    # ESLint configuration
│   └── typescript-config/# TypeScript configuration
└── docker/               # Docker configuration files


