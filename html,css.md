```html
 <!DOCTYPE html>
 <html lang="en">
 <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <meta http-equiv="X-UA-Compatible" content="ie=edge">
     <title>Document</title>
     <style>
         *{
             padding: 0;
             margin: 0;
         }
         .all{
            position: relative;
             background: url(images/back.jpg);
             background-size: 1536px 800px;
             height: 759px;
             background-repeat: no-repeat;

         }
        .blb{
            /* border: 3px solid black; */
            width: 448px;
            height: 398px;
            position: relative;
            left: 120px;
            top: 315px;
            opacity: 0.7;
        }

         div .blackb{
             width: 440px;
             height: 395px;
              -webkit-transition: width 5s, height 5s, -webkit-transform 1s; 
             transition: width 2s, height 2s, transform 5s; 
            }
              
           div .blackb:hover {
            width: 440px;
             height: 395px;
            transform: rotate(360deg);
        } 
        
         body,div,ul,li{
            margin:0;
            padding:0;
        }
        ul{
            list-style-type:none;
        }
        body{
            /* background:#000; */
            text-align:center;
            font:12px/20px Arial;
        }
        #box{
            position: absolute;
            background:#000;
            margin:10px auto;
            cursor:pointer;
            left:120px;
            top: 300px;
            width: 450px;
            height: 400px;
            border-radius: 237px;
        }
        #box .list{
            position:relative;
            width:450px;
            height:400px;
            overflow:hidden;
            border-radius: 10px
        }
        #box .list ul{
            position:absolute;
            top:0;
            left:0;
        }
        #box .list li{
            width:450px;
            height:400px;
            overflow:hidden;
        }
        #box .count{
            position:absolute;
            right:0;
            bottom:5px;
        }
        #box .count li{
            
            color:#fff;
            float:left;
            width:20px;
            height:20px;
            cursor:pointer;
            margin-right:57px;
          
            overflow:hidden;
            background:rgb(58, 38, 8);opacity:0.7;
            filter:alpha(opacity=70);
            position: relative;
            top: -18px;
        }
        #box .count li.current{
            color:#fff;
            opacity:1;
            filter:alpha(opacity=100);
            font-weight:700;
           
        }
        .list ul li img{
            width : 450px;
            height: 400px;
            opacity: 0.6;
        }
        /* #tmp{
            width:100px;
            height:100px;
            background:red;
            position:absolute;
        } */
        .topbt,.downbt{
            display: none;
            position: absolute;
            width: 50px;
            height: 100px;
            left: 600px;
            cursor: pointer;
        }
        .topbt{
            top: 400px;
            background: url(images/xiashjt.jpg);
            background-size: 50px 100px;
            opacity: 0.1;

        }
        .downbt{
            top:550px;
            background: url(images/shjt.jpg);
            background-size: 50px 100px;
            opacity: 0.1;
        }
     
         
     </style>
 </head>
 <body>
     <div class="all">
         <div class = "blb" style="display: block">
             <img src="images/黑板.jpg" alt="" class="blackb">
         </div>
            <!-- <div class = "style"> -->
              <div class="topbt"></div>
                    <div class = "downbt"></div>
            <div id="box" style="display: none">
                <div class="list">
                    <ul>
                        
                        <li><img src="images/shangc.jpg"  /></li>
                        <li><img src="images/单车.jpg"  /></li>
                        <li><img src="images/girl.jpg"  /></li>
                        <li><img src="images/bridge.jpg"  /></li>
                        <li><img src="images/that you.jpg" /></li>
                        <li><img src="images/happy.jpg"  /></li>
                    </ul>
                </div>
            <!-- </div> -->
         </div>
                   
     </div>
     <script src="轮播图.js"></script>
 </body>
 </html>
 ```
