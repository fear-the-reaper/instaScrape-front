<script setup>
    import { onMounted, ref, toRefs } from 'vue';
    
    const data = ref({});
    
    const props = defineProps({
        id: String,
        comment: String
    })

    const {id, comment} = toRefs(props);

    const sentiment_table = {
        "positive": "🙂",
        "negative": "😞",
        "neutral": "😐",
    }

    onMounted(() => {
        data.value = JSON.parse(comment.value);
    })



</script>

<template>
    <div class="box p-6 is-shadowless">
        <div class="title is-3">
            {{ data.username }}    
        </div>
        <div class="px-4 mt-4 subtitle is-5">
            <span class="has-text-weight-semibold has-text-dark">
                comment:
            </span>
            {{ data.comment }}    
        </div>
        <div class="px-4 mt-6 subtitle is-5">
            <span class="has-text-weight-semibold has-text-dark">
                sentiment:
            </span>
            {{ sentiment_table[data.sentiment] }}    
        </div>
        <div class="px-4 mt-6 subtitle is-5">
            <span class="has-text-weight-semibold has-text-dark">
                complaint:
            </span>
            <span v-if="data.is_complaint">
                ✅ 
            </span>
            <span v-else>
                ❌ 
            </span>    
        </div>
        <div class="px-4 mt-6 subtitle is-5">
            <span class="has-text-weight-semibold has-text-dark">
                CS related:
            </span>
            <span v-if="data.is_cs_comment">
                ✅ 
            </span>
            <span v-else>
                ❌ 
            </span>    
        </div>
    </div>
    <!-- <div>
        The comment id is  {{ id }}
    </div>
    <div class="title  is-">
        {{ data.username }}
    </div> -->
</template>



<style scoped>

</style>