<script>
  import "$lib/css/sponsers.css";
    export let goldSponsors = [
      { name: "Google", logo: "/mitchell-luo-jz4ca36oJ_M-unsplash.jpg", link: "https://www.google.com", description: "Leading technology company specializing in internet services and AI." },
      { name: "Microsoft", logo: "/tadas-sar-T01GZhBSyMQ-unsplash.jpg", link: "https://www.microsoft.com", description: "Global leader in software, cloud computing, and enterprise solutions." }
    ];
  
    export let silverSponsors = [
      { name: "Amazon", logo: "/rubaitul-azad-J0eqDgSQDYg-unsplash.jpg", link: "https://www.amazon.com", description: "E-commerce giant with expertise in cloud services and AI." },
      { name: "Tesla", logo: "/milan-csizmadia-d0V_DQO_xUM-unsplash.jpg", link: "https://www.tesla.com", description: "Innovative electric vehicle and clean energy company." }
    ];
  
    export let bronzeSponsors = [
      { name: "Adobe", logo: "/farhat-altaf-Y7PI4VzzW6Q-unsplash.jpg", link: "https://www.adobe.com", description: "Pioneers in creative software, including Photoshop and Illustrator." },
      { name: "Spotify", logo: "/alexander-shatov-w-qqwn5O-4I-unsplash.jpg", link: "https://www.spotify.com", description: "Popular music streaming platform with personalized playlists." }
    ];
  </script>
  
  
  
  <section>
    <h2>🚀 Our Sponsors</h2>
  
   
    <div class="gold">
      <h3 class="tier-title">🥇 Gold Sponsors</h3>
      <div class="sponsors-container">
        {#each goldSponsors as sponsor}
          <div class="sponsor-card">
            <img class="sponsor-logo" src={sponsor.logo} alt={sponsor.name} />
            <h3>{sponsor.name}</h3>
            <p>{sponsor.description}</p>
            <a class="sponsor-link" href={sponsor.link} target="_blank">{sponsor.link}</a>
          </div>
        {/each}
      </div>
    </div>
  

    <div class="silver">
      <h3 class="tier-title">🥈 Silver Sponsors</h3>
      <div class="sponsors-container">
        {#each silverSponsors as sponsor}
          <div class="sponsor-card">
            <img class="sponsor-logo" src={sponsor.logo} alt={sponsor.name} />
            <h3>{sponsor.name}</h3>
            <p>{sponsor.description}</p>
            <a class="sponsor-link" href={sponsor.link} target="_blank">{sponsor.link}</a>
          </div>
        {/each}
      </div>
    </div>
  
    <div class="bronze">
      <h3 class="tier-title">🥉 Bronze Sponsors</h3>
      <div class="sponsors-container">
        {#each bronzeSponsors as sponsor}
          <div class="sponsor-card">
            <img class="sponsor-logo" src={sponsor.logo} alt={sponsor.name} />
            <h3>{sponsor.name}</h3>
            <p>{sponsor.description}</p>
            <a class="sponsor-link" href={sponsor.link} target="_blank">{sponsor.link}</a>
          </div>
        {/each}
      </div>
    </div>
  </section>
  
  