# Learn from sayar eimaung php book

* https://eimaung.com

* My note

* Syntax, Variables & Data Types

```
<p>
 Total: 
    $num1 = 3;
    $num2 = 5;
    echo $num1 + $num2;
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
$hour = date('h') ?>
<p>
     if($hour < 6 || $hour > 18): ?>
        <b>Night Time</b>
     else: ?>
        <i>Day Time</i>
     endif ?>
</p>
```

* Variables

<code>
var_dump() က Variable ရဲ့ Data Type ကို ဖော်ပြယုံသာမက အထဲမှာရှိနေတဲ့ တန်ဖိုးကိုပါ ဖော်ပြပေးပါတယ်
</code>

```
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
$fruit = "Apple";
$price = 1.99;
echo "Buy some $fruit for \$$price each.";
// Buy some Apple for $1.99 each.
```

<code>
String တစ်ခုမှာ စာလုံးဘယ်နှစ်လုံးပါလဲဆိုတာ သိချင်ရင် strlen() Function
</code>

```
echo strlen("Hello World"); // 11
```
<code>
စာကြောင်းတစ်ကြောင်းကနေ လိုချင်တဲ့အပိုင်း ဖြတ်ယူချင်ရင် substr() Function
</code>

```
$str = "A quick brown fox.";
echo substr($str, 0, 7); // A quick
```

<code>
စာကြောင်းထဲမှာ Search & Replace လုပ်ချင်ရင် str_replace()
</code>

```
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
$user = [ "name" => "Alice", "age" => 22];
print_r($user);
// Array ( [name] => Alice [age] => 22 )
```

<code>
Array တစ်ခုရဲ့အတွင်းမှ ထပ်ဆင့် Array
</code>

```
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
$user = ["Alice", 22];
list($name, $age) = $user;
echo $name; // Alice
```

<code>
list() ကိုအသုံးပြုပြီး Array ထဲက တန်ဖိုးတွေကို Destructure လုပ်ပြီး Variable တွေရဲ့ တန်ဖိုးအဖြစ် လက်ခံလိုက်တာပါ 
PHP 7.1 ကနေစပြီး ဒီလိုရေးလို့လည်း ရသွားပါတယ်
</code>

```
$user = ["Alice", 22];
[ $name, $age ] = $user;
echo $name; // Alice
```

<code>
Associative Array ဆိုရင် အခုလိုရေးပေးဖို့ လိုအပ်ပါတယ်
</code>

```
$user = ["name" => "Alice", "age" => 22];
["name" => $name, "age" => $age] = $user;
echo $name; // Alice
```

<code>
Array Spread လုပ်ဆောင်ချက်
</code>

```
$nums1 = [1, 2];
$nums2 = [ ...$nums1, 3 ];
print_r($nums2);
// Array ( [0] => 1 [1] => 2 [2] => 3 )
```

<code>
Array တစ်ခုမှာပါဝင်တဲ့ Item အရေအတွက်ကိုသိချင်ရင် count() ကို အသုံးပြုနိုင်ပါတယ်
</code>

```
$nums = [1, 2, 3, 4];
echo count($nums); // 4
```

<code>
Variable တစ်ခုဟာ Array ဟုတ်မဟုတ် စစ်ချင်ရင် is_array() နဲ့စစ်နိုင်ပါတယ် 
ဟုတ်မှန်ရင် 1 ပြန်ပေးပြီး၊ မမှန်ရင် Empty ကို ပြန်ပေးပါတယ်
</code>

```
$users = ["alice", "bob"];
echo is_array($users); // 1
```

<code>
တန်ဖိုးတစ်ခု Array ထဲမှာ ပါမပါ သိချင်ရင် in_array() နဲ့ စစ်နိုင်ပါတယ် 
ဟုတ်မှန်ရင် 1 ပြန်ပေးပြီး၊ မမှန်ရင် Empty ကို ပြန်ပေးပါတယ်
</code>

```
$users = ["alice", "bob"];
echo in_array('bob', $users); // 1
```

<code>
array_search() က တန်ဖိုးရှိမရှိ စစ်ပေးယုံသာမက၊ ရှိတယ်ဆိုရင် အဲ့ဒီတန်ဖိုး ရှိနေတဲ့ Index ကို ပြန်ပေးပါတယ်
</code>

```
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
$input = "A quick brown fox.";
$arr = explode(" ", $input);
print_r($arr);
// Array ( [0] => A [1] => quick [2] => brown [3] => fox. )
$str = implode(" ", $arr);
echo $str;
// A quick brown fox.
```

* Operators & Control Structures

<code>
% သင်္ကေတကို အကြွင်းရှာဖို့သုံးပြီး 
** သင်္ကေတကို Exponent ရှာဖို့အတွက် သုံးပါတယ်
</code>

```
echo 5 % 3; // 2
echo 2 ** 3; // 8
```

* Assignment Operators

<code>
PHP မှာလည်း = Operator ကို တန်ဖိုးတွေ သတ်မှတ်ဖို့အသုံပြုပြီး 
+= ကို တန်ဖိုးတွေပေါင်းထည့်ဖို့ သုံးပါတယ်
အလားတူအနေနဲ့ -=, *=, /= Operator တွေလည်း ပါဝင်ပါသေးတယ်
</code>

```
$num = 3;
$num += 2;
echo $num; // 5
```

<code>
String တွေတွဲဆက်ထည့်သွင်းလို့ရတဲ့ .= Operator
</code>

```
$result = "Welcome";
$result .= " ";
$result .= "Bob";
echo $result; // Welcome Bob
```

<code>
လက်ရှိတန်ဖိုးကို 1 တိုးဖို့နဲ့ 1 နှုတ်ဖို့အတွက် ++ နဲ့ -- Operator
</code>

```
$x = 3;
$y = $x++; // $y => 3, $x => 4
```

<code>
$x ရဲ့ လက်ရှိတန်ဖိုး 3 ကို ++ နဲ့ 1 တိုးပြီး $y ထဲကို Assign လုပ်တဲ့အခါ ++ ကို
နောက်ကနေရေးတဲ့အတွက် အလုပ်အရင်လုပ်ပြီးမှ 1 တိုးပါတယ် ဒါကြောင့် $y တန်ဖိုး 3 $x တန်ဖိုးကတော့ 4 ဖြစ်နေတာပါ ++ ကိုရှေ့ကရေးမယ်ဆိုရင်
</code>

```
$x = 3;
$y = ++$x; // $y => 4, $x => 4
```

* Comparison Operators

<code>
တန်ဖိုးတွေ ညီမညီ နှိုင်းယှဉ်ဖို့အတွက် == ကို Equal Operator 
တန်ဖိုးတွေ မညီဘူးလား နှိုင်းယှဉ်ဖို့အတွက် != ကို Not Equal Operator 
ဒါမှမဟုတ် <> ကို Not Equal Operator အနေနဲ့ သုံးနိုင်ပါတယ်
Identical Equal Operator === နဲ့ Identical Not Equal Operator !== 
</code>

```
echo 5 == "5"; // 1
```

<code>
1 ဆိုတာ true ဆိုတဲ့အဓိပ္ပါယ်ဖြစ်ပါတယ် Integer 5 နဲ့ String "5" တို့ အမျိုး
အစား မတူပေမယ့် တူအောင်ညှိပြီးအလုပ်လုပ်သွားလို့ ညီတယ်လို့ ပြောနေတာပါ 
Identical Operator မှာတော့ Type ကိုတူအောင်မညှိဘဲ အရှိအတိုင်း နှိုင်းယှဉ်မှာ ဖြစ်ပါတယ်
</code>

```
echo 5 === "5"; //
```

<code>
တန်ဖိုးအကြီးအသေး နှိုင်းယှဉ်ဖို့အတွက် 
Less Than <, 
Greater Than >, 
Less Than Equal <=, 
Grater Than Equal >=
</code>

* Spaceship Operator

```
echo 3 <=> 5; // -1
echo 5 <=> 5; // 0
echo 5 <=> 3; // 1
```

* Logical Operators

<code>
! ကို NOT Operator,
&& ကို AND Operator, 
|| ကို OR Operator,
and ဆိုတဲ့ Keyword ကိုလည်း AND Operator အနေနဲ့ အသုံးပြုနိုင်ပြီး 
or ဆိုတဲ့ Keyword ကိုလည်း OR Operator အနေနဲ့ အသုံးပြုနိုင်ပါတယ်
</code>

```
$x = 3;
$y = 5;
echo $x === $y || $x === 3; // 1 (true)
echo $x === $y or $x === 3; // 1 (true)
echo $x === $y && $x === 3; // (false)
echo $x === $y and $x === 3; // (false)
echo !($x === $y and $x === 3); // 1 (true)
```

* XOR Operator

<code>
OR က နှိုင်းယှဉ်တန်ဖိုး နှစ်ခုမှာ တစ်ခုမှန်ရင် ရလဒ်မှန်သလို နှစ်ခုလုံးမှန်ရင်လည်း ရလဒ်မှန်ပါတယ် XOR ကတော့ နှိုင်းယှဉ်တန်ဖိုးနှစ်ခုမှာ တစ်ခု မှန်ရင် ရလဒ်မှန်ပြီး နှစ်ခုလုံးမှန်ရင် ရလဒ်မှားပါတယ်
</code>

```
$x = 3;
$y = 5;
echo $x < $y or $x === 3; // 1 (true)
echo $x < $y xor $x === 3; // (false)
```

* Ternary & Null Coalescing Operator

<code>
Ternary Operator က ပေးလိုက်တဲ့ ပထမဆုံး Expression ရဲ့ ရလဒ် true ဖြစ်ရင် ? နောက်က Expression ကို ဆက်လုပ်သွားမှာဖြစ်ပြီး false ဖြစ်ရင် : နောက်က Expression ကို ဆက်လုပ်သွားမှာ ဖြစ်ပါတယ်
</code>

```
$name = "";
echo $name ? $name : "Unknown"; // Unknown
$name = "Alice";
echo $name ? $name : "Unknown"; // Alice
```

<code>
အတိုကောက်ရေးထုံး
</code>

```
$name = "";
echo $name ?: "Unknown"; // Unknown
$name = "Alice";
echo $name ?: "Unknown"; // Alice
```

<code>
$name ကသာ ကြိုတင်ရှိမနေရင် Undefined variable Warning တက်ပါလိမ့်မယ်

</code>

```
echo $name ? $name : "Unknown";
// Warning: Undefined variable $name
echo $name ?: "Unknown";
// Warning: Undefined variable $name
```

<code>
isset() နဲ့ Variable ရှိမရှိ စစ်ပြီးမှ ရေးရင်တော့ ာ့ Undefined variable Warning မတက်ပါဘူး
</code>

```
echo isset($name) ? $name : "Unknown"; // Unknown
```

* Null Coalescing Operator

```
echo $name ?? "Unknown"; // Unknown
```

* Null Coalescing Assignment Operator

<code>
$result ရဲ့ မူလတန်ဖိုး Alice ဖြစ်ပြီး $name ရှိနေရင် $name တန်ဖိုးကို $result ထဲမှာ Assign လုပ်လိုက်ချင်တာပါ မရှိရင်တော့ Assign မလုပ်စေချင်ပါဘူး ဒါကြောင့် Null Coalescing
Assignment Operator ဖြစ်တဲ့ ??= ကို အသုံးပြုလိုက်တာပါ နမူနာအရ Assign လုပ်လိုက်ပေမယ့်
$name တန်ဖိုး မရှိတဲ့အတွက် မူလတန်ဖိုး Alice ကိုပဲ ဖော်ပြပေးလိုက်တာပါ

</code>

```
$result = "Alice";
$result ??= $name;
echo $result; // Alice
```

* Control Structures

<code>
if Statement
elseif Statement
</code>

```
$day = date("D");
if($day === "Sun") {
 echo "Today is Sunday.";
} elseif ($day === "Sat") {
 echo "Today is Saturday.";
} else {
echo "Today is a weekday.";
}
```

<code>
Switch Statement
</code>

```
$day = date("D");
switch($day) {
 case "Sat":
 case "Sun":
 echo "Weekend";
 break;
 case "Fri":
 echo "TGIF";
 break;
 default:
 echo "Weekday";
}
```

<code>
PHP 8 မှာ switch Statement နဲ့ဆင်တူတဲ့ match Expression ဖြည့်စွက် ပါဝင်လာပါတယ်
Expression ဖြစ်သွားတဲ့အတွက် Variable ထဲကို ထည့်လိုက်လို့ရ တာမျိုး အပါအဝင် ထူးခြားတဲ့ အသုံးပြုမှုမျိုးတွေနဲ့ သုံးလို့ရနိုင်သွားပါတယ် switch က တန်ဖိုးနှိုင်းယှဉ်ဖို့ == ကိုသုံးပြီး match က === ကိုသုံးတယ်ဆိုတာကိုလည်း သတိပြုပါ switch မှာ switch("5") လို့စစ်ထားရင် case 5 ကို အလုပ်လုပ်ပေးပါတယ် String "5" ကိုစစ်ထားပေမယ့် Integer 5 ဆိုရင်လည်း အလုပ်လုပ်ပေးမှာပါ match("5") လို့စစ်ထားရင်တော့ Int 5 => ကို အလုပ်လုပ်မှာ မဟုတ်ပါဘူး String "5" ကို စစ်ထားတဲ့အတွက် String "5" ကိုတွေ့မှသာ အလုပ်လုပ်မှာပါ
</code>

```
$day = date("D");
$result = match($day) {
 "Sat", "Sun" => "Weekend",
 "Fri" => "TGIF",
 default => "Weekday"
};
echo $result;
```

* continue Statement

<code>
ပေးထားတဲ့ ကိန်းဂဏန်းတွေထဲမှာ အနှုတ်ကိန်းပါရင် ထည့်မပေါင်းဘဲ ကျော်လိုက်စေချင်တယ်ဆိုရင် ဒီလိုရေးလို့ရပါတယ်
</code>

```
$nums = [12, 42, -2, 8, 621];
$i = 0;
$result = 0;
while($i < count($nums)) {
 if($nums[$i] < 0) {
 $i++;
 continue;
 }
 $result += $nums[$i];
 $i++;
}
echo $result; // 683
```

<code>
ပေးထားတဲ့ ကိန်းဂဏန်းတွေထဲမှာ အနှုတ်ကိန်းကိုတွေ့တာနဲ့ ရပ်လိုက် စေချင်ရင် အခုလိုရေးနိုင်ပါတယ် break နောက်ကနေ လိုအပ်ရင် Argument ထည့်ပေးလို့ရပါတယ် Default က 1 ဖြစ်ပါတယ် ဒါကြောင့် break; လို့ရေးလိုက်တာဟာ break 1; လို့ ရေးလိုက်တာနဲ့ အတူတူပါပဲ။ 1 လို့ပြောတဲ့အတွက် ကုဒ် Block တစ်ဆင့် ထွက်လိုက်မှာပါ။ အကယ်၍ နှစ်ဆင့်သုံးဆင့်ကျော်ပြီး ထွက်လိုက်ချင်ရင် break 2; တို့ break 3; တို့ကို အသုံးပြုနိုင်ပါတယ်။ continue မှာလည်း အလားတူပဲ လိုအပ်ရင် Argument ထည့်ပေးလို့ရပါတယ်
</code>

```
$nums = [12, 42, -2, 8, 621];
$i = 0;
$result = 0;
while($i < count($nums)) {
 if($nums[$i] < 0) break;
 $result += $nums[$i];
 $i++;
}
echo $result; // 54
```

<code>
do-while Statement ကတော့ အခြေခံအားဖြင့် while Statement နဲ့ အတူတူပါပဲ ကွာသွားတာက၊
ရိုးရိုး while Statement မှာ Condition စစ်ပြီး မှန်မှအလုပ်လုပ်ပြီး၊ do-while Statement မှာတော့ အလုပ်အရင်လုပ်ပြီး Condition ကိုနောက်မှ စစ်တဲ့အတွက်၊ ပထမဆုံးတစ်ကြိမ် Condition မှန်သည်ဖြစ်စေ မှားသည်ဖြစ်စေ အလုပ်လုပ်သွားမှာ ဖြစ်ပါတယ်။ ဒါကြောင့် Condition မှန်သည်ဖြစ်စေ မှားသည်ဖြစ်စေ ပထမဆုံးအကြိမ်တော့ မဖြစ်မနေ အလုပ်လုပ်ဖို့လိုတဲ့ ကုဒ်တွေမှာ while အစား do-while ကို အသုံးပြုနိုင်ပါတယ်
</code>

```
$nums = [12, 42, -2, 8, 621];
$i = 0;
$result = 0;
do {
 $result += $nums[$i];
 $i++;
} while($i < count($nums));
echo $result; // 681
```

<code>
for Statement ကိုတော့ Expression (၃) ခုကို Argument အနေနဲ့ ပေးပြီးရေးရပါတယ် ပထမဆုံး
Expression ကို စစချင်းတစ်ကြိမ် အလုပ်လုပ်ပါတယ် အလယ်က Expression ကတော့ Condition ဖြစ်
ပြီး မှန်မှ နောက်အကြိမ်တွေ ဆက်အလုပ်လုပ်မှာပါ နောက်ဆုံးက Expression ကိုတော့ Loop တစ်ကြိမ်
ပြီးတိုင်းတစ်ခါအလုပ်လုပ်ပေးမှာပဲ ဖြစ်ပါတယ်
</code>

```
$nums = [12, 42, -2, 8, 621];
$result = 0;
for($i = 0; $i < count($nums); $i++) {
 $result += $nums[$i];
}
echo $result; // 681
```

<code>
foreach Statement ကတော့ ပေးလိုက်တဲ့ Array ကို အစကနေအဆုံးထိ အလုပ်လုပ်သွားမှာမို့လို့ Condition တွေ ဘာတွေပေးစရာမလိုတော့ပါဘူး
</code>

```
$nums = [12, 42, -2, 8, 621];
$result = 0;
foreach($nums as $num) {
 $result += $num;
}
echo $result; // 681
```