<script>
    import { onMount } from "svelte";
      import "$lib/Css/Timer.css";
    let days = "00",
        hours = "00",
        minutes = "00",
        seconds = "00";

    function updateCountdown() {
        const eventDate = new Date("March 25, 2025 00:00:00").getTime();
        const now = new Date().getTime();
        const timeRemaining = eventDate - now;

        if (timeRemaining <= 0) {
            days = hours = minutes = seconds = "00";
            return;
        }

        days = String(Math.floor(timeRemaining / (1000 * 60 * 60 * 24))).padStart(2, "0");
        hours = String(Math.floor((timeRemaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))).padStart(2, "0");
        minutes = String(Math.floor((timeRemaining % (1000 * 60 * 60)) / (1000 * 60))).padStart(2, "0");
        seconds = String(Math.floor((timeRemaining % (1000 * 60)) / 1000)).padStart(2, "0");
    }

    onMount(() => {
        updateCountdown();
        setInterval(updateCountdown, 1000);
    });
</script>


<div class="countdown-container">
    <h1 class="countdown-title">TechConf 2025 Countdown</h1>
    <p class="countdown-description">Join us for the biggest tech event of the year on <strong>March 25, 2025</strong>!</p>

    <div class="countdown-timer">
        <div class="time-box">
            <span>{days}</span>
            <small>Days</small>
        </div>
        <div class="time-box">
            <span>{hours}</span>
            <small>Hours</small>
        </div>
        <div class="time-box">
            <span>{minutes}</span>
            <small>Minutes</small>
        </div>
        <div class="time-box">
            <span>{seconds}</span>
            <small>Seconds</small>
        </div>
    </div>
</div>
