<template>
    <div class="contact">
        <h1>Contact Me</h1>
        <div class="contactMe">
            <div class="contact">
                <form @submit.prevent="validateAndSubmit">
                    <form action="https://formspree.io/f/xblrvroz" method="POST">
                        <label>
                            Your email:
                            <input type="email" name="email">
                        </label>
                        <label>
                            Your message:
                            <textarea name="message"></textarea>
                        </label>
                        <!-- your other form fields go here -->
                        <button type="submit">Send</button>
                    </form>
                </form>
            </div>

        </div>
    </div>


</template>

<script>
export default {
    data() {
        return {
            formData: {
                name: '',
                email: '',
                message: ''
            }
        };
    },
    methods: {
        validateAndSubmit() {
            if (!this.formData.name || !this.formData.email || !this.formData.message) {
                alert('Please fill in all fields.');
                return;
            }

            // Additional validation logic for email format
            if (!this.isValidEmail(this.formData.email)) {
                alert('Please enter a valid email address.');
                return;
            }

            // Proceed with form submission logic
            this.submitForm();
        },
        isValidEmail(email) {
            // Basic email validation regex
            return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
        },
        submitForm() {
            // Logic to submit the form data
            console.log('Form submitted:', this.formData);
            // Example: send form data to backend or handle submission
        }
    }
};
</script>

<style>
.contact{
    background: black;
}
.contactMe {
    gap: rem;
    /* align-items: center; */
    /* padding: 2rem; */
}

.content {
    width: 50%;
}



label {
    display: inline;
    margin-bottom: 5px;
}

input,
textarea {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-sizing: border-box;
}



button {
    /* margin-top: 2rem; */
    width: 100px;
    border: 2px solid white;
}

@media screen and (max-width: 800px) {
    .contactMe {
        flex-direction: column;
        align-items: center;
        gap: 1rem;
        padding: 1rem;
    }

    .details {
        width: 100%;
        margin-top: 1rem;
    }
}
</style>