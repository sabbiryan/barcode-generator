# barcode-generator
A simple barcode RnD Windows Form application

Follow the single steps to run this application : <br/>
1. Clone this repo using <code>git clone https://github.com/sabbiryan/barcode-generator.git</code> <br/>
2. Go to <code>Source\Required Fonts</code> and install the <code>IDAutomationHC39M.ttf</code> font on your local machine first. <br/>
3. Open <code>Source\Barcode\Barcode.sln</code> with visual studio (visula studio 2015 suggested). <br/>
4. Open <code>GenerateBarcode.cs</code> for visual design and click on <code>Generate Button</code> to view the code. <br/>
5. Run the application uisng keyborad function F5 or Ctrl +  F5 or click on Start.

        using (Graphics graphics = Graphics.FromImage(bitmap))
        {
            Font font = new Font("IDAutomationHC39M", 20);
            PointF point = new PointF(2f, 2f);
            SolidBrush black = new SolidBrush(Color.Black);
            SolidBrush white  = new SolidBrush(Color.White);

            graphics.FillRectangle(white, 0, 0, bitmap.Width, bitmap.Height);
            graphics.DrawString("*"+ barcode + "*", font, black, point);
        }    
Above lines of code actuatlly generate the barcode image. <br/>

To save the generated barcode image use <code>bitmap.Save(@"D:/" + DateTime.Now.Ticks + ".png", ImageFormat.Png);</code> <br/> <br/>

        using (MemoryStream memory = new MemoryStream())
        {
            bitmap.Save(memory, ImageFormat.Png);
            pictureBox1.Image = bitmap;
            pictureBox1.Height = bitmap.Height;
            pictureBox1.Width = bitmap.Width;
        }
Above lines of code used to display the generated barcode on a PictureBox.
