<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Tools Collection</title>
    <style>
        :root {
            --primary-color: #4f46e5;
            --secondary-color: #f9fafb;
            --text-color: #1f2937;
            --light-gray: #e5e7eb;
        }
        
        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            margin: 0;
            padding: 0;
            color: var(--text-color);
            background-color: #ffffff;
            line-height: 1.5;
        }
        
        header {
            background-color: white;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            padding: 1rem 2rem;
            position: sticky;
            top: 0;
            z-index: 10;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1rem;
        }
        
        .nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-weight: 700;
            font-size: 1.25rem;
            color: var(--primary-color);
            text-decoration: none;
        }
        
        /* Gaya untuk halaman menu */
        .hero {
            text-align: center;
            padding: 3rem 0;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            color: #6b7280;
            font-size: 1.1rem;
            max-width: 700px;
            margin: 0 auto;
        }
        
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
            padding: 2rem 0;
        }
        
        .tool-card {
            background-color: white;
            border-radius: 0.5rem;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
            padding: 1.5rem;
            transition: transform 0.2s, box-shadow 0.2s;
            border: 1px solid var(--light-gray);
        }
        
        .tool-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0,0,0,0.1);
        }
        
        .tool-card h3 {
            margin-top: 0;
            color: var(--primary-color);
            font-size: 1.25rem;
        }
        
        .tool-card p {
            color: #6b7280;
            margin-bottom: 1.5rem;
        }
        
        .tool-card a {
            display: inline-block;
            padding: 0.5rem 1rem;
            background-color: var(--primary-color);
            color: white;
            text-decoration: none;
            border-radius: 0.25rem;
            font-size: 0.875rem;
            transition: background-color 0.2s;
        }
        
        .tool-card a:hover {
            background-color: #4338ca;
        }
        
        .tool-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }
        
        .search-container {
            max-width: 600px;
            margin: 0 auto 2rem;
        }
        
        #search-input {
            width: 100%;
            padding: 0.75rem 1rem;
            border: 1px solid var(--light-gray);
            border-radius: 0.375rem;
            font-size: 1rem;
        }
        
        /* Gaya untuk halaman tool */
        .tool-container {
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1rem;
        }
        
        .tool-area {
            margin-top: 2rem;
        }
        
        textarea, input[type="text"], input[type="number"] {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid var(--light-gray);
            border-radius: 0.375rem;
            font-family: 'Consolas', 'Monaco', monospace;
            resize: vertical;
        }
        
        textarea {
            min-height: 150px;
        }
        
        .button-group {
            margin: 1rem 0;
            display: flex;
            gap: 0.5rem;
        }
        
        button {
            padding: 0.5rem 1rem;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 0.25rem;
            cursor: pointer;
        }
        
        button:hover {
            background-color: #4338ca;
        }
        
        .tab-container {
            margin-top: 1rem;
        }
        
        .tabs {
            display: flex;
            border-bottom: 1px solid var(--light-gray);
        }
        
        .tab {
            padding: 0.5rem 1rem;
            cursor: pointer;
            border-bottom: 2px solid transparent;
        }
        
        .tab.active {
            border-bottom-color: var(--primary-color);
            color: var(--primary-color);
            font-weight: 500;
        }
        
        .tab-content {
            display: none;
            padding: 1rem 0;
        }
        
        .tab-content.active {
            display: block;
        }
        
        label {
            display: block;
            margin: 0.5rem 0;
        }
        
        /* Hasil Text Diff */
        .diff-result {
            padding: 1rem;
            border: 1px solid var(--light-gray);
            border-radius: 0.375rem;
            min-height: 100px;
            white-space: pre-wrap;
        }
        
        .diff-added {
            color: green;
            background-color: #f0fff4;
        }
        
        .diff-removed {
            color: red;
            background-color: #fff5f5;
            text-decoration: line-through;
        }
        
        footer {
            text-align: center;
            padding: 2rem 0;
            margin-top: 2rem;
            border-top: 1px solid var(--light-gray);
            color: #6b7280;
        }
        
        /* Responsif */
        @media (max-width: 768px) {
            .tools-grid {
                grid-template-columns: 1fr;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav class="nav">
                <a href="#" onclick="showHomePage()" class="logo">WebTools</a>
                <div>
                    <a href="https://github.com/username-anda/webtools" target="_blank">GitHub</a>
                </div>
            </nav>
        </div>
    </header>
    
    <main class="container">
        <!-- Halaman Menu Utama -->
        <div id="home-page">
            <section class="hero">
                <h1>Koleksi Alat Developer</h1>
                <p>Kumpulan alat online gratis untuk membantu pekerjaan development sehari-hari</p>
            </section>
            
            <div class="search-container">
                <input type="text" id="search-input" placeholder="Cari alat...">
            </div>
            
            <div class="tools-grid" id="tools-container">
                <!-- Alat Format JSON -->
                <div class="tool-card">
                    <div class="tool-icon">{ }</div>
                    <h3>JSON Formatter</h3>
                    <p>Format dan validasi data JSON dengan tampilan yang rapi dan mudah dibaca.</p>
                    <a href="#" onclick="showTool('json-formatter')">Buka Alat</a>
                </div>
                
                <!-- Alat Base64 -->
                <div class="tool-card">
                    <div class="tool-icon">≡</div>
                    <h3>Base64 Converter</h3>
                    <p>Encode dan decode string ke/dari format Base64.</p>
                    <a href="#" onclick="showTool('base64')">Buka Alat</a>
                </div>
                
                <!-- Alat URL Encoder/Decoder -->
                <div class="tool-card">
                    <div class="tool-icon">🔗</div>
                    <h3>URL Encoder/Decoder</h3>
                    <p>Encode atau decode komponen URL dengan mudah.</p>
                    <a href="#" onclick="showTool('url-encoder')">Buka Alat</a>
                </div>
                
                <!-- Alat Color Converter -->
                <div class="tool-card">
                    <div class="tool-icon">🎨</div>
                    <h3>Color Converter</h3>
                    <p>Konversi antara format warna HEX, RGB, HSL dengan cepat.</p>
                    <a href="#" onclick="showTool('color-converter')">Buka Alat</a>
                </div>
                
                <!-- Alat HTML Escape -->
                <div class="tool-card">
                    <div class="tool-icon">&lt;&gt;</div>
                    <h3>HTML Escape</h3>
                    <p>Escape atau unescape kode HTML khusus.</p>
                    <a href="#" onclick="showTool('html-escape')">Buka Alat</a>
                </div>
                
                <!-- Alat Text Diff -->
                <div class="tool-card">
                    <div class="tool-icon">⇆</div>
                    <h3>Text Diff</h3>
                    <p>Bandingkan dua teks dan temukan perbedaannya.</p>
                    <a href="#" onclick="showTool('text-diff')">Buka Alat</a>
                </div>
                
                <!-- Alat Password Generator -->
                <div class="tool-card">
                    <div class="tool-icon">🔒</div>
                    <h3>Password Generator</h3>
                    <p>Buat password acak yang kuat dengan kriteria tertentu.</p>
                    <a href="#" onclick="showTool('password-generator')">Buka Alat</a>
                </div>
            </div>
        </div>
        
        <!-- Halaman Alat Individual (awalnya tersembunyi) -->
        <div id="tool-pages" style="display:none">
            <!-- Alat Format JSON -->
            <div id="json-formatter" class="tool-container">
                <h2>JSON Formatter</h2>
                <a href="#" onclick="showHomePage()">← Kembali ke Menu Utama</a>
                
                <div class="tool-area">
                    <textarea id="json-input" placeholder="Tempel JSON Anda di sini..." rows="10"></textarea>
                    <div class="button-group">
                        <button id="format-btn">Format</button>
                        <button id="minify-btn">Perkecil</button>
                        <button id="clear-json-btn">Bersihkan</button>
                    </div>
                    <textarea id="json-output" placeholder="JSON yang diformat akan muncul di sini..." rows="10" readonly></textarea>
                </div>
            </div>
            
            <!-- Alat Base64 -->
            <div id="base64" class="tool-container">
                <h2>Base64 Converter</h2>
                <a href="#" onclick="showHomePage()">← Kembali ke Menu Utama</a>
                
                <div class="tool-area">
                    <div class="tabs">
                        <div class="tab active" onclick="switchTab('base64', 'encode')">Encode</div>
                        <div class="tab" onclick="switchTab('base64', 'decode')">Decode</div>
                    </div>
                    
                    <div id="base64-encode" class="tab-content active">
                        <textarea id="base64-input" placeholder="Teks untuk diencode ke Base64..." rows="5"></textarea>
                        <div class="button-group">
                            <button id="encode-btn">Encode</button>
                            <button id="clear-base64-btn">Bersihkan</button>
                        </div>
                        <textarea id="base64-output" placeholder="Hasil Base64 akan muncul di sini..." rows="5" readonly></textarea>
                    </div>
                    
                    <div id="base64-decode" class="tab-content">
                        <textarea id="base64-decode-input" placeholder="Base64 untuk didecode..." rows="5"></textarea>
                        <div class="button-group">
                            <button id="decode-btn">Decode</button>
                            <button id="clear-base64-decode-btn">Bersihkan</button>
                        </div>
                        <textarea id="base64-decode-output" placeholder="Teks hasil decode akan muncul di sini..." rows="5" readonly></textarea>
                    </div>
                </div>
            </div>
            
            <!-- Alat URL Encoder/Decoder -->
            <div id="url-encoder" class="tool-container">
                <h2>URL Encoder/Decoder</h2>
                <a href="#" onclick="showHomePage()">← Kembali ke Menu Utama</a>
                
                <div class="tool-area">
                    <div class="tabs">
                        <div class="tab active" onclick="switchTab('url', 'encode')">Encode</div>
                        <div class="tab" onclick="switchTab('url', 'decode')">Decode</div>
                    </div>
                    
                    <div id="url-encode" class="tab-content active">
                        <textarea id="url-input" placeholder="Teks untuk URL encode..." rows="5"></textarea>
                        <div class="button-group">
                            <button id="url-encode-btn">Encode</button>
                            <button id="clear-url-btn">Bersihkan</button>
                        </div>
                        <textarea id="url-output" placeholder="Hasil URL encode akan muncul di sini..." rows="5" readonly></textarea>
                    </div>
                    
                    <div id="url-decode" class="tab-content">
                        <textarea id="url-decode-input" placeholder="URL untuk decode..." rows="5"></textarea>
                        <div class="button-group">
                            <button id="url-decode-btn">Decode</button>
                            <button id="clear-url-decode-btn">Bersihkan</button>
                        </div>
                        <textarea id="url-decode-output" placeholder="Hasil URL decode akan muncul di sini..." rows="5" readonly></textarea>
                    </div>
                </div>
            </div>
            
            <!-- Alat Color Converter -->
            <div id="color-converter" class="tool-container">
                <h2>Color Converter</h2>
                <a href="#" onclick="showHomePage()">← Kembali ke Menu Utama</a>
                
                <div class="tool-area">
                    <div class="tabs">
                        <div class="tab active" onclick="switchTab('color', 'hex-rgb')">HEX ke RGB</div>
                        <div class="tab" onclick="switchTab('color', 'rgb-hex')">RGB ke HEX</div>
                    </div>
                    
                    <div id="color-hex-rgb" class="tab-content active">
                        <input type="text" id="hex-input" placeholder="#RRGGBB">
                        <div class="button-group">
                            <button id="hex-to-rgb-btn">Konversi</button>
                            <button id="clear-hex-btn">Bersihkan</button>
                        </div>
                        <textarea id="hex-rgb-output" placeholder="Hasil RGB akan muncul di sini..." rows="2" readonly></textarea>
                    </div>
                    
                    <div id="color-rgb-hex" class="tab-content">
                        <input type="text" id="rgb-input" placeholder="rgb(255, 255, 255)">
                        <div class="button-group">
                            <button id="rgb-to-hex-btn">Konversi</button>
                            <button id="clear-rgb-btn">Bersihkan</button>
                        </div>
                        <textarea id="rgb-hex-output" placeholder="Hasil HEX akan muncul di sini..." rows="2" readonly></textarea>
                    </div>
                </div>
            </div>
            
            <!-- Alat HTML Escape -->
            <div id="html-escape" class="tool-container">
                <h2>HTML Escape/Unescape</h2>
                <a href="#" onclick="showHomePage()">← Kembali ke Menu Utama</a>
                
                <div class="tool-area">
                    <div class="tabs">
                        <div class="tab active" onclick="switchTab('html', 'escape')">Escape</div>
                        <div class="tab" onclick="switchTab('html', 'unescape')">Unescape</div>
                    </div>
                    
                    <div id="html-escape-tab" class="tab-content active">
                        <textarea id="html-escape-input" placeholder="Masukkan teks untuk diescape..." rows="5"></textarea>
                        <div class="button-group">
                            <button id="html-escape-btn">Escape</button>
                            <button id="clear-html-escape-btn">Bersihkan</button>
                        </div>
                        <textarea id="html-escape-output" placeholder="Hasil escape akan muncul di sini..." rows="5" readonly></textarea>
                    </div>
                    
                    <div id="html-unescape-tab" class="tab-content">
                        <textarea id="html-unescape-input" placeholder="Masukkan teks untuk diunescape..." rows="5"></textarea>
                        <div class="button-group">
                            <button id="html-unescape-btn">Unescape</button>
                            <button id="clear-html-unescape-btn">Bersihkan</button>
                        </div>
                        <textarea id="html-unescape-output" placeholder="Hasil unescape akan muncul di sini..." rows="5" readonly></textarea>
                    </div>
                </div>
            </div>
            
            <!-- Alat Text Diff -->
            <div id="text-diff" class="tool-container">
                <h2>Text Diff</h2>
                <a href="#" onclick="showHomePage()">← Kembali ke Menu Utama</a>
                
                <div class="tool-area">
                    <div>
                        <h4>Teks Pertama</h4>
                        <textarea id="text-diff-a" rows="5"></textarea>
                    </div>
                    <div>
                        <h4>Teks Kedua</h4>
                        <textarea id="text-diff-b" rows="5"></textarea>
                    </div>
                    <div class="button-group">
                        <button id="compare-text-btn">Bandingkan</button>
                        <button id="clear-text-diff-btn">Bersihkan</button>
                    </div>
                    <div>
                        <h4>Hasil Perbandingan</h4>
                        <div id="text-diff-result" class="diff-result"></div>
                    </div>
                </div>
            </div>
            
            <!-- Alat Password Generator -->
            <div id="password-generator" class="tool-container">
                <h2>Password Generator</h2>
                <a href="#" onclick="showHomePage()">← Kembali ke Menu Utama</a>
                
                <div class="tool-area">
                    <div>
                        <label>Panjang Password: 
                            <input type="number" id="pass-length" min="4" max="64" value="12">
                        </label>
                    </div>
                    <div>
                        <label><input type="checkbox" id="pass-uppercase" checked> Huruf Besar (A-Z)</label><br>
                        <label><input type="checkbox" id="pass-lowercase" checked> Huruf Kecil (a-z)</label><br>
                        <label><input type="checkbox" id="pass-numbers" checked> Angka (0-9)</label><br>
                        <label><input type="checkbox" id="pass-symbols"> Simbol (!@#$%^&*)</label>
                    </div>
                    <div class="button-group">
                        <button id="generate-pass-btn">Generate</button>
                        <button id="copy-pass-btn">Salin</button>
                    </div>
                    <div>
                        <input type="text" id="password-output" readonly style="margin-top:1rem;">
                    </div>
                </div>
            </div>
        </div>
    </main>
    
    <footer>
        <div class="container">
            <p>© 2023 WebTools Collection. Semua alat gratis digunakan.</p>
        </div>
    </footer>
    
    <script>
        // Fungsi navigasi
        function showHomePage() {
            document.getElementById('home-page').style.display = 'block';
            document.getElementById('tool-pages').style.display = 'none';
            window.location.hash = '';
        }
        
        function showTool(toolId) {
            document.getElementById('home-page').style.display = 'none';
            document.getElementById('tool-pages').style.display = 'block';
            
            // Sembunyikan semua alat dulu
            const tools = document.querySelectorAll('#tool-pages .tool-container');
            tools.forEach(tool => {
                tool.style.display = 'none';
            });
            
            // Tampilkan alat yang dipilih
            document.getElementById(toolId).style.display = 'block';
            
            // Perbarui hash URL
            window.location.hash = toolId;
        }
        
        // Cek hash URL saat halaman dimuat
        window.addEventListener('load', function() {
            if (window.location.hash) {
                const toolId = window.location.hash.substring(1);
                showTool(toolId);
            }
        });
        
        // Fungsi ganti tab
        function switchTab(toolPrefix, tabName) {
            // Perbarui tab
            const tabs = document.querySelectorAll(`#${toolPrefix} .tabs .tab`);
            tabs.forEach(tab => {
                tab.classList.remove('active');
            });
            event.target.classList.add('active');
            
            // Perbarui konten tab
            const contents = document.querySelectorAll(`#${toolPrefix} .tab-content`);
            contents.forEach(content => {
                content.classList.remove('active');
            });
            document.getElementById(`${toolPrefix}-${tabName}`).classList.add('active');
        }
        
        // Fungsi pencarian di halaman menu
        document.getElementById('search-input').addEventListener('input', function(e) {
            const searchTerm = e.target.value.toLowerCase();
            const toolCards = document.querySelectorAll('.tool-card');
            
            toolCards.forEach(card => {
                const title = card.querySelector('h3').textContent.toLowerCase();
                const desc = card.querySelector('p').textContent.toLowerCase();
                
                if (title.includes(searchTerm) || desc.includes(searchTerm)) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        });
        
        // ===== FUNGSI UNTUK MASING-MASING ALAT =====
        
        // 1. JSON Formatter
        document.getElementById('format-btn').addEventListener('click', function() {
            try {
                const input = document.getElementById('json-input').value;
                const parsed = JSON.parse(input);
                document.getElementById('json-output').value = JSON.stringify(parsed, null, 2);
            } catch (e) {
                alert('JSON tidak valid: ' + e.message);
            }
        });
        
        document.getElementById('minify-btn').addEventListener('click', function() {
            try {
                const input = document.getElementById('json-input').value;
                const parsed = JSON.parse(input);
                document.getElementById('json-output').value = JSON.stringify(parsed);
            } catch (e) {
                alert('JSON tidak valid: ' + e.message);
            }
        });
        
        document.getElementById('clear-json-btn').addEventListener('click', function() {
            document.getElementById('json-input').value = '';
            document.getElementById('json-output').value = '';
        });
        
        // 2. Base64 Converter
        document.getElementById('encode-btn').addEventListener('click', function() {
            const input = document.getElementById('base64-input').value;
            document.getElementById('base64-output').value = btoa(input);
        });
        
        document.getElementById('decode-btn').addEventListener('click', function() {
            try {
                const input = document.getElementById('base64-decode-input').value;
                document.getElementById('base64-decode-output').value = atob(input);
            } catch (e) {
                alert('Base64 tidak valid: ' + e.message);
            }
        });
        
        // 3. URL Encoder/Decoder
        document.getElementById('url-encode-btn').addEventListener('click', function() {
            const input = document.getElementById('url-input').value;
            document.getElementById('url-output').value = encodeURIComponent(input);
        });
        
        document.getElementById('url-decode-btn').addEventListener('click', function() {
            try {
                const input = document.getElementById('url-decode-input').value;
                document.getElementById('url-decode-output').value = decodeURIComponent(input);
            } catch (e) {
                alert('Encoding URL tidak valid: ' + e.message);
            }
        });
        
        // 4. Color Converter
        document.getElementById('hex-to-rgb-btn').addEventListener('click', function() {
            const hex = document.getElementById('hex-input').value.trim();
            if (/^#([0-9A-F]{3}){1,2}$/i.test(hex)) {
                let r, g, b;
                if (hex.length === 4) {
                    r = parseInt(hex[1] + hex[1], 16);
                    g = parseInt(hex[2] + hex[2], 16);
                    b = parseInt(hex[3] + hex[3], 16);
                } else {
                    r = parseInt(hex.substring(1, 3), 16);
                    g = parseInt(hex.substring(3, 5), 16);
                    b = parseInt(hex.substring(5, 7), 16);
                }
                document.getElementById('hex-rgb-output').value = `rgb(${r}, ${g}, ${b})`;
            } else {
                alert('Format HEX warna tidak valid. Gunakan #RGB atau #RRGGBB');
            }
        });
        
        document.getElementById('rgb-to-hex-btn').addEventListener('click', function() {
            const rgb = document.getElementById('rgb-input').value.trim();
            const match = rgb.match(/^rgb\((\d+),\s*(\d+),\s*(\d+)\)$/i);
            if (match) {
                const r = parseInt(match[1]);
                const g = parseInt(match[2]);
                const b = parseInt(match[3]);
                
                if (r >= 0 && r <= 255 && g >= 0 && g <= 255 && b >= 0 && b <= 255) {
                    const hex = '#' + ((1 << 24) + (r << 16) + (g << 8) + b).toString(16).slice(1);
                    document.getElementById('rgb-hex-output').value = hex;
                } else {
                    alert('Nilai RGB harus antara 0 dan 255');
                }
            } else {
                alert('Format RGB tidak valid. Gunakan rgb(R, G, B)');
            }
        });
        
        // 5. HTML Escape/Unescape
        document.getElementById('html-escape-btn').addEventListener('click', function() {
            const input = document.getElementById('html-escape-input').value;
            const escaped = input.replace(/[&<>"'`]/g, function(m) {
                return {
                    '&': '&amp;',
                    '<': '&lt;',
                    '>': '&gt;',
                    '"': '&quot;',
                    "'": '&#39;',
                    '`': '&#96;'
                }[m];
            });
            document.getElementById('html-escape-output').value = escaped;
        });
        
        document.getElementById('html-unescape-btn').addEventListener('click', function() {
            const input = document.getElementById('html-unescape-input').value;
            const unescaped = input.replace(/&amp;|&lt;|&gt;|&quot;|&#39;|&#96;/g, function(m) {
                return {
                    '&amp;': '&',
                    '&lt;': '<',
                    '&gt;': '>',
                    '&quot;': '"',
                    '&#39;': "'",
                    '&#96;': '`'
                }[m];
            });
            document.getElementById('html-unescape-output').value = unescaped;
        });
        
        // 6. Text Diff
        document.getElementById('compare-text-btn').addEventListener('click', function() {
            const textA = document.getElementById('text-diff-a').value;
            const textB = document.getElementById('text-diff-b').value;
            
            const diff = Diff.diffWords(textA, textB);
            const display = document.getElementById('text-diff-result');
            display.innerHTML = '';
            
            diff.forEach((part) => {
                const span = document.createElement('span');
                if (part.added) {
                    span.className = 'diff-added';
                } else if (part.removed) {
                    span.className = 'diff-removed';
                }
                span.appendChild(document.createTextNode(part.value));
                display.appendChild(span);
            });
        });
        
        // 7. Password Generator
        document.getElementById('generate-pass-btn').addEventListener('click', function() {
            const length = document.getElementById('pass-length').value;
            const uppercase = document.getElementById('pass-uppercase').checked;
            const lowercase = document.getElementById('pass-lowercase').checked;
            const numbers = document.getElementById('pass-numbers').checked;
            const symbols = document.getElementById('pass-symbols').checked;
            
            let charset = '';
            if (uppercase) charset += 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
            if (lowercase) charset += 'abcdefghijklmnopqrstuvwxyz';
            if (numbers) charset += '0123456789';
            if (symbols) charset += '!@#$%^&*()_+~`|}{[]\\:;?><,./-=';
            
            if (!charset) {
                alert('Pilih setidaknya satu opsi karakter!');
                return;
            }
            
            let password = '';
            for (let i = 0; i < length; i++) {
                password += charset.charAt(Math.floor(Math.random() * charset.length));
            }
            
            document.getElementById('password-output').value = password;
        });
        
        document.getElementById('copy-pass-btn').addEventListener('click', function() {
            const passOutput = document.getElementById('password-output');
            passOutput.select();
            document.execCommand('copy');
            alert('Password disalin!');
        });
    </script>
    
    <!-- Library untuk Text Diff -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/diff/5.0.0/diff.min.js"></script>
</body>
</html>
