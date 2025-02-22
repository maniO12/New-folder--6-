<script>
    import { onMount } from "svelte";
    import "$lib/css/contact.css";

    let theme = "light";

    function updateTheme() {
        theme = document.documentElement.getAttribute("data-theme") || "light";
    }

    onMount(() => {
        updateTheme();
        const observer = new MutationObserver(updateTheme);
        observer.observe(document.documentElement, { attributes: true, attributeFilter: ["data-theme"] });
    });

    function handleSubmit(event) {
        event.preventDefault();
        alert("Message sent successfully!");
    }
</script>

<section class="contact-section">
    <div class="contact-container">
        <h1 class="contact-title">Get in Touch</h1>
        <p class="contact-description">
            Have questions or just want to say hello? Fill out the form below, and let's connect!
        </p>

        <form class="contact-form" on:submit={handleSubmit}>
            <div class="input-group">
                <label for="name">Your Name</label>
                <input type="text" id="name" required />
            </div>

            <div class="input-group">
                <label for="email">Your Email</label>
                <input type="email" id="email" required />
            </div>

            <div class="input-group">
                <label for="message">Your Message</label>
                <textarea id="message" rows="5" required></textarea>
            </div>

            <button type="submit" class="submit-btn">Send Message</button>
        </form>
    </div>

    <div class="social-icons-container">
        <div class="social-icons">
            <a href="https://www.facebook.com" class="social-icon" aria-label="Facebook">
                <i class="fab fa-facebook-f"></i>
            </a>
            <a href="https://www.twitter.com" class="social-icon" aria-label="Twitter">
                <i class="fab fa-twitter"></i>
            </a>
            <a href="https://www.linkedin.com" class="social-icon" aria-label="LinkedIn">
                <i class="fab fa-linkedin-in"></i>
            </a>
            <a href="https://www.instagram.com" class="social-icon" aria-label="Instagram">
                <i class="fab fa-instagram"></i>
            </a>
        </div>
    </div>
</section>
