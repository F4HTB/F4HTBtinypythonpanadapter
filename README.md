Fork from GrayNerd's tinypythonpanadapter

![F4HTBtinypythonpanadapter](https://user-images.githubusercontent.com/18350938/82387136-834d1580-9a36-11ea-8b6c-0b5671cc9419.jpg)

requirements:

sudo apt-get install -y rtl-sdr python-pip python-numpy git pandoc git 
sudo pip install pyrtlsdr
git clone git://git.osmocom.org/rtl-sdr.git
sudo cp ./rtl-sdr/rtl-sdr.rules /etc/udev/rules.d/rtl-sdr.rules
reboot

You can see pyrtlsdr.txt to for install pyrtlsdr

run:
git clone https://github.com/F4HTB/F4HTBtinypythonpanadapter.git 
chmod 755 F4HTBtinypythonpanadapter/*.py
cd F4HTBtinypythonpanadapter/
DISPLAY=:0 ./iq.py --RTL --rtl_gain=0 --FULLSCREEN --WATERFALL --rate=2048000 --rtl_freq=145000000 --size=800 --NOMOUSE --screenresolution=800x480 --ident=F4HTB --NOSHOWFREQ --NOINFO --NOBORDER --fontsize=16 --freqgridticksinterval=100 --freqlabelticksinterval=2 --scalscreensep=50

autorun:
sudo git clone https://github.com/F4HTB/F4HTBtinypythonpanadapter.git /opt/F4HTBtinypythonpanadapter
sudo chmod 755 /opt/F4HTBtinypythonpanadapter/*.py
sudo nano /etc/xdg/lxsession/LXDE-pi/autostart
#comment all and add:
@/opt/F4HTBtinypythonpanadapter/iq.py --RTL --rtl_gain=0 --FULLSCREEN --WATERFALL --rate=2048000 --rtl_freq=145000000 --size=800 --NOMOUSE --screenresolution=800x480 --ident=F4HTB --NOSHOWFREQ --NOINFO --NOBORDER --fontsize=16 --freqgridticksinterval=100 --freqlabelticksinterval=2 --scalscreensep=50


for FT817PNA use:
@/opt/F4HTBtinypythonpanadapter/iq.py --sp_max=-70 --REV --RTL --rtl_gain=0 --FULLSCREEN --WATERFALL --rate=1024000 --rtl_freq=68330000 --size=800 --NOMOUSE --screenresolution=800x480 --ident=F6CMB --NOSHOWFREQ --NOINFO --NOBORDER --fontsize=16 --freqgridticksinterval=50 --freqlabelticksinterval=2 --scalscreensep=50


Options:
  -h, --help            show this help message and exit
  --FULLSCREEN          Switch to full screen display.
  --HAMLIB              use Hamlib to monitor/control rig frequency.
  --LAGFIX              Special mode to fix PCM290x R/L offset.
  --LCD4                Use 4" LCD instead of large screen
  --RTL                 Set source to RTL-SDR
  --SI570               Set freq control to Si570, not RTL or Hamlib
  --REV                 Reverse I & Q to reverse spectrum display
  --WATERFALL           Use waterfall display.
  --NOMOUSE             Hide mouse.
  --NOSHOWFREQ          Hide freq.
  --NOINFO              Hide info_phase.
  --NOBORDER            Hide borders.
  --cpu_load_intvl=CPU_LOAD_INTERVAL
                        Seconds delay between CPU load calculations
  --rate=SAMPLE_RATE    sample rate (Hz), eg 48000, 96000, or 1024000 or
                        2048000 (for rtl)
  --hamlib_device=HAMLIB_DEVICE
                        Hamlib serial port.  Default /dev/ttyUSB0.
  --hamlib_intvl=HAMLIB_INTERVAL
                        Seconds delay between Hamlib operations
  --hamlib_rig=HAMLIB_RIGTYPE
                        Hamlib rig type (int).  Run 'rigctl --list' for
                        possibilities.  Default is 229 (Elecraft K3/KX3).
  --index=INDEX         index of audio input card. Use pa.py to examine
                        choices.  Index -1 selects default input device.
  --lcd4_brightness=LCD4_BRIGHTNESS
                        LCD4 display brightness 0 - 100
  --n_buffers=BUFFERS   Number of FFT buffers in 'chunk', default 12
  --pulse_clip=PULSE    pulse clipping threshold, default 10.
  --rtl_freq=RTL_FREQUENCY
                        Initial RTL operating frequency (float kHz)
  --rtl_gain=RTL_GAIN   RTL_SDR gain, default 0.
  --si570_frequency=SI570_FREQUENCY
                        Si570 LO initial frequency, (float kHz)
  --size=SIZE           size of FFT.  Default is 512.
  --skip=SKIP           Skipping input data parameter >= 0
  --sp_min=SP_MIN       spectrum level, low end, dB
  --sp_max=SP_MAX       spectrum level, hi end, dB
  --v_min=V_MIN         palette level, low end, dB
  --v_max=V_MAX         palette level, hi end, dB
  --waterfall_acc=WATERFALL_ACCUMULATION
                        No. of spectra per waterfall line
  --waterfall_palette=WATERFALL_PALETTE
                        Waterfall color palette (1 or 2)
  --screenresolution=SCREENRESOLUTION
                        --screenresolution.=800x600
  --ident=IDENT         Main Windows Title
  --fontsize=FONTSIZE   fontsize >= 9
  --freqgridticksinterval=FREQGRIDTICKSINTERVAL
                        Freq Ticks interval in hz.
  --freqlabelticksinterval=FREQLABELTICKSINTERVAL
                        Ticks label interval for freq.
  --scalscreensep=SCALSCREENSEP
                        Scalar value waterfall and spectrum separation


@F4HTB 2020