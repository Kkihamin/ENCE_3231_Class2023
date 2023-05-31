# ENCE_3231_Class2023 Phase D

## Introduction of Project
  The inspiration initially for the final project in this class was I was researching on the internet for ideas on projects that are beneficial in my daily life and achievable in three weeks even if there are complications during the process of the project. Then, I came across a fridge alarm circuit on the internet and I thought this was a good project idea that was not too difficult to achieve in three weeks and this project could be meaningful because if someone forgets to close there refridgerator this circuit could tell them through a sound from a buzzer that the refridgerator door is open.
  The original circuit that internet provided which is given below was way too complex for three weeks because there were some challenges of implementing the original circuit. First, it was implemented on Arduino instead of the stm32cubeide that I needed to use. Second, there were two timer ic chips which it would take some time to understand to incorporate in the ide. Third, the 9 volts needed for the ic chips are not able to be provided by the voltage on the stm32F4 discovery board and I did not know how to interface a battery with the STM32F4 discovery board. This is why I made the project simplier to be able to accomplish the project in three weeks.
  


## Components

| Components | Quantity |
| ------------- | ------------- |
| AST-030C0MR-R passive Buzzer  | 1  |
| Green LED  | 1  |
| 100 ohm resistor  | 1 |
| STM32F discovery board  | 1  |
| Wires  | 14  |

The table above shows all the components used in my final project which is the Fridge Alarm system.



## Schematic
Below is the Schematic and flowchart of the code on paper the only thing that needs to change is the buzzer should be using pin PE9 instead of PB11:

![Block diagram and schematic of the project on paper](https://github.com/Kkihamin/ENCE_3231_Class2023/assets/129350322/972aabb5-46ca-44a3-a927-305a9333196c)

The Schematic of the Fridge Alarm is shown in Kicad below:

<img width="899" alt="Schematic of Fridge Alarm" src="https://github.com/Kkihamin/ENCE_3231_Class2023/assets/129350322/9cff771e-7d96-4b72-b1e9-3db029bccae1">


## Shield Development


## Software Development


## Demonstration



## Future Developments




