<script>
  import Card from "smelte/src/components/Card";
  import Button from "smelte/src/components/Button";
  import Image from "smelte/src/components/Image";
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
  <Card.Card>
    <div slot="title">
      <Card.Title
        title="Bridge Test"
        subheader="lots o' bridges"
        />
    </div>
    <div slot="media">
      <Image
        class="w-full"
        src="https://upload.wikimedia.org/wikipedia/commons/3/3f/Luzern_Kapellbruecke.jpg"
        alt="bridge"
      />
	<h2>
		try editing <strong>src/routes/index.svelte</strong>
	</h2>
    </div>
  </Card.Card>

</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}
</style>
