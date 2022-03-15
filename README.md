### Kalkulator
## Bardzo prosty zrobiony kalkulator

### **KOD**

```
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

// Kalkulator stworzony przez Mateusza Ścibiorskiego
// 10.03.2022
// Wersja 1.0
namespace Test_kalkulator
{
    public partial class Form1 : Form
    {
        double l_pierwszy, l_drugi , l_wynik;

        byte dzialanie = 0, l_ktora = 1, l_error = 0;
        bool drugi = false;
        public void f_dodaj(double f_liczba)
        {
            if (l_ktora < 21)
            {
                pisak.Text = pisak.Text + f_liczba.ToString();
                if (drugi == false)
                {
                    l_pierwszy = l_pierwszy * 10 + f_liczba;
                }
                else if (drugi == true)
                {
                    l_drugi = l_drugi * 10 + f_liczba;
                }
                l_ktora++;
            }
            if (l_ktora == 255)
            {
                pisak.Text = "";
                l_ktora = 0;
                f_dodaj(f_liczba);
            }
        }
        public void f_drugi(char f_znak ,byte obliczenie)
        {
            l_ktora = 255;
            pisak.Text = f_znak.ToString();
            dzialanie = obliczenie;
            drugi = true;
        }
        public void f_oblicz()
        {
            switch (dzialanie)
            {
                case 1:
                    l_wynik = l_pierwszy + l_drugi;
                    break;
                case 2:
                    l_wynik = l_pierwszy - l_drugi;
                    break;
                case 3:
                    l_wynik = l_pierwszy * l_drugi;
                    break;
                case 4:
                    l_wynik = l_pierwszy / l_drugi;
                    break;
            }
            pisak.Text = l_wynik.ToString();
            l_pierwszy = 0;
            l_drugi = 0;
            l_wynik = 0;
            l_ktora = 255;
            drugi = false;
        }

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        private void b_8_Click(object sender, EventArgs e)
        {
            f_dodaj(8);
        }

        private void pisak_Click(object sender, EventArgs e)
        {

        }

        private void b_podzielic_Click(object sender, EventArgs e)
        {
            f_drugi('/',4);
        }

        private void b_razy_Click(object sender, EventArgs e)
        {
            f_drugi('*',3);
        }

        private void b_minus_Click(object sender, EventArgs e)
        {
            f_drugi('-',2);
        }

        private void b_plus_Click(object sender, EventArgs e)
        {
            f_drugi('+',1);
        }

        private void b_clear_Click(object sender, EventArgs e)
        {
            pisak.Text = "";
            l_pierwszy = 0;
            l_drugi = 0;
            l_wynik = 0;
            l_ktora = 0;
            drugi = false;
        }

        private void b_0_Click(object sender, EventArgs e)
        {
            f_dodaj(0);
        }

        private void b_rowna_Click(object sender, EventArgs e)
        {
            f_oblicz();
        }

        private void b_9_Click(object sender, EventArgs e)
        {
            f_dodaj(9);
        }

        private void b_7_Click(object sender, EventArgs e)
        {
            f_dodaj(7);
        }

        private void b_6_Click(object sender, EventArgs e)
        {
            f_dodaj(6);
        }

        private void b_5_Click(object sender, EventArgs e)
        {
            f_dodaj(5);
        }

        private void b_4_Click(object sender, EventArgs e)
        {
            f_dodaj(4);
        }

        private void b_3_Click(object sender, EventArgs e)
        {
            f_dodaj(3);
        }

        private void b_2_Click(object sender, EventArgs e)
        {
            f_dodaj(2);
        }

        private void b_1_Click(object sender, EventArgs e)
        {
            f_dodaj(1);
        }
    }
}

```
