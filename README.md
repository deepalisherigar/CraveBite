import weasyprint

html_content = """<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>README - CraveBite</title>
    <style>
        @page {
            size: A4;
            margin: 16mm 14mm;
            background-color: #121212;
        }

        *, *::before, *::after {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            padding: 0;
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            background-color: #121212;
            color: #E0E0E0;
            font-size: 10pt;
            line-height: 1.5;
        }

        /* Banner Header */
        .header-banner {
            background: linear-gradient(135deg, #1E1E1E 0%, #2A1A08 100%);
            border: 1px solid #FF6B00;
            border-radius: 12px;
            padding: 24px 28px;
            margin-bottom: 22px;
            text-align: center;
        }

        .header-title {
            font-size: 26pt;
            font-weight: 800;
            color: #FF6B00;
            margin: 0 0 6px 0;
            letter-spacing: -0.5px;
        }

        .header-subtitle {
            font-size: 11pt;
            color: #B0B0B0;
            margin: 0 0 14px 0;
            font-weight: 400;
        }

        .badges {
            margin-top: 10px;
        }

        .badge {
            display: inline-block;
            background-color: #262626;
            color: #FF6B00;
            border: 1px solid #FF6B00;
            padding: 3px 10px;
            border-radius: 12px;
            font-size: 8pt;
            font-weight: 600;
            margin: 0 4px;
        }

        /* Section Styling */
        h2 {
            font-size: 14pt;
            color: #FFFFFF;
            border-left: 4px solid #FF6B00;
            padding-left: 10px;
            margin-top: 20px;
            margin-bottom: 12px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            page-break-after: avoid;
        }

        h3 {
            font-size: 11pt;
            color: #FFB800;
            margin-top: 14px;
            margin-bottom: 6px;
            page-break-after: avoid;
        }

        p {
            margin: 0 0 10px 0;
            color: #CCCCCC;
        }

        ul, ol {
            margin: 0 0 12px 0;
            padding-left: 20px;
            color: #CCCCCC;
        }

        li {
            margin-bottom: 4px;
        }

        /* Cards & Highlight Boxes */
        .grid-box {
            background-color: #1E1E1E;
            border: 1px solid #333333;
            border-radius: 8px;
            padding: 14px 16px;
            margin-bottom: 14px;
        }

        .grid-box strong {
            color: #FFFFFF;
        }

        /* Code Block Styling */
        pre, code {
            font-family: 'Courier New', Courier, monospace;
            background-color: #181818;
            color: #FFB800;
            border-radius: 4px;
        }

        code {
            padding: 2px 5px;
            font-size: 9pt;
            border: 1px solid #333;
        }

        pre {
            padding: 12px 16px;
            border: 1px solid #333;
            overflow-x: auto;
            font-size: 8.5pt;
            line-height: 1.4;
            white-space: pre-wrap;
            word-wrap: break-word;
            margin: 10px 0;
        }

        /* Tables */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 12px 0;
            font-size: 9pt;
        }

        th, td {
            padding: 8px 12px;
            text-align: left;
            border: 1px solid #333333;
        }

        th {
            background-color: #252525;
            color: #FF6B00;
            font-weight: 700;
        }

        td {
            background-color: #1A1A1A;
            color: #DDDDDD;
        }

        tr:nth-child(even) td {
            background-color: #1E1E1E;
        }

        /* Footer / Credits */
        .footer {
            margin-top: 25px;
            padding-top: 12px;
            border-top: 1px solid #333333;
            text-align: center;
            font-size: 8.5pt;
            color: #888888;
        }

        .highlight {
            color: #FF6B00;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="header-banner">
        <div class="header-title">🍲 CraveBite</div>
        <div class="header-subtitle">Modern & Responsive Web Application for Online Food Ordering</div>
        <div class="badges">
            <span class="badge">JavaScript (ES6+)</span>
            <span class="badge">SQLite (WASM / SQL.js)</span>
            <span class="badge">HTML5 / CSS3</span>
            <span class="badge">Client-Side Storage</span>
        </div>
    </div>

    <h2>📌 Project Overview</h2>
    <div class="grid-box">
        <p><strong>CraveBite</strong> is a feature-rich, interactive web application designed for seamlessly ordering food online [cite: 5]. Built with standard HTML5, CSS3, and JavaScript, it leverages an embedded in-browser <strong>SQLite database (via WebAssembly / SQL.js)</strong> to maintain user accounts, saved addresses, persistent shopping carts, and detailed order histories without requiring an external backend server [cite: 2, 3, 5].</p>
    </div>

    <h2>✨ Key Features</h2>
    <ul>
        <li><strong>Dynamic Menu Browsing:</strong> Explore meals, snacks, beverages, desserts, and starters with real-time text searching, category filtering, and vegetarian-only toggling [cite: 1, 5, 8].</li>
        <li><strong>Embedded In-Browser SQLite Database:</strong> Utilizes <code>sql.js</code> to run a client-side database, persisting state directly inside <code>localStorage</code> [cite: 2].</li>
        <li><strong>User Authentication System:</strong> Complete registration and sign-in functionality with hashed credentials and active user session tracking [cite: 2, 3, 6].</li>
        <li><strong>Interactive Shopping Cart:</strong> Real-time quantity adjustments, subtotal computation, GST calculation, and delivery fee evaluation [cite: 5, 8].</li>
        <li><strong>Checkout & Delivery Management:</strong> Address management (add/save multiple addresses) and multi-tab payment gateways (Card, UPI, Net Banking, COD) [cite: 2, 3, 5, 8].</li>
        <li><strong>Order Tracking & History:</strong> View past orders with status timestamps, payment confirmation, and estimated delivery info [cite: 2, 3, 5, 8].</li>
        <li><strong>Self-Healing Image Script:</strong> Includes Python scripts that automatically detect broken image URLs and fallback to active placeholders or external API alternatives [cite: 4, 7].</li>
    </ul>

    <h2>📁 Repository Structure</h2>
    <table>
        <thead>
            <tr>
                <th>File / Folder</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><code>index.html</code></td>
                <td>Main application page featuring the navigation bar, hero banner, filterable menu, cart sidebar, and checkout modals [cite: 5].</td>
            </tr>
            <tr>
                <td><code>login.html</code></td>
                <td>Dedicated login & registration page with seamless tab switching and authentication integration [cite: 6].</td>
            </tr>
            <tr>
                <td><code>styles.css</code></td>
                <td>Custom CSS providing dark theme styling, flex/grid layouts, animations, and responsive components [cite: 5, 9].</td>
            </tr>
            <tr>
                <td><code>script.js</code></td>
                <td>Core UI logic handling menu rendering, search filters, cart operations, modals, and checkout workflows [cite: 8].</td>
            </tr>
            <tr>
                <td><code>db.js</code></td>
                <td>Initializes SQLite via <code>sql.js</code> (WASM), defines relational schema, seeds data, and persists database state to <code>localStorage</code> [cite: 2].</td>
            </tr>
            <tr>
                <td><code>dbHelper.js</code></td>
                <td>Provides async query helper methods for users, addresses, cart items, menu querying, and order processing [cite: 3].</td>
            </tr>
            <tr>
                <td><code>data.js</code></td>
                <td>Initial dataset containing predefined food items across various categories with ratings, prices, and imagery [cite: 1].</td>
            </tr>
            <tr>
                <td><code>fix_images.py</code> / <code>update_data.py</code></td>
                <td>Utility Python scripts to validate image URLs, query TheMealDB API, and auto-correct invalid visual references [cite: 4, 7].</td>
            </tr>
        </tbody>
    </table>

    <h2>🗄️ Database Schema</h2>
    <p>The SQLite database (<code>db.js</code>) manages several relational tables [cite: 2]:</p>
    <ul>
        <li><code>users</code> — Stores <code>user_id</code>, <code>full_name</code>, <code>email</code>, <code>password_hash</code>, and registration timestamps [cite: 2].</li>
        <li><code>addresses</code> — Stores saved delivery addresses linked to a specific <code>user_id</code> [cite: 2].</li>
        <li><code>menu_items</code> — Contains food items with price, rating, category, dietary badges, and descriptions [cite: 2].</li>
        <li><code>cart</code> — Tracks item quantities per user before placing an order [cite: 2].</li>
        <li><code>orders</code> & <code>order_items</code> — Captures finalized transactions, payment modes, financial totals, and individual dish line items [cite: 2].</li>
        <li><code>delivery_info</code> — Maintains driver information and live tracking coordinates [cite: 2].</li>
    </ul>

    <h2>🚀 Getting Started</h2>
    <h3>Prerequisites</h3>
    <p>Because the app runs client-side using WebAssembly for SQLite, it is best served using a basic local HTTP web server to avoid browser CORS restrictions on <code>.wasm</code> files [cite: 2, 5].</p>

    <h3>Installation & Running</h3>
    <ol>
        <li>Clone the repository:
            <pre><code>git clone https://github.com/your-username/cravebite.git
cd cravebite</code></pre>
        </li>
        <li>Start a local development server (e.g., using Python):
            <pre><code># Python 3.x
python -m http.server 8000</code></pre>
        </li>
        <li>Open your browser and navigate to:
            <pre><code>http://localhost:8000</code></pre>
        </li>
    </ol>

    <h2>👥 Credits & Acknowledgments</h2>
    <div class="grid-box">
        <p><strong>Created By:</strong> Deepali Sherigar & Bhumika Pai [cite: 5]</p>
        <p><strong>External Resources & Libraries:</strong></p>
        <ul>
            <li><a href="https://github.com/sql-js/sql.js" style="color: #FF6B00;">SQL.js</a> — SQLite compiled to WebAssembly [cite: 2, 5].</li>
            <li><a href="https://boxicons.com/" style="color: #FF6B00;">Boxicons</a> — Clean, high-quality iconography [cite: 5].</li>
            <li><a href="https://fonts.google.com/" style="color: #FF6B00;">Google Fonts</a> — <em>DM Sans</em> & <em>Playfair Display</em> typography [cite: 5].</li>
            <li><a href="https://www.themealdb.com/" style="color: #FF6B00;">TheMealDB</a> — Recipe images & descriptions [cite: 1, 7].</li>
        </ul>
    </div>

    <div class="footer">
        CraveBite © 2026 — Taste the Magic in Every Bite [cite: 5].
    </div>

</body>
</html>
"""

with open("cravebite_readme.html", "w", encoding="utf-8") as f:
    f.write(html_content)

weasyprint.HTML("cravebite_readme.html").write_pdf("README_CraveBite.pdf")
print("PDF generated successfully.")
