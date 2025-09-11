<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1" />
    <title>O/A Level Equivalence Calculator — AI Tool</title>

    <!-- Tailwind via CDN for quick styling -->
    <script src="https://cdn.tailwindcss.com"></script>

    <style>
        /* Use a professional and readable font */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap');
        
        body { 
            font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; 
            background-color: #f0f4f8; /* Softer, cooler background */
        }
        
        .glass { 
            background: rgba(255, 255, 255, 0.6); 
            backdrop-filter: blur(10px); 
            -webkit-backdrop-filter: blur(10px); 
            box-shadow: 0 10px 40px 0 rgba(4, 30, 66, 0.15);
            border-radius: 1.5rem; 
            border: 1px solid rgba(255, 255, 255, 0.4);
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }

        .glass:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 50px 0 rgba(4, 30, 66, 0.2);
        }

        /* Subtle focus styles */
        input:focus, select:focus {
            outline: none;
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.5); /* blue-500 with opacity */
        }
        
        .fade-in { animation: fadeIn 0.5s ease-out both; }
        .slide-down { animation: slideDown 0.4s ease-out both; }
        .toast { animation: toast-in 0.5s ease-out forwards; }
        .toast-out { animation: toast-out 0.5s ease-in forwards; }

        @keyframes fadeIn { 
            from { opacity: 0; transform: translateY(10px); } 
            to { opacity: 1; transform: translateY(0); } 
        }
        @keyframes slideDown { 
            from { opacity: 0; transform: translateY(-10px); } 
            to { opacity: 1; transform: translateY(0); } 
        }
        @keyframes toast-in { 
            from { transform: translateX(-100%); opacity: 0; } 
            to { transform: translateX(0); opacity: 1; }
        }
        @keyframes toast-out {
            from { transform: translateX(0); opacity: 1; }
            to { transform: translateX(-100%); opacity: 0; }
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
<body class="min-h-screen flex items-center justify-center p-4 md:p-6 bg-slate-50 text-gray-800">

    <main class="w-full max-w-4xl mx-auto space-y-8">
        <header class="flex items-center gap-4 fade-in">
            <img src="https://i.postimg.cc/0Qkg3P4h/output-onlinepngtools-4.png" alt="IBA Grads Logo" class="h-16 no-print" />
            <div class="flex-grow">
                <h1 class="text-3xl md:text-4xl font-extrabold text-blue-900">O/A Level Equivalence Calculator</h1>
                <p class="mt-2 text-md text-blue-700">Enter your grades below to instantly estimate your Pakistani equivalence.</p>
            </div>
        </header>

        <section class="glass p-6 md:p-10 fade-in" style="animation-delay: 0.1s;">
            <form id="calcForm" class="space-y-6">
                <!-- Main settings row -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 border-b pb-6">
                    <div>
                        <label for="examType" class="block mb-2 text-blue-900">Select Exam Type</label>
                        <select id="examType" class="w-full rounded-lg border-gray-300 px-3 py-2 shadow-sm focus:border-blue-500 focus:ring-blue-500">
                            <option value="o">O Level / IGCSE</option>
                            <option value="a">A Level</option>
                            <option value="both">Both O + A Levels</option>
                        </select>
                    </div>
                    <div>
                        <label for="mappingPreset" class="block mb-2 text-blue-900">Grade Mapping</label>
                        <select id="mappingPreset" class="w-full rounded-lg border-gray-300 px-3 py-2 shadow-sm focus:border-blue-500 focus:ring-blue-500">
                            <option value="default">Default (A*=90, A=85, B=75...)</option>
                            <option value="higher">Higher A* (A*=95, A=90...)</option>
                        </select>
                    </div>
                </div>

                <!-- Dynamic Subjects Area -->
                <div class="space-y-2">
                    <h3 class="text-lg font-bold text-blue-800">Subjects</h3>
                    <div id="subjectsArea" class="space-y-3">
                        <!-- dynamic subject rows will appear here -->
                    </div>
                </div>

                <!-- Action Buttons for Subjects and Calculation -->
                <div class="flex flex-wrap gap-3 items-center pt-4 border-t mt-6">
                    <button id="addSubjectBtn" type="button" class="px-4 py-2 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition-colors no-print flex items-center gap-2">
                        <!-- SVG for Add icon -->
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                          <path fill-rule="evenodd" d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z" clip-rule="evenodd" />
                        </svg>
                        Add Subject
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
                <h2 class="text-2xl font-bold text-blue-900">Your Estimated Result</h2>
                <button id="printBtn" class="px-4 py-2 bg-blue-600 hover:bg-blue-700 text-white rounded-lg no-print">
                    Print
                </button>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-5 gap-6">
                <!-- Summary on the left -->
                <div class="md:col-span-2 p-6 bg-blue-700 text-white rounded-lg flex flex-col items-center justify-center text-center">
                    <h3 class="text-lg font-semibold opacity-80">Overall Percentage</h3>
                    <div id="summaryPercent" class="text-5xl font-extrabold my-2">0%</div>
                    <div id="summaryAdvice" class="mt-2 opacity-90"></div>
                </div>

                <!-- Details on the right -->
                <div class="md:col-span-3 p-6 bg-white/80 rounded-lg">
                    <h3 class="font-bold mb-3 text-blue-900">Details</h3>
                    <div id="calculationDetails" class="text-sm text-gray-700 space-y-2"></div>
                </div>
            </div>
        </section>

        <!-- Custom Message Box -->
        <div id="messageBox" class="fixed top-4 left-4 z-50 p-4 bg-red-500 text-white rounded-lg shadow-lg flex items-center gap-3 hidden transition-transform duration-300 ease-out toast">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4m0 4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
          <span id="messageText"></span>
        </div>

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
            const messageBox = document.getElementById('messageBox');
            const messageText = document.getElementById('messageText');

            // --- Data and State ---
            const gradeOptions = ["A*", "A", "B", "C", "D", "E", "U"];
            const mappings = {
                default: { "A*": 90, "A": 85, "B": 75, "C": 65, "D": 55, "E": 45, "U": 0 },
                higher:  { "A*": 95, "A": 90, "B": 80, "C": 70, "D": 60, "E": 50, "U": 0 }
            };

            // --- Functions ---

            /**
             * Shows a custom message box instead of using alert().
             * @param {string} message - The message to display.
             */
            function showMessage(message) {
                messageText.textContent = message;
                messageBox.classList.remove('hidden', 'toast-out');
                messageBox.classList.add('toast');
                
                setTimeout(() => {
                    messageBox.classList.remove('toast');
                    messageBox.classList.add('toast-out');
                }, 3000);
            }

            /**
             * Adds a new subject input row to the form.
             */
            function addSubjectRow() {
                const row = document.createElement('div');
                row.className = 'grid grid-cols-1 md:grid-cols-12 gap-4 items-end subject-row fade-in';
                row.innerHTML = `
                    <div class="md:col-span-4">
                        <label class="text-sm font-medium text-gray-700">Subject</label>
                        <input type="text" placeholder="e.g., Mathematics" class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 subjectName" />
                    </div>
                    <div class="md:col-span-2">
                        <label class="text-sm font-medium text-gray-700">Grade</label>
                        <select class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 gradeSelect">
                            ${gradeOptions.map(g => `<option value="${g}">${g}</option>`).join('')}
                        </select>
                    </div>
                    <div class="md:col-span-2">
                        <label class="text-sm font-medium text-gray-700">Weight</label>
                        <input type="number" min="0.5" step="0.5" value="1" class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 weightInput" />
                    </div>
                    <div class="md:col-span-3">
                        <label class="text-sm font-medium text-gray-700">Notes</label>
                        <input type="text" placeholder="Optional" class="mt-1 w-full rounded-md border-gray-300 px-3 py-2 noteInput" />
                    </div>
                    <div class="md:col-span-1">
                        <button type="button" title="Remove Subject" class="remove-btn w-full h-10 bg-red-500 text-white rounded-lg hover:bg-red-600 transition-colors flex items-center justify-center font-bold text-xl no-print">
                            <!-- SVG for Remove icon -->
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                            </svg>
                        </button>
                    </div>
                `;
                subjectsArea.appendChild(row);
                // Renumber subjects after adding a new one
                renumberSubjects();
            }

            /**
             * Renumbers the subject labels dynamically.
             */
            function renumberSubjects() {
                const subjectRows = subjectsArea.querySelectorAll('.subject-row');
                subjectRows.forEach((row, index) => {
                    const label = row.querySelector('label');
                    if (label) {
                        label.textContent = `Subject ${index + 1}`;
                    }
                });
            }

            /**
             * Hides the result card.
             */
            function clearResults() {
                resultCard.classList.add('hidden');
                calculationDetails.innerHTML = '';
                summaryPercent.textContent = '0%';
                summaryAdvice.innerHTML = '';
            }

            /**
             * Handles calculation logic and displays the results.
             */
            function calculateAndShowResults() {
                const subjectRows = document.querySelectorAll('.subject-row');
                if (subjectRows.length === 0) {
                    showMessage('Please add at least one subject to calculate.');
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
                    showMessage('The total weight of subjects must be greater than zero.');
                    return;
                }

                const avgPercent = weightedSum / totalWeight;
                const avgRounded = Math.round((avgPercent + Number.EPSILON) * 100) / 100;

                // Render details
                calculationDetails.innerHTML = detailLines.map(d => `
                    <div class="flex justify-between items-center border-b border-gray-200 py-1">
                        <span><strong>${d.subj}</strong> (Grade: ${d.grade}, Weight: ${d.weight})</span>
                        <span class="font-semibold text-blue-700">${d.points} Points</span>
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
                    // For "Both O + A Levels"
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
                addSubjectRow(); // Start with a single subject row
                
                mappingPreset.value = 'default';
                examType.value = 'o';
                clearResults();
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }

            // --- Event Listeners ---
            addSubjectBtn.addEventListener('click', addSubjectRow);

            subjectsArea.addEventListener('click', (e) => {
                const removeBtn = e.target.closest('.remove-btn');
                if (removeBtn) {
                    if (subjectsArea.childElementCount > 1) {
                        removeBtn.closest('.subject-row').remove();
                        renumberSubjects();
                        clearResults();
                    } else {
                        showMessage('At least one subject is required.');
                    }
                }
            });
            
            // Listen for changes in form inputs to clear the results
            document.getElementById('calcForm').addEventListener('input', (e) => {
                if (e.target.id !== 'calcBtn' && e.target.id !== 'printBtn') {
                    clearResults();
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
