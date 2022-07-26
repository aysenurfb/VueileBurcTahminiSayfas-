<template>
  <div>
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
    <!-- burc tahmini ve kartlarından sonraki container -->
    <div class="container">
      <div class="row">
        <div class="col">
          <div class="card mt-2" style="width: 18rem;">
            <img src="https://picsum.photos/286/286" class="card-img-top" alt="">
            <div class="card-body">
              <h4>Neden Burcunuz.com</h4>
              <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto fuga sunt, eaque placeat fugit, officia harum voluptatem quidem hic ipsum provident blanditiis sint quis voluptate enim illum! Ratione, architecto autem.</p>
            </div>
          </div>
        </div>
         <div class="col">
          <div class="card mt-2" style="width: 18rem;">
            <img src="https://picsum.photos/286/286" class="card-img-top" alt="">
            <div class="card-body">
              <h4>Hesaplayın </h4>
              <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis, eaque ipsum accusamus, ab tempora odio necessitatibus quod saepe ut magnam itaque commodi consequuntur deleniti quas vel fuga! Aliquid, obcaecati sequi.</p>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="card mt-2" style="width: 18rem;">
            <img src="https://picsum.photos/286/286" class="card-img-top" alt="">
            <div class="card-body">
              <h4>Özellikleri Keşfedin </h4>
              <p class="card-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis, eaque ipsum accusamus, ab tempora odio necessitatibus quod saepe ut magnam itaque commodi consequuntur deleniti quas vel fuga! Aliquid, obcaecati sequi.</p>
            </div>
          </div>
        </div>
      </div>
    </div>

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
  </div>
</template>
