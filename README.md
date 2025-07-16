# Shrabon-weekly-
Simple personal vlog post and photographs 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Blog & Photos</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Navigation */
        .navbar {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(15px);
            border-radius: 25px;
            padding: 15px 30px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            color: white;
            font-size: 1.8em;
            font-weight: bold;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        .nav-links {
            display: flex;
            gap: 20px;
        }

        .nav-link {
            color: white;
            text-decoration: none;
            padding: 12px 24px;
            border-radius: 20px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .nav-link:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
        }

        .nav-link.active {
            background: rgba(255, 255, 255, 0.3);
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .mobile-menu {
            display: none;
            color: white;
            font-size: 1.5em;
            cursor: pointer;
        }

        /* Page Content */
        .page {
            display: none;
            animation: fadeIn 0.5s ease-in;
        }

        .page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Hero Section */
        .hero {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 25px;
            padding: 60px 40px;
            text-align: center;
            margin-bottom: 40px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .hero h1 {
            color: white;
            font-size: 3.5em;
            margin-bottom: 20px;
            text-shadow: 0 4px 8px rgba(0,0,0,0.3);
        }

        .hero p {
            color: rgba(255, 255, 255, 0.9);
            font-size: 1.3em;
            margin-bottom: 30px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.6;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .hero-btn {
            padding: 15px 35px;
            border: none;
            border-radius: 30px;
            font-size: 1.1em;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            font-weight: 500;
        }

        .hero-btn.primary {
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
        }

        .hero-btn.secondary {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .hero-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.3);
        }

        /* Content Sections */
        .content-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .section-title {
            color: white;
            font-size: 2.2em;
            margin-bottom: 30px;
            text-align: center;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        .section-subtitle {
            color: white;
            font-size: 1.8em;
            margin-bottom: 20px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        /* Form Styles */
        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            color: white;
            margin-bottom: 10px;
            font-weight: 500;
            font-size: 1.1em;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 15px;
            border: none;
            border-radius: 12px;
            background: rgba(255, 255, 255, 0.9);
            font-size: 1em;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            box-shadow: 0 0 0 3px rgba(255, 255, 255, 0.3);
            transform: scale(1.02);
        }

        .form-group textarea {
            height: 120px;
            resize: vertical;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .file-upload {
            position: relative;
            display: inline-block;
            cursor: pointer;
            width: 100%;
        }

        .file-upload input[type="file"] {
            position: absolute;
            opacity: 0;
            width: 100%;
            height: 100%;
            cursor: pointer;
        }

        .file-upload-label {
            display: block;
            padding: 20px;
            background: rgba(255, 255, 255, 0.2);
            border: 2px dashed rgba(255, 255, 255, 0.5);
            border-radius: 15px;
            text-align: center;
            color: white;
            transition: all 0.3s ease;
            font-size: 1.1em;
        }

        .file-upload:hover .file-upload-label {
            background: rgba(255, 255, 255, 0.3);
            transform: scale(1.02);
        }

        .btn {
            padding: 15px 30px;
            border: none;
            border-radius: 25px;
            font-size: 1.1em;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
            margin-right: 10px;
            margin-bottom: 10px;
        }

        .btn-primary {
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        /* Cards */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
        }

        .card h3 {
            color: white;
            margin-bottom: 15px;
            font-size: 1.4em;
        }

        .card p {
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.6;
            margin-bottom: 15px;
        }

        .card .meta {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9em;
            margin-bottom: 15px;
        }

        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 15px;
            margin-bottom: 15px;
        }

        .photos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .photo-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .photo-card:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
        }

        .photo-card img {
            width: 100%;
            height: 220px;
            object-fit: cover;
            cursor: pointer;
        }

        .photo-card .caption {
            padding: 20px;
            color: white;
        }

        .delete-btn {
            background: rgba(255, 107, 107, 0.8);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 15px;
            cursor: pointer;
            font-size: 0.9em;
            margin-top: 10px;
            transition: all 0.3s ease;
        }

        .delete-btn:hover {
            background: rgba(255, 107, 107, 1);
            transform: scale(1.05);
        }

        /* About Page Styles */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-top: 30px;
        }

        .about-text {
            color: rgba(255, 255, 255, 0.9);
            line-height: 1.8;
            font-size: 1.1em;
        }

        .about-image {
            text-align: center;
        }

        .about-image img {
            width: 100%;
            max-width: 300px;
            height: 300px;
            object-fit: cover;
            border-radius: 20px;
            border: 3px solid rgba(255, 255, 255, 0.3);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }

        .skill-icon {
            font-size: 2.5em;
            margin-bottom: 15px;
        }

        .skill-card h4 {
            color: white;
            margin-bottom: 10px;
            font-size: 1.2em;
        }

        .skill-card p {
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.5;
        }

        /* Contact Form */
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .contact-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }

        .contact-icon {
            font-size: 2.5em;
            margin-bottom: 15px;
        }

        .contact-item h4 {
            color: white;
            margin-bottom: 10px;
            font-size: 1.2em;
        }

        .contact-item p {
            color: rgba(255, 255, 255, 0.8);
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(5px);
        }

        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            max-width: 90%;
            max-height: 90%;
        }

        .modal-content img {
            max-width: 100%;
            max-height: 100%;
            border-radius: 15px;
        }

        .close {
            position: absolute;
            top: 15px;
            right: 35px;
            color: white;
            font-size: 40px;
            font-weight: bold;
            cursor: pointer;
            z-index: 1001;
        }

        .close:hover {
            color: #ff6b6b;
        }

        /* Stats */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .stat-number {
            font-size: 2.5em;
            color: white;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .stat-label {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1em;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .mobile-menu {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.5em;
            }
            
            .hero p {
                font-size: 1.1em;
            }
            
            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .cards-grid {
                grid-template-columns: 1fr;
            }
            
            .photos-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .container {
                padding: 15px;
            }
        }

        @media (max-width: 480px) {
            .hero {
                padding: 40px 20px;
            }
            
            .content-section {
                padding: 25px;
            }
            
            .nav-content {
                padding: 0 15px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Navigation -->
        <nav class="navbar">
            <div class="nav-content">
                <div class="logo">MyBlog</div>
                <div class="nav-links">
                    <a href="#" class="nav-link active" onclick="showPage('home')">Home</a>
                    <a href="#" class="nav-link" onclick="showPage('blog')">Blog</a>
                    <a href="#" class="nav-link" onclick="showPage('gallery')">Gallery</a>
                    <a href="#" class="nav-link" onclick="showPage('about')">About</a>
                    <a href="#" class="nav-link" onclick="showPage('contact')">Contact</a>
                </div>
                <div class="mobile-menu" onclick="toggleMobileMenu()">☰</div>
            </div>
        </nav>

        <!-- Home Page -->
        <div id="home" class="page active">
            <div class="hero">
                <h1>Welcome to My Blog</h1>
                <p>Discover amazing stories, beautiful photography, and creative content. Join me on this journey of sharing experiences and connecting with the world.</p>
                <div class="hero-buttons">
                    <button class="hero-btn primary" onclick="showPage('blog')">Read My Blog</button>
                    <button class="hero-btn secondary" onclick="showPage('gallery')">View Gallery</button>
                </div>
            </div>

            <div class="content-section">
                <h2 class="section-title">Latest Content</h2>
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-number" id="blogCount">0</div>
                        <div class="stat-label">Blog Posts</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="photoCount">0</div>
                        <div class="stat-label">Photos</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="visitCount">247</div>
                        <div class="stat-label">Visitors</div>
                    </div>
                </div>
            </div>

            <div class="content-section">
                <h2 class="section-title">Recent Posts</h2>
                <div id="recentPosts" class="cards-grid"></div>
            </div>
        </div>

        <!-- Blog Page -->
        <div id="blog" class="page">
            <div class="content-section">
                <h2 class="section-title">Create New Blog Post</h2>
                <form id="blogForm">
                    <div class="form-row">
                        <div class="form-group">
                            <label for="blogTitle">Title</label>
                            <input type="text" id="blogTitle" required>
                        </div>
                        <div class="form-group">
                            <label for="blogCategory">Category</label>
                            <select id="blogCategory">
                                <option value="Personal">Personal</option>
                                <option value="Technology">Technology</option>
                                <option value="Travel">Travel</option>
                                <option value="Food">Food</option>
                                <option value="Photography">Photography</option>
                                <option value="Other">Other</option>
                            </select>
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="blogContent">Content</label>
                        <textarea id="blogContent" required placeholder="Write your blog post here..."></textarea>
                    </div>
                    <div class="form-group">
                        <label for="blogImage">Featured Image (optional)</label>
                        <div class="file-upload">
                            <input type="file" id="blogImage" accept="image/*">
                            <label for="blogImage" class="file-upload-label">
                                📸 Click to select an image
                            </label>
                        </div>
                    </div>
                    <button type="submit" class="btn btn-primary">Publish Post</button>
                    <button type="button" class="b
