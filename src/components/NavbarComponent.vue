<template>

    <nav class="navbar navbar-expand-lg bg-success sticky-top">
        <div class="container-fluid">
            <router-link class="navbar-brand" to="/">
                <img src="https://lamlankosi.github.io/project_images/Images/LN_logo.png" alt="logo">
            </router-link>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link active" aria-current="page" href="#home">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#about">About Me</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#education-experience">Education & Experience</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#projects">Projects</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#contact-me">Contact Me</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

</template>

<script>
export default {

}
</script>

<style scoped></style>