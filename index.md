<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>
	<textarea id="txt" cols="2" rows="6" style="width: 30rem;height: 15rem" width="500" height="500"></textarea>
	<button onclick="fun1()">转Unicode</button>
	<button onclick="fun2()">转中文</button>
	<div id="txt1"></div>
</body>
<script type="text/javascript">

function isChinese(s){//判断是否汉字
	return /[\u4e00-\u9fa5]/.test(s);
}
function ch2Unicdoe(str){//得到Unicode
	if(!str){
		return;
	}
	var unicode = '';
	for (var i = 0; i <  str.length; i++) {
		var temp = str.charAt(i);
		// if(isChinese(temp)){
			unicode += ' ' +  temp.charCodeAt(0).toString(16);
		// }
		// else{
		// 	unicode += temp;
		// }
	}
	return unicode;
}
function fun1(){
	var a=document.getElementById('txt').value
	document.getElementById('txt1').innerHTML=ch2Unicdoe(a)
}
function fun2(){
	var a=document.getElementById('txt').value
	a=a.replace(/\s*/g,"")
	var tem=''
	for (var i = 0; i <=a.length-4;i+=4) {
		tem+=String.fromCharCode(parseInt(a.substr(i, 4),16).toString(10));
		console.log(tem)
	}
	document.getElementById('txt1').innerHTML=tem
}

</script>
</html>
