<template>
  <div class="home">
    <div class="cont">
      <div class="input">
        <label>Введите радиус звезды</label>
        <input v-model="R">
      </div>  
      <div class="input">
        <label>Введите температуру звезды</label>
        <input v-model="T">
      </div>  
    </div>
    <div class="output">
      <div v-if="this.T">Температура {{this.T}} Кельвинов</div>
      <div v-if="this.R">Радиус {{this.R}} радиусов Солнца</div>
      <button class="compute" @click="this.star">Рассчитай это дерьмо полностью</button>
    </div>
    


    <table style="width: 100%; background: #315347;" v-if="this.classA || this.classB || this.classF || this.classG || this.classK || this.classM">
      <tbody>
        <tr>
          <td style="background: #101915; text-align: center;">
            <b>Класс</b>
          </td>
          <td style="background: #101915; text-align: center;">
            <b>Изображение</b>
          </td>
          <td style="background: #101915; text-align: center;">
            <b>Описание</b>
          </td>
        </tr>
        <tr  v-if="this.classB">
          <td style="background: #1f2d26; text-align: center;">
            <b>B</b>
          </td>
          <td style="background: #101915;">
            <a
              href="https://vignette.wikia.nocookie.net/stellaris/images/8/82/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_B.png/revision/latest?cb=20161119152647&amp;path-prefix=ru"
              class="image image-thumbnail"
            >
              <img
                src="https://vignette.wikia.nocookie.net/stellaris/images/8/82/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_B.png/revision/latest/scale-to-width-down/100?cb=20161119152647&amp;path-prefix=ru"
                alt="Звезда класса B"
                class
                data-image-key="%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_B.png"
                data-image-name="Звезда класса B.png"
                width="100"
                height="100"
              >
            </a>
          </td>
          <td style="background: #1f2d26;">
            <div
              style="margin: 5px;"
            >Крупные звёзды главной последовательности, относящиеся к спектральному классу B, излучают яркий голубой свет. Они нечасто встречаются, но светят так ярко, что их легко увидеть невооруженным глазом.</div>
          <div
              style="margin: 5px;"
            >{{this.text}}</div>
          </td>
        </tr>
        <tr  v-if="this.classA">
          <td style="background: #1f2d26; text-align: center;">
            <b>A</b>
          </td>
          <td style="background: #101915;">
            <a
              href="https://vignette.wikia.nocookie.net/stellaris/images/1/1c/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_A.png/revision/latest?cb=20161119152828&amp;path-prefix=ru"
              class="image image-thumbnail"
            >
              <img
                src="https://vignette.wikia.nocookie.net/stellaris/images/1/1c/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_A.png/revision/latest/scale-to-width-down/100?cb=20161119152828&amp;path-prefix=ru"
                alt="Звезда класса A"
                class
                data-image-key="%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_A.png"
                data-image-name="Звезда класса A.png"
                width="100"
                height="100"
              >
            </a>
          </td>
          <td style="background: #1f2d26;">
            <div
              style="margin: 5px;"
            >Эти сравнительно молодые звёзды главной последовательности, излучающие белый или бело-голубой цвет, проще всего увидеть невооруженным глазом. Они крупны и быстро вращаются, но со временем эволюционируют в более медленные и холодные красные гиганты.</div>
          <div
              style="margin: 5px;"
            >{{this.text}}</div>
          </td>
        </tr>
        <tr  v-if="this.classF">
          <td style="background: #1f2d26; text-align: center;">
            <b>F</b>
          </td>
          <td style="background: #101915;">
            <a
              href="https://vignette.wikia.nocookie.net/stellaris/images/f/fe/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_F.png/revision/latest?cb=20161119152929&amp;path-prefix=ru"
              class="image image-thumbnail"
            >
              <img
                src="https://vignette.wikia.nocookie.net/stellaris/images/f/fe/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_F.png/revision/latest/scale-to-width-down/100?cb=20161119152929&amp;path-prefix=ru"
                alt="Звезда класса F"
                class
                data-image-key="%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_F.png"
                data-image-name="Звезда класса F.png"
                width="100"
                height="100"
              >
            </a>
          </td>
          <td style="background: #1f2d26;">
            <div
              style="margin: 5px;"
            >Звёзды спектрального класса F достаточно велики по размерам, их часто называют жёлто-белыми карликами. Несмотря на то, что они испускают значительное количество УФ-излучения, им присущи широкие обитаемые зоны, где могут существовать пригодные для жизни миры.</div>
          <div
              style="margin: 5px;"
            >{{this.text}}</div>
          </td>
        </tr>
        <tr v-if="this.classG">
          <td style="background: #1f2d26; text-align: center;">
            <b>G</b>
          </td>
          <td style="background: #101915;">
            <a
              href="https://vignette.wikia.nocookie.net/stellaris/images/7/7b/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_G.png/revision/latest?cb=20161119153209&amp;path-prefix=ru"
              class="image image-thumbnail"
            >
              <img
                src="https://vignette.wikia.nocookie.net/stellaris/images/7/7b/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_G.png/revision/latest/scale-to-width-down/100?cb=20161119153209&amp;path-prefix=ru"
                alt="Звезда класса G"
                class="lzyPlcHld lzyTrns lzyLoaded"
                data-image-key="%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_G.png"
                data-image-name="Звезда класса G.png"
                data-src="https://vignette.wikia.nocookie.net/stellaris/images/7/7b/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_G.png/revision/latest/scale-to-width-down/100?cb=20161119153209&amp;path-prefix=ru"
                width="100"
                height="100"
                onload="if(typeof ImgLzy==='object'){ImgLzy.load(this)}"
              >
            </a>
          </td>
          <td style="background: #1f2d26;">
            <div
              style="margin: 5px;"
            >Звёзды класса G часто называют жёлтыми карликами, хотя на самом деле цвет их излучения варьируется от белого до желтоватого. Звёзды главной последовательности синтезируют водород примерно 10 млрд лет, прежде чем начнут расширяться, чтобы стать красными гигантами. Звезды класса G живут меньше, чем звезды класса K, зато миры в их обитаемых зонах подчас идеально подходят для возникновения жизни.</div>
          <div
              style="margin: 5px;"
            >{{this.text}}</div>
          </td>
        </tr>
        <tr v-if="this.classK">
          <td style="background: #1f2d26; text-align: center;">
            <b>K</b>
          </td>
          <td style="background: #101915;">
            <a
              href="https://vignette.wikia.nocookie.net/stellaris/images/3/34/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_K.png/revision/latest?cb=20161119153241&amp;path-prefix=ru"
              class="image image-thumbnail"
            >
              <img
                src="https://vignette.wikia.nocookie.net/stellaris/images/3/34/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_K.png/revision/latest/scale-to-width-down/100?cb=20161119153241&amp;path-prefix=ru"
                alt="Звезда класса K"
                class="lzyPlcHld lzyTrns lzyLoaded"
                data-image-key="%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_K.png"
                data-image-name="Звезда класса K.png"
                data-src="https://vignette.wikia.nocookie.net/stellaris/images/3/34/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_K.png/revision/latest/scale-to-width-down/100?cb=20161119153241&amp;path-prefix=ru"
                width="100"
                height="100"
                onload="if(typeof ImgLzy==='object'){ImgLzy.load(this)}"
              >
            </a>
          </td>
          <td style="background: #1f2d26;">
            <div
              style="margin: 5px;"
            >Эти звёзды главной последовательности, обычно именуемые оранжевыми карликами, встречаются часто. Их стабильный период последовательности составляет до 30 млрд лет, а значит, у планет, вращающихся вокруг звезды класса K, есть значительно больше времени для возникновения жизни.</div>
            <div
              style="margin: 5px;"
            >{{this.text}}</div>
          </td>
        </tr>
        <tr v-if="this.classM">
          <td style="background: #1f2d26;text-align: center;">
            <b>M</b>
          </td>
          <td style="background: #101915;">
            <a
              href="https://vignette.wikia.nocookie.net/stellaris/images/6/6a/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_M.png/revision/latest?cb=20161119153309&amp;path-prefix=ru"
              class="image image-thumbnail"
            >
              <img
                src="https://vignette.wikia.nocookie.net/stellaris/images/6/6a/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_M.png/revision/latest/scale-to-width-down/100?cb=20161119153309&amp;path-prefix=ru"
                alt="Звезда класса M"
                class="lzyPlcHld lzyTrns lzyLoaded"
                data-image-key="%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_M.png"
                data-image-name="Звезда класса M.png"
                data-src="https://vignette.wikia.nocookie.net/stellaris/images/6/6a/%D0%97%D0%B2%D0%B5%D0%B7%D0%B4%D0%B0_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0_M.png/revision/latest/scale-to-width-down/100?cb=20161119153309&amp;path-prefix=ru"
                width="100"
                height="100"
                onload="if(typeof ImgLzy==='object'){ImgLzy.load(this)}"
              >
            </a>
          </td>
          <td style="background: #1f2d26;">
            <div
              style="margin: 5px;"
            >Самый распространённый класс звёзд во вселенной, известный также как красные карлики. Невысокая светимость мешает рассмотреть их невооруженным глазом. Красные карлики живут очень долго, но почти не испускают УФ-лучи и поэтому не создают комфортных условий для возникновения большинства форм жизни.</div>
            <div
              style="margin: 5px;"
            >{{this.text}}</div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home",
  components: {
    HelloWorld
  },
  data () {
    return {
      R: '',
      T: '',
      L: '',
      text: '',
      classM: false,
      classA: false,
      classB: false,
      classK: false,
      classF: false,
      classG: false,
    }
  },
  methods: {
    star() {
      this.classM = false,
      this.classA = false
      this.classB = false
      this.classK = false
      this.classF = false
      this.classG = false
      this.L = 4*3.1415*this.R**(2)*5.67*10**(-8)*this.T**(4)
      if (this.T<2000) alert("Температура должна быть больше 2000 Кельвин")
      if (this.R<0.4) alert("Радиус должен быть больше 0.4 радиусов Солнца") 
      if ((this.T>=2000 && this.T<=3500) && (this.R>=0.4 && this.R <=0.9)) {
        this.classM = true
        this.text = "Звёзды этой температуры - красные. Cветимость заданной звезды при радиусе " + this.R + " солнечных и температуре " + this.T + " градусов Кельвина равна: " + this.L
      }
      if ((this.T>=2000 && this.T<=3500) && (this.R>0.9)) alert("Среди красных звёзд радиус должен быть меньше 0.9")
      if ((this.T>3500 && this.T<=5000) && (this.R>0.9 && this.R<=1.1)) {
        this.classK = true
        this.text = "Звёзды этой температуры - оранжевые. Cветимость заданной звезды при радиусе " + this.R + " солнечных и температуре " + this.T + " градусов Кельвина равна: " + this.L
      }
      if ((this.T>3500 && this.T<=5000) && (this.R<0.9  || this.R>1.1)) alert("Среди оранжевых звёзд радиус должен быть меньше 1.1 и больше 0.9")
      if ((this.T>5000 && this.T<=6000) && (this.R>1.1 && this.R<=1.3)) {
        this.classG = true
        this.text = "Звёзды этой температуры - жёлтые. Cветимость заданной звезды при радиусе " + this.R + " солнечных и температуре " + this.T + " градусов Кельвина равна: " + this.L
      }
      if ((this.T>5000 && this.T<=6000) && (this.R<1.1  || this.R>1.3)) alert("Среди жёлтых звёзд радиус должен быть меньше 1.3 и больше 1.1")
      if ((this.T>6000 && this.T<=7500) && (this.R>1.3 && this.R<=2.1)) {
        this.classF = true
        this.text = "Звёзды этой температуры - жёлто-белые.Cветимость заданной звезды при радиусе " + this.R + " солнечных и температуре " + this.T + " градусов Кельвина равна: " + this.L
      }
      if ((this.T>6000 && this.T<=7500) && (this.R<1.3  || this.R>2.1)) alert("Среди жёлто-белых звёзд радиус должен быть меньше 2.1 и больше 1.3")
      if ((this.T>7500 && this.T<=10000) && (this.R>2.1 && this.R<=7)) {
        this.classA = true
        this.text = "Звёзды этой температуры - белые. Светимость заданной звезды при радиусе " + this.R + " солнечных и температуре " + this.T + " градусов Кельвина равна: " + this.L
      }
      if ((this.T>7500 && this.T<=10000) && (this.R<2.1  || this.R>7)) alert("Среди белых звёзд радиус должен быть меньше 7 и больше 2.1")
      if ((this.T>10000 && this.T<=30000) && (this.R>7 && this.R<=15)) {
        this.classB = true
        this.text = "Звёзды этой температуры - бело-голубые. Cветимость заданной звезды при радиусе " + this.R + " солнечных и температуре " + this.T + " градусов Кельвина равна: " + this.L
      }
      if ((this.T>10000 && this.T<=30000) && (this.R<7  || this.R>15)) alert("Среди бело-голубых звёзд радиус должен быть меньше 15 и больше 7")
    }
  }
};
</script>

<style lang="sass">
.output
  margin-bottom: 120px;
  font-size: 24px;
  margin-top: 50px;
.input
  margin-bottom: 50px;
  font-size: 24px;
  margin-top: 50px;
  input
    margin-left: 20px

.compute
  background-attachment: scroll
  background-clip: border-box
  background-color: rgba(0, 0, 0, 0)
  background-image: none
  background-origin: padding-box
  background-position-x: 0%
  background-position-y: 0%
  background-size: auto
  border-bottom-color: rgb(196, 194, 194)
  border-bottom-left-radius: 3px
  border-bottom-right-radius: 3px
  border-bottom-style: solid
  border-bottom-width: 1px
  border-image-outset: 0px
  border-image-repeat: stretch
  border-image-slice: 100%
  border-image-source: none
  border-image-width: 1
  border-left-color: rgb(196, 194, 194)
  border-left-style: solid
  border-left-width: 1px
  border-right-color: rgb(196, 194, 194)
  border-right-style: solid
  border-right-width: 1px
  border-top-color: rgb(196, 194, 194)
  border-top-left-radius: 3px
  border-top-right-radius: 3px
  border-top-style: solid
  border-top-width: 1px
  box-sizing: content-box
  color: rgb(196, 194, 194)
  cursor: pointer
  display: flex
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif
  font-size: 12px
  font-style: normal
  font-weight: 600
  height: 18px
  justify-content: center
  letter-spacing: 0.15px
  line-height: 16px
  margin-bottom: 5px
  margin-left: 12px
  margin-right: 12px
  margin-top: 0px
  min-height: 18px
  outline-color: rgb(196, 194, 194)
  outline-style: none
  outline-width: 0px
  padding-bottom: 7px
  padding-left: 18px
  padding-right: 18px
  padding-top: 7px
  text-decoration-color: rgb(196, 194, 194)
  text-decoration-line: none
  text-decoration-style: solid
  text-transform: uppercase
  transition-duration: 0.3s
  transition-property: background-color, border-color, color
  vertical-align: top
  -webkit-appearance: none
  display: inline-block
  margin-top: 20px
</style>