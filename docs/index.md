![drawing](img/logo_nobg.png)

# Introduction
Welcome to the bluz docs!

This is the place to get you started with your new hardware. We have divided up the documents into a few sections depending on what you are looking for.

* Tutorials: This includes step-by-step instructions for a range of topics, from setting up your boards to controlling it through the internet.
* Reference: Detailed breakdown of the firmware and cloud functions available.
* Hardware: Overview of all the different boards, shields, and gateways offered.
* Troubleshooting: Common solutions to problems you may be facing.


As always, there are plently of places to find help beyond the documentation.

* [Neighborhood](http://neighborhood.bluz.io/): Our community forums where you can ask questions and get lots of help.
* [GitHub](https://github.com/bluzDK): Everything is open source, from the firmware to the gateways to the hardware and it's all available on our github page.
* [Hackster](https://www.hackster.io/bluz): Check out what people are building with bluz, or get some great ideas for your own projects.
* [Blog](http://blog.bluz.io/): All our latest updates and thoughts on bluz and IoT in general.

# One more thing...
There is one concept we felt deserved enough attention to put on the front page. Many of you know the classic blank sketch for all Arduino boards.

    void setup() {
        //setup code
    }

    void loop() {
        //code to continuously run
    }

With bluz, there is one addition to this pattern that we want you to learn. You see, bluz is a little different as it is geared towards low power.

    void setup() {
        //setup code
    }

    void loop() {
        //this, and only this...
        System.sleep(SLEEP_MODE_DEEP);
    }

This pattern will keep your bluz board in the lowest possible power consumption state at all times, while staying connected and available. By removing code from
your loop, you will let the CPU sleep the maximum amount. Any necessary code, from Spark functions to sensor inputs can be handled through interrupts.

Of course, you don't HAVE to do this, you can still run your normal Arduino sketched. We just HIGHLY recommend it to provide maximum battery life for your projects.