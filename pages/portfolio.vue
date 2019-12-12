<template>
  <div>
    <section class="portfolio section">
      <div class="container">
        <div class="top-side">
          <h2 style="text-align: center;">{ PORTFOLIO }</h2>
        </div>

        <!-- <div class="filters">
          <ul>
            <li class="active" data-filter="*">All</li>
            <li data-filter=".developer">Developer</li>
            <li data-filter=".designer">Designer</li>
            <li data-filter=".logos">Logos</li>
          </ul>
        </div> -->

        <div class="filters-content">
          <div class="container">
            <div class="gallery">
              <div v-for="(work, index) of works" :key="index" class="gallery-item" tabindex="0">
                <img :src="work.image" class="gallery-image" />

                <div v-if="work.type != null" class="gallery-item-type">
                  <span class="visually-hidden">
                    <i v-if="work.type == 'Gallery'" class="icon-type-gallery" aria-hidden="true" />
                    <i v-else class="icon-type-video" aria-hidden="true" />
                  </span>
                </div>

                <div class="gallery-item-info">
                  <ul>
                    <li class="gallery-item-comments">
                      <span class="visually-hidden">
                        <i class="icon-comment" aria-hidden="true"></i>
                        {{ work.name }}
                      </span>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <script src="https://unpkg.com/isotope-layout@3.0.4/dist/isotope.pkgd.min.js"></script>
    <script src="./script.js"></script>
  </div>
</template>

<script>
const works = [
  {
    id: 1,
    name: 'Developer SPA for Pyrocode Software 1',
    type: 'Developer',
    image: './images/developer-pyrocode.png'
  },
  {
    id: 2,
    name: 'A abstract logo company 2',
    type: 'Logo',
    image: './images/logo-abstract-company.png'
  },
  {
    id: 3,
    name: 'First logo for Pyrocode Softwate',
    type: 'Logo',
    image: './images/logo-pyrocode-1.png'
  },
  {
    id: 3,
    name: 'New logo for Pyrocode Softwate',
    type: 'Logo',
    image: './images/logo-pyrocode-2.png'
  }
]
export default {
  data () {
    return {
      works,
      work: {
        id: null,
        name: String,
        type: String,
        image: String
      }
    }
  },
  created () {
    this.worksUpdate()
  },
  methods: {
    worksUpdate (tasks) {
      this.work = works
      console.log(works)
    }
  }
}
</script>

<style scoped>
.section {
  padding: 30px 0;
  color: #333;
}P
.section .top-side .title {
  font-weight: 500;
  font-size: 15px;
  display: inline-block;
}
.section .top-side .title:after {
  content: "";
  display: block;
  width: 50%;
  border-bottom: 1px solid #494949;
  margin: 8px auto;
}
.section .top-side h2 {
  font-weight: 700;
}
.section.portfolio .filters {
  text-align: center;
  margin-top: 50px;
}
.section.portfolio .filters ul {
  padding: 0;
}
.section.portfolio .filters ul li {
  list-style: none;
  display: inline-block;
  padding: 20px 30px;
  cursor: pointer;
  position: relative;
}
.section.portfolio .filters ul li:after {
  content: "";
  display: block;
  width: calc(0% - 60px);
  position: absolute;
  height: 2px;
  background: #333;
  transition: width 350ms ease-out;
}
.section.portfolio .filters ul li:hover:after {
  width: calc(100% - 60px);
  transition: width 350ms ease-out;
}
.section.portfolio .filters ul li.active:after {
  width: calc(100% - 60px);
}
.section.portfolio .filters-content {
  margin-top: 50px;
}
.section.portfolio .filters-content .show {
  opacity: 1;
  visibility: visible;
  transition: all 350ms;
}
.section.portfolio .filters-content .hide {
  opacity: 0;
  visibility: hidden;
  transition: all 350ms;
}
.section.portfolio .filters-content .item {
  text-align: center;
  cursor: pointer;
  margin-bottom: 30px;
}
.section.portfolio .filters-content .item .p-inner {
  padding: 20px 30px;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
}
.section.portfolio .filters-content .item .p-inner h5 {
  font-size: 15px;
}
.section.portfolio .filters-content .item .p-inner .cat {
  font-size: 13px;
}
.section.portfolio .filters-content .item img {
  width: 100%;
}
.container {
  max-width: 93.5rem;
  margin: 0 auto;
  padding: 0 2rem;
}
.gallery {
  display: flex;
  flex-wrap: wrap;
  margin: -1rem -1rem;
  padding-bottom: 3rem;
}
.gallery-item {
  position: relative;
  flex: 1 0 22rem;
  margin: 1rem;
  color: #fff;
  cursor: pointer;
}
.gallery-item:hover .gallery-item-info,
.gallery-item:focus .gallery-item-info {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.3);
}
.gallery-item-info {
  display: none;
}
.gallery-item-info li {
  display: inline-block;
  font-size: 1.7rem;
  font-weight: 600;
}
.gallery-item-likes {
  margin-right: 2.2rem;
}
.gallery-item-type {
  position: absolute;
  top: 1rem;
  right: 1rem;
  font-size: 2.5rem;
  text-shadow: 0.2rem 0.2rem 0.2rem rgba(0, 0, 0, 0.1);
}
.fa-clone,
.fa-comment {
  transform: rotateY(180deg);
}
.gallery-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.icon-like {
  display: block;
  background-position: -384px -87px;
  background-image: url(/sprite.png);
  background-size: 405px 379px;
  background-repeat: no-repeat;
  height: 18px;
  width: 20px;
  text-indent: -1000%;
}
.icon-comment {
  display: block;
  background-position: -384px -106px;
  background-image: url(/sprite.png);
  background-size: 405px 379px;
  background-repeat: no-repeat;
  height: 18px;
  width: 20px;
  text-indent: -1000%;
}
.icon-type-gallery {
  display: block;
  background-position: -251px -286px;
  background-image: url(/sprite.png);
  background-size: 405px 379px;
  background-repeat: no-repeat;
  height: 18px;
  width: 20px;
  text-indent: -1000%;
}
.icon-type-video {
  display: block;
  background-position: -251px -286px;
  background-image: url(/sprite.png);
  background-size: 405px 379px;
  background-repeat: no-repeat;
  height: 18px;
  width: 20px;
  text-indent: -1000%;
}
</style>
