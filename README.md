<?php
flush();
ob_start();
##########
$token = " 2096867407:AAGtZwjeVJRkSOiCJLYEKFaMZkNIf_68VXA";// حط توكنك
$kindi = "2096867407:AAGtZwjeVJRkSOiCJLYEKFaMZkNIf_68VXA";// حط توكن الاشتراك الاجباري

$buy = "xi_82";// معرفك بدون @
$userbot ="xnxtyibot";// حط بوتك
$sudo = " 736595861";// ايديك 
$admin = "$sudo";// لاتغير شي
$idBot = "2096867407";// ايدي بوتك 
$admmm = $sudo;// لاتغير
$ADMIN = $sudo;// لاتغير
$Dev = array("$sudo","736595861");// ايديك مكان 000
$Devd = "$sudo";// لاتغير 
$tbbots = xnxtyibot;// معرف بوتك
 
$channel = "MitQx1";// قنانك بدون @
$chinnl = "$channel";// لاتغير
$DevUser = "@$buy"; // 
$Devch = "@$buy"; //  
$Userbot = "$tbbots"; // 
//~~~~~~~~//
define('API_KEY',$token);
echo "setWebhook ~> <a href=\"https://api.telegram.org/bot".API_KEY."/setwebhook?url=".$_SERVER['SERVER_NAME']."".$_SERVER['SCRIPT_NAME']."\">https://api.telegram.org/bot".API_KEY."/setwebhook?url=".$_SERVER['SERVER_NAME']."".$_SERVER['SCRIPT_NAME']."</a>";
function bot($method,$datas=[]){
    $url = "https://api.telegram.org/bot".API_KEY."/".$method;
$ch = curl_init();
    curl_setopt($ch,CURLOPT_URL,$url);
    curl_setopt($ch,CURLOPT_RETURNTRANSFER,true);
    curl_setopt($ch,CURLOPT_POSTFIELDS,$datas);
    $res = curl_exec($ch);
    if(curl_error($ch)){
        var_dump(curl_error($ch));
    }else{
        return json_decode($res);
    }
}

$update = json_decode(file_get_contents('php://input'));
@$message = $update->message;
@$from_id = $message->from->id;
@$chat_id = $message->chat->id;
@$message_id = $message->message_id;
@$first_name = $message->from->first_name;
@$last_name = $message->from->last_name;
@$username = $message->from->username;
@$text= $message->text;
@$firstname = $update->callback_query->from->first_name;
@$usernames = $update->callback_query->from->username;
@$chatid = $update->callback_query->message->chat->id;
@$fromid = $update->callback_query->from->id;
@$membercall = $update->callback_query->id;
@$reply = $update->message->reply_to_message->forward_from->id;
/*===== dev ~ @MitQx1 =====*/
@$data = $update->callback_query->data;
@$messageid = $update->callback_query->message->message_id;
@$tc = $update->message->chat->type;
@$gpname = $update->callback_query->message->chat->title;
@$namegroup = $update->message->chat->title;
/*===== dev ~ @MitQx1 =====*/
@$newchatmemberid = $update->message->new_chat_member->id;
@$newchatmemberu = $update->message->new_chat_member->username;
@$rt = $update->message->reply_to_message;
@$replyid = $update->message->reply_to_message->message_id;
@$tedadmsg = $update->message->message_id;
@$edit = $update->edited_message->text;
@$re_id = $update->message->reply_to_message->from->id;
@$re_user = $update->message->reply_to_message->from->username;
@$re_name = $update->message->reply_to_message->from->first_name;
@$re_msgid = $update->message->reply_to_message->message_id;
@$re_chatid = $update->message->reply_to_message->chat->id;
@$message_edit_id = $update->edited_message->message_id;
@$chat_edit_id = $update->edited_message->chat->id;
@$edit_for_id = $update->edited_message->from->id;
@$edit_chatid = $update->callback_query->edited_message->chat->id;
@$caption = $update->message->caption;
/*===== dev ~ @MitQx1 =====*/
@$statjson = json_decode(file_get_contents("https://api.telegram.org/bot$token/getChatMember?chat_id=$chat_id&user_id=".$from_id),true);
@$status = $statjson['result']['status'];
@$statjsonrt = json_decode(file_get_contents("https://api.telegram.org/bot$token/getChatMember?chat_id=$chat_id&user_id=".$re_id),true);
@$statusrt = $statjsonrt['result']['status'];
@$statjsonq = json_decode(file_get_contents("https://api.telegram.org/bot$token/getChatMember?chat_id=$chatid&user_id=".$fromid),true);
@$statusq = $statjsonq['result']['status'];
@$info = json_decode(file_get_contents("https://api.telegram.org/bot$token/getChatMember?chat_id=$chat_edit_id&user_id=".$edit_for_id),true);
@$you = $info['result']['status'];
@$forchannel = json_decode(file_get_contents("https://api.telegram.org/bot".$token."/getChatMember?chat_id=@".$channel."&user_id=".$from_id));
@$tch = $forchannel->result->status;
/*===== dev ~ @MitQx1 =====*/
@$settings = json_decode(file_get_contents("data/$chat_id.json"),true);
@$settings2 = json_decode(file_get_contents("data/$chatid.json"),true);
@$editgetsettings = json_decode(file_get_contents("data/$chat_edit_id.json"),true);
@$user = json_decode(file_get_contents("data/user.json"),true);
@$filterget = $settings["filterlist"];

$mem = bot('getchatmemberscount',['chat_id'=>$chat_id])->result;
$cmg = file_get_contents("data/count/$chat_id.txt");
$cmssg = explode("\n",$cmg);
$cmsg = count($cmssg);

if ($tc == 'private'){  
@$user = json_decode(file_get_contents("data/user.json"),true);
if(!in_array($from_id, $user["userlist"])) {
$user["userlist"][]="$from_id";
$user = json_encode($user,true);
file_put_contents("data/user.json",$user);
}
}
elseif ($tc == 'group' | $tc == 'supergroup'){  
@$user = json_decode(file_get_contents("data/user.json"),true);
if(!in_array($chat_id, $user["grouplist"])) {
$user["grouplist"][]="$chat_id";
$user = json_encode($user,true);
file_put_contents("data/user.json",$user);
}
}
$re = $update->message->reply_to_message;
$re_id = $update->message->reply_to_message->from->id;

$grouplisturl = $user["grouplist"];
if ($tc == 'group' | $tc == 'supergroup'){
@$user = json_decode(file_get_contents("data/user.json"),true);
if(!in_array($chat_id, $user["grouplist"])) {
$user["grouplist"][]="$chat_id";
$user = json_encode($user,true);
file_put_contents("data/user.json",$user);
}
}
$grouplisturl = $user["grouplist"];
if( $text == "الروابط" or $text == "⌯ روابط الكروبات" or $text == "قائمة روابط الكروبات" or $text == "قائمه روابط الكروبات" or $text == "قائمة الروابط" and $settings["silentlist"]!== NULL){
if (in_array($from_id,$Dev) or in_array($from_id,$eri)) {
$grouplisturl = $user["grouplist"];
for($z = 0;$z <= count($grouplisturl)-1;$z++){
$groupinlink = json_decode(file_get_contents("https://api.telegram.org/bot".API_KEY."/exportChatInviteLink?chat_id=$grouplisturl[$z]"));
$grouplinkem = $groupinlink->result;
$result = $result."┇$z-$grouplinkem"."\n";
}
bot('sendMessage',[
'chat_id'=>$chat_id,
'text'=>"📋¦ قائمه الروابط/للكروبات :
┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉
-$result",
]);
}
}
######
include "k.php";
###########
if( $text=="/start" &&  $tc == "private" or $text=="رجوع" &&  $tc == "private" ){
if(in_array($from_id,$Dev) or in_array($from_id,$developer)){
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
⌯⁞ آهہ‌‏لآ عزيزي آلمـطـور !
⌯⁞ آنتهہ‌‏ آلمـطـور آلآسـآسـي هہ‌‏نآ 
────────────────
⌯⁞ CH ⋙ **[ᴛᴇᴀᴍ ɴɪᴢᴋ](https://t.me/MitQx1)** 💥
⌯⁞ CH ⋙ **[Ͳᴇᴀᴍ ʏᴇᴍᴇɴ](t.me/PT2PP)** 🇸🇦
────────────
⌯⁞ تسـتطـيع‌‏ آلتحكم بكل آلآوآمـر آلمـمـوجودهہ‌‏ بآلكيبورد
⌯⁞ فقط آضـغط ع آلآمـر آلذي تريد تنفيذهہ‌‏",
'parse_mode'=>"markdown",
'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'keyboard'=>[
[['text'=>"⌯ روابط الكروبات"]],
[['text'=>"⌯ تحديث"],['text'=>"⌯ تحديث السورس"]],
[['text'=>"⌯ حظر مجموعه"]],
[['text'=>"⌯ تغير اسم البوت"],['text'=>"⌯ تغير كليشة مطور"]],
[['text'=>"⌯ قسم الاذاعة والاحصائيات"]],

[['text'=>"⌯ تفعيل التنبيه"],['text'=>"⌯ تعطيل التنبيه"]],
[['text'=>"⌯ قسم التواصل"]],
[['text'=>"⌯ تفعيل start"],['text'=>"⌯ تعطيل start"]],
[['text'=>"⌯ جلب start"]],
[['text'=>"⌯ اضف رد عام"],['text'=>"⌯ الردود العامة"]],
[['text'=>"⌯ مسح الردود العامة"],['text'=>"⌯ مسح رد عام"]],

[['text'=>"⌯ قسم الاشتراك الاجباري"]],

],
'resize_keyboard'=>true
])
]);
}
}
if( $text=="⌯ قسم التواصل"){
if(in_array($from_id,$Dev) or in_array($from_id,$eri)){
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"✵ مرحبا ⋙ [$first_name](tg://user?id=$from_id)
⌯ انت الان في القسم العام بالتواصل
➖
",'parse_mode'=>"markdown",
'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'keyboard'=>[
[['text'=>"⌯ جلب التواصل"]],
[['text'=>"⌯ تعين رد التواصل"],['text'=>"⌯ حذف رد التواصل"]],
[['text'=>"⌯ تعطيل التواصل"],['text'=>"⌯ تفعيل التواصل"]],
[ ['text'=>"رجوع"] ],
],
'resize_keyboard'=>true
])
]);
}
}
if( $text=="⌯ قسم الاذاعة والاحصائيات"){
if(in_array($from_id,$Dev) or in_array($from_id,$eri)){
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"✵ مرحبا ⋙ [$first_name](tg://user?id=$from_id)
⌯ انت الان في القسم الاحصائيات و الاذاعه",
'parse_mode'=>"markdown",
'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'keyboard'=>[
[['text'=>"⌯ الاحصائيات"]],
[['text'=>"⌯ اذاعه خاص بالتوجيه"]],
[['text'=>"⌯ اذاعه عام"],['text'=>"⌯ اذاعه خاص"]],
[['text'=>"⌯ اذاعه عام بالتوجيه"]],
[['text'=>"⌯ المجموعات"]],
[['text'=>"⌯ المشتركين"]],
[ ['text'=>"رجوع"]],
],
'resize_keyboard'=>true
])
]);
}
}
if($text=="⌯ قسم الاشتراك الاجباري"){
if(in_array($from_id,$Dev) or in_array($from_id,$eri)){
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"✵ مرحبا ⋙ [$first_name](tg://user?id=$from_id)
⌯ انت الان في القسم الاشتراك الاجباري",
'parse_mode'=>'MarkDown',
'reply_to_message_id'=>$message_id, 
'reply_markup'=>json_encode([
'keyboard'=>[
[['text'=>"حذف قناة الاشتراك"],['text'=>"تعيين قناة الاشتراك"]],
[['text'=>"جلب قناة الاشتراك"]],
[['text'=>"⌯ تعطيل الاشتراك الاجباري"]],
[['text'=>"⌯ تفعيل الاشتراك الاجباري"]],
[ ['text'=>"رجوع"]],
],
'resize_keyboard'=>true
])]);}
}

$developers_info = file_get_contents("data/developers/developer.txt");
$developer = explode ("\n",$developers_info);
$developers_infos = file_get_contents("data/developers/developers.txt");
$developers = explode("\n",$developers_infos);
$list_developers ="";
$list_developers = $list_developers.""."$developers_infos ➖➖➖➖➖➖➖";
/*===== dev ~ @MitQx1 =====*/
$nazarr_info = file_get_contents("data/nazar/$chat_id.txt");
$nazar  = explode("\n",$nazarr_info);
$nazarr_infos = file_get_contents("data/nazar/$chat_id/nazr.txt");
$nazarr = explode ("\n",$nazarr_infos);
/*===== dev ~ @MitQx1 =====*/
$carloss_info = file_get_contents("data/carlos/$chat_id.txt");
$carlos  = explode("\n",$carloss_info);
$carloss_infos = file_get_contents("data/carlos/$chat_id/crlo.txt");
$carloss = explode ("\n",$carloss_infos);
/*===== dev ~ @MitQx1 =====*/
$mangers_info = file_get_contents("data/manger/$chat_id.txt");
$manger  = explode("\n",$mangers_info);
$mangers_infos = file_get_contents("data/manger/$chat_id/mange.txt");
$mangers = explode ("\n",$mangers_infos);
/*===== dev ~ @MitQx1 =====*/
$admin_users_info = file_get_contents("data/admin_user/$chat_id.txt");
$admin_user  = explode("\n",$admin_users_info);
$admin_users_infos = file_get_contents("data/admin_user/$chat_id/mange.txt");
$admin_users = explode ("\n",$admin_users_infos);
/*===== dev ~ @MitQx1 =====*/
$mmyazs_info = file_get_contents("data/mmyaz/$chat_id.txt");
$mmyaz  = explode("\n",$mmyazs_info);
$mmyazs_infos = file_get_contents("data/mmyaz/$chat_id/mange.txt");
$mmyazs = explode ("\n",$mmyazs_infos);
/*===== dev ~ @MitQx1 =====*/
mkdir("data");
mkdir("data/developers");
mkdir("data/nazar");
mkdir("data/nazar/$chat_id");
mkdir("data/carlos");
mkdir("data/carlos/$chat_id");
mkdir("data/manger");
mkdir("data/manger/$chat_id");
mkdir("data/admin_user");
mkdir("data/admin_user/$chat_id");
mkdir("data/mmyaz");
mkdir("data/mmyaz/$chat_id");
mkdir("statistics");
mkdir("SudoOrders");

$setch = file_get_contents("SudoOrders/setch.txt");
$setchannel = file_get_contents("SudoOrders/setchannel.txt");
if($text == "تفعيل" or $text == "حظر" or $text == "ايدي" or $text == "كتم" or $text == "تقيد" or $text == "الاوامر" or $text == "الاعدادات" or $text == "رتبتي" or $text == "كشف" or $text == "الرتبه" or $text == "رتبته" or $text == "اضف رد" or $text == "حذف رد" or $text == "تاك" or $text == "حذف امر" or $text == "اضف امر" or $text == "تاك للكل" or $text == "/start" or $text == "الاوامر" or $text == "م1" or $text == "م2" or $text == "م3" or $text == "م4" or $text == "م5" or $text == "اوامر التحشيش"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer)) {if ($tc == 'group' | $tc == 'supergroup'){
$add = $settings["information"]["added"];
if ($add == true){
if($setchannel == "الاشتراك الاجباري مفعل"){
$join = file_get_contents("https://api.telegram.org/bot".$kindi."/getChatMember?chat_id=@$setch&user_id=".$from_id);
if($message && (strpos($join,'"status":"left"') or strpos($join,'"Bad Request: USER_ID_INVALID"') or strpos($join,'"status":"kicked"'))!== false){
bot('sendMessage',[
'chat_id'=>$chat_id,
'text'=>"*⌯ مرحبا بگ عزيزي ،
⌯ لا يمڪنـك استخدام البوت ،
⌯ عليك الإشتراگ في قناة البوت ،
⌯ القناة ~⪼ ❪ @$setch ❫️ ؛*
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>"⌯ للاشتراك اضغط هنا",'url'=>"t.me/$setch"]],]])]);
 bot("sendmessage",[
      "chat_id"=>$Devd,
      "text"=>"⌯⁞  مرحبأ عزيزي المطور 
━━━━━━━━━━━━━
⌯⁞ اليك معلومات العضو قام بدخول قناة

⌯⁞ اسم العضو ~⪼ $first_name
⌯⁞ معرف العضو ~⪼ @$username
⌯⁞ ايدي العضو ~⪼ $from_id
━━━━━━━━━━━━━
⌯⁞ قناة الاشتراك الاجباري ~⪼ @$setch",
      ]);
      die('اا');
  }
bot('sendMessage',['chat_id'=>$chat_id, 'text'=>" ",'reply_to_message_id'=>$message->message_id,]);}}}}}

if(in_array($from_id,$eri)){
$info = "مطور السورس";
}
elseif(in_array($from_id,$developer) ){
$info = "مطور البوت";
}
elseif(in_array($from_id,$Dev) ){
$info = "مطور الاساسي";
}
elseif(in_array($from_id,$nazar) ){
$info = "منشئ اساسي";
}
elseif(in_array($from_id,$carlos) ){
$info = "منشئ";
}
elseif($status == "creator"){
$info = "المالك";
}
elseif($status == "administrator"){
$info = "المشرف";
}
elseif(in_array($from_id,$manger) ){
$info = "المدير";
}
elseif(in_array($from_id,$admin_user) ){
$info = "ادمن";
}
elseif(in_array($from_id,$mmyaz) ){
$info = "عضو مميز";
}elseif($status == "member" ){
$info = "عضو فقط";
}
if(!@$username){
$casss = "لايوجد يوزر";
}elseif(@$username){
$casss = "@$username";
}
if($text=="رتبتي" ){
bot('sendmessage',[
'chat_id'=>$chat_id, 
'text'=>"
⌯⁞ ايديك ↫ $from_id ،
⌯⁞ معرفك ↫ $casss ،
⌯⁞ رتبتك ↫ $info ،
",
'parse_mode'=>"html",
'reply_to_message_id'=>$message->message_id,
]);
}
/*===== dev ~ @MitQx1 =====*/
$type = $update->message->chat->type;
$from_id = $message->from->id;
$chat_id = $message->chat->id;
$statjson = json_decode(file_get_contents("https://api.telegram.org/bot".$API_KEY."/getChatMember?chat_id=".$chat_id."&user_id=".$from_id),true);
$status = $statjson['result']['status'];
$BGBBB = json_decode(file_get_contents("BGBBB.json"),true);
if($text){
if($BGBBB[$chat_id][$text]){
$text = $BGBBB[$chat_id][$text] or $text;
}
}
if ($type == 'group' || $type == 'supergroup'){
if ( $status == 'creator' or in_array($from_id,$Dev) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$nazar) or in_array($from_id,$eri)) {
if($text == "حذف امر"){
$aa ="⌯⁞ ارسل الامر القديم الان .";
bot("sendmessage",[
"chat_id"=>$chat_id,
"text"=>$aa,'parse_mode'=>"Markdown",
'reply_to_message_id'=>$message->message_id,
]);
$BGBBB["trued"][$chat_id][$from_id]="true";
file_put_contents("BGBBB.json",json_encode($BGBBB,true));
}
if($text != "حذف امر" and $BGBBB["trued"][$chat_id][$from_id]=="true"){
$BGBBB["trued"][$chat_id][$from_id]="true1";
file_put_contents("BGBBB.json",json_encode($BGBBB,true));
$aa ="⌯⁞ تم حذف الامر بنجاح .";
bot("sendmessage",[
"chat_id"=>$chat_id,
"text"=>$aa,'parse_mode'=>"Markdown",
'reply_to_message_id'=>$message->message_id,
]);
$key = array_search($BGBBB[$chat_id][$BGBBB[$chat_id][$text]],$BGBBB[$chat_id]["List"]);
unset($BGBBB[$chat_id]["List"][$key]);
$BGBBB[$chat_id]["List"] = array_values($BGBBB[$chat_id]["List"]);
unset($BGBBB[$chat_id][$BGBBB[$chat_id][$text]]);
unset($BGBBB[$chat_id][$text]);
unset($BGBBB["trued"][$chat_id][$from_id]);
unset($BGBBB["trued"][$chat_id]);
file_put_contents("BGBBB.json",json_encode($BGBBB,true));
}
if($text == "اضف امر"){
$aa ="⌯⁞ ارسل الامر القديم الان .";
bot("sendmessage",[
"chat_id"=>$chat_id,
"text"=>$aa,'parse_mode'=>"Markdown",
'reply_to_message_id'=>$message->message_id,
]);
$BGBBB["true"][$chat_id][$from_id]="true";
file_put_contents("BGBBB.json",json_encode($BGBBB,true));
}
if($text != "اضف امر" and $BGBBB["true"][$chat_id][$from_id]=="true"){
$BGBBB["true"][$chat_id][$from_id]="true1";
file_put_contents("BGBBB.json",json_encode($BGBBB,true));
$aa ="⌯⁞ ارسل الامر الجديد الان .";
bot("sendmessage",[
"chat_id"=>$chat_id,
"text"=>$aa,'parse_mode'=>"Markdown",
'reply_to_message_id'=>$message->message_id,
]);
$BGBBB["true"][$chat_id]["c"]=$text;
file_put_contents("BGBBB.json",json_encode($BGBBB,true));
}
$recv = $BGBBB["true"][$chat_id]["c"];
if($text != $BGBBB["true"][$chat_id]["c"] and $BGBBB["true"][$chat_id][$from_id]== "true1"){
$aa ="⌯⁞ تم حفظ الامر بنجاح .";
bot("sendmessage",[
"chat_id"=>$chat_id,
"text"=>$aa,'parse_mode'=>"Markdown",
'reply_to_message_id'=>$message->message_id,
]);
$BGBBB[$chat_id]["List"][]=$text;
$BGBBB[$chat_id][$recv] = $text;
$BGBBB[$chat_id][$text]= $BGBBB["true"][$chat_id]["c"];
unset($BGBBB["true"][$chat_id]);
file_put_contents("BGBBB.json",json_encode($BGBBB,true));
}
if($text == "مسح الاوامر المضافه"){
$aa ="⌯⁞ تم مسح الاوامر المضافه .";
bot("sendmessage",[
"chat_id"=>$chat_id,
"text"=>$aa,'parse_mode'=>"Markdown",
'reply_to_message_id'=>$message->message_id,
]);
for($j=0;$j<count($BGBBB[$chat_id]["List"]); $j++){
$deal = $BGBBB[$chat_id]["List"][$j];
$d = $BGBBB[$chat_id][$deal];
unset($BGBBB[$chat_id][$d]);
unset($BGBBB[$chat_id][$deal]);
}
unset($BGBBB[$chat_id]["List"]);
file_put_contents("BGBBB.json",json_encode($BGBBB,true));
}
if($text == "الاوامر المضافه" ){
if(!$BGBBB[$chat_id]["List"]){
$aa ="⌯⁞ لا يوجد اوامر مضافه";
bot("sendmessage",[
"chat_id"=>$chat_id,
"text"=>$aa,'parse_mode'=>"Markdown",
'reply_to_message_id'=>$message->message_id,
]);
}
}
if($text == "الاوامر المضافه"){
if($BGBBB[$chat_id]["List"]){
for($j=0;$j<count($BGBBB[$chat_id]["List"]); $j++){
$Eq = $BGBBB[$chat_id]["List"][$j];
$dr = $BGBBB[$chat_id][$Eq];
$msg = $msg. $j."- ".$Eq." ~ ( ".$dr." ) \n";
}
$j = "⌯⁞ قائمه الاوامر المضافه هي :  — — — — — — — — —
".$msg;
bot("sendmessage",[
"chat_id"=>$chat_id,
"text"=>$j,'parse_mode'=>"Markdown",
'reply_to_message_id'=>$message->message_id,
]);
}
}
}
}
/*===== dev ~ @MitQx1 =====*/
if($re and $text == "رفع مطور" and $re_id !=$id_Bot and  in_array($from_id,$Dev) || in_array($from_id,$eri) and !in_array($re_id,$developer)){
file_put_contents("data/developers/developer.txt",$re_id ."\n " , FILE_APPEND);
file_put_contents("data/developers/developers.txt",'[@'.$re_user ."]". "\n " , FILE_APPEND);
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ↫「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` ، 
⌯⁞ تم ترقية ليصبح مطور
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
elseif($re and $text == "رفع مطور"  and $re_id !=$id_Bot and in_array($from_id,$Dev) and  in_array($from_id,$eri) and in_array($re_id,$developer)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」 
⌯⁞ ايديه ↫ `$re_id`
⌯⁞ هوا بالفعل مطور
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if(in_array($from_id,$Dev) || in_array($from_id,$eri)){
if($re and $text == "تنزيل مطور" and in_array($re_id,$developer)){
$re_id_info = file_get_contents("data/developers/$chat_id.txt");
$devr = file_get_contents("data/developers/$chat_id/developer.txt");
$devr1 = explode("             \n",$devr);
$str = str_replace($re_id,"",$re_id_info);
$str2 = str_replace("⌯ ❨ [" . "@". $re_user ."] ❩ " . "•" . " ❨ `". $re_id ."` ❩ ","",$devr1);
file_put_contents("data/developers/developer.txt",$str);
file_put_contents("data/developers/developers.txt",$str);
bot('SendMessage',['chat_id'=>$chat_id, 'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم تنزيله من قائمة المطورين
", 'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true, ]); }}

if(in_array($from_id,$Dev)){
if($re and $text == "تنزيل مطور" and !in_array($re_id,$developer)){
bot('SendMessage',['chat_id'=>$chat_id, 'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ هو ليس مطور ليتم تنزيله
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true, ]); } }

if($text == "مسح المطورين" and   in_array($from_id,$Dev)){
			file_put_contents("data/developers/developer.txt"," ");
			file_put_contents("data/developers/developers.txt"," ");
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ عزيزي ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ تم مسح قائمة المطورين
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المطورين"  and   in_array($from_id,$Dev) and $developers_info != NULL and $developers_info != " "){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"✵⁞ اليك قائمة ⋙ المطورين
$list_developers
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المطورين" and   in_array($from_id,$Dev) and $developers_info == NULL || $developers_info == " "){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ عزيزي ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ لايوجد مطور حالين
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}

if($status == "creator" ||  in_array($from_id,$Dev) || in_array($from_id,$developer) || in_array($from_id,$eri)) {
if($re and $text == "رفع منشئ اساسي" || $text == "رفع المنشئ اساسي"  and !in_array($re_id,$manger)){
			file_put_contents("data/nazar/$chat_id.txt",$re_id . "\n" , FILE_APPEND);
			file_put_contents("data/nazar/$chat_id/nazr.txt" , " *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ". "\n" , FILE_APPEND);
bot('SendMessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم ترقية ليصبح منشئ اساسي
"
,'parse_mode'=>'markdown',
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
]);
}
elseif($re and $text == "رفع منشئ اساسي" || $text == "رفع المنشئ اساسي" and in_array($re_id,$nazar)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ هوا بالفعل منشئ اساسي
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "مسح المنشئين الاساسي" ){
file_put_contents("data/nazar/$chat_id.txt","");
file_put_contents("data/nazar/$chat_id.txt","");
file_put_contents("data/nazar/$chat_id/nazr.txt" ,"");
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطة ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ تم مسح قائمة المنشئين الاساسي
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,  
]);
}

if($re and $text == "تنزيل المنشئ اساسي" || $text == "تنزيل منشئ اساسي"  and in_array($re_id,$nazar)){
	$re_id_info = file_get_contents("data/nazar/$chat_id.txt");
	$mdrs = file_get_contents("data/nazar/$chat_id/nazr.txt");
	$mdrs1 = explode("             \n",$mdrs);
	$str = str_replace($re_id,"",$re_id_info);
	$str2 = str_replace(" *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ","",$mdrs1);
	file_put_contents("data/nazar/$chat_id.txt",$str);
	file_put_contents("data/nazar/$chat_id/nazr.txt",$str2);
	bot('SendMessage',['chat_id'=>$chat_id,
    'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم تنزيله من قائمة المنشئين الاساسي
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($re and $text == "تنزيل المنشئ اساسي" || $text == "تنزيل منشئ اساسي" || $text == "ت م ا" || $text == "تنما" and !in_array($re_id,$nazar)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ هوا ليس منشئ اساسي ليتم تنزيله
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المنشئين الاساسي" || $text == "قائمه المنشئين الاساسي" and $nazarr_info != NULL and $nazarr_info != " "){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"✵⁞ اليك قائمة ⋙ المشئين الاساسي
$nazarr_infos\n",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المنشئين الاساسي" ||  $text == "قائمه المنشيئن الاساسي" and $nazarr_info == NULL || $nazarr_info == " " || $nazarr_info == ""){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ عزيزي ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ لايوجد اي منشئ اساسي
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
}

if($status == "creator" ||  in_array($from_id,$Dev) || in_array($from_id,$developer) || in_array($from_id,$eri) || in_array($from_id,$nazar)) {
if($re and $text == "رفع منشئ" || $text == "رفع المنشئ"  and !in_array($re_id,$manger)){
			file_put_contents("data/carlos/$chat_id.txt",$re_id . "\n" , FILE_APPEND);
			file_put_contents("data/carlos/$chat_id/crlo.txt" , " *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ". "\n" , FILE_APPEND);
bot('SendMessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم ترقية ليصبح منشئ
",'parse_mode'=>'markdown',
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
]);
}
elseif($re and $text == "رفع منشئ" || $text == "رفع المنشئ" || $text == "رفع منشئ" || $text == "رفع المنشئ" and in_array($re_id,$carlos)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ هوا بالفعل منشئ 
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "مسح المنشيئن" ){
file_put_contents("data/carlos/$chat_id.txt","");
file_put_contents("data/carlos/$chat_id.txt","");
file_put_contents("data/carlos/$chat_id/crlo.txt" ,"");
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ عزيزي ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ تم مسح قائمة المنشئين
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,  
]);
}

if($re and $text == "تنزيل المنشئ" || $text == "تنزيل منشئ"  and in_array($re_id,$carlos)){
	$re_id_info = file_get_contents("data/carlos/$chat_id.txt");
	$mdrs = file_get_contents("data/carlos/$chat_id/crlo.txt");
	$mdrs1 = explode("             \n",$mdrs);
	$str = str_replace($re_id,"",$re_id_info);
	$str2 = str_replace(" *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ","",$mdrs1);
	file_put_contents("data/carlos/$chat_id.txt",$str);
	file_put_contents("data/carlos/$chat_id/crlo.txt",$str2);
	bot('SendMessage',['chat_id'=>$chat_id,
    'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم تنزيله من قائمة المنشئين
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($re and $text == "تنزيل المنشئ" || $text == "تنزيل منشئ" || $text == "ت م" || $text == "تنم" and !in_array($re_id,$carlos)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ ليس منشئ ليتم تنزيله 
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المنشئين" || $text == "قائمه المنشئين" and $carloss_info != NULL and $carloss_info != " "){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"✵⁞ اليك قائمة ⋙ المشئينن
$carloss_infos\n",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المنشيئن" ||  $text == "قائمه المنشيئن" and $carloss_info == NULL || $carloss_info == " " || $carloss_info == ""){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"✵⁞ عزيزي ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ لايوجد منشئ حاليأ
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
}

if($status == "creator" ||  in_array($from_id,$Dev) || in_array($from_id,$developer) || in_array($from_id,$carlos) || in_array($from_id,$eri)  || in_array($from_id,$nazar)) {
if($re and $text == "رفع مدير" || $text == "رفع المدير"  || $text == "ر مدير"  and !in_array($re_id,$manger)){
			file_put_contents("data/manger/$chat_id.txt",$re_id . "\n" , FILE_APPEND);
			file_put_contents("data/manger/$chat_id/mange.txt" , " *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ". "\n" , FILE_APPEND);
bot('SendMessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم ترقية ليصبح مدير
",'parse_mode'=>'markdown',
'reply_to_message_id'=>$message->message_id,
'disable_web_page_preview'=>true,
]);
}
elseif($re and $text == "رفع مدير" || $text == "رفع المدير" and in_array($re_id,$manger)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ هوا بالفعل مدير
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "مسح المدراء" ){
file_put_contents("data/manger/$chat_id.txt","");
file_put_contents("data/manger/$chat_id.txt","");
file_put_contents("data/manger/$chat_id/mange.txt" ,"");
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطة ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ تم مسح قائمة المدراء
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,  
]);
}

if($re and $text == "تنزيل المدير" || $text == "تنزيل مدير"  and in_array($re_id,$manger)){
	$re_id_info = file_get_contents("data/manger/$chat_id.txt");
	$mdrs = file_get_contents("data/manger/$chat_id/mange.txt");
	$mdrs1 = explode("             \n",$mdrs);
	$str = str_replace($re_id,"",$re_id_info);
	$str2 = str_replace(" *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ","",$mdrs1);
	file_put_contents("data/manger/$chat_id.txt",$str);
	file_put_contents("data/manger/$chat_id/mange.txt",$str2);
	bot('SendMessage',['chat_id'=>$chat_id,
    'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم تنزيله من قائمة المدراء
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($re and $text == "تنزيل المدير" || $text == "تنزيل مدير" and !in_array($re_id,$manger)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ ليس مدير ليتم تنزيله
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المدراء" || $text == "قائمه المدراء" and $mangers_info != NULL and $mangers_info != " "){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"✵⁞ اليك قائمة ⋙ المدراء
$mangers_infos\n",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المدراء" ||  $text == "قائمه المدراء" and $mangers_info == NULL || $mangers_info == " " || $mangers_info == ""){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ عزيزي ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ لايوجد اي مدراء حاليأ
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
}

if($status == "creator" ||  $status == "administrator" ||  in_array($from_id,$Dev) || in_array($from_id,$developer) || in_array($from_id,$carlos) || in_array($from_id,$eri) || in_array($from_id,$nazar)) {
if($re and $text == "رفع ادمن" || $text == "ر ادمن"  and !in_array($re_id,$admin_user)){
			file_put_contents("data/admin_user/$chat_id.txt",$re_id . "\n" , FILE_APPEND);
			file_put_contents("data/admin_user/$chat_id/mange.txt" , " *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ". "\n" , FILE_APPEND);
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم ترقية ليصبح ادمن
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
elseif($re and $text == "رفع ادمن" || $text == "رفع ادمن" || $text == "ر ادمن"  and in_array($re_id,$admin_user)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ هوه بالفعل ادمن
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "مسح الادمنية" ){
file_put_contents("data/admin_user/$chat_id.txt","");
file_put_contents("data/admin_user/$chat_id.txt","");
file_put_contents("data/admin_user/$chat_id/mange.txt" ,"");
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطة ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ تم مسح قائمة الادمنيه
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,  
]);
}

if($re and $text == "تنزيل ادمن" and in_array($re_id,$admin_user)){
	$re_id_info = file_get_contents("data/admin_user/$chat_id.txt");
	$admn = file_get_contents("data/admin_user/$chat_id/mange.txt");
	$admn1 = explode("             \n",$admn);
	$str = str_replace($re_id,"",$re_id_info);
	$str2 = str_replace(" *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ","",$admn1);
	file_put_contents("data/admin_user/$chat_id.txt",$str);
	file_put_contents("data/admin_user/$chat_id/mange.txt",$str2);
	bot('SendMessage',['chat_id'=>$chat_id,
    'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم تنزيله من قائمة الادمنيه
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($re and $text == "تنزيل ادمن"  and !in_array($re_id,$admin_user)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ هوه ليس ادمن ليتم تنزيله
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "الادمنيه" || $text == "قائمه الادمنيه" and $admin_users_info != NULL and $admin_users_info != " "){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"✵⁞ اليك قائمة ⋙ الادمنيه
$admin_users_infos\n",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "الادمنيه" ||  $text == "قائمه الادمنيه" and $admin_users_info == NULL || $admin_users_info == " " || $admin_users_info == ""){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ عزيزي ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ لايوجد اي ادمن حاليأ
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
}

if($status == "creator" ||  in_array($from_id,$Dev) || in_array($from_id,$developer) || in_array($from_id,$admin_user) || in_array($from_id,$manger) or in_array($from_id,$carlos) or in_array($from_id,$eri) || in_array($from_id,$nazar)) {
if($re and $text == "رفع مميز"  || $text == "رمميز"  and !in_array($re_id,$mmyaz)){
			file_put_contents("data/mmyaz/$chat_id.txt",$re_id . "\n" , FILE_APPEND);
			file_put_contents("data/mmyaz/$chat_id/mange.txt" , " *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ". "\n" , FILE_APPEND);
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم ترقيه ليصبح مميز
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
elseif($re and $text == "رفع مميز"  || $text == "رمميز"  and in_array($re_id,$mmyaz)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」 
⌯⁞ ايديه ↫ `$re_id`
⌯⁞ هوا بالفعل مميز 
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "مسح المميزين" ){
file_put_contents("data/mmyaz/$chat_id.txt","");
file_put_contents("data/mmyaz/$chat_id.txt","");
file_put_contents("data/mmyaz/$chat_id/mange.txt" ,"");
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطة ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ تم مسح قائمة المميزين
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,  
]);
}

if($re and $text == "تنزيل مميز"   and in_array($re_id,$mmyaz)){
	$re_id_info = file_get_contents("data/mmyaz/$chat_id.txt");
	$mdrs = file_get_contents("data/mmyaz/$chat_id/mange.txt");
	$mdrs1 = explode("             \n",$mdrs);
	$str = str_replace($re_id,"",$re_id_info);
	$str2 = str_replace(" *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ","",$mdrs1);
	file_put_contents("data/mmyaz/$chat_id.txt",$str);
	file_put_contents("data/mmyaz/$chat_id/mange.txt",$str2);
	bot('SendMessage',['chat_id'=>$chat_id,
    'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم تنزيله من قائمة المميزين
",
'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($re and $text == "تنزيل مميز" and !in_array($re_id,$mmyaz)){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ هو ليس مميز ليتم تنزيله
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المميزين" || $text == "قائمه المميزين" and $mmyazs_info != NULL and $mmyazs_info != " "){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"✵⁞ اليك قائمة ⋙ المميزين
$mmyazs_infos\n",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
if($text == "المميزين" ||  $text == "قائمه المميزين" and $mmyazs_info == NULL || $mmyazs_info == " " || $mmyazs_info == ""){
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ عزيزي ⋙「 [$first_name](tg://user?id=$from_id) 」 
⌯⁞ لايوجد اي مميز حاليأ
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
}

if($re and $text == "تنزيل الكل" || $text == "تنزيل من الكل" || $text == "تنزيله من الكل"){
if($status == "creator" ||in_array($from_id,$Dev) || in_array($from_id,$developer) || in_array($from_id,$nazar)){
$re_id_info = file_get_contents("data/manger/$chat_id.txt");
$mdrs = file_get_contents("data/manger/$chat_id/mange.txt");
$mdrs1 = explode(" \n",$mdrs);
$str = str_replace($re_id,"",$re_id_info);
$str2 = str_replace(" *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ","",$mdrs1);
file_put_contents("data/manger/$chat_id.txt",$str);
file_put_contents("data/manger/$chat_id/mange.txt",$str2);
$re_id_info = file_get_contents("data/admin_user/$chat_id.txt");
$admn = file_get_contents("data/admin_user/$chat_id/mange.txt");
$admn1 = explode(" \n",$admn);
$str = str_replace($re_id,"",$re_id_info);
$str2 = str_replace(" *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ","",$admn1);
file_put_contents("data/admin_user/$chat_id.txt",$str);
file_put_contents("data/admin_user/$chat_id/mange.txt",$str2);
$re_id_info = file_get_contents("data/mmyaz/$chat_id.txt");
$mdrs = file_get_contents("data/mmyaz/$chat_id/mange.txt");
$mdrs1 = explode(" \n",$mdrs);
$str = str_replace($re_id,"",$re_id_info);
$str2 = str_replace(" *𓆩* [" . "@". $re_user ."] *𓆪* " . "»" . " *𓆩* `". $re_id ."` *𓆪* ","",$mdrs1);
file_put_contents("data/mmyaz/$chat_id.txt",$str);
file_put_contents("data/mmyaz/$chat_id/mange.txt",$str2);
bot('restrictChatMember',[
'user_id'=>$re_id,
'chat_id'=>$chat_id,
'can_post_messages'=>true,
'can_add_web_page_previews'=>false,
'can_send_other_messages'=>true,
'can_send_media_messages'=>true,
]);
bot('SendMessage',['chat_id'=>$chat_id,
'text'=>"
✵⁞ العضو ⋙「 [$re_name](tg://user?id=$re_id) 」
⌯⁞ ايديه ↫ `$re_id` 
⌯⁞ تم تنزيله من كل الرتب
",'parse_mode'=>'markdown','reply_to_message_id'=>$message->message_id,'disable_web_page_preview'=>true,
]);
}
}

#tag
if ($settings["lock"]["tag"] == "مقفول"){
if (strstr($text ,"#") == true or strstr($caption,"#") == true) {
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id]);}}}}
#link
if($settings["lock"]["link"] == "مقفول"){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
if (strstr($text,"t.me") == true or strstr($text,"telegram.me") == true or strstr($text,"https://") == true or strstr($text,"://") == true or strstr($text,"wWw.") == true or strstr($text,"WwW.") == true or strstr($text,"T.me/") == true or strstr($text,"WWW.") == true or strstr($caption,"t.me") == true or strstr($caption,"telegram.me")) {   
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id,]);}}}
#photo
if($settings["lock"]["photo"] == "مقفول"){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
if ($update->message->photo){  
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id]);}}}
# inline
$inline = json_decode(file_get_contents('php://input'),true);
if($settings["lock"]["inline"] == "مقفول"){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
if(isset($inline['message']['reply_markup']['inline_keyboard'][0][0]['text'])){
bot('deleteMessage',['chat_id'=>$message->chat->id,'message_id'=>$message->message_id]);}}}
#gif
if($settings["lock"]["gif"] == "مقفول"){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
if ($update->message->document){  
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id]);}}}
# document
if($settings["lock"]["document"] == "مقفول"){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
if ($update->message->document){  
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id]);}}}
# video
if($settings["lock"]["video"] == "مقفول"){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
if ($update->message->video){  
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id]);}}}
# ar
if ($settings["lock"]["ar"] == "مقفول"){
if (strstr($text,"") == true  or strstr($text,"") == true or strstr($text,"") == true  or  strstr($text,"") == true   or strstr($text,"") == true or  strstr($text,"") == true  or strstr($text,"") == true or strstr($text,"") == true  or  strstr($text,"") == true   or strstr($text,"") == true or strstr($text,"") == true  or strstr($text,"") == true or strstr($text,"") == true  or  strstr($text,"") == true   or strstr($text,"") == true or  strstr($text,"") == true  or strstr($text,"") == true or strstr($text,"") == true  or  strstr($text,"") == true   or strstr($text,"") == true or strstr($text,"") == true or strstr($text,"") == true  or  strstr($text,"") == true   or strstr($text,"") == true or  strstr($text,"") == true  or strstr($text,"") == true or strstr($text,"") == true  or  strstr($text,"") == true   or strstr($text,"") == true or strstr($text,"") == true  or strstr($text,"") == true or strstr($text,"") == true  or  strstr($text,"") == true   or strstr($text,"") == true or  strstr($text,"") == true  or strstr($text,"") == true ) {
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id]);}}}}
# en
if ($settings["lock"]["en"] == "مقفول"){
if (strstr($text,"q") == true  or strstr($text,"w") == true or strstr($text,"e") == true  or  strstr($text,"r") == true   or strstr($text,"t") == true or  strstr($text,"y") == true  or strstr($text,"u") == true or strstr($text,"i") == true  or  strstr($text,"o") == true   or strstr($text,"p") == true or strstr($text,"a") == true  or strstr($text,"s") == true or strstr($text,"d") == true  or  strstr($text,"f") == true   or strstr($text,"g") == true or  strstr($text,"h") == true  or strstr($text,"j") == true or strstr($text,"k") == true  or  strstr($text,"l") == true   or strstr($text,"z") == true or strstr($text,"x") == true or strstr($text,"c") == true  or  strstr($text,"v") == true   or strstr($text,"b") == true or  strstr($text,"n") == true  or strstr($text,"m") == true or strstr($text,"Q") == true  or  strstr($text,"X") == true   or strstr($text,"C") == true or strstr($text,"F") == true  or strstr($text,"G") == true or strstr($text,"H") == true  or  strstr($text,"A") == true   or strstr($text,"L") == true or  strstr($text,"O") == true  or strstr($text,"P") == true ) {
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id]);}}}}
# edit 
if($editgetsettings["lock"]["edit"] == "مقفول"){
if ( $you != 'creator' && $you != 'administrator' && $edit_for_id != $Dev && $edit_for_id != $manger && $edit_for_id != $admin_user && $edit_for_id != $vipmem && $edit_for_id != $developer){
if ($update->edited_message->text){  
bot('deletemessage',['chat_id'=>$chat_edit_id,'message_id'=>$message_edit_id]);}}}
# contact
if ($settings["lock"]["contact"] == "مقفول"){
if($update->message->contact){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id]);}}}}
# edit media
$edit_media  = $update->edited_message->message_id;
$edit_chat_id_media = $update->edited_message->chat->id;
$edit_medias  = $update->edited_message->text;
$video_media = $update->edited_message->video;
$voice_media = $update->edited_message->voice;
$photo_media = $update->edited_message->photo;
$document_media = $update->edited_message->document;
$audio_media = $update->edited_message->audio;
$location_media = $update->edited_message->location;
if ($editgetsettings["lock"]["editmd"] == "مقفول"){
if ( $you != 'creator' && $you != 'administrator' && $edit_for_id != $Dev && $edit_for_id != $manger && $edit_for_id != $admin_user && $edit_for_id != $developer && $edit_for_id != $carlos && $edit_for_id != $eri && $edit_for_id != $nazar){
if(edit_medias || $photo_media || $document_media || $video_media || $voice_media || $audio_media || $location_media || preg_match('/^(.*)([Hh]ttp|[Hh]ttps|t.me)(.*)|([Hh]ttp|[Hh]ttps|t.me)(.*)|(.*)([Hh]ttp|[Hh]ttps|t.me)|(.*)[Tt]elegram.me(.*)|[Tt]elegram.me(.*)|(.*)[Tt]elegram.me|(.*)[Tt].me(.*)|[Tt].me(.*)|(.*)[Tt].me/',$edit_medias) ){
bot('deleteMessage',['chat_id'=>$edit_chat_id_media,'message_id'=>$edit_media,]);}}}

// username 
if ($settings["lock"]["username"] == "مقفول"){
if (strstr($text ,"@") == true or  strstr($caption,"@") == true) {
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
'chat_id'=>$chat_id,
'message_id'=>$message_id
]);
}}}}
// audio
if ($settings["lock"]["audio"] == "مقفول"){
if($update->message->audio){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
'chat_id'=>$chat_id,
'message_id'=>$message_id
]);
}}}}
// voice 
if ($settings["lock"]["voice"] == "مقفول"){
if($update->message->voice){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
'chat_id'=>$chat_id,
'message_id'=>$message_id
]);
}}}}
if ($settings["lock"]["markdown"] == "مقفول"){
if($update->message->entities){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
'chat_id'=>$chat_id,
'message_id'=>$message_id
]);
}}}}
if($settings["lock"]["bot"] == "مقفول"){
if ($message->new_chat_member->is_bot) {
$hardmodebot = $settings["information"]["hardmodebot"];
if($hardmodebot == "مقفول"){
bot('kickChatMember',[
'chat_id'=>$chat_id,
'user_id'=>$update->message->new_chat_member->id
]);
}
else
{
bot('kickChatMember',[
'chat_id'=>$chat_id,
'user_id'=>$update->message->new_chat_member->id
]);
bot('kickChatMember',[
'chat_id'=>$chat_id,
'user_id'=>$from_id
]);
}}}
// sticker is_sticker
if ($settings["lock"]["sticker"] == "مقفول"){
if($update->message->sticker){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
'chat_id'=>$chat_id,
'message_id'=>$message_id
]);
}}}}
if ($settings["lock"]["is_sticker"] == "مقفول"){
if($update->message->sticker->is_sticker){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
'chat_id'=>$chat_id,
'message_id'=>$message_id
]);
}}}}
// forward
if ($settings["lock"]["forward"] == "مقفول"){
if($update->message->forward_from | $update->message->forward_from_chat){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
'chat_id'=>$chat_id,
'message_id'=>$message->message_id
]);
}}}}
// muteall
if ($settings["lock"]["mute_all"] == "مقفول"){
if($update->message){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
'chat_id'=>$chat_id,
'message_id'=>$message->message_id
]);
}
}
}
// replay
if ($settings["lock"]["reply"] == "مقفول"){
if($update->message->reply_to_message){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
 'chat_id'=>$chat_id,
 'message_id'=>$message->message_id
 ]);
 }
}
}
}
// tg
if ($settings["lock"]["tgservic"] == "مقفول"){
if($update->message->new_chat_member | $update->message->new_chat_photo | $update->message->new_chat_title | $update->message->left_chat_member | $update->message->pinned_message){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
 bot('deletemessage',[
 'chat_id'=>$chat_id,
 'message_id'=>$message->message_id
 ]);
 }
}
}
}
// text
if ($settings["lock"]["text"] == "مقفول"){
if($update->message->text){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
 bot('deletemessage',[
 'chat_id'=>$chat_id,
 'message_id'=>$message->message_id
 ]);
 }
}
}
}
// video note
if ($settings["lock"]["video_msg"] == "مقفول"){
if($update->message->video_note){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
 bot('deletemessage',[
 'chat_id'=>$chat_id,
 'message_id'=>$message->message_id
 ]);
 }
}
}
}



if($settings["information"]["add"] == "مقفول") {
if($newchatmemberid == true){
$add = $settings["addlist"]["$from_id"]["add"];
$addplus = $add +1;
$settings["addlist"]["{$from_id}"]["add"]="$addplus";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
}

//game
if($settings["lock"]["game"] == "مقفول"){
if($update->message->game){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
 'chat_id'=>$chat_id,
 'message_id'=>$message_id
 ]);
}
}
}
}
// location
if ($settings["lock"]["location"] == "مقفول"){
if($update->message->location){
if ($tc == 'group' | $tc == 'supergroup'){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
bot('deletemessage',[
 'chat_id'=>$chat_id,
 'message_id'=>$message_id
 ]);
}
}
}
}
function check_filter($str){
global $filterget;
foreach($filterget as $d){
if (mb_strpos($str, $d) !== false) {
return true;
}
}
}
//linkk
if($settings["lock"]["linkk"] == "مقفول"){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
if (strstr($text,"t.me") == true or strstr($text,"telegram.me") == true or strstr($text,"https://") == true or strstr($text,"://") == true or strstr($text,"wWw.") == true or strstr($text,"WwW.") == true or strstr($text,"T.me/") == true or strstr($text,"WWW.") == true or strstr($caption,"t.me") == true or strstr($caption,"telegram.me")) {   
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id,]);
bot('kickChatMember',['user_id'=>$from_id,'chat_id'=>$chat_id,]);
bot('sendmessage',['chat_id'=>$chat_id,'text'=>"⌯⁞ عزيزي - [$first_name](tg://user?id=$from_id)\n⌯⁞ ممنوع نشر الروابط هنا تم طردك",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,]);}}}
//linkw
if($settings["lock"]["linkw"] == "مقفول"){
if ($status !=  creator  && $status !=  administrator  && !in_array($from_id,$Dev) && !in_array($from_id,$manger) && !in_array($from_id,$admin_user) && !in_array($from_id,$developer) && !in_array($from_id,$carlos) && !in_array($from_id,$eri) && !in_array($from_id,$nazar)){
if (strstr($text,"t.me") == true or strstr($text,"telegram.me") == true or strstr($text,"https://") == true or strstr($text,"://") == true or strstr($text,"wWw.") == true or strstr($text,"WwW.") == true or strstr($text,"T.me/") == true or strstr($text,"WWW.") == true or strstr($text,"https://") == true or strstr($caption,"t.me") == true or strstr($caption,"telegram.me")) {   
bot('deletemessage',['chat_id'=>$chat_id,'message_id'=>$message_id,]);
bot('sendmessage',['chat_id'=>$chat_id,'text'=>"⌯⁞ عزيزي - [$first_name](tg://user?id=$from_id)\n⌯⁞ ممنوع نشر الروابط هنا ",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,]);}}}

if($text =="قفل الروابط" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الروابط بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["link"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الروابط" or $text =="فتح روابط"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الروابط بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["link"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
if($text =="قفل الروابط بالطرد" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الروابط بنجاح
⌯⁞ خاصية ⋙ الطرد
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["linkk"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الروابط بالطرد" or $text =="فتح روابط بالطرد"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الروابط بالطرد
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["linkk"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
if($text =="قفل الروابط بالتحذير" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الروابط بنجاح
⌯⁞ خاصية ⋙ التحذير
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["linkw"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الروابط بالتحذير" or $text =="فتح روابط بالتحذير"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الروابط بالتحذير
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["linkw"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
if($text =="قفل الانلاين" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الانلاين بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["inline"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الانلاين" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الانلاين بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["inline"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
if($text =="قفل الانكليزيه" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الانكليزيه بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["en"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الانكليزيه" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الانكليزيه
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["en"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// lock photo
elseif($text =="قفل الصور" or $text =="قفل صور"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الصور بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["photo"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الصور" or $text =="فتح صور"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قتح الصور بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["photo"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="قفل الملصقات المتحركة" or $text =="قفل الملصقات المتحركه"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفل الملصقات المتحركة
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["is_sticker"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الملصقات المتحركة" or $text =="فتح الملصقات المتحركه"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الملصقات المتحركه
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["is_sticker"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// gif
elseif($text =="قفل المتحركة" or $text =="قفل المتحركه"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل المتحركه بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["gif"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>" يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت ",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح المتحركة" or $text =="فتح المتحركه"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح المتحركه بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["gif"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="قفل الماركدوان" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الماركدوان بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["markdown"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>" يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت ",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الماركدوان" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الماركدوان بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["markdown"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="قفل العربيه" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل العربيه بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["ar"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>" يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت ",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح العربيه" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح العربيه بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
 ]);
$settings["lock"]["ar"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// document
elseif($text =="قفل الملفات" or $text =="قفل ملفات،"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الملفات بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["document"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الملفات" or $text =="فتح ملفات"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الملفات بنجاح
",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["document"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// video
elseif($text =="قفل الفيديو" or $text =="قفل فيديو"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الفيديو بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["video"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الفيديو" or $text =="فتح فيديو"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الفيديو بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["video"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// edit
elseif($text =="قفل التعديل" or $text =="قفل تعديل"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل التعديل بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["edit"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح التعديل" or $text =="فتح تعديل"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح التعديل بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["edit"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// game
elseif($text =="قفل الالعاب" or $text =="قفل العاب"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الالعاب بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["game"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الالعاب" or $text =="فتح العاب"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الالعاب بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
 $settings["lock"]["game"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// location
elseif($text =="قفل المواقع" or $text =="قفل الموقع"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل المواقع بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["location"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت ",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح المواقع" or $text =="فتح الموقع"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح المواقع بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["location"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// contact
elseif($text =="قفل الجهات" or $text =="قفل جهات"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الجهات بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["contact"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الجهات" or $text =="فتح جهات"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الجهات بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["contact"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="قفل تعديل الميديا" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل تعديل الميديا بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["editmd"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح تعديل الميديا" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح تعديل الميديا
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["editmd"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// tag
elseif($text =="قفل التاك" or $text =="قفل الهاش تاك"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل التاك بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["tag"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح التاك" or $text =="فتح الهاش تاك"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح التاك بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["tag"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// username 
elseif($text =="قفل المعرفات" or $text =="قفل المعرف"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل المعرفات بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["username"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح المعرفات" or $text =="فتح المعرف"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح المعرفات بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["username"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// audio
elseif($text =="قفل الصوت" or $text =="قفل الموسيقى"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الصوت بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["audio"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الصوت" or $text =="فتح صوت"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الصوت بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["audio"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="قفل الاشعارات" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الاشعارات بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["tgservic"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الاشعارات" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الاشعارات بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["tgservic"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// video note
elseif($text =="قفل بصمة الفيديو" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل بصمة الفيديو بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["video_msg"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح بصمة الفيديو" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح بصمة الفيديو بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["video_msg"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// lock bots
elseif ($text== "قفل البوتات" or $text== "قفل بوتات" or $text== "قفل البوت") {
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل البوتات بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["bot"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif ($text== "فتح البوتات" or $text== "فتح بوتات"or $text== "فتح البوت") {
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح البوتات بنجاح ",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["bot"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
if($text =="قفل البصمات" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل البصمات بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["voice"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح البصمات" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح البصمات بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["voice"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
if($text =="قفل الاباحي" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الاباحي بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["xi"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الاباحي" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الاباحي بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["xi"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// sticker
elseif($text =="قفل الملصقات" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الملصقات بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["sticker"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح الملصقات" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الملصقات بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["sticker"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// forward
elseif($text =="قفل التوجيه"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل التوجيه بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["forward"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح التوجيه" ){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح التوجيه بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["forward"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
// fosh
elseif($text =="قفل السيئات" or $text =="قفل الممنوعات"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل السيئات بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["fosh"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="فتح السيئات" or $text =="فتح الممنوعات"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح السيئات بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["fosh"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif( $text =="قفل الكلايش"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
$pluscharacter = $settings["information"]["pluscharacter"];
$downcharacter = $settings["information"]["downcharacter"];
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الكلايش بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["lockcharacter"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif( $text =="فتح الكلايش"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الكلايش بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["lockcharacter"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت ",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
if( $text =="قفل الدردشه"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم قفـل الدردشه بنجاح
⌯⁞ خاصية ⋙ المسح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["text"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif( $text =="فتح الدردشه"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم فتح الدردشه بنجاح
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["text"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="قفل تحويل الصيغ" or $text =="قفل الصيغ"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$nazar) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"*
✵⁞ تم قفل تحويل الصيغ  
⌯⁞ بواسطة ⋙ *[$first_name](tg://user?id=$from_id) 
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["sigmidia"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}}}
elseif($text =="فتح تحويل الصيغ" or $text =="فتح الصيغ"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$nazar) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"*
✵⁞ تم فتح تحويل الصيغ  
⌯⁞ بواسطة⋙ * [$first_name](tg://user?id=$from_id) 
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["sigmidia"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}}}
elseif($text =="قفل تحميل الفديو" or $text =="قفل تحميل الميديا" or $text == "قفل التحميل"){
if($status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$nazar) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"*
✵⁞ تم قفل تحميل الميديا  
✵⁞ بواسطة ⋙ * [$first_name](tg://user?id=$from_id) 
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["downloadmid"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}}}
elseif($text =="فتح تحميل الفديو" or $text =="فتح تحميل الميديا" or $text == "فتح التحميل"){
if($status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$nazar) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"*
✵⁞ تم فتح تحميل الميديا  
✵⁞ بواسطة ⋙ * [$first_name](tg://user?id=$from_id) 
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["downloadmid"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
]);
}}}

elseif( $text =="تعطيل الايدي" or $text == "تعطيل الايدي بالصوره" or $text == "قفل الايدي بلصوره"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$nazar) or in_array($from_id,$carlos) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم تعطيل الايدي بالصوره
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["iduser"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="تفعيل الايدي" or $text == "تفعيل الايدي بالصوره" or $text == "فتح الايدي بلصوره"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$nazar) or in_array($from_id,$carlos) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم تفعيل الايدي بالصوره
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["iduser"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif( $text =="تعطيل ردود البوت" or $text == "تعطيل ردود بوت"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$nazar) or in_array($from_id,$carlos) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم تعطيل ردود البوت
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["rdona"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="تفعيل ردود البوت" or $text == "تفعيل ردود بوت"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$nazar) or in_array($from_id,$carlos) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم تفعيل ردود البوت
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["rdona"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif( $text =="تعطيل اطردني" or $text == "تعطيل امر اطردني"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$nazar) or in_array($from_id,$carlos) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم تعطيل الامر اطردني
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["bannnnn"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="تفعيل اطردني" or $text == "تفعيل امر اطردني"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$nazar) or in_array($from_id,$carlos) or in_array($from_id,$eri)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم تفعيل الامر اطردني
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["bannnnn"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif( $text =="تعطيل اوامر التحشيش" or $text == "تعطيل تحشيش"){
if($status == "creator" ||  $status == "administrator" ||  in_array($from_id,$Dev) || in_array($from_id,$developer) ||  in_array($from_id,$carlos) || in_array($from_id,$nazar) || in_array($from_id,$eri) || in_array($from_id,$manger)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم تعطيل اوامر التحشيش
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["jooki"]="مفتوح";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}
elseif($text =="تفعيل اوامر التحشيش" or $text == "تفعيل تحشيش"){
if($status == "creator" ||  $status == "administrator" ||  in_array($from_id,$Dev) || in_array($from_id,$developer) ||  in_array($from_id,$carlos) || in_array($from_id,$nazar) || in_array($from_id,$eri) || in_array($from_id,$manger)) {$add = $settings["information"]["added"];
if ($add == true) {
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم تفعيل اوامر التحشيش
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
$settings["lock"]["jooki"]="مقفول";
$settings = json_encode($settings,true);
file_put_contents("data/$chat_id.json",$settings);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"يجب تفعيل البوت في المجموعة قم بإرسال كلمة { • تفعيل • } لتفعيل البوت",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
}

elseif($rt && $text== "حذف"){
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) { bot('deletemessage',[
 'chat_id'=>$chat_id,
 'message_id'=>$re_msgid
 ]);
 bot('deletemessage',[
 'chat_id'=>$chat_id,
 'message_id'=>$message_id
 ]);
 }
}
// rmsg
elseif ( strpos($text, '/rmsg') !== false or strpos($text, 'تنظيف') !== false) {
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,$Dev) or in_array($from_id,$manger) or in_array($from_id,$admin_user) or in_array($from_id,$developer) or in_array($from_id,$carlos) or in_array($from_id,$eri) or in_array($from_id,$nazar)) {$num = str_replace(['/rmsg ','تنظيف'],'',$text );
if ($num <= 500 && $num >= 1){
$add = $settings["information"]["added"];
if ($add == true) {
for($i=$message_id; $i>=$message_id-$num; $i--){
bot('deletemessage',[
 'chat_id' => $chat_id,
 'message_id' =>$i,
]);
}
bot('sendmessage',[
 'chat_id' => $chat_id,
 'text' =>"
✵⁞ بواسطه ⋙ [$first_name](tg://user?id=$from_id)
⌯⁞ تم حذف عدد من رسائل ⋙ *$num*
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_markup'=>$inlinebutton,
]);
}
else
{
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"⌯⁞ خطأ البوت لا يعمل بسبب عدم تفعيل البوت
⌯⁞ ارسل كلمة تفعيل لتفعيل البوت في المجموعة
",
'reply_to_message_id'=>$message_id,
'reply_markup'=>$inlinebutton,
 ]);
}
}
else
{
bot('sendmessage',[
 'chat_id' => $chat_id,
 'text'=>"⌯⁞ يجب ان يكون العدد بين 1 إلى 500 ",
'reply_markup'=>$inlinebutton,
]);}}
}
//setname
elseif (strpos($text, 'ضع اسم') !== false) {
if ( $status == 'creator' or $status == 'administrator' or in_array($from_id,
