# ECMAScript 6 Özet #

	* let ve const anahtar kelimeleri ES6 ile gelmiştir. "var" ile olan farkları "global scope" yerine "block scope" olmalarıdır. Yani "{}" arasındaki bölgelerde anlam taşırlar.

```js
let i = 10;
console.log(i);   //Output 10

const PI = 3.14;
console.log(PI);  //Output 3.14
```
########################################################################################################################################################################

	* Dikkat etmek gerekir ki const ile tanımlanan değişkenler daha sonradan değiştirilemezler ancak bunun da belli şartları vardır. Eğer const ile bir liste tanımlar ve belli bir indisini hedef alarak değiştirme yaparsanız bu işlem gerçekleşebilir.

```js
const s = [5, 6, 7];
s = [1, 2, 3];
s[2] = 45;
console.log(s);
```
########################################################################################################################################################################

	* Ok fonksiyonları (Arrow Functions), "function" ve "return" anahtar kelimelerini ortadan kaldırır. Daha kısa ve öz bir syntax (sözdizimi) kullanarak fonksiyon tanımlanmasına olanak tanır.

```js
// Arrow function
let sumOfTwoNumbers = (a, b) => a + b;
console.log(sum(10, 20)); // Output 30

```
########################################################################################################################################################################

	* Ok fonksiyonları şişman ok notasyonu (=>) ile tanımlanır. Eğer fonksiyonun tek parametresi varsa parantez kullanımı şart değildir ancak sıfır ya da daha fazla parametresi varsa parantez kullanımı gereklidir.

	* Eğer fonksiyon birden fazla ifade içeriyorsa "{}" ile fonksiyonu sararak "return" kullanmak gereklidir.

	* Çok satırlı string ifadeler backtick (``) kullanılarak tanımlanabilir. Bu şekilde yeni satırlar da stringlere tanımlanır.

```js

let greeting = `Hello World,     
                Greetings to all,
                Keep Learning and Practicing!`
```
########################################################################################################################################################################

	* Standart Parametreler (Default Parameters), fonksiyonlara girilecek parametrelere sabit değerler atayarak çağırılırken parametrelerde girdi olmaması durumunda daha önceden tanımlanan bu değerlerle çalışmasını sağlar. ES5'te bu durum için "veya" ("||") operatörü kullanılmaktaydı.

```js
//ES6
let calculateArea = function(height = 100, width = 50) {  
    // logic
}

//ES5
var calculateArea = function(height, width) {  
   height =  height || 50;
   width = width || 80;
   // logic
}

```
########################################################################################################################################################################

	* Şablon değişmezler (Template Literals), basit şablon yapıda bir string ile yer tutucu (placeholder) kullanımını kapsar. Sözdizim (syntax) kullanımı; "${Kelime}" şeklindedir ve backtick (``) içerisinde kullanılır.

```js
let name = `My name is ${firstName} ${lastName}`

```
########################################################################################################################################################################

	* Yıkım Tanımlaması (Destructuring Assignment), basit bir şekilde dizilerden veri veya nesnelerden özellik çekmeye yarayan ve bunları başka değişkenlere atamayı sağlayan ifade biçimidir. 

	* İsmen iki türü vardır: Nesne Yıkımı (Object Destructuring) ve Dizi Yıkımı (Array Distructuring)


```js
//Array Destructuring
let fruits = ["Apple", "Banana"];
let [a, b] = fruits; // Array destructuring assignment
console.log(a, b);

//Object Destructuring
let person = {name: "Peter", age: 28};
let {name, age} = person; // Object destructuring assignment
console.log(name, age);

```
########################################################################################################################################################################

	* ES6, Geliştirilmiş Nesne Tanımı ile kolay bir şekilde nesne tanımlamaya olanak tanır.

```js
function getMobile(manufacturer, model, year) {
   return {
      manufacturer,
      model,
      year
   }
}
getMobile("Samsung", "Galaxy", "2020");

```
########################################################################################################################################################################

	* Sözler (Promises), asenkron uygulamalar için kullanılır. Ok fonksiyonları ile birlikte aşağıdaki gibi kullanılırlar.



```js
var asyncCall =  new Promise((resolve, reject) => {
   // do something
   resolve();
}).then(()=> {   
   console.log('DON!');
})

```
########################################################################################################################################################################

	* Sınıflar (Classes), önceden JS ortamında mevcut değillerdi. Diğer nesneye yönelik programlama (OOP) dillerindeki örneklerine benzer şekildedir ama tam olarak aynı şekilde çalışmazlar. ES6 sınıfları daha kolay bir şekilde nesne oluşturur ve "extends" anahtar anahtar sözcüğünü kullanarak kalıtım uygular ve ayrıca kodu verimli bir şekilde yeniden kullanır.

```js
class UserProfile {   
   constructor(firstName, lastName) { 
      this.firstName = firstName;
      this.lastName = lastName;     
   }  
    
   getName() {       
     console.log(`The Full-Name is ${this.firstName} ${this.lastName}`);    
   } 
}
let obj = new UserProfile('John', 'Smith');
obj.getName(); // output: The Full-Name is John Smith

```
########################################################################################################################################################################

	* ES5'te modül desteği mevcut değildi. ES6 ile modül olarak adlandırılan ayrı .js uzantılı dosyaların kullanımı bizlere sunuldu. "import" ve "export" ifadeleri ile değişkenler, fonksiyonlar, sınıflar ve herhangi bir komponenti aynı şekilde bir başka komponente entegre ederek kullanmamızı sağlar.

```js
export var num = 50; 
export function getName(fullName) {   
   //data
};

```

```js
import {num, getName} from 'module';
console.log(num); // 50
``` 
