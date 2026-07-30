# Collab Canvas

A real-time collaborative drawing app. Multiple people can draw on the same canvas simultaneously from their own devices — no sign-up required.

## How it works

### Rooms

Every drawing session happens inside a **room**. A room is created instantly with a unique 9-character code (format: `ABC-DEF-GHI`). Anyone with the code can join the same room and see the canvas in real time. Rooms are ephemeral — they exist as long as people are connected.

### Drawing

The canvas supports 9 tools:

| Tool | What it does |
|------|-------------|
| **Pencil** | Fine, precise strokes |
| **Brush** | Wider strokes with soft edges |
| **Shading** | Wide, low-opacity strokes for shading effects |
| **Marker** | Medium strokes with semi-transparency |
| **Eraser** | Removes strokes by drawing over them (paints white) |
| **Line** | Click + drag to draw a straight line |
| **Rectangle** | Click + drag to draw a rectangle outline |
| **Circle** | Click + drag to draw an ellipse outline |
| **Arrow** | Draws a directional arrow |
| **Flood fill** | Fills a bounded area with the selected color |
| **Eyedropper** | Picks a color from the canvas |

Each tool has adjustable **stroke size** (1–60px) and **opacity**. You can choose from preset color swatches or pick any custom color.

### Real-time sync

When you draw, every stroke is broadcast to all other users in the room via a **WebSocket** connection. Other users see your strokes appear as you make them — no refreshing needed.

The sync covers:
- Freehand strokes (throttled for performance)
- Shapes (lines, rectangles, circles, arrows)
- Flood fill actions
- Undo / Redo
- Clear canvas
- Background color changes

When someone joins a room, the full canvas state is sent to them so they're up to date immediately.

### Connection indicator

A sidebar indicator shows your connection status:
- **Green dot** + user count: connected with others in the room
- **Yellow dot**: connected but alone (waiting)
- **Red/grey dot**: disconnected

### Additional features

- **Download** the canvas as a PNG image
- **Undo / Redo** any action
- **Copy room code** by clicking the badge — share it with anyone to collaborate
- **Background color** can be changed independently
- **Works on mobile** — touch events and responsive layout with a bottom toolbar
- **Installable** as a Progressive Web App
