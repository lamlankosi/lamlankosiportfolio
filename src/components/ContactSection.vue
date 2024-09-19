<template>
    <div class="contact vw-100">
        <h1>Contact Me</h1>
        <div class="container">
            <div class="details">
                    <p><i class="bi bi-envelope"></i> : lamlanomnganga9@gmail.com</p>
                    <p><i class="bi bi-github"></i> :lamlankosi</p>
                    <p><i class="bi bi-linkedin"></i> :Lamla Nomnganga</p>
                    <p><i class="bi bi-telephone-fill"></i> :072938854</p>
            </div>
            <div class="contactMe">
                
                <!-- <div class="contact"> -->
                        <form action="https://formspree.io/f/xblrvroz" method="POST">
                            <label>
                                Your email:
                                <input type="email" name="email">
                            </label>
                            <label>
                                Your message:
                                <textarea name="message"></textarea>
                            </label>
                            <button type="submit">Send</button>
                    </form>
            </div>

        </div>

    </div>

        <!-- </div> -->


</template>

<script>
export default {
}
</script>
<style scoped>
.container{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}
.contact {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 20px;
    margin-top: 50px;
}

.contactMe {
    color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 500px;
}

.contact h1 {
    font-size: 28px;
   
    margin-bottom: 20px;
}

form {
    width: 100%;
    display: flex;
    flex-direction: column;
}

form label {
    margin-bottom: 10px;
    font-size: 16px;
    
}

input[type="email"],
textarea {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    margin-bottom: 15px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
}

textarea {
    min-height: 100px;
    resize: vertical;
}

button[type="submit"] {
    padding: 10px 15px;
    background-color: black;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
}

button[type="submit"]:hover {
    background-color: white;
    color: black;
}

/* .contactMe {
    gap: rem;
    /* align-items: center; */
    /* padding: 2rem; 
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


*/
/* button {
     margin-top: 2rem;
    width: 100px;
    border: 2px solid white;
} */

@media screen and (max-width: 800px) {
    /* .contactMe {
        flex-direction: column;
        align-items: center;
        gap: 1rem;
        padding: 1rem;
    }

    .details {
        width: 100%;
        margin-top: 1rem;
    } */
}

</style>