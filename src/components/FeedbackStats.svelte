<script>
  export let count = 0;
  export let average = 0;
</script>

<div class="feedbackStats">
  <h4>{count} Reviews</h4>
  <h4>Rating average: {Math.round(average * 100) / 100}</h4>
</div>

<style>
  .feedbackStats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
