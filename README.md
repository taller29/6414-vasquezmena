# 6414-vasquezmena


using System;
using System.Collections.Generic;

namespace FrutasMenorPrecio
{
    // Clase que representa una fruta con nombre y precio
    class Fruta
    {
        public string Nombre { get; set; }
        public double Precio { get; set; }

        public Fruta(string nombre, double precio)
        {
            Nombre = nombre;
            Precio = precio;
        }
    }

    class Program
    {
        static Random random = new Random();

        // Genera un precio aleatorio entre 1 y 10 (con 2 decimales)
        static double GenerarPrecio()
        {
            return Math.Round(random.NextDouble() * 9 + 1, 2);
        }

        // Pide los nombres de las frutas y asigna precios
        static List<Fruta> ObtenerFrutas()
        {
            List<Fruta> frutas = new List<Fruta>();

            Console.Write("Número de frutas que desea ingresar: ");
            int n;

            // Validación básica de entrada
            while (!int.TryParse(Console.ReadLine(), out n) || n <= 0)
            {
                Console.Write("Ingrese un número válido: ");
            }

            for (int i = 1; i <= n; i++)
            {
                Console.Write($"Nombre de la fruta {i}: ");
                string nombre = Console.ReadLine() ?? "Sin nombre";

                double precio = GenerarPrecio();
                frutas.Add(new Fruta(nombre, precio));

                Console.WriteLine($"Precio de {nombre}: S/.{precio}");
            }

            return frutas;
        }

        // Retorna la fruta con el menor precio
        static Fruta FrutaMenorPrecio(List<Fruta> frutas)
        {
            Fruta menor = frutas[0];
            foreach (var fruta in frutas)
            {
                if (fruta.Precio < menor.Precio)
                    menor = fruta;
            }
            return menor;
        }

        static void Main()
        {
            Console.Clear();
            Console.WriteLine("=== SISTEMA DE FRUTAS ===\n");

            List<Fruta> frutas = ObtenerFrutas();
            Fruta barata = FrutaMenorPrecio(frutas);

            Console.WriteLine("---------------------------------------");
            Console.WriteLine($"Fruta de menor precio: {barata.Nombre} -> S/.{barata.Precio}");
            Console.WriteLine("---------------------------------------");

            Console.WriteLine("\nPresione cualquier tecla para salir...");
            Console.ReadKey();
        }
    }
}




using System;
using System.Collections.Generic;

namespace FrutasMenorPrecio
{
    // Clase que representa una fruta
    class Fruta
    {
        public string Nombre { get; set; }
        public double Precio { get; set; }

        public Fruta(string nombre, double precio)
        {
            Nombre = nombre;
            Precio = precio;
        }
    }

    class Program
    {
        static Random random = new Random();

        // Función que genera un precio aleatorio entre 1 y 10
        static double GenerarPrecio()
        {
            return Math.Round(random.NextDouble() * 9 + 1, 2);
        }

        // Función que solicita los nombres y genera los precios
        static List<Fruta> ObtenerFrutas()
        {
            List<Fruta> frutas = new List<Fruta>();

            Console.Write("Número de frutas que desea ingresar: ");
            int n = int.Parse(Console.ReadLine() ?? "0");

            for (int i = 1; i <= n; i++)
            {
                Console.Write($"Nombre de la fruta {i}: ");
                string nombre = Console.ReadLine() ?? "SinNombre";

                double precio = GenerarPrecio();
                frutas.Add(new Fruta(nombre, precio));

                Console.WriteLine($"Precio de {nombre}: S/.{precio}");
            }

            return frutas;
        }

        // Función que devuelve la fruta con el menor precio
        static Fruta FrutaMenorPrecio(List<Fruta> frutas)
        {
            Fruta menor = frutas[0];
            foreach (var fruta in frutas)
            {
                if (fruta.Precio < menor.Precio)
                    menor = fruta;
            }
            return menor;
        }

        static void Main()
        {
            Console.Clear();
            Console.WriteLine("=== SISTEMA DE FRUTAS ===\n");

            List<Fruta> frutas = ObtenerFrutas();
            Fruta barata = FrutaMenorPrecio(frutas);

            Console.WriteLine("---------------------------------------");
            Console.WriteLine($"Fruta de menor precio: {barata.Nombre} -> S/.{barata.Precio}");
            Console.WriteLine("---------------------------------------");

            Console.WriteLine("\nPresione cualquier tecla para salir...");
            Console.ReadKey();
        }
    }
}
