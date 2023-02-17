# Home-Monitoring-Alert-System
IOT Project at MSME Vishakpatnam

### Plannig of Design Circuit of HMAS
- **Design 1:**
  ![image](https://user-images.githubusercontent.com/74300223/216752330-40f2fe6a-12cb-4468-ba9a-1484f5ddef46.png)
- **Design 2:**
  ![image](https://user-images.githubusercontent.com/74300223/216752690-d56c30bc-2882-4ee8-9432-1facc7657b61.png)
- **Design 3:**
  ![image](https://user-images.githubusercontent.com/74300223/216752853-4c351930-331c-4f07-bdab-be35a87b0511.png)


- **Code :**
```
    void setup() {
    pinMode(2,INPUT);
    pinMode(A0,INPUT);
    
    pinMode(5,OUTPUT);
    pinMode(6,OUTPUT);
    pinMode(7,OUTPUT);
    
    Serial.begin(9600);
  }

  void loop() {
    int gas = analogRead(A0);
    int fire = digitalRead(2);
    if (gas >180 || fire ==0){
      digitalWrite(5,0);
    }else{
      digitalWrite(5,1);
    }
     
    if(gas > 180){
      Serial.print(gas);
      Serial.println(" Gas Smoke Detected");
      tone(8,1000);
      digitalWrite(6,1);
    }
    else{
      Serial.print(gas);
      Serial.println(" No Gas Smoke Detected");
      noTone(8);
      digitalWrite(6,0);
    }
    if (fire==0){
        Serial.println("Fire Detected");
        digitalWrite(7,1);
   
      }
    else{
        digitalWrite(7,0);
        Serial.println("No Fire Detected");
      }  
      delay(1000);
  }
```
