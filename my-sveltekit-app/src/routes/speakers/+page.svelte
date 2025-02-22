<script>
  import "$lib/css/speakers.css";
  let speakers = [
    { 
      name: "Vishal", 
      title: "Senior Developer", 
      image: "/istockphoto-1200116436-2048x2048.jpg",
      bio: "Vishal is a seasoned developer with 10+ years of experience in web technologies. He specializes in building high-performance applications."
    },
    { 
      name: "Sharma", 
      title: "Tech Lead", 
      image: "/istockphoto-1382268922-2048x2048.jpg",
      bio: "Sharma has led multiple tech teams and played a key role in scaling high-traffic applications with modern architectures."
    },
    { 
      name: "Yashvi", 
      title: "UX Designer", 
      image: "/istockphoto-1395161091-2048x2048.jpg",
      bio: "Yashvi is a UX expert with a passion for creating intuitive and visually appealing user interfaces."
    },
    { 
      name: "Helly", 
      title: "AI Engineer", 
      image: "/istockphoto-2189512641-2048x2048.jpg",
      bio: "Helly is an AI researcher focused on deep learning and automation. He has worked on AI-powered solutions for various industries."
    },
    { 
      name: "Amit", 
      title: "Cybersecurity Analyst", 
      image: "/mubariz-mehdizadeh-t3zrEm88ehc-unsplash.jpg",
      bio: "Amit is an expert in cybersecurity, specializing in threat analysis and risk assessment for enterprise systems."
    },
    { 
      name: "Mohan", 
      title: "Blockchain Developer", 
      image: "/logan-weaver-lgnwvr-p0B7ueoZz8E-unsplash.jpg",
      bio: "Mohan is a blockchain enthusiast working on decentralized applications and smart contracts for secure transactions."
    },
    { 
      name: "Raj", 
      title: "Data Scientist", 
      image: "/jenean-newcomb-RzuxpXvwFbE-unsplash.jpg",
      bio: "Raj leverages big data and machine learning to drive insights and create predictive models for various industries."
    },
    { 
      name: "Andrew", 
      title: "Cloud Architect", 
      image: "/taylor-grote-rnH5ITofDAM-unsplash.jpg",
      bio: "Andrew specializes in cloud computing innovations and has worked with major cloud service providers to design scalable solutions."
    }
  ];
</script>


<div class="page-container">
  <h1>Meet Our Speakers</h1>
  <p>Learn from industry experts at our conference.</p>

  <div class="speakers-container">
    {#each speakers as speaker}
      <div class="speaker-card">
        <img src={speaker.image} alt={speaker.name} />
        <h3>{speaker.name}</h3>
        <p><strong>{speaker.title}</strong></p>
        <p class="bio">{speaker.bio}</p>
      </div>
    {/each}
  </div>
</div>
