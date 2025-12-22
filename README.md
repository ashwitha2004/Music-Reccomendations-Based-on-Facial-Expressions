# 🎶 Music Recommendations Based on Facial Expressions

<div align="center">

<!-- TODO: Add project logo (e.g., an icon representing music and emotions) -->
<!-- ![Logo](assets/logo.png) -->


**Experience music tailored to your mood – real-time recommendations powered by AI facial expression analysis.**

<!-- TODO: Add live demo link if available -->
<!-- [Live Demo](https://demo-link.com) | -->
<!-- TODO: Add documentation link if available -->
<!-- [Documentation](https://docs-link.com) -->

</div>

## 📖 Overview

This project is a web application that leverages advanced computer vision and machine learning techniques to provide real-time music recommendations based on a user's facial expressions. It captures live video from the user's webcam, detects facial expressions (e.g., happy, sad, angry), and then uses the detected emotion to fetch and suggest suitable music tracks via the Spotify API.

## Screenshots
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/198ae767-df66-4a22-a13f-f7746810a08e" />

Designed for an intuitive user experience, this application aims to enhance personal music listening by dynamically adapting playlists to the user's current emotional state, creating a more personalized and immersive audio journey.

## ✨ Features

-   🎯 **Real-time Facial Expression Detection**: Utilizes Haar cascades for robust face detection in live video streams.
-   🧠 **AI-Powered Emotion Recognition**: Employs a pre-trained deep learning model (`model.h5`) to classify emotions from facial expressions.
-   🎵 **Dynamic Music Recommendations**: Generates music suggestions tailored to the detected emotion (e.g., upbeat for happy, calming for sad).
-   🎧 **Spotify API Integration**: Connects with Spotify to fetch relevant tracks and artists based on emotional cues via `spotipy`.
-   🌐 **Interactive Web Interface**: A user-friendly Flask-based web application to display video feed, detected emotion, and music recommendations.
-   📦 **Modular Design**: Clear separation of concerns for camera processing, emotion model inference, and Spotify API interaction.

## 🛠️ Tech Stack

**Backend & ML:**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)

![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)

![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)

![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white)

![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

![Spotipy](https://img.shields.io/badge/Spotipy-1DB954?style=for-the-badge&logo=spotify&logoColor=white)

**Frontend:**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

## 🚀 Quick Start

Follow these steps to get the project up and running on your local machine.

### Prerequisites

-   **Python 3.x**: Ensure you have Python installed. You can download it from [python.org](https://www.python.org/downloads/).
-   **Spotify Developer Account**: Required to obtain API credentials (Client ID and Client Secret) for `Spotipy`. Register at [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/).

### Installation

1.  **Clone the repository**

    ```bash
    git clone https://github.com/ashwitha2004/Music-Reccomendations-Based-on-Facial-Expressions.git
    cd Music-Reccomendations-Based-on-Facial-Expressions
    ```

2.  **Create a virtual environment** (recommended)

    ```bash
    python -m venv myenv
    source myenv/bin/activate  # On Windows: myenv\Scripts\activate
    ```

3.  **Install dependencies**

    ```bash
    pip install -r requirements.txt
    ```

4.  **Environment setup**

    Create a `.env` file in the root directory of the project and add your Spotify API credentials:

    ```bash
    cp .env.example .env # If .env.example exists, otherwise create it
    ```

    Open the newly created `.env` file and populate it with your Spotify Client ID and Client Secret:

    ```
    SPOTIPY_CLIENT_ID="YOUR_SPOTIFY_CLIENT_ID"
    SPOTIPY_CLIENT_SECRET="YOUR_SPOTIFY_CLIENT_SECRET"
    # SPOTIPY_REDIRECT_URI="http://localhost:5000/callback" # Only if using user authentication flow
    ```
    *Note: The `Spotipy.py` file implies direct client credentials flow or implicit grant flow, but for development and simpler use cases, setting `SPOTIPY_CLIENT_ID` and `SPOTIPY_CLIENT_SECRET` as environment variables is often sufficient for basic access token retrieval. Adjust if full user authentication (requiring `SPOTIPY_REDIRECT_URI` and OAuth flow) is implemented.*

5.  **Start development server**

    ```bash
    python app.py
    ```

6.  **Open your browser**

    Visit `http://localhost:5000`

## 📁 Project Structure

```
Music-Reccomendations-Based-on-Facial-Expressions/
├── app.py                           # Main Flask application entry point
├── camera.py                        # Handles webcam feed, face detection, and emotion prediction
├── Spotipy.py                       # Manages Spotify API integration and music recommendations
├── train.py                         # Script for training the emotion recognition model (if needed)
├── utils.py                         # Utility functions
├── model.h5                         # Pre-trained deep learning model for emotion recognition
├── haarcascade_frontalface_default.xml # Haar cascade classifier for face detection
├── requirements.txt                 # Python dependencies
├── LICENSE                          # Project license file
├── README.md                        # Project README file
├── .env.example                     # Example environment variables (create .env from this)
├── myenv/                           # Python virtual environment (ignored by Git)
├── __pycache__/                     # Python cache directory (ignored by Git)
├── songs/                           # Directory potentially for storing song data or playlists (TODO: Clarify purpose)
├── static/                          # Static assets (CSS, JS, images) for the frontend
│   ├── css/
│   ├── js/
│   └── img/
└── templates/                       # HTML templates (Jinja2) for the web interface
    ├── index.html                   # Main page template
    └── video_feed.html              # Template for video streaming (if separate)
```

## ⚙️ Configuration

### Environment Variables
For `Spotipy.py` to function correctly and access the Spotify API, the following environment variables are required:

| Variable | Description | Default | Required |

|----------|-------------|---------|----------|

| `SPOTIPY_CLIENT_ID` | Your Spotify Application Client ID. | None | Yes |

| `SPOTIPY_CLIENT_SECRET` | Your Spotify Application Client Secret. | None | Yes |

These variables should be set in a `.env` file in the project's root directory.

## 🔧 Development

### Available Scripts
The primary script for running the application is `app.py`:

| Command | Description |

|---------|-------------|

| `python app.py` | Starts the Flask development server and makes the application accessible via `http://localhost:5000`. |

| `python train.py` | If you wish to retrain or fine-tune the emotion recognition model using your own dataset. |

### Development Workflow
To contribute or make changes:
1.  Ensure your virtual environment is activated (`source myenv/bin/activate`).
2.  Make code changes in the relevant Python files (`app.py`, `camera.py`, `Spotipy.py`, `utils.py`) or frontend files (`static/`, `templates/`).
3.  Run `python app.py` to see your changes reflected in the browser.
4.  For model training, prepare your dataset and execute `python train.py`.

## 🧪 Testing

This repository currently does not contain explicit test files (e.g., using `pytest`).
To test the application:
1.  Ensure the development server is running (`python app.py`).
2.  Navigate to `http://localhost:5000` in your web browser.
3.  Allow camera access.
4.  Observe facial expression detection and verify that music recommendations change based on your mood.
5.  Check the server console for any errors or diagnostic messages.

## 🚀 Deployment

The application is a standard Flask web application.

### Production Build
There isn't a "build" step in the traditional frontend sense. The Python code runs directly, and static assets are served as-is.

### Deployment Options
-   **Gunicorn/uWSGI + Nginx**: For production deployment, it's recommended to serve the Flask application using a WSGI server like Gunicorn or uWSGI, fronted by a web server like Nginx.
-   **Cloud Platforms**: Can be deployed on platforms like Heroku, AWS Elastic Beanstalk, Google Cloud App Engine, or a custom VPS by ensuring all dependencies are met and environment variables are configured.

## 🤝 Contributing

We welcome contributions! If you'd like to improve this project, please consider the following:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/AmazingFeature`).
3.  Make your changes and ensure they adhere to existing code style.
4.  Commit your changes (`git commit -m 'Add some AmazingFeature'`).
5.  Push to the branch (`git push origin feature/AmazingFeature`).
6.  Open a Pull Request.

Please see our [Contributing Guide](CONTRIBUTING.md) (TODO: Create if not exists) for detailed instructions.

## 📄 License

This project is licensed under the [MIT License](LICENSE) - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

-   **OpenCV**: For robust computer vision functionalities, especially Haar cascades.
-   **TensorFlow/Keras**: For the deep learning framework used in emotion recognition.
-   **Flask**: For providing a lightweight web framework.
-   **Spotipy**: For seamless integration with the Spotify API.
-   The research community in facial expression recognition and deep learning.

## 📞 Support & Contact

-   🐛 Issues: [GitHub Issues](https://github.com/ashwitha2004/Music-Reccomendations-Based-on-Facial-Expressions/issues)
-   📧 For direct inquiries: ashwitha2004@example.com <!-- TODO: Replace with actual contact email if available -->

---

<div align="center">

**⭐ Star this repo if you find it helpful!**

Made with ❤️ by ashwitha2004

</div>

