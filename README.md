# yaoyao03
<!DOCTYPE html>
<html>
<head>
	<title>yaoyao03</title>
	<style type="text/css">
	form{
		margin-top: 40px;
		text-align: center;
	}
	#outschool{
		margin-left: 100px;
	}
	#inschooler{
		margin: 20px 10px;
		font-size: 150%;
	}
	#outschooler{
		margin: 20px 10px;
		font-size: 150%;
	}
	#contain{
		margin: 30px 0px;
		font-weight: bold;
	}
	#text{
		height: 20px;
		width: 300px;
		border: solid 1px #778899;
		border-radius: 5px;
		-moz-border-radius:5px;
	}
	#city{
		margin-right: 30px;
		height: 25px;
		width: 60px;
		border: solid 1px #778899;
		border-radius: 5px;
		-moz-border-radius:5px;
	}
	#school-list{
		height: 25px;
		width: 100px;
		border: solid 1px #778899;
		border-radius: 5px;
		-moz-border-radius:5px;	
	}
	#school{
		display: none;
	}
	#work{
		display: none;
	}
	</style>
</head>
<body>
<form>
	<input type="radio" name="status" id="inschool">
	<label id="inschooler">在校生</label>
	<input type="radio" name="status" id="outschool">
	<label id="outschooler">非在校生</label>
	<div id="contain">
		<div id="school">
			<span>学校</span>
			<select id="city">
				<option>北京</option>
				<option>上海</option>
				<option>广州</option>
				<option>杭州</option>
			</select>
			<select id="school-list">
				<option>北京大学1</option>
				<option>北京大学2</option>
				<option>北京大学3</option>
			</select>
		</div>
		<div id="work">
			<span>就业单位</span>
			<input type="text" id="text">
		</div>
	</div>
</form>
</body>
<script type="text/javascript">
	var city=document.getElementById("city");
	var school=document.getElementById("school-list");
	document.addEventListener("click",function(){
		var x = event.target;
		switch(x.id){
			case "inschool":
			document.getElementById("school").style.display="block";
			document.getElementById("work").style.display="none";
			break;
			case "outschool":
			document.getElementById("school").style.display="none";
			document.getElementById("work").style.display="block";
		}
	});
	var cityarr=["北京","上海","广州","杭州"];
	var schoolarr=[["北京大学1","北京大学2","北京大学3"],["上海大学1","上海大学2","上海大学3"],["广州大学1","广州大学2","广州大学3"],["杭州大学1","杭州大学2","杭州大学3"]];
	document.addEventListener("change",function(){
		var x = event.target;
		if (x.id=="city") {
			school.innerHTML="";
			var index=city.selectedIndex;
			for (var i = 0; i < schoolarr[index].length; i++) {
				var option=document.createElement("option");
				school.appendChild(option);
				option.innerHTML=schoolarr[index][i];
			}
		}
	});
</script>
</html>
