# Coding AIs

- **Project IDX**
- **ChatHub.gg**
- **Qwen 2.5 Max**
- **Windsurf IDE**
- **Cline** (Autonomous Coding Agent)
- **Websim.ai** (Prototyping GUIs, websites)
- **Zzzzcode**
- **Youtube channel WorldofAI** (AI coding rollouts and technologies)
- **TAAFT** (There's An AI For That)

## Prompting Strategies

- **More detail, the better**
- **Code priming**

  Example: 
  ```javascript
  // Create interactive polyrhythmic pendulum simulator with the following starter code:
  class Pendulum {
    constructor(index) {
      this.index = index;
      this.angle = 0;
      this.length = 10 + index * 2;
      this.tempoOffset = 0.01 * index;
      this.speed = 0.01 + this.tempoOffset * 0.001;
      this.angularVelocity = 0;
      this.angularAcc = 0;
      this.prevAngle = 0; // Keep track of the previous angle
      this.env = new p5.Envelope();
      this.env.setADSR(0.01, 0.01, 1, 0.1);
      this.env.setRange(1, 0);

      this.note = midiNotes[index % midiNotes.length];
      this.osc = new p5.Oscillator();
      this.osc.start();
      this.osc.freq(midiToFreq(this.note));
      this.osc.amp(this.env);
    }

    update() {
      this.angle += this.speed;
      if (motionTypeSelector.value() === 'Spiral') {
        this.length += 0.1; // Increase length for spiral effect
      }

      // Calculate position based on angle and length
      this.x = width / 2 + 3 * cos(this.angle) * this.length;
      this.y = height / 2 + 3 * sin(this.angle) * this.length;
      if ((Math.sign(this.angle) !== Math.sign(this.prevAngle)) || (Math.abs(this.angle) < 0.1 && Math.abs(this.prevAngle) > 0.1)) {
        this.env.play(); // Play the sound when the pendulum crosses angle 0
      }
      this.prevAngle = this.angle; // Update the previous angle
    }
  }



