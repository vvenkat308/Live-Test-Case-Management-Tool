# Live Test
Built a real-time bug tracking system that enables QA teams to log, update, and monitor defects dynamically. Integrated REST APIs and Web Sockets for instant updates, improving issue resolution efficiency
📝 Description:
"Developed a Real-Time QA Dashboard to help testers and developers track software defects and monitor live test executions efficiently. Built using React, TypeScript, and Vite for a fast and scalable frontend. Integrated real-time data updates via WebSockets/REST API to ensure instant visibility into test cases and defects."
📌 Key Features:
Real-Time Issue Tracking – Users can log and monitor defects instantly.

Live Test Execution Monitoring – Displays test case results in real time.

WebSockets/API Integration – Enables real-time data updates.

Fast and Optimized Performance – Built with Vite for quick loading.

Modern UI/UX – Styled using Tailwind CSS for a clean, responsive interface.

Type-Safe Development – Uses TypeScript for better maintainability.

Authentication & Role Management – Manages different QA roles.

Report Generation – Allows exporting defect logs and test execution results.
🛠️ How to Code (Step-by-Step)
1️⃣ Project Setup
# Install dependencies
npm install

# Start the development server
npm run dev
2️⃣ Key Code Snippets
🟢 Real-Time Data Fetching (Using API/WebSockets)
import { useEffect, useState } from "react";

function Dashboard() {
  const [testResults, setTestResults] = useState([]);

  useEffect(() => {
    fetch("/api/tests")
      .then((res) => res.json())
      .then((data) => setTestResults(data));
  }, []);

  return (
    <div>
      <h1>Live Test Execution</h1>
      {testResults.map((test) => (
        <div key={test.id}>{test.status}</div>
      ))}
    </div>
  );
}
🟢 WebSockets for Real-Time Updates
import { useEffect, useState } from "react";

function RealTimeUpdates() {
  const [logs, setLogs] = useState([]);

  useEffect(() => {
    const socket = new WebSocket("wss://your-websocket-url");

    socket.onmessage = (event) => {
      setLogs((prevLogs) => [...prevLogs, JSON.parse(event.data)]);
    };

    return () => socket.close();
  }, []);

  return (
    <div>
      <h2>Live QA Logs</h2>
      {logs.map((log, index) => (
        <p key={index}>{log.message}</p>
      ))}
    </div>
  );
}
📌 Final Outputs
✅ Dashboard Interface – Displays real-time test case statuses.
✅ Bug Tracker – Users can log and track defects.
✅ Live Log Updates – Immediate defect tracking using WebSockets.
✅ Reports Section – Export bug reports in CSV/PDF formats.
✅ User Authentication – QA team members have different roles.

🌍 Real-Time Applications
🚀 Software Testing Companies – Tracks test cases & defects dynamically.
🚀 Agile & DevOps Teams – Helps developers monitor test executions in real time.
🚀 Bug Bounty Programs – Security researchers can log vulnerabilities instantly.
🚀 CI/CD Pipelines – Automates testing & displays results live.
🚀 Enterprise QA Teams – Enhances collaboration between testers & developers.



