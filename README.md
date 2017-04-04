# 29.03.2017
<b>3.Can you use x === “object” to test if x is an object?</b>
Bu sualin cavabi qisa olaraq olmazdir. 
Bunu test etək ücun bir x obyekti yaradiriq və muqaise edirik.

x={};
console.log(x==="object") // false 
a={
  ad:Murad,
  Soyad:Bineliyev};
b={
  ad:Murad,
  soyad:Bineliyev}

console.log(a===b); // false;

Bunun sebebi odurki yazdigimiz kod run olunanda orada sadece deyisenler yaddasda yer tutur, biz muqaise operatorlari ile muqaise etmek isteyende sadece deyisen kimi gorur. 
Bunun usulu typeof metodundan istifade etmekdir cunki typeof metodu deyisenin tipini qaytara bilir. Qaytardigi deyer ise string olur. Buda o demekdirki biz rahatliqla compare (===) operatorundan rahatliqla istifade ede bilerik.

console.log(typeof x === "object"); // true;
<br>
<b>4.What happens when you don’t declare a variable in Javascript?
</b>
<pre>
Javascriptde 2 cur deyisen teyin etmek usulu var. 
1.Local - funlsiyanin ve ya obyectin icinde var ile qlobal variable teyin edilir. Bu o demekdirki bu deyiseni funksiyanin qiraqinda teyin etmek olmur 
2. Qlobal- qlobalda var -la veya funksiya, obyectin icinde varsiz teyin ede bilerik. qlobal deyisen o demekdirki sehfede istediyimiz yerde cagira bilerik.
Declare variable odurki deyisen teyin olunub hec bir deyer mensub edilmiyib. Bu deyisenler yaddasda yer tutmur, undifined qaytarir. 
  var x ; 
  conlole.log(x);//undifined
</pre>
<b>5.What is the difference between == and === ? </b>
javascriptde muqaise(sert) operatorlari varlirdir. 
"==" beraberdir
"!=" beraber deyil
"<=" kicikdir beraberdir
">=" boyukdur beraberdir
"==="  hem tipi hemde deyisen beraberdir 

== ve === ferqleri.
Javascriptde == sadece deyeri yoxlayiriq 
"1"==1 // true
burada sag terefde string olaraq 1 sol terefde ise nubber tipi olaraqdan 1  menimsediriq ve her ikiside 1 oldugundan neticede true aliriq.
"1"===1 //false 
burada sag teref string sol teref ise nubberdir. === isare hem tipi hemde deyeri yoxladigi ucun deyerler 1 olduguna baxmayaraq tipler ferqli oldugu ucun bize false qaytarir . 
bu usul  bir cox dillerde yoxdur. imperative paradiqmalarda her ince detalin bele bir datatipi oldugu ucun hec ehtiyacda duyulmur cunki onlarda bawqa tiplerde olan deyisenleri muqaise etmek olmur. script dillerde === usuluna ehtiyac duyur 

<b> 6. What datatypes are supported in Javascript?</b>
<pre>
Javascript dilinde esas 3 eded datatipi var. bular asagidakilardir:
  String-"salam",'dunya',necesen
  Number - 1, 2.3 ve s. 
  boolean - 0, 1 , true, false.
elave olaraq null ve undifained tipleri var. Bunlar barede etrafli aciqlamani 9-cu sualda aciqlayacagam.
bunlardan bawqa :
array-[1,"salam", true,..];
object - {
  ad:murad,
  soyad: bineliyev}
function(){
  a=5;
  b=10; 
  return a*b;}
  </pre>
  <br>
  <b> 7.What would “1”+2+3 and 1+2+“3” evaluate to, respectively?</b>
  <pre>
    "1"+2+3 ifadesinin neticesi "123" -dur. Javascript de "+" isaresi stringde qosucu rolunu oynayir. buna gorede 1 ci ifade string oldugundan hamisini sringe cevirir. ve "+" isaresi ancaq qowucu rolunu oynayir.
    1+2+"3" ifadesin neticesi 33 dur. Ustegel isaresi ilk iki reqemi number oldugu ucun toplayir sonuncu reqemi ise string oldugu ucun yapisdirir.
    bu qayda riyazi emeliyeatlardan sadece '+' isaresine aiddir. diger riyazi operatorlar string oldugunda numbere convert etmeye caliwir ede bilirse riyazi hesablama aparir bilmirse NaN qaytarir.
    '12'/3 netice 4;
    12/'q' netice NaN
  </pre>
  <br>
  <b>9.What is the difference between a null value and an undefined value?</b>
  <pre>
  Null sadece bos oldugunu bildirir datatype object qaytarir. yaddasda yer tutur.
  her hansisa deyisene teyin edirikse deyisen andifined olmagdan cixir ve null olur; 
  deyisene teyin olundugunda deyiseninde tipini obyect edir .
  a= null;
  console.log(a)//null
  console.log(typeof a)//object
  undifined - yaddasda yer tutmur deyisen verilib deyer verilmiyende o undifined qaytarir.
  datatipide undifineddir. 
  muqaise:
  undifined==null;//true
  undifined===null;//false
  
 </pre>
 <br>
 <b>Which conditional statements will JavaScript support?
</b>

