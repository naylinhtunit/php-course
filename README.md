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

<code>
Output Tag ကိုသုံးရင် echo Keyword ထည့်စရာ မလိုတော့ပါဘူး
</code>

```
<?php
    $num1 = 3;
    $num2 = 5;
?>
<p>
    Total: <?= $num1 + $num2 ?>
</p>
```

<code>
Template & Alternative Syntax ရေးထုံး
</code>

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

<code>
var_dump() က Variable ရဲ့ Data Type ကို ဖော်ပြယုံသာမက အထဲမှာရှိနေတဲ့ တန်ဖိုးကိုပါ ဖော်ပြပေးပါတယ်
</code>

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

<code>
Function က တိုက်ရိုက်ယူသုံးခွင့်မရှိလို့ Warning တက်တာ ကို တွေ့ရမှာ ဖြစ်ပါတယ်
သုံးချင်တယ်ဆိုရင် သုံးချင်တဲ့အကြောင်း ကြိုပြောပေးရပါတယ်
</code>

```
$name = "Bob";
function hello() {
    global $name;
    echo $name;
}
hello(); // Bob
```

<code>
Variable တွေရှိမရှိ စစ်ချင်ရင် isset() ကိုအသုံးပြုပြီး
ရှိရင် true အနေနဲ့ 1 ကိုပြန်ပေးပြီး မရှိရင်တော့ false အနေနဲ့ Empty ကို ပြန်ပေးပါတယ်
</code>

```
<?php
echo isset($name); // Empty
$name = "Bob";
echo isset($name); // 1
```

<code>
Constant တွေကို define() Function သုံးပြီး ကြေညာပေးရပါတယ်  
$ သင်္ကေတပါစရာ မလိုအပ်ပါ 
define() Function ရဲ့ ပထမ Argument မှာ Constant ရဲ့အမည်ကိုပေးရပြီး
ဒုတိယ Argument မှာ တန်ဖိုးကိုပေးပါ Assignment Operator = ကို Constant နဲ့အတူ တွဲပြီး အသုံးပြုခွင့်ပေးမှာမဟုတ်ပါ

</code>


```
<?php
define("MIN", 1);
define("MAX", 10);
echo MAX; // 10
MAX = 20; // Syntax Error: unexpected =
```

* Strings & Arrays

<code>
Escape လုပ်ဖို့လိုတဲ့ Character တွေကို \ သင်္ကေတနဲ့ Escape လုပ်နိုင်ပါတယ်
</code>

```
<?php
$fruit = "Apple";
$price = 1.99;
echo "Buy some $fruit for \$$price each.";
// Buy some Apple for $1.99 each.
```

<code>
String တစ်ခုမှာ စာလုံးဘယ်နှစ်လုံးပါလဲဆိုတာ သိချင်ရင် strlen() Function
</code>

```
<?php
echo strlen("Hello World"); // 11
```
<code>
စာကြောင်းတစ်ကြောင်းကနေ လိုချင်တဲ့အပိုင်း ဖြတ်ယူချင်ရင် substr() Function
</code>

```
<?php
$str = "A quick brown fox.";
echo substr($str, 0, 7); // A quick
```

<code>
စာကြောင်းထဲမှာ Search & Replace လုပ်ချင်ရင် str_replace()
</code>

```
<?php
$str = "Come here, quick, quick.";
echo str_replace("quick", "hurry", $str);
// Come here, hurry, hurry.
```

* Array

* Numeric Array 

<code>
ထူးခြားချက်အနေနဲ့ echo ကို သုံးပြီး Array တွေကို ဖော်ပြခိုင်းလို့ မရတာကို သတိပြုပါ var_dump() က Data Type တွေကိုပါ ထည့်ပြလို့၊ ဖော်ပြတဲ့အချက်အလက် ပိုပြည့်စုံပါတယ် 
Array ထဲမှာ ရှိတာကိုပဲ ခပ်ရှင်းရှင်း ကြည့်ချင်တယ်ဆိုရင် print_r() ကိုသုံးနိုင်ပါတယ်
</code>

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

<code>
Array တစ်ခုရဲ့အတွင်းမှ ထပ်ဆင့် Array
</code>

```
<?php
$users = [ 
["name" => "Alice", "age" => 22],
["name" => "Bob", "age" => 23],
["name" => "Tom", "age" => 24],
];
print_r($users);
```

<code>
Array ထဲက တန်ဖိုးတစ်ခုကို ရယူလိုရင်တော့ သက်ဆိုင်ရာ Index နဲ့ထောက်ပြီး ရယူနိုင်ပါတယ်
</code>

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

<code>
Array တန်ဖိုးတွေ ထပ်တိုးသတ်မှတ်လိုရင်
</code>

```
<?php
$fruits = ['Apple', 'Orange'];
$fruits[4] = 'Mango';
print_r($fruits);
// Array ( [0] => Apple [1] => Orange [4] => Mango )
```

<code>
Array ထဲကို တန်ဖိုးတွေ ထပ်တိုးသတ်မှတ်တဲ့အခါ ကိုယ့်ဘာသာ Index နံပါတ် မပေးတော့ဘဲ၊ သူ့အလိုအလျှောက် ထပ်တိုးပြီး ထည့်သွားအောင်လည်း ရေးလို့ရပါတယ်
</code>

```
$fruits = ['Apple', 'Orange'];
$fruits[] = 'Mango';
print_r($fruits);
// Array ( [0] => Apple [1] => Orange [2] => Mango )
```

<code>
PHP မှာ မူလကတည်းက Array Destructuring ရေးဟန် ပါဝင်ပြီး နောက်ပိုင်း Version တွေမှာ Array Spread လုပ်ဆောင်ချက်လည်း ပါဝင်လာပါတယ်
</code>

```
<?php
$user = ["Alice", 22];
list($name, $age) = $user;
echo $name; // Alice
```

<code>
list() ကိုအသုံးပြုပြီး Array ထဲက တန်ဖိုးတွေကို Destructure လုပ်ပြီး Variable တွေရဲ့ တန်ဖိုးအဖြစ် လက်ခံလိုက်တာပါ 
PHP 7.1 ကနေစပြီး ဒီလိုရေးလို့လည်း ရသွားပါတယ်
</code>

```
<?php
$user = ["Alice", 22];
[ $name, $age ] = $user;
echo $name; // Alice
```

<code>
Associative Array ဆိုရင် အခုလိုရေးပေးဖို့ လိုအပ်ပါတယ်
</code>

```
<?php
$user = ["name" => "Alice", "age" => 22];
["name" => $name, "age" => $age] = $user;
echo $name; // Alice
```

<code>
Array Spread လုပ်ဆောင်ချက်
</code>

```
<?php
$nums1 = [1, 2];
$nums2 = [ ...$nums1, 3 ];
print_r($nums2);
// Array ( [0] => 1 [1] => 2 [2] => 3 )
```

<code>
Array တစ်ခုမှာပါဝင်တဲ့ Item အရေအတွက်ကိုသိချင်ရင် count() ကို အသုံးပြုနိုင်ပါတယ်
</code>

```
<?php
$nums = [1, 2, 3, 4];
echo count($nums); // 4
```

<code>
Variable တစ်ခုဟာ Array ဟုတ်မဟုတ် စစ်ချင်ရင် is_array() နဲ့စစ်နိုင်ပါတယ် 
ဟုတ်မှန်ရင် 1 ပြန်ပေးပြီး၊ မမှန်ရင် Empty ကို ပြန်ပေးပါတယ်
</code>

```
<?php
$users = ["alice", "bob"];
echo is_array($users); // 1
```

<code>
တန်ဖိုးတစ်ခု Array ထဲမှာ ပါမပါ သိချင်ရင် in_array() နဲ့ စစ်နိုင်ပါတယ် 
ဟုတ်မှန်ရင် 1 ပြန်ပေးပြီး၊ မမှန်ရင် Empty ကို ပြန်ပေးပါတယ်
</code>

```
<?php
$users = ["alice", "bob"];
echo in_array('bob', $users); // 1
```

<code>
array_search() က တန်ဖိုးရှိမရှိ စစ်ပေးယုံသာမက၊ ရှိတယ်ဆိုရင် အဲ့ဒီတန်ဖိုး ရှိနေတဲ့ Index ကို ပြန်ပေးပါတယ်
</code>

```
<?php
$users =["tom", "bob", "alice"];
echo array_search("alice", $users); // 2
```

<code>
Array ရဲ့နောက်ဆုံးကနေ တန်ဖိုး ထပ်တိုးချင်ရင် array_push() ကိုသုံးပါ 
နောက်ဆုံးက တန်ဖိုးကို ပယ်ဖျက်ချင်ရင် array_pop() ကိုသုံးပါ 
ရှေ့ဆုံးကနေ တန်ဖိုးထပ်တိုးချင်ရင် array_unshift() ကိုသုံးပါ 
ရှေ့ဆုံးကတန်ဖိုးကို ဖျက်ချင်ရင် array_shift() ကိုသုံးပါ
</code>

```
<?php
$users =["alice", "bob"];
array_push($users, "tom");
print_r($users); // ["alice", "bob", "tom"]
array_pop($users);
print_r($users); // ["alice", "bob"]
```

<code>
Array ထဲက တစ်ချို့အပိုင်းတွေကို ဖယ်ထုတ်/ထုတ်ယူ လိုရင် array_splice()
</code>

```
<?php
$users =["tom", "bob", "alice"];
$result = array_splice($users, 1, 1);
print_r($users); // Array ( [0] => tom [1] => alice )
print_r($result); // Array ( [0] => bob ) 
```

<code>
Array ရဲ့ Index တွေချည်းလိုချင်ရင် array_keys()
Array ရဲ့ Value တွေချည်းလိုချင်ရင် array_values()
</code>

```
<?php
$user =["name" => "alice", "age" => 22];
$keys = array_keys($user);
$vals = array_values($user);
print_r($keys);// Array ( [0] => name [1] => age )
print_r($vals);// Array ( [0] => alice [1] => 22 )
```

<code>
Array ကို Value နဲ့ Sorting စီချင်ရင် sort()
Array ကို ပြောင်းပြန်စီချင်ရင် rsort()
Array ကို Index နဲ့ စီရင်တော့ ksort()
Array ကို Index နဲ့ ပြောင်းပြန်စီချင်ရင် krsort()
</code>

```
<?php
$users =["tom" => 23, "bob" => 22, "alice" => 24];
sort($users);
print_r($users);
// Array ( [0] => 22 [1] => 23 [2] => 24 )
$users =["tom" => 23, "bob" => 22, "alice" => 24];
ksort($users);
print_r($users);
// Array ( [alice] => 24 [bob] => 22 [tom] => 23 )
```

<code>
String တစ်ခုမှာပါတဲ့ Character တွေ Word တွေ ကိုခွဲထုတ်ပြီး
Array အနေနဲ့လိုချင်ရင် explode() 
အပြန်အလှန်အားဖြင့် Array တန်ဖိုးတွေကို ပေါင်းစပ်ပြီး String အနေနဲ့ လိုချင်ရင်
implode()
</code>

```
<?php
$input = "A quick brown fox.";
$arr = explode(" ", $input);
print_r($arr);
// Array ( [0] => A [1] => quick [2] => brown [3] => fox. )
$str = implode(" ", $arr);
echo $str;
// A quick brown fox.
```