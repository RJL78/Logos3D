# Logos3D : A different approach to object classification
by Raphael Jaiyung Laporte 

# Description and Background: 

The aim of this project is to investigate the use of text as a descriptor in the classification of objects. Of course, this only applies to objects on which text is present and defining. Examples of such objects would be cereal boxes, soda bottles and most food products. 
The underlying idea is that if two objects have the same text in the same places on its surface as on another, the two objects are likely to be identical. 

This project contains three components: 
   - a scanner to build a 3D model of the objects we want to classify
   - a component to read text off of the 3D model (ie. compute our descriptors) 
   - a module which matches descriptors off of a single frame of an unknown object to our precomputed descriptors

Additionally, the project needs to include a way to evaluate the performance of our method. An idea could be to have our 2nd component compute a variety of descriptors, and study the reliability of our 3rd component according to which desciptors are used. 

Because of the unambiguous nature of text, and its insensitivity to lighting, we believe that text will serve as a useful descriptor. We believe this method will allow us to have a higher level of confidence when matching descriptors. Utimately, we want to leverage this to improve the performance of real-time object classification. For instance, instead of merely recognizing a can of Coca-Cola, can we distinguish between a can of Coca-Cola Light and Coca-Cola Zero? 

# Goals and Deliverables : 

Project Requirements: 
  1. All three components should be bundled together in a single application
  2. Scanning a new object and computing its descriptors should not take longer than 5 to 6 minutes. 
  3. Descriptor mactching should occur in real time or near-real time

Project Goals: 
  1. Establishing whether or not using text descriptors can be a reliable and cheap way to classify certain types of objects. 

NOTE : making our own Optical Character Recognition software goes beyond the scope of what we wish to achieve with this project. We hope to use Open Source Software for this part of the project.    

#  Challenges : 

The scanning component of our project is likely to be the trickiest. 
The first reason for this is that our project only uses an iPad for hardware. This means that for 3D modelling from Computer Vision (our project's first component), we cannot rely on Structured Light. Fortunately, much has been published on methods for 3D reconstruction which doesn't use Structured Light, but we are not yet familiar with these yet. Incorporating accelerometer data in order to speed up homography estimation should probably be used. From our research, OpenCV does not provide a straightford API for 3D modelling. 
Another challenge surrounding our scanning component is that we need to provide the user with instant feedback as to which parts of the object are still left to be scanned. How to communicate this in a way which is easy to understand? 

Descriptor extraction presents one main challenge for us: 
Any given word on our object's surface could be visible from a range of positions and angles. The object's surface itself may not be planar. How do we identify and locate text whilst running as little Optical Character Detection as possible? 

We expect our 3rd component, descriptor matching, to be relatively straightforward


#  Calendar: 

    - Week 1 : Investigate and test different Optical Character Recognition open source frameworks. Choose one.  
    - Week 2 : Read publications about different 3D reconstruction techniques, and start implementation. 
    - Week 3 : Finish implementation, and testing of 3D scanner. 
    - Week 4 : Think about, implement, and test a way of extracting text descriptors from our 3-D model
    - Week 5 : Implement and test descriptor matching 
    - Week 6 : Evaluate our method against other types of descriptors
        
    
