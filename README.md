
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>albraiki77 - Movies & Series</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            background-color: #1a1a1a;
            color: #ffffff;
        }

        header {
            background-color: #0a0a0a;
            padding: 20px;
            text-align: center;
            border-bottom: 2px solid #ff0000;
        }

        h1 {
            color: #ff0000;
            font-size: 2.5em;
        }

        nav {
            background-color: #121212;
            padding: 15px;
            text-align: center;
        }

        .filter-btn {
            background-color: #2d2d2d;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 0 5px;
            cursor: pointer;
            border-radius: 5px;
            transition: all 0.3s;
        }

        .filter-btn:hover {
            background-color: #ff0000;
        }

        .active {
            background-color: #ff0000;
        }

        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 0 20px;
        }

        .content-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .content-card {
            background-color: #2d2d2d;
            border-radius: 10px;
            overflow: hidden;
            transition: transform 0.3s;
        }

        .content-card:hover {
            transform: translateY(-5px);
        }

        .content-img {
            width: 100%;
            height: 350px;
            object-fit: cover;
        }

        .content-info {
            padding: 15px;
        }

        .content-title {
            font-size: 1.2em;
            margin-bottom: 10px;
        }

        .content-details {
            font-size: 0.9em;
            color: #cccccc;
        }

        footer {
            background-color: #0a0a0a;
            text-align: center;
            padding: 20px;
            margin-top: 40px;
            border-top: 2px solid #ff0000;
        }

        .language-tag {
            background-color: #ff0000;
            padding: 3px 8px;
            border-radius: 5px;
            font-size: 0.8em;
            margin-left: 10px;
        }

        @media (max-width: 768px) {
            .content-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 480px) {
            .content-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>albraiki77</h1>
    </header>

    <nav>
        <button class="filter-btn active" onclick="filterContent('all')">All</button>
        <button class="filter-btn" onclick="filterContent('arabic')"><i class="fas fa-book"></i> Arabic</button>
        <button class="filter-btn" onclick="filterContent('english')"><i class="fas fa-star"></i> English</button>
        <button class="filter-btn" onclick="filterContent('movies')">Movies</button>
        <button class="filter-btn" onclick="filterContent('series')">Series</button>
    </nav>

    <div class="container">
        <div class="content-grid" id="contentGrid">
            <!-- Content will be dynamically inserted here -->
        </div>
    </div>

    <footer>
        <p>&copy; 2023 albraiki77. All rights reserved.</p>
    </footer>

    <script>
        // Sample content data
        const contentData = [
            {
                title: "The Matrix",
                image: "https://via.placeholder.com/300x450/333/fff?text=The+Matrix",
                year: 1999,
                language: "english",
                type: "movie"
            },
            {
                title: "مسلسل الواد",
                image: "https://via.placeholder.com/300x450/333/fff?text=مسلسل+الواد",
                year: 2022,
                language: "arabic",
                type: "series"
            },
            {
                title: "Inception",
                image: "https://via.placeholder.com/300x450/333/fff?text=Inception",
                year: 2010,
                language: "english",
                type: "movie"
            },
            {
                title: "فيلم كدبة كل يوم",
                image: "https://via.placeholder.com/300x450/333/fff?text=كدبة+كل+يوم",
                year: 2020,
                language: "arabic",
                type: "movie"
            },
            // Add more content items here...
        ];

        // Generate content cards
        function generateContentCards(filter = 'all') {
            const grid = document.getElementById('contentGrid');
            grid.innerHTML = '';

            contentData.forEach(item => {
                if (filter === 'all' || 
                    item.language === filter || 
                    item.type === filter) {
                    const card = document.createElement('div');
                    card.className = 'content-card';
                    card.innerHTML = `
                        <img src="${item.image}" class="content-img" alt="${item.title}">
                        <div class="content-info">
                            <h3 class="content-title">${item.title}
                                <span class="language-tag">${item.language.toUpperCase()}</span>
                            </h3>
                            <p class="content-details">
                                ${item.year} | ${item.type.charAt(0).toUpperCase() + item.type.slice(1)}
                            </p>
                        </div>
                    `;
                    grid.appendChild(card);
                }
            });
        }

        // Filter content
        function filterContent(filter) {
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            generateContentCards(filter);
        }

        // Initial load
        generateContentCards();
    </script>
</body>
</html>
<!---
hamdan715/hamdan715 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
