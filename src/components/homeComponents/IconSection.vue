<template>
  <div class="icon-section">
      <div class="container">
          <div class="cards">
              <div class="card">
                  <div class="card-img">
                      <img src="../../assets/icon-1-icon-section.png" alt="">
                  </div>

                  <div class="card-content">
                      <h3>STRONG SECURITY</h3>
                      <p>Protection against DDoS attacks,
                        full data encryption, compliant 
                        with PCI DSS standards</p>
                  </div>
              </div>
              <div class="card">
                  <div class="card-img">
                      <img src="../../assets/icon-2-icon-section.png" alt="">
                  </div>

                  <div class="card-content">
                      <h3>PAYMENT OPTIONS</h3>
                   <p>Most popular methods: 
                        Visa, MasterCard, bank transfer
                        (SWIFT, SEPA), cryptocurrency</p>
                  </div>
              </div>
              <div class="card">
                  <div class="card-img">
                      <img src="../../assets/icon-3-icon-section.png" alt="">
                  </div>

                  <div class="card-content">
                      <h3>WORLD COVERAGE</h3>
                      <p>Providing services in 99% 
                            countries around the globe,
                            including 24 states of USA</p>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "IconSection",
}
</script>

<style scoped>

.container {
    width: auto;
    margin: 0 200px;
    
}

.cards {
    display: flex;
    justify-content: space-between;
    text-align: center;
    align-items: center;
    flex-wrap: wrap;
    height: 340px;
}

@media (max-width: 1419px){
    .cards {
        height: auto;
        padding: 50px 0;
        justify-content: center;

    }

    .card {
        margin: 20px 0;
    }
}

.card {
    width: 340px;
    
}

.card-img {
    margin-bottom: 15px;
}

.card-content h3 {
    margin: 5px 0;
}
.card-content p {
    margin: 0 auto;
    width: 270px;
}

@media (max-width: 1079px) {
    .card {
        display: flex;
        text-align: left;

    }

    .card img {
        margin-right: 20px;
    }

    .cards {
        justify-content: center;
    }
}

</style>