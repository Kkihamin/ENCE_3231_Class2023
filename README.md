# ENCE_3231_Class2023 Phase D

## Introduction of Project
  The inspiration initially for the final project in this class was I was researching on the internet for ideas on projects that are beneficial in my daily life and achievable in three weeks even if there are complications during the process of the project. Then, I came across a fridge alarm circuit on the internet and I thought this was a good project idea that was not too difficult to achieve in three weeks and this project could be meaningful because if someone forgets to close there refridgerator this circuit could tell them through a sound from a buzzer that the refridgerator door is open.
  The original circuit that internet provided which is given below was way too complex for three weeks because there were some challenges of implementing the original circuit. First, it was implemented on Arduino instead of the stm32cubeide that I needed to use. Second, there were two timer ic chips which it would take some time to understand to incorporate in the ide. Third, the 9 volts needed for the ic chips are not able to be provided by the voltage on the stm32F4 discovery board and I did not know how to interface a battery with the STM32F4 discovery board. This is why I made the project simplier to be able to accomplish the project in three weeks.


  ![Original idea of Fridge Alarm complex version](https://github.com/Kkihamin/ENCE_3231_Class2023/assets/129350322/3b963f1e-0243-41cf-ae86-a226dfe16fd2)



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
Below is the Schematic and flowchart of the code on paper the only thing that needs to change is the buzzer should be using pin PE9 instead of PB11 and there is no Timer2:

![Block diagram and schematic of the project on paper](https://github.com/Kkihamin/ENCE_3231_Class2023/assets/129350322/972aabb5-46ca-44a3-a927-305a9333196c)

The Schematic of the Fridge Alarm is shown in Kicad below:

<img width="892" alt="Schematic of Fridge Alarm" src="https://github.com/Kkihamin/ENCE_3231_Class2023/assets/129350322/e621cda8-ecd6-4ac5-a9fd-d5485eaf0609">



## Shield Development
Below I have included a picture of the shield for my fridge door alarm routed and in 3-D view. The only thing is that I created my own library for the HRC-SR501 motion sensor so the pins on the custom component in my custom library and at first I didn't know why they were not routing and figured out that the pins needed pin numbers so they can actually route.

<img width="657" alt="Fridge Alarm shield routed" src="https://github.com/Kkihamin/ENCE_3231_Class2023/assets/129350322/8635f890-39af-44a3-b17e-615862891943">


<img width="525" alt="Fridge Alarm shield in 3-D viewer" src="https://github.com/Kkihamin/ENCE_3231_Class2023/assets/129350322/5334bf13-c07d-4797-a6be-75fe319be492">




## Software Development
The main code for the Fridge door alarm is listed below
'''int main(void){
    HAL_Init();
    SystemClock_Config();
     MX_GPIO_Init();
     MX_TIM1_Init();
     MX_TIM2_Init();
     MX_BUZZER_Init();
     while (1)
     {

	  if(gISR_Flag_PIR){
		  HAL_GPIO_WritePin(gLED_PIN_PORT, gLED_PIN, SET); // Turn on LED
		 // HAL_GPIO_WritePin(BUZZER_PIN_PORT, BUZZER_PIN, SET); // Turn on buzzer
		  HAL_TIM_PWM_Start(&htim1, gBUZZER_TIM_CHANNEL);
		  HAL_Delay(1000); // Delay for 1 second
		  //HAL_GPIO_WritePin(BUZZER_PIN_PORT, BUZZER_PIN, RESET); // Turn off buzzer
		  HAL_TIM_PWM_Stop(&htim1, gBUZZER_TIM_CHANNEL);
		  HAL_GPIO_WritePin(gLED_PIN_PORT, gLED_PIN, RESET); // Turn off LED
		  gISR_Flag_PIR = 0; // Reset the motion detection flag
	  }


 
      }
}'''



## Demonstration
Below is a image and video recording of the Fridge door alarm being demonstrated on a breadboard that when the motion sensor detects motion the Green LED lights up and the buzzer sounds

![Demonstration of Project on STM32F4 discovery board](https://github.com/Kkihamin/ENCE_3231_Class2023/assets/129350322/61a01720-c5b8-48dd-98ba-2d21ec2fcb05)





## Future Developments
This project can definitely be developed further to be more efficient and accurate because my current demonstration is not the best cause the environment affects the motion sensor and makes it adapt and unless the white part of the ensor is completely covered to limit the range it will not be as accurate.




