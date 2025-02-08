# 2025 Spring

# Step 1

You will be creating a project from scratch with the latest versions of SvelteKit, Go, gRPC, and protobufs. The objective is for you to become familiar with how various tools work and with processing documentation efficiently.

For gRPC and protobufs, Google's documentation is the best place to start understanding, but we recommend you implement with [ConnectRPC](https://connectrpc.com/) and [Buf](https://buf.build/product/cli).

## Introduction

- Svelte is an extension of the HTML language that compiles to client in HTML, CSS, and JS that runs in the browser
- SvelteKit is a framework that allows you to run a Node (JS) server that browsers can send requests to and receive responses from which are either the client (compiled from Svelte) or data used for the client
- gRPC is the wire protocol using HTTP/2 that allows you to send and receive data between servers
- protobufs are the way to defined typed structures that gRPC should send and receive
- Go is a statically-typed garbage-collected language that compiles to a binary with extremely simple concurrency

### Review

The [OSI model](https://en.wikipedia.org/wiki/OSI_model) helps with understanding. We will stick to TCP > IP > Ethernet as the lowest layer.

If you've heard of REST, that communicates over HTTP/1.1 > TCP. You might have seen the green lock in your browser, representing HTTPS, which is HTTP/1.1 > TLS > TCP. Note how TLS comes before TCP because if TCP headers are encrypted then routers have no idea where to send the TCP packet to.

gRPC communicates over HTTP/2 > TCP. If wanting encryption, the same order HTTP/2 > TLS > TCP applies. This wire protocol takes advantage of features that are not supported by browsers' HTTP/2 implementations, so it cannot directly communicate with a client in the browser.

**You should think about and research why all of these tools are used, how they work together, and what the benefits are of using them are.** Knowing why is crucial: if you decided to quit comp but stuck through long enough to understand why, you will already have a huge advantage compared to others if you are interested in software engineering in the future. :)

# Step 2

Have the client in the browser have a button such that when you click it, a global value in the server increments by 1 and the client receives the new value. The nuance is that if there are multiple clients, the received value might be more than 1 greater than the previous value seen in the client. Using atomics on the server might be useful.

There are no other requirements in style or functionality. Keep it simple and focus on understanding how the tools work together.
