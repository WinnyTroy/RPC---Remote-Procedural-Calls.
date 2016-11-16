## RPC---Remote-Procedural-Calls.  

# making rpc calls python emaple using rpc-gen  


  - Sockets are a fundamental part of client-server networking. They provide a relatively easy mechanism for a program to establish a connection to another program, either on a remote or local machine and send messages back and forth (we can even use read and write system calls). This interface, however, forces us to design our distributed applications using a read/write (input/output) interface which is not how we generally design non-distributed applications. In designing centralized applications, the procedure call is usually the standard interface model. If we want to make distributed computing look like centralized computing, input/output-based communications is not the way to accomplish this.  
  
  - IN 1884, a mechanism was devised to allow programs to call procedures on other machines. A process on machine A can call a procedure on machine B. When it does so, the process on A is suspended and execution continues on B. When B returns, the return value is passed to A and A continues execution. This mechanism is called the Remote Procedure Call (RPC). 
  
  -  To the programmer, it appears as if a normal procedure call is taking place. But obviously, a remote procedure call is different from a local one in the underlying implementation.
  
# Steps in a remote procedure call

  - Examining how local procedures are implemented first - Every processor provides us with some form of call instruction, which pushes the address of the next instruction on the stack and transfers control to the address specified by the call. When the called procedure is done, it issues a return instruction, which pops the address from the top of the stack and transfers control there.  
  - remote procedure calls a language-level construct as opposed to sockets, which are an operating system level construct. We will have to simulate remote procedure calls with the tools that we do have, namely local procedure calls and sockets for network communication.
  - The entire trick in making remote procedure calls work is in the creation of stub functions that make it appear to the user that the call is really local. On the client, a stub function looks like the function that the user intends to call but really contains code for sending and receiving messages over a network.  
  
  
   Figure 1. Steps in executing a remote procedure call
Figure 1. Steps in executing a remote procedure call

    ![alt tag](https://www.cs.rutgers.edu/~pxk/417/notes/images/rpc-flow.png)

