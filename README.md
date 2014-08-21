SimplePubsub
==============================================

SimplePubsub is pure java implementation of pubsub mechanism without any other library dependency.

IMPLEMENTATION :

Pubsub.java is a threadsafe singleton implementation of publisher subscriber system. It uses a threadpool to deliver the events to the subscribers. If you want ordering of the events simply configure the threadpool to be single threaded.
Currently NUMBER_OF_THREADS = 1, but you can change it to any number depending on your needs.

USAGE :

PUBLISHER : Publisher should have an instance to Pubsub object and simply calls the publish function on a particular topic. Example : pubsub.publish("topic_food",obj), where obj could be any object used to pass to the subscriber.

SUBSCRIBER : Subscriber should implement the listener Pubsub.listener interface and should subscribe to a particular topic using pubsub.addListener(topic,listener) function. All the events related to that topic will now be received in the onEventReceived() function along with the object passed.  
