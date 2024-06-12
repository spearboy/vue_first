<template>
  <section id="intro">
    <div class="intro__inner">
      <h2 class="intro__title">port developer</h2>
      <div class="intro__lines" aria-hidden="true">
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
      </div>
      <div class="intro__text">
        <div class="text">
          <div>talent is</div>
          <div>found at the end of the</div>
          <div>effort</div>
        </div>
        <div class="img">
          <img src="https://images.unsplash.com/photo-1717533564570-4ea91a5df160?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="" />
        </div>
      </div>
      <div class="intro__lines bottom" aria-hidden="true">
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@keyframes animation {
  to {
    width: 100%;
  }
}
#intro {
  height: 100vh;
  .intro__inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 16px;

    .intro__title {
      font-size: 10vw;
      line-height: 1;
      font-weight: 800;
      white-space: nowrap;
      text-transform: uppercase;
      letter-spacing: -0.3vw;
    }
    .intro__lines {
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-end;
      gap: 10px;
      margin-bottom: 10px;
      .line {
        width: 100%;
        background-color: var(--black);
        animation: animation linear;
        animation-timeline: scroll(y);
        &:nth-child(1) {
          width: 10%;
          height: 1px;
        }
        &:nth-child(2) {
          width: 20%;
          height: 3px;
        }
        &:nth-child(3) {
          width: 30%;
          height: 5px;
        }
        &:nth-child(4) {
          width: 40%;
          height: 8px;
        }
        &:nth-child(5) {
          width: 56%;
          height: 12px;
        }
        &:nth-child(6) {
          width: 72%;
          height: 17px;
        }
        &:nth-child(7) {
          width: 89%;
          height: 20px;
        }
      }
      &.bottom {
        display: none;
        @media (max-width: 800px) {
          display: flex;
          margin-top: 10px;
          margin-bottom: 0px;
          flex-direction: column-reverse;
        }
      }
    }
    .intro__text {
      width: 100%;
      height: 40vh;
      background-color: var(--black);
      color: var(--white);
      align-items: center;
      justify-content: center;
      flex-direction: column;
      display: flex;
      position: relative;
      .text {
        font-size: 3vw;
        line-height: 1;
        font-weight: 900;
        text-transform: uppercase;
        text-decoration: underline;
        text-align: center;
        position: relative;
        z-index: 100;
        transition: all 0.3s ease;
        cursor: all-scroll;
      }
      .img {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 200px;
        height: 200px;
        object-fit: cover;
        border-radius: 100%;
        overflow: hidden;
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
  }
}
</style>
