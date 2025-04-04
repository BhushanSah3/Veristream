# Veristream

Veristream is a Next.js project with a Python backend, fully containerized using Docker. It is deployed on Microsoft Azure and can be accessed live at:  
[http://veristream.eastus.azurecontainer.io:3000/]
(http://veristream.eastus.azurecontainer.io:3000/)

## Project Structure

```
/veristream
├── model
│    ├── analyze_text.py
│    ├── fact_checker.py
│    ├── Dockerfile.backend
│    ├── requirements.txt
├── app
│    ├── Dockerfile.frontend
│    ├── layout.js
│    ├── page.js
├── package.json
├── docker-compose.yml
├── transcribe_video.py
```

- **model/**: Contains the Python backend code and its Dockerfile.
- **app/**: Contains the Next.js frontend source files and its Dockerfile.
- **transcribe_video.py**: A Python script used by the frontend.
- **docker-compose.yml**: Orchestrates both services.

---

## Using the Live Deployment

To use Veristream without any local setup, simply visit the live URL:  
[http://veristream.eastus.azurecontainer.io:3000/](http://veristream.eastus.azurecontainer.io:3000/)

This is the production version hosted on Microsoft Azure.

---

## Docker Setup

### Using Prebuilt Images

If you prefer not to build the images yourself, you can pull the prebuilt images from Docker Hub.

#### Pull and Run

1. **Pull the Images**

   ```bash
   docker pull bhushansah3/veristream:backend
   docker pull bhushansah3/veristream:frontend
   ```

2. **Run the Containers**

   - For the **backend** (runs on port 5000):

     ```bash
     docker run -p 5000:5000 bhushansah3/veristream:backend
     ```

   - For the **frontend** (runs on port 3000):

     ```bash
     docker run -p 3000:3000 bhushansah3/veristream:frontend
     ```

## Local Development (Without Docker)

### Frontend

1. Install dependencies:
   ```bash
   npm install
   ```
2. Start the development server:
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) in your browser.

### Backend

1. Navigate to the `model` folder and install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Run the backend server:
   ```bash
   python fact_checker.py
   ```
   *(Adjust the command if your backend entry point is different.)*

---

## Additional Notes

- **macOS Users:**  
  Docker Desktop for Mac runs inside a Linux VM. Most Docker instructions work the same as on Linux. Ensure you allocate sufficient resources (CPU, memory) in Docker Desktop Preferences.

- **Learn More:**  
  - [Next.js Documentation](https://nextjs.org/docs)
  - [Docker Documentation](https://docs.docker.com/)
  - [Multi-stage Builds](https://docs.docker.com/develop/develop-images/multistage-build/)

Happy coding, containerizing, and enjoy using Veristream!

📜 **License**: This project is licensed under the Apache License 2.0. © 2025 Bhushan Sah, Roshan Kumar Singh, Shubham Kumar Jha. See the [LICENSE](LICENSE) file for details.