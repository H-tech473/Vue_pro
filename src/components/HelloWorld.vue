<script>
  import axios from 'axios';

  export default {
    data() {
      return {
        info: [{message:'',name: ''},{message:'',name: ''},{message:'',name: ''},{message:'',name: ''}]
      }
    },
    methods : {
 
 // Creating function
    show: function(){
      var element = document.querySelector("form");
      element.classList.toggle("d-none");
        }
    },
    mounted () {
      axios({
          method: 'get',
          url: 'http://127.0.0.1:5173/api/test-api/testimonials',
          withCredentials: true,
        })
        .then(response => (this.info = response.data.testimonials))
        .catch(err => console.log(err.message))
    }
  }
</script>

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
        <a href="#" class="px-3 mx-1 py-3 svg" @click="show()"><svg class="svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zM208 352a144 144 0 1 0 0-288 144 144 0 1 0 0 288z"/></svg></a>
        <a href="#" class="px-3 mx-1 py-3 svg"><svg class="svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><path d="M0 24C0 10.7 10.7 0 24 0H69.5c22 0 41.5 12.8 50.6 32h411c26.3 0 45.5 25 38.6 50.4l-41 152.3c-8.5 31.4-37 53.3-69.5 53.3H170.7l5.4 28.5c2.2 11.3 12.1 19.5 23.6 19.5H488c13.3 0 24 10.7 24 24s-10.7 24-24 24H199.7c-34.6 0-64.3-24.6-70.7-58.5L77.4 54.5c-.7-3.8-4-6.5-7.9-6.5H24C10.7 48 0 37.3 0 24zM128 464a48 48 0 1 1 96 0 48 48 0 1 1 -96 0zm336-48a48 48 0 1 1 0 96 48 48 0 1 1 0-96z"/></svg></a>
        <a href="#" class="px-3 mx-1 py-3 svg d-sm-inline d-md-none"><svg class="svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Pro 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg></a>
      </div>
    </header>
  </div>
  <div class="flex-grow-1 position-relative" style="overflow-y: auto; overflow-x: hidden;">
    <button type="button" class="position-fixed btn btn-light" style="z-index: 999; transform: rotateZ(-90deg) translateY(39%); top: 30%; right: 0%;">FEEDBACK</button>
    <form type="button" class="position-absolute d-none input-group p-3 bg-light" action="/" style="z-index: 999; width: 30%; right: 0%;top: 0%">
      <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-default" placeholder="Enter Text">
      <button type="button" class="btn btn-warning">Search</button>
    </form>
    <div class="picture position-absolute">
      <div class="pic1 w-50 h-100 d-inline-block position-absolute d-flex align-items-end justify-content-center">
        <div class="w-100 h-60 position-absolute d-flex align-items-center justify-content-center flex-column py-3">
          <div class="circular-text">MADE FOR YOU</div>
          <div class="logo mb-5">PRISTON</div>
        </div>
      </div>
      <div class="pic2 w-50 h-100 d-inline-block position-absolute d-flex align-items-end justify-content-center">
        <div class="w-100 h-60 position-absolute d-flex align-items-center justify-content-center flex-column py-3">
          <div class="linear-text text-center text-light fs-2 fw-normal mb-4">YOU WERE MADE TO<br>MAKE AN IMPACT.</div>
          <button type="button" class="btn btn-light mb-5 border-warning-subtle text-center border border-4 rounded-pill">SHOP PENS</button>
          </div>
      </div>
    </div>
    <div class="picture position-absolute" style="top:100%">
      <div class="pic3 w-50 h-100 d-inline-block position-relative float-start d-flex  align-items-end justify-content-center">
        <div class="w-100 h-60 position-absolute d-flex align-items-center justify-content-center flex-column py-3">
          <div class="linear-text text-center text-dark fs-2 fw-normal mb-4">MADE FOR THE BEST<br>CHANGE MAKERS.</div>
          <button type="button" class="btn btn-dark mb-5 text-center border border-4 border-dark rounded-pill px-2">SHOP BRANDS</button>
          </div>
      </div>
      <div class="pic4 w-50 h-100 d-inline-block position-relative float-end d-flex align-items-end justify-content-center"></div>
    </div>
    <div class="picture position-absolute" style="top:200%">
      <div class="pic5 w-50 h-100 d-inline-block position-relative float-start d-flex align-items-end justify-content-center"></div>
      <div class="pic6 w-50 h-100 d-inline-block float-end position-relative d-flex align-items-end justify-content-center">
        <div class="w-100 h-60 position-absolute d-flex align-items-center justify-content-center flex-column py-3">
          <div class="linear-text text-center text-light fs-2 fw-normal mb-4">SAVOUR THE PRESENT.</div>
          <button type="button" class="btn btn-light mb-5 border-warning-subtle text-center border border-4 rounded-pill">SHOP MONT BLANC</button>
          </div>
      </div>
    </div>
    <div class="picture position-absolute" style="top:300%">
      <div class="pic7 w-100 h-100 d-inline-block position-relative float-start d-flex align-items-center justify-content-center">
        <div class="w-100 h-60 position-absolute d-flex align-items-center justify-content-center flex-column py-3 gap-3">
          <div class="linear-text text-center text-light fs-2 fw-normal mb-4 --letter-space">WHERE QUALITY MEETS CLASS</div>
          <div class="circular-text">MADE FOR YOU</div>
          <div class="logo mb-5">PRISTON</div>
          <button type="button" class="btn btn-light mb-5 border-warning-subtle text-center border border-4 rounded-pill">SHOP THE FALL 2023 COLLECTION</button>
          </div>
      </div>
    </div>
    <div class="picture position-absolute d-flex justify-content-center align-items-center py-5" style="top:400%">
      <div class="container px-5 position-relative h-100 ">
      <div class="pics position-relative float-start position-relative">
        <div class="carousal d-flex position-absolute w-100 h-100">
          <img src="../assets/pic8.png" alt="" />
          <img src="../assets/pic9.png" alt="" />
          <img src="../assets/pic10.png" alt="" />
          <img src="../assets/pic11.png" alt="" />
          <img src="../assets/pic8.png" alt="" />
        </div>
      </div>
      <div class="text float-end">
        <div class="heading fs-1">ABOUT PISTONS </div>
        <div class="text1 fw-normal">Established in 1897, our beloved fountain pen haven, 'PISTONS,' has been a haven for pen enthusiasts for generations. With a century-long dedication to fine writing instruments, we've bridged tradition and modernity, offering a curated selection of vintage and contemporary fountain pens. Our little shop, nestled in the heart of town, continues to inspire a love for the art of writing, connecting past and present through the timeless elegance of ink on paper.</div>
      </div>
    </div>
    </div>
    <div class="picture position-absolute d-flex flex-column justify-content-evenly align-items-stretch" style="top:500%">
      <div class="Testimonyhead d-flex align-items-center justify-content-center text-capitalize" style="overflow: hidden;">TESTIMONIALS</div>
      <div class="Testimonies position-relative d-flex align-items-stretch flex-row justify-content-evenly position-relative bg-secondary px-4 py-5 gap-4">
          <div class="test1 position-relative bg-primary flex-grow-1">
            <div class="name position-absolute text-light text-wrap d-flex align-items-center h-100 w-100 justify-content-center text-center fs-2 fw-normal p-2">{{ info[0].name }}</div>
            <div class="info position-absolute text-light text-wrap d-flex align-items-center text-center fs-5 fw-normal p-2">{{ info[0].message }}</div>
          </div>
          <div class="test2 position-relative bg-primary flex-grow-1">
            <div class="name position-absolute text-light text-wrap d-flex align-items-center h-100 w-100 justify-content-center text-center fs-2 fw-normal p-2">{{ info[1].name }}</div>
            <div class="info position-absolute text-light text-wrap d-flex align-items-center text-center fs-5 fw-normal p-2">{{ info[1].message }}</div>
          </div>
          <div class="test3 position-relative bg-primary flex-grow-1">
            <div class="name position-absolute text-light text-wrap d-flex align-items-center h-100 w-100 justify-content-center text-center fs-2 fw-normal p-2">{{ info[2].name }}</div>
            <div class="info position-absolute text-light text-wrap d-flex align-items-center text-center fs-5 fw-normal p-2">{{ info[2].message }}</div>
          </div>
          <div class="test4 position-relative bg-primary flex-grow-1">
            <div class="name position-absolute text-light text-wrap d-flex align-items-center h-100 w-100 justify-content-center text-center fs-2 fw-normal p-2">{{ info[3].name }}</div>
            <div class="info position-absolute text-light text-wrap d-flex align-items-center text-center fs-5 fw-normal p-2">{{ info[3].message }}</div>
          </div>
      </div>
    </div>
    
    <div class="footer position-absolute d-flex flex-column justify-content-center align-items-center px-3 bg-dark" style="top:600%">
      <div class="mid position-absolute d-flex flex-column justify-content-evenly align-items-stretch gap-2">
        <div class="logo mb-2 text-center mb-4">PISTONS</div>
        <div class="plaint text-center fs-4 mb-4">STAY CONNECTED</div>
        <div class="logo d-flex justify-content-evenly align-items-stretch">
          <div class="fb"><svg class="svg1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M400 32H48A48 48 0 0 0 0 80v352a48 48 0 0 0 48 48h137.25V327.69h-63V256h63v-54.64c0-62.15 37-96.48 93.67-96.48 27.14 0 55.52 4.84 55.52 4.84v61h-31.27c-30.81 0-40.42 19.12-40.42 38.73V256h68.78l-11 71.69h-57.78V480H400a48 48 0 0 0 48-48V80a48 48 0 0 0-48-48z"/></svg></div>
          <div class="yt"><svg class="svg1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><path d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z"/></svg></div>
          <div class="in"><svg class="svg1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M224,202.66A53.34,53.34,0,1,0,277.36,256,53.38,53.38,0,0,0,224,202.66Zm124.71-41a54,54,0,0,0-30.41-30.41c-21-8.29-71-6.43-94.3-6.43s-73.25-1.93-94.31,6.43a54,54,0,0,0-30.41,30.41c-8.28,21-6.43,71.05-6.43,94.33S91,329.26,99.32,350.33a54,54,0,0,0,30.41,30.41c21,8.29,71,6.43,94.31,6.43s73.24,1.93,94.3-6.43a54,54,0,0,0,30.41-30.41c8.35-21,6.43-71.05,6.43-94.33S357.1,182.74,348.75,161.67ZM224,338a82,82,0,1,1,82-82A81.9,81.9,0,0,1,224,338Zm85.38-148.3a19.14,19.14,0,1,1,19.13-19.14A19.1,19.1,0,0,1,309.42,189.74ZM400,32H48A48,48,0,0,0,0,80V432a48,48,0,0,0,48,48H400a48,48,0,0,0,48-48V80A48,48,0,0,0,400,32ZM382.88,322c-1.29,25.63-7.14,48.34-25.85,67s-41.4,24.63-67,25.85c-26.41,1.49-105.59,1.49-132,0-25.63-1.29-48.26-7.15-67-25.85s-24.63-41.42-25.85-67c-1.49-26.42-1.49-105.61,0-132,1.29-25.63,7.07-48.34,25.85-67s41.47-24.56,67-25.78c26.41-1.49,105.59-1.49,132,0,25.63,1.29,48.33,7.15,67,25.85s24.63,41.42,25.85,67.05C384.37,216.44,384.37,295.56,382.88,322Z"/></svg></div>
          <div class="tw"><svg class="svg1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"/></svg></div>
          <div class="gm"><svg class="svg1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M64 112c-8.8 0-16 7.2-16 16v22.1L220.5 291.7c20.7 17 50.4 17 71.1 0L464 150.1V128c0-8.8-7.2-16-16-16H64zM48 212.2V384c0 8.8 7.2 16 16 16H448c8.8 0 16-7.2 16-16V212.2L322 328.8c-38.4 31.5-93.7 31.5-132 0L48 212.2zM0 128C0 92.7 28.7 64 64 64H448c35.3 0 64 28.7 64 64V384c0 35.3-28.7 64-64 64H64c-35.3 0-64-28.7-64-64V128z"/></svg></div>
        </div>
      </div>
    </div>

  </div>
</div>
</template>

<style scoped>
  *{
    font-family: var(--plaint);
    font-weight: bold;
    font-size: .9rem;
    text-transform: capitalize;
  }
  .--letter-space{
    letter-spacing: 4px;
  }
  .test1{
    background-image: url('../assets/pic12.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  .test2{
    background-image: url('../assets/pic13.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  .test3{
    background-image: url('../assets/pic14.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  .test4{
    background-image: url('../assets/pic15.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  div.fb, div.in, div.yt, div.gm, div.tw{
    height: 30px;
    width: 30px;
  }
  svg.svg1 path{
    fill: #fff;
  }
  a.plain:hover{
    text-decoration: underline;
  }
  a.logo{
    font-family: var(--logo);
    font-size: 2rem;
    text-transform: capitalize;
  }
  div.logo{
    font-family: var(--logo);
    font-size: 3rem;
    color: #fff;
    letter-spacing: 4px;
    text-transform: capitalize;
  }

  div.pics{
    overflow-x: hidden;
    width: 50%;
    transform: translateY(20%);
    height: 70%;
  }
  div.pics div.carousal{
    width: 500%;
    height: 100%;
    gap: 80px;
    padding: 0 80px;
    animation: image 10s ease infinite;
  }
  div.pics img{
    height: 100%;
    width: 100%;
    position: relative;
  }

  div.test1:hover div.info,
  div.test2:hover div.info,
  div.test4:hover div.info,
  div.test3:hover div.info{
    opacity: 1;
    pointer-events: all;
    cursor: pointer;
  }
  div.info{
    height: 100%;
    width: 100%;
    background-color: #00000047;
    backdrop-filter: blur(10px);
    opacity: 0;
    pointer-events: none;
    transition: all ease .5s;
  }

  @keyframes image {
    0%{
      left: 0;
    }
    5%{
      left: 0;
    }
    25%{
      left: calc(-100% + 80px)
    }
    30%{
      left: calc(-100% + 80px)
    }
    50%{
      left: calc(-200% + 160px)
    }
    55%{
      left: calc(-200% + 160px)
    }
    75%{
      left: calc(-300% + 240px)
    }
    80%{
      left: calc(-300% + 240px)
    }
    100%{
      left: calc(-400% + 320px)
    }
  }
  div.text{
    width: 50%;
    padding: 0 100px;
    transform: translateY(30%);
    height: 100%;
  }

  div.circular-text{
    font-size: 4rem;
    font-weight: normal;
    color: #fff
  }
  div.plaint{
    letter-spacing: 10px;
    color: #fff;
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

  div.picture, div.footer{
    height: 100%;
    width: 100%;
  }
  div.footer{
    height: 50%;
  }
  div.pic1{
    background-image: url('../assets/pic1.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    top: 0;
    left: 0;
  }
  div.pic2{
    background-image: url('../assets/pic2.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    top: 0;
    right: 0;
  }
  div.pic3{
    background-image: url('../assets/pic3.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  div.pic4{
    background-image: url('../assets/pic4.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  div.pic5{
    background-image: url('../assets/pic5.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  div.pic6{
    background-image: url('../assets/pic6.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  div.pic7{
    background-image: url('../assets/pic7.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
  h1.featurette-heading{
    font-size: 3rem;
  }
  div.Testimonyhead{
    flex-grow: 1;
    letter-spacing: 10px;
    font-size: 3rem;
  }
  div.Testimonies{
    flex-grow: 3;
  }
  div.Textimonies img{
    height: 100%;
    width: 100%;
  }

  @media (max-width: 480px) {
    ul.hide{
      display: none;
      pointer-events: none;
    }
    
    div.pic1{
    background-image: url('../assets/pic1.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    top: 0;
    left: 0;
  }

  div.pic2{
    background-image: url('../assets/pic2.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    top: 50%;
    left: 0;
  }
  }

  @media (max-width: 768px) {
    ul.hide{
      display: none;
      pointer-events: none;
    }
  }

</style>
