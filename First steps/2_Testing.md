# EMC Guide from a beginner

After the brief introduction about generic EMC facts, we can now get into the testing, starting with conducted immunity.

## Preliminary steps

Always remember that you are doing EMC to guarantee functionality in nominal conditions.  
Everything you do in research to pass the test must then be applied also by the customer.  
Do not cover the issue with setup exploits (excessive isolation, different setups, ultrastable generators and so on), every workaround you make will present in the future as quality issues.

Always refer to the applicable standards and up to date product schematics.  
after this note, let's see a pair of core concepts before going into the tests.

## Ports

As we already said different product categories fall into different set of tests, but also inside a single object we can have different test procedures based on the injection port.  
I don't want to get into the details of each port also because the classifications is slightly different based on the specific standard reference.

The core of the topic is that each port inside a single product must be classified based on some criteria given by the standards.  
This is done using mainly the environment and the official schematics of the product.  
a port made to carry power from mains will have different tests compared to an ethernet port.

This classification is not trivial. the criteria for port classification and tests definition can have multiple variables and even change scope based on the use case: here are listed some criteria:

- working voltage/current of the port

- max lenght of the wire allowed by manufacturer

- presence of shields, and methodology of grounding

- scope of the port (sensing, power, signalling)

In addition to that the same port can have different scopes based on configuration of the object and therefore must consider worst case scenario.
When you factor in also the additional accessories prescribed by the schematic everything becomes very blurry.

Here the presence of a dedicated laboratory operator is crucial, mainly because the lab is the one that will sign the final results, and it will do it only if everything is perfect.

## Modes

Another critical concept is the classification of Differential mode (TM) and Common Mode (CM).  

Differential mode is what you would expect: a port have 2 conductors, and the disturbance is injected there, adding to the nominal signal. TM is short for Transfer Mode and is another way to say the same concept, more or less.  
You can also see this mode as an injection of the disturbance on the two wires in opposite polarity.  

Common mode should be the same in theory,if you have a 2 wire port for example, the disturbance is injected on both wires with the same polarity, this means that the net disturbance present on the port should be 0.

However we'll see that this is not true. some object may require a ground connection and in this case you will have a path for the disturbance, but even if the connection is not present we always have a path to ground due to parasitics.

## Injection Networks

Depending on the ports and on the modes each test will have a methodology to connect and to be performed.
One of the biggest issues in EMC testing is repetability. setup definition and coherence between lab is difficult due to a number of factors, for example  tolerances in the instrumentation and parasitic component control and management.

if we factor also complex setups needed to fully test non trivial functionalities, we get a lot of variables that may impact the difficult of testing and also troubleshooting.  

During testing we need to replicate the final environment as close as possible, but testing on site isn't ususally a possibility, mostly during certification and pre-certification phases.  
To replicate these conditions we make use of so called **Additional Equipment (AE)**.  
In this category are included for example all the power supplies for the object or all the communication equipment.

To miniumize these effects all the tests prescribe specific networks to correctly connect to the DUT depending on the port and on the mode. in addition to that the test prescribe analogue networks to separate the AE from the DUT and protect it from the disturbances.  
Coupling Networks and Decoupling Networks do this exact thing. Usually CN and DN are directly joined in one single object that is called Coupling-Decoupling Network or **CDN**.  
With these network we can connect in a precise way and inject the disturbance into the DUT either directly or on top of pre-existing signals while protecting the AE from unwanted malfunctions.

CDNs are usually designed similarity to the final environment while keeping consistency across laboratories and reduce or control parasitic effects.

## Close of the introduction

A lot of concepts were introduced in these documents, and they will become clearer once we dive into specific tests.

As usual Any discussion can be made on [Telegram](https://t.me/BarceFC) and the related group for comments or directly on github

I will try to modify this and the next documents to add images and make it overall prettier and easier to read.
