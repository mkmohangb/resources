# Event-Driven Architecture

Event-driven architecture (EDA) is a software architecture paradigm promoting the production, detection, consumption of, and reaction to events. An event-driven system typically consists of event emitters (or agents), event consumers (or sinks), and event channels.An event can be made of two parts, the event header and the event body. The event header might include information such as event name, time stamp for the event, and type of event. The event body provides the details of the state change detected.[1]

Characteristics of Event data:[2]
- Data is Rich
- Data is denormalized
- Data is nested
- Data is schemaless

[3] Events are delivered in near real time, so consumers can respond immediately to events as they occur. Producers are decoupled from consumers — a producer doesn't know which consumers are listening. Consumers are also decoupled from each other, and every consumer sees all of the events. 

EDA can use Pub/Sub model or an event stream model.
- **Pub/Sub** - The messaging infrastructure keeps track of subscriptions. When an event is published, it sends the event to each subscriber. After an event is received, it cannot be replayed, and new subscribers do not see the event.
- **Event streaming** - Events are written to a log. Events are strictly ordered (within a partition) and durable. Clients don't subscribe to the stream, instead a client can read from any part of the stream. The client is responsible for advancing its position in the stream. That means a client can join at any time, and can replay events.

On the consumer side, there are some common variations:
- **Simple event processing** - An event immediately triggers an action in the consumer. For example, you could use Azure Functions with a Service Bus trigger, so that a function executes whenever a message is published to a Service Bus topic.
- **Complex event processing** - A consumer processes a series of events, looking for patterns in the event data, using a technology such as Azure Stream Analytics or Apache Storm. For example, you could aggregate readings from an embedded device over a time window, and generate a notification if the moving average crosses a certain threshold.
- **Event stream processing** - Use a data streaming platform, such as Azure IoT Hub or Apache Kafka, as a pipeline to ingest events and feed them to stream processors. The stream processors act to process or transform the stream. There may be multiple stream processors for different subsystems of the application. This approach is a good fit for IoT workloads.

There are two main types of routers used in event-driven architectures: event buses and event topics. 
 - Amazon EventBridge - to build event buses
 - Amazon Simple Notification Service - to build event topics


### When to use this architecture

- multiple subsystems must process the same events
- Real-time processing with minimum time lag
- Complex event processing such as pattern matching or aggregation over time windows.
- High volume and high velocity of data, such as IoT 


Javascript - EventEmitter class

### References

1. https://en.wikipedia.org/wiki/Event-driven_architecture
2. https://web.archive.org/web/20160405073553/https://keen.io/blog/53958349217/analytics-for-hackers-how-to-think-about-event-data
3. https://docs.microsoft.com/en-us/azure/architecture/guide/architecture-styles/event-driven
4. https://aws.amazon.com/event-driven-architecture/
