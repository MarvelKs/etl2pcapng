
# About

This tool enables you to view ndiscap packet captures with Wireshark.

Windows ships with an inbox packet capture component called "ndiscap," which is implemented
as an ETW trace provider. Due to performance problems with the other popular packet capture
method (winpcap, which comes with Wireshark), ndiscap should be preferred. A capture can
be collected with:

netsh trace start capture=yes report=disabled

netsh trace stop

The file generated by ndiscap is an etl file, which can be opened by ETW-centric tools
like Microsoft Message Analyzer, but cannot be opened by Wireshark, which is the preferred
tool for many engineers. Etl2pcapng.exe can convert the etl file to a pcapng file for
opening with Wireshark.

# Usage

etl2pcapng.exe in.etl out.pcapng

After converting the file, the tool prints a table which shows mappings between Windows
interface indices and pcapng interface IDs.

# Building

Run msbuild.exe with no parameters in the src directory. This must be done
in a Visual Studio Command Prompt.

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
