# f(x) Protocol Quiz Application

A comprehensive quiz application built with Streamlit to test knowledge about the f(x) Protocol ecosystem, a decentralized stablecoin solution built on Ethereum.

## 📋 Features

- **Interactive Quiz**: 10 randomly selected True/False questions from a pool of 59
- **Real-time Feedback**: Immediate visual feedback with color-coded responses
- **Timed Explanations**: Detailed explanations shown for 3 seconds after each answer
- **Persistent Leaderboard**: Tracks both high scores and cumulative scores
- **User Management**: Username-based score tracking
- **Replay Functionality**: Ability to restart the quiz
- **Responsive Design**: Clean, modern UI built with Streamlit

## 🎯 Quiz Content

The quiz covers comprehensive topics about f(x) Protocol including:
- DeFi mechanics and stablecoin solutions
- Tokenomics (FXN, fxUSD, veFXN governance token)
- Stability pools and liquidity management
- Base layer-2 network expansion
- Community programs and incentives
- Historical events and protocol development

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- pip (Python package installer)

### Installation

#### Option 1: Automated Setup (Recommended)

1. **Clone or download the project files**

2. **Run the automated setup script**
   ```bash
   # On macOS/Linux
   ./setup.sh

   # Or manually:
   # chmod +x setup.sh && ./setup.sh
   ```

#### Option 2: Manual Setup

1. **Clone or download the project files**

2. **Create a virtual environment**
   ```bash
   # On macOS/Linux
   python3 -m venv venv

   # On Windows
   python -m venv venv
   ```

3. **Activate the virtual environment**
   ```bash
   # On macOS/Linux
   source venv/bin/activate

   # On Windows
   venv\Scripts\activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Run the application**
   ```bash
   streamlit run appl.py
   ```

6. **Open your browser**

   The application will be available at: `http://localhost:8501`

## 📖 Usage

1. **Enter Username**: Provide your username to start the quiz
2. **Answer Questions**: Click "True" or "False" for each question
3. **View Feedback**: See immediate color-coded feedback (green for correct, red for incorrect)
4. **Read Explanations**: Detailed explanations appear for 3 seconds after each answer
5. **Check Score**: View your current score in the top-right corner
6. **Complete Quiz**: See final results and leaderboard ranking
7. **Replay**: Click the "Replay" button to take the quiz again

## 🏗️ Project Structure

```
ibe/
├── appl.py                 # Main Streamlit application
├── question_model.py       # Question data model
├── quiz_brain.py          # Quiz logic and game flow
├── data.py                # Question data and leaderboard functionality
├── username.py            # Username management
├── leaderboard.py         # Leaderboard data persistence
├── leaderboard.json       # Persistent leaderboard data
├── requirements.txt       # Python dependencies
├── setup.sh              # Automated setup script
└── README.md             # This file
```

## 🛠️ Development

### Running in Development Mode

For better performance during development, you can install Watchdog:

```bash
pip install watchdog
```

### Customizing Questions

Questions are stored in base64-encoded format in `data.py`. To add new questions:

1. Edit the `encoded_question_data` list in `data.py`
2. Each question should have:
   - `question`: Base64-encoded question text
   - `correct_answer`: "True" or "False"
   - `explanation`: Base64-encoded explanation text

### Modifying Quiz Settings

To change the number of questions per quiz, modify line 36 in `appl.py`:

```python
selected_questions = random.sample(question_data, k=min(10, len(question_data)))
```

Change the number `10` to your desired question count.

## 📊 Leaderboard System

The application maintains a persistent leaderboard that tracks:

- **High Score**: Best single quiz performance
- **Cumulative Score**: Total points across all attempts

Scores are automatically saved to `leaderboard.json`.

## 🐛 Troubleshooting

### Common Issues

1. **Port 8501 already in use**
   ```bash
   # Run on a different port
   streamlit run appl.py --server.port 8502
   ```

2. **Permission errors**
   ```bash
   # Ensure proper permissions for leaderboard.json
   chmod 644 leaderboard.json
   ```

3. **Virtual environment issues**
   ```bash
   # Deactivate and recreate
   deactivate
   rm -rf venv
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

### Performance Optimization

For better performance, especially on slower systems:

```bash
# Run in headless mode
streamlit run appl.py --server.headless true

# Disable usage statistics
streamlit run appl.py --browser.gatherUsageStats false
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the MIT License.

## 📞 Support

For questions or issues related to the f(x) Protocol quiz:
- Check the troubleshooting section above
- Ensure all dependencies are properly installed
- Verify you're using Python 3.8+

---

**Note**: This application is for educational purposes to help users learn about the f(x) Protocol ecosystem. Always do your own research and understand the risks involved in DeFi protocols.
