Coding AIs:

Project IDX 
ChatHub.gg
Qwen 2.5 Max
Windsurf IDE
Cline (Autonomous Coding Agent)
Websim.ai (prototyping GUIs, websites)
Zzzzcode
Youtube channel WorldofAI (AI coding rollouts and technologies)
TAAFT (Theres An AI For That)


Prompting Stratefies:

More detail, the better
Code priming
Ex: "Create interactive polyrhythmic pendulum simulator with the following starter code: 
  Sample Pendulum class:

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
"
**code priming can point the AI into following a specific paradigm, code style, designing of frameworks/libraries, and overall functionality. Code priming gives some of the logic for the AI to follow**

Use AI to create better AI (specifically for prompting):

Ask AI to do the following:

""Generate a random subset of integers from {1, 2,..., n} such that no two distinct elements in the subset have a difference of 1, 2, 4, or 5." Rewrite this 5 times, each time becoming more detailed and technical. Then generate a random programming language/paradigm to implement in for each prompt."

For a specific problem or bug, put quotes around it "" then ask the question.

Use AI to enhance prompts that are vague or too wordy and to avoid prompt overloading.

Prompting for specific AI Model optimization:

Example:

"Let P = "nXnXn 0..6 triangular arrays with each element x equal to the number its neighbors equal to 6,6,2,0,0,0,1 for x=0,1,2,3,4,5,6. In other words, Every 0 is next to 0 6's, every 1 is next to 1 6's, every 2 is next to 2 2's, every 3 is next to 3 0's, every 4 is next to 4 0's, every 5 is next to 5 0's, every 6 is next to 6 1's". Optimize P for [AI Model]. Then rewrite P" (Gemini, Deepseek, Qwen 2.5, etc).




