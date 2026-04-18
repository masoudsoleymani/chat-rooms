# Chat Rooms

A full-stack chat application built with Next.js 15 and AWS Amplify Gen 2, featuring two types of chat rooms:
- **AI Chat Room** - Chat with AI powered by Amazon Bedrock (Claude 3.5 Sonnet)
- **Messenger Chat Room** - Real-time multi-user chat using AWS AppSync Event API

## Tech Stack

### Frontend
- **Framework:** Next.js 15.2.4 (App Router)
- **UI Library:** React 19 with TypeScript
- **Styling:** Tailwind CSS with shadcn/ui components
- **State Management:** AWS Amplify UI React components

### Backend (AWS Amplify Gen 2)
- **Authentication:** Amazon Cognito User Pool
- **Database:** Amazon DynamoDB (via Amplify Data)
- **Real-time Events:** AWS AppSync Event API with "chat" namespace
- **AI Integration:** Amazon Bedrock (Claude 3.5 Sonnet model)
- **Infrastructure:** AWS CDK (defined in TypeScript)

### Key Dependencies
- `@aws-amplify/backend` - Backend definition
- `@aws-amplify/ui-react` - UI components
- `@aws-amplify/ui-react-ai` - AI chat components
- `aws-amplify` - Client library

## Getting Started

### Prerequisites

- Node.js 22+ installed
- AWS account with:
  - [AWS Amplify local setup](https://docs.amplify.aws/react/start/account-setup/) configured
  - Claude 3.5 Sonnet model enabled in Amazon Bedrock

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd messenger-app-amplify
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the local backend (sandbox):
   ```bash
   npx ampx sandbox
   ```

4. In a separate terminal, start the Next.js development server:
   ```bash
   npm run dev
   ```

5. Open [http://localhost:3000](http://localhost:3000) in your browser

## Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start Next.js dev server with Turbopack |
| `npm run build` | Build for production |
| `npm run start` | Start production server |
| `npm run lint` | Run ESLint |
| `npx ampx sandbox` | Start local Amplify backend |

## Project Structure

```
├── amplify/                 # AWS Amplify backend
│   ├── auth/               # Cognito authentication
│   ├── data/               # DynamoDB schema (Rooms, Messages)
│   └── backend.ts          # Backend configuration with AppSync Events
├── app/                    # Next.js App Router pages
│   ├── ai-room/           # AI chat room page
│   ├── add-room/          # Create new room page
│   └── page.tsx           # Home/room list page
├── components/             # React components
│   ├── AIRoom.tsx         # AI chat component
│   ├── ChatArea.tsx       # Message display
│   ├── MessengerApp.tsx   # Main chat app
│   └── ui/                # shadcn/ui primitives
└── utils/                  # Client and server utilities
```

## Deployment

To deploy to production on AWS Amplify Hosting, follow the [Next.js + Amplify guide](https://docs.aws.amazon.com/amplify/latest/userguide/getting-started-next.html).
