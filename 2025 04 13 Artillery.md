Ref: https://www.artillery.io/docs/get-started/core-concepts
Artillery runs a test and record performance metrics such response times(delay) , throughput and errors. 

Virtual user 
	When testing HTTP server , each virtual user open TCP connection to the server and maintain it. Users do not share any state , being independent. 
Load phases
	It tells the number of virtual users created over certain period of time. It is made up of duration and arrival rate(number of virtual users created each second).
	Each test is made up of several phases , in which virtual users are created and execute the actions specified in the scenario. 
	Artillery does not wait for one phase to finish before starting the next one. 

Soak testing
	==a type of performance testing that assesses a system's behavior under sustained load over an extended period==. It's used to identify long-term issues like memory leaks or performance degradation that might not surface in shorter tests.
