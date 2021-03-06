# Отчет

## Седых Иван Дмитриевич БПМ185  

Я подбирал параметры порядка 80 распределений методом максимума правдоподобия.  

Я использовал два теста и получил для них разные результаты.

1. Сумма квадратов отклонений 
   $$
    \operatorname{RSS} = \sum_{i=1}^k (p_o(x_i)-p_e(x_i))^2
   $$
    где $p_o,p_e$ - наблюдаемая и полученная вероятностная мера соответственно.  
    Лучшим оказалось **полунормальное** распределение [подробнее](https://en.wikipedia.org/wiki/Half-normal_distribution).  
    $$
    f(x) = \sqrt{\frac 2 {\pi \sigma^2}} \exp\left({-\frac{(x-\mu)^2}{2\sigma^2}}\right)
$$
    с параметрами   
    $\mu=0.999999999437237 \\ \sigma =3.3289457211368303$  
    и результатом теста $\operatorname{RSS}=0.000346$

2. Дивергенция Кульбака-Лейблера  
   Лучшим оказалось **распределение Рэлея** [подробнее](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.rayleigh.html#scipy.stats.rayleigh)
   $$
    f(x) = \frac{x-\mu}{{\sigma^2 }}\exp \left( -\frac{{{(x-\mu)}^{2}}}{2{{\sigma }^{2}}} \right)
    $$
    с параметрами   
    $\mu=-2.0946774390877483 \\ \sigma =3.442789771163416$  
    и результатом теста $0.043922$.