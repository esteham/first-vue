<template>
  <div>
    <div id="homeCarousel" class="carousel slide shadow-sm" data-bs-ride="carousel">
      <ol class="carousel-indicators">
        <li data-bs-target="#homeCarousel" class="active"></li>
        <li data-bs-target="#homeCarousel"></li>
        <li data-bs-target="#homeCarousel"></li>
      </ol>

      <div class="carousel-inner">
        <div class="carousel-item active">
          <img
            src="/images/carousel/image1.jpg"
            alt="Slide 1"
            class="d-block w-100"
            style="object-fit: cover; height: 500px"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>Helping Those in Need</h5>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
          </div>
        </div>
        <div class="carousel-item">
          <img
            src="/images/carousel/image2.jpg"
            alt="Slide 2"
            class="d-block w-100"
            style="object-fit: cover; height: 500px"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>Breaking Barriers</h5>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
          </div>
        </div>
        <div class="carousel-item">
          <img
            src="/images/carousel/image3.jpg"
            alt="Slide 3"
            class="d-block w-100"
            style="object-fit: cover; height: 500px"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>Spreading Joy</h5>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
          </div>
        </div>
      </div>

      <a class="carousel-control-prev" href="#homeCarousel" role="button" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
      </a>
      <a class="carousel-control-next" href="#homeCarousel" role="button" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
      </a>
    </div>

    <section class="mt-4">
      <h2>About Our Service</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus quam harum voluptates autem
        molestiae dolorum dolore repellat, optio reiciendis, aspernatur, repellendus veritatis ad
        ullam ipsam eligendi similique iste nulla voluptatum!
      </p>
    </section>
  </div>
</template>
