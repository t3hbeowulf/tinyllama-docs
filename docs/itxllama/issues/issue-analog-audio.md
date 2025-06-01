---
search:
  exclude: true
---

# Known Issue - Analog Audio down-mixed to mono

Batch #1 and #2 (thru Rev F) are down-mixing External Line-In and External Line-Out analog connections to mono. Below details the remediation steps to restore stereo In/Out on the Blue and Green 3.5mm jacks.

### Tool Recommendations:
* [X-Acto Precision Utility Knife, Metal](https://a.co/d/3K4sjxv)
* [Benchtop Drill Press with 7-Speed CNC 795 Motor,flexible Soft Shaft Function,JTO Chuck for Precision Drilling](https://a.co/d/8muh7Dd)
* [1mm drill bits: HARFINGTON 25pcs Micro Jobber Twist Drill Bits #59 1mm / 0.0394"](https://a.co/d/gHkjsV0)
* Optional: [Pin vice: Mulwark Precision Pin Vise Hand Drill Set 25 Pcs](https://a.co/d/3Ijqc4d)
* Optional: [AM ARROWMAX Mini Electric Engraving Pen, 36 Bits With Aluminum Case](https://a.co/d/fHLRN51)
* A multimeter with "beep" continuity test: [Example: UNI-T UT210e Digital Clamp Meter](https://a.co/d/3cg1POw)
* Jig / brace for ITX-Llama board _(TBD if this really is needed)_

### Steps for fixing the External Analog Line-In Jack:
1. Place ITX-Llama upside down on a jig (if available), brace or vice
1. Identify the audio connector pins from underneath 
1. Ensure the ITX-Llama is reasonably stable by pushing on the bottom of the audio connector. _The board should not move._
1. Identify the Line-In pins 
    <p><img src=../images/issue001_identify-linein-pins.jpg title="Stereo Audio Remediation" width=50%></p>
    <p><img src=../images/issue001_identify-linein-highlight.jpg title="Line-In Remediation Highlight" width=50%></p>
1. Plug any 3.5mm cable into the blue Line-In jack _(this creates the short)_
1. Test continuity between the two identified Line-In pins
1. Using either the engraving pen with an abrasive tip OR an Xacto knife, break the trace visible between the two identified pins.
    * An engraving pen should sand/wear away the trace without digging too deep into the board. _(This will cause less wrist strain as well)_
    * An Xacto knife should be able to cut the trace by scratching it with medium pressure. **Do not gouge the board too deep!** 
    * It should look like this: 
        <p><img src=../images/issue001_linein-final-result.jpg title="Stereo Audio Line-In Remediation" width=25%></p>
1. Test continuity again between the two identified Line-In pins. 
    * If the drill was successful, there should not be any continuity. 
    * Repeat Steps 6 and 7 until the meter stops beeping, indicating continuity is broken. 
1. **Congratulations, you have restored stereo to the External Analog Line-In Jack.**

### Steps for fixing the External Analog Line-Out Jack:
#### Setup: (one-time, recheck as necessary)
1. Assumptions: 
    * You have already unpacked and set up the drill press  
    * You have loaded a 1mm drill bit into the drill press
1. Place ITX-Llama upside down on a jig (if available), brace or vice and clamp it to a drill press.
1. Identify the audio connector pins from underneath
1. Plug any 3.5mm cable into the green Line-Out jack _(this creates the short)_
1. Ensure the ITX-Llama is reasonably stable by pushing on the bottom of the audio connector. _The board should not move._
1. Set the drill press table to it's lowest depth setting _(or drill motor to its highest/tallest setting)_
1. Try a test plunge **NEXT** to a ITX-Llama board resting upside down on its jig. 
    * **The drill press should stop before the tip extends past the board.**
    * If the tip still plunges past the board, try adjusting the travel depth or limit screws until the bit does not pass through the board.
1. Once the bit is not passing through the depth of the board in its jig, carefully begin to adjust the depth so that the tip plunges just past the board _(about 1mm, use a spare 1mm drill bit for comparison)_.
1. Make several test plunges all the way to until plunge stops at the limits and check that the bit isn't too deep each time. _This is to verify that settings aren't drifting between each plunge._ 

#### Drill: (repeat for each board)
1. Place ITX-Llama upside down on a jig (if available), brace or vice and ensure it is reasonably stable and clamp it to a drill press table.
1. Identify the Line-Out pins 
    <p><img src=../images/issue001_identify-lineout-pins.jpg title="Line-Out Pin Identification" width=50%></p>
1. Test continuity between the two identified Line-Out pins 
1. With the drill **OFF**, test plunging the drill and ensure the bit tip lands directly over the correct spot. Adjust the  position of the ITX-Llama and/or fence clamps until the bit touches the right spot on each plunge. _This should be a one-time operation if using a solid jig for the ITX-Llama to rest in._
    <p><img src=../images/issue001_identify-lineout-highlight.jpg title="Line-Out Remediation Highlight" width=50%></p>
1. Once satisfied that the drill press plunges into the correct spot and the board is secure, turn **ON** the drill and make your hole.
1. Test continuity between the two identified Line-Out pins 
    * If the drilling was successful, there should not be any continuity. 
    * If there is still continuity, use the pin vice and a 1mm bit to clear out the hole until the meter stops beeping, indicating continuity is broken. 
      <p><img src=../images/issue001_final-result.jpg title="Stereo Audio Remediation" width=50%></p>
1. **Congratulations, you have restored stereo to the External Analog Line-Out Jack.**

