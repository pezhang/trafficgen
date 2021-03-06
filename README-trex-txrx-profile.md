# trex-txrx-profile.py
A script to conduct a TRex trial using a JSON file to define the stream properties.

## JSON file Documentation

The JSON file contains an object with a single property, "streams".
The "streams" property is an array of traffic streams that are defined
by the following parameters:

1. flows - required, number of active flows

2. frame_size - required, frame size in bytes

3. flow_mods - required, flow mod object ie. "function:create_flow_mod_object(<flows to use>)"

4. rate - required, frame rate in pps

5. frame_type - optional, type of frames to send, defaults to 'generic', options are: ['generic', 'icmp', 'garp']

6. stream_types - optional, array of stream types, defaults to ['measurement'], options are: ['measurement', 'teaching_warmup', 'teaching_measurement']

7. latency - optional, should latency frames be sent for this stream (latency frames only apply to measurement streams), defaults to True, options are: [True, False]

8. latency_only - optional, should this stream only be latency frames, defaults to False, options are: [True, False]

9. protocol - optional, what protocol is used for this stream, defaults to 'UDP', options are: ['UDP', 'TCP']

10. traffic_direction - optional, what direction is the traffic flowing, defaults to 'bidirectional', options are: ['bidirectional', 'unidirectional', 'revunidirectional']

11. stream_id - optional, an identifier that can be used to identify the stream, if two streams share an identifier they will use the same flow properties (MACs, IPs, etc.), defaults to nothing, is a user defined string
