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
 
1. reg2reg
2. in2reg
3. reg2out
4. in2out
 
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

now the combination logic between the





























