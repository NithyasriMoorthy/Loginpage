import { useState } from "react";
import { useNavigate, Link } from "react-router-dom";
import "./App.css";

function Login() {
    const [username, setUsername] = useState("");
    const [password, setPassword] = useState("");
    const navigate = useNavigate();

    const handleLogin = () => {
        const storedUser = JSON.parse(localStorage.getItem("user"));
        console.log('storedUser',localStorage)

        if (storedUser && storedUser.username === username && storedUser.password === password) {
            alert("Login successful!");
            navigate("/dashboard");
        } else {
            alert("Invalid username or password. Please try again.");
        }
    };

    return (
        <div style={{ textAlign: "center", marginTop: "50px" }}>
            <h2>Login Page</h2>
            <input
                type="text"
                placeholder="Enter Username"
                value={username}
                onChange={(e) => setUsername(e.target.value)}
            />
            <br />
            <input
                type="password"
                placeholder="Enter Password"
                value={password}
                onChange={(e) => setPassword(e.target.value)}
            />
            <br />
            <button onClick={handleLogin}>Login</button>
            <p className="dont">Don't have an account? <Link to="/signup">Sign up here</Link></p> {/* ✅ Updated */}
        </div>
    );
}

export default Login;# Loginpage
I create a login page in my project.
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import Login from "./Login";
import Signup from "./Signup";
import Dashboard from "./Dashboard";
import ShopPage from "./shop"; 
import "./App.css";

function App() {
  return (
    <Router>
      <Routes>
        <Rou" element={<ShopPage />} />
      </Routes>
  
export default App;# Loginpage
I create a login page in my project.
