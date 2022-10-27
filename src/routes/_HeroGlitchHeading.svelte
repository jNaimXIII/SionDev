<h1 class="site-heading glitch">
  <span>siondev ag</span>
  siondev ag
  <span>siondev ag</span>
</h1>

<style lang="scss">
  .site-heading {
    flex: 1;
    font-size: 108px;
    position: relative;
    text-transform: uppercase;

    @media (max-width: 968px) {
      font-size: 96px;
    }

    @media (max-width: 592px) {
      font-size: 66px;
    }

    @media (max-width: 480px) {
      font-size: 56px;
    }

    &::before {
      content: "";
      position: absolute;
      width: 847px;
      height: 675px;
      top: 50%;
      transform: translate(-60%, -50%);

      background: radial-gradient(50% 50% at 50% 50%, rgba(116, 0, 140, 0.5) 0%, rgba(116, 0, 140, 0) 100%);

      @media (max-width: 768px) {
        width: 500px;
      }

      z-index: -1;
    }
  }

  .glitch {
    text-shadow: 0.05em 0 0 #00fffc, -0.03em -0.04em 0 #fc00ff, 0.025em 0.04em 0 #fffc00;
    animation: glitch 2s infinite;
  }

  .glitch span {
    position: absolute;
    top: 0;
    left: 0;
  }

  .glitch span:first-child {
    animation: glitch 1.6s infinite;
    clip-path: polygon(0 0, 100% 0, 100% 35%, 0 35%);
    transform: translate(-0.04em, -0.03em);
    opacity: 0.75;
  }

  .glitch span:last-child {
    animation: glitch 1.8s infinite;
    clip-path: polygon(0 65%, 100% 65%, 100% 100%, 0 100%);
    transform: translate(0.04em, 0.03em);
    opacity: 0.75;
  }

  @keyframes glitch {
    0% {
      text-shadow: 0.05em 0 0 #00fffc, -0.03em -0.04em 0 #fc00ff, 0.025em 0.04em 0 #fffc00;
    }
    15% {
      text-shadow: 0.05em 0 0 #00fffc, -0.03em -0.04em 0 #fc00ff, 0.025em 0.04em 0 #fffc00;
    }
    16% {
      text-shadow: -0.05em -0.025em 0 #00fffc, 0.025em 0.035em 0 #fc00ff, -0.05em -0.05em 0 #fffc00;
    }
    49% {
      text-shadow: -0.05em -0.025em 0 #00fffc, 0.025em 0.035em 0 #fc00ff, -0.05em -0.05em 0 #fffc00;
    }
    50% {
      text-shadow: 0.05em 0.035em 0 #00fffc, 0.03em 0 0 #fc00ff, 0 -0.04em 0 #fffc00;
    }
    99% {
      text-shadow: 0.05em 0.035em 0 #00fffc, 0.03em 0 0 #fc00ff, 0 -0.04em 0 #fffc00;
    }
    100% {
      text-shadow: -0.05em 0 0 #00fffc, -0.025em -0.04em 0 #fc00ff, -0.04em -0.025em 0 #fffc00;
    }
  }
</style>
