<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tester votre stress</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f0f9ff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }
        
        .medical-icon {
            color: #38bdf8;
            font-size: 2rem;
            margin-bottom: 1rem;
        }
        
        .btn-primary {
            background-color: #38bdf8;
            color: white;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px rgba(56, 189, 248, 0.3);
        }
        
        .btn-primary:hover {
            background-color: #0ea5e9;
            transform: translateY(-2px);
            box-shadow: 0 6px 8px rgba(56, 189, 248, 0.4);
        }
        
        .btn-secondary {
            background-color: white;
            color: #38bdf8;
            border: 2px solid #38bdf8;
            transition: all 0.3s ease;
        }
        
        .btn-secondary:hover {
            background-color: #f8fafc;
            transform: translateY(-2px);
            box-shadow: 0 4px 6px rgba(56, 189, 248, 0.2);
        }
        
        .footer {
            background-color: white;
            border-top: 2px solid #e0f2fe;
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                transform: scale(1);
            }
        }
        
        /* Styles from second code */
        .header {
            background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 100%);
            color: white;
        }
        
        .consent-box {
            border-left: 4px solid #3b82f6;
            background-color: #f8fafc;
        }
        
        .section-title {
            border-bottom: 2px solid #3b82f6;
        }
        
        .question-card {
            transition: all 0.3s ease;
            border-left: 3px solid transparent;
        }
        
        .question-card:hover {
            background-color: #f8fafc;
            border-left-color: #3b82f6;
        }
        
        .radio-option {
            display: flex;
            align-items: center;
            margin-right: 1rem;
        }
        
        .radio-input {
            appearance: none;
            width: 18px;
            height: 18px;
            border: 2px solid #94a3b8;
            border-radius: 50%;
            margin-right: 0.5rem;
            cursor: pointer;
            position: relative;
        }
        
        .radio-input:checked {
            border-color: #3b82f6;
        }
        
        .radio-input:checked::after {
            content: '';
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #3b82f6;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        
        .thank-you {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Page transitions */
        .page {
            display: none;
            width: 100%;
        }
        
        .page.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        /* Results page styles */
        .result-card {
            background: white;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }
        
        .result-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px rgba(0,0,0,0.1);
        }
        
        .progress-bar {
            height: 10px;
            border-radius: 5px;
            background: #e0f2fe;
            overflow: hidden;
        }
        
        .progress-value {
            height: 100%;
            background: #38bdf8;
            border-radius: 5px;
        }
        
        .stress-level {
            padding: 5px 10px;
            border-radius: 20px;
            font-weight: 500;
        }
        
        .stress-low {
            background: #dcfce7;
            color: #16a34a;
        }
        
        .stress-medium {
            background: #fef9c3;
            color: #ca8a04;
        }
        
        .stress-high {
            background: #fee2e2;
            color: #dc2626;
        }
    </style>
</head>
<body class="flex flex-col min-h-screen">
    <!-- Header -->
    <header class="bg-white shadow-sm py-6">
        <div class="container mx-auto px-4 text-center">
            <h1 class="text-3xl md:text-4xl font-bold text-sky-500 mb-2">Tester votre stress</h1>
            <p class="text-gray-600">Évaluez votre niveau de stress en quelques minutes</p>
        </div>
    </header>

    <!-- Main Content - Pages -->
    <main class="flex-grow container mx-auto px-4 py-8">
        <!-- Home Page -->
        <div id="home-page" class="page active">
            <div class="bg-white rounded-xl shadow-lg p-8 max-w-2xl w-full text-center mx-auto">
                <div class="flex justify-center space-x-6 mb-8">
                    <i class="fas fa-heartbeat medical-icon pulse"></i>
                    <i class="fas fa-stethoscope medical-icon"></i>
                    <i class="fas fa-brain medical-icon pulse" style="animation-delay: 0.5s;"></i>
                </div>
                
                <h2 class="text-2xl font-semibold text-gray-800 mb-6">Bienvenue sur notre plateforme d'évaluation du stress</h2>
                
                <p class="text-gray-600 mb-8">
                    Ce test simple et rapide vous aidera à comprendre votre niveau de stress actuel. 
                    Répondez honnêtement aux questions pour obtenir une évaluation précise.
                </p>
                
                <div class="flex flex-col sm:flex-row justify-center gap-4 mb-8">
                    <button onclick="showPage('test-page')" class="btn-primary py-3 px-6 rounded-lg font-medium text-lg">
                        <i class="fas fa-play-circle mr-2"></i> Tester votre stress
                    </button>
                    <button onclick="showPage('results-page')" class="btn-secondary py-3 px-6 rounded-lg font-medium text-lg">
                        <i class="fas fa-chart-bar mr-2"></i> Voir les résultats
                    </button>
                </div>
                
                <div class="bg-blue-50 rounded-lg p-4 border border-blue-100">
                    <h3 class="text-blue-600 font-medium mb-2 flex items-center justify-center">
                        <i class="fas fa-info-circle mr-2"></i> Comment ça marche ?
                    </h3>
                    <p class="text-gray-600 text-sm">
                        Le test comporte 10 questions simples sur vos récentes expériences. 
                        À la fin, vous recevrez une évaluation de votre niveau de stress avec des conseils personnalisés.
                    </p>
                </div>
            </div>
        </div>

        <!-- Test Page -->
        <div id="test-page" class="page">
            <form id="surveyForm" class="max-w-4xl mx-auto">
                <!-- Header -->
                <div class="header rounded-lg shadow-md p-6 mb-8">
                    <div class="flex items-center">
                        <i class="fas fa-hospital-alt text-3xl mr-4"></i>
                        <div>
                            <h1 class="text-2xl font-bold">Étude sur le Stress des Infirmier(e)s Instrumentistes</h1>
                            <p class="opacity-90">ISPITS de Rabat - Option Infirmier(e) en Bloc Opératoire</p>
                        </div>
                    </div>
                </div>

                <!-- Introduction -->
                <div class="bg-white rounded-lg shadow-md p-6 mb-8">
                    <h2 class="text-xl font-semibold mb-4 text-blue-800">Préambule</h2>
                    <div class="space-y-4 text-gray-700">
                        <p>Le secteur hospitalier et en particulier le bloc opératoire constitue l'un des environnements les plus complexes, où de multiples exigences professionnels peuvent entraîner un stress accru pour toute l'équipe chirurgicale, dont l'infirmier(e) instrumentiste. Ce dernier joue un rôle central dans la sécurité et le bon déroulement de l'intervention.</p>
                        <p>Pourtant, le stress spécifique vécu par ce professionnel reste peu exploré dans la littérature internationale, malgré son impact potentiel sur la qualité des soins et la satisfaction professionnelle.</p>
                        <p class="font-medium">Monsieur / Madame,</p>
                        <p>Nous sommes des étudiantes en soins infirmiers, option Infirmier(e) en Bloc Opératoire à l'ISPITS de Rabat. Ce questionnaire s'inscrit dans le cadre de notre étude intitulée : « Le Stress dans la Phase Peropératoire : le Cas des Infirmier(e)s Instrumentistes ».</p>
                        <p>Il vise à identifier et mieux comprendre les facteurs de stress ressentis au cours de la phase peropératoire, selon le point de vue des infirmier(e)s instrumentistes eux-mêmes.</p>
                        <div class="consent-box p-4 my-4">
                            <p class="font-semibold text-blue-800">Notez bien :</p>
                            <ul class="list-disc pl-5 space-y-2">
                                <li>Il n'y a pas de bonnes ni de mauvaises réponses. C'est votre point de vue qui compte pour nous.</li>
                                <li>Le présent questionnaire est anonyme, les données ne seront utilisées qu'à des fins scientifiques et ne seront jamais communiquées de façon normative.</li>
                                <li>Votre contribution permettra de faire progresser la recherche dans un domaine encore trop peu documenté, et de sensibiliser à une problématique souvent taboue dans le contexte hospitalier.</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <!-- Consent Form -->
                <div class="bg-white rounded-lg shadow-md p-6 mb-8">
                    <h2 class="text-xl font-semibold mb-4 text-blue-800">Formulaire de consentement</h2>
                    <div class="space-y-4">
                        <div class="flex items-start">
                            <input type="checkbox" id="consent1" class="mt-1 mr-3 h-5 w-5 text-blue-600" required>
                            <label for="consent1" class="text-gray-700">Je confirme avoir pris connaissance des objectifs et du déroulement de cette étude, et j'accepte librement d'y participer</label>
                        </div>
                        <div class="flex items-start">
                            <input type="checkbox" id="consent2" class="mt-1 mr-3 h-5 w-5 text-blue-600" required>
                            <label for="consent2" class="text-gray-700">Je suis informé(e) que ma participation est volontaire, que je peux refuser d'y participer ou me retirer sans aucune contrainte</label>
                        </div>
                        <div class="flex items-start">
                            <input type="checkbox" id="consent3" class="mt-1 mr-3 h-5 w-5 text-blue-600" required>
                            <label for="consent3" class="text-gray-700">J'ai été informé(e) que toutes mes données personnelles resteront strictement anonymes et confidentielles</label>
                        </div>
                        <div class="flex items-start">
                            <input type="checkbox" id="consent4" class="mt-1 mr-3 h-5 w-5 text-blue-600" required>
                            <label for="consent4" class="text-gray-700">J'ai reçu les coordonnées du responsable de l'étude, afin d'exercer mes droits d'accès, de rectification et d'opposition, conformément à la loi 09-08.</label>
                        </div>
                    </div>
                </div>

                <!-- Identification Section -->
                <div class="bg-white rounded-lg shadow-md p-6 mb-8">
                    <h2 class="text-xl font-semibold mb-4 text-blue-800">Informations d'identification</h2>
                    <div class="grid md:grid-cols-2 gap-6">
                        <div>
                            <label for="specialty" class="block text-gray-700 mb-2">Quel est votre spécialité ?</label>
                            <input type="text" id="specialty" class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500" required>
                        </div>
                        <div>
                            <label class="block text-gray-700 mb-2">Quel est votre sexe ?</label>
                            <div class="flex space-x-4">
                                <label class="inline-flex items-center">
                                    <input type="radio" name="gender" value="female" class="radio-input" required>
                                    <span class="ml-2">Femme</span>
                                </label>
                                <label class="inline-flex items-center">
                                    <input type="radio" name="gender" value="male" class="radio-input">
                                    <span class="ml-2">Homme</span>
                                </label>
                            </div>
                        </div>
                        <div>
                            <label for="age" class="block text-gray-700 mb-2">Quel est votre âge ?</label>
                            <input type="number" id="age" class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500" required>
                        </div>
                        <div>
                            <label for="experience" class="block text-gray-700 mb-2">Depuis quand exercez-vous en bloc opératoire ?</label>
                            <input type="text" id="experience" class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500" required>
                        </div>
                        <div>
                            <label class="block text-gray-700 mb-2">Vous souffrez d'une ou des maladies chroniques ?</label>
                            <div class="flex space-x-4 mb-2">
                                <label class="inline-flex items-center">
                                    <input type="radio" name="chronic" value="yes" class="radio-input" required>
                                    <span class="ml-2">Oui</span>
                                </label>
                                <label class="inline-flex items-center">
                                    <input type="radio" name="chronic" value="no" class="radio-input">
                                    <span class="ml-2">Non</span>
                                </label>
                            </div>
                            <div id="chronic-details" class="hidden">
                                <label for="chronic-description" class="block text-gray-700 mb-2">Si oui vous pouvez les mentionner</label>
                                <textarea id="chronic-description" rows="2" class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"></textarea>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Karasek Model - Demande psychologique -->
                <div class="bg-white rounded-lg shadow-md p-6 mb-8">
                    <h2 class="text-xl font-semibold mb-6 pb-2 section-title">Modèle de KARASEK - Demande psychologique</h2>
                    <p class="text-gray-600 mb-4">Échelle de réponse : 
                        <span class="font-medium">1 = Pas du tout d'accord</span>, 
                        <span class="font-medium">2 = Pas d'accord</span>, 
                        <span class="font-medium">3 = D'accord</span>, 
                        <span class="font-medium">4 = Tout à fait d'accord</span>
                    </p>
                    
                    <div class="space-y-6">
                        <!-- Question 10 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q10 – Les interventions me demandent de travailler très rapidement</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q10" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q10" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q10" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q10" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 12 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q12 – On me confie une charge de travail excessive</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q12" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q12" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q12" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q12" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 13 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q13 – Je dispose suffisamment de temps pour préparer et exécuter correctement mon rôle d'instrumentiste</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q13" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q13" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q13" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q13" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 14 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q14 – Je reçois parfois des consignes contradictoires de la part du chirurgien ou de l'équipe</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q14" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q14" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q14" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q14" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 11 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q11 – Mon travail me demande de travailler intensément</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q11" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q11" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q11" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q11" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 15 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q15 – Mon rôle d'instrumentiste me demande de rester concentré(e) intensément pendant toute l'intervention</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q15" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q15" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q15" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q15" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 16 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q16 – Mon travail est souvent interrompu (modification de protocole, changement d'instrumentation, imprévus)</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q16" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q16" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q16" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q16" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 17 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q17 – Je dois souvent enchaîner les interventions sans réelle pause ni temps de préparation</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q17" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q17" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q17" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q17" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 18 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q18 – J'attends régulièrement les consignes d'autres membres de l'équipe (chirurgien, anesthésiste) pour avancer</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q18" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q18" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q18" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q18" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Karasek Model - Latitude décisionnelle -->
                <div class="bg-white rounded-lg shadow-md p-6 mb-8">
                    <h2 class="text-xl font-semibold mb-6 pb-2 section-title">Modèle de KARASEK - Latitude décisionnelle</h2>
                    <p class="text-gray-600 mb-4">Échelle de réponse : 
                        <span class="font-medium">1 = Pas du tout d'accord</span>, 
                        <span class="font-medium">2 = Pas d'accord</span>, 
                        <span class="font-medium">3 = D'accord</span>, 
                        <span class="font-medium">4 = Tout à fait d'accord</span>
                    </p>
                    
                    <div class="space-y-6">
                        <!-- Question 4 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q4 – Mon rôle me permet de prendre des décisions souvent moi-même</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q4" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q4" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q4" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q4" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 6 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q6 – Dans ma tâche, j'ai très peu de liberté pour décider comment je fais mon travail</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q6" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q6" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q6" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q6" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 8 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q8 – J'ai la possibilité d'influencer le déroulement de mon travail</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q8" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q8" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q8" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q8" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>

                        <!-- Question 2 -->
                        <div class="question-card p-4 border rounded-lg">
                            <p class="font-medium mb-3">Q2 – Dans mon travail, j'effectue des tâches répétitives</p>
                            <div class="flex flex-wrap gap-4">
                                <label class="radio-option">
                                    <input type="radio" name="q2" value="1" class="radio-input" required>
                                    <span>1</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q2" value="2" class="radio-input">
                                    <span>2</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q2" value="3" class="radio-input">
                                    <span>3</span>
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="q2" value="4" class="radio-input">
                                    <span>4</span>
                                </label>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Submit Button -->
                <div class="flex justify-between mt-8 mb-12">
                    <button type="button" onclick="showPage('home-page')" class="btn-primary text-white px-6 py-3 rounded-lg font-medium">
                        <i class="fas fa-home mr-2"></i>Retour à l'accueil
                    </button>
                    <button type="submit" class="btn-primary text-white px-6 py-3 rounded-lg font-medium">
                        <i class="fas fa-paper-plane mr-2"></i>Valider le questionnaire
                    </button>
                </div>
            </form>
        </div>

        <!-- Results Page -->
        <div id="results-page" class="page">
            <div class="max-w-4xl mx-auto">
                <div class="header rounded-lg shadow-md p-6 mb-8">
                    <div class="flex items-center">
                        <i class="fas fa-chart-bar text-3xl mr-4"></i>
                        <div>
                            <h1 class="text-2xl font-bold">Résultats des Évaluations de Stress</h1>
                            <p class="opacity-90">Analyse anonyme des niveaux de stress</p>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-lg shadow-md p-6 mb-8">
                    <h2 class="text-xl font-semibold mb-6 pb-2 section-title">Résultats des Participants</h2>
                    
                    <div class="overflow-x-auto">
                        <table class="min-w-full divide-y divide-gray-200">
                            <thead class="bg-gray-50">
                                <tr>
                                    <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Participant</th>
                                    <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Niveau de Stress</th>
                                    <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Détail</th>
                                </tr>
                            </thead>
                            <tbody class="bg-white divide-y divide-gray-200" id="results-body">
                                <!-- Results will be inserted here dynamically -->
                            </tbody>
                        </table>
                    </div>

                    <div class="mt-8">
                        <h3 class="text-lg font-semibold mb-4">Statistiques Globales</h3>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                            <div class="bg-blue-50 p-4 rounded-lg">
                                <p class="text-blue-700 font-semibold">Niveau de Stress Moyen</p>
                                <p class="text-3xl font-bold text-blue-800" id="average-stress">0%</p>
                            </div>
                            <div class="bg-green-50 p-4 rounded-lg">
                                <p class="text-green-700 font-semibold">Participants</p>
                                <p class="text-3xl font-bold text-green-800" id="participant-count">0</p>
                            </div>
                            <div class="bg-purple-50 p-4 rounded-lg">
                                <p class="text-purple-700 font-semibold">Dernière Participation</p>
                                <p class="text-xl font-bold text-purple-800" id="last-participation">-</p>
                            </div>
                        </div>
                    </div>

                    <div class="mt-8">
                        <button onclick="showPage('home-page')" class="btn-primary text-white px-6 py-3 rounded-lg font-medium">
                            <i class="fas fa-home mr-2"></i>Retour à l'accueil
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer class="footer py-6 mt-auto">
        <div class="container mx-auto px-4">
            <div class="text-center text-gray-600 text-sm">
                <p><span class="font-medium">Idée :</span> Oumaima CHTIOUI</p>
                <p><span class="font-medium">Développeur :</span> Yassine TAOUCH</p>
                <p><span class="font-medium">Contact :</span> coumaima989@gmail.com</p>
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
            
            // If showing results page, update results
            if(pageId === 'results-page') {
                updateResults();
            }
        }
        
        // Chronic disease details toggle
        document.querySelectorAll('input[name="chronic"]').forEach(radio => {
            radio.addEventListener('change', function() {
                const details = document.getElementById('chronic-details');
                details.classList.toggle('hidden', this.value !== 'yes');
            });
        });
        
        // Form submission
        document.getElementById('surveyForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Calculate stress level
            const demandQuestions = ['q10', 'q11', 'q12', 'q14', 'q15', 'q16', 'q17', 'q18'];
            const controlQuestions = ['q2', 'q4', 'q6', 'q8'];
            
            let demandScore = 0;
            let controlScore = 0;
            
            // Calculate demand score
            demandQuestions.forEach(q => {
                const value = document.querySelector(`input[name="${q}"]:checked`)?.value;
                if(value) {
                    // For q13 we need to reverse the score (handled separately)
                    demandScore += parseInt(value);
                }
            });
            
            // Handle q13 separately (reversed)
            const q13Value = document.querySelector('input[name="q13"]:checked')?.value;
            if(q13Value) {
                demandScore += (5 - parseInt(q13Value)); // Reverse score (1->4, 2->3, etc.)
            }
            
            // Calculate control score
            controlQuestions.forEach(q => {
                const value = document.querySelector(`input[name="${q}"]:checked`)?.value;
                if(value) {
                    // Questions 2 and 6 are reversed
                    if(q === 'q2' || q === 'q6') {
                        controlScore += (5 - parseInt(value));
                    } else {
                        controlScore += parseInt(value);
                    }
                }
            });
            
            // Calculate overall stress (demand / control ratio)
            const totalDemand = demandQuestions.length + 1; // +1 for q13
            const totalControl = controlQuestions.length;
            
            const demandPercentage = Math.round((demandScore / (totalDemand * 4)) * 100);
            const controlPercentage = Math.round((controlScore / (totalControl * 4)) * 100);
            const stressLevel = Math.round(demandPercentage - (controlPercentage / 2));
            
            // Save result to localStorage
            const results = JSON.parse(localStorage.getItem('stressResults')) || [];
            const newResult = {
                id: Date.now(),
                stressLevel: Math.min(100, Math.max(0, stressLevel)),
                timestamp: new Date().toLocaleString(),
                specialty: document.getElementById('specialty').value
            };
            results.push(newResult);
            localStorage.setItem('stressResults', JSON.stringify(results));
            
            // Show results page
            showPage('results-page');
        });
        
        // Update results display
        function updateResults() {
            const results = JSON.parse(localStorage.getItem('stressResults')) || [];
            const resultsBody = document.getElementById('results-body');
            resultsBody.innerHTML = '';
            
            let totalStress = 0;
            
            if(results.length === 0) {
                resultsBody.innerHTML = `
                    <tr>
                        <td colspan="3" class="px-6 py-4 text-center text-gray-500">
                            Aucun résultat disponible pour le moment.
                        </td>
                    </tr>
                `;
            } else {
                results.forEach((result, index) => {
                    totalStress += result.stressLevel;
                    
                    let stressClass = 'stress-low';
                    if(result.stressLevel > 40) stressClass = 'stress-medium';
                    if(result.stressLevel > 70) stressClass = 'stress-high';
                    
                    resultsBody.innerHTML += `
                        <tr>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm font-medium text-gray-900">Inconnu(e) ${index + 1}</div>
                                <div class="text-sm text-gray-500">${result.specialty}</div>
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm font-medium ${stressClass}">${result.stressLevel}%</div>
                                <div class="mt-1 w-full bg-gray-200 rounded-full h-2.5">
                                    <div class="bg-blue-600 h-2.5 rounded-full" style="width: ${result.stressLevel}%"></div>
                                </div>
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">
                                ${result.timestamp}
                            </td>
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
        
        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            // Button hover effect
            document.querySelectorAll('a, button').forEach(link => {
                link.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-2px)';
                });
                link.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });
        });
    </script>
</body>
</html>
