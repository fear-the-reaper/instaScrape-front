<script setup>
    // in <script setup>
    defineProps({
        commentNumber: Number,
        username: String,
        comment: String
    })
</script>


<template>
    <div id="comment_card" class="card m-2 size">
        <header class="card-header p-4 is-shadowless">
            <div class="rounded has-text-weight-bold has-text-white has-text-centered has-background-primary">
                {{ commentNumber }}
            </div>
        </header>
        <div class="card-content">
            <div class="content has-text-weight-bold">
                {{ username }}
            </div>
            <div class="content">
                {{ comment }}
            </div>
        </div>
        <footer class="card-footer p-2">
            <button class="button is-info is-light">Read more</button>
        </footer>
    </div>  
</template>

<style scoped>

    .card:hover {
        border: 2px solid #2213F6;
    }

    .size {
        /* height: 25px; */
        width: 25%;
    }

    .rounded {
        height: 25px;
        width: 25px;
        border-radius: 50%;
    }

</style>