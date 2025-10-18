# CSE420 - Computer Architecture Laboratory

A comprehensive collection of computer architecture laboratory assignments and projects covering fundamental concepts of computer organization, processor design, memory systems, and digital logic implementation. This laboratory coursework demonstrates practical understanding of computer hardware architecture through hands-on experiments and simulations.

## 🌟 Course Overview

CSE420 Computer Architecture Laboratory provides hands-on experience with computer hardware design principles, processor architecture, memory systems, and digital logic implementation. The coursework includes practical experiments, simulations, and projects that demonstrate understanding of how computer systems are designed and function at the hardware level.

## 📚 Lab Assignments

### Lab 01: Introduction to Computer Architecture

- **Objective**: Introduction to basic computer architecture concepts and digital logic
- **Skills**: Digital logic design, basic computer organization
- **Topics**: Logic gates, combinational circuits, basic processor components
- **Tools**: Digital logic simulators, hardware description languages

### Lab 02: Processor Design and Implementation

- **Objective**: Understanding processor architecture and instruction execution
- **Skills**: Processor design, instruction set architecture, control unit design
- **Topics**: ALU design, register file, instruction decoding, control signals
- **Tools**: Processor simulators, HDL (Hardware Description Language)

### Lab 03: Memory Systems and Cache Design

- **Objective**: Implementation and analysis of memory hierarchy systems
- **Skills**: Memory system design, cache implementation, memory management
- **Topics**: Cache memory, virtual memory, memory mapping, access patterns
- **Tools**: Memory simulators, cache analysis tools

## 🛠️ Technical Skills Demonstrated

### Digital Logic Design

- **Combinational Logic**: Logic gates, multiplexers, decoders, adders
- **Sequential Logic**: Flip-flops, registers, counters, state machines
- **Circuit Design**: Boolean algebra, Karnaugh maps, circuit optimization
- **Hardware Description**: VHDL/Verilog programming and simulation

### Processor Architecture

- **Instruction Set Architecture**: Instruction formats, addressing modes
- **Control Unit Design**: Microprogramming, hardwired control
- **Arithmetic Logic Unit**: ALU design, arithmetic operations
- **Pipeline Design**: Instruction pipelining, hazard detection

### Memory Systems

- **Cache Memory**: Direct-mapped, set-associative, fully-associative caches
- **Virtual Memory**: Page tables, TLB, memory management
- **Memory Hierarchy**: L1, L2, L3 cache design and optimization
- **Access Patterns**: Spatial and temporal locality analysis

### Computer Organization

- **Bus Systems**: Data, address, and control buses
- **I/O Systems**: Interrupt handling, DMA, I/O controllers
- **Performance Analysis**: CPI, MIPS, throughput calculations
- **System Integration**: Component interconnection and communication

## 📁 Project Structure

```
CSE420/
├── Lab01_Group_05.zip          # Introduction to Computer Architecture
├── Lab02_Group_05.zip          # Processor Design and Implementation
└── Lab03_Group_05.zip          # Memory Systems and Cache Design
```

## 🔧 Key Concepts Implemented

### Digital Logic Fundamentals

- **Boolean Algebra**: Logic operations and simplification
- **Combinational Circuits**: Multiplexers, decoders, encoders, adders
- **Sequential Circuits**: Flip-flops, registers, counters, state machines
- **Circuit Analysis**: Timing analysis, propagation delays, setup/hold times

### Processor Design

- **Instruction Set Architecture**: RISC vs CISC, instruction formats
- **Control Unit**: Microprogrammed and hardwired control units
- **Arithmetic Logic Unit**: ALU design and arithmetic operations
- **Register File**: Register organization and data paths

### Memory Hierarchy

- **Cache Memory**: Different cache organizations and replacement policies
- **Virtual Memory**: Address translation and memory management
- **Memory Mapping**: Direct, associative, and set-associative mapping
- **Performance Metrics**: Hit rates, miss penalties, access times

### System Integration

- **Bus Architecture**: System bus design and protocols
- **I/O Systems**: Interrupt-driven and programmed I/O
- **Performance Analysis**: System performance evaluation and optimization
- **Design Trade-offs**: Area, power, and performance considerations

## 📊 Lab Assignment Details

### Lab 01: Introduction to Computer Architecture

- **Digital Logic Basics**: Logic gates and combinational circuits
- **Boolean Algebra**: Logic simplification and optimization
- **Circuit Design**: Basic digital circuit implementation
- **Simulation**: Digital logic simulation and verification

### Lab 02: Processor Design and Implementation

- **Instruction Set Design**: Instruction formats and addressing modes
- **Control Unit**: Microprogrammed control unit implementation
- **ALU Design**: Arithmetic and logic operations
- **Pipeline Design**: Basic instruction pipelining concepts

### Lab 03: Memory Systems and Cache Design

- **Cache Organization**: Direct-mapped and set-associative caches
- **Replacement Policies**: LRU, FIFO, and random replacement
- **Memory Hierarchy**: Multi-level cache system design
- **Performance Analysis**: Cache performance evaluation

## 🎯 Summary

### Project Title

**CSE420 - Computer Architecture Laboratory & Hardware Design**

### Project Description

Completed comprehensive computer architecture laboratory coursework including 3 major lab assignments covering digital logic design, processor architecture, and memory systems. Implemented various computer hardware components using digital logic design principles, processor design concepts, and memory hierarchy optimization techniques.

### Key Achievements

- **Digital Logic Design**: Implemented combinational and sequential logic circuits
- **Processor Architecture**: Designed and analyzed processor components and instruction sets
- **Memory Systems**: Implemented cache memory systems and memory hierarchy
- **Hardware Simulation**: Used digital logic simulators and HDL tools
- **Performance Analysis**: Evaluated system performance and optimization techniques
- **Circuit Design**: Created optimized digital circuits with proper timing analysis
- **System Integration**: Integrated various hardware components into complete systems

### Technical Skills Demonstrated

- **Digital Logic Design**: Boolean algebra, logic gates, combinational/sequential circuits
- **Hardware Description Languages**: VHDL/Verilog programming and simulation
- **Processor Design**: Instruction set architecture, control unit design, ALU implementation
- **Memory Systems**: Cache design, virtual memory, memory hierarchy optimization
- **Computer Organization**: Bus systems, I/O systems, system integration
- **Performance Analysis**: Timing analysis, performance metrics, optimization techniques
- **Simulation Tools**: Digital logic simulators, processor simulators, memory simulators
- **Circuit Analysis**: Propagation delays, setup/hold times, timing constraints

### Technologies Used

**Hardware Design**: Digital logic, VHDL/Verilog, Circuit simulation
**Tools**: Digital logic simulators, HDL compilers, Performance analysis tools
**Concepts**: Computer architecture, Processor design, Memory systems

## 📈 Learning Outcomes

### Theoretical Knowledge

- **Computer Architecture**: Understanding of computer system organization
- **Digital Logic**: Boolean algebra and digital circuit design principles
- **Processor Design**: Instruction set architecture and control unit design
- **Memory Systems**: Memory hierarchy and cache design concepts

### Practical Skills

- **Hardware Design**: Digital circuit design and implementation
- **Simulation**: Hardware simulation and verification techniques
- **Performance Analysis**: System performance evaluation and optimization
- **Problem Solving**: Hardware design problem analysis and solution

## 🔧 Design Examples

### ALU Design

```verilog
module ALU(
    input [31:0] A, B,
    input [3:0] ALUControl,
    output reg [31:0] Result,
    output Zero
);
    always @(*) begin
        case (ALUControl)
            4'b0000: Result = A & B;      // AND
            4'b0001: Result = A | B;      // OR
            4'b0010: Result = A + B;      // ADD
            4'b0110: Result = A - B;      // SUBTRACT
            4'b0111: Result = A < B ? 1 : 0; // SLT
            default: Result = 0;
        endcase
    end
    assign Zero = (Result == 0);
endmodule
```

### Cache Controller

```verilog
module CacheController(
    input clk, reset,
    input [31:0] address,
    input [31:0] data_in,
    input read, write,
    output [31:0] data_out,
    output hit, miss
);
    // Cache implementation with hit/miss detection
    // Direct-mapped cache with 64 blocks
    reg [31:0] cache_data [0:63];
    reg [25:0] cache_tag [0:63];
    reg cache_valid [0:63];

    wire [5:0] index = address[7:2];
    wire [25:0] tag = address[31:8];

    assign hit = cache_valid[index] && (cache_tag[index] == tag);
    assign miss = !hit;

    always @(posedge clk) begin
        if (hit && read) begin
            data_out <= cache_data[index];
        end else if (hit && write) begin
            cache_data[index] <= data_in;
        end
    end
endmodule
```

### State Machine Design

```verilog
module StateMachine(
    input clk, reset, start,
    output reg [2:0] state,
    output reg done
);
    parameter IDLE = 3'b000;
    parameter FETCH = 3'b001;
    parameter DECODE = 3'b010;
    parameter EXECUTE = 3'b011;
    parameter WRITEBACK = 3'b100;

    always @(posedge clk or posedge reset) begin
        if (reset) begin
            state <= IDLE;
            done <= 0;
        end else begin
            case (state)
                IDLE: if (start) state <= FETCH;
                FETCH: state <= DECODE;
                DECODE: state <= EXECUTE;
                EXECUTE: state <= WRITEBACK;
                WRITEBACK: begin
                    state <= IDLE;
                    done <= 1;
                end
            endcase
        end
    end
endmodule
```

## 📈 Future Applications

- [ ] Advanced processor design (superscalar, VLIW)
- [ ] Memory system optimization and cache design
- [ ] Parallel processing and multi-core systems
- [ ] Embedded systems and microcontroller design
- [ ] FPGA and ASIC design
- [ ] System-on-Chip (SoC) design
- [ ] Performance optimization and power analysis
- [ ] Hardware-software co-design

## 👨‍💻 Author

**RD-Bhowmik**

- Student ID: 24141083
- Course: CSE420 Computer Architecture Laboratory
- Institution: BRAC University

---
