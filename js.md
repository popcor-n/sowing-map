```javascript
window.onload = function ()
{
    var countClic = 0;
    var blb = document.getElementsByTagName('div')[1];
    var divAll = document.getElementsByTagName('div')[0];
    var pic = document.getElementsByTagName('img')[0];
    var tbutton = document.getElementsByClassName('topbt')[0];
    var dbutton = document.getElementsByClassName('downbt')[0];
    
    var count = 0;
    var stimer = setInterval(function(){
        if(window.innerWidth < 1060){
            alert('全屏体验效果更好哦 ;_ ;');
            count++;
        }if(count == 3)
    clearInterval(stimer);
    },2000)
    blb. onclick = function(){
        oBox.style.display = 'block';
        blb.style.display = 'none';
        tbutton.style.display = 'block';
        dbutton.style.display = 'block';
       
	}
	
    
	var oBox = document.getElementById("box");
	var oList = oBox.getElementsByTagName("ul")[0];
	var aImg = oBox.getElementsByTagName("img");
	var timer = playTimer = null;
	var index = i = 0;
	var bOrder = true;
	var aTmp = [];
	var aBtn = null;
	var obtn;
	
	//生成数字按钮
	for (i = 0; i < aImg.length ; i++) {
        aTmp.push("<li>" + (i + 1) + "</li>");
    }
	//插入元素
	var oCount = document.createElement("ul");
	oCount.className = "count";
	oCount.innerHTML = aTmp.join("");
	oBox.appendChild(oCount);	
	aBtn = oBox.getElementsByTagName("ul")[1].getElementsByTagName("li");
	abtn = oBox.getElementsByTagName("ul")[1].getElementsByTagName("li")[0];
	//初始化状态
	cutover();
	
	//按钮点击切换
	for (i = 0; i < aBtn.length; i++)
	{
		aBtn[i].index = i;
		aBtn[i].onmouseover = function ()
		{
			index = this.index;
			cutover()
		}
	}
	
	function cutover()
	{
        for (i = 0; i < aBtn.length; i++) aBtn[i].className = "";
		if(index == 5){
			aBtn[0].className = 'current';
		}		
		else{
			aBtn[index].className = "current";
		}
		startMove(-(index * aImg[0].offsetHeight))
	}
	
	function next()
	{
		
		if(index == 6){
			clearInterval(playTimer);
			index = 0;
			oList.style.top = 0;
			aBtn[0].className = 'current';
			playTimer = setInterval(next, 3000);
		}
		for (i = 0; i < aBtn.length; i++) aBtn[i].className = "";
		aBtn[index].className = "current";
		startMove(-(index * aImg[0].offsetHeight));
		index++;

		
	}
	
	playTimer = setInterval(next, 3000);
	//移入停止自动播放
	oBox.onmouseover = function ()
	{
		clearInterval(playTimer)
	};
    dbutton.onmouseover = function ()
	{
		clearInterval(playTimer)
    };

	//离开开始自动播放
	oBox.onmouseout = function ()
	{
		playTimer = setInterval(next, 3000)
    };
    
	function startMove(iTarget)
	{
		clearInterval(timer);
		timer = setInterval(function ()
		{
			doMove(iTarget)
		}, 30)	
	}
	function doMove (iTarget)
	{		
		var iSpeed = (iTarget - oList.offsetTop) / 10;
		if(iSpeed > 0){
			iSpeed = Math.ceil(iSpeed);
		}else{
			iSpeed = Math.floor(iSpeed);
		}
		if(oList.offsetTop == iTarget) {
			clearInterval(timer) ;
	    }else{
			oList.style.top = oList.offsetTop + iSpeed + "px"
		} 
    }
    tbutton.onclick = function(){
		if(index == 0){
			clearInterval(playTimer);
			index = 5;
			oList.style.top = -2000 + 'px';
			aBtn[5].className = 'current';
			playTimer = setInterval(next, 3000);
		}
        index --;
		cutover();
    }
    dbutton.onclick = function(){
		if(index == 6){
			clearInterval(playTimer);
			index = 0;
			oList.style.top = 0;
			aBtn[0].className = 'current';
			playTimer = setInterval(next, 3000);
		}
        index ++;
        cutover();
    }
    // tbutton.onmouseover  = function(){
	// 	tbutton.style.opacity = 0.3;
	// 	clearInterval(playTimer);
	// }
	// tbutton.onmouseout  = function(){
	// 	playTimer = setInterval(next, 3000)
	// }
    tbutton.onmouseout  = function(){
        tbutton.style.opacity = 0.1;
	}
	tbutton.onmouseover  = function(){
        tbutton.style.opacity = 0.3;
    }
    dbutton.onmouseover  = function(){
        dbutton.style.opacity = 0.3;
    }
    dbutton.onmouseout  = function(){
        dbutton.style.opacity = 0.1;
	}
	var shd = oBox.getElementsByTagName('ul')[1].getElementsByTagName("li")[5];
	shd.style.display = 'none';

	
};
```
