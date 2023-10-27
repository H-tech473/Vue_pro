<template>
  <div class="d-flex flex-column contain">
  <div class="d-flex align-items-center py-2 bg-color justify-content-center">
    FREE SHIPING ON ALL ORDERS
  </div>
  <div class="container-fluid">
    <header class="d-flex flex-wrap align-items-center justify-content-around justify-content-md-between py-2">
      <div class="col-md-3 p-ms-3 mb-2 mb-md-0 text-start">
        <a href="/" class="logo d-inline-flex link-body-emphasis text-decoration-none link-dark">
          PISTONS
        </a>
      </div>

      <ul class="nav col-12 col-md-auto mb-2 justify-content-center hide">
        <li><a href="#" class="plain nav-link px-4 link-dark">NEW</a></li>
        <li><a href="#" class="plain nav-link px-4 link-dark">BRANDS</a></li>
        <li><a href="#" class="plain nav-link px-4 link-dark">COLLECTION</a></li>
        <li><a href="#" class="plain nav-link px-4 link-dark">ACCESSORIES</a></li>
        <li><a href="#" class="plain nav-link px-4 link-dark">ABOUT</a></li>
      </ul>

      <div class="col-md-3 text-end">
        <a href="#" class="px-3 mx-1 py-3 svg"><svg class="svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zM208 352a144 144 0 1 0 0-288 144 144 0 1 0 0 288z"/></svg></a>
        <a href="#" class="px-3 mx-1 py-3 svg"><svg class="svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><path d="M0 24C0 10.7 10.7 0 24 0H69.5c22 0 41.5 12.8 50.6 32h411c26.3 0 45.5 25 38.6 50.4l-41 152.3c-8.5 31.4-37 53.3-69.5 53.3H170.7l5.4 28.5c2.2 11.3 12.1 19.5 23.6 19.5H488c13.3 0 24 10.7 24 24s-10.7 24-24 24H199.7c-34.6 0-64.3-24.6-70.7-58.5L77.4 54.5c-.7-3.8-4-6.5-7.9-6.5H24C10.7 48 0 37.3 0 24zM128 464a48 48 0 1 1 96 0 48 48 0 1 1 -96 0zm336-48a48 48 0 1 1 0 96 48 48 0 1 1 0-96z"/></svg></a>
      </div>
    </header>
  </div>
  <div class="flex-grow-1 bg-secondary position-relative" style="overflow-y: auto;">
    <div class="picture position-absolute">
      <div class="pic1 w-50 h-100 d-inline-block"></div>
      <div class="pic2 w-50 h-100 d-inline-block"></div>
    </div>
    <div class="picture position-absolute" style="top:100%">h</div>
    <div class="picture position-absolute" style="top:200%">h</div>
    <div class="picture position-absolute" style="top:300%">h</div>
    <div class="picture position-absolute" style="top:400%">h</div>
  </div>
</div>
</template>

<script>
  import axios from 'axios';
  export default {
    data() {
      return {
        info: null
      }
    },
    mounted () {
      axios({
    method: 'get',
    url: 'http://localhost:5173/api/test-api/testimonials.json',
    withCredentials: true,
  })
        .then(response => (this.info = response.data.testimonials))
        .catch(err => console.log(err.message))
    }
  }
</script>

<style scoped>
  *{
    font-family: var(--plaint);
    font-weight: bold;
    font-size: .9rem;
    text-transform: capitalize;
  }
  a.plain:hover{
    text-decoration: underline;
  }
  a.logo{
    font-family: var(--logo);
    font-size: 2rem;
    text-transform: capitalize;
  }
  svg.svg{
    height: 30px;
    width: 30px;

  }
  a.svg:hover{
    background-color: #eee;
  }
  div.bg-color{
    background-color: #E3E3E3;
    color: #9A9A9A;
  }
  div.contain{
    min-height: 100vh;
    min-width: 100vw;
  }

  ul.hide{
    pointer-events: all;
  }

  div.picture{
    height: 100%;
    width: 100%;
  }

  @media (max-width: 480px) {
    ul.hide{
      display: none;
      pointer-events: none;
    }
  }

  @media (max-width: 768px) {
    ul.hide{
      display: none;
      pointer-events: none;
    }
  }

</style>
