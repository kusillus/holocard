<template>
	<div 
        :style="background_style"
		class="card_container">
	</div>
</template>
<script>
	export default {
		props: {
            item: {
                required: true
            }
        },
	  	data () {
	    	return {
	      	background_style: {
                background: 'linear-gradient(rgba(0, 0, 0, 0.2) 10%, rgba(0, 0, 0, 0) 20%, rgba(0, 0, 0, 0) 50%, rgba(6, 0, 14, 0.2) 80%), url("' + this.item.image +'")',
	      		backgroundSize: 'cover',
				backgroundPosition: 'center'
	      		}
	    	}
	  	},
	}
</script>
<style lang="scss">
	.card_container{
		width: 17rem;
		height: 25rem;
		margin: .5rem 1rem;
		background-size: cover;
		background-position: center;
		color: white;
		border-radius: .8rem;
		box-shadow: 0px 0px 15px 1px rgba(0, 0, 0, 0.2);
		cursor: pointer;
		transition: all .3s ease;
        position: relative;
        overflow: hidden;

        &::before,
        &::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        &::after {
            background-image: url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/13471/sparkles.gif");
            background-position: center;
            mix-blend-mode: color-dodge;
            opacity: 0.5;
        }
        
        &:hover::before {
            background-image: linear-gradient(115deg, transparent 20%, #66e2ef 40%, #ff06e8 70%, transparent 80%);
            background-position: 200% 0%;
            background-repeat: no-repeat;
            background-size: 260%;
            mix-blend-mode: overlay;
            transition: all .2s;
            z-index: 2;
            animation: efect-card 2.5s infinite;
        } 
	}
    @keyframes efect-card {
        50% {
            background-position: 120% 0%;
            opacity: 1;
        }
        50% {
            background-position: -80% 0%;
            opacity: 0.7;
        }
        100% {
            background-position: -80% 0%;
            opacity: 0.7;
        }
    }
</style>