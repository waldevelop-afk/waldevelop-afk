<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cyber Security Specialist</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://unpkg.com/typed.js@2.0.16/dist/typed.umd.js"></script>
    <style>
        :root {
            --matrix-green: #00ff00;
            --cyber-blue: #0088ff;
            --hacker-red: #ff0033;
            --dark-bg: #0a0a0f;
            --terminal-bg: #0d1117;
            --text-glow: 0 0 10px var(--matrix-green);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Courier New', monospace;
        }
        
        body {
            background: var(--dark-bg);
            color: var(--matrix-green);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }
        
        /* Matrix Rain Background */
        #matrix-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }
        
        /* Header Section */
        .cyber-header {
            text-align: center;
            padding: 3rem 1rem;
            border-bottom: 2px solid var(--matrix-green);
            box-shadow: var(--text-glow);
            position: relative;
            overflow: hidden;
        }
        
        .cyber-header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                45deg,
                transparent 30%,
                rgba(0, 255, 0, 0.1) 50%,
                transparent 70%
            );
            animation: scan 3s linear infinite;
        }
        
        @keyframes scan {
            0% { transform: translateY(-100%); }
            100% { transform: translateY(100%); }
        }
        
        .hacker-title {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 0 0 20px var(--matrix-green);
            letter-spacing: 3px;
            position: relative;
            display: inline-block;
        }
        
        .hacker-title::after {
            content: '|';
            animation: blink 1s infinite;
            color: var(--hacker-red);
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        
        .typing-text {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            min-height: 2rem;
        }
        
        /* Main Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
            z-index: 1;
        }
        
        /* Terminal Sections */
        .terminal {
            background: var(--terminal-bg);
            border: 2px solid var(--matrix-green);
            border-radius: 8px;
            margin: 2rem 0;
            padding: 1.5rem;
            box-shadow: 0 0 25px rgba(0, 255, 0, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .terminal::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 30px;
            background: linear-gradient(90deg, 
                var(--hacker-red) 0%, 
                var(--hacker-red) 33%,
                #ff9900 33%, 
                #ff9900 66%,
                var(--matrix-green) 66%, 
                var(--matrix-green) 100%
            );
        }
        
        .terminal-header {
            margin-bottom: 1.5rem;
            padding-top: 40px;
        }
        
        .prompt {
            color: var(--cyber-blue);
            font-weight: bold;
            margin-right: 10px;
        }
        
        .command {
            color: var(--matrix-green);
            animation: typewriter 2s steps(20);
        }
        
        .output {
            margin: 1rem 0;
            padding-left: 1rem;
            border-left: 2px solid var(--cyber-blue);
        }
        
        @keyframes typewriter {
            from { width: 0; }
            to { width: 100%; }
        }
        
        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .skill-category {
            background: rgba(0, 30, 0, 0.3);
            border: 1px solid var(--matrix-green);
            border-radius: 5px;
            padding: 1.5rem;
            transition: transform 0.3s;
        }
        
        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 20px rgba(0, 255, 0, 0.5);
        }
        
        .skill-bar {
            height: 8px;
            background: rgba(0, 255, 0, 0.1);
            border-radius: 4px;
            margin: 10px 0;
            overflow: hidden;
        }
        
        .skill-level {
            height: 100%;
            background: linear-gradient(90deg, var(--cyber-blue), var(--matrix-green));
            border-radius: 4px;
            position: relative;
            animation: fillBar 2s ease-out;
        }
        
        @keyframes fillBar {
            from { width: 0; }
        }
        
        /* Stats */
        .stats-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .stat-card {
            background: rgba(0, 20, 40, 0.5);
            border: 1px solid var(--cyber-blue);
            border-radius: 8px;
            padding: 1.5rem;
            text-align: center;
            min-width: 200px;
            flex: 1;
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--hacker-red);
            text-shadow: 0 0 10px var(--hacker-red);
            margin-bottom: 0.5rem;
        }
        
        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .project-card {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid;
            border-image: linear-gradient(45deg, var(--matrix-green), var(--cyber-blue)) 1;
            padding: 1.5rem;
            position: relative;
            overflow: hidden;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, 
                var(--matrix-green), 
                transparent 30%,
                transparent 70%,
                var(--cyber-blue)
            );
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s;
        }
        
        .project-card:hover::before {
            opacity: 1;
        }
        
        .project-status {
            display: inline-block;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            margin-bottom: 1rem;
        }
        
        .status-active { background: rgba(255, 0, 51, 0.2); border: 1px solid var(--hacker-red); }
        .status-secure { background: rgba(0, 255, 0, 0.2); border: 1px solid var(--matrix-green); }
        
        /* Badges */
        .badges-container {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            justify-content: center;
            margin: 2rem 0;
        }
        
        .badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.8rem 1.2rem;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 20px;
            border: 1px solid;
            text-decoration: none;
            color: white;
            transition: all 0.3s;
        }
        
        .badge:hover {
            transform: scale(1.05);
            box-shadow: 0 0 15px currentColor;
        }
        
        /* Footer */
        .cyber-footer {
            text-align: center;
            padding: 2rem;
            border-top: 1px solid var(--matrix-green);
            margin-top: 3rem;
        }
        
        .hacker-text {
            font-family: monospace;
            font-size: 0.9rem;
            color: #888;
            margin-top: 1rem;
        }
        
        /* Matrix Code */
        .matrix-code {
            position: fixed;
            color: var(--matrix-green);
            font-size: 1.2rem;
            animation: fall linear infinite;
            z-index: -1;
        }
        
        @keyframes fall {
            to { transform: translateY(100vh); }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hacker-title { font-size: 2.5rem; }
            .container { padding: 1rem; }
            .skills-grid { grid-template-columns: 1fr; }
            .stats-container { flex-direction: column; }
        }
    </style>
</head>
<body>
    <!-- Matrix Rain Effect -->
    <canvas id="matrix-canvas"></canvas>
    
    <!-- Header -->
    <header class="cyber-header">
        <h1 class="hacker-title">CYBER SECURITY SPECIALIST</h1>
        <div class="typing-text" id="typed-text"></div>
        <div class="terminal" style="max-width: 800px; margin: 0 auto;">
            <div class="terminal-header">
                <div>
                    <span class="prompt">root@kali:~#</span>
                    <span class="command" id="command"></span>
                </div>
                <div class="output" id="output"></div>
            </div>
        </div>
    </header>
    
    <!-- Main Content -->
    <div class="container">
        <!-- About Section -->
        <section class="terminal">
            <h2><i class="fas fa-user-secret"></i> WHOAMI</h2>
            <div class="output">
                <p>> Name: [YOUR NAME]</p>
                <p>> Role: Cyber Security Specialist & Ethical Hacker</p>
                <p>> Focus: Penetration Testing, Network Security, Malware Analysis</p>
                <p>> Status: <span style="color: var(--matrix-green);">● ONLINE</span></p>
            </div>
        </section>
        
        <!-- Skills -->
        <section class="terminal">
            <h2><i class="fas fa-code"></i> SKILLS & TOOLS</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3><i class="fas fa-shield-alt"></i> Security Tools</h3>
                    <p>Nmap <div class="skill-bar"><div class="skill-level" style="width: 95%"></div></div></p>
                    <p>Metasploit <div class="skill-bar"><div class="skill-level" style="width: 90%"></div></div></p>
                    <p>Wireshark <div class="skill-bar"><div class="skill-level" style="width: 88%"></div></div></p>
                    <p>Burp Suite <div class="skill-bar"><div class="skill-level" style="width: 92%"></div></div></p>
                </div>
                
                <div class="skill-category">
                    <h3><i class="fas fa-laptop-code"></i> Programming</h3>
                    <p>Python <div class="skill-bar"><div class="skill-level" style="width: 95%"></div></div></p>
                    <p>Bash Scripting <div class="skill-bar"><div class="skill-level" style="width: 85%"></div></div></p>
                    <p>PowerShell <div class="skill-bar"><div class="skill-level" style="width: 80%"></div></div></p>
                    <p>C/C++ <div class="skill-bar"><div class="skill-level" style="width: 75%"></div></div></p>
                </div>
                
                <div class="skill-category">
                    <h3><i class="fas fa-network-wired"></i> Domains</h3>
                    <p>Penetration Testing <div class="skill-bar"><div class="skill-level" style="width: 94%"></div></div></p>
                    <p>Network Security <div class="skill-bar"><div class="skill-level" style="width: 90%"></div></div></p>
                    <p>Digital Forensics <div class="skill-bar"><div class="skill-level" style="width: 85%"></div></div></p>
                    <p>Cryptography <div class="skill-bar"><div class="skill-level" style="width: 82%"></div></div></p>
                </div>
            </div>
        </section>
        
        <!-- Stats -->
        <section class="terminal">
            <h2><i class="fas fa-chart-line"></i> SECURITY METRICS</h2>
            <div class="stats-container">
                <div class="stat-card">
                    <div class="stat-number" data-count="150">0</div>
                    <p>Vulnerabilities Found</p>
                </div>
                <div class="stat-card">
                    <div class="stat-number" data-count="42">0</div>
                    <p>CTF Challenges Solved</p>
                </div>
                <div class="stat-card">
                    <div class="stat-number" data-count="5">0</div>
                    <p>CVE Discoveries</p>
                </div>
                <div class="stat-card">
                    <div class="stat-number" data-count="99">0</div>
                    <p>Security Audits</p>
                </div>
            </div>
        </section>
        
        <!-- Projects -->
        <section class="terminal">
            <h2><i class="fas fa-project-diagram"></i> SECURITY PROJECTS</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <span class="project-status status-active">ACTIVE</span>
                    <h3>Firewall Analyzer</h3>
                    <p>AI-powered firewall rule optimization and security assessment tool</p>
                    <div style="margin-top: 1rem;">
                        <span style="color: var(--cyber-blue);">Python • TensorFlow • Scapy</span>
                    </div>
                </div>
                
                <div class="project-card">
                    <span class="project-status status-secure">SECURE</span>
                    <h3>Malware Detector</h3>
                    <p>Machine learning based malware analysis and detection system</p>
                    <div style="margin-top: 1rem;">
                        <span style="color: var(--cyber-blue);">Python • YARA • Cuckoo Sandbox</span>
                    </div>
                </div>
                
                <div class="project-card">
                    <span class="project-status status-active">ACTIVE</span>
                    <h3>Network Scanner Pro</h3>
                    <p>Advanced network reconnaissance and vulnerability scanner</p>
                    <div style="margin-top: 1rem;">
                        <span style="color: var(--cyber-blue);">Go • Nmap API • React</span>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Certifications -->
        <section class="terminal">
            <h2><i class="fas fa-certificate"></i> CERTIFICATIONS & BADGES</h2>
            <div class="badges-container">
                <a href="#" class="badge" style="border-color: #ff6b6b; color: #ff6b6b;">
                    <i class="fab fa-searchengin"></i> OSCP
                </a>
                <a href="#" class="badge" style="border-color: #4ecdc4; color: #4ecdc4;">
                    <i class="fas fa-user-ninja"></i> CEH
                </a>
                <a href="#" class="badge" style="border-color: #45b7d1; color: #45b7d1;">
                    <i class="fas fa-shield-alt"></i> Security+
                </a>
                <a href="#" class="badge" style="border-color: #96ceb4; color: #96ceb4;">
                    <i class="fas fa-user-secret"></i> CISSP
                </a>
                <a href="#" class="badge" style="border-color: #ff6b6b; color: #ff6b6b;">
                    <i class="fas fa-skull-crossbones"></i> HackTheBox
                </a>
                <a href="#" class="badge" style="border-color: #4ecdc4; color: #4ecdc4;">
                    <i class="fas fa-terminal"></i> TryHackMe
                </a>
            </div>
        </section>
        
        <!-- Connect -->
        <section class="terminal">
            <h2><i class="fas fa-network-wired"></i> CONNECT</h2>
            <div class="badges-container">
                <a href="https://github.com/YOUR_USERNAME" class="badge" style="border-color: white; color: white;">
                    <i class="fab fa-github"></i> GitHub
                </a>
                <a href="https://linkedin.com/in/YOUR_PROFILE" class="badge" style="border-color: #0077b5; color: #0077b5;">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://twitter.com/YOUR_PROFILE" class="badge" style="border-color: #1da1f2; color: #1da1f2;">
                    <i class="fab fa-twitter"></i> Twitter
                </a>
                <a href="https://app.hackthebox.com/users/YOUR_ID" class="badge" style="border-color: #9fef00; color: #9fef00;">
                    <i class="fas fa-cube"></i> HackTheBox
                </a>
            </div>
        </section>
    </div>
    
    <!-- Footer -->
    <footer class="cyber-footer">
        <div class="terminal" style="max-width: 800px; margin: 0 auto;">
            <div class="output">
                <p style="color: var(--hacker-red);">⚠️ DISCLAIMER: All security research conducted ethically in authorized environments only.</p>
                <p>> "The quieter you become, the more you are able to hear."</p>
                <p>> Last updated: <span id="current-date"></span></p>
            </div>
        </div>
        <div class="hacker-text">
            <p>/* ACCESS GRANTED */</p>
            <p>CONNECTION: SECURE | PROTOCOL: HTTPS | STATUS: ENCRYPTED</p>
        </div>
    </footer>
    
    <script>
        // Matrix Rain
        const canvas = document.getElementById('matrix-canvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        
        const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789$+-*/=%\"'#&_(),.;:?!\\|{}<>[]^~";
        const charArray = chars.split("");
        const fontSize = 14;
        const columns = canvas.width / fontSize;
        const drops = [];
        
        for(let i = 0; i < columns; i++) {
            drops[i] = Math.random() * -100;
        }
        
        function drawMatrix() {
            ctx.fillStyle = 'rgba(10, 10, 15, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = '#0F0';
            ctx.font = fontSize + 'px monospace';
            
            for(let i = 0; i < drops.length; i++) {
                const text = charArray[Math.floor(Math.random() * charArray.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                
                if(drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }
        
        // Typing Effect
        const typed = new Typed('#typed-text', {
            strings: [
                'Ethical Hacker',
                'Penetration Tester',
                'Security Researcher',
                'Bug Bounty Hunter',
                'Digital Forensics Expert'
            ],
            typeSpeed: 50,
            backSpeed: 30,
            backDelay: 2000,
            loop: true,
            showCursor: false
        });
        
        // Terminal Commands
        const commands = [
            'whoami',
            'skills --show',
            'certs --list',
            'projects --active',
            'connect --social'
        ];
        
        const outputs = [
            '[root@cybersec ~]# Ethical Hacker | Security Specialist',
            '[+] Penetration Testing: ██████████ 95%\n[+] Network Security: ██████████ 92%\n[+] Malware Analysis: ██████████ 88%\n[+] Digital Forensics: ██████████ 85%',
            '[✓] OSCP - Offensive Security Certified Professional\n[✓] CEH - Certified Ethical Hacker\n[✓] Security+ - CompTIA Security+\n[✓] HTB - HackTheBox Pro Hacker',
            '[1] Firewall Analyzer - AI-powered security tool\n[2] Malware Detector - ML-based analysis system\n[3] Network Scanner - Advanced recon tool',
            '[?] GitHub: https://github.com/YOUR_USERNAME\n[?] LinkedIn: https://linkedin.com/in/YOUR_PROFILE\n[?] Twitter: https://twitter.com/YOUR_PROFILE'
        ];
        
        let cmdIndex = 0;
        let outputIndex = 0;
        
        function typeCommand() {
            const commandElement = document.getElementById('command');
            const outputElement = document.getElementById('output');
            
            commandElement.textContent = '';
            outputElement.textContent = '';
            
            let i = 0;
            const typing = setInterval(() => {
                commandElement.textContent += commands[cmdIndex][i];
                i++;
                if(i >= commands[cmdIndex].length) {
                    clearInterval(typing);
                    setTimeout(() => {
                        outputElement.textContent = outputs[outputIndex];
                        outputIndex = (outputIndex + 1) % outputs.length;
                        setTimeout(() => {
                            cmdIndex = (cmdIndex + 1) % commands.length;
                            typeCommand();
                        }, 3000);
                    }, 500);
                }
            }, 100);
        }
        
        // Animated Stats
        function animateStats() {
            const stats = document.querySelectorAll('.stat-number');
            stats.forEach(stat => {
                const target = parseInt(stat.getAttribute('data-count'));
                let current = 0;
                const increment = target / 100;
                const timer = setInterval(() => {
                    current += increment;
                    if(current >= target) {
                        stat.textContent = target;
                        clearInterval(timer);
                    } else {
                        stat.textContent = Math.floor(current);
                    }
                }, 20);
            });
        }
        
        // Current Date
        document.getElementById('current-date').textContent = new Date().toLocaleDateString('en-US', {
            year: 'numeric',
            month: 'long',
            day: 'numeric'
        });
        
        // Initialize
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
        
        // Animation loop
        function animate() {
            drawMatrix();
            requestAnimationFrame(animate);
        }
        
        // Start animations
        setTimeout(typeCommand, 1000);
        setTimeout(animateStats, 2000);
        animate();
        
        // Add some random matrix code elements
        function createMatrixCode() {
            const code = document.createElement('div');
            code.className = 'matrix-code';
            code.textContent = Math.random().toString(2).substring(2, 15);
            code.style.left = Math.random() * 100 + 'vw';
            code.style.animationDuration = (Math.random() * 5 + 3) + 's';
            code.style.opacity = Math.random() * 0.5 + 0.2;
            document.body.appendChild(code);
            
            setTimeout(() => {
                code.remove();
            }, parseFloat(code.style.animationDuration) * 1000);
        }
        
        setInterval(createMatrixCode, 100);
        
        // Interactive skill bars on hover
        document.querySelectorAll('.skill-category').forEach(card => {
            card.addEventListener('mouseenter', function() {
                const bars = this.querySelectorAll('.skill-level');
                bars.forEach(bar => {
                    const currentWidth = bar.style.width;
                    bar.style.transition = 'none';
                    bar.style.width = '0%';
                    setTimeout(() => {
                        bar.style.transition = 'width 1.5s ease-out';
                        bar.style.width = currentWidth;
                    }, 50);
                });
            });
        });
    </script>
</body>
</html>Tujuan    : Build clean, useful & impactful projects
