
sublist3r -d example.com -o results.txt
amass enum -passive -d example.com -o results.txt

cat domains.txt | httpx -sc -title -server -screenshot -o results.txt
screen shots 

katana 
alaywas 


جرب الاتي
استخدم ادات واحد للسب دومين واضف لها api كاداه amass بيها فعل خاصيه الاكتيف و البروتفورس مع الapi نتاىجها جيده
ثم ارسل الناتج لhttpx مع خاصيه التايتل و sc اخزن في targets
ثم اجمع كل الايبيهات من التاركيت ثم فلتر كل اي بي يعود لcdn ثم افحص البورتات للايبهات المتبقيه والسيرفس وجرب سكربتات nmap ثم ابدا بمعرفه المعلومات الاساسيه و دونها تحتاجها كلغه البرمجه باختبار كل تاركيت على احدى حسب نوع الاستجابه مثلا اذا كان 403 جرب تاكسس ملفات او فايلات او عن طريق تغير اوحذف كوكيز
اهم شي الدورك في كوكل و كيت هوب وشودان
بعد تحديد التاركيت حاول الحصول على كل الurl باستخدام |gau و katana وفلتر الناتج مثلا الصور او الفديوهات او استخدم uro ثم فلتر كل الurl الى باراميترات استخدم gf وحاول استغلالها
اهم شي الfuzz في كل مكان باستخدام فايلات تنتهي بلغه برمجه الموقع وجرب فحص فايلات js

السب دومين اداه amass (فعل خاصيه active -b)
الناتج الى httpx -sc -screenshot -titel |tee httpx
حول الفايل الى دومين فقط بدون بروتوكول استخدم awk
استخدم امر host لاستخراج كل الايبيهات و استخدم grep و awk للترتيب احفظ الناتج في ippp
استخرج نوع الايبيهات (السيرفر) cat ippp|httpx -server -sc -titel
استخدم grep لحذف كل cdn ip او حاول تجاوزها للوصول الى internal ip
بعد فلتره الايبي ارسل الناتج الى nmap لفحص البورتات واستخدم سكربتاتها | او اذا كان العدد كبير استخدم masscan
ثم افحص الايبيهات ابحث عن تسريب للمعلومات ايضا قم ب fuzz لل لايبيهات
الان تاتي لكل سب دومين على حدى اولا الدورك
بكوكل وكيت هوب و شودان
ثم معلومات عن الموقع لمعرفه اللستات التي يجب عليك استخدامها و البايلودات
ثم احصل على كل الurl استخدم gau katana
فلتر الurl لمجلد جديد كل ثغره حسب باراميتراتها استخدم gf arjun paramspider
لاتنسئ ان يكون كل الطلبات عبر البروكسي برب او زاب
اثناء ذالك افحص يدوي للidor او bac او ثغرات auth
ايضا الfuzz جدا مهم
1 ع
رد
مشاركة \





subfinder -d target.com | tee subdomains.txt
assetfinder --subs-only target.com | tee -a subdomains.txt
amass enum -passive -d target.com | tee -a subdomains.txt
curl -s "https://crt.sh/?q=%25.target.com&output=json" | jq -r '.[].name_value' | sed 's/\*\.//g' | sort -u | tee -a subdomains.txt

sort -u subdomains.txt -o subdomains.txt
cat subdomains.txt | httpx -silent -o live_subdomains.txt


katana -u live_subdomains.txt -o endpoints.txt

cat live_subdomains.txt | waybackurls | tee -a urls.txt

