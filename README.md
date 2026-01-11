<!DOCTYPE html>
<html>
<head>
  <title>Location Tracker</title>
</head>
<body>
  <h2>Izinkan Lokasi</h2>
  <button onclick="getLocation()">Bagikan Lokasi</button>

  <p id="result"></p>

  <script>
    function getLocation() {
      if (!navigator.geolocation) {
        alert("Browser tidak mendukung GPS");
        return;
      }

      navigator.geolocation.getCurrentPosition(
        (pos) => {
          const lat = pos.coords.latitude;
          const lon = pos.coords.longitude;

          document.getElementById("result").innerHTML =
            `Lokasi: <br>
            Latitude: ${lat}<br>
            Longitude: ${lon}<br>
            <a href="https://maps.google.com/?q=${lat},${lon}" target="_blank">
              Buka di Google Maps
            </a>`;
        },
        () => alert("Izin lokasi ditolak")
      );
    }
  </script>
</body>
</html>
