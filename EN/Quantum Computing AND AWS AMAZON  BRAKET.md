# Quantum Computing AND AWS AMAZON  BRAKET

_KY1,Yankuan Pan2,Bertran Shao3,Zoey Deng4
1.AWS HERO;2.Software Architect;
3.Head of Developer Relations of  QUDOOR.;4.Developer Relations of  QUDOOR._

Amazon Braket is a fully-managed AWS service that helps researchers, scientists, and developers get started with quantum computing.Amazon Braket can help to solve the problems of inconvenient access to quantum hardware and the limited resources of quantum software [ 《什么是 Amazon Braket？》].QUDOOR(use the company instead of it) is a quantum company in China ,which focuses on the research of the whole quantum software stack and hardware stack,such as the  trapped ion quantum computing, open-source software framework for quantum computing and so on. In China ,it is the first one who has the capacity of studying the quantum computing and quantum communication.

## 1.The Architecture of a Universal Quantum Computer

Quantum computing is a new computing mode based on the mode of traditional Turing machine .And it is also an new method,which follows the laws of quantum mechanics ,to control quantum information units .A real quantum computer needs to meet five prerequisites[ The Physics of Quantum Information ]:

- a.There is a physical system containing a large number of qubits, in which the number of qubits will increase with the enlarging scale of the problem;

- b.A system for preparing initial state qubits;

- c.A set of universal quantum gates , which can be used for universal quantum entanglement operations and unitary transformation;

- d.There is an effective solution to the problem of quantum decoherence;

- e.The final result can be obtained by measuring qubits.

Therefore, a general quantum computer must equip with the five conditions no matter the hardware architecture or the software architecture.The designing of the general quantum computers will need some key technology such as QPUs,quantum coding system, quantum algorithm,quantum assembly language and so on.

The company is developing a full stack of quantum computing products , including the full stack of quantum computing hardware and the full stack of quantum computing software. In the NISQ era,the full stack of quantum computing software in the company is developed based on classical computing,but it has APIs for the future ion trap quantum computer.

### 1.1Quantum Computing Hardware And  Software

Since the research of quantum computers is still in an early stage, each technology route of quantum computing has different advantages and resources with others . It is too difficult to choose a dominant technology route . For the industrialization of quantum computing ,it’s more important to develop a ecology of quantum computing and dominate the market where the developers are working for .Their working will promote the commercial application of the quantum computing.

Regarding quantum computing hardware, the main quantum research institutions and companies in the world ,adapt technical routes to realize quantum computing mainly include five directions: superconductivity, semiconductor quantum dots, ion traps, optics and quantum topology. Among them, the superconducting and ion trap technology routes have received high attention. For example, Google and IBM adapt superconducting quantum routes, Microsoft has invested in optical quantum company, the US listed company IonQ adapts ion trap technology routes, and the company in China is developing a distributed ion trap quantum computer (AbaQ-1).

Quantum computer software includes quantum operating system, quantum programming framework, quantum assembly language and quantum software.for application. Our quantum suite of developer software provide people with quantum programs and quantum algorithms for development and research .The full stack quantum computing software of  the company is an innovation by a Chinese local

company. The quantum software products include QuBranch (which is a quantum programming integrated development environment) , QuTrunk (which is a quantum programming framework) ,QuFlower (which is a quantum algorithm library) , QuSprout (which is a quantum computing simulation software) , and QuRoot (which is a quantum system framework).

##2.Quantum Computing AND AWS AMAZON BRAKET

Amazon Braket is a fully managed quantum computing service designed to help speed up scientific research and software development for quantum computing.With Amazon Braket ,developers have more choice to use different types of quantum computer,development environment,classical simulators and quantum algorithms.

When we use Amazon Braket, Jupyter notebooks and Amazon Braket SDK pre-installed in Amazon Braket can greatly reduce the difficulty for users. On the one hand, customers can use Jupyter notebooks conveniently to define, submit and monitor their tasks.On the other hand, customers can directly build quantum circuits or define annealing problems and parameters of annealing equipment in the Amazon Braket SDK[ 《Amazon Braket Developer Guide》;page5.].

### 2.1Amazon Braket task flow

When using Amazon Braket, customers can change quantum computing devices as needed without being limited to a certain hardware. The following is a brief introduction to the use process of Amazon Braket[ 《Amazon Braket Developer Guide》;page36.].

![image](https://user-images.githubusercontent.com/112528710/204198410-1128de92-ae7e-42ee-a97a-f0f119378a88.png)

_Picture1：This  diagram describes the Amazon Braket task flow._

To get started with Amazon Braket, we need to create an Amazon Braket notebook instance first . This step is mainly for basic operations such as creating a notebook and setting a name.

Second, run the first quantum circuit using the Amazon Braket Python SDK. Open the instance created in the first step and select the `conda_braket` option to create a new notebook. Once the preceding operations are completed, Braket can be used to create a quantum circuit.

Once the quantum circuit is created, we can then choose the appropriate quantum simulator as needed.Finally, running the quantum circuit will get the result of the simulation. The result of the task can be downloaded from Amazon Braket. The specific measurement information and parameter information are shown in the following figure:

![image](https://user-images.githubusercontent.com/112528710/204198446-3f72d4b2-6318-44e9-a12c-cc17f4886fcd.png)

_Picture2：This  picture shows the part of  measurement information when a task is completed._

![image](https://user-images.githubusercontent.com/112528710/204198447-37033d51-6276-42cf-b7c6-1e75236a82c9.png)

_Picture3：The specific measurement information and parameter information are shown in this picture.__

### 2.2Quantum Computing and Amazon Braket
As for quantum computing hardware, Amazon Braket provides access to IonQ ion trap technology, Oxford Quantum Circuits and Rigetti's superconducting quantum processors, D-Wave's quantum annealing technology, and Xanadu's optical quantum technology.

In general, if you want to try out a real quantum computer in Amazon Braket, you can use a quantum simulator for prototyping. Amazon Braket provides four kinds of simulators, namely local simulator, SV1, TN1, DM1. The local simulator can be used when our memory is large enough or for prototyping; SV1 for full state vector simulations up to 34 qubits, DM1 for simulating noise on circuits up to 16 qubits, or TN1 for simulating quantum circuits with higher local entanglement up to 50 qubits[ What kinds of quantum simulators can I use?]. 

The  AbaQ1 ion trap quantum computing adopts a distributed design to capture 20 fully linked ions per node. The platform can connect up to 8 computing nodes and will reach a link of more than 100 qubits at most.

As for quantum development software,Amazon Braket provides support for PennyLane, an open-source software framework built around the concept of quantum differentiable programming. This framework allows us to train quantum circuits in the same way that you would train a neural network to find solutions for computational problems in quantum chemistry, quantum machine learning, and optimization.The PennyLane library provides interfaces to familiar machine learning tools, including PyTorch and TensorFlow, to make training quantum circuits fast, easy and intuitive.
The PennyLane library is pre-installed in Amazon Braket notebooks. To access Amazon Braket devices from PennyLane, you need to execute the `import pennylane as qml` command to import the PennyLane library.

Setting up and running hybrid quantum algorithms with Amazon Braket is primarily using the Amazon Braket PennyLane plugin or the Amazon Braket Python SDK and instance notebook library. When there is no PennyLane plugin, we can use the SDK-based Amazon Braket to run some hybrid quantum algorithms[ 《Amazon Braket Developer Guide》；page111].The open source quantum programming framework QuTrunk  can running various quantum algorithms, such as Grover algorithm, Shor algorithm, VQE algorithm, etc., and will provide API of various mainstream machine learning frameworks to meet the  development needs of quantum artificial intelligence .

Now,the company has joined the Baidu Technology Partner Program and aims to develop the technology of quantum and artificial intelligence . QuTrunk is the one which is a quantum framework providing API to paddlepaddle.PaddlePaddle is a framework with high attention in the people of Chinese developers.According to The report of Open Source in China in 2021,the score of paddlepaddle in github was the highest in China，and the issue and comment date reached 18979,ranking the first[ 《2021中国年度开源报告》].

In a word, Amazon Braket, as a fully managed quantum computing service platform, has access to a variety of quantum computing hardware devices and software services. However, to build a larger quantum computing market, especially in China,the company will be a better choice.At present, the programming framework of the company has integrated some functions of Amazon Braket, and we can use quantum simulation devices on the Braket from QuTrunk to design some quantum circuits.

### 2.3echnical Advantages of  the  Full Stack  of  Software

The software of the company have strong scalability, which can meet the diversified needs of quantum programming and research. Because there are sufficient and comprehensive interfaces in each layer of the quantum software, which can be used with a variety of AI frameworks to achieve some function such as quantum machine learning.

The software is independent of each other and can  provide a variety  of choices for quantum programming developers. The entire quantum  software system of  the company adopts a layered architecture, which can be decoupled into independent products, and can also be combined into new product systems, such as QuBranch+QuTrunk+QuBOX, QuBranch+QuTrunk+QuRoot.

Potential standardization of the software of the company. At present, quantum software and quantum cloud are still in the early stage of industrialization, and the quantum computer market has not been dominated by any mainstream software technology, which indirectly led to the lack of a unified standard in quantum software . As one of the few companies in quantum computing in China, The software technology of the company is expected to become one of the mainstream quantum computing software in the future.

Our Software is growing up in the ecological soil of quantum computing technology in China. Its industrialization is supported by national policies, and has great market potential in China. China's cloud service market has always been the core market for cloud manufacturers. As a new track in the world, quantum technology will also create a new development opportunity for the software industry.

## 3.Quantum Computing Programming Framework -QuTrunk
QuTrunk is a free, open source, cross platform quantum computing programming framework independently developed by the company, including quantum programming API, quantum command translation, quantum computing backend interface, etc. QuTrunk uses Python as the host language, and with the syntax features of Python to implement DSL (domain specific language) for quantum programs. All IDEs programmed in Python can be installed. 

QuTrunk provides various APIs required for quantum programming based on quantum logic gates , quantum circuits and so on. These APIs are implemented by corresponding modules. For example, QCircuit implements quantum circuits, Qubit implements qubits, Qureg implements quantum registers, Command implements instructions for each quantum gate operation, Backend implements backend modules for running quantum circuits, and gate modules implement various basic quantum gate operations.

In addition, QuTrunk can also be used as the basis for other quantum computing applications, such as quantum algorithms, quantum visual programming, quantum machine learning, etc.There are some features of QuTrunk:
- a.Quantum program development is based on quantum logic gates, quantum operators and quantum circuits.

- b.QuSL which is a quantum assembly instruction standard is fully compatible with Python code.

- c.The device is independent, and the same quantum circuit can run on different quantum backend just by replacing the different type of backend . It provides a variety of quantum computing experiences. The local quantum computing provides Python computing backend. The remote backend provides OMP multi-threading, MPI multi node parallel, GPU acceleration and other computing modes. At the same time, the interface is reserved to the ion trap quantum computer .

- d.QuTrunk is Compatible with a variety of quantum assembly instruction formats， such as OpenQASM2.0 and QuSL.

- e.QuTrunk  Supports  visual  quantum  programming  (you   can  exprience	visual programing with QuTrunk and QuBranch).

![image](https://user-images.githubusercontent.com/112528710/204198477-6ac3f5f1-0b60-42f6-a486-bfa0b1e5cb31.png)

_Picture4:This diagram describes the architecture diagram of QuTrunk._

### 3.1Open Quantum Assembly Language——QuSL

Amazon Braket now supports OpenQASM 3.0 for gate-based quantum devices and simulators.However,QuSL is a superset of OpenQASM 2.0, and has richer programming language.

With python's syntax characteristics, QuTrunk implement DSL (domain specific language) for quantum programs. We call the specific language for quantum programming QuSL (a quantum assembly language similar to OpenQASM). The main feature of  QuSL  is  that  a  quantum  gate  operation  is  on  the  left  of  a  linker `*` and the operating quantum bits is one the right of `*`, such as the : `gate *qubits`. This standard makes full use of the overloading feature of Python syntax on the `*` operator. The form is closer to the calculation formula of quantum physics. In addition, `*` can represent multiplication operation in computer programming language, and QuSL can represent that quantum gate operation on the left is actually matrix multiplication operation on qubits.

The quantum assembly written using the QuSL can be directly parsed and run in QuTrunk, without any lexical or grammatical parsing. Because of the feature, QuTrunk can seamlessly connect with QuBranch and directly generate quantum circuits  based  on  the  visual   quantum   programming   function.In   an   other   word QuTrunk can directly run the quantum circuits generated by QuBranch (just do some simple initialization work) without syntax compilation or translation processing.

```python
H * q[0];  #hadamard gate operation on q[0]
CNOT * (q[0], q[1]);  # q[0] is the control bit, q[1] is the target bit 
All(Measure) * q  # a measurement operation on all bits represented by q
//Toffoli: a, b are used as control bits; c is the target bit; if a, b are both 1, negate b, otherwise do nothing
Toffoli * (a, b, c)

//Measure: measure a, the result is either 0 or 1, the measurement result is affected by the probability amplitude
Measure * a

//P: Phase shift gate, move the phase of qubit ｜0 〉 and ｜1 〉 according to a given angle
P(theta) * a
```


### 3.2Quantum Simulator——QuSprout

Amazon Braket currently provides managed state vector simulator SV1, managed density matrix simulator DM1, managed tensor network simulator TN1 and local simulator.The company also has its own quantum computing simulator, ,called QuSprout. QuSprout is a quantum computing simulator based on classical computing resources. It supports multi-threaded, multi node, GPU acceleration and can be installed in QuBox. QuBox is a PKS system hardware installed with QuSprout, which provides users with quantum simulators in the form of products. For example, QuTrunk uses  the  local  backend`qc=QCircuit  (backend=BackendLocal())`.  The   complete backend code is as follows:

```python
from qutrunk.circuit import QCircuit
from qutrunk.circuit.gates import H, CNOT, Measure # new QCircuit object
qc = QCircuit(backend=BackendLocal()) # or use as default
# qc = QCircuit()

qr = qc.allocate(2) H * qr[0]
CNOT * (qr[0], qr[1])
Measure * qr[0] Measure * qr[1]
res = qc.run(shots=100)
```

### 3.3Applications In The Financial Field—— QuFinace

QuFinace is a quantum software product developed by the company to provide financial services. Based on the quantum algorithm VQE, Monte Carlo estimation algorithm and Pennylane algorithm, QuFinace can provide support for financial practitioners and investors in the complex market environment in terms of option pricing, time series exchange rate estimation, portfolio optimization, and VAR value calculation in the financial field.The company has joined Baidu PaddlePaddle's technical partner program with time series prediction function of QuFinace.

![image](https://user-images.githubusercontent.com/112528710/204198492-952b8f99-4bad-41e5-b6bb-21660d52d579.png)

_Picture5:This picture shows the  the  function  of  time  series  prediction  in  QuFinace ,which is a quantum financial product._

aQuantum has recently launched the QuantumPath on AWS, offering graphical tools to develop and test algorithms services to integrate solutions with classical software, providing access to quantum computers and third-party solutions and development life cycle management that helps apply software engineering best practices. And AWS is enabling the development and deployment of quantum solutions on AWS. Therefore, if  there is a corporation between the company and Amazon Web Services,the technical advantages of the company will enrich developer’s experience of programming on Amazon Braket.

Github:https://github.com/qudoor

Writer

![丘](https://user-images.githubusercontent.com/112528710/205234564-6faffc77-c835-44bf-a15f-08a5d340ee7b.jpg)


Keith Yan（丘秉宜）The First Community Hero of China


![潘工照片](https://user-images.githubusercontent.com/112528710/205234582-f243daab-8fa8-4bf2-9729-943215c46b7d.jpg)

潘彦宽 项目架构师，Software Architect of QuTrunk

![image](https://user-images.githubusercontent.com/112528710/205234747-af8cf52f-1ad3-4dd4-8c15-304238e2ecd7.png)


![image](https://user-images.githubusercontent.com/112528710/205234911-53c22078-8302-40fc-938b-dba500ab6e19.png)

Bertran Shao（邵伟），Quantum Developer Relations Leader, the initiator of the first open source quantum computing community in China

Zoey Deng(邓子宜)，Developer Relations of  QUDOOR

