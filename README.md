-----------------------
# 🌐[UVM_UART_RX]

> SystemVerilog 기반 UVM을 활용해 UART IP의 **RX 모듈**을 Verification하는 프로젝트입니다.


## 🔎 Overview
본 프로젝트는 UART IP의 RX 모듈을 대상으로 UVM Testbench를 설계하고, 시뮬레이션을 통해 안정적 동작 검증을 수행합니다.

## 📌 DUT Spec Analysis

### **1. Key Parameters / Features**
- **Data Bits** : 8bit  
- **Parity Bits** : 없음 → 단순성과 리소스 절약을 위해 parity bit 미사용
- **BAUD Rate** : 9600 bps
- **Oversampling Rate** : 16  
  > UART는 asynchronous 통신이므로 TX/RX 클럭이 완벽히 맞지 않아도 동작해야 함 → **16배 Oversampling**으로 타이밍 동기화 & 정확한 데이터 샘플링 구현

---

### **2. System Block Diagram**
![System Block](https://github.com/user-attachments/assets/cdb8ee6c-ed71-44ae-be4e-9f43b3a098cb)


---

### **3. Protocol**
![Protocol](https://github.com/user-attachments/assets/c9d2f031-df47-48eb-9738-e03486856c26)


#### **필수 Protocol 규칙(ASSERTION & COVERAGE로 검증할 예정)**
| 규칙 | 설명 |
|------|------|
| **START BIT** | 각 수신 frame은 반드시 **start bit = 0**으로 시작해야 함 |
| **STOP BIT**  | 수신 종료 시 반드시 **stop bit = 1**로 끝나야 함 |
| **BIT SEQUENCE** | 데이터 bit는 **LSB → MSB** 순서로 수신 |
| **BIT WIDTH PER CLK** | 각 비트의 duration은 **baud rate**에 맞춰야 함 |

---

### **4. FSM / ASM**
**🎯 FSM**  
![FSM](https://github.com/user-attachments/assets/ab4d98de-194a-43ec-aa6f-69704e206bf9)



**🎯 ASM**  
![ASM](https://github.com/user-attachments/assets/9258bbea-55e2-4839-aee9-675114294dd5)

---



## 🔁 Verification Plan

## 📚 TB Architecture

## 📋 Testcase & Scenario

## ✨ Verification Results

## 🔥 Insights
--------------------------
