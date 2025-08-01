<html lang="en" class="scroll-smooth" >
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no" />
  <title>PCA - RXII BURS MONITORING (EYEM) - Login / Sign Up</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap"
    rel="stylesheet"
  />
  <style>
    html, body {
      height: 100%;
      margin: 0;
      padding: 0;
      background: #f9faf5; /* very light greenish */
      font-family: 'Inter', sans-serif;
      color: #3f6212; /* dark olive green */
    }
    /* Container for login/signup */
    #authContainer {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(90deg, #a3b82c 0%, #facc15 100%);
      padding: 1rem;
      box-sizing: border-box;
    }
    #authBox {
      background: white;
      border-radius: 1.5rem;
      padding: 2.5rem 3rem;
      box-shadow: 0 8px 24px rgba(163, 184, 44, 0.6);
      width: 100%;
      max-width: 400px;
      box-sizing: border-box;
      user-select: none;
    }
    #authBox h2 {
      font-weight: 700;
      font-size: 1.8rem;
      color: #3f6212;
      margin-bottom: 1.5rem;
      text-align: center;
      text-shadow: 0 0 6px rgba(250, 204, 21, 0.8);
    }
    label {
      font-weight: 600;
      font-size: 0.9rem;
      color: #4b6a0a;
      display: block;
      margin-bottom: 0.3rem;
      user-select: text;
    }
    input[type="text"], input[type="password"], input[type="date"], input[type="time"], select, textarea {
      width: 100%;
      padding: 0.75rem 1rem;
      border-radius: 12px;
      border: 1.5px solid #a3b82c;
      background-color: #f9faf5;
      color: #3f6212;
      font-weight: 600;
      font-size: 1rem;
      box-shadow: 0 1px 3px rgba(101, 123, 13, 0.15);
      transition: background-color 0.3s ease, box-shadow 0.3s ease;
      margin-bottom: 1.25rem;
      box-sizing: border-box;
      resize: vertical;
    }
    input[type="text"]:focus, input[type="password"]:focus, input[type="date"]:focus, input[type="time"]:focus, select:focus, textarea:focus {
      outline: none;
      border-color: #7c9a0a;
      box-shadow: 0 0 8px 2px #cddc39;
      background-color: #f9faf5;
      color: #2f4d0a;
    }
    button.authBtn {
      width: 100%;
      padding: 0.9rem 0;
      border-radius: 12px;
      border: none;
      background-color: #7c9a0a;
      color: #fefce8;
      font-weight: 700;
      font-size: 1.1rem;
      box-shadow: 0 6px 14px rgba(124, 154, 10, 0.7);
      cursor: pointer;
      transition: background-color 0.3s ease, box-shadow 0.3s ease;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 0.5rem;
      user-select: none;
      margin-bottom: 1rem;
    }
    button.authBtn:hover {
      background-color: #556b00;
      box-shadow: 0 8px 20px rgba(85, 107, 0, 0.9);
    }
    .error-message {
      color: #b91c1c;
      font-weight: 600;
      font-size: 0.9rem;
      margin-bottom: 1rem;
      text-align: center;
      user-select: none;
    }
    .toggle-link {
      text-align: center;
      color: #4b6a0a;
      font-weight: 600;
      cursor: pointer;
      user-select: none;
      text-decoration: underline;
      margin-top: 0.5rem;
    }
    .toggle-link:hover {
      color: #7c9a0a;
    }
  </style>
</head>
<body>
  <div id="authContainer" aria-label="Authentication screen">
    <div id="authBox" role="form" aria-live="polite">
      <h2 id="authTitle">PCA - RXII BURS MONITORING (EYEM) - Log In</h2>
      <form id="loginForm" autocomplete="off" novalidate>
        <div id="loginFields">
          <label for="usernameInput">Username</label>
          <input type="text" id="usernameInput" name="username" autocomplete="username" required aria-required="true" aria-label="Username" tabindex="1" />
          <label for="passwordInput">Password</label>
          <input type="password" id="passwordInput" name="password" autocomplete="current-password" required aria-required="true" aria-label="Password" tabindex="2" />
        </div>
        <div id="signupFields" style="display:none;">
          <label for="signupUsernameInput">Username</label>
          <input type="text" id="signupUsernameInput" name="signupUsername" autocomplete="username" aria-label="Username" tabindex="1" />
          <label for="signupPasswordInput">Password</label>
          <input type="password" id="signupPasswordInput" name="signupPassword" autocomplete="new-password" aria-label="Password" tabindex="2" />
          <label for="signupConfirmPasswordInput">Confirm Password</label>
          <input type="password" id="signupConfirmPasswordInput" name="signupConfirmPassword" autocomplete="new-password" aria-label="Confirm Password" tabindex="3" />
        </div>
        <div id="errorMessage" class="error-message" role="alert" aria-live="assertive" style="display:none;"></div>
        <button type="submit" id="authBtn" class="authBtn" tabindex="3"><i class="fas fa-sign-in-alt"></i> Log In</button>
      </form>
      <div id="toggleAuth" class="toggle-link" tabindex="4" role="button" aria-pressed="false">Don't have an account? Sign Up</div>
    </div>
  </div>

  <div id="appContainer" style="display:none;">
    <header class="bg-lime-600 text-white p-4 shadow-md select-none flex items-center justify-center relative">
      <h1 class="text-xl md:text-2xl font-extrabold text-center max-w-[90%]">PCA - RXII BURS MONITORING (EYEM)</h1>
      <button id="logoutBtn" class="absolute right-4 top-1/2 -translate-y-1/2 bg-yellow-400 hover:bg-yellow-500 text-yellow-900 font-extrabold rounded-3xl px-4 md:px-6 py-2 md:py-3 shadow-lg transition focus:outline-none focus:ring-4 focus:ring-yellow-400 flex items-center gap-2 md:gap-3 text-sm md:text-base" tabindex="1" aria-label="Log out">
        <i class="fas fa-sign-out-alt"></i> Log Out
      </button>
    </header>

    <main class="flex flex-1 flex-col md:flex-row p-4 md:p-6 gap-6 max-w-full mx-auto w-full overflow-x-hidden" style="height: calc(100vh - 64px);">
      <!-- Left Panel -->
      <section class="md:w-1/3 bg-white rounded-3xl shadow-lg p-4 md:p-6 flex flex-col overflow-y-auto" style="max-height: 100%;">
        <!-- Summary clickable boxes -->
        <div class="flex justify-start mb-6 space-x-4 md:space-x-6 flex-shrink-0">
          <button id="btnIncoming" class="flex-1 bg-lime-100 hover:bg-lime-200 rounded-xl p-4 focus:outline-none focus:ring-4 focus:ring-lime-400 ring-offset-2 ring-offset-white transition" aria-pressed="false" aria-label="Show Incoming Documents Summary" tabindex="2">
            <div class="text-center">
              <div class="text-4xl md:text-5xl font-extrabold" id="countIncoming">0</div>
              <div class="mt-1 md:mt-2 text-base md:text-lg tracking-wide font-semibold text-lime-700">Incoming Docs</div>
            </div>
          </button>
          <button id="btnOpen" class="flex-1 bg-yellow-100 hover:bg-yellow-200 rounded-xl p-4 focus:outline-none focus:ring-4 focus:ring-yellow-400 ring-offset-2 ring-offset-white transition" aria-pressed="false" aria-label="Show Currently Open Documents Summary" tabindex="3">
            <div class="text-center">
              <div class="text-4xl md:text-5xl font-extrabold" id="countOpen">0</div>
              <div class="mt-1 md:mt-2 text-base md:text-lg tracking-wide font-semibold text-yellow-700">Currently Open</div>
            </div>
          </button>
        </div>

        <!-- Form -->
        <form id="docForm" class="flex flex-col space-y-3 md:space-y-4 flex-shrink-0" autocomplete="off" novalidate>
          <div>
            <label for="dateReceived" class="block text-green-800 font-semibold mb-1 text-sm md:text-base">Date Received</label>
            <input type="date" id="dateReceived" name="dateReceived" required class="w-full rounded border border-lime-400 px-3 md:px-4 py-2 md:py-3 focus:outline-none focus:ring-4 focus:ring-lime-300 text-green-900 font-semibold text-sm md:text-base" tabindex="4" />
          </div>

          <div>
            <label for="payee" class="block text-green-800 font-semibold mb-1 text-sm md:text-base">Payee</label>
            <input type="text" id="payee" name="payee" placeholder="Enter payee" required class="w-full rounded border border-lime-400 px-3 md:px-4 py-2 md:py-3 focus:outline-none focus:ring-4 focus:ring-lime-300 text-green-900 font-semibold text-sm md:text-base" tabindex="5" />
          </div>

          <div>
            <label for="description" class="block text-green-800 font-semibold mb-1 text-sm md:text-base">Description</label>
            <textarea id="description" name="description" rows="3" placeholder="Enter description" required class="w-full rounded border border-lime-400 px-3 md:px-4 py-2 md:py-3 resize-y focus:outline-none focus:ring-4 focus:ring-lime-300 text-green-900 font-semibold text-sm md:text-base" tabindex="6"></textarea>
          </div>

          <div>
            <label for="bursNo" class="block text-green-800 font-semibold mb-1 text-sm md:text-base">BURS No.</label>
            <input type="text" id="bursNo" name="bursNo" placeholder="Enter BURS number" required class="w-full rounded border border-lime-400 px-3 md:px-4 py-2 md:py-3 focus:outline-none focus:ring-4 focus:ring-lime-300 text-green-900 font-semibold text-sm md:text-base" tabindex="7" />
          </div>

          <div>
            <label for="grossAmount" class="block text-green-800 font-semibold mb-1 text-sm md:text-base">Gross Amount</label>
            <input type="number" id="grossAmount" name="grossAmount" min="0" step="0.01" placeholder="Enter gross amount" required class="w-full rounded border border-lime-400 px-3 md:px-4 py-2 md:py-3 focus:outline-none focus:ring-4 focus:ring-lime-300 text-green-900 font-semibold text-sm md:text-base" tabindex="8" />
          </div>

          <div class="flex flex-col sm:flex-row sm:items-center sm:space-x-6">
            <label class="inline-flex items-center space-x-3 mb-3 sm:mb-0">
              <input type="checkbox" id="withSaobd" name="withSaobd" class="form-checkbox h-5 w-5 text-lime-500" tabindex="9" />
              <span class="text-green-800 font-semibold text-sm md:text-base">With SAOBD</span>
            </label>

            <label for="fundDisbursed" class="text-green-800 font-semibold text-sm md:text-base mb-1 sm:mb-0">Fund Disbursed</label>
            <select id="fundDisbursed" name="fundDisbursed" required class="rounded border border-lime-400 px-3 md:px-4 py-2 md:py-3 focus:outline-none focus:ring-4 focus:ring-lime-300 text-green-900 font-semibold text-sm md:text-base" tabindex="10">
              <option value="" disabled selected>Select fund disbursed</option>
              <option value="NG">NG</option>
              <option value="CFITF">CFITF</option>
              <option value="CF">CF</option>
            </select>
          </div>

          <div>
            <label for="fundSaobd" class="block text-green-800 font-semibold mb-1 text-sm md:text-base">Fund SAOBD</label>
            <select id="fundSaobd" name="fundSaobd" class="w-full rounded border border-lime-400 px-3 md:px-4 py-2 md:py-3 focus:outline-none focus:ring-4 focus:ring-lime-300 text-green-900 font-semibold text-sm md:text-base" tabindex="11">
              <option value="" selected>None</option>
              <option value="NG">NG</option>
              <option value="CFITF">CFITF</option>
              <option value="CF">CF</option>
            </select>
          </div>

          <div>
            <label for="remarks" class="block text-green-800 font-semibold mb-1 text-sm md:text-base">Remarks</label>
            <textarea id="remarks" name="remarks" rows="3" placeholder="Enter remarks" class="w-full rounded border border-lime-400 px-3 md:px-4 py-2 md:py-3 resize-y focus:outline-none focus:ring-4 focus:ring-lime-300 text-green-900 font-semibold text-sm md:text-base" tabindex="12"></textarea>
          </div>

          <div class="flex space-x-4">
            <button type="submit" id="saveBtn" class="flex-1 py-3 shadow-md transition focus:outline-none focus:ring-4 focus:ring-lime-400 flex items-center justify-center gap-3 text-white text-sm md:text-base font-semibold bg-lime-600 rounded-lg" tabindex="13">
              <i class="fas fa-save"></i> Save
            </button>
            <button type="button" id="deleteBtn" class="flex-1 py-3 shadow-md transition focus:outline-none focus:ring-4 focus:ring-yellow-400 flex items-center justify-center gap-3 text-yellow-900 text-sm md:text-base font-semibold bg-yellow-300 rounded-lg opacity-50 cursor-not-allowed" disabled tabindex="14">
              <i class="fas fa-trash-alt"></i> Delete
            </button>
          </div>
        </form>
      </section>

      <!-- Right Panel -->
      <section class="flex-1 flex flex-col bg-white rounded-3xl shadow-lg p-4 md:p-6 overflow-x-auto" style="height: 100vh; overflow-y: auto;">
        <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between mb-6 gap-4">
          <h2 class="text-2xl md:text-3xl font-extrabold text-lime-700 select-none drop-shadow-md">Documents Summary</h2>
          <div class="flex flex-wrap gap-3 w-full sm:w-auto">
            <input
              type="text"
              id="searchInput"
              placeholder="Search documents..."
              aria-label="Search documents"
              class="rounded-3xl border border-lime-400 px-4 md:px-5 py-2 md:py-3 focus:outline-none focus:ring-4 focus:ring-lime-300 text-lime-900 font-semibold w-full sm:w-72 text-sm md:text-base"
              tabindex="15"
            />
            <button id="searchBtn" class="bg-lime-600 hover:bg-lime-700 text-white font-extrabold rounded-3xl px-4 md:px-6 py-2 md:py-3 shadow-lg transition focus:outline-none focus:ring-4 focus:ring-lime-400 flex items-center gap-2 md:gap-3 text-sm md:text-base" tabindex="16">
              <i class="fas fa-search"></i> Search
            </button>
            <button id="clearBtn" class="bg-yellow-300 hover:bg-yellow-400 text-yellow-900 font-extrabold rounded-3xl px-4 md:px-6 py-2 md:py-3 shadow-lg transition focus:outline-none focus:ring-4 focus:ring-yellow-300 flex items-center gap-2 md:gap-3 text-sm md:text-base" tabindex="17">
              <i class="fas fa-eraser"></i> Clear
            </button>
            <button id="addBtn" class="bg-lime-600 hover:bg-lime-700 text-white font-extrabold rounded-3xl px-4 md:px-6 py-2 md:py-3 shadow-lg transition focus:outline-none focus:ring-4 focus:ring-lime-400 flex items-center gap-2 md:gap-3 text-sm md:text-base" tabindex="18">
              <i class="fas fa-plus"></i> Add
            </button>
            <button id="exportBtn" class="bg-yellow-400 hover:bg-yellow-500 text-yellow-900 font-extrabold rounded-3xl px-4 md:px-6 py-2 md:py-3 shadow-lg transition focus:outline-none focus:ring-4 focus:ring-yellow-400 flex items-center gap-2 md:gap-3 text-sm md:text-base" tabindex="19">
              <i class="fas fa-file-export"></i> Export
            </button>
          </div>
        </div>

        <div class="overflow-x-auto rounded-3xl border border-lime-400">
          <table class="min-w-full divide-y divide-lime-400" aria-label="Documents table" id="docsTable">
            <thead class="bg-lime-300 sticky top-0 z-10 rounded-t-3xl">
              <tr>
                <th scope="col" class="px-3 md:px-5 py-3 text-left text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none rounded-tl-3xl">
                  Date<br />
                  <input type="date" id="filterDate" class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by Date" tabindex="20" />
                </th>
                <th scope="col" class="px-3 md:px-5 py-3 text-left text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none">
                  Time<br />
                  <input type="time" id="filterTime" class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by Time" tabindex="21" />
                </th>
                <th scope="col" class="px-3 md:px-5 py-3 text-left text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none">
                  Payee<br />
                  <input type="text" id="filterPayee" placeholder="Filter Payee" class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by Payee" tabindex="22" />
                </th>
                <th scope="col" class="px-3 md:px-5 py-3 text-left text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none">
                  Description<br />
                  <input type="text" id="filterDescription" placeholder="Filter Description" class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by Description" tabindex="23" />
                </th>
                <th scope="col" class="px-3 md:px-5 py-3 text-left text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none">
                  BURS No.<br />
                  <input type="text" id="filterBursNo" placeholder="Filter BURS No." class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by BURS No." tabindex="24" />
                </th>
                <th scope="col" class="px-3 md:px-5 py-3 text-right text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none">
                  Gross Amount<br />
                  <input type="number" id="filterGrossAmount" min="0" step="0.01" placeholder="Filter Amount" class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm text-right focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by Gross Amount" tabindex="25" />
                </th>
                <th scope="col" class="px-3 md:px-5 py-3 text-left text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none">
                  Fund Disbursed<br />
                  <select id="filterFundDisbursed" class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by Fund Disbursed" tabindex="26">
                    <option value="">All</option>
                    <option value="NG">NG</option>
                    <option value="CFITF">CFITF</option>
                    <option value="CF">CF</option>
                  </select>
                </th>
                <th scope="col" class="px-3 md:px-5 py-3 text-left text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none">
                  Fund SAOBD<br />
                  <select id="filterFundSaobd" class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by Fund SAOBD" tabindex="27">
                    <option value="">All</option>
                    <option value="NG">NG</option>
                    <option value="CFITF">CFITF</option>
                    <option value="CF">CF</option>
                  </select>
                </th>
                <th scope="col" class="px-3 md:px-5 py-3 text-left text-xs md:text-sm font-extrabold text-lime-800 uppercase tracking-wider select-none rounded-tr-3xl">
                  Remarks<br />
                  <input type="text" id="filterRemarks" placeholder="Filter Remarks" class="mt-1 w-full rounded-xl border border-lime-400 px-2 md:px-3 py-1 md:py-2 text-xs md:text-sm focus:outline-none focus:ring-4 focus:ring-lime-300" aria-label="Filter by Remarks" tabindex="28" />
                </th>
              </tr>
            </thead>
            <tbody id="docsTableBody" class="divide-y divide-lime-400 max-h-[calc(100vh-220px)] overflow-y-auto scrollbar-thin">
            </tbody>
          </table>
        </div>
      </section>
    </main>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/xlsx@0.18.5/dist/xlsx.full.min.js"></script>
  <script>
    // Format Philippine Peso with commas and 2 decimals
    function formatPeso(amount) {
      return '₱ ' + amount.toLocaleString('en-PH', {minimumFractionDigits: 2, maximumFractionDigits: 2});
    }
    function formatDate(date) {
      const d = new Date(date);
      const month = (d.getMonth() + 1).toString().padStart(2, '0');
      const day = d.getDate().toString().padStart(2, '0');
      const year = d.getFullYear();
      return `${year}-${month}-${day}`;
    }
    function formatTime(date) {
      const d = new Date(date);
      const h = d.getHours().toString().padStart(2, '0');
      const m = d.getMinutes().toString().padStart(2, '0');
      const s = d.getSeconds().toString().padStart(2, '0');
      return `${h}:${m}:${s}`;
    }

    const STORAGE_KEY = 'pca_rxii_burs_docs';
    const USERS_KEY = 'pca_rxii_burs_users';
    let documents = [];
    let currentFilter = null;
    let selectedDocIndex = null;

    // Auth elements
    const authContainer = document.getElementById('authContainer');
    const authBox = document.getElementById('authBox');
    const authTitle = document.getElementById('authTitle');
    const loginForm = document.getElementById('loginForm');
    const loginFields = document.getElementById('loginFields');
    const signupFields = document.getElementById('signupFields');
    const authBtn = document.getElementById('authBtn');
    const toggleAuth = document.getElementById('toggleAuth');
    const errorMessage = document.getElementById('errorMessage');
    const usernameInput = document.getElementById('usernameInput');
    const passwordInput = document.getElementById('passwordInput');
    const signupUsernameInput = document.getElementById('signupUsernameInput');
    const signupPasswordInput = document.getElementById('signupPasswordInput');
    const signupConfirmPasswordInput = document.getElementById('signupConfirmPasswordInput');

    // App container
    const appContainer = document.getElementById('appContainer');

    // App elements
    const countIncomingEl = document.getElementById('countIncoming');
    const countOpenEl = document.getElementById('countOpen');
    const btnIncoming = document.getElementById('btnIncoming');
    const btnOpen = document.getElementById('btnOpen');
    const docForm = document.getElementById('docForm');
    const saveBtn = document.getElementById('saveBtn');
    const deleteBtn = document.getElementById('deleteBtn');
    const docsTableBody = document.getElementById('docsTableBody');
    const searchInput = document.getElementById('searchInput');
    const searchBtn = document.getElementById('searchBtn');
    const clearBtn = document.getElementById('clearBtn');
    const addBtn = document.getElementById('addBtn');
    const exportBtn = document.getElementById('exportBtn');
    const filterDate = document.getElementById('filterDate');
    const filterTime = document.getElementById('filterTime');
    const filterPayee = document.getElementById('filterPayee');
    const filterDescription = document.getElementById('filterDescription');
    const filterBursNo = document.getElementById('filterBursNo');
    const filterGrossAmount = document.getElementById('filterGrossAmount');
    const filterFundDisbursed = document.getElementById('filterFundDisbursed');
    const filterFundSaobd = document.getElementById('filterFundSaobd');
    const filterRemarks = document.getElementById('filterRemarks');
    const dateReceivedInput = document.getElementById('dateReceived');
    const payeeInput = document.getElementById('payee');
    const descriptionInput = document.getElementById('description');
    const bursNoInput = document.getElementById('bursNo');
    const grossAmountInput = document.getElementById('grossAmount');
    const withSaobdInput = document.getElementById('withSaobd');
    const fundDisbursedInput = document.getElementById('fundDisbursed');
    const fundSaobdInput = document.getElementById('fundSaobd');
    const remarksInput = document.getElementById('remarks');
    const logoutBtn = document.getElementById('logoutBtn');

    let isLoginMode = true;

    // Load users from localStorage or initialize empty array
    function loadUsers() {
      const stored = localStorage.getItem(USERS_KEY);
      if (stored) {
        try {
          return JSON.parse(stored);
        } catch {
          return [];
        }
      }
      return [];
    }
    // Save users to localStorage
    function saveUsers(users) {
      localStorage.setItem(USERS_KEY, JSON.stringify(users));
    }

    // Toggle between login and signup forms
    toggleAuth.addEventListener('click', () => {
      errorMessage.style.display = 'none';
      if (isLoginMode) {
        // Switch to Sign Up
        isLoginMode = false;
        authTitle.textContent = 'PCA - RXII BURS MONITORING (EYEM) - Sign Up';
        loginFields.style.display = 'none';
        signupFields.style.display = 'block';
        authBtn.innerHTML = '<i class="fas fa-user-plus"></i> Sign Up';
        toggleAuth.textContent = 'Already have an account? Log In';
        toggleAuth.setAttribute('aria-pressed', 'true');
        // Set tabindex for signup inputs
        signupUsernameInput.tabIndex = 1;
        signupPasswordInput.tabIndex = 2;
        signupConfirmPasswordInput.tabIndex = 3;
        authBtn.tabIndex = 4;
        usernameInput.tabIndex = -1;
        passwordInput.tabIndex = -1;
      } else {
        // Switch to Log In
        isLoginMode = true;
        authTitle.textContent = 'PCA - RXII BURS MONITORING (EYEM) - Log In';
        loginFields.style.display = 'block';
        signupFields.style.display = 'none';
        authBtn.innerHTML = '<i class="fas fa-sign-in-alt"></i> Log In';
        toggleAuth.textContent = "Don't have an account? Sign Up";
        toggleAuth.setAttribute('aria-pressed', 'false');
        // Set tabindex for login inputs
        usernameInput.tabIndex = 1;
        passwordInput.tabIndex = 2;
        authBtn.tabIndex = 3;
        signupUsernameInput.tabIndex = -1;
        signupPasswordInput.tabIndex = -1;
        signupConfirmPasswordInput.tabIndex = -1;
      }
      // Clear inputs and error
      loginForm.reset();
      errorMessage.style.display = 'none';
      if (isLoginMode) {
        usernameInput.focus();
      } else {
        signupUsernameInput.focus();
      }
    });

    loginForm.addEventListener('submit', e => {
      e.preventDefault();
      errorMessage.style.display = 'none';
      if (isLoginMode) {
        // Login flow
        const username = usernameInput.value.trim();
        const password = passwordInput.value;
        if (!username || !password) {
          showError('Please enter both username and password.');
          return;
        }
        const users = loadUsers();
        const user = users.find(u => u.username.toLowerCase() === username.toLowerCase());
        if (!user) {
          showError('User not found. Please sign up.');
          return;
        }
        if (user.password !== password) {
          showError('Incorrect password.');
          return;
        }
        // Successful login
        loginSuccess();
      } else {
        // Sign up flow
        const username = signupUsernameInput.value.trim();
        const password = signupPasswordInput.value;
        const confirmPassword = signupConfirmPasswordInput.value;
        if (!username || !password || !confirmPassword) {
          showError('Please fill in all fields.');
          return;
        }
        if (password !== confirmPassword) {
          showError('Passwords do not match.');
          return;
        }
        const users = loadUsers();
        if (users.some(u => u.username.toLowerCase() === username.toLowerCase())) {
          showError('Username already exists. Please choose another.');
          return;
        }
        // Save new user
        users.push({ username, password });
        saveUsers(users);
        alert('Sign up successful! You can now log in.');
        // Switch to login mode
        toggleAuth.click();
      }
    });

    function showError(msg) {
      errorMessage.textContent = msg;
      errorMessage.style.display = 'block';
    }

    function loginSuccess() {
      authContainer.style.display = 'none';
      appContainer.style.display = 'block';
      init();
    }

    logoutBtn.addEventListener('click', () => {
      // Clear any sensitive data if needed
      clearForm();
      documents = [];
      selectedDocIndex = null;
      currentFilter = null;
      // Show login container, hide app container
      authContainer.style.display = 'flex';
      appContainer.style.display = 'none';
      // Reset login form and focus username
      loginForm.reset();
      errorMessage.style.display = 'none';
      isLoginMode = true;
      authTitle.textContent = 'PCA - RXII BURS MONITORING (EYEM) - Log In';
      loginFields.style.display = 'block';
      signupFields.style.display = 'none';
      authBtn.innerHTML = '<i class="fas fa-sign-in-alt"></i> Log In';
      toggleAuth.textContent = "Don't have an account? Sign Up";
      toggleAuth.setAttribute('aria-pressed', 'false');
      usernameInput.tabIndex = 1;
      passwordInput.tabIndex = 2;
      authBtn.tabIndex = 3;
      signupUsernameInput.tabIndex = -1;
      signupPasswordInput.tabIndex = -1;
      signupConfirmPasswordInput.tabIndex = -1;
      usernameInput.focus();
    });

    function init() {
      loadDocuments();
      updateSummaryCounts();
      renderTable();
      attachEventListeners();
      updateDeleteButtonState();
    }
    function loadDocuments() {
      const stored = localStorage.getItem(STORAGE_KEY);
      if (stored) {
        try {
          documents = JSON.parse(stored);
          documents.forEach(doc => {
            doc.dateReceived = new Date(doc.dateReceived);
            doc.createdAt = new Date(doc.createdAt);
            if(doc.lastQrScan) doc.lastQrScan = new Date(doc.lastQrScan);
          });
        } catch {
          documents = [];
        }
      }
    }
    function saveDocuments() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(documents));
    }
    function updateSummaryCounts() {
      const incomingCount = documents.filter(d => d.type === 'incoming').length;
      const openCount = documents.filter(d => d.status === 'open').length;
      countIncomingEl.textContent = incomingCount;
      countOpenEl.textContent = openCount;
    }
    function renderTable() {
      const searchTerm = searchInput.value.trim().toLowerCase();
      let filteredDocs = documents;
      if (currentFilter === 'incoming') {
        filteredDocs = filteredDocs.filter(d => d.type === 'incoming');
      } else if (currentFilter === 'open') {
        filteredDocs = filteredDocs.filter(d => d.status === 'open');
      }
      if (searchTerm) {
        filteredDocs = filteredDocs.filter(d => {
          return (
            d.payee.toLowerCase().includes(searchTerm) ||
            d.description.toLowerCase().includes(searchTerm) ||
            d.bursNo.toLowerCase().includes(searchTerm) ||
            d.remarks.toLowerCase().includes(searchTerm)
          );
        });
      }
      if (filterDate.value) {
        filteredDocs = filteredDocs.filter(d => formatDate(d.dateReceived) === filterDate.value);
      }
      if (filterTime.value) {
        filteredDocs = filteredDocs.filter(d => {
          const docTime = formatTime(d.createdAt).slice(0,5);
          return docTime === filterTime.value;
        });
      }
      if (filterPayee.value.trim()) {
        const val = filterPayee.value.trim().toLowerCase();
        filteredDocs = filteredDocs.filter(d => d.payee.toLowerCase().includes(val));
      }
      if (filterDescription.value.trim()) {
        const val = filterDescription.value.trim().toLowerCase();
        filteredDocs = filteredDocs.filter(d => d.description.toLowerCase().includes(val));
      }
      if (filterBursNo.value.trim()) {
        const val = filterBursNo.value.trim().toLowerCase();
        filteredDocs = filteredDocs.filter(d => d.bursNo.toLowerCase().includes(val));
      }
      if (filterGrossAmount.value) {
        const val = parseFloat(filterGrossAmount.value);
        if (!isNaN(val)) {
          filteredDocs = filteredDocs.filter(d => d.grossAmount === val);
        }
      }
      if (filterFundDisbursed.value) {
        filteredDocs = filteredDocs.filter(d => d.fundDisbursed === filterFundDisbursed.value);
      }
      if (filterFundSaobd.value) {
        filteredDocs = filteredDocs.filter(d => d.fundSaobd === filterFundSaobd.value);
      }
      if (filterRemarks.value.trim()) {
        const val = filterRemarks.value.trim().toLowerCase();
        filteredDocs = filteredDocs.filter(d => d.remarks.toLowerCase().includes(val));
      }
      docsTableBody.innerHTML = '';
      if (filteredDocs.length === 0) {
        const tr = document.createElement('tr');
        const td = document.createElement('td');
        td.colSpan = 10;
        td.className = 'text-center py-6 text-lime-700 select-none font-semibold';
        td.textContent = 'No documents found.';
        tr.appendChild(td);
        docsTableBody.appendChild(tr);
        return;
      }
      filteredDocs.forEach((doc, index) => {
        const tr = document.createElement('tr');
        tr.className = 'hover:bg-lime-100 cursor-pointer rounded-xl';
        tr.tabIndex = 0;
        tr.setAttribute('role', 'button');
        tr.setAttribute('aria-label', `View document from ${formatDate(doc.dateReceived)} by ${doc.payee}`);
        tr.addEventListener('click', () => {
          fillFormForEdit(documents.indexOf(doc));
        });
        tr.addEventListener('keydown', e => {
          if (e.key === 'Enter' || e.key === ' ') {
            e.preventDefault();
            fillFormForEdit(documents.indexOf(doc));
          }
        });
        const tdDate = document.createElement('td');
        tdDate.className = 'px-3 md:px-5 py-3 whitespace-nowrap text-xs md:text-sm text-lime-700 font-semibold';
        tdDate.textContent = formatDate(doc.dateReceived);
        tr.appendChild(tdDate);
        const tdTime = document.createElement('td');
        tdTime.className = 'px-3 md:px-5 py-3 whitespace-nowrap text-xs md:text-sm text-lime-700 font-semibold';
        tdTime.textContent = formatTime(doc.createdAt);
        tr.appendChild(tdTime);
        const tdPayee = document.createElement('td');
        tdPayee.className = 'px-3 md:px-5 py-3 whitespace-nowrap text-xs md:text-sm text-lime-700 font-semibold';
        tdPayee.textContent = doc.payee;
        tr.appendChild(tdPayee);
        const tdDesc = document.createElement('td');
        tdDesc.className = 'px-3 md:px-5 py-3 whitespace-nowrap text-xs md:text-sm text-lime-700 max-w-xs truncate';
        tdDesc.title = doc.description;
        tdDesc.textContent = doc.description;
        tr.appendChild(tdDesc);
        const tdBursNo = document.createElement('td');
        tdBursNo.className = 'px-3 md:px-5 py-3 whitespace-nowrap text-xs md:text-sm text-lime-700 font-mono font-semibold';
        tdBursNo.textContent = doc.bursNo;
        tr.appendChild(tdBursNo);
        const tdGross = document.createElement('td');
        tdGross.className = 'px-3 md:px-5 py-3 whitespace-nowrap text-xs md:text-sm text-lime-700 text-right font-mono font-semibold';
        tdGross.textContent = formatPeso(doc.grossAmount);
        tr.appendChild(tdGross);
        const tdFundDisbursed = document.createElement('td');
        tdFundDisbursed.className = 'px-3 md:px-5 py-3 whitespace-nowrap text-xs md:text-sm text-lime-700 font-semibold';
        tdFundDisbursed.textContent = doc.fundDisbursed;
        tr.appendChild(tdFundDisbursed);
        const tdFundSaobd = document.createElement('td');
        tdFundSaobd.className = 'px-3 md:px-5 py-3 whitespace-nowrap text-xs md:text-sm text-lime-700 font-semibold';
        tdFundSaobd.textContent = doc.fundSaobd || '';
        tr.appendChild(tdFundSaobd);
        const tdRemarks = document.createElement('td');
        tdRemarks.className = 'px-3 md:px-5 py-3 whitespace-normal text-xs md:text-sm text-lime-700 max-w-xs font-semibold';
        tdRemarks.textContent = doc.remarks;
        tr.appendChild(tdRemarks);
        docsTableBody.appendChild(tr);
      });
    }
    function fillFormForEdit(index) {
      if (index < 0 || index >= documents.length) return;
      selectedDocIndex = index;
      const doc = documents[index];
      dateReceivedInput.value = formatDate(doc.dateReceived);
      payeeInput.value = doc.payee;
      descriptionInput.value = doc.description;
      bursNoInput.value = doc.bursNo;
      grossAmountInput.value = doc.grossAmount;
      withSaobdInput.checked = doc.withSaobd;
      fundDisbursedInput.value = doc.fundDisbursed;
      fundSaobdInput.value = doc.fundSaobd || '';
      remarksInput.value = doc.remarks;
      setTypeButtons(doc.type);
      updateDeleteButtonState();
      dateReceivedInput.focus();
    }
    function clearForm() {
      docForm.reset();
      selectedDocIndex = null;
      setTypeButtons(null);
      updateDeleteButtonState();
    }
    function attachEventListeners() {
      btnIncoming.addEventListener('click', () => {
        currentFilter = 'incoming';
        setTypeButtons('incoming');
        renderTable();
      });
      btnOpen.addEventListener('click', () => {
        currentFilter = 'open';
        setTypeButtons('open');
        renderTable();
      });
      docForm.addEventListener('submit', e => {
        e.preventDefault();
        saveDocument();
      });
      deleteBtn.addEventListener('click', () => {
        if (selectedDocIndex === null) {
          alert('Please select a document to delete.');
          return;
        }
        const doc = documents[selectedDocIndex];
        const confirmDelete = confirm(`Are you sure you want to delete the document from ${formatDate(doc.dateReceived)} by ${doc.payee}? This action cannot be undone.`);
        if (confirmDelete) {
          documents.splice(selectedDocIndex, 1);
          saveDocuments();
          updateSummaryCounts();
          renderTable();
          clearForm();
          alert('Document deleted successfully.');
        }
      });
      searchBtn.addEventListener('click', () => {
        renderTable();
      });
      clearBtn.addEventListener('click', () => {
        searchInput.value = '';
        filterDate.value = '';
        filterTime.value = '';
        filterPayee.value = '';
        filterDescription.value = '';
        filterBursNo.value = '';
        filterGrossAmount.value = '';
        filterFundDisbursed.value = '';
        filterFundSaobd.value = '';
        filterRemarks.value = '';
        clearForm();
        currentFilter = null;
        setTypeButtons(null);
        renderTable();
      });
      addBtn.addEventListener('click', () => {
        clearForm();
        dateReceivedInput.focus();
      });
      exportBtn.addEventListener('click', () => {
        exportToExcel();
      });
      [btnIncoming, btnOpen].forEach(btn => {
        btn.addEventListener('keydown', e => {
          if (e.key === 'Enter' || e.key === ' ') {
            e.preventDefault();
            btn.click();
          }
        });
      });
      [filterDate, filterTime, filterPayee, filterDescription, filterBursNo, filterGrossAmount, filterFundDisbursed, filterFundSaobd, filterRemarks].forEach(input => {
        input.addEventListener('input', () => {
          renderTable();
        });
      });
      const formElements = [
        dateReceivedInput,
        payeeInput,
        descriptionInput,
        bursNoInput,
        grossAmountInput,
        withSaobdInput,
        fundDisbursedInput,
        fundSaobdInput,
        remarksInput,
        saveBtn
      ];
      formElements.forEach((el, idx) => {
        el.addEventListener('keydown', e => {
          if (e.key === 'Enter') {
            e.preventDefault();
            let nextIdx = idx + 1;
            while(nextIdx < formElements.length) {
              const nextEl = formElements[nextIdx];
              if (!nextEl.disabled && nextEl.offsetParent !== null) {
                nextEl.focus();
                break;
              }
              nextIdx++;
            }
          }
        });
      });
    }
    function saveDocument() {
      if (!dateReceivedInput.value) {
        alert('Please enter Date Received.');
        dateReceivedInput.focus();
        return;
      }
      if (!payeeInput.value.trim()) {
        alert('Please enter Payee.');
        payeeInput.focus();
        return;
      }
      if (!descriptionInput.value.trim()) {
        alert('Please enter Description.');
        descriptionInput.focus();
        return;
      }
      if (!bursNoInput.value.trim()) {
        alert('Please enter BURS No.');
        bursNoInput.focus();
        return;
      }
      if (!grossAmountInput.value || parseFloat(grossAmountInput.value) < 0) {
        alert('Please enter a valid Gross Amount.');
        grossAmountInput.focus();
        return;
      }
      if (!fundDisbursedInput.value) {
        alert('Please select Fund Disbursed.');
        fundDisbursedInput.focus();
        return;
      }
      let type = currentFilter;
      if (!type) type = 'incoming';
      if (selectedDocIndex !== null && selectedDocIndex >= 0 && selectedDocIndex < documents.length) {
        // Update existing document
        const doc = documents[selectedDocIndex];
        doc.dateReceived = new Date(dateReceivedInput.value);
        doc.payee = payeeInput.value.trim();
        doc.description = descriptionInput.value.trim();
        doc.bursNo = bursNoInput.value.trim();
        doc.grossAmount = parseFloat(grossAmountInput.value);
        doc.withSaobd = withSaobdInput.checked;
        doc.fundDisbursed = fundDisbursedInput.value;
        doc.fundSaobd = fundSaobdInput.value || '';
        doc.remarks = remarksInput.value.trim();
        doc.type = type;
        doc.status = 'open';
      } else {
        // Add new document
        const newDoc = {
          id: crypto.randomUUID(),
          dateReceived: new Date(dateReceivedInput.value),
          payee: payeeInput.value.trim(),
          description: descriptionInput.value.trim(),
          bursNo: bursNoInput.value.trim(),
          grossAmount: parseFloat(grossAmountInput.value),
          withSaobd: withSaobdInput.checked,
          fundDisbursed: fundDisbursedInput.value,
          fundSaobd: fundSaobdInput.value || '',
          remarks: remarksInput.value.trim(),
          type: type,
          status: 'open',
          createdAt: new Date(),
          lastQrScan: null,
        };
        documents.push(newDoc);
      }
      saveDocuments();
      updateSummaryCounts();
      renderTable();
      clearForm();
      alert('Document saved successfully.');
    }
    function exportToExcel() {
      if (documents.length === 0) {
        alert('No documents to export.');
        return;
      }
      const headers = [
        'Date Received',
        'Time Created',
        'Payee',
        'Description',
        'BURS No.',
        'Gross Amount (₱)',
        'With SAOBD',
        'Fund Disbursed',
        'Fund SAOBD',
        'Remarks',
      ];
      const data = documents.map(doc => [
        formatDate(doc.dateReceived),
        formatTime(doc.createdAt),
        doc.payee,
        doc.description,
        doc.bursNo,
        doc.grossAmount.toLocaleString('en-PH', {minimumFractionDigits: 2, maximumFractionDigits: 2}),
        doc.withSaobd ? 'Yes' : 'No',
        doc.fundDisbursed,
        doc.fundSaobd || '',
        doc.remarks,
      ]);
      const ws = XLSX.utils.aoa_to_sheet([headers, ...data]);
      const wb = XLSX.utils.book_new();
      XLSX.utils.book_append_sheet(wb, ws, 'Documents');
      XLSX.writeFile(wb, 'pca_rxii_burs_documents.xlsx');
    }
    function setTypeButtons(type) {
      [btnIncoming, btnOpen].forEach(btn => {
        btn.classList.remove('ring-4', 'ring-offset-2', 'ring-lime-400', 'ring-yellow-400');
        btn.setAttribute('aria-pressed', 'false');
      });
      if (type === 'incoming') {
        btnIncoming.classList.add('ring-4', 'ring-offset-2', 'ring-lime-400');
        btnIncoming.setAttribute('aria-pressed', 'true');
      } else if (type === 'open') {
        btnOpen.classList.add('ring-4', 'ring-offset-2', 'ring-yellow-400');
        btnOpen.setAttribute('aria-pressed', 'true');
      }
    }
    function updateDeleteButtonState() {
      if (selectedDocIndex !== null && selectedDocIndex >= 0 && selectedDocIndex < documents.length) {
        deleteBtn.disabled = false;
        deleteBtn.classList.remove('opacity-50', 'cursor-not-allowed');
      } else {
        deleteBtn.disabled = true;
        deleteBtn.classList.add('opacity-50', 'cursor-not-allowed');
      }
    }
    window.addEventListener('load', () => {
      // Show login/signup container, hide app container initially
      authContainer.style.display = 'flex';
      appContainer.style.display = 'none';
    });
  </script>
</body>
</html>
