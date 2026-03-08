<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Antonio | AI Engineer Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        html {
            scroll-behavior: smooth;
        }

        section {
            scroll-margin-top: 3.125rem;
        }

        h3 {
            scroll-margin-top: 3.75rem;
        }
        :root {
            --orange: #FF6B00;
            --bg-dark: #000000;
            --glass: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
        }

        body {
            margin: 0;
            padding: 0;
            background-color: var(--bg-dark);
            color: white;
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Contenitore per lo sfondo animato */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        header {
            display: flex;
            justify-content: center;
            padding: 1.25rem 10%;
            gap: 5rem;
            position: fixed;
            top: 0;                
            width: 100%;
            box-sizing: border-box;
            background-color: rgba(0, 0, 0, 0.8);
            z-index: 10;
        }

        header a {
            color: white;
            text-decoration: none;
            font-size: 1rem;
            font-weight: 700;
        }

        /* Il contenitore della lista */
        .dropdown-content {
            opacity:0;
            visibility: hidden;
            transition: opacity 0.3s ease, transform 0.3s ease;
            transform: translateX(-10%) translateY(-10px);
            position: absolute;
            background: rgba(10, 10, 10, 0.98);
            border-radius: 5%;
            min-width: 17.5rem;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(10px);
            left: 50%;
            margin-top: 0px;
            z-index: 10;
        }

/* Selettore diretto per i link della lista */
        .dropdown-content a {
            display: flex;
            justify-content: space-between; /* Spinge il nome a sx e lo span a dx */
            align-items: center;
            padding: 12px 20px;
            font-size: 13px;
            color: white;
            text-decoration: none;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

/* Selettore per l'ambito (lo span dentro il link) */
        .dropdown-content a span {
            font-size: 10px;
            color: var(--orange);
            text-transform: uppercase;
            letter-spacing: 1px;
            opacity: 0.7;
        }

/* Hover sui singoli elementi */
        .dropdown-content a:hover {
            background: rgba(255, 107, 0, 0.1);
        }

/* Mostra la lista */
        .dropdown:hover .dropdown-content {
            opacity:1;
            visibility: visible;
            transform: translateX(-10%) translateY(0);
        }

        .container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 50px 20px;
        }

        /* Sezione Hero */
        .hero {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 100px;
        }

        .hero-text h1 {
            font-size: 3.5rem;
            margin: 0;
        }

        .hero-text h2 {
            font-size: 5.7rem;
            color: var(--orange);
            margin: 0;
            line-height: 1.1;
        }

        .view {
            color: white;
            text-decoration: none;
            font-weight: bold;
            border-bottom: 2px solid var(--orange); /* La linea arancione sotto il link */
            padding-bottom: 3px;
            transition: 0.3s;
        }

        .view:hover {
            color: var(--orange);
        }

        .profile-img {
            width: 300px;
            height: 300px;
            background: url('propic_2.webp') center/cover; /* Sostituisci con la tua foto */
            border-radius: 30%;
            object-fit: cover;
        }

        /* I Tag in Vetroformismo */
        .tag-container {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin: 40px auto;
            padding: 15px 30px;
            background: var(--glass);
            backdrop-filter: blur(10px);
            border-radius: 12px;
            border: 1px solid var(--glass-border);
        }

        .tag {
            color: #aaa;
            font-weight: bold;
            padding: 5px 10px;
        }

        .tag-large {
            font-size: 1.1rem; 
            padding: 10px 25px;
        }

        .tag-small {
            background: rgba(255, 255, 255, 0.05); 
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
    
    /* Forma e distanze */
            padding: 6px 14px;
            border-radius: 8px; /* Angoli leggermente smussati come nel tuo Figma */
            display: inline-block;

            font-size: 0.9rem;  
            padding: 5px 15px; 
            color: #888;        
        }

        /* Sezione About Me ed Elenco Puntato */
        .about-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            margin-top: 100px;
        }

        .interest-title {
            font-size: 1.5rem;
            margin-top: 10rem;
            margin-bottom: 20px;
        }

        .custom-list {
            list-style: none;
            padding: 0;
        }

        .custom-list li {
            position: relative;
            padding-left: 30px;
            margin-bottom: 40px;
            font-weight: bold;
            font-size: 1.2rem;
        }

        /* Linea e punti arancioni verticali */
        .custom-list li::before {
            content: "";
            position: absolute;
            left: 0;
            top: 30%;
            width: 12px;
            height: 12px;
            background: var(--orange);
            border-radius: 50%;
            z-index: 2;
        }

        .custom-list li::after {
            content: "";
            position: absolute;
            left: 5px;
            top: 30px;
            width: 2px;
            height: 40px;
            background: var(--orange);
            z-index: 1;
        }

        .custom-list li:last-child::after { display: none; }

        .about-text {
            font-size: 0.95rem;
            color: #ddd;
            text-align: justify;
            font-weight: 700;
        }

        /* Progetti */
        .projects-title {
            font-size: 2.5rem;
            text-align: center;
            display: block;
            margin: 100px auto 20px;
            width: auto;
            border-bottom: 2px solid var(--orange);
            padding: 0 80px;
        }

        .projects-section {
            display: flex;
            flex-direction: column; 
            gap: 80px;              
            margin-top: 50px;  
        }

        .project {
            display: flex;
            align-items: center;
            justify-content:space-between; 
            gap: 8.125rem;
        }

        .project.reverse {
            flex-direction: row-reverse;
        }

        .project-info h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
        }

        .project-description {
            color: #ddd;
            font-size: 0.95rem;
            margin: 20px 0;
            line-height: 1.5;
            font-weight: 600;
            flex:1;
            flex-direction: column;
            justify-content: center;
            margin:0;
            margin-top: 30px;
            margin-bottom: 30px;
        }

        .project-img {
            width: 45%;            /* Occupa quasi metà della riga */
            border-radius: 15px;    /* Angoli smussati come nel tuo Figma */
            overflow: hidden;       /* Taglia l'immagine se esce dai bordi arrotondati */
            box-shadow: 0 10px 30px rgba(0,0,0,0.5); /* Ombra per dare profondità */
            flex-shrink: 0;
            align-items: center;
            justify-content: center;
             /* Centra l'immagine all'interno del contenitore */
        }

        .project-img img {
            width: 100%;
            height: auto;
            object-fit: cover; /* Mantiene le proporzioni dell'immagine */
            display: block;
        }

        /* Contacts & Footer Section*/
        .contacts-title-h1 {
            font-size: 4rem;
            text-align: center;
            display: table;
            margin: auto;
            width: auto;
            border-bottom: 2px solid var(--orange);
            padding: 0 80px;
        }

        .contacts-title-h2 {
            font-size: 2rem;
            text-align: center;
            display: table;
            margin: auto;
            color: white;
            margin-top: 200px;
        }

        .contacts-icons {
            display: flex;
            justify-content: center;
            gap: 50px;
            margin-top: 50px;
        }

        .contacts-icons img {
            width: 40px;
            height: 40px;
            filter: invert(100%); /* Rende le icone bianche */
            transition: 0.3s;
        }

        .contacts-icons img:hover {
            transform: scale(1.1);
        }

        .contacts-wrapper {
            margin: 100px auto;
            margin-top: 250px;
            margin-bottom: 0;
            text-align: center;
            padding: 40px;
            width: auto;
            border-radius: 2px;
            backdrop-filter: blur(8px); 
            -webkit-backdrop-filter: blur(8px);
            background: rgba(0, 0, 0, 0.2); 
        }

        @media (max-width: 850px) {
            .container {
                padding: 20px;
            }

            .hero {
                flex-direction: column-reverse;
                text-align: center;
                margin-bottom: 60px;
            }

            .hero-text h2 {
                font-size: clamp(2.5rem, 10vw, 4.5rem);
            }

            .header {
                flex-direction: column;
                font-size: 8px;
                gap: 1rem;
                padding: 1rem;
            }

            .tag-large{
                font-size: 0.9rem;
                padding: 8px 2px;
            }

            .tag-container {
                display: flex;
                justify-content: center;
                margin-bottom: 10px;
            }

            .about-section {
                grid-template-columns: 1fr;
                gap: 20px;
            }

            .projects-title{
                gap: 0 20px;
            }

            .projects-section{
                gap: 10px;
            }

            .project, .project.reverse {
                flex-direction: column;
                gap: 30px;
            }

            header {
                gap: 1.5rem;
                padding: 1rem;
            }

            .interest-title {
                text-align: center;
                margin-top: 7px;
                margin-bottom: 2rem;
                font-size: 1.2rem;
            }

            .custom-list li {
                
                font-size: 1rem;
            }

            .custom-list li::after {
                display: none;
            }

            .dropdown-content{
                left: 45%;
                min-width: 12rem;
            }

            .dropdown-content a {
                font-size: 11px;
            }

            .dropdown-content a span{
                font-size: 8px;
            }

            .project-img {
                width: 70%;
            }

            .contacts-title-h1 {
                font-size: clamp(2.2rem, 7vw, 4rem);
                padding: 0 40px;
            }

             .contacts-title-h2 {
                font-size: clamp(1.2rem, 3vw, 2rem);
                margin-top: 100px;
             }
            
            .contacts-icons {
                margin-top:10px;
                gap:25px;
            }
            .contacts-icons img {
                width: 25px;
                height: 25px;
            }
        }

    </style>
</head>
<body>

    <div id="particles-js"></div>

    <header>
        <a href="#">Home</a>
        <a href="#about">About</a>
        <div class="dropdown">
            <a href="#projects">Projects</a>
            <div class="dropdown-content">
                <a href="#tiresias">Tiresias <span>Time Series</span></a>
                <a href="#mlops"> AI Component <span>MLOps</span></a>
                <a href="#clustering">Muten <span>Process Mining</span></a>
            </div>
        </div>
        <a href="#contacts">Profiles & Contacts</a>
    </header>

    <div class="container">
        <section class="hero">
            <div class="hero-text">
                <p>Hello, Nice to meet you!</p>
                <h1>I'm Antonio</h1>
                <h2>AI Engineer &<br>Data Scientist</h2>
                <p><a href="https://github.com/AntonioCampanozzi" class="view" target="_blank" rel="noopener noreferrer">Check out my resume! ↗</a></p>
            </div>
            <div class="profile-placeholder">
                <div class="profile-img"></div>
            </div>
        </section>

        <div class="tag-container">
            <span class="tag tag-large">MLOps</span>
            <span class="tag tag-large">Git</span>
            <span class="tag tag-large">Deep Learning</span>
            <span class="tag tag-large">Machine Learning</span>
            <span class="tag tag-large">Knowledge Graphs</span>
            <span class="tag tag-large">Computer Vision</span>
            <span class="tag tag-large">Process Mining</span>
        </div>

        <section id="about" class="about-section">
            <div>
                <h3 class="interest-title">Main interests</h3>
                <ul class="custom-list">
                    <li>Knowledge Graph Embeddings</li>
                    <li>Time Series</li>
                    <li>Process Discovery</li>
                    <li>Agents</li>
                </ul>
            </div>
            <div>
                <h3 style="text-align: center; font-size: 2.5rem;">About me</h3>
                <p class="about-text">
                    My journey with computer science begins by chance... (incolla qui il tuo testo corretto).
                </p>
            </div>
        </section>

        <section id="projects" class="projects-section">  
            <h2 class="projects-title">Projects</h2>
            <div class="project">
                <div class="project-info">
                    <h3 id="tiresias">TIRESIAS</h3>
                    <div class="tag tag-small">Time Series</div>
                    <div class="tag tag-small">Deep Learning</div>
                    <div class="tag tag-small">CRISP-DM</div>
                    <div class="tag tag-small">Deep Learning</div>
                    <div class="tag tag-small">Data Analysis & Processing</div>

                    <p class="project-description">Developed a framework for the early prediction of mechanical resistance 
                        in additive manufacturing samples. By applying time-series clustering to experimental data, the system 
                        identifies representative medoids to establish critical failure thresholds for each stress test group.
                        TIRESIAS leverages these insights to forecast the specific stress levels a sample can withstand before 
                        reaching the "point of no return," enabling non-destructive evaluation and subsequent sample reuse. 
                        A comparative study between LSTM and XGBoost architectures proved XGBoost to be the superior approach, 
                        delivering prediction accuracy with significantly greater earliness.</p>
                    <a href="https://github.com/AntonioCampanozzi/TIRESIAS" class="view" target="_blank" rel="noopener noreferrer">View project ↗</a>
                </div>
                <div class="project-img">
                    <img src="tiresia.webp" alt="Tiresias Project">
                </div>
            </div>
                <div class="project reverse">
                    <div class="project-info">
                        <h3 id="mlops">Deployable AI Component</h3>
                        <div class="tag tag-small">DVC</div>
                        <div class="tag tag-small">Docker</div>
                        <div class="tag tag-small">FastAPI</div>
                        <div class="tag tag-small">Github Actions</div>
    
                        <p class="project-description">Collaborated in a team to engineer a production-ready AI system focused on
                            the full MLOps lifecycle. While using diabetes diagnosis as a trivial example of prediction task, we built an integrated 
                            pipeline featuring DVC for data versioning and MLflow for experiments tracking. We automated the entire workflow
                            via GitHub Actions for CI/CD, deploying client and server containers to DockerHub and Hugging Face. The system is enriched 
                            by a Prometheus/Grafana monitoring stack and validated through Locust load testing to ensure stability 
                            under high traffic.</p>
                        <a href="https://github.com/AntonioCampanozzi/MLOps_team_project" class="view" target="_blank" rel="noopener noreferrer">View project ↗</a>
                    </div>
                    <div class="project-img">
                        <img src="mlops.webp" alt="MLOps Project">
                    </div>
                </div>
                <div class="project">
                    <div class="project-info">
                        <h3 id="clustering">MUTEN: MUltiview Trace ENcodings</h3>
                        <div class="tag tag-small">Process Discovery</div>
                        <div class="tag tag-small">Latent Space Encoding</div>
                        <div class="tag tag-small">Signal Processing</div>
                        <div class="tag tag-small">BERT</div>
    
                        <p class="project-description">MUTEN Is a multi-view extension of DOROTHY , a research framework designed to mitigate "spaghetti model"
                            complexity in non-Pareto event logs by applying clustering on encoded traces, extracting the process model only on the most 
                            representative instances. While the baseline uses Sentence-BERT to encode activity flow as semantic stories , I engineered an 
                            additional temporal view by applying Discrete Cosine Transform (DCT) to interpret time intervals as signals.  My research 
                            demonstrated that temporal dynamics alone are highly informative—achieving performance comparable to the original baseline —while
                            identifying critical challenges in multi-view feature fusion for imbalanced embedding dimensions.</p>
                        <a href="https://github.com/AntonioCampanozzi/MUTEN" class="view" target="_blank" rel="noopener noreferrer">View project ↗</a>
                    </div>
                    <div class="project-img">
                        <img src="Muten.webp" alt="MUTEN Project">
                    </div>
                </div>
        </section>

        <section id="contacts" class="contacts-section">
                <h2 class="contacts-title-h2">Do you wish to include me in your team?</h2>
                <h1 class="contacts-title-h1">Feel free to reach out!</h1>
                <div class="contacts-icons">
                    <a href="https://www.linkedin.com/in/antonio-campanozzi/" target="_blank" rel="noopener noreferrer"><img src="linkedin.webp" alt="LinkedIn"></a>
                    <a href="https://github.com/AntonioCampanozzi" target="_blank" rel="noopener noreferrer"><img src="github.webp" alt="GitHub"></a>
                    <a href="mailto:antonio.campanozziic@gmail.com" target="_blank" rel="noopener noreferrer"><img src="email.webp" alt="Email"></a>
                    <a href="https://www.kaggle.com/antoniocampanozzi" target="_blank" rel="noopener noreferrer"><img src="indeed.webp" alt="Indeed"></a>
                </div>
        </section>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        particlesJS("particles-js", {
            "particles": {
                "number": { "value": 180 },
                "color": { "value": "#ffffff" },
                "size": {
                    "value": 1,       
                    "random": true  
                },
                "line_linked": { "enable": true, "distance": 200, "color": "#ffffff", "opacity": 0.2, "width": 1 },
                "move": { "enable": true, "speed": 2 }
            },
            "interactivity": {
                "events": { "onhover": { "enable": true, "mode": "grab" } }
            }
        });
    </script>
</body>
</html>
