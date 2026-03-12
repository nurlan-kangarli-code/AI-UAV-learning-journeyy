[aerodynamika-derin-rehber.md](https://github.com/user-attachments/files/25827050/aerodynamika-derin-rehber.md)[U# 🚁 Aerodynamika — Dərin Bələdçi (Sıfırdan Ekspertə)

---

## BÖLMƏ 1: FİZİKANIN ƏSASLARİ

---

### 1.1 Newton'un 3 Qanunu — Hər Şeyin Başlanğıcı

Aerodynamikanı anlamaq üçün əvvəlcə Newtonun 3 qanununu bilmək lazımdır.

**1-ci Qanun — İnersiya:**
> Cisim ya dayanır, ya da düz xətt üzrə hərəkət edir — xarici qüvvə olmasa.

Drone havada asılı qalır (hover) — çünki Lift = Weight. Xarici qüvvə yoxdur, dəyişmir.

**2-ci Qanun — F = ma:**
> Qüvvə = Kütlə × Sürətlənmə

Drone qalxmaq istəyirsə, motorlar daha çox Lift yaratmalıdır ki, F > Weight olsun.

**3-cü Qanun — Hər fəaliyyətin əks reaksiyası var:**
> Pərvanə havanı aşağı iter → Hava dronu yuxarı iter

Bu — Thrust və Lift-in fiziki əsasıdır.

---

### 1.2 Bernoulli Prinsipinin Dərin İzahı

Sadə versiyasını öyrəndin. İndi daha dərindən baxaq.

**Bernoulli tənliyi:**
```
P + ½ρv² + ρgh = sabit
```

- P = təzyiq
- ρ (ro) = havanın sıxlığı
- v = havanın sürəti
- g = cazibə
- h = hündürlük

**Bunun mənası:**
Havanın sürəti artanda, təzyiqi azalır. Enerji saxlanır — sürətin artması təzyiqi "istehlak edir."

**Real nümunə — Venturi effekti:**
```
Geniş boru → Dar boru → Geniş boru
[====>]  →  [==>]  →  [====>]
Yavaş        Sürətli    Yavaş
Yüksək       Aşağı      Yüksək
təzyiq       təzyiq     təzyiq
```

Eyni hava eyni vaxtda keçməlidir → dar yerdə sürətlənir → təzyiq düşür.

---

### 1.3 Coanda Effekti

Hava axını əyri səthi "izləmək" istəyir.

```
Düz axın:   →→→→→→
Coanda:     →→→↘↘↘  (səthi izləyir)
                ↓
              Səthin yuxarısında aşağı təzyiq yaranır
```

Drone dizaynında qanadların forması bu effektdən istifadə edir.

---

## BÖLMƏ 2: HAVA AXINİ VƏ TURBULENTLİK

---

### 2.1 Laminar vs Turbulent Axın

**Laminar axın (hamar):**
```
→→→→→→→→→
→→→→→→→→→   (hamı eyni istiqamətdə, düzgün)
→→→→→→→→→
```
- Hava qatları bir-birini keçmədən axır
- Az enerji itkisi
- Qanad üzərindəki ideal hal

**Turbulent axın (çalxantılı):**
```
→↗↘→↗→↘↗
↗↘→↗↘→↗→   (kaos, qarışıq)
→↗↘→↘↗↘→
```
- Hava qatları qarışır, girdablar yaranır
- Çox enerji itkisi
- Daha çox drag

**Dronelar üçün problem:**
Dronelar kiçik olduğu üçün onların ətrafında hava çox asanlıqla turbulent olur. Turbulent axın Drag-i artırır, Lift-i azaldır.

---

### 2.2 Reynold Ədədi (Re) — Çox Vacib!

```
Re = (ρ × v × L) / μ

ρ = hava sıxlığı
v = sürət
L = cismin ölçüsü (uzunluq)
μ = havanın özlülüyü (viscosity)
```

**Nə deyir bu ədəd?**

| Re dəyəri | Rejim | Nümunə |
|-----------|-------|--------|
| < 2,300 | Laminar | Kiçik drone pərvanəsi |
| 2,300 – 4,000 | Keçid | Mini drone |
| > 4,000 | Turbulent | Böyük təyyarə |

**Niyə vacibdir?**
- Böyük təyyarə üçün test edilmiş qanad forması kiçik drone üçün işləməyə bilər
- Dronlar **aşağı Re** rejiminə aiddir → xüsusi pərvanə dizaynı lazımdır
- Re < 100,000 olduqda hava çox fərqli davranır

---

### 2.3 Boundary Layer (Sərhəd Qatı)

Hava səthdən keçəndə, səthin lap yaxınında nazik bir "yavaş" qat yaranır.

```
Sürətli hava:  →→→→→→→→→→→
                →→→→→→→→
Boundary         →→→→→
layer:            →→
                  → (lap yavaş, səthlə)
──────────────── QANAD SƏTHİ ──────────────
```

Bu qat:
- İncə olsa → az drag (yaxşı)
- Qalın olsa → çox drag (pis)
- "Ayrılsa" (separation) → Lift tamamilə itir → stall!

---

## BÖLMƏ 3: QANAD VƏ PƏRVANƏ FİZİKASI

---

### 3.1 Airfoil (Qanad Profili) — Formanın Sirrləri

Qanadın kəsiyinə "airfoil" deyilir.

```
       ___________
      /  Camber    \
     /    line      \
====|________________|====
    ↑                ↑
  Leading Edge    Trailing Edge
  (Ön kənar)     (Arxa kənar)
```

**Əsas parametrlər:**

- **Chord (vətər):** Leading Edge-dən Trailing Edge-ə düz xətt
- **Camber:** Qanadın nə qədər əyri olduğu (simmetrik vs asimmetrik)
- **Thickness:** Qanadın qalınlığı
- **Span:** Qanadın uzunluğu (bir ucdan digər uca)

**Simmetrik vs Asimmetrik:**
```
Simmetrik:      Asimmetrik (Cambered):
   ___              ___________
  /   \            /           \
 |     |          |_____________|
  \___/

Hər iki istiqamətdə  Yuxarıda daha çox Lift
eyni Lift            (dronlar üçün daha yaxşı)
```

---

### 3.2 Angle of Attack (Hücum Bucağı)

Qanad/pərvanənin hava axınına nəzərən bucağı.

```
Sıfır AoA:          Müsbət AoA:
→→→ [====] →→→     →→→ [/===] →→→
                           ↑
                        Lift artır

Çox böyük AoA:
      [/]
→→→  ↗        ← Hava ayrılır = STALL!
    turbulence
```

**Optimal AoA:**
- Çox az → az Lift
- Çox çox → Stall (Lift sıfıra düşür!)
- Drone pərvanələri üçün optimal: ~4-8 dərəcə

---

### 3.3 Stall (Uçuş Dayandırması) — Ən Təhlükəli Hal

Stall = Qanad/pərvanə Lift istehsalını dayandırır.

**Nə vaxt baş verir?**
AoA kritik həddən keçəndə (~15-20 dərəcə), boundary layer ayrılır.

```
Normal:                 Stall:
→→→ /====\→→→         →→↗↘→↗↘
   ↑ Lift ↑               ↓
                         Lift = 0
                         Drone düşür!
```

**Dronlarda stall:**
- Motor çox yüklənəndə
- Çox sürətli manevrlərdə
- Güclü külək zamanı

---

### 3.4 Blade Element Theory (BET) — Pərvanənin Fizikası

Pərvanəni kiçik "dilimləre" bölüb hər dilimin Lift və Drag-ini hesablayırıq.

```
Pərvanə:          Bir dilim:
   ___               AoA
  / | \           →→→/====\
 /  |  \             ↑  ↘
|   |   |           Lift  Drag
 \  |  /
  \_|_/
  hub
```

**Hər dilimdə:**
- Daha uzaqda olan dilimlər daha sürətli hərəkət edir (v = ω × r)
- Daha sürətli hərəkət = daha çox Lift
- Buna görə pərvanə ucunda pitch azaldılır (twist)

**Pərvanə twist (burma):**
```
Mərkəz:    \  (çox pitch, yavaş)
Orta:       \ (orta pitch)
Uc:          / (az pitch, sürətli)
```
Bu olmasa, uclar stall edər!

---

### 3.5 Momentum Theory — Thrust Necə Hesablanır

Pərvanə havanı aşağı iter → əks reaksiya olaraq drone yuxarı qalxır.

```
Thrust = dm/dt × Δv

dm/dt = saniyədə iter edilən havanın kütləsi
Δv    = havanın sürət artımı
```

**Sadə thrust tənliyi:**
```
T = Ct × ρ × n² × D⁴

T  = Thrust (Newton)
Ct = Thrust koeffisienti (pərvanəyə görə, ~0.08-0.15)
ρ  = hava sıxlığı (1.225 kg/m³)
n  = dövr/saniyə (RPS)
D  = pərvanə diametri (metr)
```

**Nə deyir bu formula?**
- Diametr iki qat böyüsə → Thrust 16 qat artar (D⁴!)
- Sürət iki qat artsа → Thrust 4 qat artar (n²)
- Böyük pərvanə > sürətli kiçik pərvanə (effektivlik baxımından)

---

## BÖLMƏ 4: DRONE DİNAMİKASI

---

### 4.1 6 Serbestlik Dərəcəsi (6 DOF)

Drone kosmosda 6 müxtəlif istiqamətdə hərəkət edə bilər:

**Translasiya (yerini dəyişmə):**
- X oxu → İrəli/geri
- Y oxu → Sağa/sola
- Z oxu → Yuxarı/aşağı

**Rotasiya (fırlanma):**
- Roll → X oxu ətrafında (yana əyilmə)
- Pitch → Y oxu ətrafında (irəli/geri əyilmə)
- Yaw → Z oxu ətrafında (sola/sağa dönmə)

```
        Z (yuxarı)
        ↑
        |   Y (sağa)
        |  ↗
        | /
        |/___→ X (irəli)

Roll:  ↻ X oxu ətrafında
Pitch: ↻ Y oxu ətrafında
Yaw:   ↻ Z oxu ətrafında
```

---

### 4.2 Quadrotor Kinematics — Hərəkətin Mexanikası

```
      M2(CCW)↺    M1(CW)↻
           \      /
            [BODY]
           /      \
      M3(CW)↻    M4(CCW)↺
```

**Hover (asılı qalmaq):**
Bütün motorlar eyni sürətdə → Lift = Weight → Torque sıfırlanır

**Yuxarı qalxmaq:**
Bütün motorların sürəti artır → Lift > Weight

**Yaw (dönmə):**
- Sola dönmək: M1, M4 (CW) artır; M2, M3 (CCW) azalır
- Sağa dönmək: Əksinə
- *CW motorlar artanda, drone CCW dönür (Newton 3)*

**Pitch (irəli/geri):**
- İrəli: Ön motorlar (M1, M2) azalır; Arxa motorlar (M3, M4) artır
- Drone öndən aşağı əyilir → Thrust vektoru irəli yönəlir

**Roll (yana):**
- Sağa: Sol motorlar (M2, M3) artır; Sağ motorlar (M1, M4) azalır
- Drone soldan aşağı əyilir → sağa hərəkət

---

### 4.3 Torque və Gyroscopic Effekt

**Torque problemi:**
Motor fırlandıqda, əks istiqamətdə çalxantı yaradır (torque reaksiyası).

```
Motor CW fırlanır →  Drone CCW fırlanmaq istəyir
```

Buna görə:
- 2 motor CW, 2 motor CCW
- Cütlər bir-birinin torque-unu ləğv edir

**Gyroscopic effekt:**
Sürətlə fırlanan cisim istiqamətini saxlamaq istəyir.
Drone hərəkət edəndə, pərvanələrin gyroscopic momenti kiçik bir əyilmə yaradır.
Yüksək performanslı dronlarda bu hesablanıb kompensasiya edilir.

---

### 4.4 Ground Effect (Yer Effekti)

Drone yerə yaxın uçanda, yer səthinin yaxınlığı Lift-i artırır.

```
Normal uçuş:          Yer effekti:
   [DRONE]               [DRONE]
      ↓↓↓↓                  ↓↓↓↓
   ↙  ↓  ↘               ↙↓↘↙↓↘
  (hava sərbəst yayılır)  ═══════ (yer)
                         (hava sıxışır, təzyiq artır)
```

**Nə zaman aktiv olur?**
Droneun hündürlüyü pərvanə diametrindən az olduqda.

**Niyə vacibdir?**
- Takeoff zamanı drone qəfil "atılır" kimi hiss olunur
- Landing zamanı idarə çətinləşir
- Enerji sərfiyyatı azalır (uçuş vaxtı artır!)

---

### 4.5 Vortex Ring State (VRS) — Ən Təhlükəli Hal

Bu, pilot və ya avtonom sistemin bilməli olduğu ən kritik vəziyyətdir.

**Nə baş verir?**
Drone aşağı enəndə, pərvanənin yaratdığı aşağı hava axını ilə dronun enişi toqquşur.

```
Normal uçuş:          VRS:
   [DRONE]              [DRONE]
     ↓↓↓↓                ↓↓↓↓
   (hava aşağı          ↑↑↑↑ (drone enir)
    axır)              ←[girdab]→
                       (hava geri qayıdır!)
```

**Nəticəsi:**
Pərvanə öz yarattığı turbulentliyə girir → Lift dramatik şəkildə düşür → Drone düşür!

**Nə vaxt baş verir?**
- Sürətli şaquli eniş zamanı
- Tam yüklü dronlarda
- Xüsusilə ağır yükdaşıyan dronelar üçün təhlükəlidir

**Necə qaçmaq olar?**
- Yavaş şaquli eniş
- Enişi bir az irəli hərəkətlə birləşdirmək (diagonal eniş)

---

## BÖLMƏ 5: HAVA VƏ ATMOSFER

---

### 5.1 Standart Atmosfer Modeli

```
Hündürlük    Temperatur    Sıxlıq      Təzyiq
0 m          15°C          1.225 kg/m³  101.325 kPa
1000 m       8.5°C         1.112 kg/m³  89.9 kPa
2000 m       2.0°C         1.007 kg/m³  79.5 kPa
3000 m      -4.5°C         0.909 kg/m³  70.1 kPa
```

**Dronlar üçün nəticəsi:**
Hündürlük artdıqca hava seyrəkləşir → eyni pərvanə sürəti ilə daha az Lift → motor daha çox işləməli olur → batareya daha tez boşalır.

---

### 5.2 Havanın Özlülüyü (Viscosity)

Hava "yapışqan" kimi davranır — bu, Drag-in bir hissəsidir.

**İki növ özlülük:**
- **Dinamik özlülük (μ):** Havanın daxili sürtünməsi
- **Kinematik özlülük (ν = μ/ρ):** Reynold ədədinin hesablanmasında istifadə edilir

**Temperatur təsiri:**
- İsti hava: az sıx, az özlü
- Soyuq hava: daha sıx, daha özlü
- Qış günündə drone daha yaxşı Lift, amma daha çox Drag əldə edir

---

### 5.3 Külək Modelləri

**Sabit külək:**
```
→→→→→ [DRONE] →→→→→
```
Drone ona kompensasiya edə bilir — idarəetmə sistemi meyili düzəldir.

**Güst (ani külək):**
```
      güst!
→→→  ↗↗↗↗↗ [DRONE]
→→→→
```
Qəfil artır və azalır → Drone qəfil bir yerə atılır → İdarə çətin olur.

**Türbülentlik:**
```
↗↘↗↘ [DRONE] ↙↗↘↙
↘↗↙↗          ↗↘↙↗
```
Kaotik hava hərəkəti — ən çətin idarəetmə vəziyyəti.

**Binalar ətrafında külək:**
```
        [BİNA]
→→→→→   |    | →→→→→
→→→→→   |    |
→→→    ↙|    |↘  ← turbulentlik zonası
   ↘↙↗↘↙      ↘↙↗
```
Binanın arxasında çox güclü turbulentlik olur. Drone binaların arxasına yaxın uçmamalıdır!

---

### 5.4 Termal (İsti Hava Qalxması)

Günəşdə qızınan səthlər isti hava qaldırır.

```
                 ↑↑↑
               ↑ termal ↑
              ↑          ↑
             ↑            ↑
 ═══════ İSTİ TORPAQ ═══════
```

- Drone üzərindən keçəndə qəfil yuxarı itələnir
- Qanad ilə uçan dronlar (fixed-wing) bundan istifadə edə bilər (enerji qənaəti)
- Quadrotorlar üçün çox da faydalı deyil, amma bilmək lazımdır

---

## BÖLMƏ 6: DRAG NÖVLƏRİ

---

### 6.1 Parasitic Drag (Parazit Müqaviməti)

Drone uçanda, forması havanı "kəsir" — bu müqavimət yaranır.

**3 növü var:**

**a) Form Drag:**
Cismin formasından gəlir.
```
Pis forma:  [■■■]  ← kütlə forma, çox drag
Yaxşı forma: [◄►]  ← aerodinamik forma, az drag
```

**b) Skin Friction Drag:**
Havanın səthlə sürtünməsindən gəlir.
Hamar səth → az friction drag
Kobud səth → çox friction drag

**c) Interference Drag:**
Müxtəlif hissələr bir-birinin hava axınına müdaxilə edəndə.
Motor qolları + gövdə = əlavə drag

---

### 6.2 Induced Drag (Lift-dən Gələn Müqavimət)

Lift yarandığı üçün avtomatik olaraq yaranan drag.

```
Qanad ucu:
     Yüksək     Aşağı
     təzyiq     təzyiq
       ↑          ↑
[=====alt======üst=====]
           ↓
    Qanad ucunda girdab
         (vortex)
           ↓
        Induced Drag
```

**Wingtip Vortices:**
Qanad ucunda hava yüksək təzyiqdən aşağı təzyiqə keçir → girdab yaranır.

Böyük təyyarələrdə bu o qədər güclüdür ki, arxalarından uçmaq qadağandır.
Droneların pərvanə uclarında da kiçik girdablar yaranır — bu effektivliyi azaldır.

**Aspect Ratio (En-Boy nisbəti):**
```
AR = Span² / Area

Uzun, dar pərvanə → Yüksək AR → Az Induced Drag
Qısa, geniş pərvanə → Aşağı AR → Çox Induced Drag
```

---

### 6.3 Wave Drag (Dalğa Müqaviməti)

Ses sürətinə yaxınlaşıldıqda yaranır.
Dronlar üçün praktiki deyil (onlar o qədər sürətli uçmur), amma bilik üçün vacibdir.

---

## BÖLMƏ 7: ENERJİ VƏ EFFEKTİVLİK

---

### 7.1 Figure of Merit (FM) — Hover Effektivliyi

Pərvanənin nə qədər effektiv olduğunu ölçür.

```
FM = İdeal güc / Həqiqi güc

FM = 1.0  →  Mükəmməl (mümkünsüz)
FM = 0.75  →  Çox yaxşı
FM = 0.5   →  Orta
FM < 0.4   →  Pis
```

Yaxşı drone pərvanəsi FM ≈ 0.65-0.80 aralığındadır.

---

### 7.2 Disk Loading (Disk Yükü)

```
Disk Loading = Thrust / Pərvanə sahəsi  (N/m²)
```

| Nümunə | Disk Loading |
|--------|-------------|
| Ağır qaldırıcı helikopter | Çox yüksək |
| Orta ölçülü drone | Orta |
| Böyük pərvanəli səmərəli drone | Aşağı |

**Nə deyir?**
- Aşağı disk loading → daha az enerji ilə hover → daha uzun uçuş müddəti
- Yüksək disk loading → daha çox manevr qabiliyyəti, amma az dözümlülük

---

### 7.3 Power Loading

```
Power Loading = Thrust / Motor gücü  (N/W)
```

Bu, motorun nə qədər effektiv olduğunu göstərir. Yüksək olarsa yaxşıdır.

---

## BÖLMƏ 8: AERODYNAMIC SİLAHXANASI

---

### 8.1 Reynolds Ədədi ilə Pərvanə Seçimi

```
Kiçik drone (5-7"):   Re ≈ 50,000 - 100,000
Orta drone (7-10"):   Re ≈ 100,000 - 300,000
Böyük drone (10"+):   Re ≈ 300,000+
```

Hər Re rejimi üçün fərqli airfoil forması optimal işləyir.

---

### 8.2 Tip Speed Ratio

Pərvanə ucunun səs sürətinə nisbəti.

```
TSR = (Pərvanə ucu sürəti) / (Ses sürəti)
    = (π × D × n) / 340 m/s
```

TSR > 0.7 olduqda:
- Pərvanə ucunda şok dalğaları yaranmağa başlayır
- Səs-küy dramatik şəkildə artır
- Drag artır
- Effektivlik düşür

**Practical limit:** TSR < 0.5-0.6 tövsiyə edilir

---

### 8.3 Pərvanə Materiallarının Aerodynamikaya Təsiri

| Material | Ağırlıq | Rigidity | Aerodynamik effekt |
|----------|---------|----------|-------------------|
| Plastik (nylon) | Yüngül | Aşağı | Yüksək sürətdə əyilir → pitch azalır |
| Carbon Fiber | Yüngül | Çox yüksək | Forma saxlayır → stabil Thrust |
| Folding | Orta | Orta | Atılmalarda çırpılma problemi |

---

## BÖLMƏ 9: AERODYNAMICS + KONTRol SİSTEMLƏRİ

---

### 9.1 Aerodynamika Control-a Necə Bağlıdır?

PID controller (tezliklə öyrənəcəksən) aerodynamik qüvvələrlə mübarizə aparır.

```
Xarici qüvvə (külək)
         ↓
    [Sensor (IMU)]
         ↓
    [PID Controller]
         ↓
    [Motor sürəti]
         ↓
    [Aerodynamik reaksiya]
         ↓
    [Stabilizasiya]
```

**Əsas məntiq:**
Drone aerodynamik qüvvəni ölçür → motor sürətini dəyişir → əks aerodynamik qüvvə yaradır → tarazlıq.

---

### 9.2 Propwash Effect

Drone sürətlə hərəkət edəndə, öz pərvanəsinin yarattığı turbulentliyə girə bilər.

**Nə vaxt baş verir?**
- Sürətli uçuşdan qəfil dayandıqda
- Aşağı enişdə
- Agressive manevrlarda

**Nəticə:**
Qeyri-stabil davranış, titrəmə, bəzən crash.

**Həll:**
- Props out (pərvanələri gövdədən uzaqda) dizayn
- Yaxşı filter (Betaflight-da RPM Filter)
- Yavaş manevrlar

---

## BÖLMƏ 10: XÜLASƏ — BİLMƏLİ OLDUĞUN HƏR ŞEY

---

### Fundamental Qanunlar
- Newton-un 3 qanunu hər şeyin əsasıdır
- Bernoulli: sürət ↑ → təzyiq ↓
- Lift = Aşağı sıxılan havanın əks reaksiyası

### Uçuş Fizikası
- 4 qüvvə: Lift, Weight, Thrust, Drag
- 6 DOF: x, y, z hərəkəti + Roll, Pitch, Yaw
- Stall: AoA çox böyük → Lift sıfırlanır

### Pərvanə Texnikası
- Twist (burma): uclar daha az pitch olur
- Diameter⁴ effekti: böyük pərvanə çox güclüdür
- Blade Element Theory: hər dilim ayrı analiz edilir

### Xüsusi Effektlər
- Ground Effect: yerə yaxın Lift artır
- Vortex Ring State: ən təhlükəli hal
- Propwash: öz turbulentliyinə girib çırpınma

### Atmosfer
- Hündürlük → sıxlıq ↓ → Lift ↓
- Turbulentlik → ən çətin idarəetmə şəraiti
- Binalar arxası → girdab zonası

---

## ⏭️ Növbəti Addım

Bu dərinliyi əldə etdikdən sonra sıra bunlardadır:

1. **Kontrol Sistemləri (PID)** — Drone özünü aerodynamik qüvvələrə qarşı necə tarazlayır
2. **Motor + ESC fizikası** — Elektrik → Mexanik enerji çevrilməsi
3. **Simulyasiya (Gazebo)** — Bütün bu qüvvələri virtual mühitdə test etmək
4. **ROS ilə inteqrasiya** — Aerodynamik modeli koda çevirmək

---

*"Aerodynamika fizikadan başlayır, riyaziyyatla dərinləşir, kodla həyata keçir."* 🚁
ploading aerodynamika-derin-rehber.md…]()
