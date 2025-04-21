<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Free online tool to compress your images while maintaining quality. Reduce file size for JPG, PNG, and WebP images.">
    <meta name="keywords" content="image compressor, compress images, reduce image size, online image optimizer, JPG compressor, PNG compressor">
    <title>ImageCompress Pro | Free Online Image Compression Tool</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4361ee;
            --primary-dark: #3a56d4;
            --secondary: #3f37c9;
            --accent: #4895ef;
            --light: #f8f9fa;
            --dark: #212529;
            --gray: #6c757d;
            --light-gray: #e9ecef;
            --success: #4cc9f0;
            --warning: #f72585;
            --border-radius: 12px;
            --box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background-color: #f5f7ff;
            overflow-x: hidden;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background-color: white;
            box-shadow: var(--box-shadow);
            position: sticky;
            top: 0;
            z-index: 100;
            padding: 15px 0;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }

        .logo i {
            font-size: 1.8rem;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        nav a:hover {
            color: var(--primary);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary);
            transition: var(--transition);
        }

        nav a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--dark);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            padding: 60px 0;
            text-align: center;
            background: linear-gradient(135deg, #f5f7ff 0%, #e0e5ff 100%);
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--dark);
            font-weight: 700;
        }

        .hero p {
            font-size: 1.1rem;
            color: var(--gray);
            max-width: 700px;
            margin: 0 auto 30px;
            line-height: 1.7;
        }

        /* Main Tool Container */
        .tool-container {
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            padding: 30px;
            margin: -40px auto 50px;
            position: relative;
            z-index: 1;
            max-width: 900px;
        }

        /* Upload Area */
        .upload-area {
            border: 2px dashed var(--primary);
            border-radius: var(--border-radius);
            padding: 40px 20px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            margin-bottom: 30px;
            background-color: rgba(67, 97, 238, 0.03);
            position: relative;
            overflow: hidden;
        }

        .upload-area:hover {
            background-color: rgba(67, 97, 238, 0.08);
            transform: translateY(-3px);
        }

        .upload-area.active {
            background-color: rgba(72, 149, 239, 0.1);
            border-color: var(--success);
        }

        .upload-area i {
            font-size: 3.5rem;
            color: var(--primary);
            margin-bottom: 15px;
            transition: var(--transition);
        }

        .upload-area.active i {
            color: var(--success);
        }

        .upload-area h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--dark);
        }

        .upload-area p {
            color: var(--gray);
            margin-bottom: 5px;
        }

        .upload-area .file-input {
            display: none;
        }

        .file-info {
            display: none;
            margin-top: 15px;
            padding: 10px;
            background-color: rgba(76, 201, 240, 0.1);
            border-radius: 8px;
            color: var(--dark);
        }

        .file-info.active {
            display: block;
        }

        /* Controls Section */
        .controls {
            margin-bottom: 30px;
        }

        .control-group {
            margin-bottom: 25px;
        }

        .control-group label {
            display: block;
            margin-bottom: 12px;
            font-weight: 600;
            color: var(--dark);
        }

        .slider-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .slider {
            flex-grow: 1;
            height: 8px;
            -webkit-appearance: none;
            appearance: none;
            background: var(--light-gray);
            border-radius: 10px;
            outline: none;
            transition: var(--transition);
        }

        .slider:hover {
            background: #d3d9e8;
        }

        .slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 22px;
            height: 22px;
            border-radius: 50%;
            background: var(--primary);
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        .slider::-webkit-slider-thumb:hover {
            background: var(--primary-dark);
            transform: scale(1.1);
        }

        .slider-value {
            width: 50px;
            text-align: center;
            font-weight: 700;
            color: var(--primary);
            background: rgba(67, 97, 238, 0.1);
            padding: 5px 10px;
            border-radius: 20px;
        }

        .format-options {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
        }

        .format-option {
            position: relative;
        }

        .format-option input {
            position: absolute;
            opacity: 0;
            width: 0;
            height: 0;
        }

        .format-option label {
            display: inline-block;
            padding: 10px 20px;
            background-color: var(--light-gray);
            border-radius: 8px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
            border: 1px solid transparent;
        }

        .format-option input:checked + label {
            background-color: var(--primary);
            color: white;
            border-color: var(--primary-dark);
        }

        .format-option label:hover {
            background-color: #dde2f0;
        }

        /* Buttons */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            padding: 14px 28px;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: var(--border-radius);
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            text-align: center;
            box-shadow: 0 4px 6px rgba(67, 97, 238, 0.2);
        }

        .btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(67, 97, 238, 0.25);
        }

        .btn:active {
            transform: translateY(0);
        }

        .btn:disabled {
            background-color: var(--gray);
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
            opacity: 0.7;
        }

        .btn-compress {
            width: 100%;
            margin-top: 20px;
        }

        .btn-download {
            background-color: var(--success);
            box-shadow: 0 4px 6px rgba(76, 201, 240, 0.2);
        }

        .btn-download:hover {
            background-color: #3ab4d9;
            box-shadow: 0 6px 12px rgba(76, 201, 240, 0.25);
        }

        /* Results Section */
        .results {
            display: none;
            margin-top: 40px;
            padding-top: 30px;
            border-top: 1px solid var(--light-gray);
        }

        .results h2 {
            font-size: 1.5rem;
            margin-bottom: 25px;
            color: var(--dark);
        }

        .result-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 30px;
        }

        .result-card {
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            overflow: hidden;
            transition: var(--transition);
        }

        .result-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -5px rgba(0, 0, 0, 0.04);
        }

        .image-preview {
            width: 100%;
            height: 200px;
            object-fit: contain;
            background-color: var(--light);
            border-bottom: 1px solid var(--light-gray);
        }

        .result-details {
            padding: 20px;
        }

        .result-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--dark);
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .result-stats {
            display: flex;
            flex-direction: column;
            gap: 8px;
            margin-bottom: 20px;
        }

        .stat-row {
            display: flex;
            justify-content: space-between;
        }

        .stat-label {
            color: var(--gray);
            font-weight: 500;
        }

        .stat-value {
            font-weight: 600;
        }

        .reduction {
            color: var(--success);
            font-weight: 700;
        }

        .error-card {
            border-left: 4px solid var(--warning);
        }

        .error-message {
            color: var(--warning);
            font-weight: 500;
        }

        /* Ad Containers */
        .ad-container {
            margin: 40px 0;
            text-align: center;
            min-height: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            overflow: hidden;
            padding: 20px;
        }

        .ad-placeholder {
            width: 100%;
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* Info Section */
        .info-section {
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            padding: 40px;
            margin-bottom: 40px;
        }

        .info-section h2 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--dark);
        }

        .info-section p {
            color: var(--gray);
            margin-bottom: 15px;
            line-height: 1.7;
        }

        /* Features Grid */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin: 40px 0;
        }

        .feature-card {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
            text-align: center;
        }

        .feature-card:hover {
            transform: translateY(-5px);
        }

        .feature-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 1.2rem;
            margin-bottom: 15px;
            color: var(--dark);
        }

        .feature-card p {
            color: var(--gray);
            font-size: 0.95rem;
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h3 {
            font-size: 1.2rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-col h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background-color: var(--primary);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 12px;
        }

        .footer-links a {
            color: #adb5bd;
            text-decoration: none;
            transition: var(--transition);
            display: inline-block;
        }

        .footer-links a:hover {
            color: white;
            transform: translateX(5px);
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--primary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #adb5bd;
            font-size: 0.9rem;
        }

        /* Loading Animation */
        .loader {
            display: none;
            width: 100%;
            height: 4px;
            background-color: var(--light-gray);
            border-radius: 2px;
            overflow: hidden;
            margin-bottom: 20px;
        }

        .loader.active {
            display: block;
        }

        .loader-bar {
            height: 100%;
            width: 0;
            background-color: var(--primary);
            border-radius: 2px;
            transition: width 0.3s ease;
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .tool-container {
                padding: 25px;
            }
        }

        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }
            
            nav {
                position: fixed;
                top: 70px;
                left: 0;
                width: 100%;
                background-color: white;
                box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
                padding: 20px;
                transform: translateY(-150%);
                opacity: 0;
                transition: var(--transition);
                z-index: 99;
            }
            
            nav.active {
                transform: translateY(0);
                opacity: 1;
            }
            
            nav ul {
                flex-direction: column;
                gap: 15px;
            }
            
            .hero {
                padding: 50px 0;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .result-container {
                grid-template-columns: 1fr;
            }
            
            .footer-grid {
                grid-template-columns: 1fr 1fr;
            }
        }

        @media (max-width: 576px) {
            .hero {
                padding: 40px 0;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .tool-container {
                padding: 20px;
                margin: -30px auto 40px;
            }
            
            .upload-area {
                padding: 30px 15px;
            }
            
            .format-options {
                flex-direction: column;
                gap: 10px;
            }
            
            .format-option label {
                width: 100%;
                text-align: center;
            }
            
            .footer-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-compress-alt"></i>
                <span>ImageCompress Pro</span>
            </a>
            
            <button class="mobile-menu-btn" id="mobileMenuBtn">
                <i class="fas fa-bars"></i>
            </button>
            
            <nav id="mainNav">
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Features</a></li>
                    <li><a href="#">How It Works</a></li>
                    <li><a href="#">FAQ</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h1>Optimize Your Images in Seconds</h1>
            <p>Reduce image file sizes without sacrificing quality. Perfect for websites, social media, and email attachments. Completely free with no watermarks.</p>
        </div>
    </section>

    <div class="container">
        <!-- Top Ad Banner -->
        <div class="ad-container">
            <!-- Google AdSense Code -->
            <ins class="adsbygoogle"
                 style="display:block"
                 data-ad-client="ca-pub-YOUR_AD_CLIENT_ID"
                 data-ad-slot="YOUR_AD_SLOT_ID"
                 data-ad-format="auto"
                 data-full-width-responsive="true"></ins>
            <script>
                 (adsbygoogle = window.adsbygoogle || []).push({});
            </script>
        </div>

        <!-- Main Tool Container -->
        <div class="tool-container">
            <div class="upload-area" id="uploadArea">
                <i class="fas fa-cloud-upload-alt"></i>
                <h3>Drag & Drop Your Images Here</h3>
                <p>or click to browse files</p>
                <span class="small-text">Supports JPG, PNG, WebP (Max: 10MB each)</span>
                <input type="file" id="fileInput" class="file-input" accept="image/*" multiple>
                <div class="file-info" id="fileInfo"></div>
            </div>

            <div class="loader" id="loader">
                <div class="loader-bar" id="loaderBar"></div>
            </div>

            <div class="controls">
                <div class="control-group">
                    <label for="compressionLevel">Compression Quality: <span id="compressionValue">70</span>%</label>
                    <div class="slider-container">
                        <input type="range" id="compressionLevel" class="slider" min="0" max="100" value="70">
                        <span class="slider-value" id="compressionDisplay">70%</span>
                    </div>
                </div>

                <div class="control-group">
                    <label>Output Format:</label>
                    <div class="format-options">
                        <div class="format-option">
                            <input type="radio" id="formatOriginal" name="outputFormat" value="original" checked>
                            <label for="formatOriginal">Original</label>
                        </div>
                        <div class="format-option">
                            <input type="radio" id="formatJpg" name="outputFormat" value="jpg">
                            <label for="formatJpg">JPG</label>
                        </div>
                        <div class="format-option">
                            <input type="radio" id="formatPng" name="outputFormat" value="png">
                            <label for="formatPng">PNG</label>
                        </div>
                        <div class="format-option">
                            <input type="radio" id="formatWebp" name="outputFormat" value="webp">
                            <label for="formatWebp">WebP</label>
                        </div>
                    </div>
                </div>
            </div>

            <button id="compressBtn" class="btn btn-compress" disabled>
                <i class="fas fa-compress-alt"></i> Compress Images
            </button>

            <div class="results" id="resultsSection">
                <h2><i class="fas fa-chart-bar"></i> Compression Results</h2>
                <div class="result-container" id="resultContainer">
                    <!-- Results will be inserted here dynamically -->
                </div>
            </div>
        </div>

        <!-- Features Section -->
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-lock"></i>
                </div>
                <h3>Privacy Focused</h3>
                <p>All processing happens in your browser. Your images are never uploaded to our servers.</p>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-bolt"></i>
                </div>
                <h3>Lightning Fast</h3>
                <p>Optimized algorithms process your images in seconds, even on mobile devices.</p>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-chart-line"></i>
                </div>
                <h3>Smart Compression</h3>
                <p>Advanced techniques reduce file size while preserving visual quality.</p>
            </div>
        </div>

        <!-- Middle Ad Banner -->
        <div class="ad-container">
            <!-- Google AdSense Code -->
            <ins class="adsbygoogle"
                 style="display:block"
                 data-ad-client="ca-pub-YOUR_AD_CLIENT_ID"
                 data-ad-slot="YOUR_AD_SLOT_ID"
                 data-ad-format="auto"
                 data-full-width-responsive="true"></ins>
            <script>
                 (adsbygoogle = window.adsbygoogle || []).push({});
            </script>
        </div>

        <!-- Info Section -->
        <div class="info-section">
            <h2>Why Image Compression Matters</h2>
            <p>In today's digital world, fast-loading websites are crucial for user experience and SEO rankings. Large images are one of the biggest factors slowing down page load times. Our tool helps you find the perfect balance between quality and file size.</p>
            <p>Whether you're a web developer, blogger, or social media manager, properly optimized images can make a significant difference in your site's performance and user engagement.</p>
        </div>

        <!-- Bottom Ad Banner -->
        <div class="ad-container">
            <!-- Google AdSense Code -->
            <ins class="adsbygoogle"
                 style="display:block"
                 data-ad-client="ca-pub-YOUR_AD_CLIENT_ID"
                 data-ad-slot="YOUR_AD_SLOT_ID"
                 data-ad-format="auto"
                 data-full-width-responsive="true"></ins>
            <script>
                 (adsbygoogle = window.adsbygoogle || []).push({});
            </script>
        </div>
    </div>

    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col">
                    <h3>ImageCompress Pro</h3>
                    <p>The free online tool for optimizing your images without quality loss. Perfect for web developers and content creators.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                    </div>
                </div>
                
                <div class="footer-col">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#">Home</a></li>
                        <li><a href="#">Features</a></li>
                        <li><a href="#">How It Works</a></li>
                        <li><a href="#">FAQ</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Resources</h3>
                    <ul class="footer-links">
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Documentation</a></li>
                        <li><a href="#">API</a></li>
                        <li><a href="#">Support</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>Legal</h3>
                    <ul class="footer-links">
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Cookie Policy</a></li>
                        <li><a href="#">GDPR</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                &copy; <span id="currentYear"></span> ImageCompress Pro. All rights reserved.
            </div>
        </div>
    </footer>

    <script>
        // Mobile Menu Toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mainNav = document.getElementById('mainNav');
        
        mobileMenuBtn.addEventListener('click', () => {
            mainNav.classList.toggle('active');
            mobileMenuBtn.innerHTML = mainNav.classList.contains('active') 
                ? '<i class="fas fa-times"></i>' 
                : '<i class="fas fa-bars"></i>';
        });

        // Set current year in footer
        document.getElementById('currentYear').textContent = new Date().getFullYear();

        // Compression level slider
        const compressionLevel = document.getElementById('compressionLevel');
        const compressionValue = document.getElementById('compressionValue');
        const compressionDisplay = document.getElementById('compressionDisplay');
        
        compressionLevel.addEventListener('input', function() {
            const value = this.value;
            compressionValue.textContent = value;
            compressionDisplay.textContent = `${value}%`;
            
            // Update color based on value
            if (value < 30) {
                compressionDisplay.style.color = '#f72585'; // Low quality
            } else if (value < 70) {
                compressionDisplay.style.color = '#4895ef'; // Medium quality
            } else {
                compressionDisplay.style.color = '#4cc9f0'; // High quality
            }
        });

        // File upload handling
        const uploadArea = document.getElementById('uploadArea');
        const fileInput = document.getElementById('fileInput');
        const fileInfo = document.getElementById('fileInfo');
        const compressBtn = document.getElementById('compressBtn');
        const resultsSection = document.getElementById('resultsSection');
        const resultContainer = document.getElementById('resultContainer');
        const loader = document.getElementById('loader');
        const loaderBar = document.getElementById('loaderBar');
        
        // Handle drag and drop
        ['dragover', 'dragenter'].forEach(eventName => {
            uploadArea.addEventListener(eventName, (e) => {
                e.preventDefault();
                uploadArea.classList.add('active');
            });
        });
        
        ['dragleave', 'dragend', 'drop'].forEach(eventName => {
            uploadArea.addEventListener(eventName, (e) => {
                e.preventDefault();
                uploadArea.classList.remove('active');
            });
        });
        
        uploadArea.addEventListener('drop', (e) => {
            e.preventDefault();
            if (e.dataTransfer.files.length) {
                fileInput.files = e.dataTransfer.files;
                handleFiles(fileInput.files);
            }
        });
        
        uploadArea.addEventListener('click', () => {
            fileInput.click();
        });
        
        fileInput.addEventListener('change', () => {
            if (fileInput.files.length) {
                handleFiles(fileInput.files);
            }
        });
        
        function handleFiles(files) {
            // Clear previous results
            resultContainer.innerHTML = '';
            resultsSection.style.display = 'none';
            
            // Update file info display
            let fileList = '';
            for (let i = 0; i < Math.min(files.length, 3); i++) {
                fileList += `<div>${files[i].name} (${formatFileSize(files[i].size)})</div>`;
            }
            if (files.length > 3) {
                fileList += `<div>+ ${files.length - 3} more files</div>`;
            }
            
            fileInfo.innerHTML = fileList;
            fileInfo.classList.add('active');
            
            // Enable compress button
            compressBtn.disabled = false;
            
            // Update upload area appearance
            const uploadIcon = uploadArea.querySelector('i');
            const uploadText = uploadArea.querySelector('h3');
            
            uploadIcon.className = 'fas fa-check-circle';
            uploadText.textContent = `${files.length} file(s) selected`;
        }
        
        function formatFileSize(bytes) {
            if (bytes === 0) return '0 Bytes';
            const k = 1024;
            const sizes = ['Bytes', 'KB', 'MB', 'GB'];
            const i = Math.floor(Math.log(bytes) / Math.log(k));
            return parseFloat((bytes / Math.pow(k, i)).toFixed(2) + ' ' + sizes[i];
        }
        
        // Compression functionality
        compressBtn.addEventListener('click', async () => {
            if (!fileInput.files.length) return;
            
            // Show loading state
            compressBtn.disabled = true;
            compressBtn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Compressing...';
            loader.classList.add('active');
            
            // Clear previous results
            resultContainer.innerHTML = '';
            resultsSection.style.display = 'none';
            
            // Get selected options
            const compressionQuality = compressionLevel.value / 100;
            const outputFormat = document.querySelector('input[name="outputFormat"]:checked').value;
            
            // Process each file
            const totalFiles = fileInput.files.length;
            let processedFiles = 0;
            
            for (let i = 0; i < totalFiles; i++) {
                const file = fileInput.files[i];
                
                try {
                    // Update progress bar
                    loaderBar.style.width = `${(processedFiles / totalFiles) * 100}%`;
                    
                    const compressedFile = await compressImage(file, compressionQuality, outputFormat);
                    displayResult(file, compressedFile);
                    processedFiles++;
                    
                    // Update progress bar
                    loaderBar.style.width = `${(processedFiles / totalFiles) * 100}%`;
                    
                    // Show results after first file is processed
                    if (processedFiles === 1) {
                        resultsSection.style.display = 'block';
                    }
                } catch (error) {
                    console.error('Error compressing image:', error);
                    displayError(file, error.message);
                    processedFiles++;
                }
            }
            
            // Reset button state
            compressBtn.disabled = false;
            compressBtn.innerHTML = '<i class="fas fa-compress-alt"></i> Compress Images';
            loader.classList.remove('active');
            loaderBar.style.width = '0';
        });
        
        async function compressImage(file, quality, format) {
            return new Promise((resolve, reject) => {
                if (!file.type.match('image.*')) {
                    reject(new Error('File is not an image'));
                    return;
                }
                
                if (file.size > 10 * 1024 * 1024) { // 10MB limit
                    reject(new Error('File size exceeds 10MB limit'));
                    return;
                }
                
                const reader = new FileReader();
                
                reader.onload = function(event) {
                    const img = new Image();
                    
                    img.onload = function() {
                        const canvas = document.createElement('canvas');
                        const ctx = canvas.getContext('2d');
                        
                        // Calculate new dimensions maintaining aspect ratio
                        let width = img.width;
                        let height = img.height;
                        const maxDimension = 2500; // Max width/height
                        
                        if (width > maxDimension || height > maxDimension) {
                            const ratio = Math.min(maxDimension / width, maxDimension / height);
                            width = Math.floor(width * ratio);
                            height = Math.floor(height * ratio);
                        }
                        
                        canvas.width = width;
                        canvas.height = height;
                        
                        // Draw image on canvas
                        ctx.imageSmoothingQuality = 'high';
                        ctx.drawImage(img, 0, 0, width, height);
                        
                        // Determine output format
                        let mimeType;
                        if (format === 'original') {
                            mimeType = file.type;
                        } else if (format === 'jpg') {
                            mimeType = 'image/jpeg';
                        } else if (format === 'png') {
                            mimeType = 'image/png';
                        } else if (format === 'webp') {
                            mimeType = 'image/webp';
                        }
                        
                        // Convert to blob with specified quality
                        canvas.toBlob((blob) => {
                            if (!blob) {
                                reject(new Error('Compression failed'));
                                return;
                            }
                            
                            const compressedFile = new File([blob], getOutputFilename(file.name, mimeType), {
                                type: mimeType,
                                lastModified: Date.now()
                            });
                            
                            resolve(compressedFile);
                        }, mimeType, quality);
                    };
                    
                    img.onerror = function() {
                        reject(new Error('Failed to load image'));
                    };
                    
                    img.src = event.target.result;
                };
                
                reader.onerror = function() {
                    reject(new Error('Failed to read file'));
                };
                
                reader.readAsDataURL(file);
            });
        }
        
        function getOutputFilename(originalName, mimeType) {
            const extension = mimeType.split('/')[1];
            const nameWithoutExt = originalName.lastIndexOf('.') > 0 
                ? originalName.substring(0, originalName.lastIndexOf('.')) 
                : originalName;
            return `compressed_${nameWithoutExt}.${extension}`;
        }
        
        function displayResult(originalFile, compressedFile) {
            const originalSize = originalFile.size;
            const compressedSize = compressedFile.size;
            const reduction = ((1 - (compressedSize / originalSize)) * 100;
            
            const resultCard = document.createElement('div');
            resultCard.className = 'result-card';
            
            // Create image preview
            const imgPreview = document.createElement('img');
            imgPreview.className = 'image-preview';
            imgPreview.alt = 'Compressed result';
            
            const reader = new FileReader();
            reader.onload = function(e) {
                imgPreview.src = e.target.result;
            };
            reader.readAsDataURL(compressedFile);
            
            // Create download button
            const downloadBtn = document.createElement('button');
            downloadBtn.className = 'btn btn-download';
            downloadBtn.innerHTML = '<i class="fas fa-download"></i> Download';
            
            downloadBtn.addEventListener('click', () => {
                const a = document.createElement('a');
                a.href = URL.createObjectURL(compressedFile);
                a.download = compressedFile.name;
                document.body.appendChild(a);
                a.click();
                document.body.removeChild(a);
                URL.revokeObjectURL(a.href);
            });
            
            // Build result card content
            resultCard.innerHTML = `
                <img class="image-preview" src="" alt="Compressed result">
                <div class="result-details">
                    <div class="result-title" title="${originalFile.name}">${originalFile.name}</div>
                    <div class="result-stats">
                        <div class="stat-row">
                            <span class="stat-label">Original:</span>
                            <span class="stat-value">${formatFileSize(originalSize)}</span>
                        </div>
                        <div class="stat-row">
                            <span class="stat-label">Compressed:</span>
                            <span class="stat-value">${formatFileSize(compressedSize)}</span>
                        </div>
                        <div class="stat-row">
                            <span class="stat-label">Reduction:</span>
                            <span class="stat-value reduction">${reduction.toFixed(2)}%</span>
                        </div>
                    </div>
                </div>
            `;
            
            // Replace the placeholder image with the actual one
            resultCard.querySelector('.image-preview').src = imgPreview.src;
            
            // Add download button
            resultCard.querySelector('.result-details').appendChild(downloadBtn);
            resultContainer.appendChild(resultCard);
        }
        
        function displayError(file, errorMessage) {
            const resultCard = document.createElement('div');
            resultCard.className = 'result-card error-card';
            
            resultCard.innerHTML = `
                <div class="result-details">
                    <div class="result-title">${file.name}</div>
                    <div class="error-message">
                        <i class="fas fa-exclamation-circle"></i> ${errorMessage}
                    </div>
                </div>
            `;
            
            resultContainer.appendChild(resultCard);
        }
    </script>
</body>
</html>
