# stopwatch01
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace stopwatch
{
    public partial class Stopwatch : Form
    {
        private DateTime startTime;
        public Stopwatch()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        private void startbutton_Click(object sender, EventArgs e)
        {
            // Set a value to start time
            startTime = DateTime.Now;
            // Start the timer
            formtimer.Start();

        }

        private void stopbutton_Click(object sender, EventArgs e)
        {
            formtimer.Stop();

        }

        private void Resetbutton_Click(object sender, EventArgs e)
        {
            formtimer.Stop();
            watchlabel.Text = "00:00.00";

        }

        private void formtimer_Tick(object sender, EventArgs e)
        {
            // Calculate how long it's been since start
            TimeSpan span = DateTime.Now - startTime;
            watchlabel.Text = span.ToString(@"mm\:ss\.ff");

        }
        
    }
}
