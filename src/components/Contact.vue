<template>
  <section id="contact" class="contact">
    <h2>Contact Me</h2>
    <p>Feel free to reach out!</p>

    <div class="contact-links">
      <!-- Email -->
      <a href="mailto:firon.fariz.tif425@polban.ac.id" target="_blank" class="contact-item">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="#6c63ff" viewBox="0 0 24 24">
          <path d="M12 13.5l-11-7.5v15h22v-15l-11 7.5z"/>
          <path d="M12 0l-12 8.25 12 8.25 12-8.25-12-8.25z"/>
        </svg>
        Email
      </a>

      <!-- Instagram -->
      <a href="https://www.instagram.com/frnshlk" target="_blank" class="contact-item">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="#6c63ff" viewBox="0 0 24 24">
          <path d="M12 2.163c3.204 0 3.584.012 4.849.07 1.366.062 2.633.348 3.608 1.323.975.975 1.261 2.242 1.323 3.608.058 1.265.07 1.645.07 4.849s-.012 3.584-.07 4.849c-.062 1.366-.348 2.633-1.323 3.608-.975.975-2.242 1.261-3.608 1.323-1.265.058-1.645.07-4.849.07s-3.584-.012-4.849-.07c-1.366-.062-2.633-.348-3.608-1.323-.975-.975-1.261-2.242-1.323-3.608-.058-1.265-.07-1.645-.07-4.849s.012-3.584.07-4.849c.062-1.366.348-2.633 1.323-3.608.975-.975 2.242-1.261 3.608-1.323 1.265-.058 1.645-.07 4.849-.07zm0-2.163c-3.259 0-3.667.012-4.947.072-1.567.072-2.96.363-4.064 1.467-1.104 1.104-1.395 2.497-1.467 4.064-.06 1.28-.072 1.688-.072 4.947s.012 3.667.072 4.947c.072 1.567.363 2.96 1.467 4.064 1.104 1.104 2.497 1.395 4.064 1.467 1.28.06 1.688.072 4.947.072s3.667-.012 4.947-.072c1.567-.072 2.96-.363 4.064-1.467 1.104-1.104 1.395-2.497 1.467-4.064.06-1.28.072-1.688.072-4.947s-.012-3.667-.072-4.947c-.072-1.567-.363-2.96-1.467-4.064-1.104-1.104-2.497-1.395-4.064-1.467-1.28-.06-1.688-.072-4.947-.072z"/>
          <path d="M12 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.162 6.162 6.162 6.162-2.759 6.162-6.162-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.791-4-4s1.791-4 4-4 4 1.791 4 4-1.791 4-4 4z"/>
          <circle cx="18.406" cy="5.594" r="1.44"/>
        </svg>
        Instagram
      </a>
    </div>
  </section>
</template>

<style scoped>
.contact {
  padding: 4rem 2rem;
  text-align: center;
  font-family: 'Poppins', sans-serif;
  background: #f8f8f8;
  border-radius: 20px;
  margin-top: 3rem;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 2rem;
  flex-wrap: wrap;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #6c63ff;
  font-weight: 500;
  text-decoration: none;
  transition: transform 0.3s ease;
}

.contact-item:hover {
  transform: translateY(-3px);
}

.contact-item svg {
  width: 24px;
  height: 24px;
}
</style>