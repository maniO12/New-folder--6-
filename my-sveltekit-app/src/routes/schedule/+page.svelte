<script>
  import "$lib/css/schedule.css";
  import { onMount } from "svelte";
  export let schedule = [
    { date: "March 10, 2025", time: "10:00 AM - 11:00 AM", topic: "The Future of AI in Software Development", speaker: "Helly", image: "/istockphoto-1200116436-2048x2048.jpg", color: "#E63946" },
    { date: "March 10, 2025", time: "11:30 AM - 12:30 PM", topic: "Building Scalable Web Apps with Node.js", speaker: "Vishal", image: "/istockphoto-1382268922-2048x2048.jpg", color: "#06B6D4" },
    { date: "March 10, 2025", time: "2:00 PM - 3:00 PM", topic: "Design Thinking in UX/UI and developing", speaker: "Yashvi", image: "/istockphoto-1395161091-2048x2048.jpg", color: "#F4A261" },
    { date: "March 11, 2025", time: "10:00 AM - 11:00 AM", topic: "Cybersecurity Trends and Threats", speaker: "Amit", image: "/istockphoto-2189512641-2048x2048.jpg", color: "#3D5A80" },
    { date: "March 11, 2025", time: "11:30 AM - 12:30 PM", topic: "Leveraging Blockchain for Secure Transactions", speaker: "Andrew", image: "/taylor-grote-rnH5ITofDAM-unsplash.jpg", color: "#EF476F" },
    { date: "March 11, 2025", time: "2:00 PM - 3:00 PM", topic: "Big Data and Machine Learning", speaker: "Raj", image: "/jenean-newcomb-RzuxpXvwFbE-unsplash.jpg", color: "#06D6A0" },
    { date: "March 12, 2025", time: "10:00 AM - 11:00 AM", topic: "Cloud Computing Innovations", speaker: "Mohan", image: "/logan-weaver-lgnwvr-p0B7ueoZz8E-unsplash.jpg", color: "#457B9D" },
    { date: "March 12, 2025", time: "11:30 AM - 12:30 PM", topic: "Mastering Microservices with Node.js", speaker: "Sharma", image: "/mubariz-mehdizadeh-t3zrEm88ehc-unsplash.jpg", color: "#8338EC" }
  ];

  function getTimeInMs(date, time) {
    const dateParts = date.split(" ");
    const day = parseInt(dateParts[1], 10);
    const month = new Date(Date.parse(dateParts[0] + " 1, 2025")).getMonth();
    const year = 2025;

    const [start, end] = time.split(" - ");
    const parseTime = (t) => {
      let [hours, minutes] = t.replace(/(AM|PM)/, "").split(":").map(Number);
      if (t.includes("PM") && hours !== 12) hours += 12;
      if (t.includes("AM") && hours === 12) hours = 0;
      return { hours, minutes };
    };

    const { hours: startHour, minutes: startMinute } = parseTime(start);
    const { hours: endHour, minutes: endMinute } = parseTime(end);

    const startDate = new Date(year, month, day, startHour, startMinute);
    const endDate = new Date(year, month, day, endHour, endMinute);
    return { startDate, endDate };
  }

  function updateSchedule() {
    const now = new Date();
    schedule = schedule.filter(session => getTimeInMs(session.date, session.time).endDate > now);
  }

  onMount(() => {
    updateSchedule(); // Remove expired sessions on load
    const interval = setInterval(updateSchedule, 60000);
    return () => clearInterval(interval);
  });
</script>



<section>
  <h2>📅 Conference Schedule</h2>
  <div class="schedule-container">
    {#each schedule as session}
      <div class="schedule-card" style="background-color: {session.color};">
        <img class="schedule-img" src={session.image} alt={session.speaker} />
        <div class="card-header">
          <h3>{session.topic}</h3>
        </div>
        <div class="card-content">
          <p><strong>📅 Date:</strong> {session.date}</p>
          <p><strong>⏰ Time:</strong> {session.time}</p>
          <p><strong>🎤 Speaker:</strong> {session.speaker}</p>
        </div>
      </div>
    {/each}
  </div>
</section>
