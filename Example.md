'''
mermaid
graph TD
    A[Build LiteRT for iOS] --> B[Prerequisites]
    A --> C[Build Options]
    A --> D[Usage Options]
    
    B --> B1[Install Xcode]
    B --> B2[Install Bazel]
    B --> B3[Configure WORKSPACE & .bazelrc]
    
    C --> C1[Dynamic Framework]
    C --> C2[Static Framework]
    C --> C3[Selective Build]
    
    C1[Dynamic Framework] -->|Recommended| C1A[TensorFlowLiteC_framework]
    C2[Static Framework] --> C2A[TensorFlowLiteC_static_framework]
    C3[Selective Build] --> C3A[Model-specific frameworks]
    
    D --> D1[CocoaPods]
    D --> D2[Bazel]
    D --> D3[Direct Xcode]
    
    D1 --> D1A[TensorFlowLiteSwift]
    D1 --> D1B[TensorFlowLiteObjC]
    D1 --> D1C[TensorFlowLiteC]
    
    D2 --> D2A[Swift Library]
    D2 --> D2B[Objective-C Library]
    
    D3 --> D3A[Embedded Framework]
    D3 --> D3B[Framework Search Paths]
