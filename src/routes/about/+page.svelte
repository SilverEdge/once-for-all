<script>
import Footer from '../../components/footer.svelte';
import { onMount } from 'svelte';
onMount(() => {
        // Trigger the ESV Cross-Reference Tool script (app.html runs on window.load event, so rerun)
        window.dispatchEvent(new Event('esv-crossref.trigger-linkify'));
    });
</script>

<svelte:head>
   <title>About</title>
</svelte:head>

<div style="position: absolute;top:60px;left:0px;">
<div class='content' >
    <h1>About</h1>
    <br>
    <div style="font-weight:bold;line-height: 2em;">The blog title "Once for all" comes from <span>Hebrews 1:1</span>, John 3:16 andthe mision of this blog is to carry out the commission to spread the gospel as defined by John 3:16. The word for love used here is not somekind of lesser love. It is Agapeo, the verb form describing Agaoe love, or sacrificial love.Hello and welcome to Once for All. My nace is Chase Conrad and I'm the founder of this blog. I've always enjoyed philosophy For years I prayed that God would increase my desire to learn His Word. In marriage, I was grafted into a church that adhered to systematic theoloffy, and it opened up a world of discovery. Assumptions where challanged and the rest is history. This blog is really just a collection of my thoughts. But, I hope in publishing them others might glean what is useful and toss that whichi is not.My prayerThis blog was.
        On a personal note, I married my beautifil wife, Emily, on Jan 28, 24. I enjoy playing soccer and <a href="">chess</a> though I don't prfes to be particularily god at either. I'm curenly working throght <a href="">Bill Mounce's Greek course</a> and hope to pursue a degree in through <a href="">Bible Training</a>. Thank you for stopping by!
    </div>
</div>
<Footer />
</div>

<style>
.content {
    padding:50px;
    position: relative;
    background-image: url('/stardust.png');
    background-repeat: repeat;
    color: #eeeeee;
}
</style>