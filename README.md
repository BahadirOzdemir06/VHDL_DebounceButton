# VHDL_DebounceButton
 Türkçe:
 Bu VHDL kodu bir "debounce" (zıplama bastırıcı) devresini tanımlar. Fiziksel butonlar mekanik oldukları için bastığınızda birkaç milisaniye boyunca hızlı şekilde 1-0-1-0 gibi istenmeyen "zıplamalar" (bounce) olabilir. Bu devre bu geçici zıplamaları bastırarak butonun sabit bir şekilde basılıp basılmadığını anlamayı sağlar.
////////////////////////////////////////////////////////////////
English:
This VHDL code implements a debounce circuit, which is used to suppress unwanted signal fluctuations caused by mechanical switches. When a physical push button is pressed, it may produce rapid transitions between 1 and 0 for a few milliseconds due to its mechanical structure — a phenomenon known as bouncing. This circuit filters out those temporary glitches and ensures that only stable, confirmed button presses are recognized.

////////////////////////////////////////////////////////////////////////////////////////////////////////////
# VHDL Debounce Module – Buton Zıplama Bastırıcı

## 🧠 Açıklama (Türkçe)

Bu proje, fiziksel butonlarda meydana gelen mekanik zıplamaları (bounce) filtreleyen bir debounce modülünü VHDL diliyle gerçekleştirmektedir. FSM (sonlu durum makinesi) tabanlı bu yapı, giriş sinyalinin kararlı hale gelmesini zamanlayıcı ile birlikte kontrol eder ve yalnızca geçerli (doğrulanmış) değişimleri çıkışa yansıtır.

### 🚀 Özellikler

- FSM tabanlı güvenilir debounce algoritması  
- Zamanlayıcı kontrollü geçişler  
- Parametrik yapı (saat frekansı, debounce süresi, başlangıç değeri)  
- FPGA veya CPLD platformlarında kullanılmaya uygun yapı  

### ⚙️ Parametreler (Generic)

| Parametre     | Açıklama                        | Varsayılan |
|---------------|----------------------------------|------------|
| `c_clkfreq`   | Saat frekansı (Hz cinsinden)     | 100_000_000 |
| `c_debtime`   | Debounce süresi (1/sn)           | 1000       |
| `c_initval`   | Başlangıç çıkış değeri (`'0'` veya `'1'`) | `'0'` |

### 📥 Giriş/Çıkış Portları

| Port       | Tip         | Açıklama                   |
|------------|-------------|----------------------------|
| `clk`      | `in`        | Saat sinyali               |
| `signal_i` | `in`        | Giriş (buton vb.) sinyali  |
| `signal_o` | `out`       | Debounce edilmiş çıkış     |

---

## 🧠 Description (English)

This project implements a debounce module written in VHDL to eliminate mechanical bouncing that occurs with physical push buttons. The design is based on a finite state machine (FSM) and uses a timer to verify stable signal transitions before updating the output.

### 🚀 Features

- FSM-based reliable debounce logic  
- Timer-controlled state transitions  
- Parameterized design (clock frequency, debounce time, initial value)  
- Suitable for FPGA or CPLD platforms  

### ⚙️ Parameters (Generic)

| Parameter     | Description                       | Default     |
|---------------|-----------------------------------|-------------|
| `c_clkfreq`   | Clock frequency (in Hz)           | 100_000_000 |
| `c_debtime`   | Debounce time (1/seconds)         | 1000        |
| `c_initval`   | Initial output value (`'0'` or `'1'`) | `'0'`     |

### 📥 Input/Output Ports

| Port       | Type        | Description               |
|------------|-------------|---------------------------|
| `clk`      | `in`        | Clock signal              |
| `signal_i` | `in`        | Input signal (button etc.)|
| `signal_o` | `out`       | Debounced output          |

---

## 🔧 Nasıl Kullanılır / How to Use

1. `debounce.vhd` dosyasını projenize ekleyin.
2. Parametreleri ihtiyacınıza göre düzenleyin.
3. Simülasyon veya FPGA yüklemesi ile test edin.

1.Add the debounce.vhd file to your project.

2.Adjust the generic parameters (c_clkfreq, c_debtime, c_initval) as needed.

3.Test the design through simulation or deploy it to your FPGA.


---


