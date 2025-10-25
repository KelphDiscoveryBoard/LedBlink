# LED Blink Example for STM32 Dual Core

A dual-core LED blinking implementation for STM32 microcontrollers, based on [ControllersTeach tutorial](https://controllerstech.com/).

## References
- [Video Tutorial](https://youtu.be/jI1k6p-fduE)

## Project Setup and Build Instructions

### Prerequisites
- STM32CubeIDE
- STM32 Discovery Board
- USB Cable for programming

### Build Steps

1. **Build Both Core Projects**
   - Open and build CM4 and CM7 main.c files
   - Fix the "no explicit encoding" warning if prompted

2. **Configure CM7 Core (LedBlink_CM7)**
   - Create new debug configuration
   - Record the default Port number
   - Enable "Halt all cores" option
   - Add LedBlink_CM4 to startup sequence
   - Apply and save configuration

3. **Configure CM4 Core (LedBlink_CM4)**
   - Create new debug configuration
   - Set Port number to CM7_port + 4
   - Set Reset behavior to "None"
   - Disable Download option in Startup settings
   - Apply and save configuration

4. **Running the Project**
   - Select LedBlink_CM7 debug configuration
   - Start debugging session

## Project Structure
- `CM4/` - Core M4 specific code
- `CM7/` - Core M7 specific code
- `Common/` - Shared resources

## Notes
- Ensure correct port configuration for both cores
- CM7 must be debugged first, followed by CM4
- Both cores need to be properly configured for successful operation