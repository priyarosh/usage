<!DOCTYPE html>

<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <title>climate</title>
    <script>
function populate(s1,s2){
    var s1=document.getElementById(s1);
    var s2=document.getElementById(s2);
    s2.innerHTML="";
    if(s1.value=="dry"){
        var dry_array=["|","0.75|0.75","0.80|0.80","0.85|0.85","0.90|0.90","1.00|1.00"]
    }
    else if(s1.value=="wet"){
        var dry_array=["|","0.25|0.25","0.50|0.50","0.55|0.55","0.60|0.60","0.65|0.65"] 
    }
    else if(s1.value=="heavy rain"){
        var dry_array=["|","0.10|0.10","0.20|0.20","0.30|0.30","0.40|0.40","0.55|0.55"]
    }
    else if(s1.value=="ice"){
        var dry_array=["0.10|0.10"]
    }
    for(var option in dry_array){
        var pair=dry_array[option].split("|");
        var newData=document.createElement("option");
        newData.value=pair[0];
        newData.innerHTML=pair[1];
        s2.options.add(newData);
     
      }
    }


</script>
</head>
<body>
<label for="mass">Mass : </label>
<input type="number" id="mass" name="mass" /><br /><br />

<label for="choose climate">choose climate : </label>
<select id="slct1" name="slct1" onchange="populate('slct1','slct2')">

    <option value=""</option>
    <option value="dry">dry</option>
    <option value="wet">wet</option>
    <option value="heavy rain">heavy rain</option>
    <option value="ice">ice</option>
</select><br></br>

<label for="choose climate">choose value : </label>
<select id="slct2" name="slct2">
</select><br></br>
<input type="submit" value="Submit">

        
</body>
</html>
