<script>
  export default {

  }
</script>

<template>
    <div class="container">
        <div class="citazione">
          <h1 class="citText">“La realtà e la fantasia spesso si confondono come un cocktail di cui non riesci a distinguere i sapori.”</h1>
          <h3 class="citAutore">Dario Argento</h3>
        </div>
        
        <h2 class="ourStory">La nostra storia</h2>

        <div class="container-fluid">
          <div class="row">
            <div class="col-4">
              <div class="storyColumn">
                <div class="storyYear">2000</div>

                <div class="d-flex align-items-center">
                  <div class="circle"></div>
                  <div class="line"></div>
                </div>

                <div class="storyTitle">La nascita</div>

                <div class="storyParagraph">“Lorem ipsum dolor sit amet consectetur. Nulla consectetur ut sed non turpis. Senectus commodo sed eu a et. Purus consequat morbi tellus mauris vel cursus nec faucibus.</div>
              </div>
            </div>

            <div class="col-4">
              <div class="storyColumn">
                <div class="storyYear">2000</div>

                <div class="d-flex align-items-center">
                  <div class="circle"></div>
                  <div class="line"></div>
                </div>

                <div class="storyTitle">La nascita</div>

                <div class="storyParagraph">“Lorem ipsum dolor sit amet consectetur. Nulla consectetur ut sed non turpis. Senectus commodo sed eu a et. Purus consequat morbi tellus mauris vel cursus nec faucibus.</div>
              </div>
            </div>

            <div class="col-4">
              <div class="storyColumn">
                <div class="storyYear">2000</div>

                <div class="d-flex align-items-center">
                  <div class="circle"></div>
                  <div class="line"></div>
                </div>

                <div class="storyTitle">La nascita</div>

                <div class="storyParagraph">“Lorem ipsum dolor sit amet consectetur. Nulla consectetur ut sed non turpis. Senectus commodo sed eu a et. Purus consequat morbi tellus mauris vel cursus nec faucibus.</div>
              </div>
            </div>
          </div>
        </div>

        

    </div>
</template>

<style>
.col-4{
  padding: 0;
  margin: 0;
}

.citazione{
  margin-top: 80px;
}

.citText{
  font-family: 'Playfair Display', serif;
  font-weight: 400;
  font-style: italic;
  color: white;
  font-size: 62px;
}

.citAutore{
  font-family: 'Karla', serif;
  color: white;
  font-size: 16px;
  margin-top: 24px;
}

.circle{
  height: 7px;
  width: 7px;
  border-radius: 50%;
  background-color: white;
}

.line {
  width: 100%;
  height: 1px;
  border-top: 1px solid white;
}

.storyYear{
  font-family: 'Karla', serif;
  font-weight: 300;
  color: #D1B875;
  font-size: 72px;
  letter-spacing: -3.6px;
  margin-bottom: 16px;
}

.ourStory{
  font-family: 'Playfair Display', serif;
  font-weight: 400;
  color: white;
  font-size: 40px;
  letter-spacing: -0.4px;
  margin-bottom: 16px;
  margin-top: 60px;
}

.storyTitle{
  font-family: 'Karla', serif;
  font-weight: 500;
  color: white;
  font-size: 20px;
  margin-top: 24px;
}

.storyParagraph{
  font-family: 'Karla', serif;
  font-weight: 300;
  color: white;
  font-size: 16px;
  margin-top: 16px;
  padding-right: 16px;
}

body{
  background-image: url("/imageBar2.png");
  object-fit: cover;
}

</style>