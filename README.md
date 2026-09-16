# PWM
Analyse PWM signal generation by developing a program to switch an LED ON and OFF at one-second intervals using PWM. Examine the configured PWM frequency and duty cycle. 
---

## Apparatus Required

| S. No. | Apparatus / Software | Specification |
|:---:|---|---|
| 1 | Microcontroller Development Board | **NXP S32K144 Development Board** |
| 2 | IDE | **S32 Design Studio** |
| 3 | Programming Language | **Embedded C** |
| 4 | SDK | **S32K144 SDK** |
| 5 | LED | On-board LED / External LED |
| 6 | Programmer / Debugger | On-board Debugger / OpenSDA |
| 7 | USB Cable | For programming and power supply |

---
## Procedure
1. Connect the S32K144 Development Board to the computer using a USB cable.
2. Open S32 Design Studio.
3. Create a new project for the S32K144 microcontroller.
4. Select and configure the appropriate S32K144 SDK for the project.
5. Identify the GPIO pin connected to the LED on the S32K144 development board.
6. Configure the selected GPIO pin/Drivers as a Digital Output/input.
7. Initialize the required GPIO peripheral using the GPIO initialization functions provided by the S32K144 SDK.
8. Write the Embedded C program to control the LED using the GPIO Toggle-Pin API.
9. Insert a one-second delay between successive GPIO toggle operations.
10. The program should continuously execute the following sequence.
11. Build the project in S32 Design Studio.
12. Verify that the project is compiled successfully without errors.
13. Connect the debugger/programmer to the S32K144 Development Board.
14. Download the generated program to the S32K144 microcontroller.
15. Run the program on the S32K144 board.

---
## Program
```
#include "sdk_project_config.h"
int main(void){
	CLOCK_DRV_Init(&clockMan1_InitConfig0);
	PINS_DRV_Init(NUM_OF_CONFIGURED_PINS0, g_pin_mux_InitConfigArr0);
	PWM_Init(&pwm_pal_1_instance, &pwm_pal_1_configs);

	while(1){
		PWM_UpdateDuty(&pwm_pal_1_instance,0U,0);
		OSIF_TimeDelay(1000);
		PWM_UpdateDuty(&pwm_pal_1_instance,0U,1000);
		OSIF_TimeDelay(1000);
	}
}

```
---
## OUTPUT
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/487f9790-a032-49d3-9a72-391d489c5752" />
















---
## Result

The LED was successfully switched **ON and OFF continuously at one-second intervals** using the **GPIO Toggle-Pin API** on the **S32K144** microcontroller. The output timing was observed and verified successfully.
