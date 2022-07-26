<template>
  <div>
    <!-- nav baslangıc -->
           <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
              <a class="navbar-brand">Burcunuz</a>
              <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
              </button>
              <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ml-auto" >
                  <li class="nav-item active">
                    <router-link to="/" class="nav-link">Ana Sayfa <span class="sr-only">(current)</span></router-link>
                  </li>
                  <li class="nav-item">
                    <router-link to="/About" class="nav-link">Hakkımızda</router-link>
                  </li>
                </ul>
              </div>
            </nav>
            <router-view/>
      <!-- nav bitis -->

      <!-- container kısmı -->
      <div class="container">
       <div class="row">
         <div class="col">
           <!-- form burc tahmini kısmı -->
          <div>
                <div class="card mt-2">
                  <div class="card-header">
                    <strong>BURÇ HESAPLAMA</strong>
                  </div>
                  <div class="card-body">
                    <div class="input-group mb-3">
                      <div class="input-group-prepend">
                        <label class="input-group-text" for="inputGroupSelect01">Ay</label>
                      </div>
                      <select class="custom-select" id="inputGroupSelect01" v-model="ay">
                        <option value="Ocak">Ocak</option>
                        <option value="Subat">Subat</option>
                        <option value="Mart">Mart</option>
                        <option value="Nisan">Nisan</option>
                        <option value="Mayis">Mayis</option>
                        <option value="Haziran">Haziran</option>
                        <option value="Temmuz">Temmuz</option>
                        <option value="Agustos">Agustos</option>
                        <option value="Eylul">Eylul</option>
                        <option value="Ekim">Ekim</option>
                        <option value="Kasim">Kasim</option>
                        <option value="Aralik">Aralik</option>
                      </select>
                    </div>
                    <div class="input-group mb-3">
                      <div class="input-group-prepend">
                        <label class="input-group-text" for="inputGroupSelect01">Gün</label>
                      </div>
                      <select class="custom-select" id="inputGroupSelect01" v-model="gun">
                        <option value="1">1</option>
                        <option value="2">2</option>
                        <option value="3">3</option>
                        <option value="4">4</option>
                        <option value="5">5</option>
                        <option value="6">6</option>
                        <option value="7">7</option>
                        <option value="8">8</option>
                        <option value="9">9</option>
                        <option value="10">10</option>
                        <option value="11">11</option>
                        <option value="12">12</option>
                        <option value="13">13</option>
                        <option value="14">14</option>
                        <option value="15">15</option>
                        <option value="16">16</option>
                        <option value="17">17</option>
                        <option value="18">18</option>
                        <option value="19">19</option>
                        <option value="20">20</option>
                        <option value="21">21</option>
                        <option value="22">22</option>
                        <option value="23">23</option>
                        <option value="24">24</option>
                        <option value="25">25</option>
                        <option value="26">26</option>
                        <option value="27">27</option>
                        <option value="28">28</option>
                        <option value="29">29</option>
                        <option value="30">30</option>
                        <option value="31">31</option>
                      </select>
                    </div>
                    <!-- butonlar başlangıc -->
                    <div class="container">
                      <div class="row">
                        <div class="col">
                          <button type="button" class="buttontype but btn btn-outline-dark btn-sm" v-on:click="burcHesapla()">BURC HESAPLA</button>
                        </div>
                        <div class="col">
                          <button type="button" class="buttontype btn btn-outline-dark btn-sm" v-on:click="sifirla()">SIFIRLA</button>
                        </div>
                      </div>
                    </div><!-- butonlar bitis-->
                  </div>
                  <!-- card footer-->
                  <div class="card-footer">
                    Burcunuz :<strong>{{burc}}</strong>
                  </div>
                </div>
                
            </div>
            <!-- burc tahmini bitis divi ustte-->

          <!-- kartlar -->
          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="oglakCard">
                <div class="row no-gutters">
                  <div class="col-md-4">
                    <img src="https://listelist.com/wp-content/uploads/2018/07/o%C4%9Flak-2.png" class="card-img mt-2" alt="">
                  </div>
                  <div class="col-md-8">
                    <div class="card-body">
                      <h5 class="card-title">Oğlak Burcu</h5>
                      <p class="card-text">
                        <ul>
                          <li><strong>Grup:</strong> Toprak</li>
                          <li><strong>Yönetici Gezegen:</strong> Satürn</li>
                          <li><strong>Karşıt Burç:</strong> Yengeç</li>
                          <li><strong>Şanslı Sayı: </strong> 8</li>
                        </ul>
                      </p>
                    </div>
                  </div>
                </div>
              </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="kovaCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://hthayat.haberturk.com/im/2020/02/15/1073250_0d1f4da5b883ff3b57a56cfe28d2b719.jpg" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Kova Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Hava</li>
                        <li><strong>Yönetici Gezegen:</strong> Satürn, Uranüs</li>
                        <li><strong>Karşıt Burç:</strong> Aslan</li>
                        <li><strong>Şanslı Sayı: </strong> 4</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="balikCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="http://www.rituelmedyumhoca.com/trex/assets/img/urunler/3188427210.jpg" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Balık Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Su</li>
                        <li><strong>Yönetici Gezegen:</strong> Jüpiter, Neptün</li>
                        <li><strong>Karşıt Burç:</strong> Başak</li>
                        <li><strong>Şanslı Sayı: </strong> 3</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="kocCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQnRBDqgLQchVo-HH75GWMP_WpmwER2rpTwd6LUXMLI-MX-QKalowEz_MLx4qBRaaSQbk0&usqp=CAU" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Koç Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Ateş</li>
                        <li><strong>Yönetici Gezegen:</strong> Mars</li>
                        <li><strong>Karşıt Burç:</strong> Terazi</li>
                        <li><strong>Şanslı Sayı: </strong> 9</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="bogaCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://pbs.twimg.com/profile_images/3674023490/6718a7ad3747c18cda8051261675ee9f_400x400.jpeg" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Boğa Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Toprak</li>
                        <li><strong>Yönetici Gezegen:</strong> Venüs</li>
                        <li><strong>Karşıt Burç:</strong> Akrep</li>
                        <li><strong>Şanslı Sayı: </strong> 6</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>
          
          <transition name="cardAnimation">
          <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="ikizlerCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSfzo5FMyJiyynowhXIl28CdghNLOiO30pk-IYQ3xY_JHEJonCPcuArUDevmJlQBeXdjeE&usqp=CAU" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">İkizler Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Hava</li>
                        <li><strong>Yönetici Gezegen:</strong> Merkür</li>
                        <li><strong>Karşıt Burç:</strong> Yay</li>
                        <li><strong>Şanslı Sayı: </strong> 5</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="yengecCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://hthayat.haberturk.com/im/2019/06/21/1071554_ca5154dd1a3ccabda68aac3216e846c1.jpg" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Yengec Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Su</li>
                        <li><strong>Yönetici Gezegen:</strong> Ay</li>
                        <li><strong>Karşıt Burç:</strong> Oğlak</li>
                        <li><strong>Şanslı Sayı: </strong> 2</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="aslanCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://www.dovmefiyatlari.gen.tr/wp-content/uploads/2013/11/aslan-burcu-sembol-dovmesi-01.jpg" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Aslan Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Ateş</li>
                        <li><strong>Yönetici Gezegen:</strong> Güneş</li>
                        <li><strong>Karşıt Burç:</strong> Kova</li>
                        <li><strong>Şanslı Sayı: </strong> 1-4</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="basakCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://media.istockphoto.com/vectors/virgo-vector-id1003195862?k=20&m=1003195862&s=170667a&w=0&h=74K-kqyEi8MaySEtvtK8qulcOStGh6Lo9avBeeIWp58=" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Başak Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Toprak</li>
                        <li><strong>Yönetici Gezegen:</strong> Merkür</li>
                        <li><strong>Karşıt Burç:</strong> Balık</li>
                        <li><strong>Şanslı Sayı: </strong> 5</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
          <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="teraziCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://static7.depositphotos.com/1245125/745/v/600/depositphotos_7452904-stock-illustration-justice-scales.jpg" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Terazi Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Hava</li>
                        <li><strong>Yönetici Gezegen:</strong> Venüs</li>
                        <li><strong>Karşıt Burç:</strong> Koç</li>
                        <li><strong>Şanslı Sayı: </strong> 6</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="akrepCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://st2.depositphotos.com/2527057/6297/v/600/depositphotos_62974549-stock-illustration-vector-sign-scorpion.jpg" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Akrep Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Ateş</li>
                        <li><strong>Yönetici Gezegen:</strong> Mars, Plüton</li>
                        <li><strong>Karşıt Burç:</strong> Boğa</li>
                        <li><strong>Şanslı Sayı: </strong> 9</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>

          <transition name="cardAnimation">
            <div class="card mb-3 container mt-2" style="max-width: 540px;" v-if="yayCard">
              <div class="row no-gutters">
                <div class="col-md-4">
                  <img src="https://png.vector.me/files/images/1/6/167670/zodiac_sagittarius_sign_clip_art.jpg" class="card-img mt-2" alt="">
                </div>
                <div class="col-md-8">
                  <div class="card-body">
                    <h5 class="card-title">Yay Burcu</h5>
                    <p class="card-text">
                      <ul>
                        <li><strong>Grup:</strong> Ateş</li>
                        <li><strong>Yönetici Gezegen:</strong> Jüpiter, Neptün</li>
                        <li><strong>Karşıt Burç:</strong> İkizler</li>
                        <li><strong>Şanslı Sayı: </strong> 3</li>
                      </ul>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </transition>
              </div>
            </div>
          </div>
    <!-- container kısmı bitiş -->

    <!-- burc tahmini ve kartlarından sonraki container -->
    <div class="container">
      <div class="row">
        <div class="col">
          <div class="card mt-2" style="width: 18rem;">
            <img src="https://graphicriver.img.customer.envatousercontent.com/files/308819348/preview.jpg?auto=compress%2Cformat&q=80&fit=crop&crop=top&max-h=8000&max-w=590&s=d7e61b6644a09670afb82bfc9c4258b3" class="card-img-top" alt="">
            <div class="card-body">
              <h4>Neden Burcunuz.com</h4>
              <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto fuga sunt, eaque placeat fugit, officia harum voluptatem quidem hic ipsum provident blanditiis sint quis voluptate enim illum! Ratione, architecto autem.</p>
            </div>
          </div>
        </div>
         <div class="col">
          <div class="card mt-2" style="width: 18rem;">
            <img src="https://static6.depositphotos.com/1008559/658/v/950/depositphotos_6585895-stock-illustration-zodiac-sign.jpg" class="card-img-top" alt="">
            <div class="card-body">
              <h4>Hesaplayın </h4>
              <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis, eaque ipsum accusamus, ab tempora odio necessitatibus quod saepe ut magnam itaque commodi consequuntur deleniti quas vel fuga! Aliquid, obcaecati sequi.</p>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="card mt-2" style="width: 18rem;">
            <img src="https://image.freepik.com/free-vector/vintage-thin-line-aries-zodiac-sign-label-retro-astrological-symbol-mystic-sacred-geometry-element-emblem-logo-stroke-outline-illustration-white-background_163463-514.jpg" class="card-img-top" alt="">
            <div class="card-body">
              <h4>Özellikleri Keşfedin </h4>
              <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis, eaque ipsum accusamus, ab tempora odio necessitatibus quod saepe ut magnam itaque commodi consequuntur deleniti quas vel fuga! Aliquid, obcaecati sequi.</p>
            </div>
          </div>
        </div>
      </div>
    </div><!-- burc tahmini ve kartlarından sonraki container -->

    <!-- Footer -->
    <footer class="bg-dark text-center text-white mt-5">
      <!-- Grid container -->
      <div class="container p-4">
        <!-- Section: Text -->
        <section class="mb-4">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt distinctio earum
            repellat quaerat voluptatibus placeat nam, commodi optio pariatur est quia magnam
            eum harum corrupti dicta, aliquam sequi voluptate quas.
          </p>
        </section>
        <!-- Section: Text -->
      </div>
      <!-- Grid container -->

      <!-- Copyright -->
      <div class="text-center p-3" style="background-color: rgba(0, 0, 0, 0.2);">
        © 2020 Copyright:
        <a class="text-white" href="https://mdbootstrap.com/">Burcunuz.com</a>
      </div>
      <!-- Copyright -->
    </footer>
    <!-- Footer -->

     <!--silmemen gereken div altta-->
  </div >
</template>

<script>
export default {
  data:function(){
    return{
      gun:"",
      ay:"",
      burc:"",
      oglakCard:false,
      kovaCard:false,
      balikCard:false,
      kocCard:false,
      bogaCard:false,
      ikizlerCard:false,
      yengecCard:false,
      aslanCard:false,
      basakCard:false,
      teraziCard:false,
      akrepCard:false,
      yayCard:false,
      showJS:false,
      elementWidth:100,
    }
  },
  props: {
    
  },
  methods:{
    burcHesapla:function(){
      console.log("aaaaaaaaa",this.gun,this.ay);//console log da degerleri alıp almadıgını gördük.
      if(!this.gun || !this.ay)//ozkan abi yandaki gibi yaptı.
      {
        alert("Gun ve Ay boş olamaz!!!");
      }
      else
      {
        if(this.ay=="Ocak")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Oğlak",this.oglakCard=!this.oglakCard;
          }
          else
          {
            return this.burc=" Kova",this.kovaCard=!this.kovaCard;
          }
        }
        else if(this.ay=="Subat")
        {
          if(this.gun >=1 && this.gun <=19)
          {
            return this.burc=" Kova",this.kovaCard=!this.kovaCard;
          }
          else
          {
            return this.burc=" Balık",this.balikCard=!this.balikCard;
          }
        }
        else if(this.ay=="Mart")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Balık",this.balikCard=!this.balikCard;
          }
          else
          {
            return this.burc=" Koc",this.kocCard=!this.kocCard;
          }
        }
        else if(this.ay=="Nisan")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Koc",this.kocCard=!this.kocCard;
          }
          else
          {
            return this.burc=" Boğa",this.bogaCard=!this.bogaCard;
          }
        }
        else if(this.ay=="Mayis")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Boğa",this.bogaCard=!this.bogaCard;
          }
          else
          {
            return this.burc=" İkizler",this.ikizlerCard=!this.ikizlerCard;
          }
        }
        else if(this.ay=="Haziran")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" İkizler",this.ikizlerCard=!this.ikizlerCard;
          }
          else
          {
            return this.burc=" Yengec",this.yengecCard=!this.yengecCard;
          }
        }
        else if(this.ay=="Temmuz")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Yengec",this.yengecCard=!this.yengecCard;
          }
          else
          {
            return this.burc=" Aslan",this.aslanCard=!this.aslanCard;
          }
        }
        else if(this.ay=="Agustos")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Aslan",this.aslanCard=!this.aslanCard;
          }
          else
          {
            return this.burc=" Basak",this.basakCard=!this.basakCard;
          }
        }
        else if(this.ay=="Eylul")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Basak",this.basakCard=!this.basakCard;
          }
          else
          {
            return this.burc=" Terazi",this.teraziCard=!this.teraziCard;
          }
        }
        else if(this.ay=="Ekim")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Terazi",this.teraziCard=!this.teraziCard;
          }
          else
          {
            return this.burc=" Akrep",this.akrepCard=!this.akrepCard;
          }
        }
        else if(this.ay=="Kasim")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Akrep",this.akrepCard=!this.akrepCard;
          }
          else
          {
            return this.burc=" Yay",this.yayCard=!this.yayCard;
          }
        }
        else if(this.ay=="Aralik")
        {
          if(this.gun >=1 && this.gun <=21)
          {
            return this.burc=" Yay",this.yayCard=!this.yayCard;
          }
          else
          {
            return this.burc=" Oğlak",this.oglakCard=!this.oglakCard;
          }
        }

      }
      
    },
    sifirla:function(){
      if(this.burc != "")
      {
        return this.kovaCard=false,this.oglakCard=false,this.balikCard=false,this.kocCard=false,this.bogaCard=false,this.ikizlerCard=false,this.yengecCard=false,this.aslanCard=false,this.basakCard=false,this.teraziCard=false,this.akrepCard=false,this.yayCard=false,this.gun="",this.ay="",this.burc="";
      }
      else
      {
        alert("Burç değeri boş iken sıfırla tuşuna basmayınız!!!");
      }
    },
    
  }
}
</script>

<style scoped>
/*.cardAnimation-enter{ //burası cartların ekranda yavaşça gözükmesini sağlar.
  opacity: 0;
}

.cardAnimation-enter-active{
  transition: opacity 1s;
}

.cardAnimation-leave{

}

.cardAnimation-leave-active{
  transition: opacity 1s;
  opacity: 0;
}*/

.cardAnimation-enter{
  opacity: 0;
}

.cardAnimation-enter-active{
  animation: slide-in 1s ease-out forwards;
  transition: opacity 1sn ;
}

.cardAnimation-leave{}

.cardAnimation-leave-active{
  animation: slide-out 1s ease-out forwards;
  transition: opacity 1s;
  opacity: 0;
}

@keyframes slide-in{
  from{
    transform: translateY(20px);
  }
  to{
    transform: translateY(0px);
  }
}

@keyframes slide-out{
  from{
    transform: translateY(0px);
  }
  to{
    transform: translateY(20px);
  }
}

.buttontype{
  width: 200px;
  height: 100px;
  background-color:rgb(103, 71, 190);
}
</style>

