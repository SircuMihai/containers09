# Numele lucrării de laborator
Optimizarea imaginilor

# Scopul lucrării
Scopul lucrării este de a se familiariza cu metodele de optimizare a imaginilor.

# Sarcina


Compararea diferitelor metode de optimizare a imaginilor:


- Ștergerea fișierelor temporare și a dependențelor neutilizate
- Reducerea numărului de straturi
- Utilizarea unei imagini de bază minime
- Reambalarea imaginii
- Utilizarea tuturor metodelor

# Efectuarea
## Repositoriul containers09

- Sa creat repositoriul containers09 pr GitHub, El a fost clonat pe host si in el sa creat directorul site.

## Diretorul site


In directorul site se vor crea fisierele index.html, style.css, script.js cu continutul:

### Fisierul index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wanderlust Travel Blog</title>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <header>
        <div class="container">
            <h1>Wanderlust</h1>
            <p>Discover the world through my journeys</p>
        </div>
    </header>

    <nav>
        <div class="container">
            <ul>
                <li><a href="#"><i class="fas fa-home"></i> Home</a></li>
                <li><a href="#"><i class="fas fa-map-marked-alt"></i> Destinations</a></li>
                <li><a href="#"><i class="fas fa-camera"></i> Gallery</a></li>
                <li><a href="#"><i class="fas fa-info-circle"></i> About</a></li>
            </ul>
        </div>
    </nav>

    <main class="container">
        <section class="featured-posts">
            <article class="post">
                <div class="post-image-placeholder mountain-bg"></div>
                <div class="post-content">
                    <h2>Mountain Trekking in the Alps</h2>
                    <div class="meta">
                        <span><i class="far fa-calendar"></i> June 15, 2023</span>
                        <span><i class="far fa-clock"></i> 5 min read</span>
                    </div>
                    <p>My incredible journey through the Swiss Alps, conquering peaks and making memories...</p>
                    <a href="#" class="read-more">Read More</a>
                </div>
            </article>

            <article class="post">
                <div class="post-image-placeholder beach-bg"></div>
                <div class="post-content">
                    <h2>Island Hopping in Greece</h2>
                    <div class="meta">
                        <span><i class="far fa-calendar"></i> May 3, 2023</span>
                        <span><i class="far fa-clock"></i> 8 min read</span>
                    </div>
                    <p>Exploring the crystal clear waters and white sand beaches of the Greek islands...</p>
                    <a href="#" class="read-more">Read More</a>
                </div>
            </article>

            <article class="post">
                <div class="post-image-placeholder city-bg"></div>
                <div class="post-content">
                    <h2>Urban Adventures in Tokyo</h2>
                    <div class="meta">
                        <span><i class="far fa-calendar"></i> March 22, 2023</span>
                        <span><i class="far fa-clock"></i> 10 min read</span>
                    </div>
                    <p>From neon-lit streets to tranquil temples, Tokyo offers the perfect blend of tradition and modernity...</p>
                    <a href="#" class="read-more">Read More</a>
                </div>
            </article>
        </section>

        <aside class="sidebar">
            <div class="about-widget">
                <h3>About Me</h3>
                <div class="author-placeholder"></div>
                <p>Hi, I'm Sarah! I left my corporate job in 2020 to travel the world and share my experiences.</p>
            </div>

            <div class="newsletter">
                <h3>Join My Newsletter</h3>
                <form id="newsletter-form">
                    <input type="email" placeholder="Your email address" required>
                    <button type="submit">Subscribe</button>
                </form>
            </div>
        </aside>
    </main>

    <footer>
        <div class="container">
            <p>&copy; 2023 Wanderlust Travel Blog | Powered by Docker</p>
            <div class="social-links">
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-pinterest"></i></a>
            </div>
        </div>
    </footer>

    <script src="script.js"></script>
</body>
</html>
```

### Fisierul style.css
```
/* Global Styles */
:root {
    --primary: #3498db;
    --secondary: #2ecc71;
    --dark: #2c3e50;
    --light: #ecf0f1;
    --accent: #e74c3c;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f9f9f9;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}

/* Header Styles */
header {
    background-color: var(--dark);
    color: white;
    text-align: center;
    padding: 4rem 0;
}

header h1 {
    font-size: 3rem;
    margin-bottom: 0.5rem;
}

header p {
    font-size: 1.2rem;
    opacity: 0.9;
}

/* Navigation */
nav {
    background-color: var(--dark);
    padding: 1rem 0;
}

nav ul {
    display: flex;
    list-style: none;
    justify-content: center;
}

nav a {
    color: white;
    text-decoration: none;
    padding: 0.5rem 1rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: all 0.3s ease;
}

nav a:hover {
    color: var(--secondary);
}

/* Main Content */
main {
    display: flex;
    padding: 2rem 0;
    gap: 2rem;
}

.featured-posts {
    flex: 2;
}

.sidebar {
    flex: 1;
}

.post {
    background: white;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 3px 10px rgba(0,0,0,0.1);
    margin-bottom: 2rem;
}

.post-image-placeholder {
    height: 200px;
    background-color: #ddd;
    position: relative;
}

.mountain-bg {
    background: linear-gradient(135deg, #a8c0ff, #3f2b96);
}

.beach-bg {
    background: linear-gradient(135deg, #43cea2, #185a9d);
}

.city-bg {
    background: linear-gradient(135deg, #ffafbd, #ffc3a0);
}

.post-content {
    padding: 1.5rem;
}

.post h2 {
    margin-bottom: 0.5rem;
    color: var(--dark);
}

.meta {
    display: flex;
    gap: 1rem;
    margin-bottom: 1rem;
    font-size: 0.9rem;
    color: #666;
}

.read-more {
    display: inline-block;
    margin-top: 1rem;
    color: var(--primary);
    text-decoration: none;
    font-weight: bold;
}

.read-more:hover {
    text-decoration: underline;
}

/* Sidebar */
.sidebar > div {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 3px 10px rgba(0,0,0,0.1);
    margin-bottom: 1.5rem;
}

.sidebar h3 {
    margin-bottom: 1rem;
    color: var(--dark);
    border-bottom: 2px solid var(--light);
    padding-bottom: 0.5rem;
}

.author-placeholder {
    width: 150px;
    height: 150px;
    margin: 1rem auto;
    border-radius: 50%;
    background-color: #ddd;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #777;
    font-size: 0.9rem;
}

.newsletter input {
    width: 100%;
    padding: 0.8rem;
    margin-bottom: 0.5rem;
    border: 1px solid #ddd;
    border-radius: 4px;
}

.newsletter button {
    width: 100%;
    padding: 0.8rem;
    background-color: var(--primary);
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
}

.newsletter button:hover {
    background-color: var(--dark);
}

/* Footer */
footer {
    background-color: var(--dark);
    color: white;
    text-align: center;
    padding: 2rem 0;
    margin-top: 2rem;
}

.social-links {
    margin-top: 1rem;
}

.social-links a {
    color: white;
    margin: 0 0.5rem;
    font-size: 1.2rem;
    transition: color 0.3s;
}

.social-links a:hover {
    color: var(--secondary);
}

/* Responsive Design */
@media (max-width: 768px) {
    main {
        flex-direction: column;
    }
    
    nav ul {
        flex-direction: column;
        align-items: center;
    }
}
```

### Fisierul script.js
```
document.addEventListener('DOMContentLoaded', function() {
    // Newsletter form submission
    const newsletterForm = document.getElementById('newsletter-form');
    
    if (newsletterForm) {
        newsletterForm.addEventListener('submit', function(e) {
            e.preventDefault();
            const emailInput = this.querySelector('input[type="email"]');
            alert(`Thank you for subscribing with ${emailInput.value}! You'll receive our next travel update.`);
            emailInput.value = '';
        });
    }

    // Simulate loading posts
    console.log('Travel blog loaded successfully');
    console.log('This blog is running in a Docker container!');

    // Add animation to read more links
    const readMoreLinks = document.querySelectorAll('.read-more');
    readMoreLinks.forEach(link => {
        link.addEventListener('mouseenter', function() {
            this.style.transform = 'translateX(5px)';
        });
        link.addEventListener('mouseleave', function() {
            this.style.transform = 'translateX(0)';
        });
    });
});
```

## Crearea Fisierului Dockerfile.raw
- Vom crea fisierul Dockerfile cu continutul:
```
# create from ubuntu image
FROM ubuntu:latest

# update system
RUN apt-get update && apt-get upgrade -y

# install nginx
RUN apt-get install -y nginx

# copy site
COPY site /var/www/html

# expose port 80
EXPOSE 80

# run nginx
CMD ["nginx", "-g", "daemon off;"]
```

- dupa vom crea o imagine cu comanda:
```
docker image build -t mynginx:raw -f Dockerfile.raw .
```

## Crearea Fisierului Dockerfile.clean
### Pentru eliminarea dependențelor neutilizate și a fișierelor temporare
- Vom crea fisierul Dockerfile cu continutul:
```
# create from ubuntu image
FROM ubuntu:latest

# update system
RUN apt-get update && apt-get upgrade -y

# install nginx
RUN apt-get install -y nginx

# remove apt cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# copy site
COPY site /var/www/html

# expose port 80
EXPOSE 80

# run nginx
CMD ["nginx", "-g", "daemon off;"]
```

- dupa vom crea o imagine cu comanda:
```
docker image build -t mynginx:clean -f Dockerfile.clean .
```

## Crearea Fisierului Dockerfile.few
### Pentru minimizarea numărului de straturi
- Vom crea fisierul Dockerfile cu continutul:
```
# create from ubuntu image
FROM ubuntu:latest

# update system
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y nginx && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# copy site
COPY site /var/www/html

# expose port 80
EXPOSE 80

# run nginx
CMD ["nginx", "-g", "daemon off;"]
```

- dupa vom crea o imagine cu comanda:
```
docker image build -t mynginx:few -f Dockerfile.few .
```

## Crearea Fisierului Dockerfile.alpine
### Pentru utilizarea unei imagini de bază minime
- Vom crea fisierul Dockerfile cu continutul:
```
# create from alpine image
FROM alpine:latest

# update system
RUN apk update && apk upgrade

# install nginx
RUN apk add nginx

# copy site
COPY site /var/www/html

# expose port 80
EXPOSE 80

# run nginx
CMD ["nginx", "-g", "daemon off;"]
```

- dupa vom crea o imagine cu comanda:
```
docker image build -t mynginx:alpine -f Dockerfile.alpine .
```

## Repachetarea unui conteiner intro imagine


Vom lua imaginea mynginx:raw si pe baza ei vom crea un conteiner pe care il vom repacheta in imaginea mynginx:repack. Pentru aceasta vom urmari urmatorii pasi:

- Vom crea containerul cu comanda:
```
docker container create --name mynginx mynginx:raw
```

- o sa exportam containerul creat intrun fisier de tip tar cu:
```
docker container export mynginx -o mynginx.tar
```

- vom crea imaginea pe baza la fisierul de tip tar:
```
docker image import mynginx.tar mynginx:repack
```

- stergem containerul creat:
```
docker container rm mynginx
```

## Utilizarea tuturor metodelor
### Crearea imaginii mynginx:minx
- Vom crea fisierul Dockerfile.min cu continutul:
```
# create from alpine image
FROM alpine:latest

# update system, install nginx and clean
RUN apk update && apk upgrade && \
    apk add nginx && \
    rm -rf /var/cache/apk/*

# copy site
COPY site /var/www/html

# expose port 80
EXPOSE 80

# run nginx
CMD ["nginx", "-g", "daemon off;"]
```

- dupa cream imaginea mynginx:minx cu comanda
```
docker image build -t mynginx:minx -f Dockerfile.min .
```

### Repachetarea imaginii mynginx:minx in imaginea mynginx:min
- Vom crea un container pe baza la mynginx:minx cu comanda:
```
docker container create --name mynginx mynginx:minx
```
- o sa exportam containerul creat intrun fisier de tip tar cu:
```
docker container export mynginx -o mynginx_min.tar
```
- vom crea imaginea pe baza la fisierul de tip tar:
```
docker image import mynginx_min.tar mynginx:min
```
- stergem containerul creat:
```
docker container rm mynginx
```

## Compararea metodelor de optimizare a imaginii
- pentru a compara fiecare metoda de optimizare vom compara spatiul ocupat de fiecare imagine, vom face aceasta cu ajutorul comanzii:
```
docker image list
```
- obtinem rezultatul:
![alt img](./image/Screenshot%202025-04-21%20192937.png)

### Analiza metodelor
Utilizind datele optinute in imagine potum spune urmatoarea despre metode:

#### Ștergerea fișierelor temporare și a dependențelor neutilizate (clean):
Nu a avut niciun impact asupra dimensiunii imaginii. Acest lucru se datorează faptului că curățarea cache-ului într-un strat separat nu reduce dimensiunea imaginii finale, deoarece stratul anterior care a creat fișierele temporare rămâne în istoric

#### Reducerea numărului de straturi (few):
A redus dimensiunea cu 81MB (36.16%). Combinarea comenzilor RUN într-una singură a eliminat straturi intermediare inutile.

#### Utilizarea unei imagini de bază minime (Alpine Linux) (alpine):
Cea mai eficientă metodă individuală. A redus dimensiunea cu 204.5MB (91.29%). Alpine Linux este mult mai mic decât Ubuntu.

#### Reambalarea imaginii (repack):
A avut un impact minor (doar 5.8% reducere). Repachetarea elimină istoricul și metadatele, dar păstrează conținutul fișierelor.

#### Utilizarea tuturor metodelor (minx și min):
Cea mai eficientă abordare (peste 93% reducere). Combinarea Alpine Linux cu minimizarea straturilor și curățirea cache-ului. Repachetarea ulterioară (min) aduce o reducere suplimentară neglijabilă (0.1MB)

# Concluzie
Cea mai eficientă strategie de optimizare este combinarea mai multor metode ca:
- Utilizarea unei imagini de bază minime (Alpine Linux)
- Minimizarea numărului de straturi prin combinarea comenzilor RUN
- Curățirea cache-ului și a fișierelor temporare în aceeași comandă RUN

Repachetarea oferă beneficii minore și poate fi omisă în majoritatea cazurilor, deoarece complică procesul de construcție fără reduceri semnificative de dimensiune.

# Intrebari
## Care metoda de optimizare a imaginilor vi se pare cea mai eficientă?
- Cea mai eficientă metodă este utilizarea unei imagini de bază minime (Alpine Linux), urmată de combinarea tuturor metodelor. Alpine Linux singur a redus dimensiunea cu peste 91%, iar abordarea combinată cu peste 93%.

## De ce curățirea cache-ului pachetelor într-un strat separat nu reduce dimensiunea imaginii?
- Curățirea cache-ului într-un strat separat nu reduce dimensiunea imaginii finale deoarece stratul anterior care a creat fișierele temporare rămâne în istoricul imaginii. Docker folosește un sistem de straturi suprapuse, iar fiecare comandă RUN creează un nou strat care se adaugă peste cele anterioare.

## Ce este repachetarea imaginii?
- Repachetarea imaginii este procesul de export al unui container într-o arhivă și apoi importul acesteia ca imagine nouă. Acest proces elimină istoricul de construcție și metadatele imaginii originale, păstrând doar sistemul de fișiere al containerului. În cazul nostru, repachetarea a avut un impact minor asupra dimensiunii.