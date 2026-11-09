# Every-day-Science-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Everyday Science - Shan Ali Junejo</title>
  <style>
    :root {
      --bg-color: #ffffff;
      --text-color: #1a1a1a;
      --card-bg: #f8f9fa;
      --accent-color: #0d6efd;
      --border-color: #e0e0e0;
    }

    body.dark-mode {
      --bg-color: #121212;
      --text-color: #e0e0e0;
      --card-bg: #1e1e1e;
      --accent-color: #3d8bfd;
      --border-color: #333333;
    }

    body.sepia-mode {
      --bg-color: #f4ecd8;
      --text-color: #5b4636;
      --card-bg: #eae0d0;
      --accent-color: #8b5a2b;
      --border-color: #d8c8b0;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif; }
    body { background-color: var(--bg-color); color: var(--text-color); transition: background-color 0.3s, color 0.3s; padding-bottom: 60px; }

    header {
      position: sticky; top: 0; z-index: 100; background-color: var(--card-bg);
      border-bottom: 1px solid var(--border-color); padding: 12px 16px;
      display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 4px rgba(0,0,0,0.05);
    }

    header h1 { font-size: 1.1rem; font-weight: 700; color: var(--accent-color); }
    .controls button { background: none; border: 1px solid var(--border-color); color: var(--text-color); padding: 6px 10px; border-radius: 4px; cursor: pointer; font-size: 0.9rem; margin-left: 4px; }

    .search-bar { padding: 12px 16px; background-color: var(--bg-color); }
    .search-bar input { width: 100%; padding: 10px; border: 1px solid var(--border-color); border-radius: 8px; background: var(--card-bg); color: var(--text-color); }

    main { padding: 16px; max-width: 800px; margin: 0 auto; }
    .topic-card { background: var(--card-bg); border: 1px solid var(--border-color); border-radius: 8px; padding: 16px; margin-bottom: 12px; }
    .topic-card h3 { font-size: 1rem; margin-bottom: 8px; color: var(--accent-color); }
    .mcq-option { margin-top: 4px; font-size: 0.95rem; }
    .answer { margin-top: 8px; font-weight: bold; color: #198754; font-size: 0.9rem; }

    footer { position: fixed; bottom: 0; left: 0; right: 0; background: var(--card-bg); border-top: 1px solid var(--border-color); padding: 10px; text-align: center; font-size: 0.85rem; }
  </style>
</head>
<body>

  <header>
    <h1>Everyday Science Notes</h1>
    <div class="controls">
      <button onclick="changeFontSize(1)">A+</button>
      <button onclick="changeFontSize(-1)">A-</button>
      <button onclick="toggleTheme()">🎨 Theme</button>
    </div>
  </header>

  <div class="search-bar">
    <input type="text" id="searchInput" placeholder="Search MCQs or topics (e.g., Vitamin, Planet, Cell)..." onkeyup="searchNotes()">
  </div>

  <main id="contentArea">
    <!-- Chapter 1 Sample MCQs extracted from PDF -->
    <div class="topic-card">
      <h3>1. Which is the outermost planet in the solar system?</h3>
      <div class="mcq-option">A. Mercury | B. Pluto | C. Neptune | D. Uranus</div>
      <div class="answer">Correct Answer: C. Neptune</div>
    </div>

    <div class="topic-card">
      <h3>2. Severe deficiency of Vitamin D results in?</h3>
      <div class="mcq-option">A. Scurvy | B. Rickets | C. Night blindness | D. None of these</div>
      <div class="answer">Correct Answer: B. Rickets</div>
    </div>

    <div class="topic-card">
      <h3>3. The SI unit of charge is?</h3>
      <div class="mcq-option">A. Ampere | B. Coulomb | C. Ohm | D. Volt</div>
      <div class="answer">Correct Answer: B. Coulomb</div>
    </div>

    <div class="topic-card">
      <h3>4. The lifespan of Red Blood Cells is?</h3>
      <div class="mcq-option">A. 60 days | B. 120 days | C. 180 days | D. 240 days</div>
      <div class="answer">Correct Answer: B. 120 days</div>
    </div>

    <div class="topic-card">
      <h3>5. The density of water is?</h3>
      <div class="mcq-option">A. 1 g/cm³ | B. 1.5 g/cm³ | C. 2 g/cm³ | D. None of these</div>
      <div class="answer">Correct Answer: A. 1 g/cm³</div>
    </div>
  </main>

  <footer>
    Book compiled by Shan Ali Junejo | Prepared for PPSC, FPSC & CSS Exams
  </footer>

  <script>
    let currentTheme = 0; // 0: light, 1: dark, 2: sepia
    const themes = ['', 'dark-mode', 'sepia-mode'];
    let currentFontSize = 16;

    function toggleTheme() {
      document.body.classList.remove(themes[currentTheme]);
      currentTheme = (currentTheme + 1) % themes.length;
      if (themes[currentTheme]) {
        document.body.classList.add(themes[currentTheme]);
      }
    }

    function changeFontSize(delta) {
      currentFontSize = Math.max(12, Math.min(24, currentFontSize + delta));
      document.getElementById('contentArea').style.fontSize = currentFontSize + 'px';
    }

    function searchNotes() {
      let input = document.getElementById('searchInput').value.toLowerCase();
      let cards = document.getElementsByClassName('topic-card');
      for (let card of cards) {
        let text = card.innerText.toLowerCase();
        card.style.display = text.includes(input) ? "block" : "none";
      }
    }
  </script>
</body>
</html>
