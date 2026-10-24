<!DOCTYPE html>
<html lang="pt-BR">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
        <title>Guilherme da Silva Lima – Engenharia Civil</title>
        <link href="https://fonts.googleapis.com/css2?family=Newsreader:opsz,wght@6..72,400;6..72,600&family=Instrument+Sans:wght@400;500;600&display=swap" rel="stylesheet">
        <style>
            :root {
                --bg: #F2F4F7;
                --sf: #FFF;
                --ink: #17212F;
                --mu: #566173;
                --ln: #D8DDE5;
                --ac: #1F4E8C;
                --soft: #E3ECF8;
                --ok: #1E7B4A;
                --late: #B3261E;
                --todo: #8A94A4;
                --danger: #B3261E;
                --serif: "Newsreader",Georgia,serif;
                --sans: "Instrument Sans",system-ui,-apple-system,"Segoe UI",sans-serif;
                box-sizing: border-box;
                padding-top: env(safe-area-inset-top,0px);
                padding-bottom: env(safe-area-inset-bottom,0px)
            }

            @media (prefers-color-scheme: dark) {
                :root:not([data-theme="light"]) {
                    --bg:#0F141C;
                    --sf: #171E2A;
                    --ink: #E6EBF3;
                    --mu: #9AA6B8;
                    --ln: #2A3446;
                    --ac: #7FB0F0;
                    --soft: #1B2A44;
                    --ok: #4FCB8A;
                    --late: #FF8A80;
                    --todo: #6F7A8C;
                    --danger: #FF8A80
                }
            }

            :root[data-theme="dark"] {
                --bg: #0F141C;
                --sf: #171E2A;
                --ink: #E6EBF3;
                --mu: #9AA6B8;
                --ln: #2A3446;
                --ac: #7FB0F0;
                --soft: #1B2A44;
                --ok: #4FCB8A;
                --late: #FF8A80;
                --todo: #6F7A8C;
                --danger: #FF8A80
            }

            * {
                box-sizing: border-box
            }

            html {
                scroll-behavior: smooth;
                scroll-padding-top: calc(env(safe-area-inset-top,0px) + 64px)
            }

            body {
                margin: 0;
                background: var(--bg);
                color: var(--ink);
                font: 400 1rem/1.6 var(--sans);
                -webkit-font-smoothing: antialiased
            }

            body::before {
                content: "";
                position: fixed;
                inset: 0 0 auto;
                height: env(safe-area-inset-top,0px);
                background: var(--bg);
                z-index: 40
            }

            a {
                color: var(--ac);
                text-underline-offset: 3px
            }

            :focus-visible {
                outline: 3px solid var(--ac);
                outline-offset: 2px;
                border-radius: 4px
            }

            .wrap {
                max-width: 900px;
                margin: 0 auto;
                padding: 0 20px
            }

            nav {
                position: sticky;
                top: env(safe-area-inset-top,0px);
                z-index: 20;
                background: var(--bg);
                border-bottom: 1px solid var(--ln)
            }

            nav .wrap {
                display: flex;
                align-items: center;
                justify-content: space-between;
                gap: 12px;
                height: 56px
            }

            nav strong {
                font: 600 1.05rem var(--serif);
                white-space: nowrap
            }

            nav ul {
                display: flex;
                gap: 2px;
                list-style: none;
                margin: 0;
                padding: 0;
                overflow-x: auto
            }

            nav li a {
                display: block;
                padding: 8px 10px;
                color: var(--mu);
                text-decoration: none;
                font-size: .88rem;
                font-weight: 500;
                border-radius: 6px;
                white-space: nowrap
            }

            nav li a:hover {
                color: var(--ink);
                background: var(--soft)
            }

            .hero {
                padding: 56px 0 30px
            }

            .hero h1 {
                font: 600 clamp(2.2rem,8vw,3.8rem)/1.05 var(--serif);
                letter-spacing: -.02em;
                margin: 0 0 16px;
                max-width: 18ch
            }

            .hero p {
                font-size: 1.12rem;
                max-width: 58ch;
                color: var(--mu);
                margin: 0 0 24px
            }

            .btn {
                display: inline-block;
                padding: 9px 15px;
                border-radius: 8px;
                font: 600 .9rem var(--sans);
                text-decoration: none;
                border: 1px solid var(--ac);
                background: transparent;
                color: var(--ac);
                cursor: pointer
            }

            .btn.primary {
                background: var(--ac);
                color: var(--bg)
            }

            .btn.danger {
                border-color: var(--danger);
                color: var(--danger)
            }

            .btn.small {
                padding: 3px 9px;
                font-size: .78rem
            }

            .btn:disabled {
                opacity: .4;
                cursor: default
            }

            section {
                padding: 44px 0;
                border-top: 1px solid var(--ln)
            }

            section h2 {
                font: 600 clamp(1.7rem,5vw,2.1rem)/1.15 var(--serif);
                margin: 0 0 6px
            }

            .lead {
                color: var(--mu);
                max-width: 62ch;
                margin: 0 0 20px
            }

            .chips {
                display: flex;
                flex-wrap: wrap;
                gap: 6px;
                margin-bottom: 14px;
                align-items: center
            }

            .chip {
                padding: 5px 12px;
                border-radius: 99px;
                border: 1px solid var(--ln);
                background: var(--sf);
                color: var(--ink);
                font: 500 .85rem var(--sans);
                cursor: pointer
            }

            .chip.on {
                background: var(--ac);
                color: var(--bg);
                border-color: var(--ac)
            }

            input[type=search],.chips input {
                padding: 7px 10px;
                border: 1px solid var(--ln);
                border-radius: 8px;
                background: var(--sf);
                color: var(--ink);
                font: inherit;
                font-size: .9rem;
                min-width: 0;
                flex: 1 1 160px
            }

            #plist {
                display: grid;
                grid-template-columns: repeat(auto-fill,minmax(260px,1fr));
                gap: 14px;
                margin-bottom: 14px
            }

            .card {
                background: var(--sf);
                border: 1px solid var(--ln);
                border-radius: 12px;
                overflow: hidden;
                display: flex;
                flex-direction: column
            }

            .card img {
                width: 100%;
                height: 150px;
                object-fit: cover;
                display: block;
                background: var(--soft)
            }

            .card .b {
                padding: 14px;
                display: flex;
                flex-direction: column;
                gap: 8px;
                flex: 1
            }

            h3 {
                font: 600 1.18rem/1.3 var(--serif);
                margin: 0
            }

            h4 {
                font: 600 1rem var(--serif);
                margin: 0
            }

            .meta {
                font-size: .85rem;
                color: var(--mu)
            }

            .b p,.item p {
                margin: 0;
                white-space: pre-line
            }

            .tags {
                display: flex;
                flex-wrap: wrap;
                gap: 5px;
                list-style: none;
                padding: 0;
                margin: 0
            }

            .tags li {
                font-size: .78rem;
                padding: 1px 9px;
                border-radius: 99px;
                border: 1px solid var(--ln);
                background: var(--bg)
            }

            .links {
                display: flex;
                flex-wrap: wrap;
                gap: 4px 14px
            }

            .links a {
                font-size: .88rem;
                font-weight: 500
            }

            .tools {
                display: flex;
                gap: 6px;
                flex-wrap: wrap;
                margin-top: 6px
            }

            .empty {
                color: var(--mu);
                font-style: italic;
                padding: 8px 0
            }

            .gantt {
                background: var(--sf);
                border: 1px solid var(--ln);
                border-radius: 12px;
                padding: 16px;
                margin-bottom: 18px
            }

            .gh {
                display: flex;
                justify-content: space-between;
                gap: 10px;
                flex-wrap: wrap;
                align-items: center;
                margin-bottom: 10px
            }

            .gh progress {
                width: 100%;
                height: 10px;
                accent-color: var(--ac)
            }

            .gs {
                overflow-x: auto
            }

            .gi {
                min-width: 620px
            }

            .ga {
                display: flex;
                justify-content: space-between;
                font-size: .78rem;
                color: var(--mu);
                padding-left: 170px;
                margin-bottom: 4px
            }

            .grow {
                display: grid;
                grid-template-columns: 170px 1fr;
                border-top: 1px solid var(--ln);
                align-items: center
            }

            .gl {
                padding: 6px 8px 6px 0;
                font-size: .85rem;
                line-height: 1.3
            }

            .gl b {
                display: block
            }

            .gl span {
                color: var(--mu);
                font-size: .78rem
            }

            .gt {
                position: relative;
                height: 30px
            }

            .bar {
                position: absolute;
                top: 6px;
                height: 18px;
                border-radius: 5px;
                border: 1px solid var(--bc);
                background: var(--bg);
                overflow: hidden;
                min-width: 4px
            }

            .bar i {
                display: block;
                height: 100%;
                background: var(--bc)
            }

            .bar.done {
                --bc: var(--ok)
            }

            .bar.late {
                --bc: var(--late)
            }

            .bar.prog {
                --bc: var(--ac)
            }

            .bar.todo {
                --bc: var(--todo)
            }

            .today {
                position: absolute;
                top: 0;
                bottom: 0;
                width: 2px;
                background: var(--late);
                opacity: .6;
                text-decoration: none
            }

            .leg {
                font-size: .78rem;
                color: var(--mu);
                margin-top: 8px
            }

            .item {
                display: grid;
                grid-template-columns: 90px 1fr;
                gap: 6px 18px;
                padding: 20px 0;
                border-top: 1px solid var(--ln)
            }

            .when {
                font-size: .85rem;
                color: var(--mu);
                padding-top: 3px
            }

            .item>div:last-child {
                display: flex;
                flex-direction: column;
                gap: 8px
            }

            dl {
                margin: 0;
                display: grid;
                grid-template-columns: auto 1fr;
                gap: 3px 12px;
                font-size: .93rem
            }

            dt {
                font-weight: 600
            }

            dd {
                margin: 0
            }

            .tabs {
                display: flex;
                gap: 6px;
                flex-wrap: wrap;
                margin-bottom: 14px
            }

            .cp {
                background: var(--sf);
                border: 1px solid var(--ln);
                border-radius: 12px;
                padding: 16px
            }

            .cgrid {
                display: grid;
                grid-template-columns: repeat(auto-fit,minmax(120px,1fr));
                gap: 10px;
                margin-bottom: 12px
            }

            .cp label {
                font-size: .82rem;
                font-weight: 600;
                display: block
            }

            .cp input,.cp select {
                width: 100%;
                margin-top: 3px;
                padding: 7px 9px;
                border: 1px solid var(--ln);
                border-radius: 8px;
                background: var(--bg);
                color: var(--ink);
                font: inherit
            }

            .res {
                background: var(--soft);
                border-radius: 8px;
                padding: 10px 14px;
                font-weight: 600;
                display: grid;
                gap: 3px
            }

            .steps {
                font-size: .88rem;
                color: var(--mu);
                padding-left: 20px;
                margin: 10px 0 0
            }

            .steps .w {
                color: var(--late);
                font-weight: 600
            }

            .brow {
                display: grid;
                grid-template-columns: 3fr .8fr 1fr 1.2fr 1.3fr auto;
                gap: 6px;
                margin-bottom: 6px;
                align-items: center
            }

            .brow .tt {
                font-size: .85rem;
                text-align: right
            }

            .bh {
                font-size: .75rem;
                color: var(--mu);
                font-weight: 600
            }

            .note {
                background: var(--sf);
                border: 1px solid var(--ln);
                border-radius: 12px;
                padding: 14px;
                margin-top: 12px
            }

            pre {
                margin: 8px 0;
                padding: 12px;
                background: var(--bg);
                border: 1px solid var(--ln);
                border-radius: 8px;
                overflow-x: auto;
                font: .82rem/1.5 ui-monospace,Menlo,Consolas,monospace
            }

            .warn {
                font-size: .8rem;
                color: var(--mu);
                margin-top: 10px
            }

            footer {
                border-top: 1px solid var(--ln);
                padding: 20px 0 90px;
                font-size: .85rem;
                color: var(--mu)
            }

            #bar {
                position: fixed;
                left: 0;
                right: 0;
                bottom: env(safe-area-inset-bottom,0px);
                z-index: 30;
                background: var(--sf);
                border-top: 1px solid var(--ln);
                padding: 10px 16px;
                display: flex;
                gap: 8px;
                justify-content: center;
                flex-wrap: wrap
            }

            dialog {
                width: min(560px,94vw);
                max-height: 92vh;
                overflow: auto;
                border: 1px solid var(--ln);
                border-radius: 14px;
                background: var(--sf);
                color: var(--ink);
                padding: 20px
            }

            dialog::backdrop {
                background: rgba(0,0,0,.5)
            }

            dialog h3 {
                font-size: 1.4rem;
                margin-bottom: 10px
            }

            dialog label {
                display: block;
                font-size: .85rem;
                font-weight: 600;
                margin: 12px 0 4px
            }

            dialog input,dialog textarea,dialog select {
                width: 100%;
                font: inherit;
                padding: 8px 10px;
                border: 1px solid var(--ln);
                border-radius: 8px;
                background: var(--bg);
                color: var(--ink)
            }

            dialog small {
                color: var(--mu);
                font-weight: 400
            }

            .frow {
                display: flex;
                justify-content: space-between;
                align-items: center;
                gap: 8px;
                padding: 5px 0;
                border-bottom: 1px solid var(--ln);
                font-size: .9rem
            }

            .acts {
                display: flex;
                gap: 8px;
                justify-content: flex-end;
                margin-top: 18px
            }

            #toast {
                position: fixed;
                left: 50%;
                transform: translateX(-50%);
                bottom: calc(env(safe-area-inset-bottom,0px) + 72px);
                background: var(--ink);
                color: var(--bg);
                padding: 10px 16px;
                border-radius: 8px;
                z-index: 50;
                font-size: .9rem;
                max-width: 90vw
            }

            @media (max-width: 620px) {
                .item {
                    grid-template-columns:1fr
                }

                .brow {
                    grid-template-columns: 1fr 1fr
                }
            }

            @media (prefers-reduced-motion:reduce) {
                html {
                    scroll-behavior: auto
                }
            }
        </style>
    </head>
    <body>
        <div id="app"></div>
        <script type="application/json" id="data">
            {
                "profile": {
                    "name": "Guilherme da Silva Lima",
                    "headline": "Engenheiro(a) civil. Projetos estruturais, cronogramas de obra, pesquisa científica e ferramentas de cálculo.",
                    "email": "seuemail@exemplo.com",
                    "links": [
                        {
                            "label": "LinkedIn",
                            "url": "https://linkedin.com"
                        },
                        {
                            "label": "GitHub",
                            "url": "https://github.com"
                        },
                        {
                            "label": "Lattes",
                            "url": "https://lattes.cnpq.br"
                        }
                    ]
                },
                "projects": [
                    {
                        "id": "p1",
                        "title": "Edifício residencial de 4 pavimentos (exemplo)",
                        "cat": "Estrutural",
                        "local": "Cidade, UF",
                        "year": "2025",
                        "soft": [
                            "AutoCAD",
                            "SAP2000"
                        ],
                        "desc": "Projeto estrutural em concreto armado: lançamento, dimensionamento e detalhamento. Edite ou exclua este exemplo.",
                        "cover": null,
                        "links": [
                        ],
                        "files": [
                        ]
                    },
                    {
                        "id": "p2",
                        "title": "Drenagem pluvial de loteamento (exemplo)",
                        "cat": "Hidráulica",
                        "local": "Cidade, UF",
                        "year": "2024",
                        "soft": [
                            "Excel"],
                            "desc": "Dimensionamento de galerias e bocas de lobo.",
                            "cover": null,
                            "links": [
                            ],
                            "files": [
                            ]
                        }
                    ],
                    "gantts": [
                        {
                            "id": "g1",
                            "name": "Obra residencial (exemplo)",
                            "tasks": [
                                {
                                    "id": "t1",
                                    "name": "Fundações",
                                    "start": "2026-09-14",
                                    "days": 30,
                                    "owner": "Equipe A",
                                    "pct": 100
                                },
                                {
                                    "id": "t4",
                                    "name": "Instalações",
                                    "start": "2026-10-01",
                                    "days": 20,
                                    "owner": "Equipe C",
                                    "pct": 60
                                },
                                {
                                    "id": "t2",
                                    "name": "Estrutura",
                                    "start": "2026-10-14",
                                    "days": 50,
                                    "owner": "Equipe B",
                                    "pct": 35
                                },
                                {
                                    "id": "t3",
                                    "name": "Alvenaria",
                                    "start": "2026-11-23",
                                    "days": 30,
                                    "owner": "Equipe B",
                                    "pct": 0
                                }
                            ]
                        }
                    ],
                    "research": [
                        {
                            "id": "r1",
                            "title": "Título da pesquisa de iniciação científica (exemplo)",
                            "period": "2024–2025",
                            "advisor": "Prof(a). Nome",
                            "inst": "Universidade",
                            "grant": "PIBIC",
                            "goal": "O que a pesquisa buscava responder.",
                            "method": "Abordagem e ensaios realizados.",
                            "result": "Principal resultado obtido.",
                            "kw": [
                                "Concreto",
                                "Durabilidade"
                            ],
                            "pubs": [
                                "Autor. Título do trabalho. Congresso, 2025."
                            ],
                            "links": [
                            ],
                            "files": [
                            ]
                        }
                    ],
                    "notes": [
                        {
                            "id": "n1",
                            "title": "Exemplo: área de uma barra de aço (Python)",
                            "code": "import math\n\ndef area_barra(d_mm):\n    return math.pi * (d_mm / 10) ** 2 / 4  # cm²\n\nprint(area_barra(16))"
                        }
                    ]
                }</script>
            <script>
                const $ = s => document.querySelector(s);
                const el = (t, a={}, ...k) => {
                    const e = document.createElement(t);
                    for (const [n,v] of Object.entries(a)) {
                        if (n === 'class')
                            e.className = v;
                        else if (n.startsWith('on'))
                            e.addEventListener(n.slice(2), v);
                        else if (v !== false && v != null)
                            e.setAttribute(n, v)
                    }
                    k.flat().forEach(c => e.append(c && c.nodeType ? c : document.createTextNode(c == null || c === false ? '' : c)));
                    return e
                }
                ;
                const CATS = ['Estrutural', 'Geotécnica', 'Hidráulica', 'Transportes', 'Construção']
                  , BOLSAS = ['CNPq', 'FAPESP', 'PIBIC', 'Voluntária', 'Outra'];
                let state = JSON.parse($('#data').textContent), canEdit = false, editing = false, assets = null, artifact = null, downloads = null, fcat = 'Todas', q = '', ct = 0, plist;
                const safeUrl = u => {
                    u = (u || '').trim();
                    return /^(https?:|mailto:|\/_blob\/)/.test(u) ? u : 'https://' + u
                }
                ;
                const uid = () => 'i' + Date.now().toString(36) + Math.random().toString(36).slice(2, 5);
                const lines = t => t.split('\n').map(s => s.trim()).filter(Boolean);
                const linksTxt = a => (a || []).map(l => l.label + ' | ' + l.url).join('\n');
                const parseLinks = t => lines(t).map(l => {
                    const i = l.indexOf('|');
                    return i < 0 ? {
                        label: l,
                        url: l
                    } : {
                        label: l.slice(0, i).trim(),
                        url: l.slice(i + 1).trim()
                    }
                }
                ).filter(x => x.url);
                const fmt = (n, d=2) => n.toLocaleString('pt-BR', {
                    minimumFractionDigits: d,
                    maximumFractionDigits: d
                });
                const brl = n => n.toLocaleString('pt-BR', {
                    style: 'currency',
                    currency: 'BRL'
                });
                const DAY = 864e5
                  , D = s => new Date(s + 'T00:00:00Z').getTime()
                  , iso = t => new Date(t).toISOString().slice(0, 10)
                  , br = t => iso(t).split('-').reverse().join('/');
                const today = D(new Date().toISOString().slice(0, 10));
                const mv = (arr, x, d) => {
                    const i = arr.indexOf(x)
                      , j = i + d;
                    if (j < 0 || j >= arr.length)
                        return;
                    [arr[i],arr[j]] = [arr[j], arr[i]];
                    commit()
                }
                ;
                const tools = (arr, x, edit) => editing ? el('div', {
                    class: 'tools'
                }, el('button', {
                    class: 'btn small',
                    onclick: () => edit(x)
                }, 'Editar'), el('button', {
                    class: 'btn small',
                    onclick: () => mv(arr, x, -1)
                }, 'Subir'), el('button', {
                    class: 'btn small',
                    onclick: () => mv(arr, x, 1)
                }, 'Descer'), el('button', {
                    class: 'btn small danger',
                    onclick: () => {
                        if (confirm('Excluir este item?')) {
                            arr.splice(arr.indexOf(x), 1);
                            commit()
                        }
                    }
                }, 'Excluir')) : null;
                const upsert = (arr, old, x) => {
                    const i = arr.indexOf(old);
                    i >= 0 ? arr[i] = x : arr.push(x);
                    commit()
                }
                ;
                const flinks = x => {
                    const l = [...(x.links || []).map(k => el('a', {
                        href: safeUrl(k.url),
                        target: '_blank',
                        rel: 'noopener'
                    }, k.label || k.url)), ...(x.files || []).map(f => el('a', {
                        href: '/_blob/' + f.id,
                        target: '_blank',
                        rel: 'noopener'
                    }, 'Arquivo: ' + f.label))];
                    return l.length ? el('div', {
                        class: 'links'
                    }, l) : null
                }
                ;
                const tags = a => a && a.length ? el('ul', {
                    class: 'tags'
                }, a.map(t => el('li', {}, t))) : null;
                function toast(m, ms) {
                    let t = $('#toast');
                    if (!t) {
                        t = el('div', {
                            id: 'toast',
                            role: 'status'
                        });
                        document.body.append(t)
                    }
                    t.textContent = m;
                    clearTimeout(t._t);
                    if (ms)
                        t._t = setTimeout( () => t.remove(), ms)
                }

                /* formulário genérico */
                const filesW = (x, k, multi) => {
                    const box = el('div', {})
                      , st = el('small', {})
                      , inp = el('input', {
                        type: 'file',
                        multiple: multi ? '' : null,
                        accept: '.pdf,.png,.jpg,.jpeg,.webp,.csv,.txt,.md,.json,.mp4,.webm'
                    });
                    if (multi && !x[k])
                        x[k] = [];
                    const draw = () => {
                        box.innerHTML = '';
                        const arr = multi ? x[k] : (x[k] ? [x[k]] : []);
                        arr.forEach( (f, i) => box.append(el('div', {
                            class: 'frow'
                        }, el('span', {}, f.label), el('button', {
                            class: 'btn small danger',
                            onclick: () => {
                                multi ? x[k].splice(i, 1) : x[k] = null;
                                draw()
                            }
                        }, 'Remover'))));
                        if (!arr.length)
                            box.append(el('div', {
                                class: 'empty'
                            }, 'Nenhum arquivo.'))
                    }
                    ;
                    draw();
                    inp.addEventListener('change', async () => {
                        for (const f of inp.files) {
                            st.textContent = 'Enviando ' + f.name + '…';
                            try {
                                if (!assets)
                                    throw {
                                        message: 'envio indisponível'
                                    };
                                const r = await assets.upload(f)
                                  , o = {
                                    label: f.name,
                                    id: r.id
                                };
                                multi ? x[k].push(o) : x[k] = o;
                                draw()
                            } catch (e) {
                                st.textContent = 'Falha: ' + (e.message || e.code);
                                return
                            }
                        }
                        st.textContent = 'Pronto.';
                        inp.value = ''
                    }
                    );
                    return el('div', {}, box, inp, st)
                }
                ;
                function form(title, schema, obj, onSave) {
                    const x = JSON.parse(JSON.stringify(obj))
                      , c = {}
                      , body = el('div', {})
                      , d = el('dialog', {
                        id: 'dlg'
                    });
                    schema.forEach(s => {
                        const v = x[s.k];
                        c[s.k] = s.t === 'area' ? el('textarea', {
                            rows: s.r || 4
                        }, v || '') : s.t === 'lines' ? el('textarea', {
                            rows: 3
                        }, (v || []).join('\n')) : s.t === 'links' ? el('textarea', {
                            rows: 3
                        }, linksTxt(v)) : s.t === 'tags' ? el('input', {
                            value: (v || []).join(', ')
                        }) : s.t === 'select' ? el('select', {}, s.o.map(o => el('option', {
                            value: o,
                            selected: o === v ? '' : null
                        }, o))) : s.t === 'number' ? el('input', {
                            type: 'number',
                            step: 'any',
                            value: v ?? ''
                        }) : s.t === 'date' ? el('input', {
                            type: 'date',
                            value: v || ''
                        }) : s.t === 'files' ? filesW(x, s.k, true) : s.t === 'cover' ? filesW(x, s.k, false) : el('input', {
                            value: v || ''
                        });
                        body.append(el('label', {}, s.l, s.h && el('small', {}, ' ' + s.h)), c[s.k])
                    }
                    );
                    d.append(el('h3', {}, title), body, el('div', {
                        class: 'acts'
                    }, el('button', {
                        class: 'btn',
                        onclick: () => d.close()
                    }, 'Cancelar'), el('button', {
                        class: 'btn primary',
                        onclick: () => {
                            for (const s of schema) {
                                if (s.req && !c[s.k].value.trim()) {
                                    alert('Preencha: ' + s.l);
                                    return
                                }
                            }
                            schema.forEach(s => {
                                const e = c[s.k]
                                  , t = s.t;
                                if (t === 'files' || t === 'cover')
                                    return;
                                x[s.k] = t === 'tags' ? e.value.split(',').map(a => a.trim()).filter(Boolean) : t === 'lines' ? lines(e.value) : t === 'links' ? parseLinks(e.value) : t === 'number' ? (parseFloat(e.value) || 0) : e.value.trim()
                            }
                            );
                            d.close();
                            onSave(x)
                        }
                    }, 'Salvar')));
                    d.addEventListener('close', () => d.remove());
                    document.body.append(d);
                    d.showModal()
                }
                const T = {
                    t: 'text'
                }
                  , A = {
                    t: 'area'
                };
                const PS = [{
                    k: 'title',
                    l: 'Título',
                    req: 1,
                    ...T
                }, {
                    k: 'cat',
                    l: 'Categoria',
                    t: 'select',
                    o: CATS
                }, {
                    k: 'local',
                    l: 'Local',
                    ...T
                }, {
                    k: 'year',
                    l: 'Ano',
                    ...T
                }, {
                    k: 'soft',
                    l: 'Softwares',
                    t: 'tags',
                    h: '(separe por vírgula)'
                }, {
                    k: 'desc',
                    l: 'Descrição',
                    ...A
                }, {
                    k: 'cover',
                    l: 'Imagem de capa',
                    t: 'cover'
                }, {
                    k: 'links',
                    l: 'Links',
                    t: 'links',
                    h: '(Texto | endereço, um por linha)'
                }, {
                    k: 'files',
                    l: 'Anexos',
                    t: 'files',
                    h: '(PDF, imagens, CSV)'
                }];
                const RS = [{
                    k: 'title',
                    l: 'Título',
                    req: 1,
                    ...T
                }, {
                    k: 'period',
                    l: 'Período',
                    ...T
                }, {
                    k: 'advisor',
                    l: 'Orientador(a)',
                    ...T
                }, {
                    k: 'inst',
                    l: 'Instituição',
                    ...T
                }, {
                    k: 'grant',
                    l: 'Bolsa',
                    t: 'select',
                    o: BOLSAS
                }, {
                    k: 'goal',
                    l: 'Objetivo',
                    ...A
                }, {
                    k: 'method',
                    l: 'Método',
                    ...A
                }, {
                    k: 'result',
                    l: 'Resultados',
                    ...A
                }, {
                    k: 'kw',
                    l: 'Palavras-chave',
                    t: 'tags',
                    h: '(vírgula)'
                }, {
                    k: 'pubs',
                    l: 'Publicações e eventos',
                    t: 'lines',
                    h: '(um por linha)'
                }, {
                    k: 'links',
                    l: 'Links',
                    t: 'links',
                    h: '(Texto | endereço)'
                }, {
                    k: 'files',
                    l: 'Anexos',
                    t: 'files',
                    h: '(artigo, pôster, certificado em PDF)'
                }];
                const TS = [{
                    k: 'name',
                    l: 'Etapa',
                    req: 1,
                    ...T
                }, {
                    k: 'start',
                    l: 'Início',
                    t: 'date'
                }, {
                    k: 'days',
                    l: 'Duração (dias)',
                    t: 'number'
                }, {
                    k: 'owner',
                    l: 'Responsável',
                    ...T
                }, {
                    k: 'pct',
                    l: '% concluída',
                    t: 'number'
                }];
                const NS = [{
                    k: 'title',
                    l: 'Título',
                    req: 1,
                    ...T
                }, {
                    k: 'code',
                    l: 'Código ou anotação',
                    t: 'area',
                    r: 9
                }];
                const openProject = p => form(p ? 'Editar projeto' : 'Novo projeto', PS, p || {
                    id: uid(),
                    title: '',
                    cat: CATS[0],
                    local: '',
                    year: '',
                    soft: [],
                    desc: '',
                    cover: null,
                    links: [],
                    files: []
                }, x => upsert(state.projects, p, x));
                const openRes = p => form(p ? 'Editar pesquisa' : 'Nova pesquisa', RS, p || {
                    id: uid(),
                    title: '',
                    period: '',
                    advisor: '',
                    inst: '',
                    grant: 'PIBIC',
                    goal: '',
                    method: '',
                    result: '',
                    kw: [],
                    pubs: [],
                    links: [],
                    files: []
                }, x => upsert(state.research, p, x));
                const openNote = p => form(p ? 'Editar anotação' : 'Nova anotação', NS, p || {
                    id: uid(),
                    title: '',
                    code: ''
                }, x => upsert(state.notes, p, x));
                const openTask = (g, t) => form(t ? 'Editar etapa' : 'Nova etapa', TS, t || {
                    id: uid(),
                    name: '',
                    start: iso(today),
                    days: 7,
                    owner: '',
                    pct: 0
                }, x => {
                    x.days = Math.max(1, x.days);
                    x.pct = Math.min(100, Math.max(0, x.pct));
                    if (!x.start)
                        x.start = iso(today);
                    upsert(g.tasks, t, x)
                }
                );
                const openGantt = g => form(g ? 'Renomear cronograma' : 'Novo cronograma', [{
                    k: 'name',
                    l: 'Nome',
                    req: 1,
                    ...T
                }], g || {
                    id: uid(),
                    name: '',
                    tasks: []
                }, x => upsert(state.gantts, g, x));
                const openProfile = () => form('Editar perfil', [{
                    k: 'name',
                    l: 'Nome',
                    req: 1,
                    ...T
                }, {
                    k: 'headline',
                    l: 'Apresentação',
                    ...A
                }, {
                    k: 'email',
                    l: 'E-mail',
                    ...T
                }, {
                    k: 'links',
                    l: 'Links',
                    t: 'links',
                    h: '(Texto | endereço)'
                }], state.profile, x => {
                    state.profile = x;
                    commit()
                }
                );

                /* projetos */
                function drawProjects() {
                    if (!plist)
                        return;
                    plist.innerHTML = '';
                    const l = state.projects.filter(p => (fcat === 'Todas' || p.cat === fcat) && (!q || JSON.stringify([p.title, p.local, p.desc, p.soft, p.cat]).toLowerCase().includes(q.toLowerCase())));
                    if (!l.length)
                        plist.append(el('div', {
                            class: 'empty'
                        }, 'Nenhum projeto encontrado.'));
                    l.forEach(p => plist.append(el('article', {
                        class: 'card'
                    }, p.cover && el('img', {
                        src: '/_blob/' + p.cover.id,
                        alt: p.title,
                        loading: 'lazy'
                    }), el('div', {
                        class: 'b'
                    }, el('h3', {}, p.title), el('div', {
                        class: 'meta'
                    }, [p.cat, p.local, p.year].filter(Boolean).join(' · ')), tags(p.soft), p.desc && el('p', {}, p.desc), flinks(p), tools(state.projects, p, openProject)))))
                }
                /* cronogramas */
                function ganttEl(g) {
                    const Tk = g.tasks
                      , box = el('div', {
                        class: 'gantt'
                    })
                      , tot = Tk.reduce( (a, t) => a + t.days, 0)
                      , prog = tot ? Math.round(Tk.reduce( (a, t) => a + t.days * t.pct, 0) / tot) : 0;
                    const head = el('div', {
                        class: 'gh'
                    }, el('h3', {}, g.name), el('div', {
                        class: 'tools'
                    }, downloads && el('button', {
                        class: 'btn small',
                        onclick: () => csv(g)
                    }, 'Baixar CSV')));
                    box.append(head, el('div', {
                        class: 'meta'
                    }, 'Progresso geral: ' + prog + '%'), el('progress', {
                        max: 100,
                        value: prog
                    }));
                    if (editing)
                        head.lastChild.append(el('button', {
                            class: 'btn small',
                            onclick: () => openGantt(g)
                        }, 'Renomear'), el('button', {
                            class: 'btn small',
                            onclick: () => mv(state.gantts, g, -1)
                        }, 'Subir'), el('button', {
                            class: 'btn small',
                            onclick: () => mv(state.gantts, g, 1)
                        }, 'Descer'), el('button', {
                            class: 'btn small danger',
                            onclick: () => {
                                if (confirm('Excluir cronograma inteiro?')) {
                                    state.gantts.splice(state.gantts.indexOf(g), 1);
                                    commit()
                                }
                            }
                        }, 'Excluir'));
                    if (Tk.length) {
                        const st = Tk.map(t => D(t.start))
                          , en = Tk.map( (t, i) => st[i] + t.days * DAY)
                          , min = Math.min(...st, today)
                          , max = Math.max(...en, today + DAY)
                          , span = max - min
                          , inner = el('div', {
                            class: 'gi'
                        }, el('div', {
                            class: 'ga'
                        }, el('span', {}, br(min)), el('span', {}, 'hoje: ' + br(today)), el('span', {}, br(max))));
                        Tk.forEach( (t, i) => {
                            const late = en[i] <= today && t.pct < 100
                              , cls = t.pct >= 100 ? 'done' : late ? 'late' : (t.pct > 0 || st[i] <= today) ? 'prog' : 'todo';
                            inner.append(el('div', {
                                class: 'grow'
                            }, el('div', {
                                class: 'gl'
                            }, el('b', {}, t.name), el('span', {}, (t.owner || '—') + ' · ' + t.pct + '%' + (late ? ' · atrasada' : '')), tools(Tk, t, x => openTask(g, x))), el('div', {
                                class: 'gt'
                            }, el('div', {
                                class: 'bar ' + cls,
                                style: `left:${(st[i] - min) / span * 100}%;width:${t.days * DAY / span * 100}%`,
                                title: br(st[i]) + ' a ' + br(en[i] - DAY)
                            }, el('i', {
                                style: `width:${t.pct}%`
                            })), el('i', {
                                class: 'today',
                                style: `left:${(today - min) / span * 100}%`
                            }))))
                        }
                        );
                        box.append(el('div', {
                            class: 'gs'
                        }, inner), el('div', {
                            class: 'leg'
                        }, 'Verde: concluída · Azul: em andamento · Cinza: não iniciada · Vermelho: atrasada · Linha vermelha: hoje'))
                    } else
                        box.append(el('div', {
                            class: 'empty'
                        }, 'Nenhuma etapa ainda.'));
                    if (editing)
                        box.append(el('div', {
                            class: 'tools'
                        }, el('button', {
                            class: 'btn small',
                            onclick: () => openTask(g)
                        }, '+ Adicionar etapa')));
                    return box
                }
                async function csv(g) {
                    const c = v => '"' + String(v).replace(/"/g, '""') + '"'
                      , r = [['Etapa', 'Início', 'Fim', 'Duração (dias)', 'Responsável', '% concluída'].map(c).join(';')];
                    g.tasks.forEach(t => r.push([t.name, br(D(t.start)), br(D(t.start) + (t.days - 1) * DAY), t.days, t.owner, t.pct].map(c).join(';')));
                    try {
                        await downloads.save({
                            filename: (g.name.replace(/[^\w]+/g, '-').toLowerCase() || 'cronograma') + '.csv',
                            data: new Blob(['\ufeff' + r.join('\n')],{
                                type: 'text/csv'
                            })
                        })
                    } catch (e) {
                        if (e.code !== 'declined')
                            toast('Não foi possível baixar: ' + (e.message || e.code), 5000)
                    }
                }
                /* calculadoras */
                const NB = 'Resultado auxiliar, simplificado. Verifique sempre conforme as normas aplicáveis (ABNT NBR 6118) e com responsável técnico.';
                function calc(f, run) {
                    const out = el('div', {})
                      , inp = {}
                      , go = () => {
                        const v = {};
                        for (const k in inp)
                            v[k] = parseFloat(inp[k].value.replace(',', '.')) || 0;
                        const r = run(v);
                        out.innerHTML = '';
                        out.append(el('div', {
                            class: 'res'
                        }, r.res.map(x => el('div', {}, x))), el('ol', {
                            class: 'steps'
                        }, r.steps.map(s => el('li', {
                            class: s[0] === '!' ? 'w' : null
                        }, s.replace(/^!/, '')))))
                    }
                    ;
                    const g = el('div', {
                        class: 'cgrid'
                    }, f.map( ([id,l,d,u]) => {
                        const i = el('input', {
                            type: 'number',
                            step: 'any',
                            value: d,
                            inputmode: 'decimal'
                        });
                        inp[id] = i;
                        i.addEventListener('input', go);
                        return el('label', {}, l + (u ? ' (' + u + ')' : ''), i)
                    }
                    ));
                    go();
                    return el('div', {}, g, out)
                }
                const viga = () => calc([['b', 'b', 20, 'cm'], ['h', 'h', 50, 'cm'], ['d', 'd', 46, 'cm'], ['fck', 'fck', 25, 'MPa'], ['fyk', 'fyk', 500, 'MPa'], ['Md', 'Md', 120, 'kN·m']], v => {
                    if (!(v.b > 0 && v.d > 0 && v.fck > 0 && v.fyk > 0 && v.Md > 0))
                        return {
                            res: ['Preencha todos os campos.'],
                            steps: []
                        };
                    const fcd = v.fck / 1.4
                      , fyd = v.fyk / 1.15
                      , M = v.Md * 100
                      , k = M / (0.425 * v.b * v.d * v.d * fcd / 10);
                    const s = [`fcd = fck/1,4 = ${fmt(fcd)} MPa; fyd = fyk/1,15 = ${fmt(fyd)} MPa`, `Md = ${fmt(v.Md)} kN·m = ${fmt(M, 0)} kN·cm`];
                    if (k > 1)
                        return {
                            res: ['Seção insuficiente: aumente b, d ou fck.'],
                            steps: s
                        };
                    const x = 1.25 * v.d * (1 - Math.sqrt(1 - k))
                      , xd = x / v.d
                      , lim = v.fck <= 50 ? 0.45 : 0.35
                      , z = v.d - 0.4 * x
                      , As = M / (z * fyd / 10)
                      , mn = 0.0015 * v.b * v.h
                      , Au = Math.max(As, mn);
                    s.push(`Linha neutra: x = 1,25·d·[1 − √(1 − Md/(0,425·b·d²·fcd))] = ${fmt(x)} cm`, (xd > lim ? '!' : '') + `x/d = ${fmt(xd)} (limite ${lim}, domínios 2 e 3)${xd > lim ? ': excede o limite, use armadura dupla ou aumente a seção' : ''}`, `Braço de alavanca: z = d − 0,4·x = ${fmt(z)} cm`, `As = Md/(z·fyd) = ${fmt(As)} cm²; As,mín ≈ 0,15%·b·h = ${fmt(mn)} cm²`);
                    return {
                        res: [`As calculada: ${fmt(As)} cm² (adotar ≥ ${fmt(Au)} cm²)`, 'Sugestão: ' + [10, 12.5, 16, 20, 25].map(p => {
                            const a = Math.PI * (p / 10) ** 2 / 4
                              , n = Math.max(2, Math.ceil(Au / a));
                            return `${n} φ${String(p).replace('.', ',')} (${fmt(n * a)} cm²)`
                        }
                        ).join(' · ')],
                        steps: s
                    }
                }
                );
                const traco = () => calc([['a', 'Areia (a)', 2, '1:a:b'], ['b', 'Brita (b)', 3, '1:a:b'], ['ac', 'Fator a/c', 0.5, '']], v => {
                    if (!(v.ac > 0))
                        return {
                            res: ['Informe o fator a/c.'],
                            steps: []
                        };
                    const C = 1000 / (1 / 3.15 + v.a / 2.65 + v.b / 2.7 + v.ac);
                    return {
                        res: [`Cimento: ${fmt(C)} kg/m³ (${fmt(C / 50, 1)} sacos de 50 kg)`, `Areia: ${fmt(C * v.a)} kg/m³`, `Brita: ${fmt(C * v.b)} kg/m³`, `Água: ${fmt(C * v.ac)} L/m³`],
                        steps: ['Massas específicas adotadas: cimento 3,15; areia 2,65; brita 2,70 kg/dm³', 'C = 1000 / (1/3,15 + a/2,65 + b/2,70 + a/c)  [ignora ar incorporado]', `C = 1000 / (${fmt(1 / 3.15, 3)} + ${fmt(v.a / 2.65, 3)} + ${fmt(v.b / 2.7, 3)} + ${fmt(v.ac, 3)}) = ${fmt(C)} kg/m³`, 'Areia = a·C; brita = b·C; água = (a/c)·C']
                    }
                }
                );
                const laje = () => calc([['c', 'Comprimento', 5, 'm'], ['l', 'Largura', 4, 'm'], ['e', 'Espessura', 12, 'cm']], v => {
                    const V = v.c * v.l * v.e / 100
                      , g = 25 * v.e / 100;
                    return {
                        res: [`Volume de concreto: ${fmt(V)} m³`, `Peso próprio: ${fmt(g)} kN/m² (total ${fmt(25 * V)} kN)`],
                        steps: [`V = c · l · e = ${fmt(v.c)} · ${fmt(v.l)} · ${fmt(v.e / 100)} = ${fmt(V)} m³`, `Peso próprio = 25 kN/m³ · e = 25 · ${fmt(v.e / 100)} = ${fmt(g)} kN/m²`, `Total = 25 · V = ${fmt(25 * V)} kN`]
                    }
                }
                );
                const bud = {
                    rows: [{
                        d: 'Concreto usinado fck 25 MPa',
                        u: 'm³',
                        q: 10,
                        p: 520
                    }, {
                        d: 'Aço CA-50',
                        u: 'kg',
                        q: 800,
                        p: 8.5
                    }],
                    bdi: 25
                };
                function orc() {
                    const box = el('div', {})
                      , tb = el('div', {})
                      , tot = el('div', {
                        class: 'res'
                    })
                      , sum = () => {
                        const s = bud.rows.reduce( (a, r) => a + r.q * r.p, 0)
                          , b = s * bud.bdi / 100;
                        tot.innerHTML = '';
                        tot.append(el('div', {}, 'Subtotal: ' + brl(s)), el('div', {}, `BDI (${fmt(bud.bdi, 1)}%): ${brl(b)}`), el('div', {}, 'Total: ' + brl(s + b)))
                    }
                    ;
                    const draw = () => {
                        tb.innerHTML = '';
                        tb.append(el('div', {
                            class: 'brow bh'
                        }, ['Descrição', 'Un.', 'Qtd.', 'Preço unit.', 'Total', ''].map(x => el('span', {}, x))));
                        bud.rows.forEach( (r, i) => {
                            const t = el('span', {
                                class: 'tt'
                            }, brl(r.q * r.p))
                              , f = (k, ty) => {
                                const n = el('input', {
                                    value: r[k],
                                    type: ty,
                                    step: 'any'
                                });
                                n.addEventListener('input', () => {
                                    r[k] = ty === 'number' ? (parseFloat(n.value) || 0) : n.value;
                                    t.textContent = brl(r.q * r.p);
                                    sum()
                                }
                                );
                                return n
                            }
                            ;
                            tb.append(el('div', {
                                class: 'brow'
                            }, f('d', 'text'), f('u', 'text'), f('q', 'number'), f('p', 'number'), t, el('button', {
                                class: 'btn small danger',
                                onclick: () => {
                                    bud.rows.splice(i, 1);
                                    draw()
                                }
                            }, '×')))
                        }
                        );
                        sum()
                    }
                    ;
                    const bdi = el('input', {
                        type: 'number',
                        step: 'any',
                        value: bud.bdi
                    });
                    bdi.addEventListener('input', () => {
                        bud.bdi = parseFloat(bdi.value) || 0;
                        sum()
                    }
                    );
                    draw();
                    box.append(tb, el('div', {
                        class: 'tools'
                    }, el('button', {
                        class: 'btn small',
                        onclick: () => {
                            bud.rows.push({
                                d: '',
                                u: 'un',
                                q: 1,
                                p: 0
                            });
                            draw()
                        }
                    }, '+ Linha')), el('div', {
                        class: 'cgrid',
                        style: 'margin-top:10px'
                    }, el('label', {}, 'BDI (%)', bdi)), tot, el('p', {
                        class: 'warn'
                    }, 'Os dados do orçamento ficam apenas nesta visita; baixe ou copie antes de sair.'));
                    return box
                }
                const UN = {
                    Força: {
                        N: 1,
                        kN: 1e3,
                        kgf: 9.80665,
                        tf: 9806.65
                    },
                    Pressão: {
                        Pa: 1,
                        kPa: 1e3,
                        MPa: 1e6,
                        'kgf/cm²': 98066.5
                    },
                    Comprimento: {
                        mm: .001,
                        cm: .01,
                        m: 1
                    }
                };
                function uni() {
                    const opts = el => Object.entries(UN).map( ([g,u]) => el('optgroup', {
                        label: g
                    }, Object.keys(u).map(k => el('option', {
                        value: k
                    }, k))))
                      , v = el('input', {
                        type: 'number',
                        step: 'any',
                        value: 1
                    })
                      , a = el('select', {}, opts(el))
                      , b = el('select', {}, opts(el))
                      , o = el('div', {
                        class: 'res'
                    });
                    b.value = 'kgf';
                    a.value = 'kN';
                    const go = () => {
                        const ga = Object.keys(UN).find(g => a.value in UN[g])
                          , gb = Object.keys(UN).find(g => b.value in UN[g]);
                        o.innerHTML = '';
                        if (ga !== gb) {
                            o.append(el('div', {}, 'Unidades incompatíveis.'));
                            return
                        }
                        const n = parseFloat(v.value.replace(',', '.')) || 0
                          , r = n * UN[ga][a.value] / UN[ga][b.value];
                        o.append(el('div', {}, `${fmt(n, 4)} ${a.value} = ${fmt(r, 4)} ${b.value}`))
                    }
                    ;
                    [v, a, b].forEach(n => n.addEventListener('input', go));
                    go();
                    return el('div', {}, el('div', {
                        class: 'cgrid'
                    }, el('label', {}, 'Valor', v), el('label', {}, 'De', a), el('label', {}, 'Para', b)), o)
                }
                const CALCS = [['Viga', viga], ['Traço', traco], ['Laje', laje], ['Orçamento', orc], ['Unidades', uni]];
                function copy(t) {
                    const done = () => toast('Copiado.', 1800);
                    if (navigator.clipboard && navigator.clipboard.writeText)
                        navigator.clipboard.writeText(t).then(done, () => fb(t));
                    else
                        fb(t);
                    function fb(t) {
                        const a = el('textarea', {
                            style: 'position:fixed;opacity:0'
                        }, t);
                        document.body.append(a);
                        a.select();
                        try {
                            document.execCommand('copy');
                            done()
                        } catch (e) {
                            toast('Selecione e copie manualmente.', 3000)
                        }
                        a.remove()
                    }
                }

                function render() {
                    const p = state.profile
                      , app = $('#app');
                    app.innerHTML = '';
                    const sec = (id, t, lead, ...k) => el('section', {
                        id
                    }, el('h2', {}, t), el('p', {
                        class: 'lead'
                    }, lead), ...k)
                      , add = (l, f) => editing ? el('button', {
                        class: 'btn',
                        onclick: f
                    }, l) : null;
                    app.append(el('nav', {}, el('div', {
                        class: 'wrap'
                    }, el('strong', {}, p.name), el('ul', {}, [['projetos', 'Projetos'], ['cronogramas', 'Cronogramas'], ['pesquisa', 'Pesquisa'], ['programacao', 'Programação'], ['contato', 'Contato']].map( ([i,t]) => el('li', {}, el('a', {
                        href: '#' + i
                    }, t)))))), el('header', {
                        class: 'hero'
                    }, el('div', {
                        class: 'wrap'
                    }, el('h1', {}, p.name), el('p', {}, p.headline), el('a', {
                        class: 'btn primary',
                        href: '#contato'
                    }, 'Entrar em contato'))));
                    plist = el('div', {
                        id: 'plist'
                    });
                    const chips = el('div', {
                        class: 'chips'
                    }, ['Todas', ...CATS].map(c => el('button', {
                        class: 'chip' + (fcat === c ? ' on' : ''),
                        onclick: () => {
                            fcat = c;
                            render()
                        }
                    }, c)), el('input', {
                        type: 'search',
                        placeholder: 'Buscar projetos',
                        value: q,
                        'aria-label': 'Buscar projetos',
                        oninput: e => {
                            q = e.target.value;
                            drawProjects()
                        }
                    }));
                    const panel = el('div', {
                        class: 'cp'
                    })
                      , tabs = el('div', {
                        class: 'tabs'
                    })
                      , showCalc = () => {
                        panel.innerHTML = '';
                        panel.append(CALCS[ct][1](), el('p', {
                            class: 'warn'
                        }, NB));
                        [...tabs.children].forEach( (b, i) => b.classList.toggle('on', i === ct))
                    }
                    ;
                    CALCS.forEach( ([n], i) => tabs.append(el('button', {
                        class: 'chip',
                        onclick: () => {
                            ct = i;
                            showCalc()
                        }
                    }, n)));
                    app.append(el('main', {
                        class: 'wrap'
                    }, sec('projetos', 'Projetos de engenharia civil', 'Obras e projetos por categoria, com anexos e links.', chips, plist, add('+ Adicionar projeto', () => openProject())), sec('cronogramas', 'Cronogramas', 'Gráfico de Gantt com progresso e alerta de etapas atrasadas.', state.gantts.length ? state.gantts.map(ganttEl) : el('div', {
                        class: 'empty'
                    }, 'Nenhum cronograma.'), add('+ Novo cronograma', () => openGantt())), sec('pesquisa', 'Pesquisas científicas', 'Iniciação científica, publicações e eventos.', state.research.map(r => el('article', {
                        class: 'item'
                    }, el('div', {
                        class: 'when'
                    }, r.period), el('div', {}, el('h3', {}, r.title), el('div', {
                        class: 'meta'
                    }, [r.advisor && 'Orientador(a): ' + r.advisor, r.inst, r.grant && 'Bolsa: ' + r.grant].filter(Boolean).join(' · ')), el('dl', {}, [['Objetivo', r.goal], ['Método', r.method], ['Resultados', r.result]].filter(x => x[1]).flatMap( ([a,b]) => [el('dt', {}, a), el('dd', {}, b)])), tags(r.kw), r.pubs && r.pubs.length && el('div', {}, el('h4', {}, 'Publicações e eventos'), el('ul', {}, r.pubs.map(x => el('li', {}, x)))), flinks(r), tools(state.research, r, openRes)))), add('+ Adicionar pesquisa', () => openRes())), sec('programacao', 'Programação', 'Calculadoras que funcionam aqui mesmo, e meus códigos e anotações.', tabs, panel, el('h3', {
                        style: 'margin-top:26px'
                    }, 'Anotações e códigos'), state.notes.map(n => el('div', {
                        class: 'note'
                    }, el('h4', {}, n.title), el('pre', {}, n.code), el('div', {
                        class: 'tools'
                    }, el('button', {
                        class: 'btn small',
                        onclick: () => copy(n.code)
                    }, 'Copiar'), null), tools(state.notes, n, openNote))), add('+ Adicionar anotação', () => openNote())), sec('contato', 'Contato', 'Para propostas, colaborações e oportunidades.', p.email && el('p', {}, el('a', {
                        href: 'mailto:' + p.email,
                        style: 'font:600 1.5rem var(--serif)'
                    }, p.email)), el('div', {
                        class: 'links'
                    }, (p.links || []).map(l => el('a', {
                        href: safeUrl(l.url),
                        target: '_blank',
                        rel: 'noopener'
                    }, l.label))))), el('footer', {}, el('div', {
                        class: 'wrap'
                    }, '© 2026 ' + p.name)));
                    drawProjects();
                    showCalc()
                }
                function buildHtml() {
                    const c = document.documentElement.cloneNode(true);
                    c.querySelectorAll('#dlg,#bar,#toast').forEach(n => n.remove());
                    c.querySelector('#app').innerHTML = '';
                    c.querySelector('#data').textContent = JSON.stringify(state).replace(/</g, '\\u003c');
                    return '<!DOCTYPE html>\n' + c.outerHTML
                }
                async function commit() {
                    render();
                    drawBar();
                    toast('Salvando…');
                    try {
                        await artifact.publish(buildHtml())
                    } catch (e) {
                        toast('Não foi possível salvar: ' + (e.message || e.code || 'erro'), 6000)
                    }
                }
                function drawBar() {
                    let b = $('#bar');
                    if (!b) {
                        b = el('div', {
                            id: 'bar'
                        });
                        document.body.append(b)
                    }
                    b.innerHTML = '';
                    b.append(el('button', {
                        class: 'btn' + (editing ? ' primary' : ''),
                        onclick: () => {
                            editing = !editing;
                            render();
                            drawBar()
                        }
                    }, editing ? 'Sair do modo de edição' : 'Editar site'));
                    if (editing)
                        b.append(el('button', {
                            class: 'btn',
                            onclick: openProfile
                        }, 'Editar perfil'))
                }
                render();
                (async () => {
                    try {
                        if (typeof claude === 'undefined')
                            return;
                        const u = await claude.use('user');
                        canEdit = !!(u && (u.canEdit() || u.isOwner()));
                        artifact = await claude.use('artifact');
                        assets = await claude.use('assets');
                        downloads = await claude.use('downloads');
                        if (downloads)
                            render();
                        if (artifact && (canEdit || location.hash === '#editar'))
                            drawBar()
                    } catch (e) {}
                }
                )();
            </script>
        </body>
    </html>
