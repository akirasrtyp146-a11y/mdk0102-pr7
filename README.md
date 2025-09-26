# mdk0102-pr7

using System;

class Program
{
    static void Main()
    {
        // Создаем матрицы X и Y размером 15x15
        double[,] X = new double[15, 15];
        double[,] Y = new double[15, 15];
        double[,] Z = new double[15, 15];
        
        // Инициализируем матрицы X и Y случайными значениями для демонстрации
        Random rand = new Random();
        
        // Заполняем матрицу X случайными значениями от -10 до 10
        for (int i = 0; i < 15; i++)
        {
            for (int j = 0; j < 15; j++)
            {
                X[i, j] = rand.NextDouble() * 20 - 10; // от -10 до 10
            }
        }
        
        // Заполняем матрицу Y случайными значениями от -10 до 10
        for (int i = 0; i < 15; i++)
        {
            for (int j = 0; j < 15; j++)
            {
                Y[i, j] = rand.NextDouble() * 20 - 10; // от -10 до 10
            }
        }
        
        // Вычисляем матрицу Z по формуле: z_ij = 12*x_ij - 0.85*y_ij^2
        for (int i = 0; i < 15; i++)
        {
            for (int j = 0; j < 15; j++)
            {
                Z[i, j] = 12 * X[i, j] - 0.85 * Math.Pow(Y[i, j], 2);
            }
        }
        
        // Выводим результаты
        Console.WriteLine("Матрица X (15x15):");
        PrintMatrix(X);
        
        Console.WriteLine("\nМатрица Y (15x15):");
        PrintMatrix(Y);
        
        Console.WriteLine("\nМатрица Z (15x15), вычисленная по формуле z_ij = 12*x_ij - 0.85*y_ij^2:");
        PrintMatrix(Z);
    }
    
    // Метод для вывода матрицы
    static void PrintMatrix(double[,] matrix)
    {
        int rows = matrix.GetLength(0);
        int cols = matrix.GetLength(1);
        
        for (int i = 0; i < rows; i++)
        {
            for (int j = 0; j < cols; j++)
            {
                Console.Write($"{matrix[i, j],8:F2} ");
            }
            Console.WriteLine();
        }
    }
}
