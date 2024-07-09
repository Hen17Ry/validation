<template>
    <div class="footer">
        <footer>
            <div class="footer">

                <div class="row">
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">Service</a></li>
                        <li><a href="#">Contact-Us</a></li>
                    </ul>
                </div>

                <div class="row">
                    INFERNO Copyright © 2021 Inferno - All rights reserved || Designed By: Mahesh 
                </div>
            </div>
    </footer>
    </div>
</template>
  
<script>
  export default {
    name: 'BubbleFooter',
  };
</script>
  
  <style scoped>  
    .footer{
        background: linear-gradient(to right, #b927fc 0%, #2c64fc 100%);
        padding:10px 0px;
        font-family: 'Play', sans-serif;
        text-align:center;
        font-size: 20px;
        color: white;
        font-weight: bold;
        height: 200px;
    }

    .footer .row{
        width:100%;
        margin:1% 0%;
        padding:0.6% 0%;
        font-size:0.8em;
        color: white;
        font-weight: bold;
    }

    .footer .row a{
        text-decoration:none;
        transition:0.5s;
        color: white;
        font-weight: bold;
        font-size: 30px;
    }

    .footer .row a:hover{
        color:#fff;
    }

    .footer .row ul{
        width:auto;
    }

    .footer .row ul li{
        display:inline-block;
        margin:0px 30px;
        color: white;
        font-weight: bold;
    }

    .footer .row a i{
        font-size:2em;
        margin:0% 1%;
        
    }

    @media (max-width:720px){
        .footer{
        text-align:left;
        padding:5%;
        }
        .footer .row ul li{
        display:block;
        margin:10px 0px;
        text-align:left;
        }
        .footer .row a i{
        margin:0% 3%;
        }
    }
</style>
  