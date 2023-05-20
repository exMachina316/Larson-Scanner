# Larson-Scanner
A fun project for Arduino circuit design and for loops

## Project Link
https://www.tinkercad.com/things/9NI0Kv6aiiL

## Project Image
![Screenshot from 2023-05-20 18-41-09](https://github.com/exMachina316/Larson-Scanner/assets/123073764/9278b29d-31a5-4e5e-a96e-fc2e169d5df8)

## Circuit Diagram

![Screenshot from 2023-05-20 18-36-16](https://github.com/exMachina316/Larson-Scanner/assets/123073764/4689a73f-0bfa-4c2f-bce1-577ba697c4d1)

## Code
```
int leds[10]={3,4,5,6,7,8,9,10,11,12};

void setup()
{
  for(int i=0; i<10; i++){
    pinMode(leds[i], OUTPUT);
  }
}

void sweep(int dir){
  if (dir==1){
  	for(int i=0; i<10; i++){
      digitalWrite(leds[i-1], LOW);
      digitalWrite(leds[i], HIGH);
      delay(100); 	// Wait for 1000 millisecond(s)
    }
  }
  else if(dir==-1){
    for(int i=9; i>=0; i--){
      digitalWrite(leds[i+1], LOW);
      digitalWrite(leds[i], HIGH);
      delay(100); 	// Wait for 1000 millisecond(s)
    }
  }
}

void loop(){
  	sweep(1);
	sweep(-1);
}
```
