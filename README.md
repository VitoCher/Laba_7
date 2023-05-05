#include <iostream>
#include <fstream>
#include <string>

using namespace std;

const int ARRAY_SIZE = 9;

struct human 
    {
        string first_name;
        string last_name;
        int birth_year;
    };

void sort_by_year(human arr[]) 
    {
        for (int i = 0; i < ARRAY_SIZE - 1; i++) 
            {
                for (int j = i + 1; j < ARRAY_SIZE; j++) 
                    {
                        if (arr[i].birth_year > arr[j].birth_year) 
                            {
                                human temp = arr[i];
                                arr[i] = arr[j];
                                arr[j] = temp;
                            }
                    }
            }
    }

int main() {
    human arr_1[ARRAY_SIZE];
    human arr_2[ARRAY_SIZE];

    ifstream input_file("file1.txt");
    if (input_file.is_open()) 
        {
            for (int i = 0; i < ARRAY_SIZE; i++) 
            {
                input_file >> arr_1[i].first_name >> arr_1[i].last_name >> arr_1[i].birth_year;
            }
            input_file.close();
        }

    sort_by_year(arr_1);

    for (int i = 0; i < ARRAY_SIZE; i++) 
        {
            arr_2[i] = arr_1[i];
        }

    ofstream output_file("file2.txt");
    if (output_file.is_open()) 
        {
            for (int i = 0; i < ARRAY_SIZE; i++) 
                {
                    output_file << arr_2[i].first_name << " " << arr_2[i].last_name << " " << arr_2[i].birth_year << endl;
                }
                output_file.close();
        }

    return 0;
}

################################################################################

Ippolit Sokolov 1977
Ippolit Ivanov 1985
Artem Petrov 1987
Aleksej Petrov 1989
Aleksej Mihajlov 1989
Matvej Mihajlov 1993
Sergej Vorobyaninov 1997
Andrej Smirnov 1997
Sergej Mihajlov 1999
