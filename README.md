# hse_hw2_chip

# Майнор "Биоинформатика". 2 год, 2 семестр.
## Домашнее задание 2.

Google colab ноутбуки: 
- основной + бонус: https://colab.research.google.com/drive/1yvrnde7YLSN5WDUY-LpDBLQ7F6jHfyOM#scrollTo=FAQbsIJ7B_Nb,
- бонус: https://colab.research.google.com/drive/1A6g-EZFtozs-YB11OZcNFdZdPcsC5rRd?hl=ru#scrollTo=15WIxKnNnp_t.

Были выбраны клеточная линия DND-41, гистоновая метка H3K36me3 (реплика 1 - ENCFF000AQW, реплика 2 - ENCFF000AQX, контроль - ENCFF000AOG).

____

### FastQC анализ 

Первый файл (ENCFF000AQW): [ссылка](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/ENCFF000AQW_fastqc.html)

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqw1.jpg" width="500" height="300">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqw2.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqw3.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqw4.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqw5.jpg" width="500" height="400">

Второй файл (ENCFF000AQX): [ссылка](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/ENCFF000AQX_fastqc.html)

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqx1.jpg" width="500" height="300">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqx2.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqx3.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqx4.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aqx5.jpg" width="500" height="400">

Контроль (ENCFF000AOG): [ссылка](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/ENCFF000AOG_fastqc.html)

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aog1.jpg" width="500" height="300">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aog2.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aog3.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aog4.jpg" width="500" height="400">
<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/fastqc/fastqc_aog5.jpg" width="500" height="400">

Качество чтений хорошее, необходимости в подрезании или фильтрации чтений нет.

____

### Выравнивание чтений на хромосому

Была выбрана 14 хромосома.

Таблица со статистикой по каждому из 3 образцов:

- сколько ридов НЕ выравнилось (aligned 0 times),
- сколько ридов выравнилось уникально (aligned exactly 1 time),
- сколько ридов выравнилось НЕ-уникально (aligned >1 times),
- сколько ридов было в файле (total).

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/alignments/table.jpg" width="700" height="150">

Процент выравниваний получился небольшим, потому что выравнивания производились на одну хромосому (знаем, что у человека 23 пары хромосом).

____

### Диаграммы Венна с пересечениями наших MACS2 пиков и ENCODE пиков 

Первая реплика (ENCFF000AQW): [pdf1](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/venn_diagrams/first_ref.pdf), [pdf2](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/venn_diagrams/ref_first.pdf)

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/venn_diagrams/first_ref.jpg" width="400" height="300"> <img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/venn_diagrams/ref_first.jpg" width="400" height="300">

Вторая реплика (ENCFF000AQX): [pdf1](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/venn_diagrams/second_ref.pdf), [pdf2](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/venn_diagrams/ref_second.pdf)

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/venn_diagrams/second_ref.jpg" width="400" height="300"> <img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/venn_diagrams/ref_second.jpg" width="400" height="300">

Количество пиков для одной хромосомы меньше, чем количество пиков для всего генома, поэтому эти два множества пересекаются по небольшому подмножеству. На диаграммах видно, что есть много пиков, по которым множества не пересеклись. То есть многие пики, которые были найдены нами, не присутствуют среди пиков, найденных людьми, проводившими эксперименты. Скорее всего, это произошло из-за использования разных инструментов/библиотек для анализа.

Количества пиков в пересечении при разном порядке входных файлов разные, так как мы считаем число пиков в первом файле, которые пересекаются с пиками во втором.

____

### Бонус

**deeptools**

ENCFF601WGA.bigWig vs ENCFF398WGF.bigWig

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/result1.png" width="300" height="800"> <img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/result2.png" width="300" height="800">

**ngsplot**

ENCFF329TYB: [plot1](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/first.tss.avgprof.pdf), [heatmap1](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/first.tss.heatmap.pdf), [plot2](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/res1.body.avgprof.pdf), [heatmap2](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/res1.body.heatmap.pdf) 
vs
ENCFF539XMC: [plot1](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/second.tss.avgprof.pdf), [heatmap1](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/second.tss.heatmap.pdf), [plot2](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/res2.body.avgprof.pdf), [heatmap2](https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/res2.body.heatmap.pdf) 

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/first.tss.avgprof_page-0001.jpg" width="300" height="300"> <img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/second.tss.avgprof_page-0001.jpg" width="300" height="300"> 

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/first.tss.heatmap_page-0001.jpg" width="300" height="1500"> <img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/second.tss.heatmap_page-0001.jpg" width="300" height="1500">

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/res1.body.avgprof_page-0001.jpg" width="300" height="300"> <img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/res2.body.avgprof_page-0001.jpg" width="300" height="300"> 

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/res1.body.heatmap_page-0001.jpg" width="300" height="1500"> <img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/res1.body.heatmap_page-0001.jpg" width="300" height="1500">

Li e. al. (2007) Cell

<img src="https://github.com/AnyaAkhmatova/hse_hw2_chip/blob/main/bonus/article.jpg" width="300" height="300">

Теоретическая и полученная версии локализации гистоновой метки похожи. Метка обычно находится во второй половине гена, ближе к tes, отдалена от tss. На некоторых графиках (ENCFF398WGF, ENCFF539XMC) заметен всплеск у tss, которого в теоретическом распределении нет.

Виды распределений не очень похожи. Теоретическое больше похоже на нормальное, оно выпуклое, гладкое. Полученное нами не похоже на нормальное, оно имеет моду в том же месте, что и теоретическое, и еще иногда локальный максимум в районе tss.

Такая локализация гистоновой метки, видимо, как-то влияет на регуляцию транскрипции генов.
