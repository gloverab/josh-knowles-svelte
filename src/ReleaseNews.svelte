<script>

  export let title
  export let headline
  export let img
  export let ctas
</script>

<h2 id='recent-release'>{title}</h2>
  
<h4 id='headline'>{headline}</h4>
<div id='img-and-ctas'>
  <div id='img-wrapper'>
    <img id='recent-release-img' src={img} />
  </div>
  <div id='spacer' />
  <div id='cta-list'>
    {#each ctas as cta}
      <a href={cta.link} target='blank' class='cta-item'>{cta.text}</a>
    {/each}
  </div>
</div>

<style>
  #img-and-ctas {
    display: flex;
    height: 150px;
  }

  #img-wrapper {
    width: 150px;
  }

  #recent-release-img {
    width: 100%;
    height: auto;
  }

  #spacer {
    width: 1rem;
  }

  #cta-list {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .cta-item {
    border: 1px solid rgba(255,255,255,.2);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 5px;
    color: white;
  }

  .cta-item:hover {
    border: 1px solid white;
    background-color: rgba(255,255,255,.2);
  }

  h2 {
    font-size: 1.5rem;
    text-transform: uppercase;
    font-weight: 300;
  }

  h4 {
    font-weight: 300;
  }

  #recent-release {
    margin-bottom: 1rem;
  }

  #headline {
    margin-bottom: 1rem;
  }
</style>