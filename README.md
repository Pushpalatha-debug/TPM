<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>TPM Worship Music</title>

  <style>

    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      font-family:Arial, sans-serif;
    }

    body{
      background:#121212;
      color:white;
      overflow:hidden;
    }

    /* SPLASH SCREEN */

    #splash{
      position:fixed;
      width:100%;
      height:100vh;
      background:black;
      display:flex;
      justify-content:center;
      align-items:center;
      flex-direction:column;
      z-index:1000;
      animation:fadeOut 2s ease forwards;
      animation-delay:3s;
    }

    #splash img{
      width:140px;
      margin-bottom:20px;
      border-radius:50%;
    }

    #splash h1{
      font-size:35px;
      color:#1db954;
      letter-spacing:2px;
    }

    @keyframes fadeOut{
      to{
        opacity:0;
        visibility:hidden;
      }
    }

    /* MAIN APP */

    .app{
      display:none;
      height:100vh;
    }

    .sidebar{
      width:220px;
      background:black;
      padding:20px;
    }

    .sidebar h2{
      color:#1db954;
      margin-bottom:30px;
    }

    .sidebar ul{
      list-style:none;
    }

    .sidebar ul li{
      padding:15px 0;
      cursor:pointer;
      color:#ccc;
    }

    .sidebar ul li:hover{
      color:white;
    }

    .main{
      flex:1;
      padding:20px;
      overflow-y:auto;
    }

    .topbar{
      display:flex;
      justify-content:space-between;
      align-items:center;
      margin-bottom:30px;
    }

    .topbar select{
      padding:10px;
      border:none;
      border-radius:5px;
      background:#282828;
      color:white;
    }

    .songs{
      display:flex;
      gap:20px;
      flex-wrap:wrap;
    }

    .card{
      width:180px;
      background:#181818;
      padding:15px;
      border-radius:12px;
      transition:0.3s;
      cursor:pointer;
    }

    .card:hover{
      background:#282828;
      transform:scale(1.05);
    }

    .card img{
      width:100%;
      border-radius:10px;
      margin-bottom:10px;
    }

    .card h3{
      font-size:18px;
    }

    .player{
      position:fixed;
      bottom:0;
      width:100%;
      background:#181818;
      padding:10px;
    }

    audio{
      width:100%;
    }

  </style>
</head>

<body>

<!-- SPLASH SCREEN -->

<div id="splash">

  <!-- TPM LOGO -->
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/89/HD_transparent_picture.png">

  <h1>TPM WORSHIP</h1>

</div>

<!-- MAIN APP -->

<div class="app" id="app">

  <!-- SIDEBAR -->

  <div class="sidebar">

    <h2>TPM Music</h2>

    <ul>
      <li>Home</li>
      <li>Playlists</li>
      <li>Favorites</li>
      <li>Choir Songs</li>
    </ul>

  </div>

  <!-- MAIN CONTENT -->

  <div class="main">

    <div class="topbar">

      <h1>Worship Songs</h1>

      <!-- LANGUAGE SELECT -->

      <select id="language">

        <option>Telugu</option>
        <option>Hindi</option>
        <option>English</option>
        <option>Tamil</option>

      </select>

    </div>

    <!-- SONGS -->

    <div class="songs">

      <div class="card" onclick="playSong('songs/song1.mp3')">

        <img src="https://images.unsplash.com/photo-1516280440614-37939bbacd81?q=80&w=800">

        <h3>Telugu Worship</h3>

      </div>

      <div class="card" onclick="playSong('songs/song2.mp3')">

        <img src="https://images.unsplash.com/photo-1504052434569-70ad5836ab65?q=80&w=800">

        <h3>Hindi Worship</h3>

      </div>

    </div>

  </div>

</div>

<!-- MUSIC PLAYER -->

<div class="player">

  <audio controls id="audio"></audio>

</div>

<script>

  // SHOW APP AFTER SPLASH

  setTimeout(() => {

    document.getElementById("app").style.display = "flex";

  }, 3000);

  // PLAY SONG

  const audio = document.getElementById("audio");

  function playSong(song){

    audio.src = song;

    audio.play();

  }

</script>

</body>
</html>
