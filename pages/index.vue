<template>
  <section class="section">        
    <div 
      class="content has-text-centered" 
      style="width:100%; height:500px">            
      <svg 
        version="1.1" 
        xmlns="http://www.w3.org/2000/svg" 
        xmlns:xlink="http://www.w3.org/1999/xlink" 
        x="0px" 
        y="0px"
        width="100%" 
        height="100%"
        viewBox="0 0 100 100"               
        xml:space="preserve">
        <defs>
          <clipPath 
            v-for="clips in circleClips" 
            :id="clips.id"
            :key="clips.id" 
            stroke-width="1.5" 
            stroke="#000">
            <circle                     
              :r="clips.r"
              :cx="clips.cx"
              :cy="clips.cy"
              :transform="clips.transform"
              stroke-width="1.5" 
              stroke="#000"
              fill="none" />
          </clipPath>                
        </defs>
        <g 
          id="flowerClip" 
          ref="flowerClip"                 
          transform="translate(45,40)">
          <circle 
            v-for="circle in circles" 
            :key="circle.circId" 
            :r="circle.r" 
            :cy="circle.cy" 
            :cx="circle.cx"                  
            :fill="circle.fill"                   
            :clip-path="circle.clipPath"
            :transform="circle.transform"                  
          />
        </g>
        <g 
          id="flowerCircle" 
          ref="flowerCircle"
          transform="translate(45,40)">                                
          <circle 
            v-for="circle in circles" 
            :key="circle.circId" 
            :r="circle.r" 
            :cy="circle.cy" 
            :cx="circle.cx"                  
            :transform="circle.transform"                   
            fill="none"
            stroke-width=".5"
            stroke="#DADADA" 
          />
        </g>
      </svg>
    </div>
  </section>
</template>

<script>
import SvgCircle from '@/components/SvgCircle'
import TweenMax from 'gsap'

export default {
  name: 'HomePage',
  components: { SvgCircle },
  data() {
    return {
      timeline: null,
      circleClips: [
        {
          id: 'mask_b',
          cx: 10,
          cy: 0,
          r: 10,
          transform: 'rotate(120,0,0)'
        }
      ],
      circles: [
        {
          cx: 0,
          cy: 0,
          r: 10,
          fill: 'none',
          circId: 'a'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          circId: 'b',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(60, 0, 0)',
          circId: 'c',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(120, 0, 0)',
          circId: 'd',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(180, 0, 0)',
          circId: 'e',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(240, 0, 0)',
          circId: 'f',
          clipPath: 'url(#mask_b)'
        },
        {
          cx: 10,
          cy: 0,
          r: 10,
          fill: 'red',
          transform: 'rotate(300, 0, 0)',
          circId: 'g',
          clipPath: 'url(#mask_b)'
        }
      ]
    }
  },
  mounted() {
    const flowerClip = this.$refs.flowerClip
    const flowerCircle = this.$refs.flowerCircle

    this.timeline = new TimelineMax({
      //   onComplete: () => this.timeline.restart()
    })
    this.timeline
      .to(flowerClip, 1, {
        scale: 0.1,
        rotation: 720,
        opacity: 0,
        transformOrigin: '0% 0%',
        skewX: 45
      })
      .to(flowerClip, 3, {
        x: 45,
        y: 40,
        skewX: 0,
        opacity: 1,
        scale: 1,
        rotation: -720
      })
      .to(flowerClip, 3, {
        rotation: 1080,
        transformOrigin: '50% 50%'
      })
      .to(
        flowerCircle,
        3,
        {
          rotation: 360,
          transformOrigin: '50% 50%'
        },
        '-=0.50'
      )
      .to(
        flowerCircle,
        3,
        {
          scale: 0.5
        },
        '-=0.50'
      )
      .to(
        flowerClip,
        3,
        {
          scale: 0.5
        },
        '-=1'
      )
      .to(flowerCircle, 3, {
        scale: 2
      })
      .to(
        flowerClip,
        3,
        {
          scale: 2
        },
        '-=3'
      )
  }
}
</script>
