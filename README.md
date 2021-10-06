# p-comp-week-1-labs-20007213
p-comp-week-1-labs-20007213 created by GitHub Classroom
#define LED 3       //led_1 I/O number is 3     
#define KEY 2       //key_1 I/O number is 2
 
#define LED2 5      //led_2 I/O number is 5
#define KEY2 4      //key_2 I/O number is 4
 
int KEY_NUM1 = 0;    //key_1 value 
int KEY_NUM2 = 0;    //key_2 value 
 
void setup()
{
  pinMode(LED,OUTPUT);			        // led_1 I/O is OUTPUT
  pinMode(KEY,INPUT_PULLUP);        //led_1 I/O is INPUT_PULLUP
  pinMode(LED2,OUTPUT);
  pinMode(KEY2,INPUT_PULLUP);		
  
  Serial.begin(300);
}
 
void loop()
{
  ScanKey();						
  ScanKey2();
 
}
 

void ScanKey()						
{
  KEY_NUM1 = 0;							          
  if(digitalRead(KEY) == LOW)			    
  {
    delay(20);						            
    if(digitalRead(KEY) == LOW)		    
    {
      KEY_NUM1 = 1;				            
      while(digitalRead(KEY) == LOW);	
    }
    Serial.println(digitalRead(LED));
  }
 
  if(KEY_NUM1 == 1)             
  {   
    digitalWrite(LED,!digitalRead(LED));    
  }
  
}
 
// 2
void ScanKey2()					
{
  KEY_NUM2 = 0;						
  if(digitalRead(KEY2) == LOW)			
  {
    delay(20);					
    if(digitalRead(KEY2) == LOW)		
    {
      KEY_NUM2 = 1;				
      while(digitalRead(KEY2) == LOW);	
    }
      Serial.println(digitalRead(LED2));
  }
 
  if(KEY_NUM2 == 1)
  {
    digitalWrite(LED2, !digitalRead(LED2)); 
  }
}
