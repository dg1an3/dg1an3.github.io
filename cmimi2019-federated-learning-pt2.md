## Federated Learning part 2

What other architectural problems could be addressed by a federated learning mechanism?  Proof of interop provides a rough blueprint.

If a legacy system is being designed to interact with a new system, an anti-corruption layer (ref DDD, [https://github.com/python-leap/book/blob/master/chapter_07_events_and_message_bus.asciidoc], ref E2EImageReview).  If we view the design of the ACL from the point of view of a federeated learning system, we get a design where the participants ability to contribute data is tested by the proof of interop.

Proof of interop also supports property-based testing an algorithm verification.  ALGT (expert system) or SRODecoderRing (dense layer) both would allow proof of interop based on evidence of adherence to a set of constraints.

Set of constraints can't be easily generalized, so test data synthesis from a generative model would allow pre-testing.

Pre-testing can also be viewed as a form of pre-caching (see next part).
