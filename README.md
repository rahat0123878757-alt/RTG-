<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RTG Symbol Hub | Developed by Rahat</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background: #0f172a;
            color: #f8fafc;
        }
        .gaming-font {
            font-family: 'Orbitron', sans-serif;
        }
        .symbol-card {
            background: rgba(30, 41, 59, 0.7);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        .symbol-card:hover {
            transform: translateY(-5px);
            border-color: #3b82f6;
            box-shadow: 0 0 20px rgba(59, 130, 246, 0.4);
            background: #1e293b;
        }
        .symbol-card:active {
            transform: scale(0.9);
        }
        #toast {
            visibility: hidden;
            min-width: 250px;
            background-color: #3b82f6;
            color: #fff;
            text-align: center;
            border-radius: 8px;
            padding: 16px;
            position: fixed;
            z-index: 1000;
            left: 50%;
            bottom: 30px;
            transform: translateX(-50%);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        #toast.show {
            visibility: visible;
            animation: fadein 0.5s, fadeout 0.5s 2.5s;
        }
        @keyframes fadein { from {bottom: 0; opacity: 0;} to {bottom: 30px; opacity: 1;} }
        @keyframes fadeout { from {bottom: 30px; opacity: 1;} to {bottom: 0; opacity: 0;} }
        
        /* Custom scrollbar */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #0f172a; }
        ::-webkit-scrollbar-thumb { background: #3b82f6; border-radius: 10px; }
    </style>
</head>
<body>

    <!-- Header Section -->
    <div class="relative py-12 px-6 text-center bg-gradient-to-b from-blue-900/20 to-transparent">
        <h1 class="gaming-font text-4xl md:text-6xl font-bold text-blue-500 mb-2 tracking-widest uppercase">RTG Symbol Hub</h1>
        <p class="text-gray-400 text-lg">Gaming Nickname & Esports Icon Collection</p>
        <div class="mt-6 flex justify-center">
            <input type="text" id="searchInput" placeholder="Search Symbols (e.g. cross, wing, star)..." 
                   class="w-full max-w-xl p-4 rounded-full bg-slate-800 border border-slate-700 focus:outline-none focus:ring-2 focus:ring-blue-500 text-white shadow-2xl">
        </div>
    </div>

    <!-- Symbols Sections -->
    <div id="mainContainer" class="max-w-7xl mx-auto px-6 pb-24">
        <!-- Symbols will be loaded here by JavaScript -->
    </div>

    <!-- Footer Section -->
    <footer class="bg-slate-900 py-10 border-t border-slate-800 text-center">
        <h2 class="gaming-font text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-400 to-purple-500">
            DEVELOPED BY RTG (Rahat)
        </h2>
        <p class="text-gray-500 mt-2">© 2024 RTG Esports. All Rights Reserved.</p>
    </footer>

    <div id="toast">Symbol Copied to Clipboard!</div>

    <script>
        const symbolData = {
            "Elite & Pro Tags": "々 〆 彡 ϟ ⚡ 亗 〆 ⚔ ☠ ☢ ☣ ☤ ☥ ☦ ☧ ☨ ☩ ☪ ☫ ☬ ☮ ☯ ☸ ☽ ☾ ♕ ♔ ♖ ♗ ♘ ♙ ♚ ♛ ♜ ♝ ♞ ♟ ⚖ ⚙ ⚗ ⛓ ⛏ ⚒ ⚑ ⚐ ♆ 🔱 ⚕ ⚛ 🕉 ✡ ☸ 卍 卐 ❂ ❃ ❉ ❈ ⧖ ⧗ ⌬ ⏖ ⏗ ⏘ ⏙ ⏚ ⏛ 元 亢 匚 卂 乇 丂 卄 丨 丁 ҩ 乙 乚 ム ㄖ ㄩ 丂 ㄒ ㄖ 爪 爪 卂 几 ᗪ 尺 Ҝ 乃 ㄚ 工",
            "Advanced Wings & Arrows": "← ↑ → ↓ ↔ ↕ ↖ ↗ ↘ ↙ ↚ ↛ ↜ ↝ ↞ ↟ ↠ ↡ ↢ ↣ ↤ ↥ ↦ ↧ ↨ ↩ ↪ ↫ ↬ ↭ ↮ ↯ ↰ ↱ ↲ ↳ ↴ ↵ ↶ ↷ ↸ ↹ ↺ ↻ ↼ ↽ ↾ ↿ ⇀ ⇁ ⇂ ⇃ ⇄ ⇅ ⇆ ⇇ ⇈ ⇉ ⇊ ⇋ ⇌ ⇍ ⇎ ⇏ ⇐ ⇑ ⇒ ⇓ ⇔ ⇕ ⇖ ⇗ ⇘ ⇙ ⇚ ⇛ ⇜ ⇝ ⇞ ⇟ ⇠ ⇡ ⇢ ⇣ ⇤ ⇥ ⇦ ⇧ ⇨ ⇩ ⇪ ⇫ ⇬ ⇭ ⇮ ⇯ ⇰ ⇱ ⇲ ⇳ ⇴ ⇵ ⇶ ⇷ ⇸ ⇹ ⇺ ⇻ ⇼ ⇽ ⇾ ⇿ ⟰ ⟱ ⟲ ⟳ ⟴ ⟵ ⟶ ⟷ ⟸ ⟹ ⟺ ⟻ ⟼ ⟽ ⟾ ⟿ ➔ ➘ ➙ ➚ ➛ ➜ ➝ ➞ ➟ ➠ ➡ ➢ ➣ ➤ ➥ ➦ ➧ ➨ ➩ ➪ ➫ ➬ ➭ ➮ ➯ ➱ ➲ ➳ ➴ ➵ ➶ ➷ ➸ ➹ ➺ ➻ ➼ ➽ ➾ ➴ ➵ ➶ ➷ ➸ ➹ ➺ ➻ ➼ ➽ ➾ ⛵ ⚓ ✈ ⛴ ⛽ ⛰ ⛵ ⚓ ✈ ⛴ ⛽ ⛰",
            "Frames, Boxes & Borders": "「 」 『 』 【 】 〖 〗 〚 〛 ﹙ ﹚ ﹛ ﹜ ﹝ ﹞ ₍ ₎ ⁽ ⁾ 〈 〉 《 》 〔 〕 〘 〙 ⟨ ⟩ ⟪ ⟫ ⦗ ⦘ ⟬ ⟭ ⟮ ⟯ ⦃ ⦄ ⦅ ⦆ ⦇ ⦈ ⦉ ⦊ ⦋ ⦌ ⦍ ⦎ ⦏ ⦐ ⦑ ⦒ ⦓ ⦔ ⦕ ⦖ ⧘ ⧙ ⧚ ⧛ ⧼ ⧽ ⧾ ⧿ ⌀ ⌂ ⌃ ⌄ ⌅ ⌆ ⌇ ⌈ ⌉ ⌊ ⌋ ⌌ ⌍ ⌎ ⌏ ⌐ ⌑ ⌒ ⌓ ⌔ ⌕ ⌖ ⌗ ⌘ ⌙ ⌚ ⌛ ⌜ ⌝ ⌞ ⌟ ⌠ ⌡ ⌢ ⌣ ⌤ ⌥ ⌦ ⌧ ⌨ 〈 〉 ⌫ ⌬ ⌭ ⌮ ⌯ ⌰ ⌱ ⌲ ⌳ ⌴ ⌵ ⌶ ⌷ ⌸ ⌹ ⌺ ⌻ ⌼ ⌽ ⌾ ⌿ ⍀ ⍁ ⍂ ⍃ ⍄ ⍅ ⍆ ⍇ ⍈ ⍉ ⍊ ⍋ ⍌ ⍍ ⍎ ⍏ ⍐ ⍑ ⍒ ⍓ ⍔ ⍕ ⍖ ⍗ ⍘ ⍙ ⍚ ⍛ ⍜ ⍝ ⍞ ⍟ ⍠ ⍡ ⍢ ⍣ ⍤ ⍥ ⍦ ⍧ ⍨ ⍩ ⍪ ⍫ ⍬ ⍭ ⍮ ⍯ ⍰ ⍱ ⍲ ⍳ ⍴ ⍵ ⍶ ⍷ ⍸ ⍹ ⍺ ⍻ ⍼ ⍽ ⍾ ⍿",
            "Modern Geometry & Tech": "∆ ∇ ∁ ∂ ∃ ∄ ∅ ∈ ∉ ∊ ∋ ∌ ∍ ∎ ∏ ∐ ∑ − ∓ ∔ ∕ ∖ ∗ ∘ ∙ √ ∛ ∜ ∝ ∞ ∟ ∠ ∡ ∢ ∥ ∦ ∧ ∨ ∩ ∪ ∫ ∬ ∭ ∮ ∯ ∰ ∱ ∲ ∳ ∴ ∵ ∶ ∷ ∸ ∹ ∺ ∻ ∼ ∽ ∾ ∿ ≀ ≁ ≂ ≃ ≄ ≅ ≆ ≇ ≈ ≉ ≊ ≋ ≌ ≍ ≎ ≏ ≐ ≑ ≒ ≓ ≔ ≕ ≖ ≗ ≘ ≙ ≚ ≛ ≜ ≝ ≞ ≟ ≠ ≡ ≢ ≣ ≤ ≥ ≦ ≧ ≨ ≩ ≪ ≫ ≬ ≭ ≮ ≯ ≰ ≱ ≲ ≳ ≴ ≵ ≶ ≷ ≸ ≹ ≺ ≻ ≼ ≽ ≾ ≿ ⊀ ⊁ ⊂ ⊃ ⊄ ⊅ ⊆ ⊇ ⊈ ⊉ ⊊ ⊋ ⊌ ⊍ ⊎ ⊏ ⊐ ⊑ ⊒ ⊓ ⊔ ⊕ ⊖ ⊗ ⊘ ⊙ ⊚ ⊛ ⊜ ⊝ ⊞ ⊟ ⊠ ⊡ ⊢ ⊣ ⊤ ⊥ ⊦ ⊧ ⊨ ⊩ ⊪ ⊫ ⊬ ⊭ ⊮ ⊯ ⊰ ⊱ ⊲ ⊳ ⊴ ⊵ ⊶ ⊷ ⊸ ⊹ ⊺ ⊻ ⊼ ⊽ ⊾ ⊿ ⋀ ⋁ ⋂ ⋃ ⋄ ⋅ ⋆ ⋇ ⋈ ⋉ ⋊ ⋋ ⋌ ⋍ ⋎ ⋏ ⋐ ⋑ ⋒ ⋓ ⋔ ⋕ ⋖ ⋗ ⋘ ⋙ ⋚ ⋛ ⋜ ⋝ ⋞ ⋟ ⋠ ⋡ ⋢ ⋣ ⋤ ⋥ ⋦ ⋧ ⋨ ⋩ ⋪ ⋫ ⋬ ⋭ ⋮ ⋯ ⋰ ⋱ ⨯  ⌘ ⌥ ⌃ ⇧ ⌫ ⌦ ⏎ ⏏ ⠁ ⠂ ⠃ ⠄ ⠅ ⠆ ⠇ ⠈ ⠉ ⠊ ⠋ ⠌ ⠍ ⠎ ⠏ ⠐ ⠑ ⠒ ⠓ ⠔ ⠕ ⠖ ⠗ ⠘ ⠙ ⠚ ⠛ ⠜ ⠝ ⠞ ⠟ ⠠ ⠡ ⠢ ⠣ ⠤ ⠥ ⠦ ⠧ ⠨ ⠩ ⠪ ⠫ ⠬ ⠭ ⠮ ⠯ ⠰ ⠱ ⠲ ⠳ ⠴ ⠵ ⠶ ⠷ ⠸ ⠹ ⠺ ⠻ ⠼ ⠽ ⠾ ⠿",
            "Stars, Hearts & Nature": "★ ☆ ✡ ✦ ✧ ✩ ✪ ✫ ✬ ✭ ✮ ✯ ✰ ✨ ❇ ❈ ❉ ❊ ❋ ✱ ✲ ✳ ✴ ✵ ✶ ✷ ✸ ✹ ✺ ✻ ✼ ✽ ✾ ✿ ❀ ❁ ❂ ❃ ❄ ❅ ❆ ☘ 🍀 🍁 🍂 🍃 🌺 🌻 🌹 🌷 🌼 🌸 ☸ ☯ ☮ ☦ ☧ ☨ ☩ ☪ ☫ ☬ ☮ ☯ ♡ 💖 💗 💓 💔 💟 ❣ 🖤 🤍 🤎 💜 💙 💚 💛 🧡 ❤️ 🖤 🩶 🤍 ☀ ☁ ☂ ☃ ☄ ☼ ☽ ☾ ☁ ⚡ ❄ ♨ ⚘ ☘ ❀ ❂ ❃ ❄ ❅ ❆ ❇ ❈ ❉ ❊ ❋",
            "Misc & Blocks": "▀   ▂ ▃ ▄ ▅ ▆ ▇ █ ▉ ▊ ▋ ▌ ▍ ▎ ▏ ▐ ░ ▒ ▓ ▔ ▕ ▖ ▗ ▘ ▙ ▚ ▛ ▜ ▝ ▞ ▟ ■ □ ▢ ▣ ▤ ▥ ▦ ▧ ▨ ▩ ▪ ▫ ▬ ▭ ▮ ▯ ▰ ▱ ◆ ◇ ◈ ◉ ◊ ○ ◌ ◍ ◎ ● ◐ ◑ ◒ ◓ ◔ ◕ ◖ ◗ ◘ ◙ ◚ ◛ ◜ ◝ ◞ ◟ ◠ ◡ ◢ ◣ ◤ ◥ ◦ ◧ ◨ ◩ ◪ ◫ ◬ ◭ ◮ ◯ ◰ ◱ ◲ ◳ ◴ ◵ ◶ ◷ ◸ ◹ ◺ ◻ ◼ ◽ ◾ ◿ ⚀ ⚁ ⚂ ⚃ ⚄ ⚅ ⚆ ⚇ ⚈ ⚉ ⚊ ⚋ ⚌ ⚍ ⚎ ⚏ ⚐ ⚑ ⚒ ⚓ ⚔ ⚕ ⚖ ⚗ ⚙ ⚚ ⚛ ⛈ ⚝ ⚞ ⚟ ⚠ ⚡ ⚪ ⚫ ⚬ ⚭ ⚮ ⚯ ⚰ ⚱ ⚲ ⚳ ⚴ ⚵ ⚶ ⚷ ⚸ ⚹ ⚺ ⚻ ⚼ ⚽ ⚾ ⚿ ⛀ ⛁ ⛂ ⛃ ⛄ ⛅ ⛈ ⛱ ⛲ ⛳ ⛴ ⛵ ⛶ ⛷ ⛸ ⛹ ⛺ ⛽ ⛎ ⛏ ⛾ ⛿ ⟁ ⟐ ⟑ ⟒ ⟓ ⟔ ⟕ ⟖ ⟗ ⟘ ⟙ ⟚ ⟛ ⟜ ⟝ ⟞ ⟟ ⟠ ⟡ ⟢ ⟣ ⟤ ⟥ ⟦ ⟧ ⟨ ⟩ ⟪ ⟫ ⟬ ⟭ ⟮ ⟯ ⟰ ⟱ ⟲ ⟳ ⟴ ⟵ ⟶ ⟷ ⟸ ⟹ ⟺ ⟻ ⟼ ⟽ ⟾ ⟿"
        };

        const container = document.getElementById('mainContainer');
        const toast = document.getElementById('toast');

        function showToast() {
            toast.classList.add('show');
            setTimeout(() => { toast.classList.remove('show'); }, 3000);
        }

        function copy(text) {
            const el = document.createElement('textarea');
            el.value = text;
            document.body.appendChild(el);
            el.select();
            document.execCommand('copy');
            document.body.removeChild(el);
            showToast();
        }

        // Generate Categories
        function renderSymbols() {
            container.innerHTML = '';
            for (const [category, symbols] of Object.entries(symbolData)) {
                const symArr = symbols.split(' ');
                
                const section = document.createElement('div');
                section.className = 'mt-12';
                section.innerHTML = `
                    <h3 class="gaming-font text-xl text-blue-400 mb-6 flex items-center">
                        <span class="inline-block w-8 h-1 bg-blue-500 mr-3 rounded"></span>
                        ${category} (${symArr.length})
                    </h3>
                    <div class="grid grid-cols-5 sm:grid-cols-8 md:grid-cols-10 lg:grid-cols-12 gap-3">
                        ${symArr.map(s => `
                            <div class="symbol-card p-4 text-center rounded-xl text-2xl" onclick="copy('${s}')">
                                ${s}
                            </div>
                        `).join('')}
                    </div>
                `;
                container.appendChild(section);
            }
        }

        // Search Filter
        document.getElementById('searchInput').addEventListener('input', (e) => {
            const term = e.target.value.toLowerCase();
            document.querySelectorAll('.symbol-card').forEach(card => {
                if (card.innerText.toLowerCase().includes(term)) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        });

        renderSymbols();
    </script>
</body>
</html>
