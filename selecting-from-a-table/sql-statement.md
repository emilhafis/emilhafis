# SQL Statement

Biz indi sadə select sorğular necə yazılır ona baxacağıq. Bunun üçün Elektron Bankind database-mizi istifadə edəcəyik.&#x20;

<figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

Databse imizi yaratdığımız Databasedə default edəkki hər dəfə ora keçməyə ehtiyac qalmasın

Biz lap əvvəldə baxmışdıq ki, `SELECT * FROM CUSTOMERS` cədvəldə olan bütün məlumatları çıxarır. Amma cədvəlimiz olmadığı üçün məlumatlar gəlməmişdir. Cədvəlimiz olduğu üçün gəlin bir daha sorğunu icra edək. Gördüyünüz kimi cədvəldə olan bütün məlumatlar qayıtdı.

<figure><img src="../.gitbook/assets/image (14) (1).png" alt=""><figcaption></figcaption></figure>

Biz həmçinində yalnız bir sütunu seçə bilərik. Beləki biz ulduz əvəzinə column adın yazırıq.

```
SELECT LAST_NAME FROM CUSTOMERS;
```



<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

Gördüyümüz kimi cədvəlimizdəki yalnız soyadları yəni last\_name lər qayıtdı. Həmçinində biz istədiyimiz qədə rcolumn adları yaza bilərik. Və statementləri bildiyimiz kimi bir birindən nöqtəli vergül ilə ayırırıq.

```
SELECT LAST_NAME, PHONE_NUMBER FROM CUSTOMERS;
```

<figure><img src="https://lh4.googleusercontent.com/g5ls1q3al272rBl-s8XYazltAILsw03q4KNTnMzyPFIGFw18jzIqjF5ergzLeVzoKFFh2Mvj-CckzmMFnAFj9D1zybreLFaHqcLo9shYkLFh4ckl9DDyp3PBScLBJG0-z4PVKsArfd-0dMWqNhsheEJm4qv3KPK5v-N0J8BKKqqJReoK8EKqi54yRjutgSPO8yA" alt=""><figcaption></figcaption></figure>

Gördüyümüz kimi syadlar ilə barbər nömrələrdə gəldi. Burada istədiyimiz qədər statement yaza bilərik. Amma onları nöqtəli vergül ilə ayırmalıyıq. Deməli biz sadə Select ilə məlumatları necə əldə edəcəyimizi öyrəndik

