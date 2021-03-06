# rsocket-compositemetadata-example
An example of sending composite metadata with [RSocket](http://rsocket.io).

In this example the `hello-client` sends a request to receive a hello message along with some tracing metadata to the `hello-service`. 
The service responds with a hello message and echoes the metadata back.

## Building the Example
Run the following command to build the example:

    ./gradlew clean build

## Running the Example
Follow the steps below to run the example:

1. Run the following command to start the `hello-service`:

        ./gradlew :hello-service:run
        
    If the service has started successfully you will see the following in the terminal:
    
        > Task :hello-service:run
        [main] INFO example.hello.service.HelloService - RSocket server started on port: 7000
        
2. In a new terminal, run the following command to send a hello request, with tracing metadata, using the `hello-client`:

        ./gradlew :hello-client:run --args=Bob
        
    If successful, you will see the following in your terminal:
    
        Sending request for 'Bob' [traceId: '7b34def1040fa567764848d468a6f876', spanId: '9da1e7f0427747b4']
        Response: Hello, Bob! [traceId: '7b34def1040fa567764848d468a6f876', spanId: '9da1e7f0427747b4']

## Bugs and Feedback
For bugs, questions, and discussions please use the [Github Issues](https://github.com/gregwhitaker/rsocket-compositemetadata-example/issues).

## License
MIT License

Copyright (c) 2020 Greg Whitaker

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.