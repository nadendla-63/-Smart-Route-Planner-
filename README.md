# Smart Route Planner 🚀

A web-based route planning application using Dijkstra's shortest path algorithm. Find the shortest distances between cities in a graph network.

## Features

- 💡 **Dijkstra's Algorithm**: Efficient shortest path calculation
- 🎨 **Modern UI**: Clean and responsive web interface
- 📊 **Interactive Graph**: Configure custom distance matrices
- 📈 **Visualization**: View all routes and distances from a source
- 📱 **Responsive Design**: Works on desktop and mobile devices
- ⚡ **Real-time Calculation**: Instant path computation
- 🎯 **Path Reconstruction**: See complete paths with distances

## Tech Stack

- **Backend**: Node.js + Express.js
- **Frontend**: HTML5 + CSS3 + Vanilla JavaScript
- **Algorithm**: Dijkstra's Shortest Path Algorithm

## Prerequisites

- Node.js (v14 or higher)
- npm (comes with Node.js)

## Installation

1. **Clone/Download the project**
   ```bash
   cd /Users/shanmukh_0063/CCC/smart-route-planner
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

## Running the Application

### Development Mode
```bash
npm start
```

The server will start on `http://localhost:3000`

### With Auto-Reload (Requires nodemon)
```bash
npm run dev
```

## Usage

1. **Open the Application**
   - Navigate to `http://localhost:3000` in your web browser

2. **Configure the Graph**
   - Enter the number of cities (2-10)
   - Click "Generate Graph"
   - Fill in the distance matrix with distances between cities
   - Use 0 for no direct connection

3. **Calculate Shortest Paths**
   - Select a source city
   - Click "Calculate Shortest Paths"
   - View results in the output panel

4. **View Results**
   - See all routes from the source city
   - View distances and complete paths
   - Check statistics and visualizations

## Example Graph

```
     0 ──5──→ 1
     │        │
     10      3
     │        │
     ↓        ↓
     2 ──2──→ 3
```

Enter this as distance matrix:
```
From City 0: [0, 5, 10, 0]
From City 1: [0, 0, 0, 3]
From City 2: [0, 0, 0, 2]
From City 3: [0, 0, 0, 0]
```

## API Endpoints

### POST /api/shortest-paths
Calculate shortest paths using Dijkstra's algorithm

**Request Body:**
```json
{
  "graph": [[0, 5, 10, 0], [0, 0, 0, 3], [0, 0, 0, 2], [0, 0, 0, 0]],
  "source": 0
}
```

**Response:**
```json
{
  "source": 0,
  "routes": [
    {
      "destination": 0,
      "distance": 0,
      "path": [0]
    },
    {
      "destination": 1,
      "distance": 5,
      "path": [0, 1]
    },
    ...
  ],
  "algorithm": "Dijkstra"
}
```

### GET /api/health
Health check endpoint

**Response:**
```json
{
  "status": "Server is running"
}
```

## Project Structure

```
smart-route-planner/
├── src/
│   └── app.js              # Backend server with Dijkstra implementation
├── public/
│   ├── index.html          # Main HTML file
│   ├── styles.css          # Styling
│   └── script.js           # Frontend JavaScript
├── package.json            # Dependencies
└── README.md              # This file
```

## Algorithm Explanation

**Dijkstra's Algorithm** finds the shortest path from a source vertex to all other vertices in a graph.

**Time Complexity**: O(V² + E) where V = vertices, E = edges
**Space Complexity**: O(V)

### Steps:
1. Initialize distances to all vertices as infinity except source (0)
2. Mark all vertices as unvisited
3. While there are unvisited vertices:
   - Find unvisited vertex with minimum distance
   - Mark it as visited
   - Update distances of adjacent unvisited vertices
4. Return shortest distances and paths

## Features in Detail

### Input Validation
- Validates graph configuration
- Checks source node validity
- Handles unreachable nodes

### Error Handling
- Network error handling
- Invalid input detection
- Server error messages

### User Experience
- Real-time feedback with notifications
- Loading states
- Clear error messages
- Responsive design

## Browser Support

- Chrome (Latest)
- Firefox (Latest)
- Safari (Latest)
- Edge (Latest)

## Performance

- Graph size: Up to 10 nodes
- Instant calculation for small graphs
- Efficient path reconstruction
- Optimized memory usage

## Troubleshooting

**Port 3000 already in use?**
```bash
# Kill the process using port 3000
# macOS: lsof -ti:3000 | xargs kill -9
# Linux: fuser -k 3000/tcp
# Windows: netstat -ano | findstr :3000
```

**Dependencies not installing?**
```bash
rm -rf node_modules package-lock.json
npm install
```

**Can't connect to server?**
- Check if server is running on `http://localhost:3000`
- Check browser console for errors
- Verify network connection

## Future Enhancements

- [ ] Support for larger graphs (100+ nodes)
- [ ] Graph visualization with D3.js/Cytoscape
- [ ] Multiple algorithm comparison (A*, Bellman-Ford)
- [ ] Route optimization features
- [ ] Distance/time-based routing
- [ ] Database integration for persistent graphs
- [ ] Export results as PDF/CSV
- [ ] Real-time GPS integration

## License

MIT License - Feel free to use this project for educational purposes

## Author

Created as a Smart Route Planner demonstration using Dijkstra's Algorithm

## Support

For issues or questions, please check the code comments or review the API documentation above.

---

**Made with ❤️ using Node.js + Express + Vanilla JavaScript**
