<template>
  <main>  
    <header><h1>img.src</h1></header>
    <div class="grid-wrap">
      <div class="grid">

          <a href="#" class="grid__item" v-for="item in items" :key="item.name">
            <div class="grid__item-bg"></div>
            <div class="grid__item-wrap">
              <img class="grid__item-img" :src="item.image" v-bind:alt="item.title" />
            </div>
            <h3 class="grid__item-title">{{ item.title }}</h3>
            <h4 class="grid__item-number">{{ item.year }}</h4>
          </a>
       
      </div>
    </div><!-- /grid-wrap -->


    <div class="content">
        <div class="content__item" v-for="item in items" :key="item.name">
          <div class="content__item-intro">
            <img class="content__item-img" :src="item.image" v-bind:alt="item.title" />
          </div>
          <h4 class="content__item-number">{{ item.year }}</h4>
          <h3 class="content__item-subtitle">{{ item.subline }}</h3>
          <div class="content__item-text">
            <p>{{ item.description }}</p>
          </div>
          <div class="content__item-supporting" v-if="item.image2">
            <img :src="item.image2" class="content__image-supporting">
            <figcaption v-if="item.image2copy">{{ item.image2copy }}</figcaption>
            <img :src="item.image3" class="content__image-supporting" v-if="item.image3">
            <img :src="item.image4" class="content__image-supporting" v-if="item.image4">
          </div>
        </div>
    </div><!-- /content__item -->
    
    <button class="content__close">Close</button>
		<svg class="content__indicator icon icon--caret"><use xlink:href="#icon-caret"></use></svg>

  </main>
</template>

<script>

export default {
  name: 'app',
  items: '',
  data() {
  return {
    items: [
      {
        name: 'London Underground',
        title: 'Mind the gap(s)',
        year: '2018',
        image: 'img/london_tube.jpg', 
        image2: 'img/london_tube_2.jpg', 
        image2copy: 'some copy',
        image3: 'img/london_tube_3.jpg', 
        subline: 'Belly of the metal beast', 
        description:'After the Tube worker was long out of site we all piled through the door, the easiest entrance ever. Climbing down an access shaft a good 8 levels, we found ourselves in a maze of old tube passenger tunnels. Venturing through hatches and tunnels over and under various infastructure, we arrived at a portal where some track came to an end. Following the track, we arrived at an area where the track split. Left went to the live station, right reached the dead end we had just come from. This is where the old Angel station used to be used as a island platform. The station was rebuilt a short distance away in the early 1990s. '
      },

      {
        name: 'Rochester Cathedral', 
        title: 'Bell ringer',
        year: '2017', 
        image: 'img/rochester.jpg', 
        image2: 'img/rochester2.jpg', 
        image3: 'img/rochester3.jpg', 
        subline: 'Ring the bells', 
        description:'The cathedral has always been a special building to me. Along with Rochester Castle its a sign im nearly home and an important historical monument. I jumped at the chance to view it close up when some scaffolding appeared up the side. Returning under the cover of darkness, we scaled the scaffolding, careful to avoid the various drunks and police cars frequenting the high street. The view from the top was amazing, you can see a big stretch of the medway and arrays of lights from towns in the distance. After exploring our surroundings, a door was found which led to the bell tower. Climbing the ladders and stairs to the top greeted us with another door that gave us acces to the walkway right next to the clockface. The view from here was slightly clearer being up higher and you could get a full 360 view from gillingham to the M2 bridges all of which are local to me. This trip was one of my favourite roofs so far.'
      },

      {
        name: 'Amsterdam metro', 
        title: 'Trackside blunted',
        year: '2014', 
        image: 'img/amsterdam.jpg', 
        image2: 'img/amsterdam.jpg', 
        subline: 'A dip into the system', 
        description:'After spotting this entrance on Google maps, late one night we headed over to the location. It was a week night, around 1am and super quiet. Gaining access was simple - literally up a steep bank and small wall at the top. Just as I approached what looked to be the last train of the night whizzed by into the not too distant station. Thinking by now the metro service should have stopped I ventured into the tunnel. It was eerily quiet, all that could be heard was my footsteps on the ballast, clicks and switches doing their thing echoing out inside the tunnel which didnt help my paranoia atall. I ventured into the tunnel to grab some clearer photos, the tunnel was brightly lit and had the feeling workers could appear any second wondering what the hell I would be doing there. With no real local knowledge, I grabbed a few more photos and set off back to the safety of the hotel.'
      },

      {
        name: 'Copenhagen', 
        title: 'Danish bacon',
        year: '2013', 
        image: 'img/copenhagen.jpg', 
        image2: 'img/copenhagen2.jpg', 
        image3: 'img/copenhagen3.jpg', 
        subline: 'If Carlsberg did holidays...', 
        description:'My first visit to Denmark I fell in love with the country. The people, architecture and everything in general was amazing. I met up with some of the locals from a crew called CPHCPH who showed us some of the sights. We had a late night look around the main station with around 10 plus lines all coming into one station, we took a late night visit of the then closing Carlsberg factory. The roof provided some amazing views and glimpses of the impressive statues perched upon the roof. More relaxing adventures were spent exploring the city and visits to Christiania. Cant wait to go back.'
      },

      {
        name: 'Belgium', 
        title: 'Tour de belguiq',
        year: '2012', 
        image: 'img/belgium.jpg', 
        image2: 'img/belgium2.jpg', 
        subline: 'after a trip to hell', 
        description:'Reports of epic sites and minimal security were common about Belgium at this time. So that was the plan for the next trip. Chateu noisey was a abandoned Disney castle close to the border of Luxembourg. In Charleroi we visited the half built metro line that never opened. Doel village is an abandoned nearly empty town whose residents moved out due to the gigantic power station situated right next to it.'
      },

      {
        name: 'Old Street', 
        title: 'Luxury flats coming soon',
        year: '2009', 
        image: 'img/old_street.jpg', 
        image2: 'img/old_street2.jpg', 
        subline: 'Penthouse views', 
        description:'At 36-storeys high, this City Road development stands as Islingtons tallest building. The City Basin waterside apartments, moments from Angel tube and Silicon Roundabout, feature unrivalled views, a spa, a lounge and a 24hr concierge service - quotes the website. Scaling the hoarding around the site late at night, we ventured to find the staircase. Arriving on the top floor, we tried to get to the highest point to take in the views from what would be the top penthouse apartment. London always seems alot less busy and quiet from up high.'
      },

      {
        name: 'Herstmonceux', 
        title: 'Empty observations',
        year: '2015', 
        image: 'img/observatory.jpg', 
        image2: 'img/observatory2.jpg', 
        subline: 'Through the keyhole', 
        description:'Isaac Newton Telescope Building. The giant 98-inch Isaac Newton Telescope was once housed in this silver dome to the south of the main complex at The Royal Greenwich Observatory. During its days at Herstmonceux, the RGO built up an enviable reputation for world-class astronomical research. Luckily on our visit a vent was broken and a way in was easy. I loved the atmosphere on this building as it easily felt it could be from the future or some secret military operation from the past. The gigantic gap in the center of the build where the telescope once sat, left a void throughout the buidling giving a feeling somehting is missing. '
      },

      {
        name: 'Hoo & Cliffe', 
        title: 'Sampling local delights',
        year: '2011', 
        image: 'img/hoo_cliffe.jpg', 
        image2: 'img/hoo_cliffe2.jpg', 
        subline: 'Whatevers left', 
        description:'Medway is layered with history. '
      },

      {
        name: 'Shorts Tunnels', 
        title: 'Shorts aviation co',
        year: '2011', 
        image: 'img/8.jpg', 
        subline: 'Local legends', 
        description:'had preferred their language and would learn no other. The family removed to America a month after I arrived in the islands'
      },

      {
        name: 'Ferrier Estate', 
        title: 'Council estate of mind',
        year: '2011', 
        image: 'img/ferrier.jpg', 
        subline: 'Grey and brutal', 
        description:'had preferred their language and would learn no other. The family removed to America a month after I arrived in the islands'
      },

      {
        name: 'London Nights', 
        title: 'Up high and down low',
        year: '2011', 
        image: 'img/london_night.jpg', 
        image2: 'img/london_night2.jpg', 
        subline: 'Night on the tiles', 
        description:'had preferred their language and would learn no other. The family removed to America a month after I arrived in the islands'
      },

      {
        name: 'Leybourne', 
        title: 'Asylum seeker',
        year: '2008', 
        image: 'img/maidstone.jpg', 
        image2: 'img/maidstone2.jpg', 
        subline: 'The one that started it all', 
        description:'Leybourne Grange opened in 1936. It housed up to 1200 patients and closed in 1996. Word got around of the abandonement, and I remember first visiting in 2009 which probably along with alot of other people, was my first dip into "urban exploration". The layout of the hospital was absolutley massive like most asylums. Various brick outbuildings were dotted around the site, scattered with parts of old beds and various ward apparatus. The real showpiece is the manor house, which has been kept and restored for the new housing development. '
      },

      {
        name: 'Berlin', 
        title: 'secrets of war',
        year: '2010', 
        image: 'img/berlin.jpg', 
        subline: 'The devils mountain', 
        description:'Teufelsberg is situated on the western outskirts of Berlin city center, from the moment I saw the photos of the golf ball looking structures I knew I wanted to see it in person. We left our hotel in the east of the city and headed to Teufelsberg. The Listening sation is sat atop of a man made hill, supposidly to benefit its listening capabilities. After walking through the park there is a boundary fence, luckily for us we found a hole rather easily. The whole site is massive and in various states of decay.'
      },

      {
        name: 'Aldgate', 
        title: 'Up high and down low',
        year: '2011', 
        image: 'img/aldgate.jpg', 
        subline: 'This building is not strucually safe', 
        description:'I had walked past the derelict orange Minories building for years on the way to work, always glimpsing the "Keep out dangerous structure" signs and thinking what good views it would have from the roof. After hearing of its iminent demolition, after trying another site in London on night we scaled to the roof. Entry was easy enough, we caught the site at a great time, around 3/4 levels of scaffolding had appeared and was enough to get us up and inside the building. There was not much to see inside, it was late, dark and the building has been completly stripped and laid bare for years. The roof gave great views into the city and the surrounding Aldgate.'
      }

    ]
  }
}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
