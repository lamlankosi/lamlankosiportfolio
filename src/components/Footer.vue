<template>
    <footer class="footer">
        <div class="row-content">
            <p>
                Lamlankosi Nomnganga's Portfolio &copy;<span class="shadow">{{ cYear }}</span>
            </p>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'footerComp',
    data() {
        return {
            cYear: new Date().getUTCFullYear()
        };
    }
};
</script>

<style scoped>
/* html, body {
    height: 100%;
    margin: 0;
} */

/* .wrapper {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
} */

/* .container-fluid {
    flex: 1; /* Ensure main content takes available space 
}
 */


.row-content {
    display: flex;
    justify-content: center; /* Center content in the footer */
    align-items: center; /* Align items vertically */
}
</style>
