<template>
    <div>
            <body>
                <div class="slider">
                    <div class="slide-track">
                        <div class="slide">
                            <img src="/1.png" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/2.jpeg" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/3.jpeg" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/4.png" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/5.png" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/6.png" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/7.png" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/8.png" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/2.jpeg" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/10.png" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/11.png" height="100" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/1.png" height="100" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/5.png" height="150" width="250" alt="" />
                        </div>
                        <div class="slide">
                            <img src="/8.png" height="150" width="250" alt="" />
                        </div>
                    </div>
                </div>
            </body>
    </div>
</template>

<script>

</script>

<style scoped>
body {
	align-items: center;
	background: #E3E3E3;
	display: flex;
	height: 100vh;
	justify-content: center;
}

@keyframes scroll {
	0% { transform: translateX(0); }
	100% { transform: translateX(calc(-250px * 7)); }
}

.slider {
	background: white;
	box-shadow: 0 10px 20px -5px rgba(0, 0, 0, .125);
	height: 150px;
	margin: auto;
	overflow: hidden;
	position: relative;
	width: 100%;
    margin-top: 100px;
    margin-bottom: 50px;
}

.slider::before,
.slider::after {
	background: linear-gradient(to right, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
	content: "";
	height: 100px;
	position: absolute;
	width: 200px;
	z-index: 2;
}

.slider::after {
	right: 0;
	top: 0;
	transform: rotateZ(180deg);
}

.slider::before {
	left: 0;
	top: 0;
}

.slide-track {
	animation: scroll 40s linear infinite;
	display: flex;
	width: calc(250px * 14);
}

.slide {
	height: 100px;
	width: 250px;
}

</style>