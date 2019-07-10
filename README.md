# RequestLimiter
A vegas limiter implementation in Go


Delay based algorithm where the bottleneck queue is estimated as

L * (1 - minRTT/sampleRtt)
At the end of each sampling window the limit is increased by 1 if the queue is less than alpha (typically a value between 2-3) or decreased by 1 if the queue is greater than beta (typically a value between 4-6 requests)

Inspired from - https://github.com/Netflix/concurrency-limits
