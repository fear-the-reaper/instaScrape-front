<script setup>
    import { onMounted } from 'vue';
    import card from '../components/card.vue';
    let results = {
	'post_url': 'https://www.instagram.com/p/CrTdpzkra0-/',
	'comments': [{
		'username': 'ggc_dr.zaius',
		'comment': 'Rest in paradise to Kevin Conroy the greatest of all and he will be missed but his legacy will always live on',
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}, {
		'username': 'jaysonpaceleader',
		'comment': 'Its a Beautiful Cast. I love Them😍😍😍😍😍😍😍😍😍',
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}, {
		'username': 'susaneisenberg1',
		'comment': 'What a beautiful, touching post. Thank you!! 💛❤️💙',
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}, {
		'username': 'king_hubby_',
		'comment': 'What justice league series is this please can anyone answer me',
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}, {
		'username': 'ap3_the_collector',
		'comment': "These guys's voices are the voices that I will forever hear in my head everytime I'm reading the comics.",
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'neutral'
	}, {
		'username': 'journeyblue84',
		'comment': "I met him b4 COVID pandemic. He's  FANTASTIC",
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}, {
		'username': 'sunhaitao010501',
		'comment': 'They are the best Justice League voice cast ever!😆👍😀🙌',
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}, {
		'username': 'quietriot24',
		'comment': '❤️❤️❤️',
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'neutral'
	}, {
		'username': 'dariusthurman',
		'comment': "We'll never forget you Batman.😢😢",
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}, {
		'username': 'savage_christian_kombatant',
		'comment': 'RIP KEVIN CONROY THE ORIGINAL AND ARKHAM BATMAN',
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}, {
		'username': 'savage_christian_kombatant',
		'comment': 'Love them all. Awesome voice acting by the cast',
		'is_complaint': false,
		'is_cs_comment': false,
		'sentiment': 'positive'
	}]
    }

    onMounted(() => {
        console.log("This was mounted!");
    })


</script>

<template>
    <div class="m-4 has-text-centered">
        Results of post are
    </div>
    <div class="is-flex is-flex-wrap-wrap is-justify-content-center">
        <card v-for="(comment, index) in results.comments" :comment-number=index+1 :comment="comment.comment" :username="comment.username"></card>
    </div>
</template>



<style>

</style>