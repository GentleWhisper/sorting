# sorting
bla-bla
#include <iostream>
using namespace std;

int main()
{
    // Считываем размер массива,
    // который необходимо отсортировать
    int size;
    cin >> size;

    // Динамически выделяем память под
    // хранение массива размера size
    int *a = new int[size];
    
    // Считываем массив
    for (int i = 0; i < size; i++)
    {
        cin >> a[i];
    }
    int step = size / 2;//инициализируем шаг.
    while (step > 0)//пока шаг не 0
    {
      for (int i = 0; i < (size - step); i++)
                {
                    int j = i;
                    //будем идти начиная с i-го элемента
                    while (j >= 0 && a[j] > a[j + step])
                    //пока не пришли к началу массива
                    //и пока рассматриваемый элемент больше
                    //чем элемент находящийся на расстоянии шага
                    {
                        //меняем их местами
                        int temp = a[j];
                        a[j] = a[j + step];
                        a[j + step] = temp;
                        j--; 
                    }
                }
                step = step / 2;//уменьшаем шаг
            }    
    // Выводим отсортированный массив
    for (int i = 0; i < size; i++)
    {
        cout << a[i] << ' ';
    }
	
    return 0;
	
}
