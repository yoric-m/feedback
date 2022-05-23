<script>
  import FeedbackList from "./components/FeedbackList.svelte";
  import FeedbackStats from "./components/FeedbackStats.svelte";

  let feedback = [
    {
      id: 1,
      rating: 10,
      text: "Exercitation laboris irure et pariatur dolore deserunt anim.",
    },
    {
      id: 2,
      rating: 4,
      text: "Cupidatat nostrud nulla et eiusmod.",
    },
    {
      id: 3,
      rating: 6,
      text: "Eiusmod occaecat irure eu quis ipsum qui in ullamco ipsum dolor amet. Aliqua irure est duis enim non voluptate tempor adipisicing anim esse commodo ipsum id. In ipsum irure qui non voluptate magna mollit sit. In ipsum ut esse cupidatat cillum labore voluptate adipisicing sunt.",
    },
  ];
  let count;
  let average;
  $: count = feedback.length;
  $: average =
    feedback.reduce((prev, current) => prev + current.rating, 0) / count;
</script>

<main class="container">
  <FeedbackStats {count} {average} />
  <FeedbackList
    {feedback}
    on:delete-feedback={(fb) =>
      (feedback = feedback.filter((e) => e.id !== fb.detail))}
  />
</main>
