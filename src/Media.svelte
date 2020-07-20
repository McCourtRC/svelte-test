<script>
  export let props;
  const { name, short_description, long_description } = props;
</script>

<style>
  .media {
    margin-bottom: 60px;
  }
</style>

<div class="media">
  <b>{name}</b>
  <p>{long_description}</p>
</div>
