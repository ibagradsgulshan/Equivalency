<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>O/A Level Equivalence Calculator — AI Tool</title>

  <!-- Tailwind via CDN for quick styling -->
  <script src="https://cdn.tailwindcss.com"></script>

  <style>
    /* Use a professional and readable English font */
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap');
    
    body { 
      font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; 
      background-color: #f8fafc; /* Lighter, cleaner background */
      background-image: linear-gradient(180deg, #f3f7ff, #e8f1ff);
    }
    
    .glass { 
      background: rgba(255, 255, 255, 0.7); 
      backdrop-filter: blur(10px); 
      -webkit-backdrop-filter: blur(10px); 
      box-shadow: 0 8px 32px 0 rgba(100, 149, 237, 0.15);
      border-radius: 1rem; 
      border: 1px solid rgba(255, 255, 255, 0.5);
    }
    
    label { font-weight: 600; }
    
    .fade-in { animation: fadeIn 0.5s ease-out both; }
    .slide-down { animation: slideDown 0.4s ease-out both; }
    
    @keyframes fadeIn { 
      from { opacity: 0; transform: translateY(8px); } 
      to { opacity: 1; transform: translateY(0); } 
    }
    @keyframes slideDown { 
      from { opacity: 0; transform: translateY(-10px); } 
      to { opacity: 1; transform: translateY(0); } 
    }
    
    /* Print styling improvements */
    @media print {
      body { background: white; }
      .no-print { display: none !important; }
      .glass { box-shadow: none; border: 1px solid #ccc; }
      #resultCard { display: block !important; }
      html, body { height: auto; }
    }
  </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4 md:p-6 bg-gray-50 text-gray-800">

  <main class="w-full max-w-4xl mx-auto space-y-8">
    <header class="text-center fade-in">
        <img src="https://iili.io/KTdjGbj.png" alt="Calculator Logo" class="mx-auto h-20 w-auto mb-4">
        <h1 class="text-3xl md:text-4xl font-extrabold text-sky-800">O/A Level Equivalence Calculator</h1>
        <p class="mt-2 text-md text-sky-600">Enter your grades below to instantly estimate your Pakistani equivalence.</p>
    </header>

    <section class="glass p-6 md:p-8 fade-in" style="animation-delay: 0.1s;">
      <form id="calcForm" class="space-y-6">
        <!-- Main settings row -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 border-b pb-6">
          <div>
            <label for="examType" class="block mb-2 text-sky-900">Select Exam Type</label>
            <select id="examType" class="w-full rounded-lg border-gray-300 px-3 py-2 shadow-sm focus:border-sky-500 focus:ring-sky-500">
              <option value="o">O Level / IGCSE</option>
              <option value="a">A Level</option>
              <option value="both">Both O + A Levels</option>
            </select>
          </div>
          <div>
            <label for="mappingPreset" class="block mb-2 text-sky-900">Grade Mapping</label>
            <select id="mappingPreset" class="w-full rounded-lg border-gray-300 px-3 py-2 shadow-sm focus:border-sky-500 focus:ring-sky-500">
              <option value="default">Default (A*=90, A=85, B=75...)</option>
              <option value="higher">Higher A* (A*=95, A=90...)</option>
            </select>
          </div>
        </div>

        <!-- Dynamic Subjects Area -->
        <div class="space-y-2">
            <h3 class="text-lg font-bold text-sky-800">Subjects</h3>
            <div id="subjectsArea" class="space-y-3">
              <!-- dynamic subject rows will appear here -->
            </div>
        </div>

        <!-- Action Buttons for Subjects and Calculation -->
        <div class="flex flex-wrap gap-3 items-center pt-4 border-t mt-6">
          <button id="addSubjectBtn" type="button" class="px-4 py-2 bg-sky-600 text-white rounded-lg hover:bg-sky-700 transition-colors no-print">
            + Add Subject
          </button>
          <button id="calcBtn" type="button" class="px-5 py-2 bg-green-600 text-white font-bold rounded-lg hover:bg-green-700 transition-colors no-print">
            Calculate Result
          </button>
          <button id="resetBtn" type="button" class="px-4 py-2 bg-gray-200 text-gray-700 rounded-lg hover:bg-gray-300 transition-colors no-print">
            Reset
          </button>
        </div>
      </form>
    </section>

    <!-- Result Card (Initially Hidden) -->
    <section id="resultCard" class="glass p-6 md:p-8 hidden slide-down">
      <div class="flex justify-between items-start mb-4">
        <h2 class="text-2xl font-bold text-sky-800">Your Estimated Result</h2>
        <button id="printBtn" class="px-4 py-2 bg-sky-600 hover:bg-sky-700 text-white rounded-lg no-print">
          Print
        </button>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-5 gap-6">
        <!-- Summary on the left -->
        <div class="md:col-span-2 p-6 bg-sky-700 text-white rounded-lg flex flex-col items-center justify-center text-center">
            <h3 class="text-lg font-semibold opacity-80">Overall Percentage</h3>
            <div id="summaryPercent" class="text-5xl font-extrabold my-2">0%</div>
            <div id="summaryAdvice" class="mt-2 opacity-90"></div>
        </div>

        <!-- Details on the right -->
        <div class="md:col-span-3 p-6 bg-white/80 rounded-lg">
            <h3 class="font-bold mb-3 text-sky-900">Details</h3>
            <div id="calculationDetails" class="text-sm text-gray-700 space-y-2"></div>
        </div>
      </div>
    </section>

    <footer class="text-center text-sm text-gray-600 pb-6 fade-in" style="animation-delay: 0.2s;">
      <div>Equivalence Calculator</div>
      <div class="mt-1">This equivalency is only for your reference; the actual and final equivalency will be provided by IBCC.</div>
    </footer>
  </main>

  <script>
    document.addEventListener('DOMContentLoaded', () => {
      // --- DOM Elements ---
      const subjectsArea = document.getElementById('subjectsArea');
      const addSubjectBtn = document.getElementById('addSubjectBtn');
      const mappingPreset = document.getElementById('mappingPreset');
      const examType = document.getElementById('examType');
      const calcBtn = document.getElementById('calcBtn');
      const resetBtn = document.getElementById('resetBtn');
      const resultCard = document.getElementById('resultCard');
      const calculationDetails = document.getElementById('calculationDetails');
      const summaryPercent = document.getElementById('summaryPercent');
      const summaryAdvice = document.getElementById('summaryAdvice');
      const printBtn = document.getElementById('printBtn');

      // --- Data and State ---
      let subjectCounter = 0;
      const gradeOptions = ["A*", "A", "B", "C", "D", "E", "U"];
      const mappings = {
        default: { "A*": 90, "A": 85, "B": 75, "C": 65, "D": 55, "E": 45, "U": 0 },
        higher:  { "A*": 95, "A": 90, "B": 80, "C": 70, "D": 60, "E": 50, "U": 0 }
      };

      // --- Functions ---

      /**
       * Adds a new subject input row to the form.
       */
      function addSubjectRow() {
        subjectCounter++;
        const row = document.createElement('div');
        row.className = 'grid grid-cols-1 md:grid-cols-12 gap-2 items-end subject-row fade-in';
        row.innerHTML = `
          <div class="md:col-span-4">
            <label class="text-sm font-medium text-gray-700">Subject ${subjectCounter}</label>
            <input type="text" placeholder="e.g., Mathematics" class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 subjectName" />
          </div>
          <div class="md:col-span-2">
            <label class="text-sm font-medium text-gray-700">Grade</label>
            <select class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 gradeSelect">
              ${gradeOptions.map(g => `<option value="${g}">${g}</option>`).join('')}
            </select>
          </div>
          <div class="md:col-span-2">
            <label class="text-sm font-medium text-gray-700">Weight/Units</label>
            <input type="number" min="0.5" step="0.5" value="1" class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 weightInput" />
          </div>
          <div class="md:col-span-3">
            <label class="text-sm font-medium text-gray-700">Notes</label>
            <input type="text" placeholder="Optional" class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 noteInput" />
          </div>
          <div class="md:col-span-1">
            <button type="button" title="Remove Subject" class="remove-btn w-full h-10 bg-red-500 text-white rounded-md hover:bg-red-600 transition-colors flex items-center justify-center font-bold text-xl no-print">&times;</button>
          </div>
        `;
        subjectsArea.appendChild(row);
      }

      /**
       * Handles calculation logic and displays the results.
       */
      function calculateAndShowResults() {
        const subjectRows = document.querySelectorAll('.subject-row');
        if (subjectRows.length === 0) {
            alert('Please add at least one subject to calculate.');
            return;
        }

        const preset = mappingPreset.value || 'default';
        const currentMap = mappings[preset];

        let totalWeight = 0;
        let weightedSum = 0;
        let detailLines = [];

        subjectRows.forEach((row, i) => {
          const grade = row.querySelector('.gradeSelect').value;
          const weight = parseFloat(row.querySelector('.weightInput').value) || 1;
          const subjName = row.querySelector('.subjectName').value || `Subject ${i + 1}`;
          const note = row.querySelector('.noteInput').value || '';
          const points = currentMap[grade] !== undefined ? currentMap[grade] : 0;
          
          totalWeight += weight;
          weightedSum += points * weight;

          detailLines.push({ subj: subjName, grade, weight, points, note });
        });

        if (totalWeight <= 0) {
          alert('The total weight of subjects must be greater than zero.');
          return;
        }

        const avgPercent = weightedSum / totalWeight;
        const avgRounded = Math.round((avgPercent + Number.EPSILON) * 100) / 100;

        // Render details
        calculationDetails.innerHTML = detailLines.map(d => `
          <div class="flex justify-between items-center border-b border-gray-200 py-1">
            <span><strong>${d.subj}</strong> (Grade: ${d.grade}, Weight: ${d.weight})</span>
            <span class="font-semibold text-sky-700">${d.points} Points</span>
          </div>
        `).join('') + `<div class="flex justify-between items-center pt-2 font-bold text-md"><span>Total Average:</span><span>${avgRounded}%</span></div>`;

        // Render summary
        summaryPercent.textContent = `${avgRounded}%`;
        
        let suggestedEquivalence = '';
        const level = examType.value;
        if (level === 'o') {
            suggestedEquivalence = getEquivalenceMessage('Matric', avgRounded);
        } else if (level === 'a') {
            suggestedEquivalence = getEquivalenceMessage('Intermediate', avgRounded);
        } else {
            suggestedEquivalence = `${getEquivalenceMessage('Matric', avgRounded)}<br>${getEquivalenceMessage('Intermediate', avgRounded)}`;
        }
        summaryAdvice.innerHTML = suggestedEquivalence;

        // Show result card
        resultCard.classList.remove('hidden');
        resultCard.scrollIntoView({ behavior: 'smooth', block: 'start' });
      }

      /**
       * Returns an informal equivalence message based on percentage.
       * @param {string} level - "Matric" or "Intermediate"
       * @param {number} percent - The calculated average percentage.
       * @returns {string} - A formatted string with the equivalence suggestion.
       */
      function getEquivalenceMessage(level, percent) {
        let remark = '';
        if (percent >= 85) remark = 'A+ Grade / Outstanding';
        else if (percent >= 75) remark = 'A Grade / Excellent';
        else if (percent >= 60) remark = 'B Grade / Very Good';
        else if (percent >= 50) remark = 'C Grade / Good';
        else if (percent >= 40) remark = 'D Grade / Satisfactory';
        else remark = 'Needs Improvement';
        return `<strong>Equivalent to ${level}:</strong> ${remark}`;
      }

      /**
       * Resets the form to its initial state.
       */
      function resetForm() {
        subjectsArea.innerHTML = '';
        subjectCounter = 0;
        for (let i = 0; i < 5; i++) addSubjectRow(); // Start with 5 subjects
        
        mappingPreset.value = 'default';
        examType.value = 'o';
        resultCard.classList.add('hidden');
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }

      // --- Event Listeners ---
      addSubjectBtn.addEventListener('click', addSubjectRow);

      subjectsArea.addEventListener('click', (e) => {
        if (e.target.classList.contains('remove-btn')) {
          if (subjectsArea.childElementCount > 1) {
            e.target.closest('.subject-row').remove();
          } else {
            alert('At least one subject is required.');
          }
        }
      });

      calcBtn.addEventListener('click', calculateAndShowResults);
      resetBtn.addEventListener('click', resetForm);
      printBtn.addEventListener('click', () => window.print());

      // Accessibility: Enter key triggers calculation
      document.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' && document.activeElement.tagName !== 'TEXTAREA' && !document.activeElement.classList.contains('remove-btn')) {
          e.preventDefault();
          calcBtn.click();
        }
      });

      // --- Initialisation ---
      resetForm(); // Call reset to build the initial form
    });
  </script>
</body>
</html>




