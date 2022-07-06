# WSLg-OpenJTalk

---

Windows 11上のWSLgでOpenJTalkを使って音声合成

---

# 標準音声

```bash
sudo apt update -y && sudo apt upgrade -y
sudo apt install open-jtalk open-jtalk-mecab-naist-jdic hts-voice-nitech-jp-atr503-m001
sudo apt install alsa-utils

echo '本日は晴天なり。' | open_jtalk -x /var/lib/mecab/dic/open-jtalk/naist-jdic -m /usr/share/hts-voice/nitech-jp-atr503-m001/nitech_jp_atr503_m001.htsvoice -ow voice.wav
aplay voice.wav
```

# 音響モデルを変更

## MMDAgent

```bash
wget -O MMDAgent_Example-1.8.zip "https://downloads.sourceforge.net/project/mmdagent/MMDAgent_Example/MMDAgent_Example-1.8/MMDAgent_Example-1.8.zip?ts=gAAAAABixZDLgO-PdVWo3hj5y0B-SD31nNRkeakBidpFwEpaivAbujtf_AfP-FdBrIiKsP5jVB_bCo5lKUuPyyVMve1_9Q5qYQ%3D%3D&r=https%3A%2F%2Fsourceforge.net%2Fprojects%2Fmmdagent%2Ffiles%2FMMDAgent_Example%2FMMDAgent_Example-1.8%2FMMDAgent_Example-1.8.zip%2Fdownload"
unzip MMDAgent_Example-1.8.zip

echo '本日は晴天なり。' | open_jtalk -x /var/lib/mecab/dic/open-jtalk/naist-jdic -m MMDAgent_Example-1.8/Voice/mei/mei_normal.htsvoice -ow voice.wav
aplay voice.wav
```

```
MMDAgent_Example-1.8/Voice/
├── mei
│   ├── COPYRIGHT.txt
│   ├── README.txt
│   ├── mei_angry.htsvoice
│   ├── mei_bashful.htsvoice
│   ├── mei_happy.htsvoice
│   ├── mei_normal.htsvoice
│   └── mei_sad.htsvoice
├── slt
│   ├── COPYRIGHT.txt
│   └── cmu_us_arctic_slt.htsvoice
└── takumi
    ├── COPYRIGHT.txt
    ├── README.txt
    ├── takumi_angry.htsvoice
    ├── takumi_happy.htsvoice
    ├── takumi_normal.htsvoice
    └── takumi_sad.htsvoice
```

---

Copyright (c) 2022 YA-androidapp(https://github.com/YA-androidapp) All rights reserved.
