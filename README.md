# YouTube Video Analyzer

A full-stack application to analyze YouTube videos using Google Gemini API. The system extracts characters, scenes, and content from YouTube videos.

**Available as both Web Application and Electron Desktop App!**

## Project Structure

```
CloneVideoAI/
├── backend/          # Node.js/Express backend
├── frontend/         # React + Ant Design frontend
├── electron/         # Electron desktop app files
└── backend/key.txt   # API keys file
```

## Features

- Analyze single or multiple YouTube videos
- Extract characters, scenes, and content
- Random API key distribution for multiple videos
- MongoDB storage for analysis results
- Beautiful UI with Ant Design
- Real-time status updates
- **Desktop app support via Electron**

## Setup

### Backend

1. Navigate to backend folder:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Set up MongoDB (default: mongodb://localhost:27017/)

4. Run the server:
```bash
npm start
```

For development with auto-reload:
```bash
npm run dev
```

The API will run on http://localhost:8000

### Frontend

1. Navigate to frontend folder:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Run the development server:
```bash
npm run dev
```

The frontend will run on http://localhost:3000

## Usage

### Web Application Mode

1. Start MongoDB
2. Start the backend server (port 8000)
3. Start the frontend (port 5173)
4. Enter YouTube URLs (one per line) in the input field
5. Click "Analyze Videos" to process
6. View results in the table below

### Electron Desktop App Mode

#### Development Workflow (Recommended)

**Cách 1: Chạy riêng biệt (Khuyến nghị cho debug)**

```bash
# Terminal 1: Chạy backend server (để check/debug)
npm run dev:backend

# Terminal 2: Chạy frontend dev server
npm run dev:frontend

# Terminal 3: Chạy Electron app
npm run electron:dev
```

**Cách 2: Chạy backend + frontend cùng lúc**

```bash
# Terminal 1: Chạy backend + frontend
npm run dev

# Terminal 2: Chạy Electron app
npm run electron:dev
```

#### Setup

1. **Install all dependencies:**
```bash
npm run install:all
```

2. **Setup MongoDB:**
   - Make sure MongoDB is running on `localhost:27017`
   - Or set `MONGO_URI` in `backend/.env`

3. **Setup API Keys:**
   - Create `backend/key.txt` file
   - Add your Google Gemini API keys (one per line)

#### Build Desktop App

```bash
# Build for current platform
npm run electron:build

# Build for specific platform
npm run electron:build -- --win    # Windows
npm run electron:build -- --mac    # macOS
npm run electron:build -- --linux  # Linux
```

#### Electron App Features

- **Automatic Backend Detection**: Electron automatically detects if backend is running
- **Standalone Desktop Application**: Can run with or without separate server processes
- **Cross-platform Support**: Windows, macOS, Linux
- **Development Mode**: Hot reload for both frontend and backend
- **Production Build**: Create distributable installers


## API Endpoints

- `POST /api/analyze` - Analyze single video
- `POST /api/analyze/bulk` - Analyze multiple videos in parallel
- `GET /api/videos` - Get all analyzed videos
- `DELETE /api/videos/{video_id}` - Delete a video

## Electron App Features

- Standalone desktop application
- Embedded backend server (no separate server process needed)
- Cross-platform support (Windows, macOS, Linux)
- Automatic API key management
- Local MongoDB integration

