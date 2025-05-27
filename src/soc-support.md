# Guide for Silicon Vendors to Enable Rust Support for Their SoCs

## Introduction

Rust has emerged as a powerful and safety-focused programming language that is gaining traction among embedded developers. Silicon vendors who wish to enable Rust support for their System-on-Chip (SoC) products can benefit from this trend by attracting a growing community of Rust developers.

This guide aims to help silicon vendors enable Rust support, either independently or by empowering third-party developers. It outlines the essential resources, tasks, and priorities needed to foster a robust Rust ecosystem around their SoCs.

[TODO: Add note to contact REWG leads for assistance with strategy in engaging with community]

## Essential Resources

### Documentation

Detailed documentation is essential to effective development and debugging. It allows developers to understand the SoC, including the memory map, peripherals, interrupt handling, low-power modes, etc.
Ensure documentation covers all hardware aspects, from register-level details to system-level interactions. The documentation should be publicly available (in the regrettable case where it would not be possible to make the documentation public, any NDA should allow the publication of open-source code derived from it).

### Register Description Files

Register description files are used to generate Peripheral Access Crates (PACs). The most common format is SVD ([System View Description](https://open-cmsis-pack.github.io/svd-spec)).

[TODO: Rust developers has often encountered issues with SVD files, we want contact information to report those issues.]

### Flash Algorithms

[Flash Algorithms](https://open-cmsis-pack.github.io/Open-CMSIS-Pack-Spec/main/html/flashAlgorithm.html) are integrated with debugging tools like `probe-rs`. They facilitate firmware programming and debugging and streamline development workflows.

### Vendor Tooling

[TODO: @diondokter pointed out that some SoCs have custom tools to generate images or flash them.]

### Contact Information

[TODO: Request contact information]

## Maintaining PAC and HAL Crates

Maintaining Peripheral Access Crates (PACs) and Hardware Abstraction Layer (HAL) crates is the core of enabling Rust support.

### Generate and maintain PACs

[TODO: Multiple tools (svd2rust, chiptool, raltool, svd2pac) perform this operation.]
[TODO: Give some context as to why]

### Develop and maintain HAL crates

Implement `embedded-hal` and `embedded-hal-async` traits. Adhering to those traits ensures compatibility across the Rust embedded ecosystem, enhancing interoperability.

[TODO: We want Rust code, not a wrapper around HAL implemented in C. Incremental porting strategy acceptable. Release early, releast often]

### Common recommendations

- [TODO: no_std]
- [TODO: Publish on crates.io]
- [TODO: Semantic versioning]
- [TODO: Licenses: Apache 2.0 and MIT strongly recommended]
- [TODO: Other Rust ]

### Issue Tracking

[TODO: Discuss triaging, labeling, and involving the community in issue resolution.]

### Facilitate Debugging and Testing

[TODO: Provide guidance on integrating with `probe-rs` for debugging and testing.]
[TODO: Emphasize the importance of debug-based tooling like `defmt-rtt`.]

## Nice-to-Have for Enhanced Ecosystem Support

### Examples

[TODO: Some basic examples are expected to be part of the HAL]

### BSP (Board Support Package) crates

[TODO: Explain when BSP is relevant]

### Project templates

[TODO: Explain what project templates are, and some examples]

### Integration with Popular IDEs and Tools

[TODO: Offer guides on setting up development environments for Rust embedded projects?]
[TODO: List popular tools used in embedded Rust, such as `probe-rs`, `defmt`, `defmt-test`]

## Conclusion (AI-generated)

Enabling Rust support for your SoC opens the door to a vibrant community of developers who value safety, performance, and reliability. By providing essential resources, maintaining high-quality PACs and HAL crates, and fostering a supportive ecosystem, you can empower both internal teams and third-party developers to unlock the full potential of your hardware.

As the Rust embedded ecosystem continues to grow, embracing these practices positions your company at the forefront of this movement, attracting developers who are passionate about building robust and innovative systems. Encourage ongoing engagement with the Rust community to stay updated on best practices and tools, ensuring that your SoC remains a preferred choice for Rust developers.

By following this guide, you can create a comprehensive and supportive environment that not only enables Rust support but also nurtures a thriving developer ecosystem around your products.
