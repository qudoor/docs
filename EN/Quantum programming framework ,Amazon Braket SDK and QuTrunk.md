# Quantum programming framework——Amazon Braket SDK and QuTrunk

_KY1,Bertran Shao2,Don Tang3
1.AWS HERO;2.Head of Developer Relations of QUDOOR;3.Developer Relations of QUDOOR._

In the field of classical computing programming, software framework is an abstract form with general software functions. Developers using these software frameworks can provide customized services for specific applications after rewriting the framework code according to specific functional requirements. In the era of big data, classical computing is slightly weak to solve massive data. Quantum computing stands out in terms of computational acceleration due to its entanglement and superposition feature. The research and design of quantum programming software in the industry generally inherits the classical programming ideas to show the advantages of quantum computing.

At present, many scientific and technological enterprises at home and abroad have launched quantum programming framework software, such as ProjectQ,(an open source software framework for quantum computing), Qiskit,( an open source quantum programming development kit from IBM ), Cirq ( an open source quantum algorithm framework from Google), AmazonBraket SDK, and QuTrunk, ( a quantum programming framework from QUDOOR). The next mainly introduces the Amazon Braket SDK quantum software development kit and QUDOOR's QuTrunk quantum programming framework .

## 1.What is a quantum programming framework
Quantum programming framework focuses more on the rapid development of quantum subprograms under the current technical conditions. Quantum programming frameworks usually use traditional programming languages as host languages, add variables, functions, objects and other elements that can describe the quantum computing system. And then developers can implement quantum algorithms and develop quantum programs in the quantum programing frameworks. Quantum programming frameworks often contain software libraries of commonly used quantum algorithms, which will be more efficient for the development of quantum programs. Quantum and classical hybrid programming can be easily realized using the  host language of quantum programming framework.

Common quantum programming frameworks include QPanda, QDK, Cirq, Qiskit, ProjectQ, Forest, AmazonBraketSDK and QuTrunk. Because the quantum programming framework introduces the concepts of quantum computing in the classical host program language, and in a quantum computer QPU is just a device similar to CPU.This will be a familiar development paradigm for developers. After the program developed by the quantum programming framework is compiled, the classical program codes are  converted into machine instructions and subsequently executed on the classical processor, while the quantum circuit codes describing the quantum algorithm is converted into the quantum intermediate representation and subsequently sent to the QPU for processing.

| company |	Quantum Programming Framework| Support classic language types |
| ----- |----- |----- | 
| Microsoft	| QDK| C# |
| IBM | Qiskit | Python |
| Google | Cirq | Python |
| Xanadu | Strawberry Fields | Python |
| Rigetti | Forest | Python |
| Amazon | Braket SDK | Python |
| Huawei |	HiQ	 |Python/C++ |
| Originqc | QPanda | Python/C++ |
| QUDOOR | QuTrunk | Python |

Quantum programming framework software is used to write quantum algorithms and programs running in quantum computers. After encapsulation, it can also provide commonly used quantum computing components and quantum algorithm libraries for rapid development of quantum programs.

## 2.Amazon Braket SDK
### 2.1 Amazon Braket
Amazon Braket is a full-service Amazon Web Services (AWS) solution launched by Amazon, which can help researchers and developers explore potential applications and evaluate current quantum computing technologies. It allows users to design their own quantum algorithms, or choose quantum algorithms from algorithm libraries. After defining the algorithm, Amazon Braket will provide a fully hosted simulator to help troubleshoot[ 《什么是Amazon Braket?》].
(1) Build, install Jupyter of Amazon Braket SDK, perform quantum programming  (2) Test, run quantum circuits in the simulator. Braket supports four kinds of simulators, among which the local simulator can simulate the quantum environment locally
(3) Run, run quantum algorithms in the real quantum environment. At present, AWS quantum devices include D-Wave, IonQ, OQC. Because the influence of quantum
computer noise cannot be completely removed at present, AWS provides a hybrid quantum environment, works with CPU through QPU, and supports hybrid algorithm through PennyLane .

![image](https://user-images.githubusercontent.com/112528710/204198658-43df05fc-3dcd-46a6-b8aa-684af71b645d.png)

How Amazon Braket Works[ 《Amazon Braket Developer Guide》]

![image](https://user-images.githubusercontent.com/112528710/204198672-87d0c055-8ea8-4dda-a73d-575fe9c59551.png)

![image](https://user-images.githubusercontent.com/112528710/204198686-1c9cbd0a-abed-4b6c-ad7a-e6dd9259a408.png)

(1)Learn
AmazonBraket, which provides step-by-step instructions, tutorials, and resource libraries help you quickly start experimenting with quantum computing.

(2)Design
To design quantum algorithms, you can use a fully hosted Jupyter notebook directly in the Amazon Braket . The sample gives you access to pre-installed developer tools, sample algorithms, and documentation to get started quickly.

(3)Testing 
You can use simulators running on traditional hardware to simplify code diagnosis and design optimization, thus speeding up algorithm development. Amazon Braket runs the simulators in a fully hosted service mode, and then automatically sets the required computing instance,and publishes the results to Amazon S3, and closes the resources when it is finished.

(4)Run 
You can perform quantum algorithms on the quantum hardware you have done a
choice, and pay according to the actual usage. If you choose to run a hybrid quantum algorithm, Amazon Braket can automatically set the required classical computing resources and manage the workflow between classical and quantum tasks.

(5)Analysis
After the analysis is completed, the system will automatically notify you and store the results in Amazon S3. Amazon Braket will publish event logs and performance indicators such as completion status and running time to Amazon CloudWatch.

Amazon Braket functions
| Project | Instructions |
| ----- |----- |
| QPU | 1.The QPU resource is limited.So the task will not return the calculation result immediately. It will provide an API to obtain the task execution status; 2.QPU supports quantum annealing: (D-Wave) and gate model (ionq, Rigetti, OQC) | 
| Simulator | 1. Local Simulator (free), integrated in the Brake SDK; 2. On demand Simulator (charging), a more efficient simulation service, supports more qubits, embedded simulators, etc; 3. Nosie simulation supports two intervention modes: intervention during initialization of quantum circuit and intervention during circuit operation. | 
| notebook	 | 1.You can directly create a notebook instance integrated with the Braket SDK; 2. You can also download the Braket SDK to deploy jupyter locally. | 
| Braket Moment features | Braket Moment features is to dismantling a circuit with the gate as the unit, obtain the current status of the qubits of the circuit after a gate operation , and then analyze the running process of the algorithm. | 
| Task batching | 1.Local simulator does not support task batching; 2. On-demand simulator&QPU support it, allowing circuit parallelism (higher parallel price) | 
| Task Result | 	
| Hybrid jobs | 1.The QPUs supported by different Region are different. QPUs not supported by the current Region;2.You can choses the container with PennyLane (Tensorflow, PyTorch) ;3.Support BYOC, and customize the container through Dockerfile;4. Create a job instance (EC2), upload the algorithm code, and after the job is completed, ec2 resources are automatically released | 
| Notification | Combined with SNS, the informations of the task execution status and QPU change status will be informed. | 

Braket Task Flow[ 《Amazon Braket Developer Guide》]

![image](https://user-images.githubusercontent.com/112528710/204198727-19f3b1dd-b8bd-4223-becc-f6da49bcf655.png)

(1)To make it easy for customers to define, submit, and monitor their tasks, Amazon Braket provides an environment with Jupyter notebooks.

(2) Amazon Braket Development Kit. You can directly build quantum circuits in SDK, or define annealing problems and parameters for annealing equipment. These areas include: Amazon Braket SDK also provides a plug-in D-Wave's Ocean tool, so that You can use the D-Wave device for native programming. After defining the task, you can select the device on Amazon Braket to perform and submit it to the Amazon Braket API.

(3)Depending on the device you choose, the task will be sent to the QPU or emulator for execution until the device becomes available.

(4)Amazon Braket allows you to access five different types of QPUs(D-Wave, IonQ, OQC, Xanadu, Rigetti) and three  simulators (SV1, DM1, TN1). After your task is processed, Amazon Braket returns the results to the Amazon S3 , and the data is stored in your AWS account.

(5) At the same time, the SDK will poll the results in the background and load them into the Jupyter notebook when the task is completed. You can also view and manage a page in your task task page on the Amazon Braket console or use the console or the operations Amazon Braket API of GetQuantumTask. Amazon Braket integrates with Amazon Identity and Access ManagAmazon CloudWatch, Amazon CloudTrail and Amazon Event Bridge for access management, monitoring and recording, and event based processing.

### 2.2  Braket Python SDK
Amazon Braket Python SDK is a quantum software development package, which provides a framework that can be used to interact with quantum computing hardware devices through Amazon Braket. Amazon Braket can be used to run its quantum algorithms on quantum processors based on different technologies, including systems from D-Wave, IonQ and Rigetti. Simulation and quantum hardware operations are managed through unified development experience, and customers only need to pay for the computing resources. Based on the resources of the Amazon Braket, part of the Amazon Braket SDK provides a free local simulator, which is suitable for running small and medium-sized simulations (usually up to 25 qubit). Customers can run on a quantum computer simulator using Amazon EC2 computing resources, test the algorithms and troubleshoot . When ready, customers can run their algorithms on quantum computers based on their choice without having to hire multiple providers or adopt a single technology.

For larger and more complex algorithms that require high-performance computing resources (up to 34 qubits), you can submit simulation tasks to the Braket. The cost of using the Braket simulator depends on the duration of each simulation task. The billing method is billed at an hourly rate, in one-second increments, and is ultimately settled by the time it takes to execute the simulation.

### 2.3 local Simulator

You can program quantum circuits by installing Jupyter locally.Install AWS Brake SDk,`pip install amazon-braket-sdk`.

(1) Use Jupyter to run Bell algorithm locally

![image](https://user-images.githubusercontent.com/112528710/204198754-cba411e5-d8a9-4f5d-8ec0-07cf3a793d80.png)

(2) Visualization results can be displayed using the visualization library

![image](https://user-images.githubusercontent.com/112528710/204198770-793b17bf-4fd0-49d5-af2e-e1acd22c62ba.png)

AWS can support local simulors, as well as efficient and more qubit capable simulator services.

![image](https://user-images.githubusercontent.com/112528710/204198785-d2a8e1d5-d9e1-4254-960a-f022a0742bce.png)

### 2.4 Features of Amazon Braket SDK
（1）Moment Features. There is a pseudo-time concept in Braket, defined as moment, which means that a qubit performs a gate operation at the current moment.. The moment attribute is to disassemble a circuit in units of gates, so as to obtain the temporary state of the circuit at a moment, and analyze the running process of the algorithm.. The code is shown in the following figure:

![image](https://user-images.githubusercontent.com/112528710/204198804-a16ec6ae-1d2c-4dbc-ba8e-3025eb986628.png)

![image](https://user-images.githubusercontent.com/112528710/204198819-24a05d3d-379d-410b-99a8-b8ef9650e253.png)


（2）The types of results returned by BraketSDK: Braket returns a result that supports multiple types. For different backends, the returned result types are also different, as shown in the following table:

![image](https://user-images.githubusercontent.com/112528710/204198864-9aad022c-6a45-405b-a905-55914fa9ea6f.png)

（3）The Verbatim compilation compiler does not optimize. Every step of the algorithm is translated accurately to ensure that the implementation of the algorithm is consistent with its design. (In the compilation stage, that is, the gate operation in the circuit is translated into the QPU native gate stage, and the Branch compiler will optimize by default.) .Application scenarios of this function: such as benchmarking the performance of hardware. 

（4）Support the OpenQASM 3.0 . 

（5）Amazon Braket supports access to quantum connectivity query interfaces for different quantum computer platforms

![image](https://user-images.githubusercontent.com/112528710/204198885-7561956e-ddac-4c71-9fc4-58002fe21568.png)

（6）Hybrid jobs. Braket support embedded simulators of PennyLane, which is embedded simulator GPU。

![image](https://user-images.githubusercontent.com/112528710/204198897-c5183424-c450-43cb-8c98-a309f332887a.png)

（7）Hybrid jobs and Braket provide Hybrid jobs for hybrid algorithms. When creating a job, you can upload the script of the quantum algorithm and other related parameters. The job results can be persisted in s3, or viewed in the console and cloud watch.

## 3.QuTrunk Introduce
### 3.1 Quantum Programming Framework
QuTrunk is a free, open source, cross platform quantum computing programming framework independently developed by QUDOOR, including quantum programming API, quantum command translation, quantum computing backend interface, etc. 

QuTrunk uses Python as the host language, and with the syntax features of Python to implement DSL (domain specific language) for quantum programs. All IDEs programmed in Python can be installed. QuTrunk provides various APIs required for quantum programming based on quantum logic gates , quantum circuits and so on. These APIs are implemented by corresponding modules. For example, QCircuit implements quantum circuits, Qubit implements qubits, Qureg implements quantum registers, Command implements instructions for each quantum gate operation, Backend implements backend modules for running quantum circuits, and gate modules implement various basic quantum gate operations. In addition, QuTrunk can also be used as the basis for other  quantum computing applications, such as quantum algorithms, quantum visual programming, quantum machine learning, etc.

QuSprout now is the backend of QuTrunk. QuSprout is also a quantum computing simulation software developed by QUDOOR based on classical computing resources. It supports multi-threading, multi-node, GPU acceleration, and can also be pre-installed in QuBox. QuTrunk provides a quantum programming framework for quantum programming .In QuTrunk,we have established a unified set of quantum programming specifications 

### 3.2 Structure Resolution
The architecture of QuTrunk is shown in the figure below. Developers can use QuBranch to directly compile Python language. Modular design allows developers to adjust the compiler gate group according to the actual situation to better complete customized design. At present, QuTrunk  uses BackendLocal as the backend by default, and provides a Python version of the local backend.

![image](https://user-images.githubusercontent.com/112528710/204198918-678953ae-6d90-4754-81b9-900448efbfc1.png)

At the same time, QuTrunk also supports extending more backends.Theoretically, as long as the backend of the quantum computing access interface is developed externally, QuTrunk can be compatible,for example, IBM, lonq and so on. Developers can use QuTrunk to write quantum programs, then use QuSL to translate the quantum programs into instructions for the target platform, and then choose different backends for computation.

## 4.The usage example of QuTrunk quantum programming framework 

### 4.1  Start your first quantum program with Qutrunk
After the deployment of QuTrunk, we can start to write and run our first quantum computing program.

#### 4.1.1  Switch Python interpreter
Execute` ctrl+shift+p `in Windows and Linux, and `command+shift+p` in MacOS to open the command line.And then enter quan search, and select quan: python interpreter switch. Switching the python interpreter can switch the whole workspace or a single project, that is, switch the python environment.

![image](https://user-images.githubusercontent.com/112528710/204198930-8f66a4a0-5867-4315-8709-0f08d8d1dfbe.png)

#### 4.1.2 Create a new project
Create a new project under the directory to be saved,such as Qun-Demo. In the IDE start interface, select Open Folder, and then select the newly created folder , the display is as follows:

![image](https://user-images.githubusercontent.com/112528710/204198940-3885119b-0779-4eeb-9caa-3aaf0c7e8a0f.png)

#### 4.1.3 Compilation and operation of demo program for quantum computing
From the start interface, select the new python file and save it as demo.py. The following code is an example of the bell_pair algorithm:
Step 1: Environment preparation
```python
    from qutrunk.circuit import QCircuit
from qutrunk.circuit.gates import H, CNOT, Measure
```
Quantum circuit: The `core.circuit` in the above code module provides the quantum circuit function.
Quantum logic gate operation: `from qutrunk. circuit Gates import H, CNOT, Measure` can prepare H gates, CNOT gates and measurement operations. 

Step 2: Initialize the quantum circuit and allocate quantum registers 
```python
    qc = QCircuit()
qr = qc.allocate(2)```python
```

Step 3: Quantum logic gate operation 
```python
    H * qr[0]
    CNOT * (qr[0], qr[1])
    Measure * qr[0]
    Measure * qr[1]

    # print circuit
    qc.print()
```
Print circuit: After the code of the quantum circuit is edited, print the quantum circuit directly. (Use the instruction` Printer.+` to customize the function.) 
According to the prediction result of logic gate operation: ｜00〉+｜11〉

Step 4: Bell Pair quantum circuit operation and result
```python
    # run circuit
    res = qc.run(shots=1024)

    # print result
    print(res.get_measure())
print(res.get_counts()) 
```
At present, QuTrunk can directly output the quantum circuit diagram by running the quantum circuit. 

Step 5: Output the operation results
```python
   *qreg q[2]  
    creg c[2]  
    H * q[0]  
    MCX(1) * (q[0], q[1])  
    Measure * q[0]  
    Measure * q[1]  
[{"00": 505}, {"11": 519}]*  
```
Define quantum register: The above defined quantum register is completed by qreg operation. The instruction `qregq [2] `defines a 2-bit quantum register named q; Similarly, the instruction `creg c [2]` defines a classical register named c.
Measurement result: the measurement result is [{"00": 505}, {"11": 519}]. The result shows that the quantum circuit runs 505 and 519 times respectively, 1024 times in total. Run the above program several times, and the results are different. For example, the second and third run results are [{"00": 507}, {"11": 517}], [{"00": 528}, {"11": 496}], respectively. 


### 4.2 Visual Programming
#### 4.2.1 Initialize quantum programming workspace
Open QuBranch, first initialize the quantum programming workspace: through `ctrl+shift+p` on Windows, `command+shift+p` on macOS to open the command line, enter quan.And then select `quan:初始化量子编程`  and execute initialization. Start the function of initializing the visual programming workspace, which will create a virtual workspace for the developers to program visually.

![image](https://user-images.githubusercontent.com/112528710/204198966-e0182f21-73a3-4d99-a134-b26a44f01940.png)

#### 4.2.2 Start visual quantum programming
Press `ctrl+shift+p/comand+shift+p` again and enter quan. You will see the workforce of   visual quantum programming.Select "quan:quan:量子可视化编程 " to start the visualization function of quantum programming. This function allows users to generate multiple qdoor files for visual programming, and if you switch different qdoor files, you can get different quantum circuit diagrams. It also allows you to edit circuit diagrams by coding or by dragging and dropping quantum gate symbols. Quantum circuit diagrams can be generated when a quantum gate is dragged into a circuit diagram, and removed by dragging a quantum gate from a circuit diagram.. Currently, H, NOT, Sdg, Toffoli, Tdg are supported , X, Y, Z, P, Rx, Ry, Rz, R, SqrtX, T, Measure, where X, Y, Z, P, Rx, Ry, Rz allow adding a control bit, Rx, Ry, Rz allow changing the rotation angle. QuBranch also provides keyword highlighting, code prompt and code auto-completion and other functions. With the help of Qutrunk, developers can check the quantum state statistics of the current quantum circuit diagram.

![image](https://user-images.githubusercontent.com/112528710/204198985-56a6f89b-ee99-483b-821b-c446be085204.png)

#### 4.2.3 Start visual programming example
In the visual programming workforce, the developers can select each graphical programming element to add or delete to complete the programming by dragging and dropping them. If delete an element, just take the element out of the window and release it. The visual programming example is as follows:

![image](https://user-images.githubusercontent.com/112528710/204199005-568edf48-8be0-4567-b2bd-04dc3bb6c6aa.png)


**Writer**
Keith Yan（丘秉宜）The First Community Hero of China
![丘](https://user-images.githubusercontent.com/112528710/204707041-70198ae8-248c-4606-b973-031af5bdb5e9.jpg)


Bertran Shao（邵伟），Quantum Developer Relations Leader, the initiator of the first open source quantum computing community in China
![image](https://user-images.githubusercontent.com/112528710/204704277-97d14273-ef55-46d7-a0c7-626881cb8dec.png)

Don Tang (唐松炎), a founder member of Qike Quantum Developer Relations, the first open source quantum computing community in China
![image](https://user-images.githubusercontent.com/112528710/204704300-4c88a2ff-de40-401b-b6fb-fe2b2c6afaea.png)


