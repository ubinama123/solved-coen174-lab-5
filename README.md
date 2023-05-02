Download Link: https://assignmentchef.com/product/solved-coen174-lab-5
<br>
In this Lab, you will use UML tools to draw models using <strong>Use-case Diagrams</strong>, <strong>Class, Sequence</strong> and <strong>State-Chart</strong> diagrams.

Hopefully you have gone through PreLab5, downloaded and installed <strong>VisualParadigm </strong>Community Edition which is free (but leaves a small watermark on your diagrams). If you have not installed it on your machines, please do so. <strong>VisualParadigm</strong> makes it easy to draw various UML diagrams. The link for downloading and installation on Macs seems to point to the same link as for Windows users. If Mac users have not been able to install it, you may use <strong>Draw.io</strong>, an online tool. <strong>UMLet</strong> is another choice, but <strong>VisualParadigm </strong>gives you more flexibility.




<a href="https://www.visual-paradigm.com/download/community.jsp">VisualParadigm</a>

<a href="https://app.diagrams.net/">Draw.io</a>

<strong>Create a folder called Lab5.</strong>

You will do <strong>four</strong> exercises in this lab. You can do each exercise using VisualParadigm (recommended) or Draw.io or any other UML tool you are already familiar with.

<strong>Using VisualParadigm</strong>

Once you have installed VisualParadigm, you can open it and choose the UML diagram you want to create. For most of the diagrams, the tool gives you options to start with a blank diagram or an example template which you can edit for your purpose. You should export the diagram as an image file and save it under Lab5 folder.

<strong> </strong>

<strong>Using Draw.Io</strong>

You will use draw.io (go to <a href="https://app.diagrams.net/">https://app.diagrams.net/</a>) to draw the diagrams in exercises. Choose Device (your local machine) to store your diagram and click New Diagram. You will see the following page.







Choose the option, BlankDiagram and it will ask you to choose a name. From the options shown on the left, choose UML (see diagram below)







Now, you will see the different icons and relationship lines applicable in UML. Select them and draw your diagrams.










<strong>Note:</strong> You are required to create the diagrams using any one of the UML tools – <strong>VisualParadigm or Draw.io or any other UML tool you are familiar which allows you draw the diagrams required.</strong>







<strong> </strong>

The diagrams you will draw will use the description of a system described below.

<strong>                                                                        </strong>

<em>DreamHome_RealEstateAssistant (DHA) is a software system to help real-estate agents to list and sell houses. </em>

<em>The DHA system allows a <strong>seller</strong> to list their house for sale by providing the details of the house, price and the date it is available. The seller adds his/her details including name, address and contact information. A seller is assigned to an agent in the RealEstate co.</em>

<em>A potential buyer registers with DHA by providing his/her details, the type of house wanted, desired location, price range and other requirements. A buyer is assigned to an agent in the RealEstate co. DHA sends information to the buyers, once a week, about houses on the market that meet their requirements. </em>

<em>When a buyer shows interest in a house, DHA schedules a house tour. When a buyer agrees to purchase a house, he/she makes an offer through the RealEstate Agency. If the seller agrees on the price, an appraisal of the house is scheduled. On successful appraisal, an application may be filed with a bank for a loan (this is optional since a buyer may pay cash for the transaction). The sale will be final once the payment is made to the buyer either via cash or a bank loan.</em>

Note: you are free to make any reasonable assumptions about the software system.




<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>Exercise 1 – </strong><strong>Use Case Diagram</strong>

You will draw the Use-Case Diagram showing the important use-cases of DHA and the actors.

<strong>Identify the actors</strong><strong>:</strong> Buyer, Seller, Agent, DHAManagement for example. Identify at least 2 other actors (think appraisals, loans etc).

<strong>Identify the Use Cases</strong><strong>:</strong>

Some of the uses are: List a property, Sell a property, Buy a Property and so on. Identify others (think of appraisal, financing etc). Make sure that you connect the usecases with a dependency line (<em>includes</em> or <em>extends</em>) where applicable.




<strong>Exercise 2 – Class Diagram (simplified)</strong>

What are the different classes that you can identify in the problem description?

A <strong>Buyer, Seller, DHA, Property</strong> and so on. Create a Class Diagram with the classes given (you must identify at least one more) and draw them with some of the important attributes and operations. Connect the classes using association line, where you label the line, identify the cardinality (how many to how many). Most of the relations are binary (two classes involved) but some may involve three (a buyer buys a property from a seller).




<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>Exercise 3 – Sequence Diagram </strong>

Draw a <strong>Sequence diagram</strong> for the following scenario where a buyer wants to buy a property through DHA.

The scenario starts with the buyer object making an offer on a property – this is done by the <strong>Buyer </strong>sending a message, <em>makeOffer(propertyId,amount)</em> to a <strong>DHA</strong> object. The DHA object, sends a message, <em>offerOnProperty(propertyId, offerDetails)</em> to <strong>Property</strong> object.

On receiving the message,<em> offerOnProperty</em>(), the Property object sends a message, <em>notifySeller(offerDetails)</em> to <strong>Seller</strong> object. The <strong>Seller</strong> object sends <em>acceptOffer(offerDetails)</em> to DHA object, which in turn sends a message, <em>offerAccepted(propertId)</em> to <strong>Buyer</strong> object.

On receiving the message, <strong>offerAccepted()</strong>, buyer object sends a message, <em>applyForLoan(propertyDetails,amount)</em> to Bank object. At the same time (asynchronously), the buyer object sends a message, <em>scheduleAppraisal(propertId)</em> to <strong>Appraiser</strong> object.

The buyer object, on receiving the reply (<em>appraisalOk())</em> from Appraiser object and <em>loanGranted()</em> reply from Bank object, sends a message, <em>loanApproved(propertId)</em> to DHA object, which sends the message, <em>sold()</em> to Property object.

<strong>Exercise 4 -State Chart</strong>

Draw a state chart for a <strong>Property</strong> object.  A Property object starts from an <strong>Available</strong> (initial state) and transitions to <strong>Listed, UnderOffer, SalePending, Sold, Unlisted</strong> states. A Property object moves from its initial state to Listed state on the event, makeRealEstateListing. From Listed, a Property object moves to <strong>UnderOffer</strong>, when a buyer <em>makes an offer</em>. When it is in UnderOffer state, it can accept more offers (it stays in the same state). From UnderOffer, a Property object moves to <strong>SalePending</strong>, when the seller <em>accepts the offer</em>. On entering SalePending state (entry event), <strong>scheduleAppraisal()</strong> should take place. While in (do event) SalePending state, <strong>applyForBankLoan()</strong> should take place.

From SalePending, a Property object moves to <strong>Sold</strong>, when the <em>appraisal_ok</em> and <em>bank loan sanctioned</em>. From Sold state, the Property object moves to <strong>UnListed</strong> state (final state). From any of the states, the final state can be reached on <em>removeFromListing</em> event.