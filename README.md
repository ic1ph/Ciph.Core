# Ciph.Core - EDR Stress-Testing Framework

## Overview
Ciph.Core is a specialized .NET 8 framework designed for advanced security testing and EDR evasion research. The project implements cutting-edge techniques for memory-resident threat simulation in authorized environments.

## Features

### 1. D/Invoke Engine (Native.cs)
- Dynamic ntdll.dll function resolution from disk
- User-mode API hook bypassing
- PEB traversal for module enumeration
- Manual function pointer resolution

### 2. AES-256-GCM Encryption (Encryption.cs)
- Military-grade payload encryption
- Password-based key derivation (PBKDF2)
- Chunked encryption for large payloads
- Anti-forensics obfuscation techniques

### 3. Process Hollowing (ProcessHollowing.cs)
- Complete process hollowing implementation
- PE header validation and parsing
- Memory allocation and protection
- Thread context manipulation
- Real-time process monitoring

### 4. Diagnostic UI (MainWindow.xaml)
- Real-time injection stage monitoring
- Memory offset tracking
- Process status visualization
- Dark theme interface

## Technical Specifications

### Requirements
- .NET 8.0 Windows Target
- x64 Architecture
- Administrative privileges required

### Core Components

#### Native Operations
- `VirtualAllocEx` - Memory allocation in target processes
- `WriteProcessMemory` - Memory writing capabilities
- `SetThreadContext` - Thread context manipulation
- `NtUnmapViewOfSection` - Memory unmapping
- `NtResumeThread` - Thread execution control

#### Encryption Standards
- AES-256-GCM authenticated encryption
- 12-byte nonce for IV
- 16-byte authentication tag
- PBKDF2 with SHA-256 and 100,000 iterations

#### Memory Management
- PAGE_EXECUTE_READWRITE protection
- MEM_COMMIT | MEM_RESERVE allocation
- Section-based PE mapping
- Entry point redirection

## Usage

### Basic Workflow
1. Select target process (e.g., svchost.exe)
2. Load and encrypt payload
3. Bypass user-mode hooks
4. Execute process hollowing
5. Monitor injection stages
6. Track memory offsets

### Advanced Features
- Chunked payload delivery
- Noise embedding for stealth
- Decoy payload generation
- Secure memory erasure

## Compilation
```bash
dotnet build Ciph.Core.csproj --configuration Release
```

## Execution
```bash
dotnet Ciph.Core.exe
```

## Architecture
```
Ciph.Core/
├── Ciph.Core.csproj          # Project configuration
├── Native.cs                 # D/Invoke engine
├── Encryption.cs             # AES-256-GCM wrapper
├── ProcessHollowing.cs       # Memory manipulation
├── MainWindow.xaml           # UI definition
├── MainWindow.xaml.cs        # UI logic
├── App.xaml                  # Application entry
├── App.xaml.cs              # Application logic
└── README.md                # Documentation
```

## Security Notes
This framework is designed exclusively for authorized security testing environments. All operations are performed within controlled simulation contexts with proper oversight.

## Compatibility
- Windows 10/11 x64
- .NET 8.0 Runtime
- Administrative privileges required for memory operations
