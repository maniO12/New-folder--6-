<script>
  import "$lib/Css/SpeakersCard.css";
  export let speakers = [
      { name: "Vishal", title: "Senior Developer", image: "/istockphoto-1200116436-2048x2048.jpg", class: "speaker-vishal" },
      { name: "Sharma", title: "Tech Lead", image: "/istockphoto-1382268922-2048x2048.jpg", class: "speaker-sharma" },
      { name: "Yashvi", title: "UX Designer", image: "/istockphoto-1395161091-2048x2048.jpg", class: "speaker-yashvi" },
      { name: "Helly", title: "AI Engineer", image: "/istockphoto-2189512641-2048x2048.jpg", class: "speaker-helly" }
  ];
</script>

<section>
  <h2 class="speakers-title">Meet Our Speakers</h2>
  <div class="speakers-grid">
      {#each speakers as speaker}
          <div class="speaker-card {speaker.class}">
              <img class="speaker-img" src={speaker.image} alt={speaker.name} />
              <div class="speaker-name">{speaker.name}</div>
              <div class="speaker-title">{speaker.title}</div>
          </div>
      {/each}
  </div>
</section>
