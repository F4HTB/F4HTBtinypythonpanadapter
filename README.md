
Fork from GrayNerd's tinypythonpanadapter<br />
<br />
![F4HTBtinypythonpanadapter](https://user-images.githubusercontent.com/18350938/82387136-834d1580-9a36-11ea-8b6c-0b5671cc9419.jpg)<br />
<br />
<pre style="background-color:white;font-size:80%">
requirements:<br />
<br />
sudo apt-get install -y rtl-sdr python-pip python-numpy git pandoc git <br />
sudo pip install pyrtlsdr<br />
git clone git://git.osmocom.org/rtl-sdr.git<br />
sudo cp ./rtl-sdr/rtl-sdr.rules /etc/udev/rules.d/rtl-sdr.rules<br />
reboot<br />
<br />
You can see pyrtlsdr.txt to for install pyrtlsdr<br />
<br />
run:<br />
git clone https://github.com/F4HTB/F4HTBtinypythonpanadapter.git <br />
chmod 755 F4HTBtinypythonpanadapter/*.py<br />
cd F4HTBtinypythonpanadapter/<br />
DISPLAY=:0 ./iq.py --RTL --rtl_gain=0 --FULLSCREEN --WATERFALL --rate=2048000 --rtl_freq=145000000 --size=800 --NOMOUSE --screenresolution=800x480 --ident=F4HTB --NOSHOWFREQ --NOINFO --NOBORDER --fontsize=16 --freqgridticksinterval=100 --freqlabelticksinterval=2 --scalscreensep=50<br />
<br />
autorun:<br />
sudo git clone https://github.com/F4HTB/F4HTBtinypythonpanadapter.git /opt/F4HTBtinypythonpanadapter<br />
sudo chmod 755 /opt/F4HTBtinypythonpanadapter/*.py<br />
sudo nano /etc/xdg/lxsession/LXDE-pi/autostart<br />
#comment all and add:<br />
@/opt/F4HTBtinypythonpanadapter/iq.py --RTL --rtl_gain=0 --FULLSCREEN --WATERFALL --rate=2048000 --rtl_freq=145000000 --size=800 --NOMOUSE --screenresolution=800x480 --ident=F4HTB --NOSHOWFREQ --NOINFO --NOBORDER --fontsize=16 --freqgridticksinterval=100 --freqlabelticksinterval=2 --scalscreensep=50<br />
<br />
<br />
for FT817PNA use:<br />
@/opt/F4HTBtinypythonpanadapter/iq.py --sp_max=-70 --REV --RTL --rtl_gain=0 --FULLSCREEN --WATERFALL --rate=1024000 --rtl_freq=68330000 --size=800 --NOMOUSE --screenresolution=800x480 --ident=F6CMB --NOSHOWFREQ --NOINFO --NOBORDER --fontsize=16 --freqgridticksinterval=50 --freqlabelticksinterval=2 --scalscreensep=50<br />
<br />
<br />
Options:<br />
  -h, --help            show this help message and exit<br />
  --FULLSCREEN          Switch to full screen display.<br />
  --HAMLIB              use Hamlib to monitor/control rig frequency.<br />
  --LAGFIX              Special mode to fix PCM290x R/L offset.<br />
  --LCD4                Use 4" LCD instead of large screen<br />
  --RTL                 Set source to RTL-SDR<br />
  --SI570               Set freq control to Si570, not RTL or Hamlib<br />
  --REV                 Reverse I & Q to reverse spectrum display<br />
  --WATERFALL           Use waterfall display.<br />
  --NOMOUSE             Hide mouse.<br />
  --NOSHOWFREQ          Hide freq.<br />
  --NOINFO              Hide info_phase.<br />
  --NOBORDER            Hide borders.<br />
  --cpu_load_intvl=CPU_LOAD_INTERVAL<br />
                        Seconds delay between CPU load calculations<br />
  --rate=SAMPLE_RATE    sample rate (Hz), eg 48000, 96000, or 1024000 or<br />
                        2048000 (for rtl)<br />
  --hamlib_device=HAMLIB_DEVICE<br />
                        Hamlib serial port.  Default /dev/ttyUSB0.<br />
  --hamlib_intvl=HAMLIB_INTERVAL<br />
                        Seconds delay between Hamlib operations<br />
  --hamlib_rig=HAMLIB_RIGTYPE<br />
                        Hamlib rig type (int).  Run 'rigctl --list' for<br />
                        possibilities.  Default is 229 (Elecraft K3/KX3).<br />
  --index=INDEX         index of audio input card. Use pa.py to examine<br />
                        choices.  Index -1 selects default input device.<br />
  --lcd4_brightness=LCD4_BRIGHTNESS<br />
                        LCD4 display brightness 0 - 100<br />
  --n_buffers=BUFFERS   Number of FFT buffers in 'chunk', default 12<br />
  --pulse_clip=PULSE    pulse clipping threshold, default 10.<br />
  --rtl_freq=RTL_FREQUENCY<br />
                        Initial RTL operating frequency (float kHz)<br />
  --rtl_gain=RTL_GAIN   RTL_SDR gain, default 0.<br />
  --si570_frequency=SI570_FREQUENCY<br />
                        Si570 LO initial frequency, (float kHz)<br />
  --size=SIZE           size of FFT.  Default is 512.<br />
  --skip=SKIP           Skipping input data parameter >= 0<br />
  --sp_min=SP_MIN       spectrum level, low end, dB<br />
  --sp_max=SP_MAX       spectrum level, hi end, dB<br />
  --v_min=V_MIN         palette level, low end, dB<br />
  --v_max=V_MAX         palette level, hi end, dB<br />
  --waterfall_acc=WATERFALL_ACCUMULATION<br />
                        No. of spectra per waterfall line<br />
  --waterfall_palette=WATERFALL_PALETTE<br />
                        Waterfall color palette (1 or 2)<br />
  --screenresolution=SCREENRESOLUTION<br />
                        --screenresolution.=800x600<br />
  --ident=IDENT         Main Windows Title<br />
  --fontsize=FONTSIZE   fontsize >= 9<br />
  --freqgridticksinterval=FREQGRIDTICKSINTERVAL<br />
                        Freq Ticks interval in hz.<br />
  --freqlabelticksinterval=FREQLABELTICKSINTERVAL<br />
                        Ticks label interval for freq.<br />
  --scalscreensep=SCALSCREENSEP<br />
                        Scalar value waterfall and spectrum separation<br />
<br />
<br />
@F4HTB 2020
<pre>