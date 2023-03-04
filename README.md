# Kitchen-Monitoring-Alert-System
Arduino Project at MSME Vishakpatnam

### Design Circuit of KMAS
- **Design 1:**
  ![image](https://user-images.githubusercontent.com/74300223/222870413-2f9a3c87-039d-4ea3-866b-90a212e6f16e.png)


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

- **Result When in Safe Condition**
  ![IMG20230217112619](https://user-images.githubusercontent.com/74300223/222869100-f10813eb-aa9d-4a45-a2c9-7a7e38eac591.jpg)

- **Result When in Lekage of Gas Detected**
  ![IMG20230217112645](https://user-images.githubusercontent.com/74300223/222869141-e77b1740-d550-4a87-ac6a-46ecf66f8df3.jpg)

- **Result When in Fire or Flame Detected**
  ![IMG20230217112120](https://user-images.githubusercontent.com/74300223/222869181-89787124-6473-4d0d-92eb-70e27203218a.jpg)
