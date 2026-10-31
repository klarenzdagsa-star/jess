<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Chowking Self-Service Kiosk - Social Media Presentation</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            chowking: {
              red: '#D91B24',
              darkred: '#990000',
              yellow: '#FFB800',
              gold: '#E5A000',
              warmbg: '#FFFDF9',
              cardbg: '#FFFFFF',
              dark: '#161616'
            }
          },
          fontFamily: {
            sans: ['Plus Jakarta Sans', 'sans-serif']
          }
        }
      }
    }
  </script>

  <style>
    @keyframes floatSlow {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-6px); }
    }
    .floating-badge {
      animation: floatSlow 3s ease-in-out infinite;
    }
    @keyframes pulseRing {
      0% { transform: scale(0.95); opacity: 0.8; }
      50% { transform: scale(1.08); opacity: 1; }
      100% { transform: scale(0.95); opacity: 0.8; }
    }
    .pulse-glow {
      animation: pulseRing 2s infinite ease-in-out;
    }
    ::-webkit-scrollbar {
      width: 5px;
      height: 5px;
    }
    ::-webkit-scrollbar-track {
      background: #F8F4EE;
    }
    ::-webkit-scrollbar-thumb {
      background: #D91B24;
      border-radius: 4px;
    }
    .hide-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .hide-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
  </style>
<style data-bard-injected="true">
@media screen {
    html {
        background-color: #0f172a;
    }
    body {
        padding: 16px 0 32px 0;
    }
}
@media screen and (prefers-color-scheme: dark) {
    html {
        background-color: #0f172a;
    }
}
@media screen and (max-width: 600px) {
    body {
        padding: 0;
        margin: 0 auto;
    }
}
</style></head>
<body class="bg-slate-950 text-slate-800 font-sans antialiased select-none min-h-screen flex items-center justify-center p-0 sm:p-6">

  <!-- Showcase Wrapper with Video Recording Guide Frame -->
  <div class="w-full max-w-5xl h-[100vh] sm:h-[92vh] bg-chowking-warmbg sm:rounded-3xl shadow-2xl flex flex-col overflow-hidden relative border-0 sm:border-[6px] border-slate-800 ring-1 ring-white/10">

    <!-- VIDEO RECORDER OVERLAY BAR (Top Social Banner) -->
    <div class="bg-slate-900 text-white px-4 py-2.5 flex items-center justify-between border-b border-slate-800 shrink-0 z-30">
      <div class="flex items-center gap-2.5">
        <span class="w-3 h-3 bg-red-500 rounded-full animate-ping"></span>
        <span class="text-xs font-black uppercase tracking-widest text-chowking-yellow">REC // UI Showcase Mode</span>
      </div>
      <div class="flex items-center gap-2 text-xs text-slate-400">
        <span class="hidden sm:inline">Designed for TikTok / Reels / Shorts</span>
        <span class="bg-slate-800 text-chowking-yellow px-2 py-0.5 rounded font-mono font-bold text-[11px]">9:16 Optimized</span>
      </div>
    </div>

    <!-- MAIN KIOSK HEADER -->
    <header class="bg-gradient-to-r from-chowking-red via-chowking-darkred to-red-950 text-white p-3.5 sm:p-5 flex items-center justify-between shadow-lg z-20 shrink-0">
      <div class="flex items-center gap-3">
        <!-- Logo Badge -->
        <div class="bg-white text-chowking-red font-black text-xl sm:text-2xl px-3 py-1.5 rounded-2xl shadow-md tracking-wider flex items-center gap-2 transform -rotate-1">
          <i class="fa-solid font-bold fa-bowl-rice text-chowking-yellow text-xl"></i>
          <span>Chowking</span>
        </div>
        <div>
          <span class="text-[11px] uppercase tracking-widest text-chowking-yellow font-black block">Self-Service Kiosk 2.0</span>
          <span class="text-xs text-white/90 font-medium">Flagship Store Experience</span>
        </div>
      </div>

      <!-- Controls Right -->
      <div class="flex items-center gap-2.5">
        <span id="orderTypeBadge" class="hidden bg-chowking-yellow text-chowking-dark font-extrabold text-xs px-3.5 py-1.5 rounded-full uppercase tracking-wider shadow-md">
          Dine In
        </span>
        <button id="toggleEvalBtn" onclick="toggleEvaluatorPanel()" class="bg-black/30 hover:bg-black/50 text-chowking-yellow border border-chowking-yellow/40 font-bold text-xs px-3 py-2 rounded-xl flex items-center gap-2 transition active:scale-95 backdrop-blur shadow">
          <i class="fa-solid fa-flask text-sm"></i>
          <span class="hidden sm:inline">HCI Usability Log</span>
          <span class="sm:hidden">HCI</span>
        </button>
      </div>
    </header>

    <!-- MAIN INTERACTIVE SCREEN CONTAINER -->
    <main class="flex-1 relative overflow-hidden flex flex-col">

      <!-- ================= SCREEN 1: WELCOME / START SCREEN ================= -->
      <section id="screenWelcome" class="absolute inset-0 bg-gradient-to-b from-chowking-red via-red-900 to-slate-950 text-white flex flex-col justify-between p-6 z-10 overflow-y-auto">
        
        <!-- Top banner graphics -->
        <div class="text-center pt-6 sm:pt-10">
          <span class="floating-badge inline-block bg-chowking-yellow/20 text-chowking-yellow text-xs font-bold px-4 py-1.5 rounded-full border border-chowking-yellow/40 uppercase tracking-widest shadow">
            Touch to Start Ordering
          </span>
          <h1 class="text-3xl sm:text-5xl font-black mt-4 text-chowking-yellow tracking-tight drop-shadow-lg leading-none">
            CHINESE-STYLE<br>FAVORITES
          </h1>
          <p class="text-slate-200 text-xs sm:text-sm mt-3 max-w-sm mx-auto font-medium">
            Freshly cooked Wok-fried Chao Fan, Crispy Fried Chicken, and Halo-Halo.
          </p>
        </div>

        <!-- Featured Dish Graphic Hero Carousel Simulation -->
        <div class="my-auto text-center relative py-6">
          <div class="w-52 h-52 sm:w-64 sm:h-64 mx-auto rounded-full bg-chowking-yellow/10 border-8 border-chowking-yellow/30 flex items-center justify-center p-3 relative shadow-2xl pulse-glow">
            <img src="https://placehold.co/400x400/990000/FFB800?text=Chao+Fan+%26+Lauriat" alt="Chowking Hero Food" class="rounded-full object-cover w-full h-full border-4 border-chowking-yellow shadow-inner">
            <span class="absolute -bottom-3 bg-chowking-yellow text-chowking-dark text-xs sm:text-sm font-black px-5 py-2 rounded-full shadow-xl uppercase tracking-wide border-2 border-white">
              🔥 Best Sellers Today
            </span>
          </div>
        </div>

        <!-- Bottom Action: Select Order Type -->
        <div class="bg-white/10 backdrop-blur-lg rounded-3xl p-5 border border-white/20 text-center shadow-2xl max-w-md mx-auto w-full mb-2">
          <p class="text-xs font-extrabold uppercase tracking-widest text-chowking-yellow mb-3">Please Select Dining Option</p>
          <div class="grid grid-cols-2 gap-3.5">
            <button onclick="startOrder('Dine In')" class="bg-chowking-yellow hover:bg-chowking-gold text-chowking-dark font-black py-4 px-4 rounded-2xl shadow-xl flex flex-col items-center justify-center gap-1.5 active:scale-95 transition border-b-4 border-amber-700 group">
              <i class="fa-solid fa-utensils text-2xl group-hover:scale-110 transition"></i>
              <span class="text-sm uppercase tracking-wide">Dine In</span>
            </button>
            <button onclick="startOrder('Take Out')" class="bg-white hover:bg-slate-100 text-chowking-red font-black py-4 px-4 rounded-2xl shadow-xl flex flex-col items-center justify-center gap-1.5 active:scale-95 transition border-b-4 border-slate-300 group">
              <i class="fa-solid fa-bag-shopping text-2xl group-hover:scale-110 transition"></i>
              <span class="text-sm uppercase tracking-wide">Take Out</span>
            </button>
          </div>
        </div>
      </section>

      <!-- ================= SCREEN 2: MENU & CATALOG ================= -->
      <section id="screenMenu" class="hidden flex-1 flex flex-col h-full bg-chowking-warmbg overflow-hidden">
        
        <!-- Category Navigation Bar -->
        <nav class="bg-white border-b border-slate-200/80 shadow-sm shrink-0 overflow-x-auto hide-scrollbar p-2.5 flex gap-2.5">
          <!-- Categories populated by JavaScript -->
        </nav>

        <!-- Main Content Grid (Items + Cart Bar) -->
        <div class="flex-1 flex flex-col md:flex-row overflow-hidden relative">
          
          <!-- Food Menu Items Grid -->
          <div class="flex-1 overflow-y-auto p-3 sm:p-5 grid grid-cols-2 sm:grid-cols-3 gap-3.5 sm:gap-4 content-start" id="foodItemsContainer">
            <!-- Items injected by JS -->
          </div>

          <!-- Bottom / Side Cart Drawer Summary Bar -->
          <div class="bg-white border-t md:border-t-0 md:border-l border-slate-200/80 shadow-2xl p-4 flex flex-col shrink-0 md:w-88 justify-between z-10">
            <div>
              <div class="flex items-center justify-between mb-3 pb-2 border-b border-slate-100">
                <h3 class="font-black text-slate-800 text-sm flex items-center gap-2">
                  <i class="fa-solid fa-cart-shopping text-chowking-red text-base"></i> Order Tray
                </h3>
                <span id="cartCountBadge" class="bg-chowking-red text-white text-xs font-extrabold px-2.5 py-0.5 rounded-full shadow">
                  0 items
                </span>
              </div>

              <!-- Cart Item List Container -->
              <div id="cartItemList" class="max-h-40 md:max-h-80 overflow-y-auto divide-y divide-slate-100 text-xs text-slate-600 pr-1">
                <div class="py-10 text-center text-slate-400 italic">
                  Your tray is empty.<br>Tap a delicious item to add!
                </div>
              </div>
            </div>

            <!-- Cart Totals & Checkout Trigger -->
            <div class="pt-3 border-t border-slate-200 mt-2 bg-white">
              <div class="flex justify-between items-center text-xs mb-1 text-slate-500 font-medium">
                <span>Subtotal</span>
                <span id="subtotalPrice" class="font-bold text-slate-800">₱0.00</span>
              </div>
              <div class="flex justify-between items-center text-sm font-black text-chowking-red mb-3">
                <span>Total Amount</span>
                <span id="totalPrice" class="text-xl">₱0.00</span>
              </div>
              <button id="btnProceedCheckout" onclick="openCheckoutModal()" disabled class="w-full bg-slate-200 text-slate-400 font-extrabold py-3.5 rounded-2xl shadow-none uppercase tracking-wider text-xs flex items-center justify-center gap-2 transition cursor-not-allowed">
                <span>Proceed to Payment</span>
                <i class="fa-solid fa-arrow-right"></i>
              </button>
            </div>
          </div>

        </div>
      </section>

      <!-- ================= SCREEN 3: ORDER SUCCESS / QUEUE STATUS ================= -->
      <section id="screenSuccess" class="hidden absolute inset-0 bg-slate-950 text-white flex flex-col justify-between p-6 z-30 text-center">
        <div class="pt-8">
          <div class="w-20 h-20 bg-emerald-500 text-white rounded-full flex items-center justify-center mx-auto text-4xl shadow-2xl mb-4 animate-bounce">
            <i class="fa-solid fa-check"></i>
          </div>
          <h2 class="text-3xl sm:text-4xl font-black text-chowking-yellow tracking-tight">ORDER CONFIRMED!</h2>
          <p class="text-slate-300 text-xs sm:text-sm mt-1">Your ticket has been sent to the kitchen counter.</p>
        </div>

        <!-- Big Ticket Order Number Display -->
        <div class="bg-slate-900 border-2 border-chowking-yellow/50 rounded-3xl p-6 my-auto max-w-xs mx-auto w-full shadow-2xl relative overflow-hidden">
          <span class="text-xs uppercase tracking-widest text-slate-400 font-bold block mb-1">Queue Number</span>
          <div id="queueOrderNumber" class="text-6xl sm:text-7xl font-black text-chowking-yellow tracking-wider my-2 font-mono drop-shadow">
            #101
          </div>
          <div id="diningOptionResult" class="inline-block bg-slate-800 text-chowking-yellow text-xs px-4 py-1.5 rounded-full uppercase font-extrabold tracking-wider border border-slate-700">
            Dine In
          </div>

          <div class="mt-6 pt-4 border-t border-slate-800 flex items-center justify-center gap-3">
            <div class="w-3.5 h-3.5 bg-chowking-yellow rounded-full pulse-glow"></div>
            <span class="text-xs text-slate-200 font-bold uppercase tracking-wider">Kitchen is preparing...</span>
          </div>
        </div>

        <!-- Order Done Reset Action -->
        <div class="pb-4 max-w-xs mx-auto w-full">
          <p class="text-[11px] text-slate-400 mb-3">Please keep your printed receipt ready.</p>
          <button onclick="resetKioskToWelcome()" class="bg-chowking-red hover:bg-chowking-darkred text-white font-black px-6 py-4 rounded-2xl uppercase tracking-wider text-sm shadow-xl w-full active:scale-95 transition border-b-4 border-red-950">
            Finish &amp; New Order
          </button>
        </div>
      </section>

    </main>

    <!-- ================= MODAL 1: CUSTOMIZATION MODAL ================= -->
    <div id="customizationModal" class="hidden fixed inset-0 bg-slate-950/80 backdrop-blur-md z-40 flex items-end sm:items-center justify-center p-0 sm:p-4">
      <div class="bg-white w-full sm:max-w-md rounded-t-3xl sm:rounded-3xl max-h-[90vh] flex flex-col overflow-hidden shadow-2xl animate-in slide-in-from-bottom duration-300">
        
        <!-- Modal Header -->
        <div class="bg-chowking-red text-white p-4 flex justify-between items-center shrink-0">
          <h3 id="modalItemTitle" class="font-black text-base">Item Name</h3>
          <button onclick="closeCustomizationModal()" class="text-white/80 hover:text-white text-xl w-8 h-8 rounded-full flex items-center justify-center hover:bg-white/10 transition">
            <i class="fa-solid fa-xmark"></i>
          </button>
        </div>

        <!-- Modal Body Options -->
        <div class="p-4 sm:p-5 overflow-y-auto space-y-4 flex-1 text-xs sm:text-sm">
          <!-- Price & Description -->
          <div class="flex gap-4 border-b border-slate-100 pb-4 items-center">
            <img id="modalItemImg" src="" alt="Food" class="w-24 h-24 object-cover rounded-2xl border border-slate-200 shadow-sm shrink-0">
            <div>
              <p id="modalItemDesc" class="text-slate-500 text-xs leading-relaxed">Description goes here...</p>
              <p id="modalItemBasePrice" class="font-black text-chowking-red text-lg mt-1.5">₱0.00</p>
            </div>
          </div>

          <!-- Dynamic Options Injected Here -->
          <div id="modalOptionsContainer" class="space-y-4">
            <!-- Choices -->
          </div>

          <!-- Special Instructions -->
          <div>
            <label class="block font-bold text-slate-700 mb-1 text-xs">Special Requests / Notes</label>
            <input type="text" id="modalNotes" placeholder="e.g. Extra chili garlic oil, less ice" class="w-full bg-slate-50 border border-slate-200 rounded-xl p-3 text-xs focus:outline-none focus:border-chowking-red transition">
          </div>
        </div>

        <!-- Modal Footer Actions -->
        <div class="bg-slate-50 p-4 border-t border-slate-200 flex items-center justify-between shrink-0 gap-3">
          <!-- Quantity Stepper -->
          <div class="flex items-center border border-slate-300 rounded-xl bg-white overflow-hidden shadow-sm">
            <button onclick="adjustModalQty(-1)" class="w-10 h-10 flex items-center justify-center text-slate-700 font-black hover:bg-slate-100 text-base active:bg-slate-200">-</button>
            <span id="modalQtyDisplay" class="w-8 text-center font-black text-slate-800 text-sm">1</span>
            <button onclick="adjustModalQty(1)" class="w-10 h-10 flex items-center justify-center text-slate-700 font-black hover:bg-slate-100 text-base active:bg-slate-200">+</button>
          </div>

          <!-- Add to Tray Button -->
          <button onclick="confirmAddToCart()" class="flex-1 bg-chowking-red hover:bg-chowking-darkred text-white font-black py-3.5 px-4 rounded-xl shadow-lg uppercase tracking-wider text-xs flex justify-between items-center transition active:scale-95">
            <span>Add to Tray</span>
            <span id="modalFinalPrice" class="text-sm">₱0.00</span>
          </button>
        </div>

      </div>
    </div>

    <!-- ================= MODAL 2: CHECKOUT & PAYMENT ================= -->
    <div id="checkoutModal" class="hidden fixed inset-0 bg-slate-950/80 backdrop-blur-md z-40 flex items-center justify-center p-4">
      <div class="bg-white w-full max-w-sm rounded-3xl overflow-hidden shadow-2xl flex flex-col">
        <div class="bg-slate-900 text-white p-4 flex justify-between items-center">
          <h3 class="font-black text-sm flex items-center gap-2">
            <i class="fa-solid fa-credit-card text-chowking-yellow"></i> Select Payment Method
          </h3>
          <button onclick="closeCheckoutModal()" class="text-white/80 hover:text-white">
            <i class="fa-solid fa-xmark text-lg"></i>
          </button>
        </div>

        <div class="p-5 space-y-4">
          <div class="bg-amber-50 p-3.5 rounded-2xl border border-amber-200 flex justify-between items-center shadow-inner">
            <span class="text-xs font-bold text-slate-700">Total Amount Due:</span>
            <span id="checkoutTotalDisplay" class="text-2xl font-black text-chowking-red">₱0.00</span>
          </div>

          <!-- Payment Options Grid -->
          <div class="grid grid-cols-2 gap-3 text-xs">
            <button onclick="selectPayment('GCash')" class="payment-btn border-2 border-slate-200 hover:border-blue-500 hover:bg-blue-50/50 rounded-2xl p-3.5 flex flex-col items-center gap-2 transition active:scale-95 group">
              <i class="fa-solid fa-mobile-screen-button text-2xl text-blue-500 group-hover:scale-110 transition"></i>
              <span class="font-extrabold text-slate-700">GCash</span>
            </button>
            <button onclick="selectPayment('Maya')" class="payment-btn border-2 border-slate-200 hover:border-emerald-500 hover:bg-emerald-50/50 rounded-2xl p-3.5 flex flex-col items-center gap-2 transition active:scale-95 group">
              <i class="fa-solid fa-wallet text-2xl text-emerald-500 group-hover:scale-110 transition"></i>
              <span class="font-extrabold text-slate-700">Maya</span>
            </button>
            <button onclick="selectPayment('Card')" class="payment-btn border-2 border-slate-200 hover:border-purple-500 hover:bg-purple-50/50 rounded-2xl p-3.5 flex flex-col items-center gap-2 transition active:scale-95 group">
              <i class="fa-solid fa-credit-card text-2xl text-purple-500 group-hover:scale-110 transition"></i>
              <span class="font-extrabold text-slate-700">Card</span>
            </button>
            <button onclick="selectPayment('Cash Counter')" class="payment-btn border-2 border-slate-200 hover:border-chowking-red hover:bg-red-50/50 rounded-2xl p-3.5 flex flex-col items-center gap-2 transition active:scale-95 group">
              <i class="fa-solid fa-hand-holding-dollar text-2xl text-chowking-red group-hover:scale-110 transition"></i>
              <span class="font-extrabold text-slate-700">Counter Cash</span>
            </button>
          </div>
        </div>

        <div class="p-3.5 bg-slate-50 border-t border-slate-200 text-center">
          <p class="text-[11px] text-slate-400 font-medium">⚡ Instant Demo Simulation Mode</p>
        </div>
      </div>
    </div>

    <!-- ================= HCI EVALUATOR MODE DRAWER ================= -->
    <div id="evaluatorDrawer" class="hidden absolute inset-x-0 top-14 sm:top-16 bg-slate-900 text-white z-50 p-4 border-b-4 border-chowking-yellow shadow-2xl transition-all duration-300">
      <div class="flex justify-between items-center border-b border-slate-700 pb-2 mb-3">
        <h4 class="font-black text-chowking-yellow text-xs uppercase tracking-wider flex items-center gap-2">
          <i class="fa-solid fa-flask"></i> HCI Usability Evaluation Log &amp; Timer
        </h4>
        <button onclick="toggleEvaluatorPanel()" class="text-slate-400 hover:text-white text-xs font-bold">
          <i class="fa-solid fa-chevron-up"></i> Close
        </button>
      </div>

      <div class="grid grid-cols-2 gap-3 text-xs mb-3">
        <!-- Timer -->
        <div class="bg-slate-800 p-3 rounded-xl border border-slate-700">
          <span class="text-slate-400 block text-[10px] uppercase font-bold">Task Completion Time</span>
          <span id="evalTimer" class="font-mono text-lg font-bold text-emerald-400">00:00.0</span>
          <div class="mt-2 flex gap-1.5">
            <button onclick="startEvalTimer()" class="bg-emerald-600 px-2.5 py-1 rounded text-[10px] hover:bg-emerald-500 font-bold transition">Start</button>
            <button onclick="resetEvalTimer()" class="bg-slate-700 px-2.5 py-1 rounded text-[10px] hover:bg-slate-600 font-bold transition">Reset</button>
          </div>
        </div>

        <!-- Task Tracker -->
        <div class="bg-slate-800 p-3 rounded-xl border border-slate-700">
          <span class="text-slate-400 block text-[10px] uppercase font-bold">System Usability Scale (SUS)</span>
          <div class="flex gap-1.5 text-chowking-yellow text-base mt-2" id="starRating">
            <i class="fa-solid fa-star cursor-pointer" onclick="setRating(1)"></i>
            <i class="fa-solid fa-star cursor-pointer" onclick="setRating(2)"></i>
            <i class="fa-solid fa-star cursor-pointer" onclick="setRating(3)"></i>
            <i class="fa-solid fa-star cursor-pointer" onclick="setRating(4)"></i>
            <i class="fa-solid fa-star cursor-pointer" onclick="setRating(5)"></i>
          </div>
        </div>
      </div>

      <!-- Feedback Notes & Log Submission -->
      <div class="space-y-2.5">
        <input type="text" id="evaluatorName" placeholder="Evaluator Name / Student ID" class="w-full bg-slate-800 border border-slate-700 rounded-xl p-2.5 text-xs text-white placeholder-slate-500 focus:outline-none focus:border-chowking-yellow transition">
        <textarea id="evalNotes" rows="2" placeholder="Usability observations (e.g. intuitive navigation, smooth modal selection...)" class="w-full bg-slate-800 border border-slate-700 rounded-xl p-2.5 text-xs text-white placeholder-slate-500 focus:outline-none focus:border-chowking-yellow transition"></textarea>
        <button onclick="saveEvaluationLog()" class="w-full bg-chowking-yellow text-chowking-dark font-black py-2 rounded-xl text-xs uppercase tracking-wide hover:bg-chowking-gold transition shadow">
          Log Test Data &amp; Reset
        </button>
      </div>

      <!-- Past Logs Mini Display -->
      <div class="mt-3 pt-2.5 border-t border-slate-800">
        <span class="text-[10px] text-slate-400 uppercase tracking-wider block mb-1">Logged Test Results (<span id="logCount">0</span>)</span>
        <div id="evalLogsList" class="max-h-24 overflow-y-auto space-y-1.5 text-[10px] text-slate-300 pr-1">
          <!-- Logs appear here -->
        </div>
      </div>
    </div>

  </div>

  <!-- ================= JAVASCRIPT LOGIC ================= -->
  <script>
    let orderType = 'Dine In';
    let currentCategory = 'lauriat';
    let cart = [];
    let currentItemForModal = null;
    let modalQuantity = 1;
    let selectedModalOptions = {};
    let orderQueueNumber = 101;

    let timerInterval = null;
    let timerStartTime = 0;
    let elapsedTime = 0;
    let currentRating = 5;
    let evaluationLogs = [];

    const menuCategories = [
      { id: 'lauriat', name: 'Lauriat Meals', icon: 'fa-utensils' },
      { id: 'chaofan', name: 'Chao Fan', icon: 'fa-bowl-rice' },
      { id: 'dimsum', name: 'Dim Sum', icon: 'fa-dumpling' },
      { id: 'noodles', name: 'Noodles & Soups', icon: 'fa-bowl-food' },
      { id: 'desserts', name: 'Halo-Halo', icon: 'fa-ice-cream' },
      { id: 'drinks', name: 'Drinks', icon: 'fa-glass-water' }
    ];

    const foodItems = [
      {
        id: 'l1',
        category: 'lauriat',
        name: 'Pork Siomai Lauriat',
        price: 215,
        image: 'https://placehold.co/300x300/D91B24/FFFFFF?text=Siomai+Lauriat',
        desc: 'Pork Siomai, Chao Fan, Pancit Canton, Buchi, Chicharabao, & Egg Roll.',
        options: [
          { type: 'select', title: 'Siomai Preparation', key: 'prep', choices: [{ name: 'Steamed', price: 0 }, { name: 'Fried', price: 0 }] },
          { type: 'checkbox', title: 'Add Extras', key: 'extras', choices: [{ name: 'Extra 2pcs Siomai', price: 45 }, { name: 'Extra Buchi 1pc', price: 25 }] },
          { type: 'select', title: 'Drink Upgrade', key: 'drink', choices: [{ name: 'Regular Iced Tea', price: 0 }, { name: 'Large Iced Tea', price: 20 }, { name: 'Small Pineapple Juice', price: 25 }] }
        ]
      },
      {
        id: 'l2',
        category: 'lauriat',
        name: 'Chinese Style Fried Chicken Lauriat',
        price: 245,
        image: 'https://placehold.co/300x300/990000/FFB800?text=Chicken+Lauriat',
        desc: '1pc Crispy Fried Chicken, Chao Fan, Pancit Canton, Buchi, and Chicharabao.',
        options: [
          { type: 'select', title: 'Chicken Part', key: 'part', choices: [{ name: 'Thigh / Leg', price: 0 }, { name: 'Breast / Wing', price: 0 }] },
          { type: 'select', title: 'Drink Upgrade', key: 'drink', choices: [{ name: 'Regular Iced Tea', price: 0 }, { name: 'Large Iced Tea', price: 20 }] }
        ]
      },
      {
        id: 'c1',
        category: 'chaofan',
        name: 'Yang Chow Chao Fan',
        price: 115,
        image: 'https://placehold.co/300x300/E5A000/FFFFFF?text=Yang+Chow',
        desc: 'Wok-fried rice packed with meat, egg, and green peas.',
        options: [
          { type: 'select', title: 'Add Topping', key: 'topping', choices: [{ name: 'No Topping', price: 0 }, { name: '4pcs Steamed Siomai', price: 55 }, { name: '4pcs Fried Siomai', price: 55 }, { name: 'Fried Dumplings', price: 60 }] },
          { type: 'checkbox', title: 'Rice Upgrade', key: 'rice', choices: [{ name: 'Extra Egg', price: 20 }] }
        ]
      },
      {
        id: 'c2',
        category: 'chaofan',
        name: 'Pork Chao Fan with Egg',
        price: 99,
        image: 'https://placehold.co/300x300/FFB800/990000?text=Pork+Chao+Fan',
        desc: 'Signature wok-fried rice topped with savory fried egg.',
        options: [
          { type: 'select', title: 'Add Topping', key: 'topping', choices: [{ name: 'No Topping', price: 0 }, { name: '4pcs Steamed Siomai', price: 55 }] }
        ]
      },
      {
        id: 'd1',
        category: 'dimsum',
        name: 'Pork Siomai (4 pcs)',
        price: 75,
        image: 'https://placehold.co/300x300/990000/FFFFFF?text=Pork+Siomai',
        desc: 'Classic savory pork dimsum served with chili garlic sauce.',
        options: [
          { type: 'select', title: 'Preparation', key: 'prep', choices: [{ name: 'Steamed', price: 0 }, { name: 'Fried', price: 0 }] }
        ]
      },
      {
        id: 'd2',
        category: 'dimsum',
        name: 'Chao Bao (1 pc)',
        price: 49,
        image: 'https://placehold.co/300x300/FFFDF9/D91B24?text=Chao+Bao',
        desc: 'Soft steamed bun filled with sweet & savory braised pork.',
        options: []
      },
      {
        id: 'n1',
        category: 'noodles',
        name: 'Beef Wonton Noodle Soup',
        price: 175,
        image: 'https://placehold.co/300x300/D91B24/FFB800?text=Beef+Noodle+Soup',
        desc: 'Tender beef brisket and pork wontons in rich flavorful broth.',
        options: [
          { type: 'checkbox', title: 'Extras', key: 'extras', choices: [{ name: 'Extra Wonton (2pcs)', price: 40 }, { name: 'Extra Egg', price: 20 }] }
        ]
      },
      {
        id: 'h1',
        category: 'desserts',
        name: 'Super Sangkap Halo-Halo',
        price: 110,
        image: 'https://placehold.co/300x300/FFB800/D91B24?text=Super+Halo-Halo',
        desc: 'Shaved ice with sweet beans, leche flan, ube halaya, and ice cream.',
        options: [
          { type: 'select', title: 'Ice Cream Scoop', key: 'icecream', choices: [{ name: 'Ube Ice Cream', price: 0 }, { name: 'Vanilla Ice Cream', price: 0 }] },
          { type: 'checkbox', title: 'Extra Toppings', key: 'extras', choices: [{ name: 'Extra Leche Flan Slice', price: 25 }, { name: 'Extra Ube Scoop', price: 30 }] }
        ]
      },
      {
        id: 'dr1',
        category: 'drinks',
        name: 'Nai Cha (Pearl Milk Tea)',
        price: 95,
        image: 'https://placehold.co/300x300/E5A000/161616?text=Nai+Cha',
        desc: 'Authentic Hong-Kong style milk tea with chewy tapioca pearls.',
        options: [
          { type: 'select', title: 'Sweetness Level', key: 'sweetness', choices: [{ name: '100% Normal', price: 0 }, { name: '75% Less Sweet', price: 0 }, { name: '50% Half Sweet', price: 0 }] },
          { type: 'select', title: 'Size Upgrade', key: 'size', choices: [{ name: 'Medium', price: 0 }, { name: 'Large', price: 20 }] }
        ]
      }
    ];

    window.onload = function() {
      renderCategories();
      renderMenuItems();
      updateCartUI();
    };

    function startOrder(type) {
      orderType = type;
      document.getElementById('orderTypeBadge').innerText = type;
      document.getElementById('orderTypeBadge').classList.remove('hidden');
      document.getElementById('screenWelcome').classList.add('hidden');
      document.getElementById('screenMenu').classList.remove('hidden');
      startEvalTimer();
    }

    function resetKioskToWelcome() {
      cart = [];
      orderType = 'Dine In';
      updateCartUI();
      document.getElementById('screenSuccess').classList.add('hidden');
      document.getElementById('screenMenu').classList.add('hidden');
      document.getElementById('screenWelcome').classList.remove('hidden');
      document.getElementById('orderTypeBadge').classList.add('hidden');
    }

    function renderCategories() {
      const nav = document.querySelector('nav');
      nav.innerHTML = menuCategories.map(cat => `
        <button onclick="switchCategory('${cat.id}')" class="px-4 py-2.5 rounded-2xl text-xs font-black whitespace-nowrap flex items-center gap-2 transition shadow-sm ${cat.id === currentCategory ? 'bg-chowking-red text-white shadow-md ring-2 ring-red-400' : 'bg-white text-slate-700 hover:bg-slate-100 border border-slate-200'}">
          <i class="fa-solid ${cat.icon}"></i>
          <span>${cat.name}</span>
        </button>
      `).join('');
    }

    function switchCategory(catId) {
      currentCategory = catId;
      renderCategories();
      renderMenuItems();
    }

    function renderMenuItems() {
      const container = document.getElementById('foodItemsContainer');
      const filtered = foodItems.filter(item => item.category === currentCategory);

      container.innerHTML = filtered.map(item => `
        <div onclick="openCustomizationModal('${item.id}')" class="bg-white rounded-3xl p-3 border border-slate-200/80 shadow-md hover:shadow-xl transition cursor-pointer flex flex-col justify-between group active:scale-95">
          <div>
            <div class="relative overflow-hidden rounded-2xl mb-2.5 bg-slate-100 aspect-square shadow-inner">
              <img src="${item.image}" alt="${item.name}" class="w-full h-full object-cover group-hover:scale-105 transition duration-300">
              <span class="absolute top-2 right-2 bg-chowking-red text-white text-[11px] font-black px-2.5 py-1 rounded-lg shadow">
                ₱${item.price}
              </span>
            </div>
            <h4 class="font-black text-xs text-slate-800 line-clamp-1">${item.name}</h4>
            <p class="text-[10px] text-slate-500 line-clamp-2 mt-0.5 leading-relaxed">${item.desc}</p>
          </div>
          <button class="mt-3 w-full bg-amber-50 border border-chowking-yellow/60 text-chowking-dark hover:bg-chowking-yellow font-extrabold text-[11px] py-2 rounded-xl flex items-center justify-center gap-1.5 transition shadow-sm">
            <i class="fa-solid fa-plus text-[10px]"></i> Customize
          </button>
        </div>
      `).join('');
    }

    function openCustomizationModal(itemId) {
      currentItemForModal = foodItems.find(i => i.id === itemId);
      modalQuantity = 1;
      selectedModalOptions = {};

      document.getElementById('modalItemTitle').innerText = currentItemForModal.name;
      document.getElementById('modalItemDesc').innerText = currentItemForModal.desc;
      document.getElementById('modalItemBasePrice').innerText = `₱${currentItemForModal.price.toFixed(2)}`;
      document.getElementById('modalItemImg').src = currentItemForModal.image;
      document.getElementById('modalQtyDisplay').innerText = modalQuantity;
      document.getElementById('modalNotes').value = '';

      if (currentItemForModal.options) {
        currentItemForModal.options.forEach(opt => {
          if (opt.type === 'select') {
            selectedModalOptions[opt.key] = opt.choices[0];
          } else if (opt.type === 'checkbox') {
            selectedModalOptions[opt.key] = [];
          }
        });
      }

      renderModalOptions();
      updateModalPrice();
      document.getElementById('customizationModal').classList.remove('hidden');
    }

    function closeCustomizationModal() {
      document.getElementById('customizationModal').classList.add('hidden');
    }

    function renderModalOptions() {
      const container = document.getElementById('modalOptionsContainer');
      if (!currentItemForModal.options || currentItemForModal.options.length === 0) {
        container.innerHTML = `<p class="text-xs text-slate-400 italic">No extra options needed for this item.</p>`;
        return;
      }

      container.innerHTML = currentItemForModal.options.map(opt => {
        if (opt.type === 'select') {
          return `
            <div>
              <label class="block font-black text-slate-700 text-xs mb-2">${opt.title}</label>
              <div class="grid grid-cols-2 gap-2.5">
                ${opt.choices.map(choice => {
                  const isSelected = selectedModalOptions[opt.key]?.name === choice.name;
                  return `
                    <button type="button" onclick="selectOptionRadio('${opt.key}', '${choice.name}', ${choice.price})" class="p-2.5 border-2 rounded-2xl text-left text-xs flex justify-between items-center transition ${isSelected ? 'border-chowking-red bg-red-50 text-chowking-red font-black shadow-sm' : 'border-slate-200 hover:border-slate-300 text-slate-600 font-semibold'}">
                      <span>${choice.name}</span>
                      <span class="text-[10px] text-slate-400 font-bold">${choice.price > 0 ? `+₱${choice.price}` : ''}</span>
                    </button>
                  `;
                }).join('')}
              </div>
            </div>
          `;
        } else if (opt.type === 'checkbox') {
          return `
            <div>
              <label class="block font-black text-slate-700 text-xs mb-2">${opt.title}</label>
              <div class="space-y-2">
                ${opt.choices.map(choice => {
                  const isChecked = (selectedModalOptions[opt.key] || []).some(c => c.name === choice.name);
                  return `
                    <button type="button" onclick="toggleOptionCheckbox('${opt.key}', '${choice.name}', ${choice.price})" class="w-full p-2.5 border-2 rounded-2xl text-left text-xs flex justify-between items-center transition ${isChecked ? 'border-chowking-red bg-red-50 text-chowking-red font-black shadow-sm' : 'border-slate-200 hover:border-slate-300 text-slate-600 font-semibold'}">
                      <div class="flex items-center gap-2.5">
                        <i class="fa-solid ${isChecked ? 'fa-square-check text-chowking-red text-base' : 'fa-square text-slate-300 text-base'}"></i>
                        <span>${choice.name}</span>
                      </div>
                      <span class="text-[10px] text-slate-500 font-bold">${choice.price > 0 ? `+₱${choice.price}` : ''}</span>
                    </button>
                  `;
                }).join('')}
              </div>
            </div>
          `;
        }
      }).join('');
    }

    function selectOptionRadio(key, choiceName, price) {
      selectedModalOptions[key] = { name: choiceName, price: price };
      renderModalOptions();
      updateModalPrice();
    }

    function toggleOptionCheckbox(key, choiceName, price) {
      if (!selectedModalOptions[key]) selectedModalOptions[key] = [];
      const index = selectedModalOptions[key].findIndex(c => c.name === choiceName);
      if (index > -1) {
        selectedModalOptions[key].splice(index, 1);
      } else {
        selectedModalOptions[key].push({ name: choiceName, price: price });
      }
      renderModalOptions();
      updateModalPrice();
    }

    function adjustModalQty(delta) {
      modalQuantity = Math.max(1, modalQuantity + delta);
      document.getElementById('modalQtyDisplay').innerText = modalQuantity;
      updateModalPrice();
    }

    function calculateSingleItemPrice() {
      let base = currentItemForModal.price;
      Object.keys(selectedModalOptions).forEach(k => {
        const val = selectedModalOptions[k];
        if (Array.isArray(val)) {
          val.forEach(v => base += v.price);
        } else if (val && val.price) {
          base += val.price;
        }
      });
      return base;
    }

    function updateModalPrice() {
      const total = calculateSingleItemPrice() * modalQuantity;
      document.getElementById('modalFinalPrice').innerText = `₱${total.toFixed(2)}`;
    }

    function confirmAddToCart() {
      const notes = document.getElementById('modalNotes').value.trim();
      const unitPrice = calculateSingleItemPrice();

      let summaryArr = [];
      Object.keys(selectedModalOptions).forEach(k => {
        const val = selectedModalOptions[k];
        if (Array.isArray(val) && val.length > 0) {
          summaryArr.push(val.map(v => v.name).join(', '));
        } else if (val && val.name) {
          summaryArr.push(val.name);
        }
      });
      if (notes) summaryArr.push(`Note: ${notes}`);

      const cartItem = {
        cartItemId: Date.now(),
        itemId: currentItemForModal.id,
        name: currentItemForModal.name,
        unitPrice: unitPrice,
        qty: modalQuantity,
        optionsSummary: summaryArr.join(' | ') || 'Standard'
      };

      cart.push(cartItem);
      updateCartUI();
      closeCustomizationModal();
    }

    function updateCartUI() {
      const cartList = document.getElementById('cartItemList');
      const countBadge = document.getElementById('cartCountBadge');
      const btnCheckout = document.getElementById('btnProceedCheckout');

      const totalItemsCount = cart.reduce((acc, i) => acc + i.qty, 0);
      const subtotal = cart.reduce((acc, i) => acc + (i.unitPrice * i.qty), 0);

      countBadge.innerText = `${totalItemsCount} item${totalItemsCount === 1 ? '' : 's'}`;
      document.getElementById('subtotalPrice').innerText = `₱${subtotal.toFixed(2)}`;
      document.getElementById('totalPrice').innerText = `₱${subtotal.toFixed(2)}`;

      if (cart.length === 0) {
        cartList.innerHTML = `<div class="py-10 text-center text-slate-400 italic">Your tray is empty.<br>Tap a delicious item to add!</div>`;
        btnCheckout.disabled = true;
        btnCheckout.className = "w-full bg-slate-200 text-slate-400 font-extrabold py-3.5 rounded-2xl uppercase text-xs tracking-wider flex items-center justify-center gap-2 cursor-not-allowed shadow-none";
        return;
      }

      btnCheckout.disabled = false;
      btnCheckout.className = "w-full bg-chowking-red hover:bg-chowking-darkred text-white font-black py-3.5 rounded-2xl shadow-lg uppercase text-xs tracking-wider flex items-center justify-center gap-2 transition cursor-pointer active:scale-95";

      cartList.innerHTML = cart.map(item => `
        <div class="py-3 flex justify-between items-start gap-2.5">
          <div class="flex-1">
            <h5 class="font-extrabold text-slate-800 text-xs">${item.name}</h5>
            <p class="text-[10px] text-slate-400 leading-tight mt-0.5">${item.optionsSummary}</p>
            <div class="text-[11px] font-black text-chowking-red mt-1">
              ₱${(item.unitPrice * item.qty).toFixed(2)}
            </div>
          </div>
          <div class="flex items-center gap-1 bg-slate-100 rounded-xl p-1 border border-slate-200 shadow-inner">
            <button onclick="changeCartQty(${item.cartItemId}, -1)" class="w-6 h-6 flex items-center justify-center font-black text-slate-700 hover:bg-white rounded-lg text-xs transition">-</button>
            <span class="w-5 text-center font-black text-xs text-slate-800">${item.qty}</span>
            <button onclick="changeCartQty(${item.cartItemId}, 1)" class="w-6 h-6 flex items-center justify-center font-black text-slate-700 hover:bg-white rounded-lg text-xs transition">+</button>
          </div>
        </div>
      `).join('');
    }

    function changeCartQty(cartItemId, delta) {
      const idx = cart.findIndex(i => i.cartItemId === cartItemId);
      if (idx > -1) {
        cart[idx].qty += delta;
        if (cart[idx].qty <= 0) {
          cart.splice(idx, 1);
        }
      }
      updateCartUI();
    }

    function openCheckoutModal() {
      const subtotal = cart.reduce((acc, i) => acc + (i.unitPrice * i.qty), 0);
      document.getElementById('checkoutTotalDisplay').innerText = `₱${subtotal.toFixed(2)}`;
      document.getElementById('checkoutModal').classList.remove('hidden');
    }

    function closeCheckoutModal() {
      document.getElementById('checkoutModal').classList.add('hidden');
    }

    function selectPayment(method) {
      closeCheckoutModal();
      orderQueueNumber++;
      pauseEvalTimer();

      document.getElementById('queueOrderNumber').innerText = `#${orderQueueNumber}`;
      document.getElementById('diningOptionResult').innerText = orderType;
      
      document.getElementById('screenMenu').classList.add('hidden');
      document.getElementById('screenSuccess').classList.remove('hidden');
    }

    function toggleEvaluatorPanel() {
      const drawer = document.getElementById('evaluatorDrawer');
      drawer.classList.toggle('hidden');
    }

    function startEvalTimer() {
      if (timerInterval) clearInterval(timerInterval);
      timerStartTime = Date.now() - elapsedTime;
      timerInterval = setInterval(() => {
        elapsedTime = Date.now() - timerStartTime;
        const totalSeconds = Math.floor(elapsedTime / 1000);
        const mins = String(Math.floor(totalSeconds / 60)).padStart(2, '0');
        const secs = String(totalSeconds % 60).padStart(2, '0');
        const ms = String(Math.floor((elapsedTime % 1000) / 100));
        document.getElementById('evalTimer').innerText = `${mins}:${secs}.${ms}`;
      }, 100);
    }

    function pauseEvalTimer() {
      if (timerInterval) {
        clearInterval(timerInterval);
        timerInterval = null;
      }
    }

    function resetEvalTimer() {
      pauseEvalTimer();
      elapsedTime = 0;
      document.getElementById('evalTimer').innerText = "00:00.0";
    }

    function setRating(stars) {
      currentRating = stars;
      const starEls = document.querySelectorAll('#starRating i');
      starEls.forEach((el, idx) => {
        if (idx < stars) {
          el.className = "fa-solid fa-star cursor-pointer text-chowking-yellow";
        } else {
          el.className = "fa-regular fa-star cursor-pointer text-slate-500";
        }
      });
    }

    function saveEvaluationLog() {
      const evaluatorName = document.getElementById('evaluatorName').value.trim() || 'Guest Evaluator';
      const notes = document.getElementById('evalNotes').value.trim() || 'Smooth kiosk flow experienced.';
      const timeFormatted = document.getElementById('evalTimer').innerText;

      const log = {
        name: evaluatorName,
        time: timeFormatted,
        rating: currentRating,
        notes: notes
      };

      evaluationLogs.push(log);
      renderEvalLogs();

      document.getElementById('evalNotes').value = '';
      resetEvalTimer();
    }

    function renderEvalLogs() {
      document.getElementById('logCount').innerText = evaluationLogs.length;
      const listContainer = document.getElementById('evalLogsList');
      listContainer.innerHTML = evaluationLogs.map(l => `
        <div class="bg-slate-800 p-2 rounded-xl border border-slate-700/80 shadow-sm">
          <div class="flex justify-between font-black text-chowking-yellow">
            <span>${l.name}</span>
            <span>⏱️ ${l.time} | ⭐ ${l.rating}/5</span>
          </div>
          <p class="text-slate-300 text-[10px] mt-1">${l.notes}</p>
        </div>
      `).join('');
    }
  </script>
</body>
</html>