<template>
  <div class="home fade-in">
    <div class="icon-container">
      <a href="https://github.com/lamlankosi" target="_blank" class="icon">
        <i class="fab fa-github"></i>
      </a>
      <a href="https://www.linkedin.com/in/lamlankosi-nomnganga-59b500268/" target="_blank" class="icon">
        <i class="fab fa-linkedin"></i>
      </a>
      <a href="mailto:lamlanomnganga9@gmail.com" class="icon">
        <i class="fas fa-envelope"></i>
      </a>
    </div>

    <h1 class="wavy-text">WELCOME TO MY</h1>
    <h2 class="wavy-text">PORTFOLIO WEBSITE</h2>

    <a href="#about" class="cta-button">GET TO KNOW ME</a>
  </div>
</template>

<script>
export default {
  name: "PortfolioHero",
};
</script>

<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');

/* Fade-in animation */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in {
  opacity: 0;
  animation: fadeIn 1s ease-out forwards;
}

/* Wavy text animation */
@keyframes waveText {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-5px); }
  100% { transform: translateY(0px); }
}

.wavy-text {
  font-size: 2.5rem;
  font-weight: bold;
  color: #e0e0e0; /* Light grey for better contrast */
  animation: waveText 3s infinite ease-in-out;
  margin: 0.5rem 0; /* Add spacing between lines */
}

/* Home container */
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: #f5f5f5; /* Light grey text */
  height: 100vh;
  background: #1a1a1a; /* Slightly lighter dark background */
  padding: 2rem;
}

/* Social icons */
.icon-container {
  display: flex;
  gap: 15px;
  margin-bottom: 30px; /* Increased spacing */
}

.icon {
  font-size: 1.8rem;
  color: #e0e0e0; /* Light grey */
  transition: transform 0.3s ease-in-out, background-color 0.3s;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 50px;
  height: 50px;
  background-color: rgba(255, 255, 255, 0.05); /* Subtle background */
  border-radius: 50%;
  backdrop-filter: blur(10px);
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Softer shadow */
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.icon:hover {
  transform: scale(1.2);
  background-color: rgba(255, 255, 255, 0.1); /* Slightly brighter on hover */
}

/* CTA Button */
.cta-button {
  margin-top: 30px; /* Increased spacing */
  padding: 12px 25px;
  background: #2c2c2c; /* Dark grey */
  color: #e0e0e0; /* Light grey text */
  border-radius: 50px;
  font-size: 1.2rem;
  font-weight: bold;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1); /* Softer shadow */
  transition: background-color 0.3s, transform 0.3s;
  border: 1px solid rgba(255, 255, 255, 0.1);
  text-decoration: none; /* Remove underline */
}

.cta-button:hover {
  background-color: #4a4a4a; /* Medium grey */
  color: #ffffff;
  transform: scale(1.05);
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .wavy-text {
    font-size: 2rem;
  }
  .icon-container {
    gap: 10px;
  }
  .icon {
    font-size: 1.5rem;
    width: 40px;
    height: 40px;
  }
}
</style>