<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Google</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Basic Reset & Font */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            background-color: #fff;
            color: #202124;
            overflow: hidden; /* Prevent body scroll */
        }

        /* Google Fonts - Inter */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

        /* Header Styling */
        .header {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            padding: 15px 20px;
        }

        .header .nav-item {
            margin-left: 15px;
            text-decoration: none;
            color: #202124;
            font-size: 13px;
            transition: text-decoration 0.2s ease;
        }

        .header .nav-item:hover {
            text-decoration: underline;
        }

        .header .app-launcher {
            font-size: 20px;
            color: #5f6368;
            margin-left: 15px;
            cursor: pointer;
            padding: 8px;
            border-radius: 50%;
            transition: background-color 0.2s ease;
        }

        .header .app-launcher:hover {
            background-color: #f0f0f0;
        }

        .header .sign-in-button {
            background-color: #1a73e8;
            color: #fff;
            border: none;
            padding: 9px 20px;
            border-radius: 4px;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            margin-left: 15px;
            transition: background-color 0.2s ease, box-shadow 0.2s ease;
        }

        .header .sign-in-button:hover {
            background-color: #186ac9;
            box-shadow: 0 1px 1px rgba(0,0,0,.1);
        }

        /* Main Content Styling */
        .main-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding-bottom: 100px; /* Space for footer */
        }

        .main-content .logo img {
            width: 272px;
            height: 92px;
            margin-bottom: 25px;
        }

        .search-container {
            width: 100%;
            max-width: 584px;
            position: relative;
            margin-bottom: 30px;
        }

        .search-input {
            width: 100%;
            padding: 14px 20px 14px 45px; /* Left padding for search icon */
            border: 1px solid #dfe1e5;
            border-radius: 24px;
            font-size: 16px;
            outline: none;
            box-shadow: 0 2px 5px 1px rgba(64,60,67,.16);
            transition: border-color 0.2s ease, box-shadow 0.2s ease;
        }

        .search-input:focus {
            border-color: #dadce0;
            box-shadow: 0 3px 8px 1px rgba(64,60,67,.24);
        }

        .search-icon {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: #9aa0a6;
            font-size: 16px;
        }

        .search-buttons {
            display: flex;
            justify-content: center;
            gap: 12px;
        }

        .search-button {
            background-color: #f8f9fa;
            border: 1px solid #f8f9fa;
            border-radius: 4px;
            color: #3c4043;
            font-size: 14px;
            padding: 10px 16px;
            cursor: pointer;
            transition: background-color 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
        }

        .search-button:hover {
            background-color: #f0f0f0;
            border-color: #dadce0;
            box-shadow: 0 1px 1px rgba(0,0,0,.1);
        }

        /* Footer Styling */
        .footer {
            background-color: #f2f2f2;
            padding: 15px 20px;
            border-top: 1px solid #dadce0;
            font-size: 14px;
            color: #70757a;
            width: 100%;
            flex-shrink: 0; /* Prevent shrinking */
        }

        .footer-top {
            margin-bottom: 15px;
        }

        .footer-bottom {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap; /* Allow wrapping on smaller screens */
        }

        .footer-links {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
        }

        .footer-link {
            text-decoration: none;
            color: #70757a;
            transition: text-decoration 0.2s ease;
        }

        .footer-link:hover {
            text-decoration: underline;
        }

        /* Responsive Adjustments */
        @media (max-width: 768px) {
            .header {
                padding: 10px 15px;
            }
            .header .nav-item,
            .header .app-launcher {
                margin-left: 10px;
            }
            .header .sign-in-button {
                padding: 8px 15px;
                font-size: 13px;
                margin-left: 10px;
            }
            .main-content .logo img {
                width: 200px;
                height: auto;
                margin-bottom: 20px;
            }
            .search-container {
                max-width: 90%;
            }
            .search-input {
                padding: 12px 15px 12px 40px;
                font-size: 15px;
            }
            .search-icon {
                left: 12px;
                font-size: 15px;
            }
            .search-buttons {
                flex-direction: column;
                gap: 10px;
            }
            .search-button {
                width: 80%; /* Make buttons wider on small screens */
                margin: 0 auto; /* Center buttons */
            }
            .footer {
                padding: 10px 15px;
                font-size: 13px;
            }
            .footer-bottom {
                flex-direction: column;
                align-items: center;
                gap: 10px;
            }
            .footer-links {
                justify-content: center;
                gap: 10px;
            }
        }

        @media (max-width: 480px) {
            .header .nav-item {
                display: none; /* Hide text links on very small screens */
            }
            .header .app-launcher {
                margin-left: auto; /* Push to right */
            }
            .search-input {
                padding: 10px 10px 10px 35px;
                font-size: 14px;
            }
            .search-icon {
                left: 10px;
                font-size: 14px;
            }
            .search-button {
                width: 90%;
            }
            .footer-bottom {
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <a href="#" class="nav-item">Gmail</a>
        <a href="#" class="nav-item">Images</a>
        <i class="fas fa-th app-launcher"></i>
        <button class="sign-in-button">Sign in</button>
    </div>

    <div class="main-content">
        <div class="logo">
            <img src="https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png" alt="Google Logo">
        </div>
        <div class="search-container">
            <i class="fas fa-search search-icon"></i>
            <input type="text" class="search-input" id="search-input" placeholder="">
        </div>
        <div class="search-buttons">
            <button class="search-button" id="google-search-button">Google Search</button>
            <button class="search-button" id="feeling-lucky-button">I'm Feeling Lucky</button>
        </div>
    </div>

    <div class="footer">
        <div class="footer-top">
            India
        </div>
        <div class="footer-bottom">
            <div class="footer-links">
                <a href="#" class="footer-link">About</a>
                <a href="#" class="footer-link">Advertising</a>
                <a href="#" class="footer-link">Business</a>
                <a href="#" class="footer-link">How Search works</a>
            </div>
            <div class="footer-links">
                <a href="#" class="footer-link">Privacy</a>
                <a href="#" class="footer-link">Terms</a>
                <a href="#" class="footer-link">Settings</a>
            </div>
        </div>
    </div>

    <script>
        const searchInput = document.getElementById('search-input');
        const googleSearchButton = document.getElementById('google-search-button');
        const feelingLuckyButton = document.getElementById('feeling-lucky-button');

        // Function to perform a Google search
        function performSearch() {
            const query = searchInput.value.trim();
            if (query) {
                window.location.href = `https://www.google.com/search?q=${encodeURIComponent(query)}`;
            }
        }

        // Event listener for Google Search button
        googleSearchButton.addEventListener('click', performSearch);

        // Event listener for Enter key in the search input
        searchInput.addEventListener('keypress', function(event) {
            if (event.key === 'Enter') {
                performSearch();
            }
        });

        // Event listener for "I'm Feeling Lucky" button
        feelingLuckyButton.addEventListener('click', function() {
            const query = searchInput.value.trim();
            if (query) {
                // This simulates "I'm Feeling Lucky" by redirecting to the first search result.
                // In a real scenario, this would require more complex server-side logic
                // to fetch the first result directly. For this clone, it will still
                // perform a regular search but with the spirit of the button.
                window.location.href = `https://www.google.com/search?q=${encodeURIComponent(query)}&btnI`;
            } else {
                // If no query, "I'm Feeling Lucky" typically goes to a Google Doodles page.
                // For simplicity, we'll just go to the main Google page.
                window.location.href = `https://www.google.com/doodles`;
            }
        });

        // Set focus on the search input when the page loads
        window.onload = function() {
            searchInput.focus();
        };
    </script>
</body>
</html>
