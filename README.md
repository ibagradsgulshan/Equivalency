<html lang="en" class=""> <!-- 'dark' class will be toggled here -->
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>O/A Level Equivalence Calculator — Pakistan</title>

  <!-- Tailwind via CDN for quick styling -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Google Fonts: Inter & a serif font for headings -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Lora:wght@700&display=swap" rel="stylesheet">

  <style>
    /* Custom styles for a polished, educational look */
    body { 
      font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; 
      /* Light mode background */
      background-color: #f5f3f0;
      background-image: 
        linear-gradient(rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0.8)),
        url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100'%3E%3Cg fill-rule='evenodd'%3E%3Cg fill='%23d1d5db' fill-opacity='0.1'%3E%3Cpath opacity='.5' d='M96 95h4v1h-4v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9zm-1 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm9-10v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm9-10v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
      transition: background-color 0.3s ease;
    }
    .educational-header { font-family: 'Lora', serif; }

    /* Dark mode styles */
    .dark body { 
      background-color: #0d132a; /* Dark navy */
      background-image: 
        linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
        url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100'%3E%3Cg fill-rule='evenodd'%3E%3Cg fill='%231e293b' fill-opacity='0.4'%3E%3Cpath opacity='.5' d='M96 95h4v1h-4v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4h-9v4h-1v-4H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15v-9H0v-1h15V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h9V0h1v15h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9h4v1h-4v9zm-1 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm9-10v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm9-10v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-10 0v-9h-9v9h9zm-9-10h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9zm10 0h9v-9h-9v9z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    }
    .dark .glass {
      background: rgba(13, 19, 42, 0.7); /* Darker navy glass */
      backdrop-filter: blur(12px); 
      -webkit-backdrop-filter: blur(12px); 
      border-color: rgba(40, 53, 147, 0.5);
      box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.2);
    }
    .dark .text-gray-800 { color: #e8e6e1; } /* Light cream */
    .dark .educational-header, .dark .text-navy-800 { color: #a3b2f8; } /* Light indigo */
    .dark .text-navy-600 { color: #c5cae9; } /* Lighter indigo */
    .dark .text-navy-900 { color: #e8eaf6; } /* Almost white indigo */
    .dark .text-gray-600 { color: #9e9e9e; }
    .dark .text-gray-700 { color: #bdbdbd; }
    .dark .border-gray-300 { border-color: #3949ab; } /* Indigo border */
    .dark input, .dark select { 
        background-color: #1a237e; /* Dark indigo */
        color: #e8eaf6; 
        border-color: #3949ab;
    }
    .dark input::placeholder { color: #9fa8da; }
    .dark .bg-gray-200 { background-color: #283593; } /* Mid indigo */
    .dark .hover\:bg-gray-300:hover { background-color: #303f9f; }
    .dark .bg-white\/80 { background-color: rgba(26, 35, 126, 0.8); }

    .glass { 
      background: rgba(255, 255, 255, 0.7); 
      backdrop-filter: blur(10px); 
      -webkit-backdrop-filter: blur(10px); 
      box-shadow: 0 8px 32px 0 rgba(40, 53, 147, 0.1);
      border-radius: 1rem; 
      border: 1px solid rgba(255, 255, 255, 0.6);
      transition: background 0.3s ease, border-color 0.3s ease;
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

    .modal-overlay { transition: opacity 0.2s ease-in-out; }
    .modal-box { transition: transform 0.2s ease-in-out, opacity 0.2s ease-in-out; }
    .modal-hidden .modal-overlay { opacity: 0; }
    .modal-hidden .modal-box { transform: scale(0.95); opacity: 0; }
    
    @media print {
      body { background: white; }
      .no-print { display: none !important; }
      .glass { box-shadow: none; border: 1px solid #ccc; background: white; }
      #resultCard, #infoSection { display: block !important; }
      html, body { height: auto; }
      .print-header { display: block !important; text-align: center; margin-bottom: 2rem; }
    }
  </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4 md:p-6 text-gray-800">

  <!-- Custom Modal -->
  <div id="customModal" class="fixed inset-0 z-50 flex items-center justify-center p-4 modal-hidden pointer-events-none">
    <div class="modal-overlay fixed inset-0 bg-black bg-opacity-50"></div>
    <div class="modal-box bg-white dark:bg-slate-800 rounded-lg shadow-xl p-6 w-full max-w-sm text-center transform">
        <h3 id="modalTitle" class="text-lg font-bold text-navy-800 dark:text-indigo-300 mb-4 educational-header">Notification</h3>
        <p id="modalMessage" class="text-gray-700 dark:text-slate-300 mb-6"></p>
        <button id="modalCloseBtn" class="px-6 py-2 bg-navy-700 text-white rounded-lg hover:bg-navy-800 transition-colors">OK</button>
    </div>
  </div>

  <main class="w-full max-w-4xl mx-auto space-y-8">
    <header class="text-center fade-in relative">
        <div class="absolute top-0 right-0 p-2 sm:p-4 flex items-center gap-2">
            
            <button id="darkModeToggle" class="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors no-print" title="Toggle Dark Mode">
                <svg id="sunIcon" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-navy-800 dark:hidden"><path d="M12 1v2m0 18v2M4.22 4.22l1.42 1.42m12.72 12.72 1.42 1.42M1 12h2m18 0h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"/><circle cx="12" cy="12" r="5"/></svg>
                <svg id="moonIcon" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-indigo-300 hidden dark:block"><path d="M12 3a6 6 0 0 0 9 9 9 9 0 1 1-9-9Z"/></svg>
            </button>
        </div>
        <!-- Thematic icon representing 'equivalence' -->
        <img src="https://iili.io/KTdjGbj.png" alt="Site Logo" class="mx-auto h-16 sm:h-20 w-auto mb-4 rounded-full no-print">
        <h1 class="text-2xl sm:text-3xl md:text-4xl font-extrabold text-navy-800 educational-header">O/A Level Equivalence Calculator</h1>
        <p class="mt-2 text-sm sm:text-base text-navy-600">Enter your grades below to instantly estimate your Pakistani equivalence.</p>
    </header>

    <section class="glass p-4 sm:p-6 md:p-8 fade-in" style="animation-delay: 0.1s;">
      <form id="calcForm" class="space-y-6">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 border-b border-gray-300 pb-6">
          <div>
            <label for="examType" class="block mb-2 text-navy-900">Select Exam Type</label>
            <select id="examType" class="w-full rounded-lg border-gray-300 px-3 py-2 shadow-sm focus:border-indigo-500 focus:ring-indigo-500">
              <option value="o">O Level / IGCSE</option>
              <option value="a">A Level</option>
              <option value="both">Both O + A Levels</option>
            </select>
          </div>
          <div>
            <label for="mappingPreset" class="block mb-2 text-navy-900">Grade Mapping</label>
            <select id="mappingPreset" class="w-full rounded-lg border-gray-300 px-3 py-2 shadow-sm focus:border-indigo-500 focus:ring-indigo-500">
              <option value="default">Default (A*=90, A=85, B=75...)</option>
              <option value="higher">Higher A* (A*=95, A=90...)</option>
            </select>
          </div>
        </div>

        <div class="space-y-2">
            <h3 class="text-lg font-bold text-navy-800 educational-header">Subjects</h3>
            <div id="subjectsArea" class="space-y-3"></div>
        </div>

        <div class="flex flex-wrap gap-3 items-center justify-center sm:justify-start pt-4 border-t border-gray-300 mt-6">
          <button id="addSubjectBtn" type="button" class="flex items-center gap-2 px-4 py-2 bg-indigo-700 text-white rounded-lg hover:bg-indigo-800 transition-colors no-print">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>
            Add Subject
          </button>
          <button id="calcBtn" type="button" class="flex items-center gap-2 px-5 py-2 bg-amber-600 text-white font-bold rounded-lg hover:bg-amber-700 transition-colors no-print">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"/><rect x="8" y="2" width="8" height="4" rx="1" ry="1"/></svg>
            Calculate Result
          </button>
          <button id="resetBtn" type="button" class="flex items-center gap-2 px-4 py-2 bg-gray-200 text-gray-700 rounded-lg hover:bg-gray-300 transition-colors no-print">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 2v6h6"/><path d="M21 12A9 9 0 0 0 6 5.3L3 8"/><path d="M21 22v-6h-6"/><path d="M3 12a9 9 0 0 0 15 6.7l3-2.7"/></svg>
            Reset
          </button>
        </div>
      </form>
    </section>

    <!-- Result Card -->
    <section id="resultCard" class="glass p-4 sm:p-6 md:p-8 hidden slide-down">
      <div class="print-header hidden">
          <h2 class="text-2xl font-bold">Equivalence Calculation Report</h2>
          <p class="text-sm">Generated on: <span id="printDate"></span></p>
      </div>
      <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center mb-4">
        <h2 class="text-xl sm:text-2xl font-bold text-navy-800 educational-header mb-2 sm:mb-0">Your Estimated Result</h2>
        <button id="printBtn" class="flex items-center gap-2 px-4 py-2 bg-indigo-700 hover:bg-indigo-800 text-white rounded-lg no-print self-end sm:self-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"/><path d="M6 9V3a1 1 0 0 1 1-1h10a1 1 0 0 1 1 1v6"/><rect x="6" y="14" width="12" height="8" rx="1"/></svg>
          Print
        </button>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-5 gap-6">
        <div class="md:col-span-2 p-6 bg-navy-800 dark:bg-indigo-900 text-white rounded-lg flex flex-col items-center justify-center text-center">
            <h3 class="text-lg font-semibold opacity-80 educational-header">Overall Percentage</h3>
            <div id="summaryPercent" class="text-4xl sm:text-5xl font-extrabold my-2">0%</div>
            <div id="summaryAdvice" class="mt-2 opacity-90 text-sm sm:text-base"></div>
        </div>

        <div class="md:col-span-3 p-4 sm:p-6 bg-white/80 dark:bg-slate-900/80 rounded-lg">
            <h3 class="font-bold mb-3 text-navy-900 educational-header">Details</h3>
            <div id="calculationDetails" class="text-sm text-gray-700 space-y-2"></div>
        </div>
      </div>
    </section>
    
    <!-- Info Section -->
    <section id="infoSection" class="glass p-4 sm:p-6 md:p-8 fade-in" style="animation-delay: 0.2s;">
      <h2 class="text-xl sm:text-2xl font-bold text-navy-800 educational-header mb-4">About IBCC Equivalence</h2>
      <div class="space-y-3 text-gray-700 dark:text-slate-300 text-sm sm:text-base">
        <p>The <a href="https://ibcc.edu.pk/" target="_blank" rel="noopener noreferrer" class="text-indigo-600 dark:text-indigo-400 font-semibold hover:underline">Inter Board Committee of Chairmen (IBCC)</a> is the sole authority in Pakistan for granting equivalence to foreign qualifications like O/A Levels, IGCSE, and IB.</p>
        <p>This calculator provides an <strong class="text-navy-800 dark:text-indigo-300">unofficial estimate</strong> based on standard conversion formulas. The final marks and certificate are issued exclusively by the IBCC after a formal application process.</p>
        <p><strong>Key Requirements for Equivalence:</strong></p>
        <ul class="list-disc list-inside pl-4 space-y-1">
          <li><strong>O-Level/IGCSE:</strong> A minimum of eight subjects, including compulsory subjects: English, Mathematics, Urdu, Islamiyat, and Pakistan Studies.</li>
          <li><strong>A-Level:</strong> A minimum of three A-Level subjects.</li>
        </ul>
        <p>For official procedures and the latest updates, please visit the official IBCC website. The Karachi office is one of the main regional centers for processing applications.</p>
      </div>
    </section>

    <footer class="text-center text-sm text-gray-600 pb-6 fade-in" style="animation-delay: 0.3s;">
      <div>O/A Level Equivalence Calculator | Developed in Karachi</div>
      <div class="mt-1">Disclaimer: This is an estimation tool. The final and official equivalence is only provided by the IBCC.</div>
      <div class="mt-2 text-xs text-gray-500">Last logic update: September 2025</div>
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
      const darkModeToggle = document.getElementById('darkModeToggle');
      const sunIcon = document.getElementById('sunIcon');
      const moonIcon = document.getElementById('moonIcon');
      const htmlEl = document.documentElement;
      const customModal = document.getElementById('customModal');
      const modalMessage = document.getElementById('modalMessage');
      const modalCloseBtn = document.getElementById('modalCloseBtn');

      // --- Data and State ---
      let subjectCounter = 0;
      const gradeOptions = ["A*", "A", "B", "C", "D", "E", "U"];
      const mappings = {
        default: { "A*": 90, "A": 85, "B": 75, "C": 65, "D": 55, "E": 45, "U": 0 },
        higher:  { "A*": 95, "A": 90, "B": 80, "C": 70, "D": 60, "E": 50, "U": 0 }
      };

      // --- Functions ---
      function showModal(message) {
        modalMessage.textContent = message;
        customModal.classList.remove('modal-hidden', 'pointer-events-none');
        document.body.style.overflow = 'hidden';
      }

      function hideModal() {
        customModal.classList.add('modal-hidden', 'pointer-events-none');
        document.body.style.overflow = '';
      }

      function addSubjectRow(data = {}) {
        subjectCounter++;
        const row = document.createElement('div');
        row.className = 'grid grid-cols-12 gap-2 items-end subject-row fade-in';
        row.innerHTML = `
          <div class="col-span-12 md:col-span-6">
            <label class="text-xs sm:text-sm font-medium text-gray-700">Subject ${subjectCounter}</label>
            <input type="text" placeholder="e.g., Physics" value="${data.name || ''}" class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 subjectName" />
          </div>
          <div class="col-span-6 md:col-span-3">
            <label class="text-xs sm:text-sm font-medium text-gray-700">Grade</label>
            <select class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 gradeSelect">
              ${gradeOptions.map(g => `<option value="${g}" ${data.grade === g ? 'selected' : ''}>${g}</option>`).join('')}
            </select>
          </div>
          <div class="col-span-6 md:col-span-2">
            <label class="text-xs sm:text-sm font-medium text-gray-700">Weight</label>
            <input type="number" min="0.5" step="0.5" value="${data.weight || 1}" class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 weightInput" />
          </div>
          <div class="col-span-12 md:col-span-1 flex justify-end">
            <button type="button" title="Remove Subject" class="remove-btn w-full md:w-10 h-10 bg-red-600 text-white rounded-md hover:bg-red-700 transition-colors flex items-center justify-center font-bold no-print">
                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 6h18"/><path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6"/><path d="M8 6V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/></svg>
            </button>
          </div>
        `;
        subjectsArea.appendChild(row);
      }

      function calculateAndShowResults() {
        const subjectRows = document.querySelectorAll('.subject-row');
        if (subjectRows.length === 0) {
          showModal('Please add at least one subject to calculate.');
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
          const points = currentMap[grade] !== undefined ? currentMap[grade] : 0;
          
          totalWeight += weight;
          weightedSum += points * weight;

          detailLines.push({ subj: subjName, grade, weight, points });
        });

        if (totalWeight <= 0) {
          showModal('The total weight of subjects must be greater than zero.');
          return;
        }

        const avgPercent = weightedSum / totalWeight;
        const avgRounded = avgPercent.toFixed(2);

        calculationDetails.innerHTML = detailLines.map(d => `
          <div class="flex flex-wrap justify-between items-center border-b border-gray-200 dark:border-indigo-800 py-1">
            <span class="mr-2"><strong>${d.subj}</strong> (Grade: ${d.grade}, W: ${d.weight})</span>
            <span class="font-semibold text-indigo-700 dark:text-indigo-300">${d.points} Points</span>
          </div>
        `).join('') + `<div class="flex justify-between items-center pt-2 font-bold text-md"><span>Total Average:</span><span>${avgRounded}%</span></div>`;

        summaryPercent.textContent = `${avgRounded}%`;
        
        let suggestedEquivalence = '';
        const level = examType.value;
        if (level === 'o') {
            suggestedEquivalence = getEquivalenceMessage('Matric', avgRounded);
        } else if (level === 'a') {
            suggestedEquivalence = getEquivalenceMessage('Intermediate', avgRounded);
        } else {
            suggestedEquivalence = `A combined O+A Level calculation.`;
        }
        summaryAdvice.innerHTML = suggestedEquivalence;

        resultCard.classList.remove('hidden');
        resultCard.scrollIntoView({ behavior: 'smooth', block: 'start' });
        saveState();
      }

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

      function addDefaultSubjects() {
        const defaultSubjects = [
            { name: 'English Language', grade: 'A', weight: '1' },
            { name: 'Mathematics', grade: 'A', weight: '1' },
            { name: 'Pakistan Studies', grade: 'A', weight: '1' },
            { name: 'Islamiyat', grade: 'A', weight: '1' },
            { name: 'Urdu', grade: 'B', weight: '1' }
        ];
        defaultSubjects.forEach(addSubjectRow);
      }

      function resetForm() {
        subjectsArea.innerHTML = '';
        subjectCounter = 0;
        addDefaultSubjects();
        
        mappingPreset.value = 'default';
        examType.value = 'o';
        resultCard.classList.add('hidden');
        localStorage.removeItem('equivalenceCalculatorState');
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }

      function saveState() {
        const subjectRows = document.querySelectorAll('.subject-row');
        const subjectsData = Array.from(subjectRows).map(row => ({
            name: row.querySelector('.subjectName').value,
            grade: row.querySelector('.gradeSelect').value,
            weight: row.querySelector('.weightInput').value,
        }));
        
        const state = {
            subjects: subjectsData,
            examType: examType.value,
            mappingPreset: mappingPreset.value,
        };
        localStorage.setItem('equivalenceCalculatorState', JSON.stringify(state));
      }

      function loadState() {
        const savedState = localStorage.getItem('equivalenceCalculatorState');
        if (savedState) {
          const state = JSON.parse(savedState);
          examType.value = state.examType || 'o';
          mappingPreset.value = state.mappingPreset || 'default';
          subjectsArea.innerHTML = '';
          subjectCounter = 0;
          if (state.subjects && state.subjects.length > 0) {
            state.subjects.forEach(addSubjectRow);
          } else {
            addDefaultSubjects();
          }
        } else {
          addDefaultSubjects();
        }
      }

      function applyTheme(theme) {
          if (theme === 'dark') {
              htmlEl.classList.add('dark');
              moonIcon.classList.remove('hidden');
              sunIcon.classList.add('hidden');
          } else {
              htmlEl.classList.remove('dark');
              sunIcon.classList.remove('hidden');
              moonIcon.classList.add('hidden');
          }
      }

      // --- Event Listeners ---
      addSubjectBtn.addEventListener('click', () => { addSubjectRow(); saveState(); });
      subjectsArea.addEventListener('click', (e) => {
        const removeBtn = e.target.closest('.remove-btn');
        if (removeBtn) {
          if (subjectsArea.childElementCount > 1) {
            removeBtn.closest('.subject-row').remove();
            saveState();
          } else {
            showModal('At least one subject is required.');
          }
        }
      });
      examType.addEventListener('change', saveState);
      mappingPreset.addEventListener('change', saveState);
      subjectsArea.addEventListener('input', saveState);
      calcBtn.addEventListener('click', calculateAndShowResults);
      resetBtn.addEventListener('click', resetForm);
      printBtn.addEventListener('click', () => {
          document.getElementById('printDate').textContent = new Date().toLocaleString();
          window.print();
      });
      modalCloseBtn.addEventListener('click', hideModal);
      customModal.addEventListener('click', (e) => { if (e.target === customModal) hideModal(); });
      darkModeToggle.addEventListener('click', () => {
          const currentTheme = htmlEl.classList.contains('dark') ? 'light' : 'dark';
          localStorage.setItem('theme', currentTheme);
          applyTheme(currentTheme);
      });
      document.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' && !customModal.classList.contains('modal-hidden')) {
            hideModal();
        } else if (e.key === 'Enter' && document.activeElement.tagName !== 'TEXTAREA' && !document.activeElement.closest('.remove-btn')) {
          e.preventDefault();
          calcBtn.click();
        }
      });

      // --- Initialisation ---
      const savedTheme = localStorage.getItem('theme') || (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light');
      applyTheme(savedTheme);
      loadState();
    });
  </script>
</body>
</html>


