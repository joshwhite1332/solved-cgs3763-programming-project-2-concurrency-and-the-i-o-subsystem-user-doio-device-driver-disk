Download Link: https://assignmentchef.com/product/solved-cgs3763-programming-project-2-concurrency-and-the-i-o-subsystem-user-doio-device-driver-disk
<br>






1.- In this assignment you will  implement a simulation of the interaction of user programs with the OS to execute an I/O operation.

<strong>User programs:</strong>

User programs will communicate with DOIO (OS) to request an I/O operation. (this will simulate a system call)

User programs will give to DOIO two parameters: User id and an address (addr is a random number in the range 1 and 200.) (addr is an integer that represents a track number in the hard drive).

User programs will pass the parameters to DOIO through two buffers of size one each (bufid and bufaddr).

Once the parameters are stored in the buffers, user programs executes a P(request served) operation to wait for the completion of the I/O operation.

There will be one user running concurrently and it will execute 10 I/O operations.

<strong>DOIO:</strong>

DOIO will collect and id and address(addr) from bufid and bufaddr to assemble the IORB.

DOIO will store the IORB (id and addr) into two buffers that represent the IORQ (iorqid and iorqaddr).

<strong>Device driver: </strong>

Device driver will collect an IORB (pair id and addr) from iorqid and iorqaddr and then  initiates the physical I/O operation on the hard drive and wait for the I/O operation to be completed: P(operation complete).

The device driver initiate the physical I/O operation by storing addr into a buffer of length one. The buffer name is “pio” (physical I/O).

When the I/O operation completes a signal is received, the driver will identify the user that issued the I/O request using the id, and will signal the semaphore “request served” associated to the user.




<strong>Disk:</strong>

The disk process simulates the access to a track in the hard drive.

The Disk process gets the addr from pio   and stores it in a variable called “seek” and iterates in a dummy loop from 1 to “seek”.

Once out of the loop, disk will execute a V on the semaphore “operation complete”

<ol>

 <li>Define all semaphores that you need according to the number of buffers used.</li>

</ol>




The user will make 10 system calls to initiate I/O operations

DOIO will create 10 IORB

<strong> </strong>

<strong>Project Direction </strong>

You will write the program C– based on the <strong>BACI</strong> interpreter that you used in programming project 1.







<strong>Test your solution</strong>




You must run and test your solution and   comment on the results emitted.

<strong> </strong>


