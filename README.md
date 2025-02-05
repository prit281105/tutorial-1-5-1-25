#include <iostream>

class Vehicle {
public:
    int speed;
    float fuelLevel;

    Vehicle(int spd, float fuel) : speed(spd), fuelLevel(fuel) {}

    void displayStatus() {
        std::cout << "Speed: " << speed << " km/h, Fuel Level: " << fuelLevel << " L\n";
    }
};

int main() {
    Vehicle car(0, 50.0f); 
    int Vehicle::*ptrSpeed = &Vehicle::speed;
    void (Vehicle::*ptrDisplay)() = &Vehicle::displayStatus;
    car.*ptrSpeed = 80;  // Equivalent to car.speed = 80;
    (car.*ptrDisplay)();

    return 0;
}
