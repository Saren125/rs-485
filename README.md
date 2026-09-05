# RS-485 MCU Load Control Module (Work in Progress) / Модуль Управления Нагрузкой с Интерфейсом RS-485 на МК (В разработке)

[English](#english) | [Русский](#русский)

---

## English

### Project Overview
A robust, industrial-grade microcontroller module designed for load control and communication via an isolated **RS-485** interface. The heart of the system is an **STM32F103** MCU, complemented by a fully isolated RS-485 transceiver. 

The module features a highly reliable dual-stage power architecture and strict isolation between high-power switching nodes and sensitive digital logic to ensure flawless operation in high-noise industrial environments.

> **Status:** Schematics completed. PCB layout and manufacturing files are currently under development.

### Technical Specifications
* **Microcontroller:** STMicroelectronics **STM32F103C8T6** (ARM Cortex-M3)
* **Interface:** Isolated RS-485 using **ADM2587EBRWZ** (Features integrated signal and power galvanic isolation).
* **Power Supply Architecture (Dual-Stage):**
  1. *Stage 1 (Buck):* **LM2596S-5.0** high-efficiency switching regulator drops input voltage down to 5.0V.
  2. *Stage 2 (LDO):* **AMS1117-3.3** linear regulator provides ultra-low-noise 3.3V power directly to the MCU core.
* **Load Rating:** Up to **2A** control capacity.
* **CAD Software:** Altium Designer

### Design Strategy & Hardware Features
* **Galvanic Isolation:** The ADM2587E transceiver fully separates the RS-485 bus from the internal digital logic, protecting the MCU from ground loops, high-voltage surges, and communication line faults.
* **Grounding Strategy:** Rigid separation between the digital ground (`GND_Digital`) and high-current/power ground (`GND_Power`) to shield the analog/digital circuitry from switching noise.
* **Dual-Stage Regulation:** Combining a switching buck with a linear LDO guarantees maximum power efficiency without sacrificing the voltage stability required for the ARM microcontroller.

---

## Русский

### Обзор проекта
Надежный модуль управления нагрузкой промышленного класса с поддержкой обмена данными по изолированному интерфейсу **RS-485**. Устройство построено на базе микроконтроллера **STM32F103** и специализированного трансивера с полной гальванической развязкой сигналов и питания.

В модуле реализована двухступенчатая топология питания и жесткое разделение силовых и сигнальных цепей для стабильной работы в условиях высокого уровня индустриальных помех.

> **Текущий статус:** Схема полностью готова. Трассировка печатной платы и подготовка файлов для производства находятся в активной разработке.

### Технические характеристики
* **Микроконтроллер:** STMicroelectronics **STM32F103C8T6** (ARM Cortex-M3)
* **Интерфейс связи:** Изолированный RS-485 на базе **ADM2587EBRWZ** (микросхема со встроенной гальванической развязкой сигнальных линий и линий питания).
* **Архитектура питания (Двухступенчатая):**
  1. *1-я ступень:* Высокоэффективный импульсный понижающий регулятор **LM2596S-5.0** (понижение входного напряжения до 5.0В).
  2. *2-я ступень:* Линейный стабилизатор (LDO) **AMS1117-3.3** (формирование чистых 3.3В без импульсных помех для питания ядра МК).
* **Коммутируемая нагрузка:** До **2А**.
* **Программное обеспечение:** Altium Designer.

### Особенности схемотехники и трассировки
* **Гальваническая развязка:** Применение трансивера ADM2587E изолирует шину RS-485 от внутренней логики устройства, защищая МК от контуров заземления (ground loops), высоковольтных скачков и повреждений линии связи.
* **Разделение земель:** Цифровая (сигнальная) земля и силовая земля нагрузки строго разделены, что исключает влияние импульсных токов коммутации на стабильность работы цифровой части.
* **Двухступенчатая стабилизация:** Связка из импульсного buck-регулятора и линейного LDO обеспечивает высокий общий КПД системы при сохранении идеальной стабильности напряжения питания для ARM-ядра.
