<template>
  <nav
    class="flex items-center py-3 w-full bg-green-600 justify-between px-[24px]"
  >
    <div class="space-x-10 flex items-center">
      <div class="space-x-4">
        <button
          class="border-2 border-white hover:border-green-200 px-3 bg-white rounded-lg py-1 text-green-500 hover:bg-green-200"
        >
          {{ mudatliTolov }}
        </button>
        <button
          class="border-2 hover:border-green-200 px-3 rounded-lg py-1 bg-transparent text-white hover:text-green-200"
        >
          {{ chegirmalar }}
        </button>
        <button
          class="border-2 border-white hover:border-green-200 px-3 bg-white rounded-lg py-1 text-green-500 hover:bg-green-200"
        >
          {{ yutuqliOyinlar }}
        </button>
      </div>
    </div>
    <div class="flex items-center">
      <a
        class="text-2xl font-bold text-white hover:text-green-200"
        href="tel:+998712022021"
        aria-label="+998712022021"
      >
        +998 (71) 202 2021
      </a>
      <button
        class="border-2 border-white px-3 rounded-lg py-1 bg-transparent text-white hover:text-green-500 hover:bg-white mx-7"
      >
        {{ olchadaSoting }}
      </button>

      <div
        class="flex space-x-4 border-[1px] border-t-transparent border-b-transparent px-[24px] text-green-200"
      >
        <button @click="engLotin" class="hover:text-white focus:font-bold">
          Eng
        </button>
        <button @click="ozbekLotin" class="hover:text-white focus:font-bold">
          O'z
        </button>
        <button @click="krilrus" class="hover:text-white focus:font-bold">
          Pyc
        </button>
      </div>
    </div>
  </nav>
  <main class="flex px-10 py-10 items-center justify-between">
    <a href="#"
      ><img
        src="./assets/logo.png"
        alt="olma.uz"
        width="102"
        height="30"
    /></a>
    <div class="flex items-center space-x-10">
      <button
        class="border-2 rounded-lgatalog py-2 px-5 rounded-lg hover:text-green-600 hover:border-green-600 text-[20px] flex items-center gap-2"
      >
        <i class="bi bi-list text-[23px]"></i>{{ katalog }}
      </button>
      <div>
        <input
          type="text"
          placeholder="search"
          class="py-3 px-5 rounded-lg w-[590px] bg-slate-100 focus:bg-white"
        />
        <button
          class="px-5 py-2 border rounded-lg bg-green-600 text-white ms-[-66px]"
        >
          <img src="./assets/search.svg" alt=""
          width="30"
        height="30">
        </button>
      </div>
    </div>
    <div class="space-x-7 flex">
      <a
        @click="taqqoslashClick"
        href="#"
        class="hover:text-green-600 items-center flex"
        style="flex-direction: column"
      >
        <i class="bi bi-text-left text-[24px]"></i>
        <p class="text-[14px]">{{ taqqoslash }}</p>
      </a>
      <a
        @click="sevimlilarClick"
        href="#"
        class="hover:text-green-600 items-center flex"
        style="flex-direction: column"
      >
        <!-- <i class="bi bi-heart text-[24px]"></i> -->
        <img 
        src="./assets/heart.svg" 
        alt="heart"         
        width="30"
        height="30"
        class="box-green-200"
        >
      </a>
      <a
        @click="savatchaClick"
        href="#"
        class="hover:text-green-600 items-center flex"
        style="flex-direction: column"
      >
        <span
          class="w-[15px] h-[15px] bg-green-600 rounded-full flex justify-center items-center text-[12px] mb-[-18px] ms-[15px] text-white z-10"
          >0</span
        >
      <img 
      src="./assets/basket.svg" 
      alt="basket"
      width="30"
      height="33"
      class="svg-icon"
      >
      </a>
      <div
        v-if="akk"
        class="w-[370px] py-7 border bg-white rounded-lg right-[50px] top-[27%] shadow-lg flex justify-start px-7 items-center"
        style="position: absolute; flex-direction: column"
      >
        <div class="flex justify-end" style="width: 100%">
          <button @click="orqaga">
            <i class="bi bi-x-lg"></i>
          </button>
        </div>
        <h1 class="text-2xl mt-3 mb-3">
          {{ tizimgaKirishYokiProfilYaratish }}
        </h1>
        <label for="number" class="flex justify-start w-[100%]">{{
          telefonRaqam
        }}</label>
        <input
          id="number"
          type="number"
          placeholder="+998 (99) 999 9999"
          class="border rounded-lg py-2 px-3 w-[100%] mt-2"
          v-model="number"
        />
        <p class="text-green-500 text-[14px] mt-2" v-if="ogoh">
          {{ ogohlantiruvchi }}
        </p>
        <button
          @click="submib"
          class="border-green-400 border-2 rounded-lg w-[100%] py-2 text-[18px] mt-5 text-white hover:text-green-400 bg-green-400 hover:bg-white"
        >
          {{ tasdiqlash }}
        </button>
      </div>
      <a
        @click="akaunt"
        href="#"
        class="hover:text-green-600 items-center flex"
        style="flex-direction: column"
      >
      <img 
      src="./assets/user.svg" 
      alt=""        
      width="25"
      height="25"
      class="svg-icon"
      >
      
      </a>
    </div>
  </main>
  <div v-if="numberThero" class="h-[100px]">
    <h1 class="text-5xl font-bold">
      {{ yutuqliOyinlar2 }}
    </h1>
  </div>
  <div v-if="numberOne" class="h-[400px]">
    <h1 class="text-5xl font-bold">
      {{ tavarlarningSotilishi }}
    </h1>
  </div>
  <div v-if="numberTwo" class="h-[400px]">
    <h1 class="text-5xl font-bold">
      {{ sevimliMahsulotlar }}
    </h1>
    <div class="flex items-center mt-12" style="flex-direction: column">
      <img src="https://olcha.uz/_nuxt/empty-img.3a4aef3b.png" alt="mahsulot" />
      <h2 class="text-4xl mt-3">{{ SevimliMahsulotlarYoq }}</h2>
    </div>
  </div>
  <div
    v-if="numberThera"
    class="h-[400px] flex items-center justify-center"
    style="flex-direction: column"
  >
    <i class="bi bi-cart-check-fill text-5xl"></i>

    <h1 class="text-4xl mt-8">
      {{ savatchangizBosh }}
    </h1>

    <h2 class="text-1xl mt-3">{{ LekinSizUniHarDoimToldirishingizMumkin }}</h2>
    <button
      class="border-2 border-green-600 py-[10px] px-[17px] rounded-lg mt-10 bg-green-600 text-white hover:bg-white hover:text-green-600"
    >
      {{ asosiySahifa }}
    </button>
  </div>
  <div
    class="h-[297px] w-[100%] bg-neutral-100 mb-20 flex items-center justify-around"
  >
    <div class="w-[479px]">
      <h2 class="text-2xl font-bold">{{ bizningMobilIlova }}</h2>
      <div class="flex-wrap flex mt-5">
        <div
          class="m-2 ml-0 bg-green-500 w-[185px] h-[55px] flex items-center justify-center hover:bg-neutral-400 bg-white rounded-lg"
        >
          <a href="#">
            <img
              class="w-[150px] h-[50px]"
              src="https://olcha.uz/_nuxt/appstore.32a5f67a.svg"
              alt="olcha app story"
            />
          </a>
        </div>
        <div
          class="m-2 mr-0 bg-green-500 w-[185px] h-[55px] flex items-center justify-center hover:bg-neutral-400 bg-white rounded-lg"
        >
          <a href="#">
            <img
              class="w-[150px] h-[50px]"
              src="https://olcha.uz/_nuxt/googleplay.4ba35be8.svg"
              alt="olcha app story"
            />
          </a>
        </div>
      </div>
    </div>
    <div>
      <img
        src="./assets/main-img.jpg"
        alt="saasas"
        class="w-[489px] h-[264px]"
      />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      mudatliTolov: "0% Muddatli to'lov",
      chegirmalar: "Chegirmalar",
      yutuqliOyinlar: "Yutuqli o'yinlar",
      satyHaritasi: "Sayt xaritasi ",
      olchadaSoting: "Olma da soting",
      katalog: " Katalog",
      taqqoslash: "Taqqoslash",

      savatcha: "Savatcha",
      kirish: "Kirish",
      sevimliMahsulotlar: "Sevimli mahsulotlar",
      SevimliMahsulotlarYoq: "Sevimli mahsulotlar yo'q",
      tavarlarningSotilishi: "Tavarlarni solishtirish",
      savatchangizBosh: "Savatchangiz bo'sh",
      LekinSizUniHarDoimToldirishingizMumkin:
        "Lekin siz uni har doim to'ldirishingiz mumkin",
      asosiySahifa: "Asosiy sahifa",
      yutuqliOyinlar2: "Yutuqli o'yinlar",
      tizimgaKirishYokiProfilYaratish: "Tizimga kirish yoki profil",
      telefonRaqam: "Telefon raqam:",
      tasdiqlash: "Tasdiqlash",
      ogohlantiruvchi: "Telefon raqami maydoni majburiy, to'ldirishingiz lozim",
      numberOne: false,
      numberTwo: false,
      numberThera: false,
      numberThero: true,
      akk: false,
      ogoh: false,
      number: "",
      bizningMobilIlova:
        "Bizning mobil ilovamiz  App store va Google play-da",
    };
  },

  methods: {
    taqqoslashClick() {
      this.numberOne = true;
      this.numberTwo = false;
      this.numberThera = false;
      this.numberThero = false;
    },
    sevimlilarClick() {
      this.numberOne = false;
      this.numberTwo = true;
      this.numberThera = false;
      this.numberThero = false;
    },
    savatchaClick() {
      this.numberOne = false;
      this.numberTwo = false;
      this.numberThera = true;
      this.numberThero = false;
    },
    akaunt() {
      this.akk = true;
    },
    orqaga() {
      this.akk = false;
    },
    submib() {
      if (this.number === "") {
        this.ogoh = true;
      } else {
        this.ogoh = false;
        this.akk = false;
      }
    },
    ozbekLotin() {
      this.bizningMobilIlova =
        "Bizning mobil ilovamiz  App store va Google play-da";
      this.mudatliTolov = "0% Muddatli to'lov";
      this.chegirmalar = "Chegirmalar";
      this.yutuqliOyinlar = "Yutuqli o'yinlar";
      this.satyHaritasi = "Sayt xaritasi";
      this.olchadaSoting = "Olma da soting";
      this.katalog = " Katalog";
      this.taqqoslash = "Taqqoslash";
      this.sevimlilar = "Sevimlilar";
      this.savatcha = "Savatcha";
      this.kirish = "Kirish";
      this.sevimliMahsulotlar = "Sevimli mahsulotlar";
      this.SevimliMahsulotlarYoq = "Sevimli mahsulotlar yo'q";
      this.tavarlarningSotilishi = "Tavarlarni solishtirish";
      this.savatchangizBosh = "Savatchangiz bo'sh";
      this.LekinSizUniHarDoimToldirishingizMumkin =
        "Lekin siz uni har doim to'ldirishingiz mumkin";
      this.asosiySahifa = "Asosiy sahifa";
      this.yutuqliOyinlar2 = "Yutuqli o'yinlar";
      this.tizimgaKirishYokiProfilYaratish = "Tizimga kirish yoki profil";
      this.telefonRaqam = "Telefon raqam:";
      this.tasdiqlash = "Tasdiqlash";
      this.ogohlantiruvchi =
        "Telefon raqami maydoni majburiy, to'ldirishingiz lozim";
    },
    engLotin() {
      this.mudatliTolov = "0% Term payment";
      this.chegirmalar = "Discounts";
      this.yutuqliOyinlar = "Winning games";
      this.satyHaritasi = "Sitemap";
      this.olchadaSoting = "Sale in apples";
      this.katalog = "Catalogue";
      this.taqqoslash = "Compare";
      this.sevimliMahsulotlar = "Favorite products";
      this.SevimliMahsulotlarYoq = "No favorite products";
      this.tavarlarningSotilishi = "Comparison of tavars";
      this.savatchangizBosh = "Your basket is empty";
      this.LekinSizUniHarDoimToldirishingizMumkin =
        "But you can always fill it";
      this.asosiySahifa = "Main page";
      this.yutuqliOyinlar2 = "Winning games";
      this.tizimgaKirishYokiProfilYaratish = "Login or profile";
      this.telefonRaqam = "Phone number:";
      this.tasdiqlash = "Tasdiqlash";
      this.ogohlantiruvchi = "The area of the phone number is mandatory, you need to fill out";
      this.bizningMobilIlova =
        "Our mobile app is in the App store and Google play";
    },
    krilrus() {
      this.mudatliTolov = "0% Рассрочка";
      this.chegirmalar = "Скидки";
      this.yutuqliOyinlar = "Розыгрыши";
      this.yutuqliOyinlar2 = "Розыгрыши";
      this.satyHaritasi = "Карта сайта";
      this.olchadaSoting = "Продавайте на olma";
      this.katalog = " Каталог";
      this.taqqoslash = "Сравнение";
      this.sevimlilar = "Избранные";
      this.savatcha = "Корзина";
      this.kirish = "Войти";
      this.sevimliMahsulotlar = "Избранные товары";
      this.SevimliMahsulotlarYoq = "Нет избранных товаров";
      this.tavarlarningSotilishi = "Сравнение товаров";
      this.savatchangizBosh = "Корзина пуста";
      this.LekinSizUniHarDoimToldirishingizMumkin =
        "Но вы всегда можете ее наполнить";
      this.asosiySahifa = "На главную";
      this.tizimgaKirishYokiProfilYaratish = "Войти или создать профиль";
      this.telefonRaqam = "Номер телефона:";
      this.tasdiqlash = "Подтвердить";
      this.ogohlantiruvchi = "Поле номер телефона обязательно для заполнения";
      this.bizningMobilIlova =
        "Наше мобильное приложение доступно в  App store и Google play";
    },
  },
};
</script>

<style scoped>
</style>
