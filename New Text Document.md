# Ollama API Endpoints

## Available Endpoints
- `POST /api/generate` - For text completion
- `POST /api/chat` - For chat-style interactions
- `GET /api/tags` - List available models
- `POST /api/pull` - Download models
- `POST /api/show` - Shows detailed info about a specific model
- `GET /api/version` - Check if Ollama is running and get version

## Response Formats

### Ollama Response Format
```json
{
  "model": "llava",
  "created_at": "2023-12-12T14:13:43.416799Z",
  "message": {
    "role": "assistant",
    "content": "response text"
  },
  "done": true
}
```

### OpenAI Response Format
```json
{
  "choices": [
    {
      "message": {
        "content": "response text"
      }
    }
  ]
}
```

## Response Access

### OpenAI Response Access
```javascript
const data = await response.json();
return data.choices[0].message.content;
```

### Ollama Response Access
```javascript
const data = await response.json();
return data.message.content;
```

## Example Code Implementation
```javascript
const response = await fetch(`${baseURL.value}/api/chat`, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    model: "llava", // or another vision model like "llava:7b", "llava:13b", "bakllava"
    messages: [
      {
        role: "user",
        content: instruction,
        images: [imageBase64URL.split(',')[1]] // Remove data:image/jpeg;base64, prefix
      }
    ],
    stream: false
  })
});