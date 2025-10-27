meu-projeto/
│
├─ index.html
├─ css/
│   ├─ variables.css      (paleta de cores, tipografia, espaçamento)
│   ├─ layout.css         (grid, flex, responsividade)
│   ├─ components.css     (cards, botões, formulários, badges, modals)
│   └─ main.css           (importa todos os outros arquivos)
├─ images/
│   └─ ... (todas as imagens usadas)
└─ js/
    └─ scripts.js         (para menu hambúrguer, dropdown e interações)
    /* Paleta de cores */
:root {
    /* Primárias */
    --color-primary: #1E90FF;
    --color-primary-dark: #1C86EE;

    /* Secundárias */
    --color-secondary: #FF8C00;
    --color-secondary-dark: #FF7F00;

    /* Neutras */
    --color-white: #FFFFFF;
    --color-black: #000000;
    --color-gray-light: #F5F5F5;
    --color-gray-dark: #333333;

    /* Tipografia */
    --font-size-xs: 12px;
    --font-size-sm: 14px;
    --font-size-md: 16px;
    --font-size-lg: 24px;
    --font-size-xl: 32px;

    /* Espaçamento modular */
    --space-8: 8px;
    --space-16: 16px;
    --space-24: 24px;
    --space-32: 32px;
    --space-48: 48px;
    --space-64: 64px;
}
/* Grid principal */
.container {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    gap: var(--space-16);
}

/* Flex para alinhamento interno */
.flex {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

/* Responsividade */
@media (max-width: 1200px) { /* breakpoint 1 */ }
@media (max-width: 992px)  { /* breakpoint 2 */ }
@media (max-width: 768px)  { /* breakpoint 3 */ }
@media (max-width: 576px)  { /* breakpoint 4 */ }
@media (max-width: 360px)  { /* breakpoint 5 */ }
/* Botões */
button {
    background-color: var(--color-primary);
    color: var(--color-white);
    padding: var(--space-8) var(--space-16);
    border: none;
    border-radius: 4px;
    cursor: pointer;
}
button:hover { background-color: var(--color-primary-dark); }
button:disabled { background-color: var(--color-gray-dark); cursor: not-allowed; }

/* Cards */
.card {
    background-color: var(--color-white);
    border-radius: 8px;
    padding: var(--space-16);
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}

/* Badges */
.badge {
    display: inline-block;
    padding: 4px 8px;
    border-radius: 12px;
    background-color: var(--color-secondary);
    color: var(--color-white);
}

/* Formularios */
input, textarea, select {
    padding: var(--space-8);
    border: 1px solid var(--color-gray-dark);
    border-radius: 4px;
}

/* Alerts */
.alert {
    padding: var(--space-16);
    border-radius: 4px;
    background-color: var(--color-secondary);
    color: var(--color-white);
}
@import url('variables.css');
@import url('layout.css');
@import url('components.css');
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Projeto CSS3</title>
    <link rel="stylesheet" href="css/main.css">
</head>
<body>
    <!-- Menu -->
    <header class="flex">
        <h1>Meu Projeto</h1>
        <nav>
            <ul class="flex">
                <li><a href="#">Home</a></li>
                <li><a href="#">Projetos</a>
                    <ul class="dropdown">
                        <li><a href="#">Projeto 1</a></li>
                        <li><a href="#">Projeto 2</a></li>
                    </ul>
                </li>
                <li><a href="#">Contato</a></li>
            </ul>
        </nav>
        <button class="hamburger">☰</button>
    </header>

    <!-- Cards -->
    <section class="container">
        <div class="card">
            <h2>Card 1</h2>
            <p>Descrição do card 1.</p>
            <span class="badge">Novo</span>
        </div>
        <div class="card">
            <h2>Card 2</h2>
            <p>Descrição do card 2.</p>
            <span class="badge">Em destaque</span>
        </div>
    </section>

    <!-- Formulário -->
    <form>
        <input type="text" placeholder="Nome" required>
        <input type="email" placeholder="Email" required>
        <button type="submit">Enviar</button>
    </form>

    <script src="js/scripts.js"></script>
</body>
</html>
