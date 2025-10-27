# StremioBox.com
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>StremioBox - TeraBox Video Player</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f2f5; /* Light grey background */
        }
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        ::-webkit-scrollbar-thumb {
            background: #888;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #555;
        }
        /* Custom Modal for alerts */
        .custom-modal {
            z-index: 50;
        }
    </style>
</head>
<body class="min-h-screen text-gray-800">

    <!-- Navigation Bar -->
    <nav class="bg-white p-4 shadow-sm sticky top-0 z-40">
        <div class="container mx-auto flex justify-between items-center max-w-2xl">
            <div class="flex items-center space-x-2">
                <button id="logoHomeBtn" class="flex items-center space-x-2 focus:outline-none">
                    <img src="https://placehold.co/32x32/60A5FA/FFFFFF?text=S" alt="StremioBox Logo" class="w-8 h-8 rounded-full">
                    <span class="text-xl font-bold text-gray-900">StremioBox</span>
                </button>
            </div>
            <div class="flex items-center space-x-4">
                
                <a href="https://t.me/StremioBox" target="_blank" class="bg-gradient-to-r from-green-400 to-emerald-500 text-white px-4 py-2 rounded-full font-semibold hover:from-green-500 hover:to-emerald-600 transition duration-300 hidden sm:inline-block">
                    Telegram Channel
                </a>
                <button id="menuToggleButton" class="text-gray-600 hover:text-gray-900 focus:outline-none p-2 rounded-lg bg-gray-100 sm:bg-transparent">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
                </button>
            </div>
        </div>
    </nav>

    <!-- Mobile/Hidden Menu (Includes all new links) -->
    <div id="mobileMenu" class="hidden bg-white shadow-xl absolute top-[64px] left-0 right-0 z-40 border-t border-gray-200">
        <div class="container mx-auto max-w-2xl px-4 py-3 space-y-2">
            <!-- Company Section -->
            <p class="text-xs font-bold text-gray-500 uppercase pt-2">Company</p>
            <button id="homeLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">Home</button>
            <button id="aboutUsLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">About Us</button>
            <button id="privacyPolicyLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">Privacy Policy</button>
            <button id="disclaimerLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">Disclaimer</button>
            <button id="tosLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">ToS (Terms of Service)</button>

            <!-- Support Section -->
            <p class="text-xs font-bold text-gray-500 uppercase pt-4">Support</p>
            <button id="playerLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">TeraBox Video Player</button>
            <button id="contactUsLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">Contact Us</button>
            <a href="https://t.me/StremioBox" target="_blank" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium">Telegram Channel</a>
            <button id="telegramBotLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">Telegram Bot (Link)</button>

            <!-- Resources Section -->
            <p class="text-xs font-bold text-gray-500 uppercase pt-4">Resources</p>
            <button id="betaLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">Beta (Test Features)</button>
            <button id="statusLink" class="block text-gray-700 hover:bg-gray-100 p-2 rounded-lg font-medium w-full text-left">Status (System Health)</button>
        </div>
    </div>


    <main class="container mx-auto px-4 py-8 max-w-2xl relative min-h-[80vh]">

        <!-- 1. Landing Page (Home) & Features -->
        <div id="landingPageContainer" class="min-h-[70vh] flex flex-col items-center justify-center p-4 text-center">
            <div class="absolute inset-0 z-0 opacity-50 overflow-hidden rounded-lg pointer-events-none" style="background: linear-gradient(135deg, #A7F3D0 0%, #FFFFFF 50%, #E0F2F7 100%);"></div>

            <div class="relative z-10 p-6">
                <h1 class="text-4xl sm:text-5xl font-extrabold text-gray-900 leading-tight mb-12">
                    Fast, Free, Secure, <br> No Limits at <span class="text-green-600">StremioBox</span>
                </h1>

                <button id="teraboxPlayerBtn" class="bg-gray-800 hover:bg-gray-900 text-white text-xl font-semibold px-12 py-4 rounded-full shadow-xl transition duration-300 transform hover:scale-[1.02] focus:outline-none focus:ring-4 focus:ring-gray-400 focus:ring-opacity-50">
                    Terabox Video Player
                </button>
            </div>
        </div>
        <div id="featuresContainer" class="py-12 hidden">
            <h2 class="text-3xl font-bold text-center text-gray-900 mb-10">Why Choose <span class="text-green-600">StremioBox</span>?</h2>
            
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 text-center">

                <div class="p-6 bg-white rounded-xl shadow-lg transform hover:scale-[1.02] transition duration-300">
                    <div class="flex justify-center mb-4">
                        <svg class="w-12 h-12 text-green-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-900 mb-2">Fast & Free</h3>
                    <p class="text-gray-600">No speed limits or restrictions, unlike other websites.</p>
                </div>

                <div class="p-6 bg-white rounded-xl shadow-lg transform hover:scale-[1.02] transition duration-300">
                    <div class="flex justify-center mb-4">
                        <svg class="w-12 h-12 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 9l3 3m0 0l-3 3m3-3H8m13 0a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-900 mb-2">No Login Required</h3>
                    <p class="text-gray-600">Users can use our tools instantly without creating an account.</p>
                </div>

                <div class="p-6 bg-white rounded-xl shadow-lg transform hover:scale-[1.02] transition duration-300">
                    <div class="flex justify-center mb-4">
                        <svg class="w-12 h-12 text-lime-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path></svg>
                    </div>
                    <h3 class="text-xl font-bold text-gray-900 mb-2">Privacy-Focused</h3>
                    <p class="text-gray-600">No logs, no IP tracking, and files are auto-deleted after use.</p>
                </div>
            </div>
        </div>
        
        <!-- 2. Video Player UI -->
        <div id="videoPlayerUIContainer" class="hidden">
            <div class="bg-gray-800 text-white p-6 rounded-lg text-center shadow-lg">
                <h1 class="text-3xl sm:text-4xl font-extrabold mb-2">Terabox Video Player</h1>
                <p class="text-gray-300 text-lg">Join telegram for updates & more!</p>
                <a href="https://t.me/StremioBox" target="_blank" class="inline-block mt-4 bg-blue-600 hover:bg-blue-700 text-white px-6 py-3 rounded-full text-lg font-semibold transition duration-300">
                    Join Telegram
                </a>
            </div>

            <div class="bg-white p-6 rounded-lg shadow-lg mt-8">
                <label for="teraboxUrl" class="block text-gray-700 text-xl font-semibold mb-3">Terabox URL</label>
                <div class="flex flex-col sm:flex-row space-y-3 sm:space-y-0 sm:space-x-3">
                    <input type="url" id="teraboxUrl" placeholder="https://1024tera.com/..." class="flex-grow p-3 border border-gray-300 rounded-lg focus:ring-blue-500 focus:border-blue-500 text-lg text-gray-700" value="https://1024tera.com/example">
                    <button id="pasteBtn" class="bg-blue-500 hover:bg-blue-600 text-white px-5 py-3 rounded-lg font-semibold flex-shrink-0 transition duration-300">
                        <i class="fas fa-paste mr-2"></i> Paste
                    </button>
                </div>
            </div>

            <div id="videoPlayerContainer" class="hidden bg-black mt-8 rounded-lg overflow-hidden shadow-xl aspect-video relative">
                <p id="playerMessage" class="absolute inset-0 flex items-center justify-center text-white text-center p-4">
                    Video is loading... (If the URL is not a direct file link, this may fail.)
                </p>
                <video id="videoPlayer" class="w-full h-full" controls autoplay></video>
            </div>
            
            <div class="mt-8">
                <!-- NEW PREVIEW BUTTON -->
                <button id="previewVideoBtn" class="bg-orange-500 hover:bg-orange-600 text-white px-8 py-4 rounded-lg text-xl font-bold flex items-center justify-center w-full shadow-lg transition duration-300 mb-4">
                    <i class="fas fa-eye mr-3"></i> 5 Second Video Preview
                </button>
                
                <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
                    <button id="playVideoBtn" class="bg-gray-800 hover:bg-gray-900 text-white px-8 py-4 rounded-lg text-xl font-bold flex items-center justify-center w-full shadow-lg transition duration-300 sm:w-1/2">
                        <i class="fas fa-play-circle mr-3"></i> Play Video
                    </button>
                    <button id="downloadVideoBtn" class="bg-indigo-600 hover:bg-indigo-700 text-white px-8 py-4 rounded-lg text-xl font-bold flex items-center justify-center w-full shadow-lg transition duration-300 sm:w-1/2">
                        <i class="fas fa-download mr-3"></i> Download Video
                    </button>
                </div>
            </div>
        </div>
        
        <!-- 3. About Us -->
        <div id="aboutUsContainer" class="hidden bg-orange-500 text-white p-6 sm:p-8 rounded-lg shadow-xl mt-4">
            <h2 class="text-3xl font-bold text-white mb-4">About StremioBox</h2>
            <p class="mb-4 text-xl font-bold leading-relaxed">
                I AM <span class="text-white">StremioBox</span> my motive is to provide comfort in downloading videos to people.
            </p>
            <p class="mb-4 text-lg leading-relaxed">
                StremioBox is a privacy-focused online tool platform that works directly in the browser—no login, no downloads, no tracking, and fewer ads. It offers a variety of free tools. Unlike other sites, <span class="font-bold">StremioBox</span> does not store any personal data. All information is automatically deleted from the server after use.
            </p>
            <p class="text-xl font-bold mt-8">
                If you want to know more about us or have any other query:
            </p>
            <p class="text-xl font-bold mt-2">
                Contact us: <span class="text-white">StremioBox</span>
            </p>
            <a href="https://t.me/StremioBox" target="_blank" class="text-sm text-yellow-200 hover:text-yellow-100 font-semibold mt-1 inline-block">
                Join our Telegram Channel <i class="fab fa-telegram-plane ml-1"></i>
            </a>
        </div>
        
        <!-- 4. Contact Us -->
        <div id="contactUsContainer" class="hidden bg-white p-6 sm:p-8 rounded-lg shadow-xl mt-4">
            <h2 class="text-2xl font-bold text-gray-900 mb-6 border-b-2 pb-2 border-blue-500">Contact Us</h2>
            <form id="contactForm" class="space-y-6">
                <div>
                    <label for="firstName" class="block text-gray-700 font-semibold mb-1">First Name (Optional)</label>
                    <input type="text" id="firstName" placeholder="E.g. John" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-blue-500 focus:border-blue-500 text-lg text-gray-700">
                </div>
                <div>
                    <label for="emailAddress" class="block text-gray-700 font-semibold mb-1">Email Address (Optional)</label>
                    <input type="email" id="emailAddress" placeholder="E.g. john.doe@example.com" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-blue-500 focus:border-blue-500 text-lg text-gray-700">
                </div>
                <div>
                    <label for="message" class="block text-gray-700 font-semibold mb-1">Message <span class="text-red-500">*</span></label>
                    <textarea id="message" placeholder="Enter your message..." rows="4" maxlength="180" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-blue-500 focus:border-blue-500 text-lg text-gray-700" required></textarea>
                    <p class="text-right text-sm text-gray-500"><span id="charCount">0</span>/180</p>
                </div>
                <button type="submit" class="bg-orange-500 hover:bg-orange-600 text-white px-8 py-4 rounded-lg text-xl font-bold w-full shadow-lg transition duration-300">
                    Send Message
                </button>
            </form>
        </div>
        
        <!-- 5. Disclaimer -->
        <div id="disclaimerContainer" class="hidden bg-white p-6 sm:p-8 rounded-lg shadow-xl mt-4">
            <h2 class="text-2xl font-bold text-gray-900 mb-6 border-b-2 pb-2 border-green-500">Disclaimer</h2>
            <p class="mb-6 text-base leading-relaxed text-gray-700">
                <span class="font-bold">Stremiobox</span> is a free, tool-based platform designed to facilitate user-initiated processes. We do not host, endorse, or promote any specific content.
            </p>
            <p class="mb-2 text-lg font-bold">Key Points:</p>
            <ul class="list-disc list-inside space-y-2 text-gray-700 ml-4">
                <li><span class="font-bold">No Data Storage Guarantee:</span> While we aim for rapid deletion, we cannot guarantee absolute non-storage.</li>
                <li><span class="font-bold">User Responsibility:</span> Users are solely responsible for the content they access or process through our service.</li>
                <li><span class="font-bold">Prohibited Content:</span> Accessing, processing, or transmitting illegal, malicious, or copyrighted material without permission is strictly prohibited.</li>
            </ul>
            <p class="mt-8 pt-4 border-t border-gray-200 text-base italic text-gray-600">
                ~ By using Stremiobox, you agree to these terms.
            </p>
        </div>

        <!-- 6. NEW: Privacy Policy -->
        <div id="privacyPolicyContainer" class="hidden bg-white p-6 sm:p-8 rounded-lg shadow-xl mt-4">
            <h2 class="text-2xl font-bold text-gray-900 mb-6 border-b-2 pb-2 border-red-500">Privacy Policy</h2>
            <p class="mb-4 text-gray-700 text-lg font-semibold">Our Commitment to Your Privacy</p>
            <ul class="list-disc list-inside space-y-3 text-gray-700">
                <li><span class="font-bold">No Personal Data Collection:</span> We do not require registration or collect personal identifiable information (PII).</li>
                <li><span class="font-bold">No IP/Usage Logging:</span> We do not track or store your IP address or specific usage history.</li>
                <li><span class="font-bold">Temporary Data:</span> Any file data processed is automatically deleted from our server after a short period (typically 15 minutes).</li>
                <li><span class="font-bold">Cookies:</span> We use only essential, non-intrusive cookies for basic site functionality.</li>
            </ul>
            <p class="mt-6 text-gray-600 italic">For any questions about privacy, please use the Contact Us page.</p>
        </div>

        <!-- 7. NEW: Terms of Service (ToS) -->
        <div id="tosContainer" class="hidden bg-white p-6 sm:p-8 rounded-lg shadow-xl mt-4">
            <h2 class="text-2xl font-bold text-gray-900 mb-6 border-b-2 pb-2 border-purple-500">Terms of Service (ToS)</h2>
            <p class="mb-4 text-gray-700 text-lg font-semibold">Agreement to Use</p>
            <ul class="list-disc list-inside space-y-3 text-gray-700">
                <li><span class="font-bold">Acceptable Use:</span> You agree to use StremioBox only for lawful, personal, and non-commercial purposes.</li>
                <li><span class="font-bold">No Abuse:</span> You must not use the service to infringe on copyrights, upload malicious content, or conduct illegal activity.</li>
                <li><span class="font-bold">Limitation of Liability:</span> StremioBox is provided "as is." We are not liable for any damages or data loss resulting from its use.</li>
                <li><span class="font-bold">Termination:</span> We reserve the right to terminate access to any user violating these terms.</li>
            </ul>
            <p class="mt-6 text-gray-600 italic">These terms are subject to change without notice.</p>
        </div>

        <!-- 8. NEW: Telegram Bot Link -->
        <div id="telegramBotContainer" class="hidden bg-blue-100 p-6 sm:p-8 rounded-lg shadow-xl mt-4 text-center">
            <i class="fab fa-telegram-plane text-5xl text-blue-600 mb-4"></i>
            <h2 class="text-2xl font-bold text-gray-900 mb-4">Our Telegram Bot</h2>
            <p class="mb-6 text-lg text-gray-700">Get quick links, updates, and support directly through our Telegram Bot!</p>
            <a href="https://t.me/StremioBoxBot" target="_blank" class="inline-block bg-blue-600 hover:bg-blue-700 text-white px-8 py-4 rounded-full text-xl font-bold transition duration-300 shadow-md">
                Connect with the Bot
            </a>
            <p class="mt-4 text-sm text-gray-500">Note: This is a placeholder link and assumes the bot is named @StremioBoxBot.</p>
        </div>

        <!-- 9. NEW: Beta (Placeholder) -->
        <div id="betaContainer" class="hidden bg-yellow-100 p-6 sm:p-8 rounded-lg shadow-xl mt-4 text-center">
            <i class="fas fa-flask text-5xl text-yellow-600 mb-4"></i>
            <h2 class="text-2xl font-bold text-gray-900 mb-4">Beta Features</h2>
            <p class="mb-6 text-lg text-gray-700">You are in the testing area! Help us refine new features before they are fully released.</p>
            <div class="p-4 bg-yellow-50 rounded-lg 
