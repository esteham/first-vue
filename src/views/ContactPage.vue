<template>
  <div class="container mt-5">
    <h1 class="text-center mb-4">Contact Us</h1>
    <div class="row">
      <div class="col-md-6">
        <h3>Get in Touch</h3>
        <p>If you have any questions or need assistance, feel free to reach out to us using the form below or the contact information provided.</p>
        <ul class="list-unstyled">
          <li><strong>Address:</strong> 123 Clinic Street, City, State 12345</li>
          <li><strong>Phone:</strong> (123) 456-7890</li>
          <li><strong>Email:</strong> info@clinic.com</li>
        </ul>
      </div>
      <div class="col-md-6">
        <form>
          <div class="mb-3">
            <label for="name" class="form-label">Name</label>
            <input type="text" class="form-control" id="name" placeholder="Your Name" required>
          </div>
          <div class="mb-3">
            <label for="email" class="form-label">Email</label>
            <input type="email" class="form-control" id="email" placeholder="your@email.com" required>
          </div>
          <div class="mb-3">
            <label for="message" class="form-label">Message</label>
            <textarea class="form-control" id="message" rows="5" placeholder="Your message here..." required></textarea>
          </div>
          <button type="submit" class="btn btn-primary">Send Message</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Add any custom styles if needed */
</style>
