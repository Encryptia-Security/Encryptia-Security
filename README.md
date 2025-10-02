<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Encryptia Security</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117;
            color: #c9d1d9;
            line-height: 1.6;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .container {
            background: linear-gradient(135deg, #0d1117 0%, #161b22 100%);
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid #30363d;
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
            padding-bottom: 20px;
            border-bottom: 1px solid #30363d;
        }
        
        .header h1 {
            font-size: 2.8rem;
            margin-bottom: 15px;
            background: linear-gradient(90deg, #58a6ff, #8e6cff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 700;
        }
        
        .header h3 {
            font-size: 1.5rem;
            color: #8b949e;
            font-weight: 500;
            margin-bottom: 20px;
        }
        
        .badges {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }
        
        .badge {
            display: inline-block;
            padding: 8px 16px;
            background-color: #161b22;
            border: 1px solid #30363d;
            border-radius: 6px;
            font-size: 0.9rem;
            font-weight: 500;
            color: #58a6ff;
        }
        
        .code-block {
            background-color: #161b22;
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 20px;
            margin: 25px 0;
            font-family: 'JetBrains Mono', monospace;
            overflow-x: auto;
        }
        
        .code-block.diff {
            color: #c9d1d9;
        }
        
        .diff-add {
            color: #3fb950;
        }
        
        .diff-remove {
            color: #f85149;
        }
        
        .diff-comment {
            color: #8b949e;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .service-card {
            background-color: #161b22;
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 20px;
            transition: transform 0.3s, border-color 0.3s;
        }
        
        .service-card:hover {
            transform: translateY(-5px);
            border-color: #58a6ff;
        }
        
        .service-icon {
            font-size: 2rem;
            margin-bottom: 15px;
        }
        
        .service-card h4 {
            font-size: 1.2rem;
            margin-bottom: 10px;
            color: #58a6ff;
        }
        
        .service-features {
            list-style-type: none;
        }
        
        .service-features li {
            margin-bottom: 8px;
            padding-left: 20px;
            position: relative;
        }
        
        .service-features li:before {
            content: "▸";
            position: absolute;
            left: 0;
            color: #3fb950;
        }
        
        .tools-table {
            width: 100%;
            border-collapse: collapse;
            margin: 25px 0;
        }
        
        .tools-table th {
            background-color: #161b22;
            padding: 15px;
            text-align: center;
            border: 1px solid #30363d;
            color: #58a6ff;
        }
        
        .tools-table td {
            padding: 15px;
            text-align: center;
            border: 1px solid #30363d;
            background-color: #0d1117;
        }
        
        .tool-badge {
            display: inline-block;
            padding: 6px 12px;
            background-color: #21262d;
            border-radius: 4px;
            font-size: 0.85rem;
            font-family: 'JetBrains Mono', monospace;
        }
        
        .expandable {
            margin: 25px 0;
        }
        
        .expandable summary {
            cursor: pointer;
            padding: 15px;
            background-color: #161b22;
            border: 1px solid #30363d;
            border-radius: 8px;
            font-weight: 600;
            color: #58a6ff;
        }
        
        .expandable-content {
            padding: 20px;
            background-color: #161b22;
            border: 1px solid #30363d;
            border-top: none;
            border-radius: 0 0 8px 8px;
        }
        
        .research-item {
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid #30363d;
        }
        
        .research-item:last-child {
            border-bottom: none;
        }
        
        .research-item h4 {
            color: #58a6ff;
            margin-bottom: 8px;
        }
        
        .cta-section {
            text-align: center;
            margin: 40px 0;
            padding: 30px;
            background: linear-gradient(135deg, #161b22 0%, #1c2128 100%);
            border-radius: 12px;
            border: 1px solid #30363d;
        }
        
        .cta-buttons {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin: 25px 0;
        }
        
        .cta-button {
            display: inline-block;
            padding: 12px 24px;
            background-color: #238636;
            color: white;
            text-decoration: none;
            border-radius: 6px;
            font-weight: 600;
            transition: background-color 0.3s;
        }
        
        .cta-button:hover {
            background-color: #2ea043;
        }
        
        .cta-button.secondary {
            background-color: #21262d;
            border: 1px solid #30363d;
        }
        
        .cta-button.secondary:hover {
            background-color: #30363d;
        }
        
        .footer {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid #30363d;
            color: #8b949e;
            font-style: italic;
        }
        
        .counter {
            display: inline-block;
            padding: 10px 20px;
            background-color: #0d1117;
            border: 1px solid #30363d;
            border-radius: 6px;
            margin-top: 15px;
            font-weight: 600;
        }
        
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2rem;
            }
            
            .header h3 {
                font-size: 1.2rem;
            }
            
            .services-grid {
                grid-template-columns: 1fr;
            }
            
            .tools-table {
                font-size: 0.9rem;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .cta-button {
                width: 100%;
                max-width: 300px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>ENCRYPTIA SECURITY</h1>
            <h3>⚡ Elite Security Testing & Research Lab ⚡</h3>
            
            <div class="badges">
                <span class="badge">WEB APPLICATION TESTING</span>
                <span class="badge">ANDROID APP TESTING</span>
                <span class="badge">NETWORK PENTEST</span>
                <span class="badge">SECURITY RESEARCH</span>
            </div>
        </div>
        
        <div class="code-block">
            <pre># Our Security Arsenal
🎯 Web Application Pentesting (WAPT)
📱 Android Application Pentesting (AAPT) 
🌐 Network Pentesting (NPT)
🔬 Vulnerability Research & Labs
📝 Professional Write-ups
⚒️ Custom Security Tools</pre>
        </div>
        
        <h2>🛠️ Our Core Services</h2>
        
        <div class="services-grid">
            <div class="service-card">
                <div class="service-icon">🌐</div>
                <h4>Web Application Pentesting</h4>
                <ul class="service-features">
                    <li>OWASP Top 10 Testing</li>
                    <li>API Security Assessment</li>
                    <li>Business Logic Flaws</li>
                    <li>Authentication Bypass</li>
                </ul>
            </div>
            
            <div class="service-card">
                <div class="service-icon">📱</div>
                <h4>Android App Pentesting</h4>
                <ul class="service-features">
                    <li>MSTG Compliance Testing</li>
                    <li>Reverse Engineering</li>
                    <li>Runtime Analysis</li>
                    <li>Secure Storage Assessment</li>
                </ul>
            </div>
            
            <div class="service-card">
                <div class="service-icon">🔌</div>
                <h4>Network Pentesting</h4>
                <ul class="service-features">
                    <li>Internal/External Testing</li>
                    <li>Wireless Security Assessment</li>
                    <li>Network Architecture Review</li>
                    <li>Firewall & IDS Testing</li>
                </ul>
            </div>
            
            <div class="service-card">
                <div class="service-icon">🔬</div>
                <h4>Security Research & Labs</h4>
                <ul class="service-features">
                    <li>Vulnerability Research</li>
                    <li>Training Labs Development</li>
                    <li>Proof-of-Concepts</li>
                    <li>Custom Tool Development</li>
                </ul>
            </div>
        </div>
        
        <h2>🔥 Our Toolbox</h2>
        
        <table class="tools-table">
            <tr>
                <th>Web Testing</th>
                <th>Mobile Analysis</th>
                <th>Network Recon</th>
                <th>Custom Tools</th>
            </tr>
            <tr>
                <td>Burp Suite Pro</td>
                <td>MobSF</td>
                <td>Nmap</td>
                <td><span class="tool-badge">Automated Scanners</span></td>
            </tr>
            <tr>
                <td>OWASP ZAP</td>
                <td>Frida</td>
                <td>Wireshark</td>
                <td><span class="tool-badge">Exploit Frameworks</span></td>
            </tr>
            <tr>
                <td>SQLmap</td>
                <td>Jadx</td>
                <td>Metasploit</td>
                <td><span class="tool-badge">Research Scripts</span></td>
            </tr>
            <tr>
                <td>Custom Scripts</td>
                <td>Objection</td>
                <td>Nessus</td>
                <td><span class="tool-badge">Lab Environments</span></td>
            </tr>
        </table>
        
        <h2>📊 Our Deliverables</h2>
        
        <div class="code-block diff">
            <pre><span class="diff-add">+ Comprehensive Penetration Test Reports</span>
<span class="diff-add">+ Detailed Vulnerability Write-ups</span>  
<span class="diff-add">+ Custom Security Tools & Scripts</span>
<span class="diff-add">+ Training Labs & Environments</span>
<span class="diff-add">+ Research Papers & Case Studies</span>
<span class="diff-add">+ Remediation Guidance & Support</span></pre>
        </div>
        
        <div class="expandable">
            <details>
                <summary>🛡️ Click to see our latest work</summary>
                <div class="expandable-content">
                    <h3>🔬 Recent Research</h3>
                    
                    <div class="research-item">
                        <h4>Zero-Day in Popular CMS</h4>
                        <p>Technical write-up with Proof-of-Concept exploit and mitigation strategies.</p>
                    </div>
                    
                    <div class="research-item">
                        <h4>API Security Best Practices</h4>
                        <p>Comprehensive guide covering authentication, authorization, and data validation for modern APIs.</p>
                    </div>
                    
                    <div class="research-item">
                        <h4>Mobile App Hardening Techniques</h4>
                        <p>Research paper on advanced obfuscation, anti-tampering, and runtime protection methods.</p>
                    </div>
                    
                    <h3>⚒️ Custom Tools</h3>
                    
                    <div class="research-item">
                        <h4>APKAnalyzer</h4>
                        <p>Enhanced Android app analysis tool with automated vulnerability detection.</p>
                    </div>
                    
                    <div class="research-item">
                        <h4>WebVulnScanner</h4>
                        <p>Custom web vulnerability scanner with advanced detection capabilities.</p>
                    </div>
                    
                    <div class="research-item">
                        <h4>NetworkMapper</h4>
                        <p>Advanced network discovery and mapping tool with service fingerprinting.</p>
                    </div>
                    
                    <h3>🧪 Training Labs</h3>
                    
                    <div class="research-item">
                        <h4>Web Security Dojo</h4>
                        <p>OWASP Top 10 practice environment with vulnerable applications and challenges.</p>
                    </div>
                    
                    <div class="research-item">
                        <h4>Mobile Pentest Lab</h4>
                        <p>Android app testing playground with intentionally vulnerable applications.</p>
                    </div>
                    
                    <div class="research-item">
                        <h4>Network Defense Range</h4>
                        <p>Real-world network scenarios for practicing offensive and defensive techniques.</p>
                    </div>
                </div>
            </details>
        </div>
        
        <h2>📈 Why Choose Us?</h2>
        
        <div class="code-block diff">
            <pre><span class="diff-comment"># We don't just find vulnerabilities - we provide solutions</span>
<span class="diff-add">+ Expert-level testing methodology</span>
<span class="diff-add">+ Custom tools for unique challenges</span>  
<span class="diff-add">+ Detailed, actionable reports</span>
<span class="diff-add">+ Ongoing research & innovation</span>
<span class="diff-add">+ Training and knowledge transfer</span></pre>
        </div>
        
        <div class="cta-section">
            <h2>🚀 Get Secured Today</h2>
            
            <div class="cta-buttons">
                <a href="https://encryptiasecurity.com" class="cta-button">Visit Our Website</a>
                <a href="mailto:contact@encryptiasecurity.com" class="cta-button secondary">Email Us</a>
                <a href="https://linkedin.com/company/encryptia-security" class="cta-button secondary">Follow Our Research</a>
            </div>
            
            <h3>💼 Enterprise-Grade Security Testing</h3>
            <h3>🔬 Cutting-Edge Research & Development</h3>
            <h3>⚒️ Custom Tools & Training Solutions</h3>
        </div>
        
        <div class="footer">
            <p>"From vulnerability discovery to comprehensive protection"</p>
            <div class="counter">SECURITY PROFESSIONALS VIEWED THIS PROFILE: <span id="viewCount">1,247</span></div>
        </div>
    </div>

    <script>
        // Simple view counter animation
        document.addEventListener('DOMContentLoaded', function() {
            const viewCountElement = document.getElementById('viewCount');
            let targetCount = 1247;
            let currentCount = 0;
            const increment = Math.ceil(targetCount / 100);
            
            const timer = setInterval(() => {
                currentCount += increment;
                if (currentCount >= targetCount) {
                    currentCount = targetCount;
                    clearInterval(timer);
                }
                viewCountElement.textContent = currentCount.toLocaleString();
            }, 20);
        });
    </script>
</body>
</html>
