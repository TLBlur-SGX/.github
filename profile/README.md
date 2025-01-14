# TLBlur: Compiler-Assisted Automated Hardening against Controlled Channels on Off-the-Shelf Intel SGX Platforms

TLBlur is a *compiler-assisted defense* against page fault attacks on Intel SGX that leverages the AEX-Notify hardware extension.
Instrumented code builds a *Page Access Map (PAM)* at runtime to inform a *page prefetcher* and reconstruct the TLB after IRQ in order to hide page accesses from the untrusted operating system.

TLBlur is the result of our research publication at the 34th USENIX Security Symposium (USENIX Security 2025). It should be cited as follows:

> Vanoverloop, D., Sanchez, A., Toffalini, F., Piessens, F., Payer, M., Van Bulck , J. (2025, August). TLBlur: Compiler-Assisted Automated Hardening against Controlled Channels on Off-the-Shelf Intel SGX Platforms. In 34th USENIX Security Symposium (USENIX Security 2025).

BibTeX:

```bib
@inproceedings{vanoverloop2025tlblur,
  title={{TLBlur}: Compiler-Assisted Automated Hardening against Controlled Channels on Off-the-Shelf {Intel SGX} Platforms},
  author={Vanoverloop, Daan and Sanchez, Andres and Toffalini, Flavio and Piessens, Frank and Payer, Mathias and Van Bulck, Jo},
  booktitle={34th {USENIX} Security Symposium ({USENIX} Security 25)},
  month=August,
  year=2025
}
```

This organization contains the following repositories:

- `tlblur`: Main repository with benchmarked programs. Includes other repositories as submodules.
- `llvm-project`: Fork of [llvm/llvm-project](https://github.com/llvm/llvm-project) with TLBlur instrumentation passes
- `sgx-step`: Fork of [jovanbulck/sgx-step](https://github.com/jovanbulck/sgx-step) with attack on libjpeg and profiler (to be upstreamed soon)
- `linux-sgx`: Fork of [intel/linux-sgx](https://github.com/intel/linux-sgx) with TLBlur page prefetcher
- `intel-sgx-ssl`: Fork of [intel/intel-sgx-ssl](https://github.com/intel/intel-sgx-ssl) with changes to compile with TLBlur instrumentation
