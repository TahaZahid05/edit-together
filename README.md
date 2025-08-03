# Edit Together - Collaborative Text Editor

A real-time collaborative text editor that allows multiple users to edit documents simultaneously using advanced conflict resolution algorithms. Built with Qt (C++) for the frontend and Python WebSockets for the backend.

![Version](https://img.shields.io/badge/version-1.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## ✨ Features

- **Real-time Collaboration**: Multiple users can edit the same document simultaneously
- **Conflict-Free Editing**: Uses RGA (Replicated Growable Array) algorithm for seamless conflict resolution
- **Rich Text Formatting**: Support for bold, italic, underline, and text alignment
- **File Operations**: Create, open, save, and save as functionality
- **Client Identification**: Automatic assignment of unique client IDs (A, B, C, etc.)
- **Version Vector Synchronization**: Advanced synchronization mechanism for concurrent edits
- **Cross-platform**: Works on Windows, macOS, and Linux

## 🏗️ Architecture

- **Frontend**: Qt 6.x (C++) with rich text editing capabilities
- **Backend**: Python WebSocket server for real-time communication
- **Algorithm**: RGA (Replicated Growable Array) for conflict-free replicated data types (CRDT)
- **Networking**: WebSocket protocol for low-latency real-time updates

## 📋 Requirements

### Software Dependencies
- **Qt 6.x** with Qt WebSockets module
- **Python 3.7+** with the following packages:
  - `asyncio` (built-in)
  - `websockets`
  - `json` (built-in)

### System Requirements
- Windows 10+, macOS 10.14+, or Linux (Ubuntu 18.04+)
- Minimum 4GB RAM
- Network connectivity for collaboration features

## 🚀 Installation

### 1. Install Qt

1. Download **Qt Online Installer** from [qt.io](https://www.qt.io/download)
2. Create a Qt account and accept terms and conditions
3. Select **Custom Installation**
4. Choose **Qt 6.8.x** and ensure **Qt WebSockets** module is selected
5. Complete the installation

### 2. Install Python Dependencies

```bash
pip install websockets
```

### 3. Clone Repository

```bash
git clone https://github.com/TahaZahid05/edit-together.git
cd edit-together
```

## 🖥️ Usage

### Starting the Server

1. Open a terminal and navigate to the project directory
2. Start the Python WebSocket server:
   ```bash
   python server.py
   ```
3. You should see:
   ```
   WebSocket Server Started on ws://0.0.0.0:12345
   ```

### Running the Client Application

1. Open **Qt Creator**
2. Open the project file **`HelloWorld.pro`**
3. Build the project: **Build → Build All Projects**
4. Run the application: **Build → Run**

### Collaborating

1. Start the server (as described above)
2. Launch multiple instances of the client application
3. Each client will automatically connect and receive a unique ID (A, B, C, etc.)
4. Start editing - changes will be synchronized in real-time across all connected clients
5. Use the formatting toolbar for rich text features

## 📁 Project Structure

```
edit-together/
├── main.cpp                 # Application entry point
├── MainWindow.h/.cpp        # Main window and UI logic
├── ds2_proj.h              # RGA algorithm implementation
├── mainwindow.ui           # Qt UI design file
├── server.py               # Python WebSocket server
├── HelloWorld.pro          # Qt project configuration
├── resources.qrc           # Qt resources file
├── HelloWorld_en_GB.ts     # Translation file
└── icons/                  # Application icons
```

## 🔧 Technical Details

### RGA Algorithm

The Replicated Growable Array (RGA) is a conflict-free replicated data type (CRDT) that enables multiple users to edit a document simultaneously without conflicts. Key features:

- **Unique Identifiers**: Each character has a unique ID
- **Version Vectors**: Track the state of each client
- **Tombstone Deletion**: Deleted characters are marked but not removed
- **Deterministic Ordering**: Ensures consistent document state across all clients

### Network Protocol

- **WebSocket Communication**: Real-time bidirectional communication
- **JSON Messages**: Structured message format for operations
- **Client Management**: Server tracks connected clients and assigns unique IDs
- **Message History**: New clients receive full document state upon connection

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🎓 Academic Context

This project was developed as part of a research study on collaborative editing algorithms and conflict-free replicated data types (CRDTs). The implementation demonstrates practical applications of distributed systems concepts in real-time collaborative software.

## 🐛 Troubleshooting

### Common Issues

**Server won't start:**
- Ensure Python 3.7+ is installed
- Check if port 12345 is available
- Install websockets: `pip install websockets`

**Client won't connect:**
- Verify server is running
- Check firewall settings
- Ensure Qt WebSockets module is installed

**Build errors:**
- Update Qt to version 6.x
- Verify Qt WebSockets module is available
- Check C++17 compiler support

## 📞 Support

For questions, issues, or contributions, please open an issue on GitHub or contact the development team.
