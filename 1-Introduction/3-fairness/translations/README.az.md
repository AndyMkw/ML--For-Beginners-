# Məhsul Sİ ilə maşın öyrənməsi həlləri tapmaq.

![Eskizdə Maşın Öyrənməsində məhsul Sİ-in xülasəsi](../../../sketchnotes/ml-fairness.png)
> [Tomomi Imura](https://www.twitter.com/girlie_mac) tərəfindən eskiz

## [Mühazirə öncəsi test](https://gray-sand-07a10f403.1.azurestaticapps.net/quiz/5/)

## Giriş

Bu kurrikulumda siz maşın öyrənməsinin gündəlik həyatımıza necə təsir edə biləcəyini və necə təsir etdiyini kəşf etməyə başlayacaqsınız. Hətta indi də sistemlər və modellər səhiyyə diaqnozları, kreditlərin təsdiqlənməsi və ya dələduzluğun aşkarlanması kimi gündəlik qərar qəbuletmə işlərində iştirak edirlər. Buna görə də, etibarlı nəticələr əldə etmək üçün bu modellərin yaxşı işləməsi vacibdir. Hər hansı bir proqram tətbiqi kimi, Sİ sistemləri də gözləntilərə çatmayacaq və ya arzuolunmaz nəticə ilə üzləşəcək. Buna görə də Sİ modelinin davranışını başa düşmək və izah etmək vacibdir.

Təsəvvür edin ki, bu modelləri yaratmaq üçün istifadə etdiyiniz məlumatlar irq, cins, siyasi görüş, din kimi müəyyən demoqrafik göstəricilərə malik olmadıqda və ya qeyri-mütənasib şəkildə bu cür demoqrafik göstəriciləri təmsil edərsə nə baş verə bilər. Modelin çıxışı bəzi demoqrafik göstəricilərə üstünlük vermək üçün şərh edilməsinin nəticəsi nə olacaq? Tətbiq üçün nəticəsi nə olacaq? Bundan əlavə, modelin mənfi nəticəsi olduqda və insanlar üçün zərərli olduqda nə baş verəcək? Sİ sistemlərinin davranışına görə kim cavabdehdir? Bunlar bu kurrikulumda araşdıracağımız bəzi suallardır.

Bu dərsdə siz:

- Maşın öyrənməsində ədalətin əhəmiyyəti və ədalətlə əlaqəli zərərlər haqqında məlumatlılığınızı artıracaqsınız
- Etibarlılıq və təhlükəsizliyi təmin etmək üçün kənar göstəriciləri və qeyri-adi ssenariləri araşdırmaq təcrübəsi ilə tanış olacaqsınız
- İnklüziv sistemlərin dizayn edilməsi ilə hər kəsin səlahiyyətləndirilməsi ehtiyacı haqqında anlayış əldə edəcəksiniz
- Məlumatların və insanların məxfiliyinin və təhlükəsizliyinin qorumasının nə qədər vacib olduğunu araşdıracaqsınız
- Süni intellekt modellərinin davranışını izah etmək üçün şüşə qutu yanaşmasının vacibliyini görəcəksiniz
- Süni intellekt sistemlərinə inam yaratmaq üçün məsuliyyətliliyin necə vacib olduğunu nəzərə alacaqsınız

## Tələb olunanlar

İlkin olaraq, zəhmət olmasa, "Məsul Sİ Prinsipləri" Təlim Yolunu başlayın və mövzu ilə bağlı aşağıdakı videoya baxın:

Bu [Təlim Yolunu](https://docs.microsoft.com/learn/modules/responsible-ai-principles/?WT.mc_id=academic-77952-leestott) izləməklə Məhsul Sİ haqqında daha çox məlumat əldə edin

[![Microsoft-un Məsul Sİ-ə yanaşması](https://img.youtube.com/vi/dnC8-uUZXSc/0.jpg)](https://youtu.be/dnC8-uUZXSc "Microsoft-un Məsul Sİ-ə yanaşması")

> 🎥 Video üçün yuxarıdakı şəklə klikləyin: Microsoft-un Məsul Sİ-ə yanaşması

## Ədalətlilik

Süni intellekt sistemləri hər kəsə ədalətli davranmalı və oxşar insan qruplarına müxtəlif yollarla təsir etməməlidir. Məsələn, süni intellekt sistemləri tibbi müalicə, kredit müraciətləri və ya işə qəbulla bağlı təlimat verdikdə, oxşar simptomları, maliyyə vəziyyəti və ya peşəkar keyfiyyətləri olan hər kəsə eyni tövsiyələri verməlidir. İnsan olaraq hər birimiz qərarlarımıza və hərəkətlərimizə təsir edən irsi qərəzləri daşıyırıq. Bu qərəzlər AI sistemlərini öyrətmək üçün istifadə etdiyimiz məlumatlarda aydın görünə bilər. Belə manipulyasiya bəzən istəmədən baş verə bilər. Məlumatlarda qərəzliliyi nə vaxt tətbiq etdiyinizi şüurlu şəkildə bilmək çox vaxt çətindir.

**“Haqsızlıq”** irq, cins, yaş və ya əlillik statusu kimi xüsusiyyətləti baxımından bir qrup insan üçün mənfi təsirləri və ya “zərərləri” əhatə edir. Ədalətlə əlaqəli əsas zərərlər aşağıdakı kimi təsnif edilə bilər:

- **Ayrı-seçkilik**, məsələn, cins və ya etnik mənsubiyyət digərindən üstündürsə.

- **Xidmət keyfiyyəti**. Əgər məlumatı konkret bir ssenari üçün öyrədirsinizsə, lakin reallıq daha mürəkkəbdirsə, bu, xidmətin keyfiyyətsiz olmasına gətirib çıxarır. Məsələn, qara dərili insanları hiss edə bilməyən əl sabunu dispenseri. [İstinad](https://gizmodo.com/why-cant-this-soap-dispenser-identify-dark-skin-1797931773)

- **Təhqir**. Bir şeyi və ya kimisə haqsız yerə tənqid etmək, etiketləmək. Məsələn, bir şəkil etiketləmə texnologiyası qara dərili insanların şəkillərini qorilla kimi yanlış etiketlədi.

- **Həddindən artıq və ya az təmsil olunma**. İdeya ondan ibarətdir ki, müəyyən bir qrup müəyyən bir peşədə kifayət qədər təmsil olunmur və zərər verən hər hansı bir xidmət və ya funksiya bunu təbliğ etməyə davam edir.

- **Stereotipləşdirmə**. Müəyyən bir qrupun ön yarğılı fikirlər əlaqələndirilməsi. Məsələn, ingilis və türk dilləri arasında dil tərcümə sistemində cins ilə stereotipik əlaqəsi olan sözlərə görə səhvlər ola bilər.

![translation to Turkish](../images/gender-bias-translate-en-tr.png)
> türk dilinə tərcümə

![translation back to English](../images/gender-bias-translate-tr-en.png)
> ingilis dilinə geri tərcümə

Süni intellekt sistemlərinin dizayn edilməsi və test olunması zamanı biz süni intellektin ədalətli olmasını və qərəzli və ya ayrı-seçkilik xarakterli qərarlar qəbul etmək üçün proqramlaşdırılmamasını təmin etməliyik, hansı ki insanların da qəbul etməsi qadağandır. Süni intellekt və maşın öyrənməsində ədalətin təmin edilməsi mürəkkəb sosial texniki problem olaraq qalır.

### Etibarlılıq və təhlükəsizlik

Güvən yaratmaq üçün AI sistemləri həm normal həm də gözlənilməz şəraitdə etibarlı, təhlükəsiz və düzgün olmalıdır. Süni intellekt sistemlərinin müxtəlif situasiyalarda necə davranacağını bilmək vacibdir, xüsusən də onlar normal şəraitdən kənara çıxdıqda. Süni intellekt həllərini qurarkən, süni intellektin qarşılaşacağı müxtəlif vəziyyətlərin necə idarə olunacağına böyük diqqət yetirilməlidir. Məsələn, özünü idarə edən avtomobil insanların təhlükəsizliyini əsas prioritet kimi qoymalıdır. Nəticədə, avtomobili idarə süni intellekt avtomobilin qarşılaşa biləcəyi bütün mümkün ssenariləri nəzərə almalıdır, məsələn, gecə, tufan və ya çovğun, küçədə qaçan uşaqlar, ev heyvanları, yol tikintiləri və s. Bir Sİ sisteminin nə qədər yaxşı olduğu bir sıra fərqli şəraitdə nə dərəcə etibarlı və təhlükəsiz işlədiyindən asılıdır, bu, sistem dizaynı və testi zamanı data alimi və ya Sİ təminatçısı tərəfindən nəzərə alınan proqnoz səviyyəsini göstərir.

> [🎥 Video üçün bura klikləyin: ](https://www.microsoft.com/videoplayer/embed/RE4vvIl)

### Daxil edilmə

Sİ sistemləri hər kəslə əlaqədə olacaq və fayda verəcək şəkildə formalaşdırılmalıdır. Sİ sistemlərinin dizayn və icra mərhələrində data mühəndisləri və proqramçılar sistemin istəmədən kimlərisə xaric etməsi ehtimalarını təyin etməyə və qarşısını almağa çalışırlar. Misal üçün dünyada müxtəlif əngəlləri olan 1 milyard insan var. Sİ inkişafı nəticəsində onlar geniş miqyasda məlumatlara və fürsətlərə gündəlik həyatlarında asanlıqla çata bilirlər. Əngəllər barədə öncədən düşünmək Sİ məhsullarını hər kəs tərəfindən faydalana biləcəyi daha yaxşı təcrübəni yaratmağa fürsətlər yaradır.

> [🎥 Video üçün bura klikləyin: Sİ-də daxil edilmə](https://www.microsoft.com/videoplayer/embed/RE4vl9v)

### Təhlükəsizlik və məxfilik

Sİ sistemləri təhlükəsiz olmalı və insanlarım məxfiliyinə hörmət etməlidir. İnsanlar onların məxfiliyini, məlumatlarını və ya həyatlarını risk altında qoyan sistemlərə az güvənirlər. Maşın öyrənməsi modellərini sazladığımız zaman ən yaxşı nəticəni verən datalara etibar edirik. Bunu etdiyimiz zaman datanın mənbəsini və düzgün üsulla əldə olduğunu da nəzərə almalıyıq. Misal üçün, bu məlumat istifadəçi tərəfindən təqdim olunub və ya ictimai olaraq əlçatandırmı? Data ilə işləyərkən nəzərə alınmalı növbəti məsələ, Sİ sistemlərinin məxfi məlumatlarını qoruyacağı və hücumlara davamlı olacağı şəkildə hazırlanması vacibdir. Sİ istifadəsi artıqca vacib şəxsi və biznes məlumatlarının məxfiliyinin qorunması daha vacib və qəliz hala gəlir. Məxfilik və data təhlükəsizliyi problemləri Sİ üçün daha çox diqqət tələb edir, çünki bu məlumatlar Sİ sistemlərinin insanlar barədə dəqiq təxminlər və qərarlar verməsi üçün lazımdır.

> [🎥 Video üçün bura klikləyin: Sİ-də təhlükəsizlik](https://www.microsoft.com/videoplayer/embed/RE4voJF)

- Cari sənayedə Məxfilik və təhlükəsizlik sahəsində əhəmiyyətli irəliləyişlər etmişik, GDPR (Ümumi Məlumatların Qorunması Qaydası) kimi qaydalarla diqqəti daha da artırmışıq
- Buna baxmayaraq biz Sİ sistemlərində effektiv fərdiləşdirilmə üçün şəxsi məlumatlara olan ehtiyac ilə təhlükəsizlik arasında olan gərginliyi başa düşməliyik.
- Kompüterlərin internetə qoşulması ilə təhlükəsizlik problemlərinin yaranmasındakı böyük sıçrayışı indi Sİ ilə əlaqəli sistemlərində görürük.
- Eyni zamanda biz Sİ təhlükəsizlik tərəfdən inkişaf etdiyini də görürük. Misal olaraq, bugünkü müasir anti-virus proqramları Sİ sistemlərinin iştirakı ilə həyata keçirir.
- Bizim Data elmi proseslərinin ən son məxfilik və təhlükəsizlik təcrübələrini özündə birləşdiyinə əmin olmağımız lazımdır.

### Şəffaflıq

Sİ sistemləri başa düşülən olmalıdır. Şəffaflığın ən vacib hissəsi Sİ sistemlərinin davranışını və komponentlərini izah etməkdir. Sİ sistemlərinin anlaşıqlığını artırmaqla biz mümkün performans problemlərini, təhlükəsizlik və məxfilik məsələlərini, qərəzləri, çıxdaş edilmə hallarını və ya istənilməyən nəticələri daha tez tapa bilərik. Biz həmçinin inanırıq ki, insanlar Sİ sistemlərini nə zaman, nə üçün və necə istifadə edəcəklərini seçməkləri barədə səmimi, məsuliyyətli olmalıdırlar. Əlavə olaraq işlətdikləri sistemin limitləri barədə də məlumatlı olmalıdırlar. Misal üçün, əgər bank Sİ sistemini müştərilərə verəcək kredit təklifini hazırlamaqda köməkçi kimi istifadə edirsə, bu sistemin verdiyi təklifləri ən çox hansı parametrlərin təsir etdiyini araşdırması vacibdir. Hökümətlər Sİ-in sənayelərdə istifadəsinə qaydalar tətbiq etməyə başlayır, belə ki data mühəndisləri və şirkətləri Sİ sisteminin verdiyi qərarların (xüsusilə arzuolunmaz nəticələrin) tənzimləyici tələblərə cavab verdiyini izah edə bilməlidirlər.

> [🎥 Video üçün bura klikləyin: Sİ-də şəffaflıq](https://www.microsoft.com/videoplayer/embed/RE4voJF)

- Sİ sistemləri qəliz olduğu üçün onun işləmə qaydasını və verdiyi qərarları anlamaq çətindir.
- Bu anlaşılmada əksiklik həmin sistemlərin idarə edilməsinə, istifadə edilməsinə və sənədləşməsinə təsir edir.
- Bu anlaşılmadakı əksiklik ən vacib olaraq sistemin səbəb olduğunu nəticəyə gətirən qərarlara təsir edir.

### Məsuliyyət

Sİ tərtib edən və işə salan şəxslər sistemin necə işlədiyi ilə bağlı məsuliyyət daşımalıdırlar. Üz tanınması kimi həssas texnologiyaların istifadəsində məsuliyyət ehtiyacı daha əhəmiyyətlidir. Son zamanlar, itmiş uşaqları tapmaq kimi istifadəyə yararlı üz tanıma texnologiyalarına tələb hüquq təşkilatlarından tərəfindən kəskin artmışdır. Lakin bu texnologiyalar dövlət tərəfindən istifadə olunaraq vətəndaşları fundamental azadlıq risklərinə gətirib çıxara bilər. Misal üçün onlar seçilmiş fərdləri daim müşahidə edə bilərlər. Buna görə də data alimləri və təşkilatlar Sİ sistemlərinin fərdlərə və cəmiyyətə necə təsir etməsi ilə bağlı məsuliyyətli olmalıdırlar.

[![Tanınmış Sİ tədqiqatçısı üz tanınması tətbiqi ilə ilə kütləvi izləmə barədə xəbərdarlıq edir edir](../images/accountability.png)](https://www.youtube.com/watch?v=Wldt8P5V6D0 "Microsoft-un məsuliyyətli Sİ-ə yanaşması")

> 🎥 Video üçün yuxarıdakı şəkilə klikləyin: Üz tanınması tətbiqi ilə ilə kütləvi izləmə barədə xəbərdarlıq

Sİ-i cəmiyyətimizə gətirmiş ilk nəsil olaraq bizə ünvanlanmış ən böyük suallardan biri, komputerlərin insanlara məlusiyyətli qalacağına və komputerləri tərtib edən insanların digər hər kəsə məsuliyyətli qalacağına necə əmin ola bilərik.

## Təsirin qiymətləndirilməsi

Maşın öyrənmə modelini öyrətməzdən əvvəl Sİ sisteminin məqsədini anlamaq üçün mümkün ola biləcək təsirlər qiymətləndirməyimiz vacibdir. Sistemin istifadəsində məqsəd nədir, harada tətbiq olunacaq və bununla kim işləyəcək. Bu məqamlar mümkün ola biləcək riskləri və gözlənilənil nəticələri nəzərə almaq üçün sistemi yoxlayan və ya test edən şəxslər üçün faydalı olacaqdır.

Aşağıda qeyd olunanlar təsirin qiymətləndirilməsi zamanı nəzərə alınacaq sahələrdir:

* **Fərdlərə mənfi təsir**. Tələbləri və məhdudiyyətləri, nəzərdə tutulmayan istifadə yeri və sistemin performans limitlərini bilməklə bu sistemin başqa fərdlərə hansısa yolla zərər vurmayacağına əmin olmalısınız.
* **Məlumat tələbləri**. Sistemin dataları necə və harada istifadə edəcəyini öyrənməklə yoxlayan şəxslər məlumat saxlanmasındakı tələblərdə nələrə diqqət etməli olacağını biləcəklər (misal üçün GDPR və ya HIPPA data qaydaları). Əlavə olaraq datanın mənbəyini və öyrənmə üçün həcminin kifayət edəcəyi də bilinəcək.
* **Təsirin xülasəsi**. Sistemin istifadəsindən yarana biləcək bütün mümkün təhlükələrin siyahın formasında topla. MÖ prosesi boyunca təyin olunmuş problemləri necə həll edəcəyini nəzərdən keçir.
* **Uyğun məqsədlər** 6 əsas prinsipin hər birinin məqsədinə çatıla bildiyini yoxla və mümkün boşluqları düşün.


## Məsul Sİ-i izləmək

Proqram təminatlarının izlənildiyi kimi Sİ sistemlərində də problemlərin tapılması və həlli üçün izləmə mütləqdir. Modelin gözlənildiyi kimi və ya məsuliyyətlə işləməməsinə təsir edən bir çox amil var. Ənənəvi model performans göstəricilərinin əksəriyyəti modelin performansının kəmiyyət aqreqatlarıdır və modelin məsul Sİ prinsiplərini necə pozduğunu təhlil etmək üçün kifayət deyil. Bundan əlavə, maşın öyrənmə modelləri qara qutudur və onun nəticəyə necə gəldiyini başa düşmək, səhvlərini izah etmət qəlizdir. Bu kursun davamında Məsul Sİ panelini necə qura və sistemi izləyə biləcəyimizi öyrənəcəyik. İdarə paneli data tədqiqatçıları və Sİ proqramçıları üçün aşağıdakıları yerinə yetirmək üçün vahid bir alət təqdim edir:

* **Xəta analizi**. Sistemin ədalətliliyinə və ya etibarlılığına təsir edə biləcək modelin statistik xəta paylanmasını müəyyən etmək.
* **Modelin təsviri**. Data topluları arasında modelin performansında uyğunsuzluğun harada olduğunu aşkar etmək.
* **Data analizi**. Məlumatların paylanmasını başa düşmək və məlumatlarda ədalətlilik, əhatəlilik və etibarlılıq problemlərinə səbəb ola biləcək hər hansı potensial qərəzliyi müəyyən etmək.
* **Model tətbiq qabiliyyəti**. Modelin proqnozlarına nəyin təsir etdiyini başa düşmək. Bu modelin davranışını izah etməyə kömək edir, şəffaflıq və cavabdehlik üçün vacibdir.

## 🚀 Məşğələ

Zərərin baş verməsinin qabağını almaq üçün ilk növbədə biz:

- sistem üzərində işləyən insanların müxtəlif təcrübə və istiqamətlərdən gəldiyinə əmin olaq
- cəmiyyətimizin fərqliliyini özündə əks etdirən data toplusunu yığmağa sərmayə qoyaq
- problem olduqda cavabdeh Sİ-i tapmağa və düzəltməyə qadir olan daha yaxşı maşın öyrənməsi metodları tapaq

Modelin qurulmasında və istifadəsində etibarsızlığın aşkar olduğu real həyat ssenariləri haqqında düşünün. Başqa nələri nəzərə almalıyıq?

## [Mühazirə sonrası test](https://gray-sand-07a10f403.1.azurestaticapps.net/quiz/6/)

## Təkrarlayın və özünüz öyrənin

Bu dərsdə siz maşın öyrənməsində ədalət və ədalətsizlik anlayışlarının bəzi əsaslarını öyrəndiniz.

Mövzuları daha dərindən öyrənmək üçün bu seminara baxın:

- Məsuliyyətli Sİ axtarışında: Besmira Nushi, Mehrnoosh Sameki və Amit Sharma tərəfindən praktikaya prinsiplərin gətirilməsi

[![Məsuliyyətli Sİ alətləri: Məsul Sİ yaratmaq üçün açıq mənbəli çərçivə](https://img.youtube.com/vi/tGgJCrA-MZU/0.jpg)](https://www.youtube.com/watch?v=tGgJCrA-MZU "MSİ (Məsuliyyətli Sİ) Toolbox: Məsuliyyətli Sİ yaratmaq üçün açıq mənbəli çərçivə")

> 🎥 Videoya baxmaq üçün yuxarıdakı şəkilə klikləyin: MSİ (Məsuliyyətli Sİ) Toolbox: Besmira Nushi, Mehrnoosh Sameki və Amit Sharma tərəfindən məsuliyyətli Sİ yaratmaq üçün açıq mənbə çərçivəsi

Həmçinin oxuyun:

- Microsoft-un MSİ məlumat mərkəzi: [Məsuliyyətli Sİ məlumat mərkəzi – Microsoft AI](https://www.microsoft.com/ai/responsible-ai-resources?activetab=pivot1%3aprimaryr4)

- Microsoft-un FATE tədqiqat qrupu: [FATE: Süni intellektdə ədalət, cavabdehlik, şəffaflıq və etika - Microsoft Research](https://www.microsoft.com/research/theme/fate/)

MSİ Toolbox:

- [Məsuliyyətli Sİ Toolbox GitHub reposu](https://github.com/microsoft/responsible-ai-toolbox)

Ədalətliliyi təmin etmək üçün Azure Machine Learning alətləri haqqında oxuyun:

- [Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-fairness-ml?WT.mc_id=academic-77952-leestott)

## Tapşırıq

[MSİ (RAI) Toolbox kəşf edin](assignment.az.md)
