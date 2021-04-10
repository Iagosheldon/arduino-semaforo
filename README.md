# arduino-semaforo
avaliação do curso técnico
//tinkercad

void setup()
{
  pinMode(2, INPUT); // Botão
  pinMode(3, OUTPUT);// Led Verde Semarforo Veicular
  pinMode(4, OUTPUT);// Led Amarelo Semarforo Veicular
  pinMode(5, OUTPUT);// Led Vermelho Semarforo Veicular
  pinMode(6, OUTPUT);// Led Verde Semarforo Pedestre
  pinMode(7, OUTPUT);// Led Vermelho Semarforo Pedestre
}

void loop()
{
  int botao = digitalRead(2);
  if(botao == HIGH)
  {
    for(int i = 1; i <= 10; i++)
    {
      digitalWrite(7, HIGH);
      delay(400);
      digitalWrite(7, LOW);
      delay(400);
      digitalWrite(3, LOW);
      digitalWrite(4, HIGH);
    }
    digitalWrite(7, LOW);
    digitalWrite(4, LOW);
    digitalWrite(5, HIGH);
    delay(500);
    digitalWrite(6, HIGH);
    delay(10000);
  }
  else
  {
    digitalWrite(7, HIGH);
    digitalWrite(6, LOW);
    digitalWrite(5, LOW);
    digitalWrite(4, LOW);
    delay(500);
    digitalWrite(3, HIGH);
  }
}
