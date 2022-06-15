# day04
 What is XMLHTTP Request? &amp; scope
 
1.How to compare two JSON have the same properties without order?
    var obj1 = { name: "Person 1", age:5 };
    var obj2 = { age:5, name: "Person 1" };
    
 Code:
 var obj1 = { name: "Person 1", age:5 };
 var obj2 = { age:5, name: "Person 1" };
 if(Object.keys(obj1).length==Object.keys(obj2).length){
    for(var key in obj1) { 
        if(obj1[key] == obj2[key]) {
          console.log(key+" "+"is equal")}
          else{
            console.log(key+" "+"is Not equal")
          }
        }
}

2.Use the rest countries API url -> https://restcountries.eu/rest/v2/all and display all the country flags in console

Code:
var request=new XMLHttpRequest();
request.open("get","https://raw.githubusercontent.com/rvsp/restcountries-json-data/master/res-countries.json")
request.send();
request.onload =function(){
    var result=JSON.parse(request.response);
   for(i=0;i<result.length;i++)
    {console.log(result[i].name+" "+result[i].flag);
}
}

3. Use the same rest countries and print all countries name, region, sub region and population

code:
var request=new XMLHttpRequest();
request.open("get","https://raw.githubusercontent.com/rvsp/restcountries-json-data/master/res-countries.json")
request.send();
request.onload =function(){
    var result=JSON.parse(request.response);
   for(i=0;i<result.length;i++)
    {console.log(result[i].name+" "+result[i].region+" "+result[i].subregion+" "+result[i].population);
}
}
