<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kyla P. Manalo | Interactive Portfolio</title>
<style>
    /* Root Variables */
    :root {
        --bg-color: #f8f9fa;
        --card-bg: #ffffff;
        --text-color: #343a40;
        --accent-color: #007bff;
    }

    /* Dark Mode */
    body.dark {
        --bg-color: #121212;
        --card-bg: #1e1e1e;
        --text-color: #f1f1f1;
        --accent-color: #4dabf7;
    }

    /* General Styles */
    body {
        font-family: 'Arial', sans-serif;
        background: var(--bg-color);
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        margin: 0;
        transition: background 0.3s;
    }

    /* Toggle Button */
    .toggle-btn {
        position: fixed;
        top: 20px;
        right: 20px;
        background: var(--accent-color);
        border: none;
        padding: 10px 15px;
        border-radius: 5px;
        color: white;
        cursor: pointer;
        font-weight: bold;
        transition: background 0.3s;
    }
    .toggle-btn:hover {
        background: darken(var(--accent-color), 10%);
    }

    /* Card Container */
    .card {
        background: var(--card-bg);
        border-radius: 20px;
        box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        width: 360px;
        padding: 30px;
        text-align: center;
        animation: float 4s ease-in-out infinite;
        transition: background 0.3s, color 0.3s;
    }

    @keyframes float {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(-15px); }
    }

    /* Header */
    .card h1 {
        margin: 0;
        font-size: 1.6em;
        color: var(--text-color);
        animation: fadeIn 1s ease forwards;
    }

    .card h2 {
        font-size: 1em;
        color: gray;
        margin-bottom: 20px;
    }

    /* Section Styles */
    .section {
        text-align: left;
        margin-bottom: 20px;
        animation: fadeIn 2s ease forwards;
    }
    .section h3 {
        margin-bottom: 10px;
        color: var(--accent-color);
    }

    .tech-icons span {
        display: inline-block;
        margin-right: 10px;
        font-size: 1.5em;
        transition: transform 0.3s;
        cursor: pointer;
    }
    .tech-icons span:hover {
        transform: translateY(-10px) scale(1.3);
    }

    /* GitHub Stats Animation */
    .stats {
        display: flex;
        justify-content: space-around;
        font-weight: bold;
        color: var(--text-color);
    }

    /* Fade-in animation */
    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }

    /* Links */
    a {
        color: var(--accent-color);
        text-decoration: none;
        transition: 0.3s;
    }
    a:hover {
        text-decoration: underline;
    }
</style>
</head>
<body>

<button class="toggle-btn" onclick="toggleDarkMode()">🌙</button>

<div class="card">
    <h1>Hi, I'm Kyla P. Manalo 👋</h1>
    <h2>Associate in Computer Technology | City College of Angeles</h2>

    <div class="section about">
        <h3>💡 About Me</h3>
        <p>I’m a student at City College of Angeles pursuing ACT.</p>
        <p>I enjoy coding, web development, database management, and system design.</p>
        <p>My goal is to improve my skills and become a creative IT professional.</p>
    </div>

    <div class="section tech">
        <h3>💻 Tech Stack</h3>
        <div class="tech-icons">
            <span title="Java">☕</span>
            <span title="Python">🐍</span>
            <span title="JavaScript">💻</span>
            <span title="Git">🧰</span>
            <span title="VS Code">🖥️</span>
        </div>
    </div>

    <div class="section projects">
        <h3>🚀 Projects</h3>
        <p>Python Fundamentals</p>
        <p>Creating Functions</p>
        <p>Shopping Cart Program</p>
        <div class="stats">
            <div>⭐ 120</div>
            <div>🍴 30</div>
            <div>📦 8</div>
        </div>
    </div>

    <div class="section contact">
        <h3>📫 Contact Me</h3>
        <p>Email: <a href="mailto:kylmanalosbnhs23@gmail.com">kylmanalosbnhs23@gmail.com</a></p>
        <p>GitHub: <a href="https://github.com/yourusername" target="_blank">github.com/yourusername</a></p>
    </div>
</div>

<script>
    // Dark Mode Toggle
    function toggleDarkMode() {
        document.body.classList.toggle('dark');
        const btn = document.querySelector('.toggle-btn');
        btn.textContent = document.body.classList.contains('dark') ? '☀️' : '🌙';
    }

    // GitHub Stats Animation
    const stats = document.querySelectorAll('.stats div');
    stats.forEach(stat => {
        let count = 0;
        const target = parseInt(stat.textContent.replace(/\D/g,''),10);
        stat.textContent = '0';
        const interval = setInterval(() => {
            if(count < target){
                count++;
                stat.textContent = stat.textContent.replace(/\d+/, count);
            } else {
                clearInterval(interval);
            }
        }, 20);
    });
</script>
</body>
</html>
