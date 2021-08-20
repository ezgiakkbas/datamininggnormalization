### dataminingnormalizationC#code

## dataminingnormalizationC#code with nodejs

# z-scorenormalizationc#code 
# min-maxnormalizationc#code


* * **Min-Max normalization c# code**  
                                                         

*Finding min max normalization in data normalization with C# code                          
Calculation can be made easier with this code.*  
                                                                                         
                                          
```C#
List<int> sayiDizisi = new List<int>();                                                       
      private void button1_Click(object sender, EventArgs e)
      {
          int aralik = Convert.ToInt32(textBox1.Text);
          Random Rand = new Random();
          int sayi = 0;
          listBox1.Items.Clear();
          sayiDizisi.Clear();
          for (int i = 1; i < 15; i++)
          {
              sayi = Rand.Next(aralik);
              listBox1.Items.Add(sayi);
              sayiDizisi.Add(sayi);
          }
      }
 
      private void button2_Click(object sender, EventArgs e)
      {
          listView1.Items.Clear();
          foreach(double i in sayiDizisi)
          {
              ListViewItem liste = new ListViewItem();
              liste.Text = i.ToString();
              liste.SubItems.Add(minmaxnormalizasyon(i).ToString("0.###"));
              listView1.Items.Add(liste);
          }            
      }
      double minmaxnormalizasyon(double sayi)
      {
          double deger = (sayi - sayiDizisi.Min()) / (sayiDizisi.Max() - sayiDizisi.Min());
           return deger;
      }
   ``` 
///  
                                                                                                                                         
      
      
* * **Z-Score normalization c# code** 
      
*Finding Z-Score in data normalization with C# code                          
 Calculation can be made easier with this code.* 
 ```C#
 List<int> sayiDizisi = new List<int>();
       private void button1_Click(object sender, EventArgs e)
       {
           int sayi = Convert.ToInt32(textBox1.Text);
           listBox1.Items.Add(sayi);
           sayiDizisi.Add(sayi);
           textBox1.Text = "";
       }
 
       private void button2_Click(object sender, EventArgs e)
       {
           listView1.Items.Clear();
           double ort = ortalama(sayiDizisi);
           double ssapma = standart(sayiDizisi);
           label2.Text = "Ortalama="+ort.ToString("0.####");
           label3.Text = "Standart Sapma="+ssapma.ToString("0.####");
           foreach (double i in sayiDizisi)
           {
               ListViewItem liste = new ListViewItem();
               liste.Text = i.ToString();
               double zscore = (i - ort) / ssapma;
                 liste.SubItems.Add(zscore.ToString("0.####"));
              // liste.SubItems.Add(zscore.ToString());
               listView1.Items.Add(liste);
           }
 
       }
 
       static double ortalama(List<int> dizi) // Ortalama
       {
           double toplam = 0;
           for (int i = 0; i < dizi.Count; i++)
               toplam += dizi[i];
 
           return toplam / dizi.Count;
       }
       static double standart(List<int> dizi) // Standart Sapma
       {
           double ort = ortalama(dizi);
           double toplam = 0.0;
           for (int i = 0; i < dizi.Count; i++)
               toplam += Math.Pow((dizi[i] - ort), 2);
           return Math.Sqrt(toplam / (dizi.Count - 1));
       }
``` 
      
      //
     
     
     
     
     
