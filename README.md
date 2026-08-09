# Quickstart AI Chatbot Widget

A customizable, secure React chatbot widget component. It enables business owners to easily integrate a custom AI-driven chatbot widget on their website by passing a token and their API endpoint.

## Installation

```bash
npm install quickstart-ai-chatbot-widget
```

## Usage

```jsx
import React from 'react';
import { ChatBot } from 'quickstart-ai-chatbot-widget';

function App() {
  return (
    <div>
      <ChatBot 
        token="YOUR_BUSINESS_TOKEN" 
        apiUrl="https://quick-start-ai-backend.vercel.app/api/v1" // Your quickstart-ai backend URL
        theme="primary"
        wantToShowSuggestions={true}
      />
    </div>
  );
}

export default App;
```

## Props Customization

You can use the following props to customize the widget's behavior and appearance:

| Prop Name | Type | Description |
|-----------|------|-------------|
| `token` | string | **(Required)** The unique integration token key for your registered business. |
| `apiUrl` | string | **(Required)** The API backend endpoint where chat session and messages are processed. |
| `toggleBtncolor` | string | The icon color of the floating chatbot button (e.g., `white` or `#ffffff`). |
| `toggleBtnBgColor` | string | The background color of the floating chatbot button (e.g., `#007bff`). |
| `icon` | ReactNode | Custom icon for the closed state button (defaults to `TbMessageChatbot`). |
| `position` | 'left' \| 'right' | The position of the chatbot button and window on the screen (default: `right`). |
| `animate` | boolean | Enables a subtle bounce animation on the closed toggle button (default: `true`). |
| `theme` | 'primary' \| 'secondary' \| 'professional' \| 'tech' | The UI theme color scheme for the widget (default: `primary`). |
| `wantToShowSuggestions` | boolean | If enabled, displays alternative dynamic suggestion questions when the chatbot cannot fully address a query (default: `false`). |

---

## 🔒 Security & Privacy Transparency

This library acts strictly as a UI wrapper client for your backend chatbot service.
* **PII Collection**: When a user starts a chat, they are prompted for their name and email. This information is used solely to generate a session ID for backend context management.
* **Data Transmission**: All submitted names, emails, and chat messages are sent exclusively to the endpoint you configure in the `apiUrl` prop. No telemetry or data is sent to third-party servers.
* **Authentication**: All API requests are verified using the business-specific `token` prop.
