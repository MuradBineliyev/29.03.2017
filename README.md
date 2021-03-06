# 29.03.2017
<b>1.Describe an instance of prototypal inheritance in JavaScript?
</b>
<pre>
function Dog() {
}
Dog.prototype.bark = function() {
 console.log(‘woof!’);
};
var fido = new Dog();
fido.bark(); // ‘woof!’

Bu misalda fido-nun bark adlanan bir metodu yoxdur. Lakin, new decleration-u vasitəsilə burada prototype chain yaranır. Fido.bark() yazdıqda isə JS fido-da bark metodun axtarmır, onu Dog funksiyasından götürür.
Real olaraq, belə bir funksiya yazaraq yuxaırda göstərilənləri aydınlaşdırmaq olar:
Function Rectangle(width, height
){
this.width=width;
this.height=height;
}
Var rect = new Rectangle(3,4);
Rectangle.prototype.area = function(){
Return.this.width*this.height
};
Rect.area()//12
Burda baş verənləri aydınlaşdırsaq, Rectangle adında bir konstruktor funksiyamız var, və onun 2arqumenti var, this. deklarasiyası ilə arqumentləri götürüb yeni width, height properity-lər yaradırıq ki, bu da bizə sonradan prototype vasitəsilə bunlardan istifaəd edərək yeni object yaratmağa imkan verir. This decleration-u bizə imkan verir ki, bizə lazım olan arqumentləri götürüb istifadə edə bilək, və iki funksiya arasında əlaqə yaradır. Prototype-a baxsaq burada return görərəik ki, bu da konstruktor funksiyadakı this vasitəsilə gpötürdüyümüz arqumentləri bizə qaytarır.
</pre>
<br>
<b>2.What are closures and how are they used?</b>
<br>
Funksiyaya her hansi bir argument otururuk ve onun ve funksiyanin icinde birdenede funksiya aciriq  bu funksiya  clouserin mentiqidir.  Bu xususiyyet obyeklerede aitdir;
<pre>
var a=10; // qlobal deyisen
function first(b){
var a =4;//local deyisen
  return function second(c){
  a+=b;
  console.log(a);
  
  }
  a++
}
first(second(5));
</pre>
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
 <b>10.Which conditional statements will JavaScript support?
</b>
<br>
<pre>
Javascriptde sert funksiyalari asagidakilardir:
  1. if-> if(sert){ emlyat} -> eger sert truedirse emeliyyet icra olunur eks halda ise uzerinden kecilir.
  2. else if-> else if(sert){ emliyyat} -> bezen bize bir nece dene sert vermeli oluruq bu zaman birinci ifden sonra else if isledilir.
  3.else-> else{emeliyyat} -> elsden qabaq gelen ifin(iflerin) serti odenilmedikde elsde olan emeliyyat icra olunur.
  4. switch case ->
  switch(argument){
    case 0: emelyat;
    break;
    case 1: emelyat1;
    break;
    case 2: emelyat2;
    break;
    case 3: emelyat3;
    } -> 
   Bu operotor argunti yoxlayir ve argumente gore casede olan emeliyyati icra edir;
   </pre>
   <br>
   <b> 11.What is NaN</b>
   <br>
   <pre>
    mueyyen riyazi emelyatlar icra oluna bilmedikde NaN deyeri qaytarir. sonsuzlugada ise infinity
    buna misal olaraq edein 0 a bolunmesinden NaN 
    strin ve namber uzerinde riyazi emelyatlar icra etdikde NaN deyeri qaytarir;
    "a"/2;//NaN
    3/00 ;//infinity
    
   </pre>
   <br>
   <b> 12.Explain the meaning of the keyword ‘this’ in JavaScript functions</b>
   <br>
   <pre>
   this keywordu funksiyanin yerini gosterir. bizim buyun kodlarimiz window objectinde oldugu ucun funksiyanin icinde yazanda window obyectinin icinde funksiyaya aid olan propertyleri cixardir.
   event funksiyalarinda click olunan obyecti qaytari.
   </pre>
   <br>
   <b> 13.What is the difference between undefined and not defined in JavaScript?</b>
   <br>
   <pre>
   Undifined - deyisen teyin olunub amma hec bir deyer verilmiyib. Bu barede 9 - cu sualda etrafliaciqlama vermisem.
   Not defined - umumiyyetce teyin etmediyimiz bir deyisen var ve onu istifade edirik.
   Buna misal: 
   Tutaqki bizim proyektimizde a dan hec bir yerde istifade etmemisik ve her hardasa lokal deyisendir biz bunu cagirdigimizda qarsimiza eror cixacaq. Bu hadisenin bas vermesi note difaint adlanir yeni scope de teyin olunmuyub 
   fuction myFun(){ 
   var a =;
   console.log(a);//undifined 
   }
   console.log(a)//not defined
   </pre>
   <br>
   <b>14What is function hoisting in JavaScript?</b>
   <br>
   <pre>
   Bizim kod browzer terefinden oxunanda ilk olara deyisenleri scopba undifined olaraq yazir ondan sonra funsiyalari oxuyaraq yazir . Deyisenler deyer verdiyimiz setir run olunana geder undifined olur , hemin setirden sonra ise verdiyimiz deyeri dasiyir
   Bizim kodda funksiyalari, obyect ve ya deyisenleri cagirdigimiz yerler hoisting mentiqi gedir. Funksiyalar istenilen sutunda cagrildiginda isleyir amma deyisenler undifined olur . 
   mis :
   var a = 5;
   b();// undifined
   fubction b(){
    console.log(c);
   }
   b()//undifined
   var c = 10;
   b();//10
   </pre>
   <br>
   <b> 15.Can you name two programming paradigms important for JavaScript app developers?
</b>
<br>
<pre>
  JavaScript dili paradigma dillerinden scripting, object-oriented (prototype-based), imperative, functional istifade edir.
    funksional paradigmani 16 - ci sualda aciqlamisam.
    OOP(prototype - base) - javascriptde OOP istifadesi en cox prototyp mentiqinde hiss olunur . Bizim ozumuzun obyectimizi , classlarimizi yaradaraq bir biri ile elaqelendirmemiz rahatliqla basqa yerde istifade etmemiz OOP paradigmasinin esasinda olur.
    Scripting - esas temeli script basdir. fayllara mudaxile ede bilmemeyi buradan ireli gelir . Standartlari ECMA standarti oldu bunun aciqlamasidir.
    Imperativ - bu paradigma ise datatyp larla islemesi buna nianedir.
</pre>
   <br>
   <b>16.What is functional programming? </b>
   <br>
   <pre>
   Programlasdirma paradiqmalardan biride funksional paradiqmadir. Bu paradiqma demek olarki bututn programlawdiram dillerinde tetbiq olunur. 
   kod tekrarini aradan qaldirmaq ucun funksiya yaziriq elazim olan yerde sadece cagiririq.
   bu paradigmainin bize verdiyi rahatliqlar: 
    Kodun oxunarligi.
    Argumentlerin rahat istifadesi ve s.
   mis:
        function name(arg, arg1){
          console.log(arg);
          return arg1;
        }
   </pre>
<br>
 <b>16.What is the difference between classical inheritance and prototypal inheritance?
</b>
<pre>

</pre>
