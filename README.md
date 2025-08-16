<!DOCTYPE html>
<html lang="ms">
<head>
  <meta charset="UTF-8">
  <title>Wedding Invitation</title>
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <style>
    /* Basic styling for tabs and content */
    body { font-family: sans-serif; margin: 0; padding: 0; }
    nav { display: flex; background: #ececec; }
    nav button { flex: 1; padding: 1em; border: none; background: #ddd; cursor: pointer; }
    nav button.active { background: #bbb; }
    section { display: none; padding: 1em; }
    section.active { display: block; }
    form input, form select, form button { display: block; margin: .5em 0; padding: .5em; width: 100%; }
  </style>
</head>
<body>
  <nav>
    <button class="tab-btn active" data-target="rsvp">RSVP</button>
    <button class="tab-btn" data-target="contact">Contact</button>
    <button class="tab-btn" data-target="location">Location</button>
    <button class="tab-btn" data-target="calendar">Calendar</button>
    <button class="tab-btn" data-target="money">Money Gift</button>
    <button class="tab-btn" data-target="wishlist">Wishlist</button>
  </nav>

  <section id="rsvp" class="active">
    <h2>RSVP</h2>
    <form id="rsvpForm">
      <label>Nama Anda<input type="text" name="name" required></label>
      <label>Hadir/Tidak Hadir 
        <select name="status"><option>Hadir</option><option>Tidak Hadir</option></select>
      </label>
      <label>Slot Masa
        <select name="slot">
          <option>11:00–12:30</option>
          <option>12:30–14:30</option>
          <option>14:30–16:00</option>
        </select>
      </label>
      <label>Jumlah Dewasa <input type="number" name="adult" value="1" min="0"></label>
      <label>Jumlah Kanak-kanak <input type="number" name="kids" value="0" min="0"></label>
      <button type="submit">Hantar</button>
      <button type="reset">Batal</button>
    </form>
    <p id="rsvpResponse"></p>
  </section>

  <section id="contact">
    <h2>Contact</h2>
    <p>Mariani &amp; Mazlan</p>
  </section>

  <section id="location">
    <h2>Location</h2>
    <p>Bukit Beruntung Golf Club, Rawang, Selangor</p>
    <a href="https://maps.google.com" target="_blank">Google Maps</a> |
    <a href="https://waze.com" target="_blank">Waze</a>
  </section>

  <section id="calendar">
    <h2>Calendar</h2>
    <a href="#" onclick="addToCalendar('google')">Add to Google Calendar</a><br>
    <a href="#" onclick="addToCalendar('apple')">Add to Apple Calendar</a>
  </section>

  <section id="money">
    <h2>Money Gift</h2>
    <p>Maybank Berhad – 162076697556</p>
    <img src="qrcode.png" alt="QR Code">
  </section>

  <section id="wishlist">
    <h2>Wishlist</h2>
    <div>
      <div><img src="item1.jpg" alt="Item 1"><a href="#">Tempaℎ</a></div>
      <div><img src="item2.jpg" alt="Item 2"><a href="#">Tempaℎ</a></div>
    </div>
  </section>

  <script>
    // Tab navigation
    document.querySelectorAll('.tab-btn').forEach(btn => {
      btn.onclick = () => {
        document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        document.querySelectorAll('section').forEach(sec => sec.classList.remove('active'));
        document.getElementById(btn.dataset.target).classList.add('active');
      };
    });

    // RSVP form handling (client-side)
    document.getElementById('rsvpForm').addEventListener('submit', e => {
      e.preventDefault();
      const data = new FormData(e.target);
      const name = data.get('name');
      document.getElementById('rsvpResponse').textContent =
        `Terima kasih, ${name}! RSVP Anda telah direkodkan.`;
      e.target.reset();
    });

    // Stub for Add to Calendar
    function addToCalendar(type) {
      alert(`Implement logic to add event to ${type} calendar.`);
    }
  </script>
</body>
</html>
