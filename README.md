# Exchange vocab

This is separated out from the [OVN vocab](https://github.com/openvocab/ovn), of which it is a component. See also the [Principles](https://github.com/openvocab/ovn/wiki/Principles-for-this-vocabulary) for the OVN vocab, which are also the principles for this one.

## Why?

We are seeing several organizations that do exchanges, but not production processes. They also sometimes use several different software apps that might want to know about those exchanges. Some of them even conduct different exchanges in different instances of the same app, or in different apps altogether! As with all of the other Open Vocab projects, its goal is to help different apps talk to each other by means of a common vocabulary and protocols.

## Who uses this?

[NRP](https://github.com/valnet/valuenetwork) is the source of much of the vocabulary, and continues to refine the model, collaborating with user networks like [Sensorica](http://nrp.sensorica.co). [Holodex](https://github.com/open-app/holodex) is using the [organization aspects of the OVN vocab](https://github.com/openvocab/holodex).

But most of the vocabulary comes from the [Resource-Event-Agent (REA) ontology](http://en.wikipedia.org/wiki/Resources,_events,_agents_(accounting_model)) originated by [Professor William McCarthy of Michigan State University](https://www.msu.edu/~mccarth4/) in 1982, used in many places around the world.

## Overview of Exchanges

This vocabulary subset looks at exchanges of resources from an independent or neutral viewpoint (not the viewpoint of one of the Agents in the exchange). For example, from one Agent's viewpoint, the exchange may be a Purchase, from the other Agent's viewpoint, it might be a Sale. From the neutral viewpoint, it is an exchange of resources, with usually at least two flows of resources, one from each direction. So for example, the seller might give some goods to the buyer, and the buyer might give some money to the seller. Or in a barter exchange, one agent might give the other some books, and the other agent might compensate with some cookies.

This differs from (for example) the [Good Relations Conceptual Model](http://wiki.goodrelations-vocabulary.org/Documentation/Conceptual_model), which otherwise we like and want to intertrade with. But Good Relations assumes Compensation in the form of money; the compensation itself is not a separate promise; and the actual flow events are not part of the model. (That's not a criticism. Good Relations has different goals, and a more minimal model makes sense for them.)

Other related vocabularies include [this product type ontology based on Wikipedia](http://www.productontology.org/) and the [ISO Accounting and Economic Ontology based on REA](https://webstore.iec.ch/preview/info_isoiec15944-4%7Bed2.0%7Den.pdf).

In the [OVN vocab](https://github.com/openvocab/ovn), we want to track not only the offers and promises, but also the actual flows of resources in networks, in all directions. And we want to support exchanges that don't involve money as well as those that do.

![exchanges](https://docs.google.com/drawings/d/1BnVK0J6mJd9OCpqLhJPp59vyutK_Q2ggOJJSyMkNc4o/pub?w=485&h=398)


If exchanges happen between agents in different systems, then a resource transfer needs to be separated into a Give event (might be called a Shipment) in one system and a Take event (might be called a Receipt) in the other system.

If the agents operate in the same logical system, then a resource transfer can just be a transfer - a single event where the resource moves from the Giver to the Taker - although the Giver and the Taker will have different views of the same event.

### Exchange protocols

Exchanges may use any of several technical protocols, but the main human-level protocol has been in use for many years. It may be called [Offer-Acceptance](https://en.wikipedia.org/wiki/Offer_and_acceptance) or [Conversation for Action](http://conversationsforaction.com/cfa-playground). It may include several preparation stages for agents who have never exchanged anything before, or it may be really simple if they exchange resources all the time.

ISO lists 5 phases:

1. Planning: In the Planning Phase, both the buyer and seller are engaged in activities to decide what action to take for acquiring or selling a good, service, and/or right. 
2. Identification: The Identification Phase pertains to all those actions or events whereby data is interchanged among potential buyers and sellers in order to establish a one-to-one linkage.
3.  Negotiation: The Negotiation Phase pertains to all those actions and events involving the exchange of information following the Identification Phase where a potential buyer and seller have (1) identified the nature of good(s) and/or service(s) to be provided; and, (2) identified each other at a level of certainty.  The process of negotiation is directed at achieving an explicit, mutually understood, and agreed upon goal of a business collaboration and associated terms and conditions.  This may include such things as the detailed specification of the good, service, and/or right, quantity, pricing, after sales servicing, delivery requirements, financing, use of agents and/or third parties, etc.
4. Actualization: The Actualization Phase pertains to all activities or events necessary for the execution of the results of the negotiation for an actual business transaction.  Normally the seller produces or assembles the goods, starts providing the services, prepares and completes the delivery of good, service, and/or right, etc., to the buyer as agreed according to the terms and conditions agreed upon at the termination of the Negotiation Phase.  Likewise, the buyer begins the transfer of acceptable equivalent value, usually in money, to the seller providing the good, service, and/or right.
5. Post-Actualization: The Post-Actualization Phase includes all of the activities or events and associated exchanges of information that occur between the buyer and the seller after the agreed upon good, service, and/or right is deemed to have been delivered.  These can be activities pertaining to warranty coverage, service after sales, post-sales financing such as monthly payments or other financial arrangements, consumer complaint handling and redress or some general post-actualization relationships between buyer and seller.

Offers and Wants are matched in the Planning and Identification Phases. Conversation for Action covers Negotiation, Actualization and some of Post-Actualization.

![Conversation for Action](https://github.com/valnet/exchange/blob/master/images/CfA_state_machine.png)

### Resource flows

One of the purposes of this vocab is to support resource flows connecting many websites. These flows may be oriented around Processes, Exchanges, or combinations of both. We are breaking out the Processes and Exchanges into their own vocab repositories, but here some overview diagrams.

In general, processes and exchanges alternate in a flow. But in some situations, either the processes or the exchanges are more important, and the other is not worth tracking and can be elided. This Exchange vocab is focused on the situations where the processes are not important.

#### Exchange-oriented flow

![exchange-oriented flow](https://github.com/valnet/exchange/blob/master/images/exchange-exchange.png)


