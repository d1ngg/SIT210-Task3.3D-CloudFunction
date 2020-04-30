int led = A5;

void setup() {
    pinMode(led, OUTPUT); //set up my led connected to my argon circuit board
    Particle.subscribe("Deakin_RIOT_SIT210_Photon_Buddy", handler); //handler method is called upon photon buddy publishing an event
}


void handler(const char *event, const char *data){
    if (strcmp(data,"wave") == 0){
        Particle.publish("Deakin_RIOT_SIT210_Photon_Buddy", data, PRIVATE); //this is just to track when the buddy photon published the event
        //blink 3 times
        digitalWrite(led, HIGH);
        delay(500);
        digitalWrite(led, LOW);
        delay(500);
        digitalWrite(led, HIGH);
        delay(500);
        digitalWrite(led, LOW);
        delay(500);
        digitalWrite(led, HIGH);
        delay(500);
        digitalWrite(led, LOW);
    }
}

void loop() {

}
