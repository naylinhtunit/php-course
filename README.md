# Learn from sayar eimaung php book

* url = https://eimaung.com

* Syntax, Variables & Data Types

```
<p>
 Total: 
 <?php
    $num1 = 3;
    $num2 = 5;
    echo $num1 + $num2;
 ?>
</p>
```

<code>ဒီ Output Tag ကိုသုံးရင် echo Keyword ထည့်စရာ မလိုတော့ပါဘူး</code>

```
<?php
    $num1 = 3;
    $num2 = 5;
?>
<p>
    Total: <?= $num1 + $num2 ?>
</p>
```

<code>ဒီရေးနည်းကိုတော့ Template & Alternative Syntax ရေးထုံးလို့ ခေါ်ပါတယ်</code>

```
<?php $hour = date('h') ?>
<p>
    <?php if($hour < 6 || $hour > 18): ?>
        <b>Night Time</b>
    <?php else: ?>
        <i>Day Time</i>
    <?php endif ?>
</p>
```

* Variables

<code>var_dump() က Variable ရဲ့ Data Type ကို ဖော်ပြယုံသာမက အထဲမှာရှိနေတဲ့ တန်ဖိုးကိုပါ ဖော်ပြပေးပါတယ်</code>

```
<?php
    $var;
    var_dump($var); // Warning: Undefined Variable // NULL
    $var = 123;
    var_dump($var); // int(123)
    $var = "abc";
    var_dump ($var); // String(3) "abc"
```

* Globale Variable

```
$name = "Bob";
function hello() {
 echo $name;
}
hello(); // Warining: Undefined variable $namec
```

<code>Function က တိုက်ရိုက်ယူသုံးခွင့်မရှိလို့ Warning တက်တာ ကို တွေ့ရမှာ ဖြစ်ပါတယ် သုံးချင်တယ်ဆိုရင် သုံးချင်တဲ့အကြောင်း ကြိုပြောပေးရပါတယ်</code>

```
$name = "Bob";
function hello() {
    global $name;
    echo $name;
}
hello(); // Bob
```

<code>Variable တွေရှိမရှိ စစ်ချင်ရင် isset() ကိုအသုံးပြုပြီး စစ်နိုင်ပါတယ် ရှိရင် true အနေနဲ့ 1 ကိုပြန်ပေးပြီး မရှိရင်တော့ false အနေနဲ့ Empty ကို ပြန်ပေးပါတယ်</code>

```
<?php
echo isset($name); // Empty
$name = "Bob";
echo isset($name); // 1
```

<code>Constant တွေကို define() Function သုံးပြီး ကြေညာပေးရပါတယ်  $ သင်္ကေတပါစရာ မလိုအပ်ပါ define() Function ရဲ့ ပထမ Argument မှာ Constant ရဲ့အမည်ကိုပေးရပြီး ဒုတိယ Argument မှာ တန်ဖိုးကိုပေးပါ Assignment Operator = ကို Constant နဲ့အတူ တွဲပြီး အသုံးပြုခွင့်ပေးမှာမဟုတ်ပါ</code>

```
<?php
define("MIN", 1);
define("MAX", 10);
echo MAX; // 10
MAX = 20; // Syntax Error: unexpected =
```

* Strings & Arrays

<code>Escape လုပ်ဖို့လိုတဲ့ Character တွေကို \ သင်္ကေတနဲ့ Escape လုပ်နိုင်ပါတယ်</code>

```
<?php
$fruit = "Apple";
$price = 1.99;
echo "Buy some $fruit for \$$price each.";
// Buy some Apple for $1.99 each.
```

<code>String တစ်ခုမှာ စာလုံးဘယ်နှစ်လုံးပါလဲဆိုတာ သိချင်ရင် strlen() Function ကို သုံးနိုင်ပါတယ်</code>

```
<?php
echo strlen("Hello World"); // 11
```
<code>စာကြောင်းတစ်ကြောင်းကနေ လိုချင်တဲ့အပိုင်း ဖြတ်ယူချင်ရင် substr() Function ကို သုံးနိုင်ပါတယ်</code>

```
<?php
$str = "A quick brown fox.";
echo substr($str, 0, 7); // A quick
```

<code>စာကြောင်းထဲမှာ Search & Replace လုပ်ချင်ရင် str_replace() ကို သုံးနိုင်ပါတယ်</code>

```
<?php
$str = "Come here, quick, quick.";
echo str_replace("quick", "hurry", $str);
// Come here, hurry, hurry.
```

* Array
* Numeric Array 

<code> ထူးခြားချက်အနေနဲ့ echo ကို သုံးပြီး Array တွေကို ဖော်ပြခိုင်းလို့ မရတာကို သတိပြုပါ var_dump() က Data Type တွေကိုပါ ထည့်ပြလို့၊ ဖော်ပြတဲ့အချက်အလက် ပိုပြည့်စုံပါတယ် Array ထဲမှာ ရှိတာကိုပဲ ခပ်ရှင်းရှင်း ကြည့်ချင်တယ်ဆိုရင် print_r() ကိုသုံးနိုင်ပါတယ်</code>

```
<?php
$users = array("Alice", "Bob");
$fruits = ["Apple", "Orange"];
echo $users;
// Warning: Array to string conversion
// Array
print_r($fruits);
// Array ( [0] => Apple [1] => Orange )
var_dump($fruits);
array(2) { [0]=> string(5) "Apple" [1]=> string(6) "Orange" }
```

* Associative Array

```
<?php
$user = [ "name" => "Alice", "age" => 22];
print_r($user);
// Array ( [name] => Alice [age] => 22 )
```

<code>Array တစ်ခုရဲ့အတွင်းမှာ ထပ်ဆင့် Array တွေလည်း ရှိနိုင်ပါတယ်</code>

```
<?php
$users = [ 
["name" => "Alice", "age" => 22],
["name" => "Bob", "age" => 23],
["name" => "Tom", "age" => 24],
];
print_r($users);
```

<code>Array ထဲက တန်ဖိုးတစ်ခုကို ရယူလိုရင်တော့ သက်ဆိုင်ရာ Index နဲ့ထောက်ပြီး ရယူနိုင်ပါတယ်</code>

```
<?php
$users = [ 
["name" => "Alice", "age" => 22],
["name" => "Bob", "age" => 23],
["name" => "Tom", "age" => 24],
];
print_r( $users[0] );
// Array ( [name] => Alice [age] => 22 )
echo $users[0]['name'];
// Alice
```

<code>Array တန်ဖိုးတွေ ထပ်တိုးသတ်မှတ်လိုရင်လည်း ဒီနည်းအတိုင်းပဲ ထပ်တိုးသတ်မှတ်နိုင်ပါတယ်</code>

```
<?php
$fruits = ['Apple', 'Orange'];
$fruits[4] = 'Mango';
print_r($fruits);
// Array ( [0] => Apple [1] => Orange [4] => Mango )
```