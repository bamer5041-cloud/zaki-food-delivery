# 😂 Random Joke Generator

A simple yet fun joke generator application that fetches random jokes from multiple external APIs. Built with Node.js/Express backend and vanilla JavaScript frontend.

## Features

- 🎭 Multiple joke APIs (Official Joke API, JokeAPI, Dad Jokes)
- 🎯 Random source selection for variety
- 🎨 Beautiful and responsive UI
- ⚡ Fast API calls
- 🔄 Real-time updates
- 📱 Mobile-friendly design

## API Endpoints

### Backend Endpoints

```
GET /api/joke/random              - Get joke from Official Joke API
GET /api/joke/random-jokeapi      - Get joke from JokeAPI
GET /api/joke/dad-joke            - Get dad joke
GET /api/joke/random-source       - Get joke from random API source
GET /api/health                   - Health check endpoint
```

## Installation

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn

### Setup

1. **Install dependencies:**
   ```bash
   cd joke-generator
   npm install
   ```

2. **Create `.env` file:**
   ```bash
   cp .env.example .env
   ```

3. **Configure environment variables** (optional):
   ```env
   PORT=3001
   NODE_ENV=development
   ```

## Running the Application

### Start the Backend Server

```bash
npm start
```

The API will be running at `http://localhost:3001`

### Development Mode (with auto-reload)

```bash
npm run dev
```

### Open Frontend

Open `index.html` in your browser or serve it via:

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (http-server)
npx http-server
```

Then visit `http://localhost:8000` (or your server URL)

## Usage

### Via Frontend UI

1. Click "Get Random Joke" button to fetch a joke from a random source
2. Use specific buttons to get jokes from particular APIs
3. Each joke displays with source attribution

### Via API (cURL)

```bash
# Get random joke
curl http://localhost:3001/api/joke/random

# Get joke from JokeAPI
curl http://localhost:3001/api/joke/random-jokeapi

# Get dad joke
curl http://localhost:3001/api/joke/dad-joke

# Get from random source
curl http://localhost:3001/api/joke/random-source

# Health check
curl http://localhost:3001/api/health
```

### Via JavaScript Fetch

```javascript
// Get random joke
fetch('http://localhost:3001/api/joke/random-source')
  .then(res => res.json())
  .then(data => console.log(data.joke));

// Get specific type
fetch('http://localhost:3001/api/joke/dad-joke')
  .then(res => res.json())
  .then(data => console.log(data.joke));
```

## Response Format

### Setup-Punchline Format

```json
{
  "success": true,
  "source": "Official Joke API",
  "joke": {
    "setup": "Why don't scientists trust atoms?",
    "punchline": "Because they make up everything!",
    "type": "general"
  }
}
```

### Single-Line Format

```json
{
  "success": true,
  "source": "I Can Haz Dad Jokes",
  "joke": {
    "content": "Why don't eggs tell jokes? They'd crack each other up."
  }
}
```

## External APIs Used

1. **Official Joke API**
   - URL: `https://official-joke-api.appspot.com/random_joke`
   - Format: Setup + Punchline

2. **JokeAPI**
   - URL: `https://v2.jokeapi.dev/joke/Any?type=single`
   - Format: Single-line jokes
   - Categories: Multiple

3. **I Can Haz Dad Jokes**
   - URL: `https://icanhazdadjoke.com/?format=json`
   - Format: Dad jokes (single-line)

## Project Structure

```
joke-generator/
├── server.js           # Express backend
├── index.html          # Frontend UI
├── package.json        # Dependencies
├── .env.example        # Environment template
└── README.md          # Documentation
```

## Technologies

- **Backend**: Express.js, Axios
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Middleware**: CORS
- **Development**: Nodemon

## Error Handling

The application handles errors gracefully with:
- Try-catch blocks on API calls
- User-friendly error messages
- Status indicators in frontend

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## Future Enhancements

- [ ] Add more API sources
- [ ] Filter jokes by category
- [ ] Save favorite jokes
- [ ] Share jokes on social media
- [ ] Joke rating system
- [ ] Dark mode
- [ ] Multi-language support

## License

MIT

## Author

Zaki Food Delivery Team

## Support

For issues or suggestions, please open an issue on GitHub.

---

**Made with ❤️ for Zaki Food Delivery**
