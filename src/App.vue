<script setup>
import { ref } from 'vue'
import Kickstarter from './views/Kickstarter.vue';

const smoothScroll = (target, duration) => {
  const targetElement = document.querySelector(target);
  const targetPosition = targetElement.getBoundingClientRect().top;
  let startPosition = window.pageYOffset;
  let startTime = null;

  const animation = (currentTime) => {
    if (startTime === null) startTime = currentTime;
    let timeElapsed = currentTime - startTime;
    let run = easeOutCubic(timeElapsed, startPosition, targetPosition, duration);
    window.scrollTo(0, run);
    if (timeElapsed < duration) requestAnimationFrame(animation);
  };

  const easeOutCubic = (t, b, c, d) => {
    t /= d;
    t--;
    return c*(t*t*t + 1) + b;
  };

  requestAnimationFrame(animation);
};

const smoothScrollTo = ref(smoothScroll);

const form = ref({
  name: '',
  email: '',
  message: ''
});

const submitForm = () => {

  console.log(form.value);
};
</script>

<template>
  <header>
    <nav>
      <ul>
        <li>
          <a href="#accueil"></a>
        </li>
        <li>
          <a href="#presentation" @click.prevent="smoothScrollTo('#presentation', 1000)">PRÉSENTATION</a>
        </li>
        <li>
          <a href="#project" @click.prevent="smoothScrollTo('#project', 1000)">PROJET</a>
        </li>
        <li>
          <a href="#project" @click.prevent="smoothScrollTo('#process', 1000)">PROCÉDÉ</a>
        </li>
        <li>
          <a href="#team" @click.prevent="smoothScrollTo('#team', 1000)">ÉQUIPE</a>
        </li>
        <li>
          <a href="#kickstarter" @click.prevent="smoothScrollTo('#kickstarter', 1000)">KICKSTARTER</a>
        </li>
        <li>
          <a href="#news" @click.prevent="smoothScrollTo('#news', 1000)">OFFRES</a>
        </li>
        <li>
          <a href="#contact" @click.prevent="smoothScrollTo('#contact', 1000)">CONTACT</a>
        </li>
      </ul>
    </nav>
  </header>
  <body>
    <div class="bc">
      <section id="accueil">
        <h1 class="h1t">Projet <span class="bluespan">3D Mapping</span> <br>Villeroy Industrie</h1>
      </section>
      <section id="presentation">
        <h1 class="title-presentation">
          Chez SeeIT,<span class="bluespan"> nous sommes passionnés </span>par la technologie et l'innovation.
        </h1>
            <h1 class="h1-presentation">
              Nous sommes un groupe d'étudiants en 3ème année du BUT MMI 
              (Métiers du Multimédia et de l'Internet)<span class="bluespan"> spécialisés dans le 
              développement web.  </span>Nous sommes ravis de vous présenter notre
              <span class="bluespan">projet de modélisation et de réalisation </span>d'une vue 3D de 
              l'entreprise Villeroy Industrie.
                <br> <br>
              Ce qu’on propose aujourd’hui c’est une solution numérique clé en main pour donner vie à ces  
              entreprises. Une visualisation 3D de leurs locaux, dans leur contexte géographique. 
              <span class="bluespan">C’est l’occasion idéale pour se créer une identité</span>, être visible en ligne et se faire
               enfin remarquer. 
            </h1>
      </section>
      <section id="project">
        <div class="project-details">
          <h1>Projet :</h1>
        </div>
        <iframe class="three" src="https://sae501-product.axelduquelzar.fr/"></iframe>
        <a href="https://sae501-product.axelduquelzar.fr/">Ouvrir le projet dans un autre onglet</a>
      </section>
      <section id="process">
        <h1>Étapes de <span class="bluespan">conception</span></h1> <br>
        <div class="project-details">
          <h2 class="process-h2"><span class="bluespan">Étape 1 : </span>La découverte du sujet</h2> <br>
          <p>Notre groupe constitué, nous avons eu la surprise de prendre connaissance de notre sujet : la modélisation 3D des locaux d'une entreprise.</p>
          <p>En premier lieu nous avons donc pris le temps de nous renseigner sur ce qui existait à ce sujet pour nous faire rapidement un premier benchmark.</p>
          <p>Pléthore de modélisation 3D de villes, quartiers et différents bâtiments étaient à portée de mains, là à nous attendre pour nous inspirer.</p>
          <p><a href="https://windland-neotix.vercel.app/" class="ref-poc">Exemple de modélisation 3D</a></p> <br>
      
          <h2 class="process-h2"><span class="bluespan">Étape 2 : </span> Mise en place technique et répartition des tâches</h2> <br>
          <p>L'important était à ce moment de bien décomposer les tâches pour nous les répartir. Et pour cela un choix s'imposait quant à l'exécution du projet : les technologies.</p>
          <p>De notre côté nous sommes partis sur les outils les plus communs et bien documentés disponibles : modélisation à la main sur Blender et l'intégration de la 3D dans le web avec du ThreeJS.</p>
          <p>Et quant à notre attribution des missions :</p>
          <ul> <br>
            <li>Antoine s'occupera de la modélisation 3D</li>
            <li>Axel gèrera la mise en place du projet dans une scène ThreeJS et lui donnera vie</li>
            <li>Camel préparera le site de rendu avec un design modern et attirant</li>
            <li>Paco fera les différents textes, oraux et créations de contenus du projet.</li>
          </ul> <br> <br>
          <p>Evidemment, tout le monde travail en commun avec un retour constant des autres.</p> <br>
      
          <h2 class="process-h2"><span class="bluespan">Étape 3 : </span> Les premiers pas</h2> <br>
          <p>Côté 3D Antoine a réalisé un premier jet en 3D du bâtiment principale des locaux de notre entreprise. Un modèle simple et non texturé mais au plus proche du réel pour avoir une base de travail.</p>
          <p>Axel à mis en place un scène ThreeJS fonctionnel en prenant un model 3D d'exemple mais qui permet de se faire la main. Le tout est fonctionnel et n'attendra plus que la modélisation finale lui donner vie !</p>
          <p>Camel et Paco construisent le site de rendu ainsi que son contenu. Cela comprends notamment l'élaboration d'un pitch deck dans lequel on se projette à créer un modèle économique et une communication externe crédible lors d'une demande de financement auprès d'investisseurs fictifs.</p> <br>

          <h2 class="process-h2"><span class="bluespan">Étape 4 : </span> Réalisation finale</h2> <br>
          <p>Nouvelle étape pour Antoine qui ajoute désormais tout un background autour du bâtiment. L'idée est de reproduire l'environnement réel autour de son bâtiment 3D. Route, champs, forêt, véhicules. Tout y passe pour rendre la mise en scène crédible et vivante !</p>
          <p>Au tour d'Axel de prendre en main la première version du modèle d'Antoine et de l'intégrer dans ThreeJS. Il ajoute des mouvement de caméra, des éléments visuels et des interactions légères. On approche de la version finale de notre POC tel qu'on l'avait imaginé au départ.</p>
          <p>Camel et Paco réalise cette fois une page kickstarter <a href="https://fr.tipeee.com/seeit/">Tipee</a> pour simuler une recherche de financement auprès du public cette fois-ci. Nouveau modèle économique, création de paliers et de contreparties pertinentes pour donner une fois de plus de corps au projet.</p> <br>
                

          <h2 class="process-h2"><span class="bluespan">Étape 5 : </span> Le rendu</h2> <br>
          <p>Les efforts cumulés de chacun se concrétisent dans la réalisation de ce site de rendu et du modèle 3D finale qui se trouve ici. Nos différents objectifs individuels ont étés atteint sans trop d'encombres. De nombreux ajustements, changement d'idées et micro adaptions ont eu lieu tout le long du processus pour répondre au mieux à notre sujet.</p>
          <p>Notre travail se conclut sur ce rendu final qui constitue selon nous une très bonne preuve de concept pour la modélisation 3D d'une entreprise.</p>

        </div>
      </section>
      <section id="team">
        <h1>Membres de l'Équipe</h1>
        <div class="team-members">
          <div class="team-member">
            <img src="/src/assets/photos/camel.jpeg" alt="Membre 1">
            <p>Camélien Tournu <br>Commercial <span class="bluespan">Terrain</span></p>
          </div>
          <div class="team-member">
            <img src="/src/assets/photos/antoine.jpg" alt="Membre 3">
            <p>Antoine Lauzis <br> <span class="bluespan"> Modélisateur</span> 3D</p>
          </div>
          <div class="team-member">
            <img src="/src/assets/photos/paco.jpeg" alt="Membre 4">
            <p>Paco Garcia <br> <span class="bluespan">Chef </span>de Projet</p>
          </div>
          <div class="team-member">
            <img src="/src/assets/photos/axel.jpeg" alt="Membre 2">
            <p>Axel Duquelzar <br> <span class="bluespan">Développeur </span>Full Stack</p>
          </div>
        </div>
      </section>
      <section id="kickstarter">
        <Kickstarter />
      </section>
      <section id="news">
        <div class="pricing-cards">
          <div class="price-card">
            <div class="price-card-header">
              <h2 class="price-card-title">Offre Unique</h2>
              <p class="price-card-description">Repartez avec ce projet, clé en main !</p>
            </div>
            <div class="price-card-body">
              <div class="price-card-price">
                <h2 class="h2-price">3900€</h2>
              </div> <br>
              <ul class="price-card-features">
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Visite et prospection du lieu</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Prise radar des dimensions 3D</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Modélisation de l'entreprise</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Installation du projet</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Livraison et consignes</li>
              </ul>
            </div> <br> <br> <br>
            <a href="#contact" class="a-contact">
              <button class="price-card-button">Contactez-nous</button>
            </a>          
          </div>
          <div class="price-card">
            <div class="price-card-header">
              <h2 class="price-card-title">Offre Abonnement</h2>
              <p class="price-card-description">Pour la création et le suivi de votre modélisation 3D</p>
            </div>
            <div class="price-card-body">
              <div class="price-card-price">
                <h2 class="h2-price">2400€ + 25€</h2>
                <span>/mois</span>
              </div> 
              <span class="abo">Abonnement sur 1 an minimum*</span>
              <br> <br>
              <ul class="price-card-features">
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Visite et prospection du lieu</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Prise radar des dimensions 3D</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Modélisation de l'entreprise</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Installation du projet</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Livraison et consignes</li>
                <li><img src="/src/assets/check-icon3.png" alt="Check Icon"> Suivi et Accompagnement</li>

              </ul>
            </div>
            <a href="#contact" class="a-contact">
            <button class="price-card-button">Contactez-nous</button>
          </a>
          </div>
        </div>
      </section>
      <section id="contact">
        <h1>Contactez-nous</h1>
        <div class="contact-container">
          <div class="contact-info">
            <p>Email: info@seeit.com</p>
            <p>Téléphone: +33 1 23 45 67 89</p>
            <p>Adresse: 4 rue Quebec, 10430, Rosière-Près Troyes</p>
            <img src="./assets/photos/map.png" alt="map" class="image-map">
          </div>
          <form @submit.prevent="submitForm">
            <div class="form-group">
              <label for="name">Nom:</label>
              <input type="text" id="name" v-model="form.name" required>
            </div>
            <div class="form-group">
              <label for="email">Email:</label>
              <input type="email" id="email" v-model="form.email" required>
            </div>
            <div class="form-group">
              <label for="message">Message:</label>
              <textarea id="message" v-model="form.message" required></textarea>
            </div>
            <button type="submit">Envoyer</button>
          </form>
        </div>
      </section>
    </div>
  </body>
</template>

<style lang="scss" scoped>

@import url('https://fonts.cdnfonts.com/css/gilroy-bold');

header {
  height: 100px;
  width: 100%;
  background-color: black;
  display: flex;
  align-items: center;
  position: fixed;
  top: 0;
  z-index: 1000;
  background-image: url('/src/assets/degrade.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  margin: 0;
  padding: 0;

  nav {
    width: 100%;
  
    ul {
      display: flex;
      flex-direction: row;
      justify-content: flex-end; 
      align-items: center;
      list-style: none;
      margin-right: 40px;
  
      a {
        color: white;
        text-decoration: none;
        font-family: "gilroy-bold";
        font-size: 16px;
        transition: all 0.3s ease-in-out;
      }

      
      a:hover {
        color: #3773ea;
        transition: all 0.3s ease-in-out;
      }

      li {
        margin-left: 20px;
      }
    }
  }
}

.a-contact {
  color: white;
  text-decoration: none;
}
.abo {
  font-size: 12px!important;
  font-weight: bold;
  color: #ffffff!important;
  line-height: 1.5!important;
}


.h1-presentation {
  font-size: 20px;
  font-weight: 500;
  color: #ffffff;
  margin-bottom: 2rem;
  text-align: center;
  padding: 20px;
  width: 1300px;
}

.h1-project {
  font-size: 2rem;
  font-weight: 900;
  color: #ffffff;
  margin-bottom: 2rem;
  text-align: center;
  padding: 20px;
  width: 1330px;
}


.title-presentation {
  font-size: 2rem;
  font-weight: 900;
  color: #ffffff;
  margin-bottom: 2rem;
  text-align: center;
  padding: 20px;
  width: 1330px;
}

.bluespan {
  color: #3773ea;
  font-weight: 800;
}

body {
  a {
    color: #3773ea;
    text-decoration: none;

    &:hover {
      color: #ffffff;
    }
  }
  overflow: hidden;

  video {
    height: 100%;
    left: 0;
    object-fit: cover;
    top: 0;
    transform: none;
    width: 100%;
  }
}

#kickstarter {
  height: 100vh;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

#presentation {
  height: 100vh;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

#project {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  color: white;

  h1 {
    font-size: 3rem;
    font-weight: 600;
    color: #e1e1e1;
  }

  .project-details {

    a {
      color: #3773ea;
      text-decoration: none;

      &:hover {
        color: #ffffff;
      }
    }
  }
}

.price-card {
  border-radius: 20px;
  border: 2px solid #84b4de;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  width: 300px;
  padding: 20px;
  margin-left: 40px;
  transition: transform 0.3s ease-in-out; 

  &:hover {
    transform: scale(1.05);
    transition: transform 0.3s ease-in-out;
  }


  span {
    font-size: 14px;
    font-weight: bold;
    color: #989898;
  }

  .h2-price {
    font-size: 28px;
    font-weight: bold;
    color: #6095ff;
  }
}

#process {
  height: 250vh;
  color: white;
  margin-top: 450px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  p {
    text-align: center;
  }

  ul {
    list-style-type: none;
    margin-left: 70px;
    text-align: center;

  }

  a {
    color: #5679be;
    text-decoration: underline;

    &:hover {
      color: #ffffff;
    }
  }

  h1 {
    font-size: 3rem;
    font-weight: 600;
    color: #e1e1e1;
  }

  .project-details {
    text-align: left;

    p {
      margin-bottom: 1rem;
      margin-top: 5px; 
      margin-left: 60px;
      margin-right: 50px;
      line-height: 1.5;
      font-weight: 900;
    }
  }
}

.price-card-header {
  border-bottom: 1px solid #ccc;
  padding-bottom: 10px;
  margin-bottom: 20px;
}

.price-card-title {
  font-size: 24px;
  font-weight: bold;
  color: #ffffff;
}

.price-card-description {
  font-size: 14px;
  color: #989898;
}

.price-card-body {
  margin-bottom: 20px;
}

.price-card-price {
  display: flex;
  justify-content: flex-start;
  align-items: baseline; 
  gap: 0.5rem; 
}

.process-h2 {
  font-size: 2rem;
  font-weight: 600;
  color: #e1e1e1;
  margin-left: 40px;
  text-align: center;
}

.image-map {
  width: 400px;
  height: auto;
  border-radius: 10px;
  border: 2px solid #092357;
  transition: all 0.3s ease-in-out;
  margin-top: 20px;
}

.price-card-features {
  list-style: none; 

  li {
    display: flex;
    align-items: center; 
    gap: 0.5rem; 

    img {
      width: 1rem; 
    }
  }
}

.price-card-features li {
  margin-bottom: 10px;
}

.price-card-button {
  display: block;
  width: 100%;
  padding: 15px 20px;
  font-size: 18px;
  font-weight: bold;
  text-align: center;
  margin-top: 9px;
  color: #fff;
  background-color: #007bff;
  border: none;
  border-radius: 0 0 20px 20px;
  cursor: pointer;
  transition: all 0.3s ease-in-out;

  &:hover {
    background-color: #0056b3;
    transition: all 0.3s ease-in-out;
  }
}


#news {
  height: 100vh;
  color: white;
  display: flex;
  margin-top: 20px;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  .pricing-cards {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    margin-top: 2rem;
    font-family: 'Gilroy-Medium', sans-serif;

    .pricing-card {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 200px;
      margin: 2rem;
      padding: 2rem;
      border: 1px solid #ffffff;
      border-radius: 10px;
      background-color: #fff;
      color: #000;

      h2 {
        margin-bottom: 1rem;
        font-size: 2rem;
        color: #ffffff;
      }

      p {
        text-align: center;
        color: white;
      }
    }
  }
}

#team {
  height: 100vh;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  h1 {
    font-size: 3rem;
    font-weight: 600;
    color: #e1e1e1;
  }

  .team-members {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    margin-top: 2rem;

    .team-member {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 200px;
      margin: 3.5rem;
      transition: transform 0.3s ease-in-out;

      &:hover {
        transform: scale(1.1);
      }

      img {
        width: 270px;
        height: auto;
        transition: all 0.3s ease-in-out;
        border: 2px solid #092357;
        border-radius: 10px;

      }

      p {
        margin-top: 1rem;
        text-align: center;
        font-weight: bold;
      }
    }
  }
}

#accueil {
  height: 100vh;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.h1t {
  font-size: 4.5rem;
  font-weight: 800;
  line-height: 1;
  color: #e3e2e2;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

#contact {
  height: 100vh;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  .contact-container {
    display: flex;
    justify-content: space-between;
    align-items: start;
    gap: 15rem;
    margin-top: 30px;
  }

  .contact-info {
    flex: 1;
    text-align: left;
    line-height: 1.5;
  }

  h1 {
    font-size: 3rem;
    font-weight: 600;
    color: #e1e1e1;
  }

  .contact-info {
    margin-top: 2rem;

    p {
      margin-bottom: 1rem;
    }
  }

  form {
    margin-top: 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    flex: 1;
    text-align: right;


    .form-group {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      margin-bottom: 1rem;

      label {
        margin-bottom: 0.5rem;
        font-weight: bold;
      }

      input, textarea {
        padding: 0.5rem;
        font-size: 1rem;
        border: 1px solid #ccc;
        border-radius: 5px;
        width: 440px;
      }

      textarea {
        height: 150px;
      }
    }

    button {
      padding: 0.5rem 1rem;
      font-size: 1rem;
      font-weight: bold;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: all 0.3s ease-in-out;

      &:hover {
        background-color: #0056b3;
        transition: all 0.3s ease-in-out;
      }
    }
  }
}

.three {
  width: 100%;
  height: 100%;
  border: none;
  overflow: hidden;
  margin-top: 20px;
  margin-bottom: 20px;
  border-radius: 5px;
  border: 2px solid #092357;
  transition: all 0.3s ease-in-out;
}

/* Pour les écrans de taille moyenne (tablette, 768px et plus) */
@media (min-width: 768px) {
  header nav ul {
    flex-direction: row;
    justify-content: flex-end;
  }

  .h1-presentation, .h1-project, .title-presentation {
    font-size: 20px;
    width: 1300px;
    padding: 20px;
  }

  .price-card {
    width: 300px;
  }

  .image-map {
    width: 400px;
  }

  form input, form textarea {
    width: 440px;
  }

  .contact-container {
    flex-direction: row;
    gap: 15rem;
  }

  .three {
    width: 100%;
    height: 100%;
  }

  .h1t {
    text-align: left;
  }
}

@media (max-width: 767px) {

  .h1-presentation, .h1-project, .title-presentation {
    font-size: 16px;
    width: auto;
    padding: 10px;
  }

  .image-map {
    width: 100%;
  }

  form input, form textarea {
    width: auto;
  }

  .contact-container {
    flex-direction: column;
    gap: 1rem;
  }

  .three {
    width: 100%;
    height: 50vh;
  }

  .h1t {
    text-align: center;
  }

  #process {
    height: 450vh;
    margin-bottom: 200px;
    text-align: center;

    h1 {
      font-size: 2rem;
      text-align: center;
    }

    .project-details {
      flex-direction: column;
      gap: 1rem;
      text-align: center;

      .process-h2 {
        margin: 0;
        text-align: center;
        font-size: 1.5rem;
      }
    }

  }

  #team {
    h1 {
      font-size: 2rem;
      text-align: center;
      margin-top: 100px;
    }

    .team-members {
      flex-direction: column;
      gap: 1rem;

      .team-member {
        width: 100%;
        margin: 0;
      }
    }
    margin-bottom: 100px;
  }

  .price-card {
    width: 80%;
    margin: 20px 0;
  }

  #contact {
    h1 {
      text-align: center;
      margin-top: 60vh;
    }

    .contact-container {
      flex-direction: column;
      gap: 1rem;

      .contact-info {
        text-align: center;
      }

      form {
        width: 100%;
        align-items: center;
      }
    }
  }
  header nav {
    padding: 0.5rem 0; 
    width: 109%;
  }
  
  header nav ul li {
    margin: 0.25rem 0;
  }
  
  header nav ul li a {
    font-size: 10px; 
    margin: 0 0.25rem; 
  }
}


</style>
