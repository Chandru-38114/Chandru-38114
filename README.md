#include <stdio.h>

float celsius_to_fahrenheit(float celsius) {
    return (celsius * 9.0 / 5.0) + 32;
}

float celsius_to_kelvin(float celsius) {
    return celsius + 273.15;
}

float fahrenheit_to_celsius(float fahrenheit) {
    return (fahrenheit - 32) * 5.0 / 9.0;
}

float fahrenheit_to_kelvin(float fahrenheit) {
    return (fahrenheit - 32) * 5.0 / 9.0 + 273.15;
}

float kelvin_to_celsius(float kelvin) {
    return kelvin - 273.15;
}

float kelvin_to_fahrenheit(float kelvin) {
    return (kelvin - 273.15) * 9.0 / 5.0 + 32;
}

void convert_temperature(float value, char unit) {
    if (unit == 'C' || unit == 'c') {
        float fahrenheit = celsius_to_fahrenheit(value);
        float kelvin = celsius_to_kelvin(value);
        printf("%.2f°C is equal to %.2f°F and %.2fK\n", value, fahrenheit, kelvin);
    } else if (unit == 'F' || unit == 'f') {
        float celsius = fahrenheit_to_celsius(value);
        float kelvin = fahrenheit_to_kelvin(value);
        printf("%.2f°F is equal to %.2f°C and %.2fK\n", value, celsius, kelvin);
    } else if (unit == 'K' || unit == 'k') {
        float celsius = kelvin_to_celsius(value);
        float fahrenheit = kelvin_to_fahrenheit(value);
        printf("%.2fK is equal to %.2f°C and %.2f°F\n", value, celsius, fahrenheit);
    } else {
        printf("Invalid unit. Please enter C for Celsius, F for Fahrenheit, or K for Kelvin.\n");
    }
}

int main() {
    float value;
    char unit;

    printf("Enter the temperature value: ");
    scanf("%f", &value);

    printf("Enter the unit of the temperature (C, F, K): ");
    scanf(" %c", &unit);

    convert_temperature(value, unit);

    return 0;
}
