# Paul Thapa

Computer Engineering | Systems & Core Logic

```cpp
#include <iostream>
#include <cstdint>

// Simple 8-bit CPU state simulation
class VirtualCPU {
public:
    uint8_t reg_A = 0;
    uint8_t reg_B = 0;
    uint16_t program_counter = 0;

    void execute(std::string op, uint8_t val) {
        if (op == "LOAD_A") reg_A = val;
        else if (op == "LOAD_B") reg_B = val;
        else if (op == "ADD") reg_A += reg_B;
        program_counter++;
    }
};

int main() {
    VirtualCPU cpu;
    cpu.execute("LOAD_A", 15);
    cpu.execute("LOAD_B", 25);
    cpu.execute("ADD", 0);
    return 0;
}
