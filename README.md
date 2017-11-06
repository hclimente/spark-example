![spark logo](https://upload.wikimedia.org/wikipedia/commons/e/ea/Spark-logo-192x100px.png)

Apache Spark is an open-source cluster computing framework for real-time processing. Since its launch in 2014, Spark has taken over Hadoop as the leading platform for big data computation. The keys to its success are:

- Speed: Spark runs up to 100 times faster than Hadoop, based on the MapReduce paradigm. This is achieved, partly, thanks to lazy evaluation i.e. evaluations are only performed when it is absolutely necessary.
- Real time computation, as opposed to batch computation, where data is stored for some time before being evaluated.
- Accessibility: APIs available for Java, Scala, Python and R; compatibility with Hadoop; ability to take in multiple data sources (CSV, JSON...).

I found and verified installation instructions for [macOS](https://gist.github.com/ololobus/4c221a0891775eaa86b0).

## Locality-sensitive hashing

We will address the problem of finding pairs of documents that are similar to each other. An exhaustive approach that calculate all pairwise distances would be very inefficient ($O(n^2)$). Instead, we will study an approximate methods, that produces a good enough estimation of similarity in a reasonable time. The process is divided in:

1. Shingling: convert documents into vectors/sets.
2. Minhashing: convert sets to signatures.
3. Local-sensitivity hashing: find candidate pairs.
4. Calculate similarity between candidates.
