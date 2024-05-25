2. За дадениот код во функцијата function нацртајте Control Flow Graph со некоја алатка за цртање дијаграми. Внесете го нацртанот CFG во документацијата.
- Објаснувањето на функцијата е претставено во слика која се наоѓа во репозиториумот.

3. Пресметајте ја цикломатската комплексност на дадениот код. Објаснете како стигнавте до резултатот.
- Во прво време го идентификуваме бројот на јазли (𝑁 N) и бројот на рабови (𝐸E). Според тоа, пресметуваме бројот на компоненти (𝑃P). Потоа ги вметнуваме овие вредности во формулата 𝑉(𝐺)=𝐸−𝑁+2𝑃V(G)=E−N+2P. За дадениот код, 𝑉(𝐺)V(G) ќе зависи од должината на баркодот (𝑛n). Откако ги пресметавме вредностите, ја добиваме цикломатската комплексност 𝑉(𝐺)V(G).

4. Напишете ги сите тест случаи според Every Branch критериумот. Напишете и објаснете ги тест случаите во документацијата.
- allItems е null:
Влез: allItems = null, payment = 100.
Излез: RuntimeException "allItems list can't be null!".
allItems е празна листа:

Влез: allItems = [], payment = 100.
Излез: false.
Сите ставки се валидни:

Влез: листа со валидни ставки, валидно payment.
Излез: true.
Името на ставката е null:

Влез: листа со една ставка со null име, валидно payment.
Излез: true.
Името на ставката е празен стринг:

Влез: листа со една ставка со празно име, валидно payment.
Излез: true.
Баркодот на ставката е null:

Влез: листа со една ставка со null баркод, валидно payment.
Излез: RuntimeException "No barcode!".
Невалиден карактер во баркодот:

Влез: листа со една ставка со баркод што содржи невалиден карактер, валидно payment.
Излез: RuntimeException "Invalid character in item barcode!".
Баркодот е валиден и има попуст, и цената е поголема од 300, првиот карактер на баркодот е '0':

Влез: листа со една ставка со валиден баркод, попуст и цена поголема од 300, првиот карактер на баркодот е '0', валидно payment.
Излез: true.
Сумата на ставките е поголема од плаќањето:

Влез: листа со ставки со сума поголема од плаќањето, валидно payment.
Излез: false.
Сумата на ставките е еднаква на плаќањето:

Влез: листа со ставки со сума еднаква на плаќањето, валидно payment.
Излез: true.


5. Напишете ги сите тест случаи според Multiple Condition критериумот за условот if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0'). Напишете и објаснете ги тест случаите во документацијата.
- Сите услови се исполнети:

Влез: item.getPrice() = 400, item.getDiscount() = 0.1, item.getBarcode().charAt(0) = '0'.
Излез: sum -= 30, вредност за останатото (напр. payment = 500).
Првиот услов не е исполнет (item.getPrice() <= 300):

Влез: item.getPrice() = 200, item.getDiscount() = 0.1, item.getBarcode().charAt(0) = '0'.
Излез: Сумата се изчислува без да се одзема 30.
Вториот услов не е исполнет (item.getDiscount() <= 0):

Влез: item.getPrice() = 400, item.getDiscount() = 0, item.getBarcode().charAt(0) = '0'.
Излез: Сумата се изчислува без да се одзема 30.
Третиот услов не е исполнет (item.getBarcode().charAt(0) != '0'):

Влез: item.getPrice() = 400, item.getDiscount() = 0.1, item.getBarcode().charAt(0) = '1'.
Излез: Сумата се изчислува без да се одзема 30.

Овие тест случаи ги покриваат сите можни комбинации на условите во if-условот.
