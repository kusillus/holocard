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
        &::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            background-image: url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/13471/sparkles.gif");
            background-position: center;
            mix-blend-mode: color-dodge;
            opacity: 0.5;
            // z-index: 2;
            width: 100%;
            height: 100%;
        }
        &:hover::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: linear-gradient(115deg, transparent 20%, #66e2ef 40%, #ff06e8 70%, transparent 80%);
            z-index: 2;
            mix-blend-mode: overlay;
            transition: all .2s;
            background-position: 200% 0%;
            background-repeat: no-repeat;
            background-size: 260%;
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

	.card_content{
		text-align: left;
		padding: 1rem;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		box-sizing: border-box;
	}
	.text_top{
		font-weight: bold;
		font-family: 'Gugi', cursive;
	}
	.text_bottom{
		font-weight: 300;
    	font-family: 'Exo 2', sans-serif;
    	text-align: center;
	}
	.card_container:hover{
		filter: brightness(120%);
	}
</style>