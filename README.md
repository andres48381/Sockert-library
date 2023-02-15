# Socket-library
Socket library useful for TCP &amp; UDP communications in C++ projects.

# How to build and install it
Just include the .h and .cpp files in your project. The repository includes an example with cmake, and a simple code to check how it works in a server-client application.

# Example

The next code is an *example* for comutication between a server and a client:

Server.cpp

<pre><code class="cpp">
//Initial setup
Socket servidor;
Socket conexion;

...

servidor.InitServer("10.0.2.15", 12000); //ip and port example
conexion = servidor.Accept(); //block until get a new client connection

...

//Read buffer
unsigned char inputBuffer[BUFFER_SIZE];
conexion.Receive(inputBuffer, BUFFER_SIZE;

//int var = (int)outputBuffer[0];
//...
//int varN = (int)outputBuffer[N];

//Send buffer
stringstream outputBuffer;
string message = outputBuffer.str();
conexion.Send((char *)message.c_str(), message.length());
</code></pre>

Client.cpp

<pre><code class="cpp">
//Initial setup
Socket cliente;

...

cliente.Connect("10.0.2.15", 12000); //server ip and port

//Send buffer
char outputBuffer[BUFFER_SIZE];

//outputBuffer[0] = xxx
//...
//outputBuffer[n] = xxx

cliente.Send(outputBuffer, BUFFER_SIZE);

//Read buffer
char inputBuffer[BUFFER_SIZE];
cliente.Receive(inputBuffer, BUFFER_SIZE);

...
</code></pre>
