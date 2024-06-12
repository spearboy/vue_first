<script setup>
import { skillText } from '@/constants';
</script>
<template>
  <section id="skill">
    <div class="skill__inner">
      <div class="skill__title">
        <h2>Challenge <em>나의 도전</em></h2>
      </div>
      <div class="skill__desc">
        <div v-for="(text, index, key) in skillText" :key="key">
          <span>{{ index + 1 }}.</span>

          <h3>{{ text.title }}</h3>
          <p>{{ text.description }}</p>
        </div>
        <!-- <div>
          <span>1.</span>
          <h3>끊임없는 자기계발</h3>
          <p>
            나 자신을 끊임없이 발전시키는 것은 내가 중요하게 생각하는 가치입니다. 새로운 기술을 배우고, 다양한 경험을 쌓으며, 항상 성장하고자 하는 열정이 저를 움직이게 합니다. 이러한 열정은 저의
            경력과 개인적인 삶 모두에서 큰 동기부여가 됩니다. 어려움을 극복하고, 새로운 도전을 마주할 때마다 저는 한 단계 더 성장하고 있음을 느낍니다.
          </p>
        </div>
        <div>
          <span>2.</span>
          <h3>팀워크와 협력</h3>
          <p>
            성공적인 프로젝트는 팀의 협력 없이는 이루어질 수 없습니다. 저는 항상 팀원들과의 원활한 소통과 협력을 위해 노력하며, 서로의 강점을 살려 최고의 결과를 도출하고자 합니다. 서로의 의견을
            존중하고, 문제를 함께 해결해 나가는 과정에서 우리는 더욱 강한 팀이 됩니다. 이는 제가 일을 대하는 데 있어 가장 중요한 원칙 중 하나입니다.
          </p>
        </div>
        <div>
          <span>3.</span>
          <h3>혁신과 창의성</h3>
          <p>
            변화와 혁신을 두려워하지 않는 자세는 오늘날의 빠르게 변하는 환경에서 매우 중요합니다. 저는 항상 새로운 아이디어를 탐구하고, 창의적인 해결책을 찾기 위해 노력합니다. 창의성은 단지 예술적인
            영역에만 국한되지 않으며, 일상적인 문제 해결에서도 큰 역할을 합니다. 이러한 자세가 저를 차별화시키고, 더욱 가치 있는 결과를 창출하게 합니다.
          </p>
        </div>
        <div>
          <span>4.</span>
          <h3>책임감과 성실함</h3>
          <p>
            모든 일에 있어 책임감을 가지고 성실하게 임하는 것은 저의 신념입니다. 맡은 일에 최선을 다하고, 결과에 대해 책임을 지는 자세는 신뢰를 쌓는 데 중요합니다. 저는 항상 주어진 일을 완수하기 위해
            필요한 모든 노력을 기울이며, 이러한 태도는 저를 더욱 신뢰받는 사람으로 만들어줍니다.
          </p>
        </div>
        <div>
          <span>5.</span>
          <h3>긍정적인 마인드</h3>
          <p>
            어떤 상황에서도 긍정적인 마인드를 유지하는 것은 매우 중요합니다. 어려운 상황에서도 긍정적으로 생각하고, 문제를 해결할 수 있는 방법을 찾으려는 태도는 많은 어려움을 극복하게 해줍니다.
            긍정적인 마인드는 저뿐만 아니라 주변 사람들에게도 좋은 영향을 미치며, 함께하는 모든 이들에게 희망과 용기를 줍니다.
          </p>
        </div> -->
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
#skill {
  min-height: 100vh;
}
.skill__inner {
  padding: 16px;
  display: flex;
  justify-content: space-between;
  @media (max-width: 800px) {
    flex-direction: column;
  }
  .skill__title {
    position: sticky;
    top: 100px;
    left: 0px;
    width: 48%;
    height: 5vw;
    @media (max-width: 800px) {
      width: 100%;
      background-color: var(--mainBg-color);
      top: 68px;
      height: fit-content;
      margin-bottom: 60px;
    }
    h2 {
      font-size: 4vw;
      font-weight: 900;
      line-height: 0.7;
      text-transform: uppercase;
      color: var(--black100);
      font-family: var(--mainKor-font);
      border-bottom: 0.4vw solid var(--black100);
      @media (max-width: 800px) {
        padding: 10px 0px;
        line-height: 1;
      }
      em {
        font-size: 1.25rem;
        font-weight: 400;
        line-height: 1.1;
      }
    }
  }
  .skill__desc {
    width: 50%;
    @media (max-width: 800px) {
      width: 100%;
    }
    span {
      font-size: 5vw;
      line-height: 1.3;
      font-weight: 900;
      font-family: var(--mainNum-font);
    }

    h3 {
      font-size: 1.5rem;
      text-decoration: underline;
      text-underline-position: under;
      margin-bottom: 1vw;
    }

    p {
      margin-bottom: 30vh;
      font-size: 1.1rem;
      color: var(--black300);
      line-height: 1.7;
    }
  }
}
</style>
