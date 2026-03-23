# BITSilicon – Digital Design Assignment 2

This project implements a *Synchronous FIFO (First In First Out)* queue in Verilog. The design uses:
- **Memory-Based Storage**: Uses a register array (`mem`) to store FIFO data, with configurable width (`DATA_WIDTH`) and depth (`DEPTH`)
- **Pointer-Based Address Management**: Maintains separate write (`wr_ptr`) and read (`rd_ptr`) pointers that increment with wrap-around behavior
- **Occupancy Counter**: Tracks the number of elements in the FIFO using an occupancy counter (`oc`), used for generating full and empty flags
- **Status Signals**: 
  - `wr_full`: Asserted when occupancy equals DEPTH
  - `rd_empty`: Asserted when occupancy equals 0
- **Simultaneous Operations**: Supports concurrent read and write operations, with individual operation controllers for write-only, read-only, or simultaneous access
- **Wrapper Module**: `sync_fifo_top` provides a clean interface with automatic address width calculation using `$clog2(DEPTH)`

