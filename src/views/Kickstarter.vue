<template>
  <section id="kickstarter">
      <h1 class="h1-presentation">
          Bienvenue sur notre page Kickstarter
      </h1>
      <p class="intro-text">
          Cliquez sur le lien ci-dessous pour soutenir notre projet et nous aider à donner vie aux entreprises grâce à la modélisation 3D.
      </p>
      <a href="https://fr.tipeee.com/seeit/" target="_blank" rel="noopener noreferrer" class="kickstarter-link">
        Kickstarter
    </a>
  </section>
</template>

<style scoped>
.h1-presentation {
  font-size: 20px;
  font-weight: 500;
  color: #ffffff;
  margin-bottom: 2rem;
  text-align: center;
  padding: 20px;
  width: 1300px;
}

.intro-text {
  font-size: 18px;
  color: #ffffff;
  margin-bottom: 1rem;
  text-align: center;
  padding: 20px;
  width: 1300px;
}

.kickstarter-link {
  display: inline-block;
  font-size: 24px;
  font-weight: bold;
  color: #3773ea;
  text-decoration: none;
  padding: 10px 20px;
  border: 2px solid #3773ea;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.kickstarter-link:hover {
  color: #ffffff;
  background-color: #3773ea;
}

/* Pour les écrans de taille moyenne (tablette, 768px et plus) */
@media (min-width: 768px) {
  .h1-presentation, .intro-text {
    font-size: 20px;
    width: 1300px;
    padding: 20px;   
  }

  .kickstarter-link {
    font-size: 24px;
    padding: 10px 20px;
  }
}

/* Pour les petits écrans (mobile, moins de 768px) */
@media (max-width: 767px) {
  .h1-presentation, .intro-text {
    font-size: 16px;
    width: auto;
    padding: 10px;
    margin-top: 30px;
  }

  .kickstarter-link {
    font-size: 20px;
    padding: 5px 10px;
  }
}

</style>