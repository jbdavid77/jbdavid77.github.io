---
layout: post
title:  "Choose the Right Tools"
date:   2025-09-22 
categories: tooling
excerpt_separator: <!--more-->
---
In my process of setting up this site, I found a tool that was packaged for easy installation on my OS, and developed with familiar to me languages.  The documentation looked good, but once I finished the quickstart and tried to make my site mine, I quickly started running into python syntax errors.  

To fix them I needed to reinstall and run in a less packaged way, so that I could edit the code. But fixing the tool is not the same as editing my next post. <!--more-->

In the end I dropped that tool and found one written in a new language, but that has many more users and available resources.  I don't know Ruby, and Im learning Jekyll's markdown support, but then I didn't need to fix this tool. I can proceed to using it. This tool has many more available templates should I decide the default one is not really what I want.  But if I really need to customize the tool, I will probably return to the python based one to get that working. 

The job I want to accomplish is to be able to focus on the writing, not tool development. 
If you and your team are finding yourself at a similar crossroads for your Mixed-Signal project, a conversation with the right person can be very helpful.  I may be that right person for a discussion about making sure the control functionality is correct.  Please reach out.  Some further thoughts follow for your consideration.
## Functional Verification
The primary goal of functional verification is to minimize the cost and impact of design "respins".  Additionally, this design database maybe useful for some software development.  If possible, an event driven simulator is used, which generally requires behavioral models of the analog circuits. Design impairments are only modeled so that controls for them can be tested. 
To support chip level verification efforts, these models must be developed before detailed design is ready.  This requires your modeling tool to be nimble and able to modify the model as the design matures. Ideally it will provide an easy path to checking that the model and the design are a functional match. 
Users of [MiM](https://designers-guide.com/main/) find that it's an ideal tool for this type of modeling. 

## Performance Verification
The focus here is to verify specific design performance meets goals. For most analog circuits this is accomplished with transistor level simulation in a tool like [SPICE](https://en.wikipedia.org/wiki/SPICE). But for Mixed-Signal blocks with higher levels of digital integration and many long duration simulation runs to meet strict analog performance goals - Audio, for example - using digital models of the digital blocks and analog models of many less performance critical circuits can dramatically increase simulation speed sufficiently to allow all import cases to be completed quickly enough to be re-run as a part of [tape-out](https://en.wikipedia.org/wiki/Tape-out) signoff. Modeling the critical impairments accurately is more important than speed in this case. The overall verification environment may not look much different than in the case for Functional Verification, but the pass/fail criteria are based on the performance achieved.  

In either case, tool selection is important. Please reach out at our email below if we might be of assitance. 
## Test-Bench Generation
Once the Modeling aspect of the design is accomplished, there is still the matter of a verification environment.  This includes the Test-bench that connects to the DUT , the tests and the test running, reporting and tracking mechanisms.  

[UVM](https://en.wikipedia.org/wiki/Universal_Verification_Methodology) is the de-facto standard for a verification environment, but offers little for the Mixed-Signal aspect.  Writing a System-Verilog UVM testbench is difficult enough once.  In the early stages of the design cycle, as the mixed signal part of the design is undergoing significant changes week-to-week, it quickly becomes a tedious job to update the testbench to match the design.  

This was a place where I did not find a good tool to help, but with the help of python and jinja, it was rather easy to put together a flow to re-build the testbench as the analog architecture changed.  While it took awhile the first time, I was eventually able to get to the point where the design update time was reduced enough to write tests between design updates. 

It was a story I was able to share with the world at DVCON 2024: [UVM Testbench Automation for AMS Designs]({% link /assets/pdfs/UVM_Testbench_Automation_for_AMS_Designs_DVCON2024.pdf %}).

We are happy to have a conversation about tool development like this as well.  Contact details are in footer. 



