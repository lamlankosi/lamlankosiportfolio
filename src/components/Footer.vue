<template>
    <footer class="footer fade-in">
      <div class="row-content">
        <p>
          Lamlankosi Nomnganga's Portfolio &copy; <span class="shadow">{{ cYear }}</span>
        </p>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'FooterComp',
    data() {
      return {
        cYear: new Date().getUTCFullYear(),
      };
    },
  };
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
  
  /* Footer Styling */
  .footer {
    color: #e0e0e0; /* Light grey text */
    background: #1a1a1a; /* Dark background */
    backdrop-filter: blur(10px); /* Blur effect */
    box-shadow: 0 -4px 6px rgba(0, 0, 0, 0.1); /* Subtle top shadow */
    text-align: center;
    padding: 15px 0;
    margin-top: auto; /* Push footer to the bottom */
    font-size: 14px;
    font-weight: 500;
    border-top: 1px solid #3a3a3a; /* Medium grey border */
  }
  
  .row-content {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .shadow {
    font-weight: bold;
    color: #b0b0b0; /* Slightly lighter grey */
  }
  
  /* Responsive Styling */
  @media (max-width: 768px) {
    .footer {
      font-size: 12px;
    }
  }
  </style>