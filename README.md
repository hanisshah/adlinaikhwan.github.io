<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>You're Invited!</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body { font-family: 'Georgia', serif; margin: 0; padding: 0; background: #fdfdfd; color: #333; }
    header { background: url('cover.jpg') center/cover no-repeat; height: 60vh; display: flex; align-items: center; justify-content: center; }
    header h1 { color: #fff; font-size: 4vw; background: rgba(0,0,0,0.4); padding: 1em; }
    .details { padding: 2em; text-align: center; }
    .details p { margin: 0.5em 0; font-size: 1.2em; }
    .rsvp { background: #eee; padding: 2em; text-align: center; }
    .rsvp input, .rsvp button, .rsvp textarea { margin: 0.5em; padding: 0.8em; font-size: 1em; }
    .rsvp input[type="text"] { width: 60%; max-width: 300px; }
    .rsvp textarea { width: 60%; max-width: 300px; height: 100px; }
  </style>
</head>
<body>
  <header>
    <h1>Asyraf & Aisyah</h1>
  </header>

  <section class="details">
    <p><strong>Date:</strong> 25 October 2025</p>
    <p><strong>Time:</strong> 4 PM</p>
    <p><strong>Venue:</strong> KL Convention Centre</p>
    <p><strong>Address:</strong> Jalan Pinang, Kuala Lumpur, Malaysia</p>
  </section>

  <section class="rsvp">
    <h2>RSVP</h2>
    <form id="rsvpForm">
      <input type="text" name="name" placeholder="Your Name" required><br>
      <input type="text" name="guests" placeholder="Number of Guests" required><br>
      <textarea name="message" placeholder="Message (optional)"></textarea><br>
      <button type="submit">Submit</button>
    </form>
    <p id="rsvpResponse"></p>
  </section>

  <script>
    document.getElementById('rsvpForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const name = this.name.value.trim();
      const guests = this.guests.value.trim();
      // You could send data via AJAX to your server here.
      document.getElementById('rsvpResponse').textContent =
        `Thank you, ${name}! We have received your RSVP for ${guests} guest(s).`;
      this.reset();
    });
  </script>
</body>
</html>
