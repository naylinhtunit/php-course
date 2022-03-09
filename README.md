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

* Output Tag ကိုသုံးရင် echo Keyword ထည့်စရာ မလိုတော့ပါဘူး

```
<?php
    $num1 = 3;
    $num2 = 5;
?>
<p>
    Total: <?= $num1 + $num2 ?>
</p>
```

* Template & Alternative Syntax ရေးထုံး

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

* var_dump() က Variable ရဲ့ Data Type ကို ဖော်ပြယုံသာမက အထဲမှာရှိနေတဲ့ တန်ဖိုးကိုပါ ဖော်ပြပေးပါတယ်

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

* Function က တိုက်ရိုက်ယူသုံးခွင့်မရှိလို့ Warning တက်တာ ကို တွေ့ရမှာ ဖြစ်ပါတယ်
* သုံးချင်တယ်ဆိုရင် သုံးချင်တဲ့အကြောင်း ကြိုပြောပေးရပါတယ်

```
$name = "Bob";
function hello() {
    global $name;
    echo $name;
}
hello(); // Bob
```

* Variable တွေရှိမရှိ စစ်ချင်ရင် isset() ကိုအသုံးပြုပြီး
ရှိရင် true အနေနဲ့ 1 ကိုပြန်ပေးပြီး မရှိရင်တော့ false အနေနဲ့ Empty ကို ပြန်ပေးပါတယ်

```
echo isset($name); // Empty
$name = "Bob";
echo isset($name); // 1
```

* Constant တွေကို define() Function သုံးပြီး ကြေညာပေးရပါတယ် 
* $ သင်္ကေတပါစရာ မလိုအပ်ပါ 
* define() Function ရဲ့ ပထမ Argument မှာ Constant ရဲ့အမည်ကိုပေးရပြီး ဒုတိယ Argument မှာ တန်ဖိုးကိုပေးပါ 
* Assignment Operator = ကို Constant နဲ့အတူ တွဲပြီး အသုံးပြုခွင့်ပေးမှာမဟုတ်ပါ


```
define("MIN", 1);
define("MAX", 10);
echo MAX; // 10
MAX = 20; // Syntax Error: unexpected =
```

* Strings & Arrays

* Escape လုပ်ဖို့လိုတဲ့ Character တွေကို \ သင်္ကေတနဲ့ Escape လုပ်နိုင်ပါတယ်

```
$fruit = "Apple";
$price = 1.99;
echo "Buy some $fruit for \$$price each.";
// Buy some Apple for $1.99 each.
```

* String တစ်ခုမှာ စာလုံးဘယ်နှစ်လုံးပါလဲဆိုတာ သိချင်ရင် strlen() Function

```
echo strlen("Hello World"); // 11
```

* စာကြောင်းတစ်ကြောင်းကနေ လိုချင်တဲ့အပိုင်း ဖြတ်ယူချင်ရင် substr() Function

```
$str = "A quick brown fox.";
echo substr($str, 0, 7); // A quick
```

* စာကြောင်းထဲမှာ Search & Replace လုပ်ချင်ရင် str_replace()

```
$str = "Come here, quick, quick.";
echo str_replace("quick", "hurry", $str);
// Come here, hurry, hurry.
```

* Array

* Numeric Array 

* ထူးခြားချက်အနေနဲ့ echo ကို သုံးပြီး Array တွေကို ဖော်ပြခိုင်းလို့ မရတာကို သတိပြုပါ 
* var_dump() က Data Type တွေကိုပါ ထည့်ပြလို့၊ ဖော်ပြတဲ့အချက်အလက် ပိုပြည့်စုံပါတယ် 
* Array ထဲမှာ ရှိတာကိုပဲ ခပ်ရှင်းရှင်း ကြည့်ချင်တယ်ဆိုရင် print_r() ကိုသုံးနိုင်ပါတယ်

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

* Array တစ်ခုရဲ့အတွင်းမှ ထပ်ဆင့် Array

```
$users = [ 
["name" => "Alice", "age" => 22],
["name" => "Bob", "age" => 23],
["name" => "Tom", "age" => 24],
];
print_r($users);
```

* Array ထဲက တန်ဖိုးတစ်ခုကို ရယူလိုရင်တော့ သက်ဆိုင်ရာ Index နဲ့ထောက်ပြီး ရယူနိုင်ပါတယ်

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

* Array တန်ဖိုးတွေ ထပ်တိုးသတ်မှတ်လိုရင်

```
$fruits = ['Apple', 'Orange'];
$fruits[4] = 'Mango';
print_r($fruits);
// Array ( [0] => Apple [1] => Orange [4] => Mango )
```

* Array ထဲကို တန်ဖိုးတွေ ထပ်တိုးသတ်မှတ်တဲ့အခါ ကိုယ့်ဘာသာ Index နံပါတ် မပေးတော့ဘဲ၊ သူ့အလိုအလျှောက် ထပ်တိုးပြီး ထည့်သွားအောင်လည်း ရေးလို့ရပါတယ်

```
$fruits = ['Apple', 'Orange'];
$fruits[] = 'Mango';
print_r($fruits);
// Array ( [0] => Apple [1] => Orange [2] => Mango )
```

* PHP မှာ မူလကတည်းက Array Destructuring ရေးဟန် ပါဝင်ပြီး နောက်ပိုင်း Version တွေမှာ Array Spread လုပ်ဆောင်ချက်လည်း ပါဝင်လာပါတယ်

```
$user = ["Alice", 22];
list($name, $age) = $user;
echo $name; // Alice
```

* list() ကိုအသုံးပြုပြီး Array ထဲက တန်ဖိုးတွေကို Destructure လုပ်ပြီး Variable တွေရဲ့ တန်ဖိုးအဖြစ် လက်ခံလိုက်ပါတယ်

```
$user = ["Alice", 22];
[ $name, $age ] = $user;
echo $name; // Alice
```

* Associative Array ဆိုရင် အခုလိုရေးပေးဖို့ လိုအပ်ပါတယ်

```
$user = ["name" => "Alice", "age" => 22];
["name" => $name, "age" => $age] = $user;
echo $name; // Alice
```

* Array Spread လုပ်ဆောင်ချက်

```
$nums1 = [1, 2];
$nums2 = [ ...$nums1, 3 ];
print_r($nums2);
// Array ( [0] => 1 [1] => 2 [2] => 3 )
```

* Array တစ်ခုမှာပါဝင်တဲ့ Item အရေအတွက်ကိုသိချင်ရင် count() ကို အသုံးပြုနိုင်ပါတယ်

```
$nums = [1, 2, 3, 4];
echo count($nums); // 4
```

* Variable တစ်ခုဟာ Array ဟုတ်မဟုတ် စစ်ချင်ရင် is_array() နဲ့စစ်နိုင်ပါတယ် ဟုတ်မှန်ရင် 1 ပြန်ပေးပြီး၊ မမှန်ရင် Empty ကို ပြန်ပေးပါတယ်

```
$users = ["alice", "bob"];
echo is_array($users); // 1
```

* တန်ဖိုးတစ်ခု Array ထဲမှာ ပါမပါ သိချင်ရင် in_array() နဲ့ စစ်နိုင်ပါတယ် ဟုတ်မှန်ရင် 1 ပြန်ပေးပြီး၊ မမှန်ရင် Empty ကို ပြန်ပေးပါတယ်

```
$users = ["alice", "bob"];
echo in_array('bob', $users); // 1
```

* array_search() က တန်ဖိုးရှိမရှိ စစ်ပေးယုံသာမက၊ ရှိတယ်ဆိုရင် အဲ့ဒီတန်ဖိုး ရှိနေတဲ့ Index ကို ပြန်ပေးပါတယ်

```
$users =["tom", "bob", "alice"];
echo array_search("alice", $users); // 2
```

* Array ရဲ့နောက်ဆုံးကနေ တန်ဖိုး ထပ်တိုးချင်ရင် array_push() ကိုသုံးပါ 
* နောက်ဆုံးက တန်ဖိုးကို ပယ်ဖျက်ချင်ရင် array_pop() ကိုသုံးပါ 
* ရှေ့ဆုံးကနေ တန်ဖိုးထပ်တိုးချင်ရင် array_unshift() ကိုသုံးပါ 
* ရှေ့ဆုံးကတန်ဖိုးကို ဖျက်ချင်ရင် array_shift() ကိုသုံးပါ

```
$users =["alice", "bob"];
array_push($users, "tom");
print_r($users); // ["alice", "bob", "tom"]
array_pop($users);
print_r($users); // ["alice", "bob"]
```

* Array ထဲက တစ်ချို့အပိုင်းတွေကို ဖယ်ထုတ်/ထုတ်ယူ လိုရင် array_splice()

```
$users =["tom", "bob", "alice"];
$result = array_splice($users, 1, 1);
print_r($users); // Array ( [0] => tom [1] => alice )
print_r($result); // Array ( [0] => bob ) 
```

* Array ရဲ့ Index တွေချည်းလိုချင်ရင် array_keys()
* Array ရဲ့ Value တွေချည်းလိုချင်ရင် array_values()

```
$user =["name" => "alice", "age" => 22];
$keys = array_keys($user);
$vals = array_values($user);
print_r($keys);// Array ( [0] => name [1] => age )
print_r($vals);// Array ( [0] => alice [1] => 22 )
```

* Array ကို Value နဲ့ Sorting စီချင်ရင် sort()
* Array ကို ပြောင်းပြန်စီချင်ရင် rsort()
* Array ကို Index နဲ့ စီရင်တော့ ksort()
* Array ကို Index နဲ့ ပြောင်းပြန်စီချင်ရင် krsort()

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

* String တစ်ခုမှာပါတဲ့ Character တွေ Word တွေ ကိုခွဲထုတ်ပြီး Array အနေနဲ့လိုချင်ရင် explode() 
* အပြန်အလှန်အားဖြင့် Array တန်ဖိုးတွေကို ပေါင်းစပ်ပြီး String အနေနဲ့ လိုချင်ရင် implode()

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

* % သင်္ကေတကို အကြွင်းရှာဖို့သုံးပြီး 
* ** သင်္ကေတကို Exponent ရှာဖို့အတွက် သုံးပါတယ်

```
echo 5 % 3; // 2
echo 2 ** 3; // 8
```

* Assignment Operators

* PHP မှာလည်း = Operator ကို တန်ဖိုးတွေ သတ်မှတ်ဖို့အသုံပြုပြီး 
* += ကို တန်ဖိုးတွေပေါင်းထည့်ဖို့ သုံးပါတယ်
* အလားတူအနေနဲ့ -=, *=, /= Operator တွေလည်း ပါဝင်ပါသေးတယ်

```
$num = 3;
$num += 2;
echo $num; // 5
```

* String တွေတွဲဆက်ထည့်သွင်းလို့ရတဲ့ .= Operator

```
$result = "Welcome";
$result .= " ";
$result .= "Bob";
echo $result; // Welcome Bob
```

* လက်ရှိတန်ဖိုးကို 1 တိုးဖို့နဲ့ 1 နှုတ်ဖို့အတွက် ++ နဲ့ -- Operator

```
$x = 3;
$y = $x++; // $y => 3, $x => 4
```

* $x ရဲ့ လက်ရှိတန်ဖိုး 3 ကို ++ နဲ့ 1 တိုးပြီး $y ထဲကို Assign လုပ်တဲ့အခါ ++ ကို နောက်ကနေရေးတဲ့အတွက် အလုပ်အရင်လုပ်ပြီးမှ 1 တိုးပါတယ် 
* ဒါကြောင့် $y တန်ဖိုး 3 $x တန်ဖိုးကတော့ 4 ဖြစ်နေတာပါ 
* ++ ကိုရှေ့ကရေးမယ်ဆိုရင် ဒီလိုဖြစ်သွားမှာပါ

```
$x = 3;
$y = ++$x; // $y => 4, $x => 4
```

* Comparison Operators

* တန်ဖိုးတွေ ညီမညီ နှိုင်းယှဉ်ဖို့အတွက် == ကို Equal Operator 
* တန်ဖိုးတွေ မညီဘူးလား နှိုင်းယှဉ်ဖို့အတွက် != ကို Not Equal Operator 
* <> ကို Not Equal Operator အနေနဲ့ သုံးနိုင်ပါတယ်
* Identical Equal Operator === နဲ့ Identical Not Equal Operator !== 

```
echo 5 == "5"; // 1
```

* 1 ဆိုတာ true ဆိုတဲ့အဓိပ္ပါယ်ဖြစ်ပါတယ် 
* Integer 5 နဲ့ String "5" တို့ အမျိုးအစား မတူပေမယ့် တူအောင်ညှိပြီးအလုပ်လုပ်သွားလို့ ညီတယ်လို့ ပြောနေတာပါ 
* Identical Operator မှာတော့ Type ကိုတူအောင်မညှိဘဲ အရှိအတိုင်း နှိုင်းယှဉ်မှာ ဖြစ်ပါတယ်

```
echo 5 === "5"; //
```

* တန်ဖိုးအကြီးအသေး နှိုင်းယှဉ်ဖို့အတွက် 
* Less Than <, 
* Greater Than >, 
* Less Than Equal <=, 
* Grater Than Equal >=

* Spaceship Operator

```
echo 3 <=> 5; // -1
echo 5 <=> 5; // 0
echo 5 <=> 3; // 1
```

* Logical Operators

* ! ကို NOT Operator,
* && ကို AND Operator, 
* || ကို OR Operator,
* and ဆိုတဲ့ Keyword ကိုလည်း AND Operator အနေနဲ့ အသုံးပြုနိုင်ပြီး 
* or ဆိုတဲ့ Keyword ကိုလည်း OR Operator အနေနဲ့ အသုံးပြုနိုင်ပါတယ်

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

* OR က နှိုင်းယှဉ်တန်ဖိုး နှစ်ခုမှာ တစ်ခုမှန်ရင် ရလဒ်မှန်သလို နှစ်ခုလုံးမှန်ရင်လည်း ရလဒ်မှန်ပါတယ် 
* XOR ကတော့ နှိုင်းယှဉ်တန်ဖိုးနှစ်ခုမှာ တစ်ခု မှန်ရင် ရလဒ်မှန်ပြီး နှစ်ခုလုံးမှန်ရင် ရလဒ်မှားပါတယ်

```
$x = 3;
$y = 5;
echo $x < $y or $x === 3; // 1 (true)
echo $x < $y xor $x === 3; // (false)
```

* Ternary & Null Coalescing Operator

* Ternary Operator က ပေးလိုက်တဲ့ ပထမဆုံး Expression ရဲ့ ရလဒ် true ဖြစ်ရင် ? နောက်က Expression ကို ဆက်လုပ်သွားမှာဖြစ်ပြီး 
* false ဖြစ်ရင် : နောက်က Expression ကို ဆက်လုပ်သွားမှာ ဖြစ်ပါတယ်

```
$name = "";
echo $name ? $name : "Unknown"; // Unknown
$name = "Alice";
echo $name ? $name : "Unknown"; // Alice
```

* အတိုကောက်ရေးထုံး

```
$name = "";
echo $name ?: "Unknown"; // Unknown
$name = "Alice";
echo $name ?: "Unknown"; // Alice
```

* $name ကသာ ကြိုတင်ရှိမနေရင် Undefined variable Warning တက်ပါလိမ့်မယ်

```
echo $name ? $name : "Unknown";
// Warning: Undefined variable $name
echo $name ?: "Unknown";
// Warning: Undefined variable $name
```

* isset() နဲ့ Variable ရှိမရှိ စစ်ပြီးမှ ရေးရင်တော့ ာ့ Undefined variable Warning မတက်ပါဘူး

```
echo isset($name) ? $name : "Unknown"; // Unknown
```

* Null Coalescing Operator

```
echo $name ?? "Unknown"; // Unknown
```

* Null Coalescing Assignment Operator

* $result ရဲ့ မူလတန်ဖိုး Alice ဖြစ်ပြီး $name ရှိနေရင် $name တန်ဖိုးကို $result ထဲမှာ Assign လုပ်လိုက်ချင်တာပါ 
* မရှိရင်တော့ Assign မလုပ်စေချင်ပါဘူး ဒါကြောင့် Null Coalescing Assignment Operator ဖြစ်တဲ့ ??= ကို အသုံးပြုလိုက်တာပါ 
* Assign လုပ်လိုက်ပေမယ့် $name တန်ဖိုး မရှိတဲ့အတွက် မူလတန်ဖိုး Alice ကိုပဲ ဖော်ပြပေးလိုက်တာပါ

```
$result = "Alice";
$result ??= $name;
echo $result; // Alice
```

* Control Structures

* if Statement
* elseif Statement

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

* Switch Statement

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

* PHP 8 မှာ switch Statement နဲ့ဆင်တူတဲ့ match Expression ဖြည့်စွက် ပါဝင်လာပါတယ်
* Expression ဖြစ်သွားတဲ့အတွက် Variable ထဲကို ထည့်လိုက်လို့ရ တာမျိုး အပါအဝင် ထူးခြားတဲ့ အသုံးပြုမှုမျိုးတွေနဲ့ သုံးလို့ရနိုင်သွားပါတယ် 
* switch က တန်ဖိုးနှိုင်းယှဉ်ဖို့ == ကိုသုံးပြီး match က === ကိုသုံးတယ်ဆိုတာကိုလည်း သတိပြုပါ 
* switch မှာ switch("5") လို့စစ်ထားရင် case 5 ကို အလုပ်လုပ်ပေးပါတယ် 
* String "5" ကိုစစ်ထားပေမယ့် Integer 5 ဆိုရင်လည်း အလုပ်လုပ်ပေးမှာပါ 
* match("5") လို့စစ်ထားရင်တော့ Int 5 => ကို အလုပ်လုပ်မှာ မဟုတ်ပါဘူး 
* String "5" ကို စစ်ထားတဲ့အတွက် String "5" ကိုတွေ့မှသာ အလုပ်လုပ်မှာပါ

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

* ပေးထားတဲ့ ကိန်းဂဏန်းတွေထဲမှာ အနှုတ်ကိန်းပါရင် ထည့်မပေါင်းဘဲ ကျော်လိုက်စေချင်တယ်ဆိုရင် ဒီလိုရေးလို့ရပါတယ်

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

* ပေးထားတဲ့ ကိန်းဂဏန်းတွေထဲမှာ အနှုတ်ကိန်းကိုတွေ့တာနဲ့ ရပ်လိုက် စေချင်ရင် အခုလိုရေးနိုင်ပါတယ် 
* break နောက်ကနေ လိုအပ်ရင် Argument ထည့်ပေးလို့ရပါတယ် Default က 1 ဖြစ်ပါတယ် 
* break; လို့ရေးလိုက်တာဟာ break 1; လို့ ရေးလိုက်တာနဲ့ အတူတူပါပဲ 
* 1 လို့ပြောတဲ့အတွက် ကုဒ် Block တစ်ဆင့် ထွက်လိုက်မှာပါ 
* နှစ်ဆင့်သုံးဆင့်ကျော်ပြီး ထွက်လိုက်ချင်ရင် break 2; တို့ break 3; တို့ကို အသုံးပြုနိုင်ပါတယ် 
* continue မှာလည်း အလားတူပဲ လိုအပ်ရင် Argument ထည့်ပေးလို့ရပါတယ်

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

* do-while Statement ကတော့ အခြေခံအားဖြင့် while Statement နဲ့ အတူတူပါပဲ က
* ရိုးရိုး while Statement မှာ Condition စစ်ပြီး မှန်မှအလုပ်လုပ်ပြီး၊ do-while Statement မှာတော့ အလုပ်အရင်လုပ်ပြီး Condition ကိုနောက်မှ စစ်တဲ့အတွက်၊ ပထမဆုံးတစ်ကြိမ် Condition မှန်သည်ဖြစ်စေ မှားသည်ဖြစ်စေ အလုပ်လုပ်သွားမှာ ဖြစ်ပါတယ် 
* Condition မှန်သည်ဖြစ်စေ မှားသည်ဖြစ်စေ ပထမဆုံးအကြိမ်တော့ မဖြစ်မနေ အလုပ်လုပ်ဖို့လိုတဲ့ ကုဒ်တွေမှာ while အစား do-while ကို အသုံးပြုနိုင်ပါတယ်

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

* for Statement ကိုတော့ Expression (၃) ခုကို Argument အနေနဲ့ ပေးပြီးရေးရပါတယ် 
* ပထမဆုံး Expression ကို စစချင်းတစ်ကြိမ် အလုပ်လုပ်ပါတယ် 
* အလယ်က Expression ကတော့ Condition ဖြစ်ပြီး မှန်မှ နောက်အကြိမ်တွေ ဆက်အလုပ်လုပ်မှာပါ 
* နောက်ဆုံးက Expression ကိုတော့ Loop တစ်ကြိမ် ပြီးတိုင်းတစ်ခါအလုပ်လုပ်ပေးမှာပဲ ဖြစ်ပါတယ်

```
$nums = [12, 42, -2, 8, 621];
$result = 0;
for($i = 0; $i < count($nums); $i++) {
 $result += $nums[$i];
}
echo $result; // 681
```

* foreach Statement ကတော့ ပေးလိုက်တဲ့ Array ကို အစကနေအဆုံးထိ အလုပ်လုပ်သွားမှာမို့လို့ Condition တွေ ဘာတွေပေးစရာမလိုတော့ပါဘူး

```
$nums = [12, 42, -2, 8, 621];
$result = 0;
foreach($nums as $num) {
 $result += $num;
}
echo $result; // 681
```

* Functions

```
function add($a, $b) {
 echo $a + $b;
}
add(1, 2); // 3
```

* Rest Parameter

* $b Parameter ဟာ Rest Parameter တစ်ခုဖြစ်လို့ ပါဝင်လာတဲ့ Argument အားလုံးကို
လက်ခံထားပေးမှာပါ 
* add(1, 2, 3, 4) လို့ခေါ်လိုက်တဲအခါ $a တန်ဖိုး 1 ဖြစ်သွားပြီး ကျန်တဲ့ 2,
3, 4 အားလုံးဟာ $b ထဲမှာ Array တစ်ခုအနေနဲ့ ရောက်ရှိသွားတယ်ဆိုတာကို တွေ့ရမှာပဲ ဖြစ်ပါတယ်

```
function add($a, ...$b) {
 print_r($b);
}
add(1, 2, 3, 4);
// Array ( [0] => 2 [1] => 3 [2] => 4 )
```

* add() Function ကိုခေါ်တဲအခါ Array ကို Argument အနေနဲ့ ပေးဖို့လိုအပ်ပါတယ်
* Integer တွေပေးထားတဲ့အတွက် Error တက်ပါတယ် 
* Function ခေါ်တဲ့အခါမှာ တက်တာမဟုတ်ပါဘူး 
* Function ထဲက array_sum() ကိုအလုပ်လုပ်ချိန်ကျတော့မှ တက်တာပါ 
* ဒီ Error ကို ကြည့်လိုက်ရင် array_sum() ကိုခေါ်ရင် Array ကိုပေးရမယ်လို့ ပြောနေပါတယ်
* တစ်ကယ်တမ်း Function ခေါ်တာက array_sum() ကိုခေါ်နေတာ မဟုတ်ပါဘူး 
* add() ကိုခေါ်နေတာပါ Error က မတိကျပါဘူး

```
function add($nums) {
 return array_sum($nums);
}
echo add(1, 2);
// Error: array_sum(): Argument must be array
```

* Function ကြေညာစဉ်မှာ လက်ခံမယ့် Parameter ဟာ Array ဖြစ်ကြောင့် Hint လုပ်ပေးလိုက်တာပါ
* Scalar Type Hinting လို့ခေါ်ပါတယ်။ ခေါ်ယူပုံ မမှန်လို့ Error တက်တာပါ 
* Error က တိကျသွားပါပြီ add() ကိုခေါ်တဲ့အခါ Array ကို Argument အနေနဲ့ ပေးရမယ်ဆိုတဲ့ Error ဖြစ်သွားလို့ အကြောင်းရင်းက ရှင်းသွားပါတယ် 
* Type Hinting လုပ်ဆောင်ချက်ဟာ အလွန် အရေးပါတယ်လို့ ပြောတာပါ 
* ကုဒ်တွေထဲမှာ Error ရှိလာတဲ့အခါ ပိုပြီးတော့ အမှားရှာရလွယ်ကူ မြန်ဆန်သွားစေမှာ ဖြစ်ပါတယ်

```
<?php
function add(Array $nums) {
 return array_sum($nums);
}
echo add(1, 2);
// Error: add(): Argument must be array
```

* Return Type Hinting

* Function ဝိုက်ကွင်းအပိတ်နဲ့ တွန့်ကွင်းအစ ကြားထဲမှာ Colon လေးခံပြီး Return Type ကို သတ်မှတ်ပေးရတာပါ 
* ဒီနမူနာမှာ Function ရဲ့ Return Value ဟာ float ဖြစ်ရမယ်လို့ သတ်မှတ်ထားပါတယ် 
* Array ကို Argument အနေနဲ့ပေးပြီး ခေါ်ယူအသုံးပြုထားလို့ အသုံးပြုပုံ မှန်ပေမယ့် Error တက်နေပါတယ် 
* Function က Return ပြန်ပေးမထားလို့ Return Value က NULL ဖြစ်နေလို့ပါ

```
function add(Array $nums): float {
 echo array_sum($nums);
}
add([1, 2]);
// Error: add(): Return value must be float
```

* PHP 8 မှာတော့ Union Type လို့ခေါ်တဲ့ လုပ်ဆောင်ချက် ဖြည့်စွက်ပါဝင်လာပါတယ် 
* Type Hint လုပ်တဲ့အခါ တစ်မျိုးထက်ပိုပြီး Hint လုပ်လို့ရသွားစေတဲ့ ရေးနည်းပါ

```
function price(int|float $n) {
 return "Price is \$$n";
}
echo price(3.1); // Price is $3.1
echo price(2); // Price is $2
```

* $name Variable တစ်ခုရှိနေပြီး အဲ့ဒီ $name ကို Argument အနေနဲ့ hello() ကိုခေါ်ယူစဉ်
မှာ ပေးလိုက်ပါတယ် 
* ပေးလိုက်တဲ့ $name ထဲမှာရှိနေတဲ့တန်ဖိုးဖြစ်တဲ့ Alice က hello() ရဲ့ $n ထဲကို ရောက်ရှိသွားပါတယ် 
* $n တန်ဖိုးကို Bob လို့ပြောင်းတဲ့အခါ $n တန်ဖိုးပဲ ပြောင်းမှာပါ
* ပေးလိုက်တဲ့ $name နဲ့ သက်ဆိုင်ခြင်းမရှိပါဘူး 
* Function ရဲ့ ပြင်ပမှာ echo $name နဲ့ ပြန်ထုတ်ကြည့်လိုက်တဲ့ အခါမှာလည်း မူလတန်ဖိုး Alice သာဆက်ရှိနေတာကို တွေ့မြင်ရမှာဖြစ်ပါတယ်

```
$name = "Alice";
function hello($n) {
 $n = "Bob";
 echo "Hello $n";
}
hello($name); // Hello Bob
echo $name; // Alice
```

* Pass by Reference

* Variable တစ်ခုကို Argument အနေနဲ့ပေးလိုက်ရင် Variable ကြီးတစ်ခုလုံးကို ချိတ်ပေးလိုက်တာပါ 
* Function အတွင်းထဲမှာ၊ အဲ့ဒီ Variable ပေါ်မှာ ပြုလုပ်သမျှ အပြောင်းအလဲတွေက မူလ Variable
ပေါ်မှာလည်း သက်ရောက်သွားမှာ ဖြစ်ပါတယ် 
* Parameter မှာ & သင်္ကေတလေး ပါသွားတာပါ Reference Operator ဖြစ်ပါတယ် 
* hello() ကိုခေါ်ယူစဉ်မှာ $name ကိုပေးလိုက်တဲ့အခါ Variable တစ်ခုလုံးကို ချိပ်ပေးလိုက်တာပါ 
* Function ထဲမှာ $name ကို လက်ခံယူတဲ့ $n တန်ဖိုး ပြောင်းတဲ့အခါ မူလ $name တန်ဖိုးလည်း လိုက်ပြောင်းသွားတာကို တွေ့ရမှာပဲ ဖြစ်ပါတယ်

```
$name = "Alice";
function hello(&$n) {
 $n = "Bob";
 echo "Hello $n";
}
hello($name); // Hello Bob
echo $name; // Bob
```

* Variable Function

* Variable ရဲ့နောက်မှာ ဝိုက်ကွင်းအဖွင့်အပိတ် ထည့်ပေးလိုက်ခြင်းအားဖြင့် Function တစ်ခုကဲ့သို့ ခေါ်ယူနိုင်တဲ့ သဘောမျိုးပါ 
* $name Variable ထဲမှာ add ဆိုတဲ့ String တန်ဖိုးတစ်ခုရှိနေတဲ့အတွက် $name() လို့ပြောလိုက်တာဟာ add() လို့ပြောလိုက်တာနဲ့ အတူတူပါပဲ 
* add() Function အလုပ်လုပ်သွားတာကို တွေ့ရမှာပဲ ဖြစ်ပါတယ်

```
function add($a, $b) {
 echo $a + $b;
}
$name = "add";
$name(1, 2); // 3
```

* Function Expression  ရေးထုံးလည်း ရှိပါသေးတယ် Nameless Function (သို့မဟုတ်) Anonymous Function လို့လည်း ခေါ်နိုင်ပါတယ်

* $nums Array ရှိပြီး ပေးလိုက်တဲ့တန်ဖိုးကို 2 နဲ့ မြှောက်ပေးတဲ့ two() Function လည်းရှိနေပါတယ် 
* Array တွေ Loop လုပ်ဖို့အတွက် array_map() Function ရှိပါတယ် 
* array_map() က Callback Function နဲ့ Array တို့ကို Parameter အနေနဲ့လက်ခံတယ် 
* Callback အဖြစ် two ကိုပေးပြီး Array အဖြစ် $nums ကိုပေးလိုက်တဲ့အခါ အထဲကတန်ဖိုးတွေကို 2 နဲ့ ကိုယ်စီမြှောက်ပေးထားတဲ့ $result Array ကို ပြန်ရတာ တွေ့မြင်ရမှာပဲ ဖြစ်ပါတယ်

```
$nums = [1, 2, 3, 4];
function two($n) {
 return $n * 2;
}
$result = array_map("two", $nums);
print_r($result);
// Array ( [0] => 2 [1] => 4 [2] => 6 [3] => 8 )
```

* Nameless Function

* ကြိုရေးထားတဲ့ Function ကို Callback အနေနဲ့ မပေးတော့ဘဲ၊ Function
Expression ကို Callback အနေနဲ့ ပေးလိုက်တာပါ

```
$nums = [1, 2, 3, 4];
$result = array_map(function($n) {
 return $n * 2;
}, $nums);
print_r($result);
// Array ( [0] => 2 [1] => 4 [2] => 6 [3] => 8 )
```

* Function Expression ကို Variable တွေထဲမှာ Assign လုပ်ထားလို့လည်း ရနိုင်ပါတယ်

```
$two = function($n) {
 echo $n * 2;
};
$two(2); // 4
```

* Function Expression တွေရေးတဲ့အခါ အသုံးပြုစေလိုတဲ့ Variable တွေကို use Statement နဲ့ ထည့်ပေးလိုက်လို့ ရနိုင်ပါတယ် 
* use Statement ကိုသုံးပြီး တစ်ခါထဲ တွဲထည့်ပေးလိုက်လို့ပါ ဒီနည်းရဲ့ အားသာချက်ကတော့ တန်ဖိုးကို Value အနေနဲ့သာ ပေးလိုက်တာပါ 
* Function အတွင်းမှာ တန်ဖိုးပြောင်းလိုက်လို့လည်း မူလပင်မ Variable မှာ တန်ဖိုးပြောင်းမှာ မဟုတ်ပါဘူး

```
$name = "Alice";
$hello = function() use ($name) {
 echo "Hello $name";
};
$hello(); // Hello Alice
```

* Function အတွင်းမှာ $name တန်ဖိုးကို ပြောင်းလိုက်ပေမယ့်၊ မူလ $name တန်ဖိုးကတော့ မပြောင်းဘူးဆိုတာကို တွေ့မြင်ရတာပဲ ဖြစ်ပါတယ်

```
$name = "Alice";
$hello = function() use ($name) {
 $name = "Bob";
 echo "Hello $name";
};
$hello(); // Hello Bob
echo $name; // Alice
```

* Arrow Function

* fn ရဲ့နောက်မှာ ဝိုက်ကွင်းအဖွင့်အပိတ်နဲ့ Parameter List လိုက်ရပြီး သူ့နောက်ကနေ => သင်္ကေတနဲ့အတူ Return ပြန်ပေးရမယ့် Expression ကို ပေးလိုက်ရတာပါ 
* => သင်္ကေတကို Array တွေမှာလည်း သုံးတဲ့အတွက် Array နဲ့မရောစေဖို့အတွက် ရှေ့ကနေ fn ထည့်ပေးရတဲ့သဘော ဖြစ်မယ်လို့ ယူဆပါတယ်
* တွန့်ကွင်းအဖွင့်အပိတ်တွေ ထည့်လို့မရတာကိုလည်း သတိပြုရပါမယ် 
* Function Statement တွေရေးလို့တော့ ရမှာ မဟုတ်ပါဘူး Expression တစ်ခုပဲ ရေးလို့ရမှာပါ

```
$two = fn ($n) => $n * 2;
echo $two(3); // 6
```

* Arrow Function ရဲ့ နောက်ထပ်ထူးခြားချက်တစ်ခုက Global Variable တွေကို တိုက်ရိုက် အသုံးပြုနိုင်ခြင်းဖြစ်ပါတယ် 
* global တွေuse တွေ မလိုအပ်တော့ပါဘူး Global Variable ဖြစ်တဲ့ $x တန်ဖိုးကို Arrow Function ရဲ့ Expression မှာ ထည့်သုံးလို့ ရနေတာကို တွေ့ရမှာဖြစ်ပါတယ်

```
$x = 3;
$add = fn($y) => $x + $y;
echo $add(5); // 8
```

* Named Arguments

* Argument အမည်နဲ့ ပေးချင်တဲ့ တန်ဖိုးကို တွဲပေးလိုက်တဲ့အတွက် ရှေ့နောက်အစီအစဉ် မှန်စရာ မလိုအပ်တော့ပါဘူး 
* ပေးတဲ့ Argument တွေများတဲ့အခါ နှစ်ကြောင်းသုံးကြောင်းခွဲရေးလို့ရတယ် ဆိုတာလေးကို မှတ်သားစေချင်ပါတယ်

```
function profile($name, $email, $age) {
 echo "$name ($age) @ $email";
}
profile(
 age: 23,
 name: "Bob",
 email: "bob@gmail.com",
);
// Bob (23) @ bob@gmail.com
```

* Object-Oriented Programming

* PHP မှာ Public, Private နဲ့ Protected လို့ပေ]ါ်တဲ့ Access Control သတ်မှတ်ချက် (၃) မျိုး ရှိပါတယ်
* Public ဆိုတာ ကြိုက်တဲ့နေရာမှာ အသုံးပြုခွင့်ရှိတယ်ဆိုတဲ့ အဓိပ္ပါယ်ဖ်စ်ပြီး 
* Private ဆိုတာကတော့ လက်ရှိ Class အတွင်းမှာသာ အသုံးပြုခွင့်ရှိတယ်ဆိုတဲ့ အဓိပ္ပါယ်ပ် 
* Protected ကတော့ လက်ရှိ Class နဲ့ လက်ရှိ Class ကို ဆက်ခံဖို့ဖြစ်ပေါ်လာတဲ့ Child Class တွေမှာ အသုံးပြုခွင့်ရှိတယ်ဆိုတဲ့အဓိပ္ပါယ်ပါ
* Property တွေ Method တွေ သတ်မှတ်တဲ့အခါ ဒီလို Access Control တွေကို ထည့်သွင်းသတ်မှတ်ပေးရပါတယ်
* Animal Class မှာ $name လို့ခေါ်တဲ့ Property နဲ့ run() လို့ခေါ်တဲ့ Method တစ်ခုပါဝင်
သွားပါပြီ 
* Property တွေသတ်မှတ်တဲ့အခါ Variable အနေနဲ့ပဲ သတ်မှတ်ပေးရပါတယ်
* Method တွေ သတ်မှတ်လိုရင်တော့ Function တွေကို အသုံးပြုရတာပါ
* $this လို့ခေါ်တဲ့ Pseudo Variable ကို သတိပြုပါ
* Class အတွင်းမှာ ကြေညာထားတဲ့ Property တွေMethod တွေကို အသုံးပြုလိုရင် ဒီအတိုင်းခေါ်သုံးလိုက်လို့ မရပါဘူး 
* $this ကနေတစ်ဆင့် သုံးပေးရပါတယ်
* $this->name ဆိုတာဟာ သူ့အပေါ်မှာ ကြေညာထားတဲ့ $name Property ကို အသုံးပြုလိုက်ခြင်း
ဖြစ်ပါတယ်

```
class Animal
{
 public $name;
 public function run()
 {
 echo "$this->name is running...";
 }
}
```

* Class ကိုအသုံးပြုပြီး Object တည်တောက်လိုက်ရင် တည်ဆောက်လိုက်တဲ့ Object တွေမှာ
name Property နဲ့ run() Method တို့ပါဝင်သွားမှာပဲ ဖြစ်ပါတယ်
* Animal Class ကိုအသုံးပြုပြီး $dog Object ကိုတည်ဆောက်ထားပါတယ်
* $dog Object မှာ name Property နဲ့ run() Method တို့ရှိနေပါပြီ
* Object ရဲ့ Property တွေMethod တွေကို ရယူ/အသုံးပြုဖို့အတွက် Object Operator အနေနဲ့ -> သင်္ကေတကိုအသုံးပြုရပါတယ်
* Dart Operator လို့ ခေါ်ကြပါတယ်
* name Property ရဲ့ တန်ဖိုးကို Bobby လို့သတ်မှတ်ပေးလိုက်တာပါ
* run() Method ကို ခေါ်ယူလိုက်တဲအခါ ရလဒ်အနေနဲ့ Bobby is running… ကို တွေ့မြင်ရမှာဖြစ်ပါတယ် 
* run() Method က name Property ရဲ့တန်ဖိုးကို ထည့်သွင်း အသုံးပြုသွားတာပါ

```
$dog = new Animal;
$dog->name = "Bobby";
$dog->run(); // Bobby is running…
```

* Object ကနေ Property တွေMethod တွေကို အသုံးပြုလို့ရတယ်ဆိုတာ Public အဖြစ် ကြေညာ
ရေးသားထားလို့ပါ
* Public Member တွေကို အခုလိုအသုံးပြုခွင့်ရှိပါတယ်
* Private ဆိုရင်တော့ အခုလိုသုံးလို့ရမှာ မဟုတ်ပါဘူး
* name ဟာ Private Property ဖြစ်သွားပါပြီ
* Object ကနေတစ်ဆင့် name ရဲ့တန်ဖိုးကို ပြောင်းဖို့ကြိုးစားတဲ့အခါ ပြောင်းခွင့် မရှိဘူးဆိုတဲ့ Error ကို ရရှိမှာ ဖြKစ်ပါတယ်

```
class Animal
{
 private $name;
}
$dog = new Animal;
$dog->name = "Bobby";
// Error: Cannot access private property
```

* Object တည်ဆောက်လိုက်တာနဲ့ အလုပ်လုပ်သွားစေချင်တာတွေ ရှိရင်လည်း သတ်မှတ်ထားနိုင်ပါတယ်
* Constructor လို့ခေါ်ပါတယ် 
* ရှေ့ဆုံးက Underscore နှစ်ခုနဲ့ စပေးရတာကို သတိပြုပါ

```
class Animal
{
 public function __construct()
 {
 echo "Creating Animal object";
 }
}
$dog = new Animal;
// Creating Animal object
```

* Constructor က Private ဆိုရင် Object တည်ဆောက်လို့ ရတော့မှာ မဟုတ်ပါဘူး
* Object တည်ဆောက်ချိန်မှာ Constructor ကို အလုပ်လုပ်ဖို့ ကြိုးစားတဲ့အခါ မရနိုင်တဲ့အတွက်ပါ
* Object တည်ဆောက်လို့မရတော့ဘဲ Error တက်သွားတာကို တွေ့ရမှာပါ

```
class Animal
{
 private function __construct()
 {
 echo "Creating Animal object...";
 }
}
$dog = new Animal;
// Error: Call to private __construct()
```

*  Class Member ခေါ် Static Member 
*  Object တည်ဆောက်စရာ မလိုဘဲ Class အမည်ကနေ တိုက်ရိုက် အသုံးပြုလို့ရတဲ့ Property တွေMethod တွေကြေညာလို့ရနိုင်ပါတယ်
* Static Property တစ်ခုနဲ့ Static Method တစ်ခုရှိနေတာကို တွေ့ရမှာပါ
* Static Member တွေကို အသုံးပြုနိုင်ဖို့အတွက် Object မဆောက်တော့ဘဲ Class အမည်ဖြစ်တဲ့ Animal ပေါ်မှာ တိုက်ရိုက် အသုံးပြုထားတာကိုလည်း တွေ့ရနိုင်ပါတယ်
* Static Member တွေကို ရယူဖို့အတွက် :: သင်္ကေတကို အသုံးပြုရတာကို သတိပြုပါ
* Scope Resolution Operator လို့ခေါ်ပါတယ်
* Double Colon Operator လို့လည်း ခေါ်နိုင်ပါတယ်
* Class အတွင်းထဲမှာ Static Member တွေကို အသုံးပြုဖို့အတွက် $this ကို မသုံးဘဲ static ကို ပဲသုံးတယ် ဆိုတာလည်း သတိပြုပါ

```
class Animal
{
 static $type = "Mammal";
 static function info()
 {
 echo "Group: " . static::$type;
 }
}
echo Animal::$type; // Mammal
Animal::info(); // Group: Mammal
```

* Object ဆောက်ခွင့်မပြုဘဲ Class Name တွေသာ တိုက်ရိုက်အသုံးပြုစေလို့တဲ့ အတွက် Static 
* Member တွေကို Private Constructor နဲ့ တွဲသုံးတာမျိုးတွေ ရှိကြပါတယ်
* $name ဆိုတဲ့အမည်နဲ့ Private Property တစ်ခု ပါသွားပါပြီ
* Constructor က Argument တစ်ခုလက်ခံပြီး လက်ခံရရှိတဲ့ တန်ဖိုးကို Property အဖြစ် ပြောင်းပေးထားပါတယ်
* Object တည်ဆောက်တဲ့ Argument တစ်ခုပေးမှပဲ တည်ဆောက်လို့ ရတော့မှာဖြစ်ပြီး ပေးလိုက်တဲ့
Argument ဟာ Property တန်ဖိုးဖြစ်သွားမှာပါ

```
class Animal
{
 private $name;
 public function __construct($name)
 {
 $this->name = $name;
 }
public function run()
 {
 echo "$this->name is running...";
 }
}
$dog = new Animal("Bobby");
$dog->run(); 
```

* PHP 8 မှာ Constructor Property Promotion လို့ခေါ်တဲ့ လုပ်ဆောင်ချက် အသစ်ထည့်သွင်း ပေးလာပါတယ်
* Property ကို သပ်သပ် ကြေညာစရာ မလိုတော့သလို၊ Construct Argument ကို Property တန်ဖိုးဖြစ်အောင် Assign လုပ်ပေးတဲ့ ကုဒ်ကိုလည်း ကိုယ်ဘာသာ ရေးစရာ မလိုတော့ပါဘူး
* Constructor ရဲ့ Argument မှာ Access Control Modifier ထည့်ရေးပေးလိုက်ယုံနဲ့ Property ကြေညာတဲ့အဆင့်နဲ့ တန်ဖိုး Assign လုပ်တဲ့အဆင့်၊ ရေးရတာ နှစ်ဆင့် လျော့သွားတာပါ

```
class Animal
{
 public function __construct(private $name)
 {
 //
 }
 public function run()
 {
 echo "$this->name is running...";
 }
}
$dog = new Animal("Rambo");
$dog->run(); // Rambo is running…
```

* Class တစ်ခုကိုရေးသားတဲ့အခါ အခြား Class ပေါ်မှာ အခြေခံပြီးတော့လည်း ရေးလို့ရပါတယ်
* Inheritance လို့ခေါ်ပါတယ်
* အမွေဆက်ခံပြီး Inherit လုပ်လိုက်တဲ့အခါ မူလပင်မ Class ရဲ့ လုပ်ဆောင်ချက်တွေကို ဆက်ခံသူက ရရှိသွားမှာ ဖြစ်ပါတယ်
* ပင်မ Class ဖြစ်တဲ့ Animal မှာ Private Property ဖြစ်တဲ့ $name ရှိနေပါတယ်
* Constructor နဲ့ run() Method တို့လည်း ရှိနေပါတယ်
* Dog Class က extends ကိုသုံးပြီး Animal ကို ဆက်ခံလိုက်တဲ့အခါ Animal ရဲ့ လုပ်ဆောင်ချက်တွေကို ရရှိသွားပါပြီ
* Constructor ကအစပင်မ Class ရဲ့ Constructor ကို ရရှိသွားတာကို တွေ့မြင်ရခြင်းပဲ ဖြစ်ပါတယ်
* Dog Class မှာ run() Method မရှိပေမယ့် ပင်မ Class ကနေ ဆက်ခံရရှိထားလို့ အသုံးပြုနိုင်တာကိုလည်း တွေ့မြင်ရမှာပါ

```
class Animal
{
 private $name;
 public function __construct($name)
 {
 $this->name = $name;
 }
 public function run()
 {
 echo "$this->name is running...";
 }
}
class Dog extends Animal
{
 public function bark()
 {
 echo "Woof.. woof...";
 }
}
$bobby = new Dog("Bobby");
$bobby->run(); // Bobby is running...
$bobby->bark(); // Woof.. woof…
```

* ပင်မ Class မှာ $name Property ရှိပေမယ့် Private Property ဖြစ်နေလို့ ပင်မ Class နဲ့သာ သက်ဆိုင်ပါတယ်
* Dog Class က ဆက်ခံရရှိတဲ့အထဲမှာ မပါပါဘူး

```
class Animal
{
 private $name;
 public function __construct($name)
 {
 $this->name = $name;
 }
}
class Dog extends Animal
{
 public function bark()
 {
 echo "$this->name : Woof.. woof...";
 }
}
$bobby = new Dog("Bobby");
$bobby->bark(); // Undefined property: Dog::$name
```

* Protected ကို အသုံးပြုရတာပါ
* Protected Member တွေဟာ ပင်မ Class နဲ့ရော ဆက်ခံတဲ့ Class နဲ့ပါ သက်ဆိုင်တဲ့ Member
တွေဖြစ်ပါတယ်
* ပင်မ Class မှာ $name Property က Protected ဖြစ်တဲ့အတွက် ဆက်ခံတဲ့ Dog Class မှာပါ အသုံးပြုခွင့် ရှိသွားလို့ပါ

```
class Animal
{
 protected $name;
 public function __construct($name)
 {
 $this->name = $name;
 }
}
class Dog extends Animal
{
 public function bark()
 {
 echo "$this->name : Woof.. woof...";
 }
}
$bobby = new Dog("Bobby");
$bobby->bark(); // Bobby : Woof.. woof…
```

* ဆက်ခံထားတဲ့ Class တွေက ပင်မ Class ရဲ့ လုပ်ဆောင်ချက်တွေကို Override လုပ်ပြီးလိုအပ်ရင် ပြန်ရေးလို့ ရပါတယ် 
* ပင်မ Class ရဲ့လုပ်ဆောင်ချက်ကို ခေါ်သုံးလို့လည်း ရပါသေးတယ်
* ဆက်ခံထားတဲ့ Dog Class မှာ Constructor ကိုပြန်ရေးလိုက်တာပါ
* Dog Object တည်ဆောက်တဲ့အခါ မူလဆက်ခံထားတဲ့ Animal Constructor အလုပ်မလုပ်တော့ဘဲ အသစ်ပြန်ရေးထားတဲ့ Dog Constructor က အလုပ်လုပ်သွားမှာပါ
* Method တွေ Property တွေကိုလည်း ဒီအတိုင်းပဲ ပြန်ရေးလို့ရပါတယ် 
* ဒီလိုပြန်ရေးတဲ့အခါ လိုအပ်ရင် ပင်မ Class ရဲ့မူလလုပ်ဆောင်ချက်ကို ပြန်ခေါ်သုံးလို့ ရပါတယ်
* Dog Constructor က ပင်မ Animal Class ရဲ့ Constructor ကို parent
ရေးထုံးကနေတစ်ဆင့် ခေါ်သုံးထားတာကို တွေ့နိုင်ပါတယ်
* Dog Object တည်ဆောက်စဉ်မှာ အလုပ်လုပ်သွားမှာက Dog Constructor ဆိုပေမယ့် မူလ Animal Constructor ကိုလည်း ခေါ်သုံးထားလို့ နှစ်ခုလုံး ပူးပေါင်း အလုပ်လုပ်သွားတဲ့သဘောကို ရရှိသွားပါတယ်

```
class Animal
{
 protected $name;
 public function __construct($name)
 {
 $this->name = $name;
 }
}
class Dog extends Animal
{
 private $color;
 public function __construct($name, $color)
 {
 parent::__construct($name);
 $this->color = $color;
 }
 public function profile()
 {
 echo "$this->name has $this->color color.";
 }
}
$bobby = new Dog("Bobby", "brown");
$bobby->profile(); // Bobby has brown color.
```

* Override လုပ်ပြီး ပြင်ရေးခွင့် မပြုချင်တဲ့ လုပ်ဆောင်ချက်တွေရှိရင် final ရေးထုံးကို အသုံးပြုနိုင်ပါတယ်
* Animal Class ရဲ့ run() Method ကို final လို့ ကြေညာထားတဲ့အတွက် သူ့ကိုဆက်ခံတဲ့
Dog Class က Override လုပ်ပြီးရေးဖို့ကြိုးစားတဲ့အခါ ခွင့်မပြုဘဲ Error ပေးတာကို တွေ့မြင်ရမှာပဲ ဖြစ်ပါတယ်

```
class Animal
{
 final public function run()
 {
 echo "Animal is running...";
 }
}
class Dog extends Animal
{
 public function run()
 {
 echo "The dog is running...";
 }
}
// Error: Cannot override final method
```

*  Class တစ်ခုလုံးကို ဆက်ခံခွင့် မပြုချင်ရင်လည်း final လို့ကြေညာပေးလို့ ရပါသေး
တယ်
* final Class ကနေ Inherit လုပ်လို့မရဘူးဆိုတဲ့ Error ကို ရရှိမှာ ဖြစ်ပါတယ်

```
final class Animal
{
 public function run()
 {
 echo "Animal is running...";
 }
}
class Dog extends Animal
{
 //
}
// Error: may not inherit from final class
```

* Class တွေမှာ Abstract Class ဆိုတာလည်း ရှိပါသေးတယ် 
* ဆက်ခံသူက မဖြစ်မနေ ရေးပေးရမယ့် သတ်မှတ်ချက်တွေကို Abstract Class မှာ ထည့်သတ်မှတ်နိုင်ပါတယ်
* Animal Class ဟာ Abstract Class ဖြစ်သွားပါပြီ
* Abstract Class ဖြစ်သွားရင် Abstract Method တွေလည်း ထည့်ရေးလို့ ရသွားပါပြီ
* talk() ဟာ Abstract Method ဖြစ်ပြီး Code Body မပါတဲ့ Method ကြေညာချက်သက်သက် ဆိုတာကို တွေ့ရမှာပါ
* ဆက်ခံသူတွေက ဒီ Abstract Method အတွက် Code Body ကို Implement လုပ် ရေးပေးရမှာပါ
* Dog Class ဟာ Animal Class ကို ဆက်ခံထားပေမယ့် သတ်မှတ်ထားတဲ့ Abstract Method ကို ဆက်ရေးမပေးလို့ Error ဖြစ်နေတာကို တွေ့မြင်ရမှာပဲ ဖြစ်ပါတယ်

```
abstract class Animal
{
 public abstract function talk();
 public function run()
 {
 echo "Running...";
 }
}
class Dog extends Animal
{
 //
}
// Error: abstract method must be 
// declared or implement the remaining
```

* Abstract Class နဲ့ နည်းနည်းဆင်တဲ့ Interface ရေးထုံးလည်း ရှိပါသေးတယ်
* ကွာသွားတာကတော့ Abstract Class မှာ ရိုးရိုး Method တွေရော Abstract Method တွေရော ထည့်ရေးလို့ ရပေမယ့်၊ Interface ကတော့ Abstract Method တွေချည်းပဲ ရေးလို့ရပါတယ်
* ရိုးရိုး Method တွေ ထည့်ရေးလို့ မရပါဘူး
* လက်တွေ့ပရောဂျက်တွေမှာ ပြုပြင်ထိန်းသိမ်းရလွယ်တဲ့ကုဒ်တွေ ရေးသားဖို့အတွက် အထောက်အကူပြုတဲ့ ရေးနည်းတွေပါ
* Dog နဲ့ Fish ဆိုတဲ့ Class နှစ်ခုရှိပါတယ်
* ဆက်ရေးထားတဲ့ app() Function ကတော့ Dog Object ကို Parameter အနေနဲ့ ပေးရမယ်လို့ ရေးထားတာကိုလည်း တွေ့ရနိုင်ပါတယ် 
* Dog Object ကိုပေးတဲ့ခါ အလုပ်လုပ်ပြီး၊ Fish Object ကိုပေးတဲ့အခါ Error တက်
သွားတာကို တွေ့ရမှာ ဖြစ်ပါတယ်
* Dog Object ပေးရမယ့်နေရာမှာ Dog Object ကိုပဲ အတိအကျပေးရမှာဖြစ်ပါတယ်
* တစ်ခြား Object အမျိုးအစားကို လက်ခံမှာ မဟုတ်ပါဘူး
* Type Hinting ရေးထုံးကိုသုံးထားလို့ ဒီလို Error တက်တာဖြစ်သလို Type Hinting ရေးထုံးကို မသုံးရင်လည်း Error တက်မှာပါပဲ
* ပေးလိုက်တဲ့ Fish Object မှာ app() Function က အသုံးပြုလိုတဲ့ run() Method မရှိလို့ပါ

```
class Dog
{
 public function run()
 {
 echo "The dog is running";
 }
}
class Fish
{
 public function swim()
 {
 echo "The fish is swimming";
 }
}
function app(Dog $obj) {
 $obj->run();
}
app(new Dog); // The dog is running
app(new Fish); // Error: Argument must be Dog
```

* Interface ကိုအသုံးပြုလို့ရပါတယ်
* အတိအကျ မတူပေမယ့် အမျိုးအစားဆင်တူတဲ့ Object တွေ တည်ဆောက်ဖို့အတွက် Interface ကိုသုံးရတာပါ
* Animal Interface ပါဝင်သွားပါပြီ
* အထဲမှာ Abstract Method move() ကို ကြေညာထားပါတယ်
* Abstract Class မှာရိုးရိုး Method နဲ့ Abstract Method ကိုခွဲခြားနိုင်ဖို့ abstract Keyword ကို သုံးရပေမယ့် Interface မှာတော့ Abstract Method တွေပဲ ရေးလို့ရတာမို့လို့ ခွဲခြားပေးစရာမလိုတော့လို့ abstract Keyword ထည့်သုံးစရာ မလိုတော့ပါဘူး
* Dog Class နဲ့ Fish Class တို့ဟာ အမျိုးအစား မတူကြပေမယ့် Implement လုပ်ထားတဲ့ Interface တူကြပါတယ် 
* Interface တစ်ခုကို Implement လုပ်ပြီဆိုရင် Interface ကသတ်မှတ်ထားတဲ့ Method တွေကို
ရေးပေးရပါတယ်
* Dog Class ရော Fish Class မှာပါ move() Method ရှိပါတယ်
* app() Function က Animal Object ကို လက်ခံမယ်လို့ သတ်မှတ်ထားပါတယ်
* Animal Interface ကနေဆက်ခံဖြစ်ပေါ်လာတဲ့ Dog Object ကိုပေးတဲ့အခါ အလုပ်လုပ်သွားသလို
Animal Interface ကနေပဲ ဆက်ခံဖြစ်ပေါ်လာတဲ့ Fish Object ကို ပေးတဲ့အ]ါမှာလည်း အလုပ်လုပ်သွားတာကို တွေ့မြင်ရမှာပဲ ဖြစ်ပါတယ်။
* Interface ကိုအသုံးပြုပြီး အမျိုးအစားမတူပေမယ့်၊ Interface တူတဲ့ Object တွေကို ဖလှယ်
အစားထိုး အသုံးပြုလို့ရရှိနိုင်သွားမှာပါ

```
interface Animal
{
 public function move();
}
class Dog implements Animal
{
 public function move()
 {
 echo "The dog is running";
 }
}
class Fish implements Animal
{
 public function move()
 {
 echo "The fish is swimming";
 }
}
function app(Animal $obj) {
 $obj->move();
}
app(new Dog); // The dog is running
app(new Fish); // The fish is swimming
```

* Inheritance မှာ Multiple Inheritance ခွင့်မပြုပေမယ့် Interface မှာတော့ Interface နှစ်ခုသုံးခုကို Implement လုပ်တာကို လက်ခံပါတယ်
* Cow Class ဟာ Animal Interface နဲ့ Livestock Interface နှစ်ခုကို Implement လုပ်ထား
တာကို တွေ့ရမှာဖြစ်ပါတယ်
* Interface နှစ်ခုလုံးမှာ သတ်မှတ်ထားတဲ့ Abstract Method တွေဖြစ်ကြတဲ့ move() နဲ့ isFriendly() တို့ကို ပြည့်စုံအောင် Cow Class မှာ ရေးပေးရမှာပါ

```
interface Animal
{
 public function move();
}
interface Livestock
{
 public function isFriendly();
}
class Cow implements Animal, Livestock
{
 public function move()
 {
 echo "The cow is walking";
 }
 public function isFriendly()
 {
 return true;
 }
}
```

* Multiple Inheritance ကို ခွင့်မပြုတဲ့အတွက်ကြောင့် အစားထိုးထည့်သွင်းပေးထားတဲ့
လုပ်ဆောင်ချက်တစ်ခု ရှိပါတယ်
* Traits လို့ခေါ်ပါတယ်
* Multiple Inheritance မရလို့ Class နှစ်ခုသုံးခုက လုပ်ဆောင်ချက်တွေကို တစ်ခါထဲ ဆက်ံလို့မရဘူး ဖြစ်နေတယ် ဒါကြောင့် တူညီတဲ့ကုဒ်တွေပြန်ရေးရမလို ဖြစ်နေနိုင်ပါတယ်
* တွက်ချက်မှုတွေ လုပ်ပေးနိုင်တဲ့ Math Class နဲ့ Area Class တို့ရှိနေပါတယ်
* Calculator Class က နှစ်ခုလုံးရဲ့လုပ်ဆောင်ချက်တွေကို ဆက်ရေံ းသားချင်ပေမယ့် Multiple Inheritance မရလို့ မရနိုင်ဘူး ဖြစ်နေပါတယ်
* နှစ်ခုထဲက တစ်ခုပဲ ရပါတော့မယ်

```
class Math
{
 public function add($a, $b)
 {
 echo $a + $b;
 }
}
class Area
{
 private $PI = 3.14;
 public function circle($r)
{
 echo $this->PI * $r * $r;
 }
}
class Calculator extends Math // and Area
{
 //
}
```

* ဒီလို အခြေအနေမျိုးမှာ Traits ကို အသုံးပြုနိုင်ပါတယ်
* Math နဲ့ Area တို့ဟာ Class တွေ မဟုတ်ကြတော့ပါဘူး
* လိုတဲ့ Class ကနေ ခေါ်သုံးလို့ရတဲ့ Traits တွေ ဖြစ်သွားကြပါပြီ
* Calculator Class မှာ use Statement နဲ့ ခေါ်ပေးလိုက်တဲ့အခါ Math နဲ့
Area နှစ်ခုလုံးရဲ့လုပ်ဆောင်ချက်တွေကို Calculator Class က ရရှိသွားတာကို တွေ့ရမှာပဲ ဖြစ်ပါတယ်

```
trait Math
{
 public function add($a, $b)
 {
 echo $a + $b;
 }
}
trait Area
{
 private $PI = 3.14;
 public function circle($r)
 {
 echo $this->PI * $r * $r;
 }
}
class Calculator
{
 use Math, Area;
}
$calc = new Calculator;
$calc->add(1, 2); // 3
$calc->circle(5); // 78.5
```