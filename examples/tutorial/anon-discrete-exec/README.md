## Tutorial: Anonymous Discrete Execution Data I/O

The following examples demonstrate data I/O on discrete executions of R scripts by [anonymous users](http://deployr.revolutionanalytics.com/documents/dev/api-doc/guide/introduction.html#introusers) on [stateless projects](http://deployr.revolutionanalytics.com/documents/dev/api-doc/guide/introduction.html#anonymousprojects) managed by DeployR.

```
Source: src/main/java/com/revo/deployr/client/example/data/io/anon/discrete/exec/*.java
```

## Tutorial: Summary

| Example Application | Example Data Input | Example Data Output |
| ------------------- | ------------------ | ------------------- |
| EncodedDataInBinaryFileOut | DeployR-encoded application data | Working directory binary file |
| ExternalDataInDataFileOut | Reference to external data source | Working directory data file |
| RepoFileInEncodedDataOut | Reference to repository-managed binary file | DeployR-encoded R object data |
| RepoFileInGraphicsPlotOut | Reference to repository-managed data file | Graphics device generated plot | 
| MultipleDataInMultipleDataOut | Multilple data inputs | Multiple data outputs |

The name of each example application indicates the data input and data output types used by the application. The following naming convention applies:

[`Data Input Type`]In[`Data Output Type`]Out

For example, the `EncodedDataInBinaryFileOut` example indicates that DeployR-encoded application data (`EncodedDataIn`) will be sent as a data input while a binary file from the R session working directory (`BinaryFileOut`) will be returned as a data output.

The set of data input and output types currently demonstrated by these examples are described as follows:

- `EncodedDataIn` represents DeployR-encoded application data sent as a data input.
- `RepoFileIn` represents a reference to a repository-managed file sent as a data input.
- `ExternalDataIn` represents DeployR-encoded references to external data sources sent as an input.
- `MultipleDataIn` represents multiple data inputs.
- `EncodedDataOut` represents DeployR-encoded R object data returned as a data output.
- `BinaryFileOut` represents a binary file from the working directory returned as a data output.
- `GraphicsPlotOut` represents a plot generated by the graphics device returned as a data output.
- `DataFileOut` represents a data file from the working directory returned as a data output.
- `MultipleDataOut` represents multiple data outputs.

## Tutorial: Running the Examples

Use the [DeployR CLI](https://github.com/deployr/deployr-cli) to download and run the `java-example-client-data-io` examples.


## Tutorial: Example-by-Example


### 1. EncodedDataInBinaryFileOut

```
Example: com/revo/deployr/client/example/data/io/anon/discrete/exec/EncodedDataInBinaryFileOut.java
```

The following table describes the application workflow (steps) along with the log output generated at each step:

| Step          | Log Output                                   |
| --------------| ---------------------------------------------|
| CONFIGURATION | Using endpoint=http://localhost:7400/deployr |
| CONNECTION    | Established anonymous connection [ RClient ] |
| DATA INPUT    | DeployR-encoded R input set on execution, [ ProjectExecutionOptions.rinputs ]|
| EXECUTION     | Discrete R script execution completed [ RScriptExecution ] |
| DATA OUTPUT   | Retrieved working directory file output hip.rData [ RProjectFile ] |

### 2. ExternalDataInDataFileOut

```
Example: com/revo/deployr/client/example/data/io/anon/discrete/exec/ExternalDataInDataFileOut.java
```

The following table describes the application workflow (steps) along with the log output generated at each step:

| Step           | Log Output                                   |
| -------------- | ---------------------------------------------|
| CONFIGURATION  | Using endpoint=http://localhost:7400/deployr |
|   CONNECTION   | Established anonymous connection [ RClient ] |
|   DATA INPUT   | External data source input set on execution, [ ProjectPreloadOptions.rinputs ] |
|   EXECUTION    | Discrete R script execution completed [ RScriptExecution ] |
|  DATA OUTPUT   | Retrieved working directory file output hip.csv [ RProjectFile ] |

### 3. RepoFileInEncodedDataOut

```
Example: com/revo/deployr/client/example/data/io/anon/discrete/exec/RepoFileInEncodedDataOut.java
```

The following table describes the application workflow (steps) along with the log output generated at each step:

| Step           | Log Output                                   |
| -------------- | ---------------------------------------------|
| CONFIGURATION  | Using endpoint=http://localhost:7400/deployr |
|   CONNECTION   | Established anonymous connection [ RClient ] |
|   DATA INPUT   | DeployR-encoded R input set on execution, [ ProjectExecutionOptions.rinputs ] |
|   EXECUTION    | Discrete R script execution completed [ RScriptExecution ] |
|  DATA OUTPUT   | Retrieved working directory file output hip.rData [ RProjectFile ] |

### 4. RepoFileInGraphicsPlotOut

```
Example: com/revo/deployr/client/example/data/io/anon/discrete/exec/RepoFileInGraphicsPlotOut.java
```

The following table describes the application workflow (steps) along with the log output generated at each step:

| Step           | Log Output                                   |
| -------------- | ---------------------------------------------|
| CONFIGURATION  | Using endpoint=http://localhost:7400/deployr |
|   CONNECTION   | Established anonymous connection [ RClient ] |
|   DATA INPUT   | Repository data file input set on execution, [ ProjectExecutionOptions.preloadDirectory ] |
|   EXECUTION    | Discrete R script execution completed [ RScriptExecution ] |
|  DATA OUTPUT   | Retrieved graphics device plot output unnamedplot001.png [ RProjectResult ] |

### 5. MultipleDataInMultipleDataOut

```
Example: com/revo/deployr/client/example/data/io/anon/discrete/exec/MultipleDataInMultipleDataOut.java
```

The following table describes the application workflow (steps) along with the log output generated at each step:

| Step           | Log Output                                   |
| -------------- | ---------------------------------------------|
| CONFIGURATION  | Using endpoint=http://localhost:7400/deployr |
|   CONNECTION   | Established anonymous connection [ RClient ] |
|   DATA INPUT   | Repository binary file input set on execution, [ ProjectExecutionOptions.preloadWorkspace ] |
|   DATA INPUT   | External data source input set on execution, [ ProjectPreloadOptions.rinputs ] |
|  EXEC OPTION   | DeployR-encoded R object request set on execution [ ProjectExecutionOptions.routputs ] |
|   EXECUTION    | Discrete R script execution completed [ RScriptExecution ] |
|  DATA OUTPUT   | Retrieved R console output [ String ] |
|  DATA OUTPUT   | Retrieved DeployR-encoded R object output hip [ RDataFrame ] |
|  DATA OUTPUT   | Retrieved DeployR-encoded R object output hipDim [ RNumericVector ] |
|  DATA OUTPUT   | Retrieved DeployR-encoded R object hipDim value=[2719.0, 9.0] |
|  DATA OUTPUT   | Retrieved DeployR-encoded R object output hipNames [ RStringVector ] |
|  DATA OUTPUT   | Retrieved DeployR-encoded R object hipNames value=[HIP, Vmag, RA, DE, Plx, pmRA, pmDE, e_Plx, B.V] |
|  DATA OUTPUT   | Retrieved working directory file output hip.csv [ RProjectFile ] |
|  DATA OUTPUT   | Retrieved working directory file output hip.rData [ RProjectFile ] |
|  DATA OUTPUT   | Retrieved graphics device plot output unnamedplot001.png [ RProjectResult ] |


## License ##

Copyright (C) 2010-2015 by Revolution Analytics Inc.

This program is licensed to you under the terms of Version 2.0 of the
Apache License. This program is distributed WITHOUT
ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING THOSE OF NON-INFRINGEMENT,
MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE. Please refer to the
Apache License 2.0 (http://www.apache.org/licenses/LICENSE-2.0) for more 
details.
