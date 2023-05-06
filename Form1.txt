namespace WinFormsApp18
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        int saniye = 60;
        int dakika = 5;

        int dogru2 = 0;
        int yanlis2 = 0;
        int dogru = 0;
        int yanlis = 0;

        public void sonuclar(RadioButton seciliolan)
        {
            if (seciliolan.Checked == true)
            {
                dogru++;
                seciliolan.BackColor = Color.Blue;
            }
            else
            {
                yanlis++;
            }


        }
        public void sonuclar2(RadioButton seciliolan)
        {
            if (seciliolan.Checked == true)
            {
                dogru2++;
                seciliolan.BackColor = Color.Blue;
            }
            else
            {
                yanlis2++;
            }


        }

        private void button1_Click(object sender, EventArgs e)
        {
            timer1.Start();
            button1.Visible = false;
        }

        private void timer1_Tick(object sender, EventArgs e)
        {
            timer1.Interval = 1000;
            saniye = saniye - 1;
            label3.Text = saniye.ToString();
            label2.Text = (dakika - 1).ToString();
            if (saniye == 0)
            {
                dakika = dakika - 1;
                label2.Text = dakika.ToString();
                saniye = 60;
            }
            if (label2.Text == "-1")
            {
                timer1.Stop();
                label2.Text = "00";
                label3.Text = "00";
                //show message
                MessageBox.Show("programlama dogru sýnavý sayisi", dogru.ToString());
                MessageBox.Show("programlama sýnavý yanlýþ sayisi", yanlis.ToString());
                MessageBox.Show(" donaným yanlis sayisi", yanlis2.ToString());
                MessageBox.Show(" donaným dogru sayisi", dogru2.ToString());


            }
        }

        private void comboBox1_SelectedIndexChanged(object sender, EventArgs e)
        {
            if (comboBox1.SelectedIndex == 0)
            {
                groupBox1.Visible = true;
                groupBox2.Visible = true;
                groupBox3.Visible = true;
                groupBox4.Visible = true;
                groupBox5.Visible = true;
            }
            if (comboBox1.SelectedIndex == 1)
            {
                groupBox6.Visible = true;
                groupBox7.Visible = true;
                groupBox8.Visible = true;
                groupBox9.Visible = true;
                groupBox10.Visible = true;
            }
        }

        private void button2_Click(object sender, EventArgs e)
        {

            sonuclar(radioButton3);
            sonuclar(radioButton8);
            sonuclar(radioButton13);
            sonuclar(radioButton18);
            sonuclar(radioButton21);
            sonuclar2(radioButton28);
            sonuclar2(radioButton33);
            sonuclar2(radioButton37);
            sonuclar2(radioButton41);
            sonuclar2(radioButton48);



            MessageBox.Show("dogru sayisi", dogru.ToString());
            MessageBox.Show("yanlýþ sayisi", yanlis.ToString());
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            groupBox1.Visible = false;
            groupBox2.Visible = false;
            groupBox3.Visible = false;
            groupBox4.Visible = false;
            groupBox5.Visible = false;
            groupBox6.Visible = false;
            groupBox7.Visible = false;
            groupBox8.Visible = false;
            groupBox9.Visible = false;
            groupBox10.Visible = false;

        }
    }
}