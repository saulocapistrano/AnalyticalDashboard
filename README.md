Certainly! Here’s an enhanced and more visually appealing README using Markdown features like icons, emojis, and colors. This version incorporates some basic UI/UX principles to make the README more engaging and user-friendly.

---

# 📊 **Analytical Dashboard Project with Angular and MongoDB**

## 🌟 Overview

This project is an analytical dashboard developed with **Angular** and **MongoDB**. The system displays information about mobile devices, including geographic visualization on maps 🗺️, performance metrics 📈, and messages exchanged between the devices 💬.

## 🛠️ Project Structure

- **Backend**: MongoDB running in a Docker container, with multiple collections to store data related to devices, carriers, metrics, user-device associations, and messages.
- **Frontend**: Angular application that consumes data from MongoDB and displays it in charts, tables, and maps.

## 📚 Summary

- [📦 Installation of Docker Desktop](#installation-of-docker-desktop)
- [🐳 Creating the MongoDB Container](#creating-the-mongodb-container)
- [💾 Database Structure](#database-structure)
- [📝 Example of Data Insertion](#example-of-data-insertion)
- [🚀 Installation and Running the Angular Frontend](#installation-and-running-the-angular-frontend)
- [📐 Frontend Structure](#frontend-structure)

## 📦 Installation of Docker Desktop

1. **Download and install Docker Desktop**:
   - Go to [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop).
   - Follow the installation instructions provided on the website.

2. **Start Docker Desktop**:
   - After installation, open Docker Desktop and make sure it is running correctly.

## 🐳 Creating the MongoDB Container

1. **Open the terminal (or PowerShell)**.

2. **Run the following command to create and run the MongoDB container**:
   ```bash
   docker run -d -p 27017:27017 --name mongodb-container mongo:latest
   ```

3. **Check if the MongoDB container is running**:
   ```bash
   docker ps
   ```

4. **Connect to MongoDB using the MongoDB Shell (`mongosh`)**:
   - Download MongoDB Shell [here](https://www.mongodb.com/try/download/shell).
   - Run the command to connect to MongoDB:
     ```bash
     mongosh --host localhost --port 27017
     ```

## 💾 Database Structure

### Database: `analytics_db`

This database contains several collections that store data related to mobile devices and their interactions.

### 📂 Created Collections:

1. **`devices`**: Stores information about mobile devices.
   - **Fields**: `deviceId`, `name`, `location`, `status`, `carrierId`.

2. **`carriers`**: Stores information about carriers.
   - **Fields**: `carrierId`, `name`.

3. **`deviceMetrics`**: Stores performance metrics for devices.
   - **Fields**: `deviceId`, `battery`, `signalStrength`, `dataUsage`.

4. **`usersDevices`**: Maps users to the devices they own.
   - **Fields**: `userId`, `userName`, `deviceId`.

5. **`messages`**: Stores messages exchanged between devices.
   - **Fields**: `fromDeviceId`, `toDeviceId`, `message`, `timestamp`.

6. **`fictitiousMessages`**: Stores standard fictitious messages between devices.
   - **Fields**: `fromDeviceId`, `toDeviceId`, `message`, `timestamp`.

## 📝 Example of Data Insertion

### 1. Collection `devices`:
```javascript
db.devices.insertOne({
  deviceId: 1,
  name: "Device A",
  location: { lat: 37.7749, lng: -122.4194 },
  status: "active",
  carrierId: 1
})
```

### 2. Collection `carriers`:
```javascript
db.carriers.insertOne({
  carrierId: 1,
  name: "Carrier A"
})
```

### 3. Collection `deviceMetrics`:
```javascript
db.deviceMetrics.insertOne({
  deviceId: 1,
  battery: 78,
  signalStrength: -70,
  dataUsage: 500
})
```

### 4. Collection `usersDevices`:
```javascript
db.usersDevices.insertOne({
  userId: 1,
  userName: "Alice",
  deviceId: 1
})
```

### 5. Collection `messages`:
```javascript
db.messages.insertOne({
  fromDeviceId: 1,
  toDeviceId: 2,
  message: "Hello, Device B!",
  timestamp: new Date("2024-08-25T10:00:00Z")
})
```

### 6. Collection `fictitiousMessages`:
```javascript
db.fictitiousMessages.insertOne({
  fromDeviceId: 1,
  toDeviceId: 2,
  message: "Hello, my friend",
  timestamp: new Date("2024-08-25T10:00:00Z")
})
```

## 🚀 Installation and Running the Angular Frontend

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/your-repository.git
cd your-repository
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Run the Angular Project
```bash
ng serve
```

### 4. Access the Application
- Open your browser and go to `http://localhost:4200`.

## 📐 Frontend Structure

### Main Components:

1. **`AppComponent`**:
   - The root component that controls the main layout of the dashboard.

2. **`DashboardComponent`**:
   - The component responsible for displaying charts and maps, calling services to fetch data from MongoDB.

3. **`ChartsComponent`**:
   - A dedicated component for displaying charts such as bar, line, and pie charts.

4. **`MapComponent`**:
   - The component for geographic visualization, integrating Leaflet to display the locations of devices.

5. **`DataService`**:
   - Angular service responsible for making requests to MongoDB to fetch data and provide it to the components.

### Technologies Used:

- **Angular 14**: Front-end framework for building single-page applications (SPA).
- **Ngx-Charts**: Library for creating charts in Angular.
- **Leaflet.js**: Library for interactive maps.
- **MongoDB**: NoSQL database for storing project data.
- **Docker**: Tool for creating and managing containers, used to run MongoDB.

## 💡 Conclusion

This README serves as a friendly guide to install and configure the development environment necessary for the project. By following these instructions, you will be able to run both the backend (MongoDB) and the frontend (Angular) in an integrated manner and explore the functionalities offered by the analytical dashboard.

If you have any questions or issues, feel free to open an issue in the GitHub repository. Happy coding! 😄
