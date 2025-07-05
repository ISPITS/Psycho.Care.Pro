<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PsychoCare Pro | Évaluation du Stress Professionnel</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #38bdf8;
            --primary-dark: #0ea5e9;
            --primary-light: #e0f2fe;
            --accent: #1e3a8a;
            --text: #334155;
            --light: #f8fafc;
            --border: #cbd5e1;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f0f9ff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            color: var(--text);
            line-height: 1.6;
        }
        
        .header {
            background: linear-gradient(135deg, var(--accent) 0%, var(--primary) 100%);
            color: white;
            padding: 1.5rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            color: var(--primary);
        }
        
        .nav-buttons {
            display: flex;
            gap: 15px;
            margin-top: 10px;
        }
        
        .nav-btn {
            background: rgba(255, 255, 255, 0.15);
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 30px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .nav-btn:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateY(-2px);
        }
        
        .main-content {
            flex: 1;
            padding: 40px 0;
        }
        
        .page {
            display: none;
        }
        
        .page.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .home-container {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        
        .medical-icons {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 30px 0;
        }
        
        .medical-icon {
            font-size: 3rem;
            color: var(--primary);
            background: white;
            width: 80px;
            height: 80px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 5px 15px rgba(56, 189, 248, 0.2);
            animation: pulse 2s infinite;
        }
        
        .medical-icon:nth-child(2) {
            animation-delay: 0.5s;
        }
        
        .medical-icon:nth-child(3) {
            animation-delay: 1s;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        h1 {
            font-size: 2.5rem;
            color: #1e40af;
            margin-bottom: 15px;
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: #475569;
            margin-bottom: 30px;
        }
        
        .welcome-card {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            margin-bottom: 30px;
        }
        
        .welcome-card h2 {
            color: #1e40af;
            margin-bottom: 20px;
            font-size: 1.8rem;
        }
        
        .welcome-card p {
            color: #475569;
            margin-bottom: 25px;
            font-size: 1.1rem;
        }
        
        .button-group {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 15px 30px;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            border: none;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
            box-shadow: 0 5px 15px rgba(59, 130, 246, 0.3);
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(59, 130, 246, 0.4);
        }
        
        .btn-secondary {
            background: white;
            color: var(--primary);
            border: 2px solid var(--primary);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .btn-secondary:hover {
            background: #f0f7ff;
            transform: translateY(-3px);
        }
        
        .info-box {
            background: var(--primary-light);
            border-left: 4px solid var(--primary);
            padding: 20px;
            border-radius: 8px;
            margin-top: 30px;
        }
        
        .info-box h3 {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--accent);
            margin-bottom: 10px;
        }
        
        .form-container {
            max-width: 900px;
            margin: 0 auto;
        }
        
        .form-section {
            background: white;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 25px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
        }
        
        .section-title {
            color: var(--accent);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary-light);
            font-size: 1.4rem;
        }
        
        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--text);
        }
        
        input, select, textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--border);
            border-radius: 8px;
            font-family: 'Poppins', sans-serif;
            font-size: 1rem;
        }
        
        .radio-group {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }
        
        .radio-option {
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .question-card {
            background: #f8fafc;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 15px;
            border-left: 3px solid var(--primary-light);
            transition: all 0.3s ease;
        }
        
        .question-card:hover {
            border-left-color: var(--primary);
            background: #f0f9ff;
        }
        
        .question-card p {
            font-weight: 500;
            margin-bottom: 15px;
            color: #1e293b;
        }
        
        .options-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 10px;
        }
        
        .option-label {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 10px;
            background: white;
            border: 1px solid var(--border);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .option-label:hover {
            border-color: var(--primary);
        }
        
        .form-actions {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
            flex-wrap: wrap;
            gap: 15px;
        }
        
        .results-container {
            max-width: 1000px;
            margin: 0 auto;
        }
        
        .results-header {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .results-header h2 {
            color: var(--accent);
            font-size: 2rem;
            margin-bottom: 10px;
        }
        
        .user-results {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            margin-bottom: 30px;
            text-align: center;
        }
        
        .stress-level {
            font-size: 3rem;
            font-weight: 700;
            color: var(--primary);
            margin: 20px 0;
        }
        
        .stress-meter {
            height: 20px;
            background: #e2e8f0;
            border-radius: 10px;
            margin: 30px 0;
            overflow: hidden;
        }
        
        .stress-progress {
            height: 100%;
            background: linear-gradient(90deg, #4ade80, #3b82f6, #ef4444);
            border-radius: 10px;
        }
        
        .stress-description {
            font-size: 1.2rem;
            color: #475569;
            max-width: 600px;
            margin: 0 auto 20px;
        }
        
        .stress-interpretation {
            background: var(--primary-light);
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
            text-align: left;
        }
        
        .participants-results {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            margin-bottom: 30px;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        th, td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid #e2e8f0;
        }
        
        th {
            background: #f1f5f9;
            color: #475569;
            font-weight: 600;
        }
        
        .participant-name {
            font-weight: 500;
            color: #1e293b;
        }
        
        .participant-specialty {
            font-size: 0.9rem;
            color: #64748b;
        }
        
        .stress-badge {
            display: inline-block;
            padding: 5px 15px;
            border-radius: 20px;
            font-weight: 500;
        }
        
        .stress-low {
            background: #dcfce7;
            color: #166534;
        }
        
        .stress-medium {
            background: #fef9c3;
            color: #854d0e;
        }
        
        .stress-high {
            background: #fee2e2;
            color: #991b1b;
        }
        
        .progress-bar {
            height: 8px;
            background: #e2e8f0;
            border-radius: 4px;
            overflow: hidden;
            margin: 8px 0;
        }
        
        .progress-value {
            height: 100%;
            background: var(--primary);
        }
        
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .stat-card {
            background: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            text-align: center;
        }
        
        .stat-card h3 {
            color: #475569;
            margin-bottom: 10px;
            font-size: 1.1rem;
        }
        
        .stat-value {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--accent);
        }
        
        .advice-list {
            margin-top: 20px;
            padding-left: 20px;
            text-align: left;
        }
        
        .advice-list li {
            margin-bottom: 10px;
        }
        
        .footer {
            background: white;
            padding: 30px 0;
            border-top: 1px solid #e2e8f0;
            text-align: center;
        }
        
        .footer-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .footer p {
            margin-bottom: 5px;
            color: #64748b;
        }
        
        .footer strong {
            color: #475569;
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .nav-buttons {
                width: 100%;
                justify-content: center;
            }
            
            .button-group {
                flex-direction: column;
            }
            
            .btn {
                width: 100%;
                justify-content: center;
            }
            
            .form-actions {
                flex-direction: column;
            }
            
            .medical-icons {
                gap: 15px;
            }
            
            .medical-icon {
                width: 60px;
                height: 60px;
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-brain"></i>
                    <span>PsychoCare Pro</span>
                </div>
                <div class="nav-buttons">
                    <button class="nav-btn" onclick="showPage('home-page')">
                        <i class="fas fa-home"></i> Accueil
                    </button>
                    <button class="nav-btn" onclick="showPage('results-page')">
                        <i class="fas fa-chart-bar"></i> Résultats
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="main-content">
        <div class="container">
            <!-- Home Page -->
            <div id="home-page" class="page active">
                <div class="home-container">
                    <div class="medical-icons">
                        <div class="medical-icon">
                            <i class="fas fa-heartbeat"></i>
                        </div>
                        <div class="medical-icon">
                            <i class="fas fa-stethoscope"></i>
                        </div>
                        <div class="medical-icon">
                            <i class="fas fa-brain"></i>
                        </div>
                    </div>
                    
                    <h1>Tester votre stress</h1>
                    <p class="subtitle">Évaluez votre niveau de stress professionnel en quelques minutes</p>
                    
                    <div class="welcome-card">
                        <h2>Bienvenue sur notre plateforme d'évaluation du stress</h2>
                        <p>
                            Ce test complet vous aidera à comprendre votre niveau de stress actuel dans votre environnement professionnel.
                            Répondez honnêtement aux questions pour obtenir une évaluation précise basée sur les modèles scientifiques
                            de Karasek et Siegrist.
                        </p>
                        
                        <div class="button-group">
                            <button class="btn btn-primary" onclick="showPage('test-page')">
                                <i class="fas fa-play-circle"></i> Commencer le test
                            </button>
                            <button class="btn btn-secondary" onclick="showPage('results-page')">
                                <i class="fas fa-chart-bar"></i> Voir les résultats
                            </button>
                        </div>
                        
                        <div class="info-box">
                            <h3>
                                <i class="fas fa-info-circle"></i> Comment ça marche ?
                            </h3>
                            <p>
                                Le test comporte plusieurs sections basées sur des modèles scientifiques validés.
                                À la fin, vous recevrez une évaluation détaillée de votre niveau de stress avec des conseils personnalisés.
                            </p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Test Page -->
            <div id="test-page" class="page">
                <div class="form-container">
                    <div class="form-section">
                        <h2 class="section-title">Étude sur le Stress des Infirmier(e)s Instrumentistes</h2>
                        <p>ISPITS de Rabat - Option Infirmier(e) en Bloc Opératoire</p>
                    </div>
                    
                    <form id="surveyForm">
                        <!-- Introduction -->
                        <div class="form-section">
                            <h3 class="section-title">Préambule</h3>
                            <p>
                                Le secteur hospitalier et en particulier le bloc opératoire constitue l'un des environnements les plus complexes, 
                                où de multiples exigences professionnels peuvent entraîner un stress accru pour toute l'équipe chirurgicale, 
                                dont l'infirmier(e) instrumentiste. Ce dernier joue un rôle central dans la sécurité et le bon déroulement 
                                de l'intervention.
                            </p>
                            <p>
                                Pourtant, le stress spécifique vécu par ce professionnel reste peu exploré dans la littérature internationale, 
                                malgré son impact potentiel sur la qualité des soins et la satisfaction professionnelle.
                            </p>
                            <p class="form-section">
                                <strong>Monsieur / Madame,</strong>
                            </p>
                            <p>
                                Nous sommes des étudiantes en soins infirmiers, option Infirmier(e) en Bloc Opératoire à l'ISPITS de Rabat. 
                                Ce questionnaire s'inscrit dans le cadre de notre étude intitulée : 
                                « Le Stress dans la Phase Peropératoire : le Cas des Infirmier(e)s Instrumentistes ».
                            </p>
                            <p>
                                Il vise à identifier et mieux comprendre les facteurs de stress ressentis au cours de la phase peropératoire, 
                                selon le point de vue des infirmier(e)s instrumentistes eux-mêmes.
                            </p>
                            <div class="form-section" style="background-color: #f0f9ff; border-left: 4px solid #38bdf8;">
                                <p><strong>Notez bien :</strong></p>
                                <ul style="padding-left: 20px; margin-top: 10px;">
                                    <li>Il n'y a pas de bonnes ni de mauvaises réponses. C'est votre point de vue qui compte pour nous.</li>
                                    <li>Le présent questionnaire est anonyme, les données ne seront utilisées qu'à des fins scientifiques et ne seront jamais communiquées de façon normative.</li>
                                    <li>Votre contribution permettra de faire progresser la recherche dans un domaine encore trop peu documenté, et de sensibiliser à une problématique souvent taboue dans le contexte hospitalier.</li>
                                </ul>
                            </div>
                        </div>
                        
                        <!-- Consent Form -->
                        <div class="form-section">
                            <h3 class="section-title">Formulaire de consentement</h3>
                            <div class="form-group">
                                <div class="radio-option" style="margin-bottom: 15px;">
                                    <input type="checkbox" id="consent1" required>
                                    <label for="consent1">Je confirme avoir pris connaissance des objectifs et du déroulement de cette étude, et j'accepte librement d'y participer</label>
                                </div>
                                <div class="radio-option" style="margin-bottom: 15px;">
                                    <input type="checkbox" id="consent2" required>
                                    <label for="consent2">Je suis informé(e) que ma participation est volontaire, que je peux refuser d'y participer ou me retirer sans aucune contrainte</label>
                                </div>
                                <div class="radio-option" style="margin-bottom: 15px;">
                                    <input type="checkbox" id="consent3" required>
                                    <label for="consent3">J'ai été informé(e) que toutes mes données personnelles resteront strictement anonymes et confidentielles</label>
                                </div>
                                <div class="radio-option">
                                    <input type="checkbox" id="consent4" required>
                                    <label for="consent4">J'ai reçu les coordonnées du responsable de l'étude, afin d'exercer mes droits d'accès, de rectification et d'opposition, conformément à la loi 09-08.</label>
                                </div>
                            </div>
                        </div>
                        
                        <!-- Identification Section -->
                        <div class="form-section">
                            <h3 class="section-title">Informations d'identification</h3>
                            <div class="form-grid">
                                <div class="form-group">
                                    <label for="specialty">Quel est votre spécialité ?</label>
                                    <input type="text" id="specialty" required>
                                </div>
                                
                                <div class="form-group">
                                    <label>Quel est votre sexe ?</label>
                                    <div class="radio-group">
                                        <div class="radio-option">
                                            <input type="radio" name="gender" value="female" id="female" required>
                                            <label for="female">Femme</label>
                                        </div>
                                        <div class="radio-option">
                                            <input type="radio" name="gender" value="male" id="male">
                                            <label for="male">Homme</label>
                                        </div>
                                    </div>
                                </div>
                                
                                <div class="form-group">
                                    <label for="age">Quel est votre âge ?</label>
                                    <input type="number" id="age" required>
                                </div>
                                
                                <div class="form-group">
                                    <label for="experience">Depuis quand exercez-vous en bloc opératoire ?</label>
                                    <input type="text" id="experience" required>
                                </div>
                                
                                <div class="form-group">
                                    <label>Vous souffrez d'une ou des maladies chroniques ?</label>
                                    <div class="radio-group">
                                        <div class="radio-option">
                                            <input type="radio" name="chronic" value="yes" id="chronic-yes" required>
                                            <label for="chronic-yes">Oui</label>
                                        </div>
                                        <div class="radio-option">
                                            <input type="radio" name="chronic" value="no" id="chronic-no">
                                            <label for="chronic-no">Non</label>
                                        </div>
                                    </div>
                                    <div id="chronic-details" style="display: none; margin-top: 10px;">
                                        <label for="chronic-description">Si oui vous pouvez les mentionner</label>
                                        <textarea id="chronic-description" rows="2"></textarea>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <!-- Karasek Model - Demande psychologique -->
                        <div class="form-section">
                            <h3 class="section-title">Modèle de KARASEK - Demande psychologique</h3>
                            <p style="margin-bottom: 20px; background: #f0f9ff; padding: 10px; border-radius: 8px;">
                                Échelle de réponse : 
                                <strong>1 = Pas du tout d'accord</strong>, 
                                <strong>2 = Pas d'accord</strong>, 
                                <strong>3 = D'accord</strong>, 
                                <strong>4 = Tout à fait d'accord</strong>
                            </p>
                            
                            <div id="demande-questions">
                                <!-- Questions will be generated here -->
                            </div>
                        </div>
                        
                        <!-- Karasek Model - Latitude décisionnelle -->
                        <div class="form-section">
                            <h3 class="section-title">Modèle de KARASEK - Latitude décisionnelle</h3>
                            <p style="margin-bottom: 20px; background: #f0f9ff; padding: 10px; border-radius: 8px;">
                                Échelle de réponse : 
                                <strong>1 = Pas du tout d'accord</strong>, 
                                <strong>2 = Pas d'accord</strong>, 
                                <strong>3 = D'accord</strong>, 
                                <strong>4 = Tout à fait d'accord</strong>
                            </p>
                            
                            <div id="latitude-questions">
                                <!-- Questions will be generated here -->
                            </div>
                        </div>
                        
                        <!-- Karasek Model - Soutien social -->
                        <div class="form-section">
                            <h3 class="section-title">Modèle de KARASEK - Soutien social</h3>
                            <p style="margin-bottom: 20px; background: #f0f9ff; padding: 10px; border-radius: 8px;">
                                Échelle de réponse : 
                                <strong>1 = Pas du tout d'accord</strong>, 
                                <strong>2 = Pas d'accord</strong>, 
                                <strong>3 = D'accord</strong>, 
                                <strong>4 = Tout à fait d'accord</strong>
                            </p>
                            
                            <div id="soutien-questions">
                                <!-- Questions will be generated here -->
                            </div>
                        </div>
                        
                        <!-- Siegrist Model - Récompense -->
                        <div class="form-section">
                            <h3 class="section-title">Modèle de SIEGRIST - Récompense</h3>
                            <p style="margin-bottom: 20px; background: #f0f9ff; padding: 10px; border-radius: 8px;">
                                Échelle de réponse : 
                                <strong>1 = Pas du tout d'accord</strong>, 
                                <strong>2 = Pas d'accord</strong>, 
                                <strong>3 = D'accord</strong>, 
                                <strong>4 = Tout à fait d'accord</strong>
                            </p>
                            
                            <div id="recompense-questions">
                                <!-- Questions will be generated here -->
                            </div>
                        </div>
                        
                        <div class="form-actions">
                            <button type="button" class="btn btn-secondary" onclick="showPage('home-page')">
                                <i class="fas fa-arrow-left"></i> Retour à l'accueil
                            </button>
                            <button type="submit" class="btn btn-primary">
                                <i class="fas fa-paper-plane"></i> Valider le questionnaire
                            </button>
                        </div>
                    </form>
                </div>
            </div>

            <!-- Results Page -->
            <div id="results-page" class="page">
                <div class="results-container">
                    <div class="results-header">
                        <h2>Résultats des Évaluations de Stress</h2>
                        <p>Analyse anonyme des niveaux de stress professionnel</p>
                    </div>
                    
                    <div class="user-results">
                        <h3>Votre Évaluation de Stress</h3>
                        <div class="stress-level" id="user-stress-level">0%</div>
                        
                        <div class="stress-meter">
                            <div class="stress-progress" id="stress-progress" style="width: 0%"></div>
                        </div>
                        
                        <div class="stress-description" id="stress-description">
                            Votre niveau de stress est en cours d'évaluation
                        </div>
                        
                        <div class="stress-interpretation" id="stress-interpretation">
                            <h4>Interprétation :</h4>
                            <p id="interpretation-text"></p>
                            
                            <h4 style="margin-top: 15px;">Conseils personnalisés :</h4>
                            <ul class="advice-list" id="advice-list">
                                <!-- Advice will be inserted here -->
                            </ul>
                        </div>
                    </div>
                    
                    <div class="participants-results">
                        <h3 class="section-title">Résultats des Participants</h3>
                        
                        <table>
                            <thead>
                                <tr>
                                    <th>Participant</th>
                                    <th>Niveau de Stress</th>
                                    <th>Date</th>
                                </tr>
                            </thead>
                            <tbody id="results-body">
                                <!-- Results will be inserted here dynamically -->
                            </tbody>
                        </table>
                        
                        <div class="stats-container">
                            <div class="stat-card">
                                <h3>Niveau de Stress Moyen</h3>
                                <div class="stat-value" id="average-stress">0%</div>
                            </div>
                            <div class="stat-card">
                                <h3>Nombre de Participants</h3>
                                <div class="stat-value" id="participant-count">0</div>
                            </div>
                            <div class="stat-card">
                                <h3>Dernière Participation</h3>
                                <div class="stat-value" id="last-participation">-</div>
                            </div>
                        </div>
                    </div>
                    
                    <div style="text-align: center; margin-top: 30px;">
                        <button class="btn btn-primary" onclick="showPage('home-page')">
                            <i class="fas fa-home"></i> Retour à l'accueil
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <p><strong>Idée :</strong> Oumaima CHTIOUI</p>
                <p><strong>Développeur :</strong> Yassine TAOUCH</p>
                <p><strong>Contact :</strong> coumaima989@gmail.com</p>
                <p>ISPIT de Rabat, Promotion 2024/2025</p>
            </div>
        </div>
    </footer>

    <script>
        // Page navigation
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId).classList.add('active');
            
            // Update results when showing results page
            if(pageId === 'results-page') {
                updateResults();
            }
        }
        
        // Chronic disease details toggle
        document.querySelectorAll('input[name="chronic"]').forEach(radio => {
            radio.addEventListener('change', function() {
                const details = document.getElementById('chronic-details');
                details.style.display = this.value === 'yes' ? 'block' : 'none';
            });
        });
        
        // Generate questions from the Karasek and Siegrist models
        function generateQuestions() {
            // Demande psychologique questions
            const demandeQuestions = [
                {id: "q10", text: "Q10 – Les interventions me demandent de travailler très rapidement"},
                {id: "q12", text: "Q12 – On me confie une charge de travail excessive"},
                {id: "q13", text: "Q13 – Je dispose suffisamment de temps pour préparer et exécuter correctement mon rôle d'instrumentiste"},
                {id: "q14", text: "Q14 – Je reçois parfois des consignes contradictoires de la part du chirurgien ou de l'équipe"},
                {id: "q11", text: "Q11 – Mon travail me demande de travailler intensément"},
                {id: "q15", text: "Q15 – Mon rôle d'instrumentiste me demande de rester concentré(e) intensément pendant toute l'intervention"},
                {id: "q16", text: "Q16 – Mon travail est souvent interrompu (modification de protocole, changement d'instrumentation, imprévus)"},
                {id: "q17", text: "Q17 – Je dois souvent enchaîner les interventions sans réelle pause ni temps de préparation"},
                {id: "q18", text: "Q18 – J'attends régulièrement les consignes d'autres membres de l'équipe (chirurgien, anesthésiste) pour avancer"}
            ];
            
            // Latitude décisionnelle questions
            const latitudeQuestions = [
                {id: "q4", text: "Q4 – Mon rôle me permet de prendre des décisions souvent moi-même"},
                {id: "q6", text: "Q6 – Dans ma tâche, j'ai très peu de liberté pour décider comment je fais mon travail"},
                {id: "q8", text: "Q8 – J'ai la possibilité d'influencer le déroulement de mon travail"},
                {id: "q2", text: "Q2 – Dans mon travail, j'effectue des tâches répétitives"},
                {id: "q5", text: "Q5 – Mon travail demande un haut niveau de compétence (durant les interventions chirurgicales)"},
                {id: "q7", text: "Q7 – Dans mon travail, j'ai des activités variées (en salle d'opération)"},
                {id: "q1", text: "Q1 – Dans mon travail, je dois apprendre des choses nouvelles"},
                {id: "q3", text: "Q3 – Mon travail me demande d'être créatif"},
                {id: "q9", text: "Q9 – J'ai des occasions d'apprendre de nouvelles techniques ou d'approfondir mes savoirs"}
            ];
            
            // Soutien social questions
            const soutienQuestions = [
                {id: "q22", text: "Q22 – Le chirurgien réussit facilement à faire collaborer ses subordonnés au bloc opératoire"},
                {id: "q21", text: "Q21 – Le chirurgien m'aide à mener ma tâche à bien pendant les interventions"},
                {id: "q23", text: "Q23 – Les collègues avec qui je travaille en salle opératoire sont des gens professionnellement compétents"},
                {id: "q26", text: "Q26 – Les collègues avec qui je travaille me soutiennent dans mes tâches lors des situations complexes"},
                {id: "q20", text: "Q20 – Le chirurgien (ou mon supérieur hiérarchique) est attentif à mes remarques et observations pendant l'intervention"},
                {id: "q19", text: "Q19 – Le chirurgien se sent concerné par le bien-être de ses subordonnés dans le bloc opératoire"},
                {id: "q25", text: "Q25 – Les collègues avec qui je travaille sont amicaux au sein de l'équipe opératoire"},
                {id: "q24", text: "Q24 – Je me sens considéré(e) par mes collègues"}
            ];
            
            // Récompense questions
            const recompenseQuestions = [
                {id: "q7s", text: "Q7 – Je reçois le respect que je mérite de la part des chirurgiens"},
                {id: "q8s", text: "Q8 – Je reçois le respect que je mérite de la part de mes collègues du bloc opératoire"},
                {id: "q9s", text: "Q9 – En situation difficile (urgence, imprévu), je bénéficie d'un soutien adéquat de la part de l'équipe chirurgicale"},
                {id: "q10s", text: "Q10 – Je me sens parfois traité(e) de façon injuste dans le bloc opératoire"},
                {id: "q11s", text: "Q11 – Je suis en train de vivre ou je m'attends à vivre un changement indésirable dans ma situation de travail"},
                {id: "q12s", text: "Q12 – Je vois peu d'opportunités de progression dans ma carrière"},
                {id: "q13s", text: "Q13 – Ma sécurité d'emploi est menacée"},
                {id: "q14s", text: "Q14 – Mon poste actuel correspond à mes compétences et à ma formation"},
                {id: "q15s", text: "Q15 – Vu tous mes efforts, je reçois le respect et l'estime que je mérite à mon travail"},
                {id: "q16s", text: "Q16 – Vu tous mes efforts, mes perspectives d'évolution professionnelle sont satisfaisantes"},
                {id: "q17s", text: "Q17 – Vu les exigences de mon travail au bloc, mon salaire est satisfaisant"}
            ];
            
            // Generate questions for each section
            generateQuestionSection('demande-questions', demandeQuestions);
            generateQuestionSection('latitude-questions', latitudeQuestions);
            generateQuestionSection('soutien-questions', soutienQuestions);
            generateQuestionSection('recompense-questions', recompenseQuestions);
        }
        
        // Generate questions for a specific section
        function generateQuestionSection(sectionId, questions) {
            const container = document.getElementById(sectionId);
            container.innerHTML = '';
            
            questions.forEach((q, index) => {
                const questionHTML = `
                    <div class="question-card">
                        <p>${q.text}</p>
                        <div class="options-grid">
                            ${[1,2,3,4].map(val => `
                                <label class="option-label">
                                    <input type="radio" name="${q.id}" value="${val}" required>
                                    <span>${val}</span>
                                </label>
                            `).join('')}
                        </div>
                    </div>
                `;
                container.innerHTML += questionHTML;
            });
        }
        
        // Calculate stress level using Karasek method
        function calculateStressLevel() {
            // Get all values
            const values = {};
            document.querySelectorAll('input[type="radio"]:checked').forEach(input => {
                values[input.name] = parseInt(input.value);
            });
            
            // Calculate Demande psychologique
            const demande = (
                (values['q10'] || 0) +
                (values['q11'] || 0) +
                (values['q12'] || 0) +
                (5 - (values['q13'] || 0)) + // reversed
                (values['q14'] || 0) +
                (values['q15'] || 0) +
                (values['q16'] || 0) +
                (values['q17'] || 0) +
                (values['q18'] || 0)
            );
            
            // Calculate Autonomie
            const autonomie = 4 * (
                (values['q4'] || 0) +
                (5 - (values['q6'] || 0)) + // reversed
                (values['q8'] || 0)
            );
            
            // Calculate Utilisation des compétences
            const utilisation = 2 * (
                (values['q1'] || 0) +
                (5 - (values['q2'] || 0)) + // reversed
                (values['q3'] || 0) +
                (values['q5'] || 0) +
                (values['q7'] || 0) +
                (values['q9'] || 0)
            );
            
            // Calculate Latitude décisionnelle
            const latitude = autonomie + utilisation;
            
            // Calculate overall stress level (percentage)
            const maxDemande = 9 * 4; // 9 questions, max 4 each
            const maxLatitude = 12 * 4; // Based on calculation method
            
            // Stress level based on demand and autonomy
            const stressLevel = Math.round(
                (demande / maxDemande * 70) + 
                ((maxLatitude - latitude) / maxLatitude * 30)
            );
            
            return {
                stressLevel: Math.min(100, Math.max(0, stressLevel)),
                demande: demande,
                latitude: latitude
            };
        }
        
        // Get interpretation based on stress level
        function getInterpretation(level) {
            if(level < 40) return "Le sujet est détendu, s'il bénéficie d'une faible demande psychologique et d'une grande autonomie pour réaliser son travail.";
            if(level < 70) return "Le sujet est actif, s'il dispose d'une forte demande psychologique mais également d'une grande autonomie.";
            return "Le sujet est passif, s'il dispose à la fois d'une faible demande psychologique et d'une faible autonomie.";
        }
        
        // Get advice based on stress level
        function getAdvice(level) {
            const advice = [];
            
            if(level < 40) {
                advice.push("Maintenez vos bonnes habitudes de gestion du stress");
                advice.push("Continuez à prendre des pauses régulières pendant votre travail");
                advice.push("Pratiquez des activités relaxantes en dehors du travail");
            } 
            else if(level < 70) {
                advice.push("Prenez des pauses régulières pendant votre travail");
                advice.push("Pratiquez des techniques de respiration profonde");
                advice.push("Établissez des limites claires entre vie professionnelle et personnelle");
                advice.push("Consultez un spécialiste si le stress persiste");
            } 
            else {
                advice.push("Consultez un professionnel de santé pour évaluer votre situation");
                advice.push("Mettez en place des techniques de relaxation quotidiennes");
                advice.push("Envisagez un soutien psychologique spécialisé");
                advice.push("Parlez à votre supérieur de votre charge de travail");
                advice.push("Prenez du temps pour des activités qui vous ressourcent");
            }
            
            return advice;
        }
        
        // Update results display
        function updateResults() {
            const results = JSON.parse(localStorage.getItem('stressResults')) || [];
            const resultsBody = document.getElementById('results-body');
            resultsBody.innerHTML = '';
            
            let totalStress = 0;
            
            if(results.length === 0) {
                resultsBody.innerHTML = `
                    <tr>
                        <td colspan="3" class="text-center py-4">
                            Aucun résultat disponible pour le moment.
                        </td>
                    </tr>
                `;
            } else {
                results.forEach((result, index) => {
                    totalStress += result.stressLevel;
                    
                    let stressClass = 'stress-low';
                    if(result.stressLevel >= 40) stressClass = 'stress-medium';
                    if(result.stressLevel >= 70) stressClass = 'stress-high';
                    
                    resultsBody.innerHTML += `
                        <tr>
                            <td>
                                <div class="participant-name">Inconnu(e) ${index + 1}</div>
                                <div class="participant-specialty">${result.specialty}</div>
                            </td>
                            <td>
                                <div class="stress-badge ${stressClass}">${result.stressLevel}%</div>
                                <div class="progress-bar">
                                    <div class="progress-value" style="width: ${result.stressLevel}%"></div>
                                </div>
                            </td>
                            <td>${result.timestamp}</td>
                        </tr>
                    `;
                });
            }
            
            // Update stats
            document.getElementById('participant-count').textContent = results.length;
            document.getElementById('average-stress').textContent = results.length ? 
                Math.round(totalStress / results.length) + '%' : '0%';
            document.getElementById('last-participation').textContent = results.length ? 
                results[results.length - 1].timestamp : '-';
        }
        
        // Initialize when page loads
        document.addEventListener('DOMContentLoaded', function() {
            generateQuestions();
            
            // Form submission
            document.getElementById('surveyForm').addEventListener('submit', function(e) {
                e.preventDefault();
                
                // Calculate stress level
                const result = calculateStressLevel();
                const stressLevel = result.stressLevel;
                const interpretation = getInterpretation(stressLevel);
                const advice = getAdvice(stressLevel);
                
                // Save result to localStorage
                const results = JSON.parse(localStorage.getItem('stressResults')) || [];
                const newResult = {
                    id: Date.now(),
                    stressLevel: stressLevel,
                    timestamp: new Date().toLocaleDateString('fr-FR'),
                    specialty: document.getElementById('specialty').value,
                    interpretation: interpretation,
                    advice: advice
                };
                results.push(newResult);
                localStorage.setItem('stressResults', JSON.stringify(results));
                
                // Update user results display
                document.getElementById('user-stress-level').textContent = stressLevel + '%';
                document.getElementById('stress-progress').style.width = stressLevel + '%';
                document.getElementById('interpretation-text').textContent = interpretation;
                
                // Update stress description
                if(stressLevel < 40) {
                    document.getElementById('stress-description').textContent = 
                        "Votre niveau de stress est dans la norme pour votre profession.";
                } else if(stressLevel < 70) {
                    document.getElementById('stress-description').textContent = 
                        "Votre niveau de stress nécessite une attention particulière.";
                } else {
                    document.getElementById('stress-description').textContent = 
                        "Votre niveau de stress est élevé et mérite une prise en charge professionnelle.";
                }
                
                // Add advice
                const adviceList = document.getElementById('advice-list');
                adviceList.innerHTML = '';
                advice.forEach(item => {
                    adviceList.innerHTML += `<li>${item}</li>`;
                });
                
                // Show results page
                showPage('results-page');
            });
        });
    </script>
</body>
</html>
