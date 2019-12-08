<template>
  <div class="how-to-join">
      <div class="how-to-join-header">
          <h3>how to join</h3>
      </div>

      <div class="how-to-join-img">
          <img class="how-to-join-img-desktop" src="../../assets/how-to-join.png" alt="">
          <img class="how-to-join-mobile-img" src="../../assets/how-to-join-mobile.png" alt="">

      </div>
  </div>
</template>

<script>
export default {
    name: 'HowToJoin',
}
</script>

<style>

.how-to-join-mobile-img {
    display: none;
}


    .how-to-join {
        height: auto;
        padding: 50px;
    
    }

    .how-to-join-header {
        text-align: center;
        font-size: 53px;
        
        text-transform: uppercase;
    }

    .how-to-join-header h3 {
        font-weight: lighter;
    }

    .how-to-join-img {
        margin: 0 auto;
        text-align: center;
    }

    @media (max-width: 1400px) {
        .how-to-join-img img {
            width: 1000px;
        }
    }
    @media (max-width: 1100px) {
        .how-to-join-img img {
            width: 800px;
        }
    }
    @media (max-width: 900px) {
        .how-to-join-img img {
            width: 600px;
        }
    }
    @media (max-width: 620px) {
        .how-to-join-mobile-img {
            display: block;
        }

        .how-to-join-img img {
            width: 280px;
            margin: 0 auto;
        }

        

        .how-to-join-img-desktop {
            display: none;
        }
    }
</style>