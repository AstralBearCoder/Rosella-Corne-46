# Rosella-Corne-46

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>40 to 46-key with Rosella Layout</title>
    <style>
        :root {
            --bg-page: #0a0a0a;
            --bg-card: #121212;
            --bg-inset: #1a1a1a;
            --accent-nav: #e83;
            --accent-sym: #55a;
            --accent-acc: #008523;
            --text-main: #eee;
            --key-fill: #222;
            --stroke: #333;

            /* Couleurs doigts Ortho (Léger) */
            --f-pinky: rgba(255, 100, 100, 0.12);
            --f-ring: rgba(255, 200, 100, 0.12);
            --f-middle: rgba(100, 255, 100, 0.12);
            --f-index: rgba(100, 150, 255, 0.18);
        }

        body {
            background-color: var(--bg-page);
            color: #eee;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            margin: 0;
            padding: 40px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .intro-card {
            background: var(--bg-card);
            border-radius: 20px;
            padding: 35px;
            width: 100%;
            max-width: 1200px;
            margin: 0 auto 50px auto;
            border: 1px solid #222;
            box-shadow: 0 10px 40px rgba(0,0,0,0.6);
            box-sizing: border-box;
        }

        .header-top { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 30px; }
        .header-top h1 { margin: 0; font-size: 2.2rem; font-weight: 600; letter-spacing: -1px; }
        .header-top p { margin: 5px 0 0 0; color: #999; font-size: 1.1rem; }

        .badge {
            background: var(--accent-nav);
            color: #000;
            padding: 8px 20px;
            border-radius: 6px;
            font-weight: 800;
            font-size: 0.8rem;
            text-transform: uppercase;
        }

        .dashboard-main {
            display: grid;
            grid-template-columns: 1fr 1.5fr;
            gap: 40px;
            border-top: 1px solid #222;
            padding-top: 30px;
            align-items: center;
        }

        .stats-box table { width: 100%; border-collapse: collapse; }
        .stats-box th { text-align: left; color: #aaa; font-size: 0.75rem; text-transform: uppercase; padding-bottom: 15px; }
        .stats-box td { padding: 12px 0; border-bottom: 1px solid #222; font-size: 1rem; }
        .lang { color: var(--accent-nav); font-weight: 500; }

        .ortho-box { background: var(--bg-inset); padding: 25px; border-radius: 12px; }
        .ortho-title { font-size: 0.8rem; color: #aaa; text-transform: uppercase; margin-bottom: 20px; display: block; text-align: center; font-weight: 600; }
        .ortho-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr) 25px repeat(5, 1fr);
            gap: 6px;
            max-width: 500px;
            margin: 0 auto;
        }
        .ortho-key {
            aspect-ratio: 1;
            background: #252525;
            border: 1px solid #333;
            display: flex; align-items: center; justify-content: center;
            font-size: 0.9rem; color: #ccc; border-radius: 4px;
        }
        .ortho-gap { grid-column: 6; }

        .f-p { background-color: var(--f-pinky); border-color: rgba(255,100,100,0.3); }
        .f-r { background-color: var(--f-ring); border-color: rgba(255,200,100,0.3); }
        .f-m { background-color: var(--f-middle); border-color: rgba(100,255,100,0.3); }
        .f-i { background-color: var(--f-index); border-color: rgba(100,150,255,0.4); }

        .kb-section {
            background: var(--bg-card);
            padding: 35px;
            border-radius: 15px;
            border: 1px solid #1a1a1a;
        }
        .kb-section.full { width: 100%; max-width: 1200px; margin-bottom: 60px; box-sizing: border-box; }

        .layers-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            width: 100%;
            max-width: 1200px;
            box-sizing: border-box;
        }

        .layer-title {
            font-size: 1.1rem;
            color: var(--text-main);
            margin-bottom: 30px;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-align: center;
            border-bottom: 1px solid #222;
            padding-bottom: 15px;
            font-weight: 600;
        }

        /* --- SVG STYLING --- */
        svg { width: 100%; height: auto; }
        rect { fill: var(--key-fill); stroke: var(--stroke); stroke-width: 0.6px; }
        text { fill: #888; font-size: 17px; text-anchor: middle; dominant-baseline: middle; }

        .specialKey text { font-size: 18px; fill: #aaa; }
        .col_mid_L text, .col_mid_R text { font-size: 11px; fill: #666; }

        /* Couleurs permanentes Calques */
        #nav-key rect { fill: var(--accent-nav); stroke: none; }
        #nav-key text { fill: #000 !important; font-weight: 500; }
        #sym-key rect { fill: var(--accent-sym); stroke: none; }
        #sym-key text { fill: #fff !important; font-weight: 500; }
        #acc-key rect { fill: var(--accent-acc); stroke: none; }
        #acc-key text { fill: #fff !important; }

        /* Positions */
        #left  { transform: translate(4px, 15px); }
        #right { transform: translate(600px, 15px); }

        .col_L { transform: translate(0px, 22.5px); }
        .col_1 { transform: translate(60px, 22.5px); }
        .col_2 { transform: translate(120px, 7.5px); }
        .col_3 { transform: translate(180px, 0.0px); }
        .col_4 { transform: translate(240px, 7.5px); }
        .col_5 { transform: translate(300px, 15.0px); }
        .col_mid_L { transform: translate(360px, 37.5px); }
        .col_mid_R { transform: translate(-60px, 37.5px); }
        .col_6 { transform: translate(0px, 15.0px); }
        .col_7 { transform: translate(60px, 7.5px); }
        .col_8 { transform: translate(120px, 0.0px); }
        .col_9 { transform: translate(180px, 7.5px); }
        .col_0 { transform: translate(240px, 22.5px); }
        .col_R { transform: translate(300px, 22.5px); }

        .thb_3 { transform: translate(210px, 190px); }
        .thb_4 { transform: translate(280px, 191px); }
        .thb_5 { transform: translate(360px, 182px); }
        .thb_4 g { transform: rotate(12deg); }
        .thb_5 g { transform: rotate(24deg); }
        .thb_8 { transform: translate(90px, 190px); }
        .thb_7 { transform: translate(20px, 201px); }
        .thb_6 { transform: translate(-57px, 201px); }
        .thb_7 g { transform: rotate(-12deg); }
        .thb_6 g { transform: rotate(-24deg); }

        /* --- PREVIEW LAYERS (2x2) --- */
        .target text { font-size: 20px; }
        .sym { fill: var(--accent-sym); font-size: 15px; }
        .acc { fill: var(--accent-acc); font-size: 18px; transform: translateY(-22px); }
        .nav { display: none; fill: var(--accent-nav); font-size: 22px; }

        /* 1. Normal - Lettre seule centrée */
        .layer-normal .sym, .layer-normal .acc, .layer-normal .nav { display: none; }
        .layer-normal .level2 { transform: translate(13px, 5px); font-size: 24px; fill: #ddd; }
        .layer-normal .level1 ~ .level2 { transform: translate(13px, -4px); font-size: 18px; }
        .layer-normal .level1 { transform: translate(13px, -10px); font-size: 18px; fill: #888; }

        /* 2. Accents centrés */
        .layer-acc .level1, .layer-acc .level2, .layer-acc .sym, .layer-acc .nav { display: none; }
        .layer-acc .acc { transform: translate(-12px, -13px); font-size: 24px; }

        /* 3. Symbols centrés */
        .layer-sym .level1, .layer-sym .level2, .layer-sym .acc, .layer-sym .nav { display: none; }
        .layer-sym .sym { transform: translate(-12px, -13px); font-size: 24px; }

        /* 4. Navigation */
        .layer-nav .sym, .layer-nav .acc, .layer-nav .level1, .layer-nav .level2 { display: none; }
        .layer-nav .nav { display: block; }

        /* SPECIFIQUE TOUCHE 0 / ETOILE DANS NAV */
        .layer-nav #acc-key rect { fill: var(--key-fill) !important; stroke: var(--stroke) !important; }
        .layer-nav #acc-key .acc-star { display: block !important; fill: var(--accent-acc) !important; font-size: 14px; transform: translateY(-15px); }
        .layer-nav #acc-key .nav { fill: var(--accent-nav) !important; transform: translateY(5px); font-weight: bold; }

    </style>
</head>
<body>

    <div class="intro-card">
        <div class="header-top">
            <div>
                <h1>40 to 46-key Corne Rosella Layout</h1>
                <p>Layout optimised for 50/50 French & English typing + Spanish compatible<br><i>Corne keyboard, Rosella Layout by GalileoBlue, globally inspired by ErgoL by NuclearSquid</i></p>
            </div>
            <div class="badge">40-46 key Corne Layout</div>
        </div>

        <div class="dashboard-main">
            <div class="stats-box">
                <table>
                    <thead><tr><th>Language</th><th>&nbsp;SBS</th><th>&nbsp;SFS</th></tr></thead>
                    <tbody>
                        <tr><td class="lang">English (Cmini | Mt-Quotes)</td><td>0.94%</td><td>4.83%</td></tr>
                        <tr><td class="lang">Français (Cmini | French)</td><td>1.19%</td><td>4.63%</td></tr>
                        <tr><td class="lang">Español (Cmini | Spanish)</td><td>1.47%</td><td>7.76%</td></tr>
                    </tbody>
                </table>
            </div>
            <div class="ortho-box">
                <span class="ortho-title"><b>Rosella </b>by GalileoBlue</span>
                <div class="ortho-grid">
                    <div class="ortho-key f-p">B</div><div class="ortho-key f-r">L</div><div class="ortho-key f-m">D</div><div class="ortho-key f-i">C</div><div class="ortho-key f-i">V</div>
                    <div class="ortho-gap"></div>
                    <div class="ortho-key f-i">X</div><div class="ortho-key f-i">'</div><div class="ortho-key f-m">O</div><div class="ortho-key f-r">U</div><div class="ortho-key f-p">Z</div>
                    <div class="ortho-key f-p">N</div><div class="ortho-key f-r">R</div><div class="ortho-key f-m">T</div><div class="ortho-key f-i">S</div><div class="ortho-key f-i">F</div>
                    <div class="ortho-gap"></div>
                    <div class="ortho-key f-i">Y</div><div class="ortho-key f-i">H</div><div class="ortho-key f-m">A</div><div class="ortho-key f-r">I</div><div class="ortho-key f-p">E</div>
                    <div class="ortho-key f-p">Q</div><div class="ortho-key f-r">J</div><div class="ortho-key f-m">M</div><div class="ortho-key f-i">G</div><div class="ortho-key f-i">W</div>
                    <div class="ortho-gap"></div>
                    <div class="ortho-key f-i">K</div><div class="ortho-key f-i">P</div><div class="ortho-key f-m">.</div><div class="ortho-key f-r">,</div><div class="ortho-key f-p">-</div>
                </div>
            </div>
        </div>
    </div>

    <!-- MAIN VIEW -->
    <div class="kb-section layer-all full">
        <div class="layer-title">All layers (except Nav)</div>
        <div id="master-svg">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1080 300">
                <g id="left">
                    <g class="col_L specialKey">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="26" y="26">⎋</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="26" y="26">↹</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="26" y="26" style="font-size:22px;">❖</text></g>
                    </g>
                    <g class="col_1">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">B</text><text x="38" y="43" class="sym">!</text><text x="26" y="26" class="nav">f2</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">N</text><text x="38" y="43" class="sym">?</text><text x="38" y="43" class="acc">ñ</text><text x="26" y="26" class="nav">↖</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">Q</text><text x="38" y="43" class="sym">~</text><text x="26" y="26" style="font-size: 15px;" class="nav">undo</text></g>
                    </g>
                    <g class="col_2">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">L</text><text x="38" y="43" class="sym">[</text><text x="38" y="43" class="acc">ó</text><text x="26" y="26" class="nav">f4</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">R</text><text x="38" y="43" class="sym">(</text><text x="38" y="43" class="acc">í</text><text x="26" y="26" class="nav">←</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">J</text><text x="38" y="43" class="sym">{</text><text x="38" y="43" class="acc">ü</text><text x="26" y="26" style="font-size: 15px;" class="nav">cut</text></g>
                    </g>
                    <g class="col_3">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">D</text><text x="38" y="43" class="sym">]</text><text x="38" y="43" class="acc">ú</text><text x="26" y="26" class="nav">↑</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">T</text><text x="38" y="43" class="sym">)</text><text x="38" y="43" class="acc">á</text><text x="26" y="26" class="nav">↓</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">M</text><text x="38" y="43" class="sym">}</text><text x="38" y="43" class="acc">ä</text><text x="26" y="26" class="nav"></text><text x="26" y="26" style="font-size: 15px;" class="nav">copy</text></g>
                    </g>
                    <g class="col_4">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">C</text><text x="38" y="43" class="sym">+</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">S</text><text x="38" y="43" class="sym">=</text><text x="38" y="43" class="acc">ç</text><text x="26" y="26" class="nav">→</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">G</text><text x="38" y="43" class="sym">*</text><text x="38" y="43" class="acc">ö</text><text x="26" y="26" style="font-size: 15px;" class="nav">paste</text></g>
                    </g>
                    <g class="col_5">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">V</text><text x="38" y="43" class="sym">×</text><text x="26" y="26" class="nav">⇞</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">F</text><text x="38" y="43" class="sym">`</text><text x="26" y="26" class="nav">⇟</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">W</text><text x="38" y="43" class="acc">æ</text></g>
                    </g>
                    <g class="col_mid_L specialKey">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="26"/><text x="26" y="26">Vol</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="6"/><text x="26" y="26">Scr</text></g>
                    </g>
                    <g class="thb_3 specialKey"><g><rect width="52" height="52" rx="5"/><text x="26" y="26" style="font-size:14px;">Ctrl</text></g></g>
                    <g class="thb_4" id="nav-key"><g><rect width="52" height="52" rx="5"/><text x="26" y="26" style="font-size:15px;">Nav</text></g></g>
                    <g class="thb_5 specialKey"><g><rect width="52" height="82" rx="5"/><text x="26" y="41">⎵</text></g></g>
                </g>
                <g id="right">
                    <g class="col_mid_R specialKey">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="26"/><text x="26" y="26">Lum</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="6"/><text x="26" y="26">Alt</text></g>
                    </g>
                    <g class="col_6">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">X</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">Y</text><text x="38" y="43" class="sym">\</text><text x="38" y="43" class="acc">œ</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">K</text></g>
                    </g>
                    <g class="col_7">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">'</text><text x="38" y="43" class="sym">&amp;</text><text x="38" y="43" class="acc">î</text><text x="26" y="26" class="nav">7</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">H</text><text x="38" y="43" class="sym">_</text><text x="38" y="43" class="acc">é</text><text x="26" y="26" class="nav">4</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">P</text><text x="38" y="43" class="sym">#</text><text x="38" y="43" class="acc">ï</text><text x="26" y="26" class="nav">1</text></g>
                    </g>
                    <g class="col_8">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">O</text><text x="38" y="43" class="sym">&lt;</text><text x="38" y="43" class="acc">ê</text><text x="26" y="26" class="nav">8</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">A</text><text x="38" y="43" class="sym">@</text><text x="38" y="43" class="acc">à</text><text x="26" y="26" class="nav">5</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="43" class="level1">:</text><text x="13" y="21" class="level2">.</text><text x="38" y="43" class="sym">|</text><text x="38" y="43" class="acc">â</text><text x="26" y="26" class="nav">2</text></g>
                    </g>
                    <g class="col_9">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">U</text><text x="38" y="43" class="sym">&gt;</text><text x="38" y="43" class="acc">ù</text><text x="26" y="26" class="nav">9</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">I</text><text x="38" y="43" class="sym">$</text><text x="38" y="43" class="acc">è</text><text x="26" y="26" class="nav">6</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="43" class="level1">,</text><text x="13" y="21" class="level2">;</text><text x="38" y="43" class="sym">€</text><text x="26" y="26" class="nav">3</text></g>
                    </g>
                    <g class="col_0">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">Z</text><text x="38" y="43" class="sym">%</text><text x="38" y="43" class="acc">û</text><text x="26" y="26" class="nav">f11</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="13" y="21" class="level2">E</text><text x="38" y="43" class="sym">"</text><text x="38" y="43" class="acc">ô</text><text x="26" y="26" class="nav">↘</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="13" y="43" class="level1">-</text><text x="13" y="21" class="level2">/</text><text x="38" y="43" class="sym">°</text><text x="38" y="43" class="acc">ë</text></g>
                    </g>
                    <g class="col_R specialKey">
                        <g transform="translate(0 0)"><rect width="52" height="52" rx="5"/><text x="26" y="26">⏎</text></g>
                        <g transform="translate(0 60)"><rect width="52" height="52" rx="5"/><text x="26" y="26">⌫</text></g>
                        <g transform="translate(0 120)"><rect width="52" height="52" rx="5"/><text x="26" y="26">⌃⇧</text></g>
                    </g>
                    <g class="thb_6 specialKey"><g><rect width="52" height="82" rx="5"/><text x="26" y="41" style="font-size:14px;">Shift</text></g></g>
                    <g class="thb_7" id="acc-key">
                        <g>
                            <rect width="52" height="52" rx="5"/>
                            <text x="26" y="26" class="acc-star">★</text>
                            <text x="26" y="26" class="nav">0</text>
                        </g>
                    </g>
                    <g class="thb_8" id="sym-key"><g><rect width="52" height="52" rx="5"/><text x="26" y="26" style="font-size:12px;">AltGr</text></g></g>
                </g>
            </svg>
        </div>
    </div>

    <!-- 2x2 GRID -->
    <div class="layers-grid">
        <div class="kb-section layer-normal">
            <div class="layer-title">1. Alpha Layer<Base></div>
            <div class="target"></div>
        </div>
        <div class="kb-section layer-acc">
            <div class="layer-title">2. Accents Layer (★)</div>
            <div class="target"></div>
        </div>
        <div class="kb-section layer-sym">
            <div class="layer-title">3. Symbols Layer (AltGr)</div>
            <div class="target"></div>
        </div>
        <div class="kb-section layer-nav">
            <div class="layer-title">4. Navigation Layer</div>
            <div class="target"></div>
        </div>
    </div>

    <script>
        const masterHTML = document.getElementById('master-svg').innerHTML;
        document.querySelectorAll('.target').forEach(el => {
            el.innerHTML = `<svg viewBox="0 0 1080 300">${masterHTML}</svg>`;
        });
    </script>
</body>
</html>
