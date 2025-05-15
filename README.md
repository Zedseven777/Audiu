<script>
  const audio = document.getElementById('typeSound');
  function playSound() {
    audio.currentTime = 0;
    audio.play().catch(err => {
      console.log("Som bloqueado até interação do usuário.");
    });
  }

  const bgMusic = document.getElementById('bgMusic');
  const musicBtn = document.getElementById('musicBtn');

  function toggleMusic() {
    if (bgMusic.paused) {
      bgMusic.play().then(() => {
        musicBtn.textContent = '🔈';
      }).catch((err) => {
        console.error("Erro ao tocar música:", err);
        alert("Clique novamente para ativar o som.");
      });
    } else {
      bgMusic.pause();
      musicBtn.textContent = '🔊';
    }
  }

  // DICA EXTRA: Permitir tocar som com qualquer clique inicial no body
  document.body.addEventListener('click', () => {
    bgMusic.play().catch(() => {});
  }, { once: true });
</script>



