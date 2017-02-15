using System;
using System.IO;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;


namespace Project3
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void newToolStripMenuItem_Click(object sender, EventArgs e)
        {
            // set the title to untitled and clear the text contained in the text box
            this.Text = "Untitled";
            richTextBox1.Clear();

            // release the font from the previous file
            richTextBox1.Font.Dispose();
        }

        private void openToolStripMenuItem_Click(object sender, EventArgs e)
        {
            // title for the open file 
            openFileDialog1.Title = "Open";
            openFileDialog1.Filter = "Text Files (.txt)|*txt|All Files (*.*)|*.*";

            // open file
            if (openFileDialog1.ShowDialog() == DialogResult.OK)
            {

                StreamReader reader = new StreamReader(File.OpenRead(openFileDialog1.FileName));

                // Read user information into the rich text box
                richTextBox1.Text = reader.ReadToEnd();
                
                // close streamreader
                reader.Dispose();
            }
            this.Text = openFileDialog1.FileName;
        }

        private void saveToolStripMenuItem_Click(object sender, EventArgs e)
        {
            // title for the save file
            saveFileDialog1.Title = "Save As";
            saveFileDialog1.Filter = "Text File (*txt)|*txt| All Files (*.*)|*.*";

            if(saveFileDialog1.ShowDialog() == DialogResult.OK)
            {
                StreamWriter writer = new StreamWriter(File.Create(saveFileDialog1.FileName));

                // save the text contained within the rich text box...
                writer.Write(richTextBox1.Text);

                // close streamwriter
                writer.Dispose();

            }
            this.Text = saveFileDialog1.FileName;
        }

        private void wordWrapToolStripMenuItem_Click(object sender, EventArgs e)
        {
            // set the word wrap to true if it is false
            if (!richTextBox1.WordWrap)
            {
                richTextBox1.WordWrap = true;
            }
            else
            {
                richTextBox1.WordWrap = false;
            }
        }

        private void fontToolStripMenuItem_Click(object sender, EventArgs e)
        {
            if(fontDialog1.ShowDialog() == DialogResult.OK)
            {
                richTextBox1.Font = fontDialog1.Font;
            }
        }
    }
}
