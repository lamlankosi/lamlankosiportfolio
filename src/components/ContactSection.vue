<template>
    <div class="contact">
      <h1 class="title fade-in">Contact Me</h1>
      <div class="container fade-in" style="animation-delay: 0.3s">
        <div class="details">
          <p><i class="bi bi-pin-map-fill"></i> Cape Town, Western Cape</p>
          <p><i class="bi bi-envelope"></i> lamlanomnganga9@gmail.com</p>
          <p><i class="bi bi-github"></i> <a href="https://github.com/lamlankosi" target="_blank">lamlankosi</a></p>
          <p><i class="bi bi-linkedin"></i> <a href="https://linkedin.com/in/lamlankosi-nomnganga-59b500268" target="_blank">Lamlankosi Nomnganga</a></p>
          <p><i class="bi bi-telephone-fill"></i> 072 938 854</p>
        </div>
  
        <div class="contactMe">
          <form action="https://formspree.io/f/xblrvroz" method="POST">
            <label for="email">Your email:</label>
            <input type="email" id="email" name="email" required>
  
            <label for="message">Your message:</label>
            <textarea id="message" name="message" required></textarea>
  
            <button type="submit">Send</button>
          </form>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {};
  </script>
  
  <style scoped>
  /* Fade-in animation */
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(30px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  /* Apply the fade-in animation */
  .fade-in {
    opacity: 0; /* Start hidden */
    animation: fadeInUp 0.8s ease-out forwards;
  }
  
  /* Overall Styling */
  .contact {
    background: #1a1a1a; /* Dark background */
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 50px 20px;
    color: #e0e0e0; /* Light grey text */
  }
  
  /* Title */
  .contact h1 {
    font-size: 2.5rem;
    font-weight: bold;
    color: #ffffff; /* White title */
    margin-bottom: 20px;
  }
  
  /* Container Layout */
  .container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    background: #2c2c2c; /* Dark grey */
    padding: 30px;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);

    max-width: 900px;
  }
  
  /* Contact Details */
  .details {
    flex: 1;
    font-size: 1rem;
    color: #e0e0e0; /* Light grey text */
    line-height: 1.8;
  }
  
  .details p {
    display: flex;
    align-items: center;
    gap: 8px;
    margin: 10px 0;
  }
  
  .details i {
    font-size: 1.2rem;
    color: #b0b0b0; /* Light grey */
  }
  
  .details a {
    color: #e0e0e0; /* Light grey text */
    text-decoration: none;
    font-weight: bold;
  }
  
  .details a:hover {
    text-decoration: underline;
    color: #ffffff; /* White on hover */
  }
  
  /* Contact Form */
  .contactMe {
    flex: 1;
    padding: 20px;
    background: #1e1e1e; /* Dark grey */
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.05);
  }
  
  /* Form Fields */
  form {
    display: flex;
    flex-direction: column;
  }
  
  form label {
    font-size: 1rem;
    font-weight: bold;
    color: #e0e0e0; /* Light grey text */
    margin-bottom: 5px;
  }
  
  input[type="email"],
  textarea {
    width: 100%;
    padding: 12px;
    margin-bottom: 15px;
    border: 1px solid #3a3a3a; /* Medium grey border */
    border-radius: 5px;
    font-size: 1rem;
    background: #2c2c2c; /* Dark grey */
    color: #e0e0e0; /* Light grey text */
    transition: all 0.3s ease;
  }
  
  input[type="email"]:focus,
  textarea:focus {
    border-color: #555;
    background: #333; /* Slightly lighter grey */
    outline: none;
  }
  
  /* Button */
  button[type="submit"] {
    padding: 12px;
    background: #1e1e1e; /* Dark grey */
    color: #e0e0e0; /* Light grey text */
    font-size: 1rem;
    font-weight: bold;
    border: 1px solid #3a3a3a; /* Medium grey border */
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s ease;
  }
  
  button[type="submit"]:hover {
    background: #2a2a2a; /* Medium grey */
    color: #ffffff; /* White text */
    transform: scale(1.05);
  }
  
  /* Responsive Design */
  @media screen and (max-width: 768px) {
    .container {
      flex-direction: column;
      align-items: center;
    }
  
    .details, .contactMe {
      width: 100%;
      text-align: center;
    }
  }
  </style>