
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Development Knowledge Hub</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            margin-bottom: 3rem;
            color: white;
        }

        .header h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .header p {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        .questions-grid {
            display: grid;
            gap: 2rem;
            grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
        }

        .question-card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .question-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .question-number {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }

        .question-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #2c3e50;
            font-weight: 600;
        }

        .answer-content {
            color: #444;
        }

        .answer-content h4 {
            color: #667eea;
            margin: 1rem 0 0.5rem 0;
            font-weight: 600;
        }

        .steps-list {
            list-style: none;
            margin: 1rem 0;
        }

        .steps-list li {
            padding: 0.5rem 0;
            border-left: 3px solid #667eea;
            padding-left: 1rem;
            margin: 0.5rem 0;
            background: rgba(102, 126, 234, 0.1);
            border-radius: 0 8px 8px 0;
        }

        .steps-list li strong {
            color: #667eea;
        }

        .comparison-table {
            width: 100%;
            border-collapse: collapse;
            margin: 1rem 0;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .comparison-table th {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 1rem;
            text-align: left;
            font-weight: 600;
        }

        .comparison-table td {
            padding: 1rem;
            border-bottom: 1px solid #eee;
        }

        .comparison-table tr:nth-child(even) {
            background: rgba(102, 126, 234, 0.05);
        }

        .code-block {
            background: #2d3748;
            color: #e2e8f0;
            padding: 1.5rem;
            border-radius: 10px;
            margin: 1rem 0;
            overflow-x: auto;
            font-family: 'Courier New', monospace;
            position: relative;
        }

        .code-block::before {
            content: 'JavaScript';
            position: absolute;
            top: 0.5rem;
            right: 1rem;
            color: #a0aec0;
            font-size: 0.8rem;
        }

        .highlight {
            background: linear-gradient(120deg, rgba(102, 126, 234, 0.2) 0%, rgba(118, 75, 162, 0.2) 100%);
            padding: 1rem;
            border-radius: 10px;
            margin: 1rem 0;
            border-left: 4px solid #667eea;
        }

        .tip {
            background: rgba(52, 211, 153, 0.1);
            border: 1px solid rgba(52, 211, 153, 0.3);
            padding: 1rem;
            border-radius: 10px;
            margin: 1rem 0;
        }

        .tip::before {
            content: "💡 ";
            font-weight: bold;
        }

        .optimization-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin: 1rem 0;
        }

        .optimization-item {
            background: rgba(102, 126, 234, 0.1);
            padding: 1rem;
            border-radius: 10px;
            border-left: 4px solid #667eea;
        }

        .optimization-item h5 {
            color: #667eea;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .security-points {
            list-style: none;
        }

        .security-points li {
            padding: 0.5rem 0;
            border-left: 3px solid #e53e3e;
            padding-left: 1rem;
            margin: 0.5rem 0;
            background: rgba(229, 62, 62, 0.1);
            border-radius: 0 8px 8px 0;
        }

        @media (max-width: 768px) {
            .questions-grid {
                grid-template-columns: 1fr;
            }
            
            .header h1 {
                font-size: 2rem;
            }
            
            .question-card {
                padding: 1.5rem;
            }
        }

        .interactive-demo {
            background: #f8f9fa;
            padding: 1rem;
            border-radius: 10px;
            margin: 1rem 0;
        }

        .demo-button {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: transform 0.2s ease;
        }

        .demo-button:hover {
            transform: scale(1.05);
        }

        .demo-output {
            margin-top: 1rem;
            padding: 1rem;
            background: white;
            border-radius: 8px;
            border: 2px solid #667eea;
            min-height: 50px;
            font-family: monospace;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🌐 Web Development Knowledge Hub</h1>
            <p>Master the fundamentals of web development with these essential concepts</p>
        </div>

        <div class="questions-grid">
            <!-- Question 1 -->
            <div class="question-card">
                <div class="question-number">1️⃣</div>
                <h3 class="question-title">What happens when you open a website in the browser?</h3>
                <div class="answer-content">
                    <p>When you type a URL and hit Enter, a fascinating series of steps happen behind the scenes:</p>
                    
                    <ol class="steps-list">
                        <li><strong>DNS Lookup</strong> – The browser finds the IP address of the server using the domain name.</li>
                        <li><strong>TCP Connection</strong> – Browser establishes a connection with the server (via TCP/IP).</li>
                        <li><strong>HTTP Request</strong> – Browser sends a request for the webpage.</li>
                        <li><strong>Server Response</strong> – Server responds with HTML, CSS, JS, images, etc.</li>
                        <li><strong>Browser Rendering</strong>:
                            <ul style="margin-left: 1rem; margin-top: 0.5rem;">
                                <li><strong>HTML Parsing</strong> → Builds the <strong>DOM tree</strong></li>
                                <li><strong>CSS Parsing</strong> → Builds the <strong>CSSOM</strong></li>
                                <li><strong>JavaScript Execution</strong> → Modifies DOM/CSSOM if needed</li>
                                <li><strong>Render Tree Construction</strong> → Combines DOM + CSSOM</li>
                                <li><strong>Layout / Reflow</strong> → Calculates positions/sizes of elements</li>
                                <li><strong>Paint / Repaint</strong> → Fills pixels on the screen</li>
                            </ul>
                        </li>
                        <li><strong>Browser Display</strong> – Page is finally shown to the user.</li>
                    </ol>

                    <div class="tip">
                        Modern browsers also do optimizations like caching, preloading, and lazy loading to make this faster.
                    </div>
                </div>
            </div>

            <!-- Question 2 -->
            <div class="question-card">
                <div class="question-number">2️⃣</div>
                <h3 class="question-title">Difference between reflow and repaint</h3>
                <div class="answer-content">
                    <table class="comparison-table">
                        <thead>
                            <tr>
                                <th>Aspect</th>
                                <th>Reflow (Layout)</th>
                                <th>Repaint (Paint)</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>What it affects</strong></td>
                                <td>Layout and geometry (size, position) of elements</td>
                                <td>Visual styling only (color, background)</td>
                            </tr>
                            <tr>
                                <td><strong>Triggered by</strong></td>
                                <td>Changing width, height, padding, margin, display</td>
                                <td>Changing color, visibility, background</td>
                            </tr>
                            <tr>
                                <td><strong>Cost</strong></td>
                                <td>Expensive (affects layout of elements + children)</td>
                                <td>Less expensive (just redraw pixels)</td>
                            </tr>
                            <tr>
                                <td><strong>Example</strong></td>
                                <td><code>element.style.width = "200px"</code></td>
                                <td><code>element.style.backgroundColor = "red"</code></td>
                            </tr>
                        </tbody>
                    </table>

                    <div class="highlight">
                        ✅ <strong>Key Point:</strong> Reflow is heavier than repaint. Repaints often follow reflows.
                    </div>
                </div>
            </div>

            <!-- Question 3 -->
            <div class="question-card">
                <div class="question-number">3️⃣</div>
                <h3 class="question-title">How would you make a slow site load faster?</h3>
                <div class="answer-content">
                    <div class="optimization-grid">
                        <div class="optimization-item">
                            <h5>🎨 Front-end Optimizations</h5>
                            <ul>
                                <li>Minify CSS, JS, and HTML</li>
                                <li>Compress images (WebP, AVIF)</li>
                                <li>Use lazy loading for images/videos</li>
                                <li>Reduce render-blocking resources (defer JS, async)</li>
                                <li>Use CDN for assets</li>
                            </ul>
                        </div>

                        <div class="optimization-item">
                            <h5>⚙️ Back-end Optimizations</h5>
                            <ul>
                                <li>Enable caching (HTTP cache, Redis)</li>
                                <li>Optimize database queries</li>
                                <li>Use server-side compression (gzip, Brotli)</li>
                            </ul>
                        </div>

                        <div class="optimization-item">
                            <h5>🌐 Browser & Network</h5>
                            <ul>
                                <li>Use HTTP/2 or HTTP/3</li>
                                <li>Prefetch and preload critical resources</li>
                                <li>Reduce number of HTTP requests</li>
                            </ul>
                        </div>
                    </div>

                    <div class="tip">
                        Tools like <strong>Lighthouse</strong> or <strong>WebPageTest</strong> help identify slow parts of a page.
                    </div>
                </div>
            </div>

            <!-- Question 4 -->
            <div class="question-card">
                <div class="question-number">4️⃣</div>
                <h3 class="question-title">How do closures help in JavaScript?</h3>
                <div class="answer-content">
                    <p>Closures occur when a function <strong>remembers variables from its outer scope</strong> even after that scope has finished execution.</p>

                    <h4>📋 Benefits:</h4>
                    <ul style="margin-left: 1rem;">
                        <li><strong>Data privacy / Encapsulation</strong>: Keep variables private</li>
                        <li><strong>Partial application / currying</strong>: Store some arguments for later use</li>
                        <li><strong>Event handlers & callbacks</strong>: Maintain access to outer variables</li>
                        <li><strong>Memoization</strong>: Store results of expensive operations</li>
                    </ul>

                    <h4>💻 Example:</h4>
                    <div class="code-block">
function counter() {
  let count = 0;
  return function () {
    count++;
    return count;
  }
}

const increment = counter();
console.log(increment()); // 1
console.log(increment()); // 2
                    </div>

                    <div class="interactive-demo">
                        <p><strong>Try it yourself:</strong></p>
                        <button class="demo-button" onclick="demonstrateClosure()">Run Closure Demo</button>
                        <div class="demo-output" id="closureOutput">Click the button to see closure in action!</div>
                    </div>

                    <div class="highlight">
                        <code>count</code> is private but persists between calls.
                    </div>
                </div>
            </div>

            <!-- Question 5 -->
            <div class="question-card">
                <div class="question-number">5️⃣</div>
                <h3 class="question-title">How do you protect a site from attacks like XSS?</h3>
                <div class="answer-content">
                    <p><strong>XSS (Cross-Site Scripting)</strong> happens when attackers inject malicious scripts.</p>
                    
                    <h4>🛡️ Protection strategies:</h4>
                    <ol class="security-points">
                        <li><strong>Escape / sanitize user input</strong> before rendering on the page.</li>
                        <li><strong>Use Content Security Policy (CSP)</strong> to restrict script sources.</li>
                        <li><strong>HttpOnly cookies</strong> for sensitive session data.</li>
                        <li><strong>Validate input on both client & server</strong>.</li>
                        <li><strong>Avoid <code>innerHTML</code> with untrusted data</strong>; use <code>textContent</code> instead.</li>
                        <li><strong>Use frameworks that auto-escape content</strong> (React, Angular, Vue).</li>
                    </ol>

                    <div class="interactive-demo">
                        <p><strong>Security Demo:</strong></p>
                        <input type="text" id="userInput" placeholder="Enter some text..." style="width: 100%; padding: 0.5rem; margin: 0.5rem 0; border: 1px solid #ccc; border-radius: 5px;">
                        <button class="demo-button" onclick="demonstrateSecurity()">Test XSS Protection</button>
                        <div class="demo-output" id="securityOutput">Enter text above to see how we safely handle user input</div>
                    </div>

                      <div class="interactive-demo">
                        <p><strong>data-block-id="{{ block_id }}"
     data-block-type="{{ block_type }}"</strong></p>
                        <input type="text" id="userInput" placeholder="Enter some text..." style="width: 100%; padding: 0.5rem; margin: 0.5rem 0; border: 1px solid #ccc; border-radius: 5px;">
                        <button class="demo-button" onclick="demonstrateSecurity()">{% render 'group', children: children, settings: block.settings, shopify_attributes: block.shopify_attributes block_id: block.id,</button>
                        <div class="demo-output" id="securityOutput">Enter text above to see how we safely handle user input</div>
                    </div>

                    
                </div>
            </div>
        </div>
    </div>

    <script>
        // Closure demonstration
        function createCounter() {
            let count = 0;
            return function() {
                count++;
                return count;
            };
        }

        const demoCounter = createCounter();

        function demonstrateClosure() {
            const result = demoCounter();
            const output = document.getElementById('closureOutput');
            output.innerHTML += `<div>Counter called: ${result}</div>`;
        }

        // Security demonstration
        function demonstrateSecurity() {
            const input = document.getElementById('userInput');
            const output = document.getElementById('securityOutput');
            const userText = input.value;
            
            // Safe way - using textContent (prevents XSS)
            const safeDiv = document.createElement('div');
            safeDiv.textContent = `✅ Safe output: ${userText}`;
            safeDiv.style.background = 'rgba(52, 211, 153, 0.1)';
            safeDiv.style.padding = '0.5rem';
            safeDiv.style.margin = '0.5rem 0';
            safeDiv.style.borderRadius = '5px';
            
            output.innerHTML = '';
            output.appendChild(safeDiv);
            
            // Show what would be dangerous
            const warningDiv = document.createElement('div');
            warningDiv.innerHTML = `⚠️ Using innerHTML with user input would be dangerous!`;
            warningDiv.style.background = 'rgba(229, 62, 62, 0.1)';
            warningDiv.style.padding = '0.5rem';
            warningDiv.style.margin = '0.5rem 0';
            warningDiv.style.borderRadius = '5px';
            warningDiv.style.color = '#e53e3e';
            
            output.appendChild(warningDiv);
            
            input.value = '';
        }

        // Add some interactive animations
        document.addEventListener('DOMContentLoaded', function() {
            const cards = document.querySelectorAll('.question-card');
            
            const observer = new IntersectionObserver(entries => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            });

            cards.forEach(card => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(card);
            });
        });
    </script>
</body>
</html>
