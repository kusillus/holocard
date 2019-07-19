<template>
  <div class="container">
    <card 
		v-for="(item, i) in posts" 
		:item="item"
		:key="i"/>
  </div>
</template>

<script>

import Card from '@/components/Card.vue'
export default {
  	data() {
    	return {
			posts: [
				{
					id: 1,
					image: require('@/assets/BWP_ES_BW45.png'),
                },
				{
                    id: 2,
                    image: require('@/assets/SM5_ES_13.png')
                },
                {
                    id: 3,
                    image: require('@/assets/XYP_ES_XY124.png'),
                },
                {
                    id: 4,
                    image: require('@/assets/XYP_ES_XY84.png'),
				},
				{
                    id: 5,
                    image: require('@/assets/XYA_ES_24a.png'),
                },
                {
                    id: 6,
                    image: require('@/assets/SM4_ES_119.png')
                },
			]
    	}
  	},
  	components: {
    	'card': Card
  	}
}
</script>

<style>
.container {
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
