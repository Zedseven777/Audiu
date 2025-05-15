function toggleMusic() {
  if (bgMusic.paused) {
    bgMusic.play().then(() => {
      musicBtn.textContent = '🔈';
    }).catch((err) => {
      console.error("Erro ao tocar música:", err);
      alert("Clique novamente para permitir o som.");
    });
  } else {
    bgMusic.pause();
    musicBtn.textContent = '🔊';
  }
}


