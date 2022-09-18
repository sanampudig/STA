# STA

## Static timing analysis
checks, constraints, library

## Static timing analysis Part 1 "checks"

<img width="1324" alt="image" src="https://user-images.githubusercontent.com/110079648/190870494-6458f966-d7f7-4687-bfe4-13d382415fca.png">

<img width="1303" alt="image" src="https://user-images.githubusercontent.com/110079648/190870534-fb7c2d8f-05de-4d95-8335-56c098e27050.png">

<img width="1334" alt="image" src="https://user-images.githubusercontent.com/110079648/190870572-128aee34-04d2-4ed9-805a-9fe43a021a78.png">

<img width="1363" alt="image" src="https://user-images.githubusercontent.com/110079648/190870573-d5f596e9-2707-4f06-9770-2d285ea81e8a.png">

<img width="1354" alt="image" src="https://user-images.githubusercontent.com/110079648/190870581-85909633-e22e-416f-b66f-62aa6176a198.png">

<img width="1313" alt="image" src="https://user-images.githubusercontent.com/110079648/190870624-ed535397-b007-4b1f-aaf3-98f31b4cc7f9.png">

Arival time is caluculated at end points.

<img width="1316" alt="image" src="https://user-images.githubusercontent.com/110079648/190870654-181008e3-daaa-4d5d-a919-8660e5dfdb5a.png">

Required time is expected time of signal arival

<img width="1345" alt="image" src="https://user-images.githubusercontent.com/110079648/190870745-dfb3c9e6-aa6e-4586-9899-b2d11facd4cd.png">

<img width="1333" alt="image" src="https://user-images.githubusercontent.com/110079648/190870790-bda2d346-88c1-40a7-8005-f47a2c143cec.png">
 
 <img width="334" alt="image" src="https://user-images.githubusercontent.com/110079648/190870844-8848ddb9-265d-496d-9abf-346083ef1d3a.png">

let arival time is 3.5ns

<img width="916" alt="image" src="https://user-images.githubusercontent.com/110079648/190870871-991035b6-4f44-447a-9763-d1e3345a86fe.png">

<img width="940" alt="image" src="https://user-images.githubusercontent.com/110079648/190870874-b3e66795-7368-454f-a544-72263e6af989.png">

<img width="1236" alt="image" src="https://user-images.githubusercontent.com/110079648/190870923-8bbe198f-3258-4eaa-b335-5368125509f1.png">

<img width="1152" alt="image" src="https://user-images.githubusercontent.com/110079648/190870935-1b72aacd-1de2-4a1c-9494-6ffa137ea93a.png">

Max difference (max slack)= 0.8ns =>setup slack, setup timing, setup analysis (Setup slack = Expected time max - Arrival time)
Min difference (min slack)=-0.1ns =>hold slack, hold timing, hold analysis  (Hold slack = Arrival time - Expected time min)
 
 ## Types of setup/hold analysis
 
Types of setup/hold analysis
1. reg2reg
2. in2reg
3. reg2out
4. in2out
5. clock gating
6. recovery/removal 
7. data-to-data
8. latch (time borrow/time given)

Slew/Transition analysis
1. Data (max/min) CLK
2. Clock (max/min)

Load analysis
1. Fanout (max/min)
2. Capacitance (max/min)

Clock analysis
1. Skew
2. Pulse width
 
 <img width="1373" alt="image" src="https://user-images.githubusercontent.com/110079648/190871255-14fde47d-4f34-4711-acb8-ce99fb482cda.png">
 
 <img width="1370" alt="image" src="https://user-images.githubusercontent.com/110079648/190871264-87571f50-18c2-45e3-a426-16cd01c33f96.png">

<img width="1396" alt="image" src="https://user-images.githubusercontent.com/110079648/190871291-1656fea0-4e93-47de-b03c-999ea1366abc.png">

<img width="1366" alt="image" src="https://user-images.githubusercontent.com/110079648/190871323-5cb86380-4045-42b0-9dde-7684e5fffacc.png">
 
Cat 2,3,4 belongs to IO timing 

<img width="1093" alt="image" src="https://user-images.githubusercontent.com/110079648/190871547-10796f35-6420-4260-9690-805979cd142c.png">

clock coming to capture flop is coming throgh an and gate. we are trying gate the clock. this thechnique is called ** clock gateing **. this is used to reduce the chip power. if that portion of circuit is not using we can turn of clock which imples flop dosent switches.

<img width="1375" alt="image" src="https://user-images.githubusercontent.com/110079648/190871567-1b04c473-a104-43c7-8eb8-2f8a76d99cdf.png">

for flops we have asynchronous pins also present.

<img width="1404" alt="image" src="https://user-images.githubusercontent.com/110079648/190871605-06124220-ba92-4d5c-b472-91b31f90d626.png">

now the combination logic that connected to reset pin is replaced by and gate, this is done to save some power in reset path. if control is high, the gate is open.

<img width="1410" alt="image" src="https://user-images.githubusercontent.com/110079648/190885750-aef6b504-5768-4c36-a4e2-3247a16e7541.png">

a nd control signal should be in sync.to get them into synchronous level, so we take **a** and **ctrl** as final points to analise the ariving time.

<img width="1406" alt="image" src="https://user-images.githubusercontent.com/110079648/190885946-106fa3cf-8cb4-4513-bdb0-09b51516179a.png">

latch is level triggered. if previos flop to latch dosent met timing constraints, it can barrow some time from level triggerd latch. similarly flop connected at output of latch failted to meet timing constraints, latch can give time to lext flop. thats why latches are very important in design.

<img width="1411" alt="image" src="https://user-images.githubusercontent.com/110079648/190886130-42e0eed9-80c5-45c4-9fc5-8f4e053b00cb.png">

## Slew/Transition analysis 
there is some minium and maximum requirement of slew. 
slew and the transition analysis ensures that each and every point on this particular set of it meets that criteria.

Basically if you the slew is too sharp, it will increase short circuit power and if it is too large then it will increase opening time for gate.

slew analysis- 2parts
data and clock
data dosent switch so often as compared to clock.
clock has to switch at equal intervels, that that's why the clock transition requirements becomes a bit stringent compared to the data requirements. 
 
<img width="1390" alt="image" src="https://user-images.githubusercontent.com/110079648/190886365-21d6c35a-42d4-4c76-98f2-65a7a349fe3b.png">

<img width="1412" alt="image" src="https://user-images.githubusercontent.com/110079648/190886377-25f47977-04ce-4b06-a442-7ea227959e06.png">

## Load analysis
fanout analysis- eg. if fanout is 3 whether it is able to charge that load or not.

<img width="1385" alt="image" src="https://user-images.githubusercontent.com/110079648/190886419-2f0b08cf-c733-4f76-b3f2-f5d2db874d43.png">

Capacitance

<img width="1419" alt="image" src="https://user-images.githubusercontent.com/110079648/190886468-c6895bca-6c80-47b5-bad5-de1bf794a2ab.png">

## Clock analysis

<img width="1396" alt="image" src="https://user-images.githubusercontent.com/110079648/190886518-e4a04ac7-d785-4c4e-9c2c-6a868cd03e9c.png">

 <img width="1426" alt="image" src="https://user-images.githubusercontent.com/110079648/190886587-dfb2f241-d7b3-4845-ae7e-aad1f3716463.png">
 
 ###################################################################
 reg2reg
 
 <img width="1335" alt="image" src="https://user-images.githubusercontent.com/110079648/190896130-0da83810-ead4-48a4-a185-d02b3d26d0b1.png">

<img width="803" alt="image" src="https://user-images.githubusercontent.com/110079648/190896165-696e7fd2-1dc4-429f-9ffb-3a119c949e55.png">

<img width="917" alt="image" src="https://user-images.githubusercontent.com/110079648/190896212-59720aab-5361-4c75-805c-53754a064f73.png">

<img width="941" alt="image" src="https://user-images.githubusercontent.com/110079648/190896244-9f845b4c-9387-43a1-8c35-0074dea7814e.png">

<img width="1340" alt="image" src="https://user-images.githubusercontent.com/110079648/190896294-4647b494-4d6a-4104-8fcd-751eaf6ca569.png">

<img width="1318" alt="image" src="https://user-images.githubusercontent.com/110079648/190896384-a8709c9f-118a-4107-bc08-2e03de6d4ddb.png">

<img width="1232" alt="image" src="https://user-images.githubusercontent.com/110079648/190896424-2659c9a5-8530-45ae-84b8-e8ec4953bc36.png">

<img width="1286" alt="image" src="https://user-images.githubusercontent.com/110079648/190896434-071de0de-1c64-4fcf-9aa6-25d67f76a045.png">

<img width="1103" alt="image" src="https://user-images.githubusercontent.com/110079648/190896514-6055ea43-7741-4ff6-8962-a0c0085f73dc.png">

<img width="1146" alt="image" src="https://user-images.githubusercontent.com/110079648/190896527-a1305ada-cd53-414d-b7eb-802071491e97.png">

<img width="1102" alt="image" src="https://user-images.githubusercontent.com/110079648/190896540-dec6a7c6-7ee9-491a-bc5d-d83ebcb7ffc5.png">

now among A1 and A2 which we have to consider?
that depends on type of analysis that we are doing. lower value considered if we are doing hold analysis, higher value while while doing setup analysis.
not lets go with setup time.

<img width="1123" alt="image" src="https://user-images.githubusercontent.com/110079648/190896654-bfcab204-4209-40e7-a5f5-348e8f508c63.png">

<img width="1116" alt="image" src="https://user-images.githubusercontent.com/110079648/190896675-a1d3c0c7-99ca-44df-b683-e7dc6785f563.png">

<img width="1300" alt="image" src="https://user-images.githubusercontent.com/110079648/190896695-d2474caf-5a99-468d-a326-5753143eb5a6.png">

<img width="1231" alt="image" src="https://user-images.githubusercontent.com/110079648/190896709-fa2c1f80-752c-47c3-94a8-5c924dbe87b2.png">



























