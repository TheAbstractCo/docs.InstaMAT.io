---
title: InstaMAT Pipeline
description: InstaMAT Pipeline is a cross-platform console application that enables you to render your Element library without having to use a graphical user interface.
published: true
date: 2023-03-02T17:25:58.523Z
tags: 
editor: markdown
dateCreated: 2023-01-20T15:25:35.553Z
---

![pipelinepreviewcompressed.jpg](/instamat_pipeline/pipelinepreviewcompressed.jpg)

InstaMAT Pipeline is a cross-platform console application that enables you to render your Element library without having to use a graphical user interface. Complex pipeline tools such as highly custom mesh bakers or unit tests can be set up within minutes.

<a name="getting-started"></a>
## Getting Started
To get started quickly with InstaMAT Pipeline, it is recommended to inspect the sample files that are included in the InstaMAT Pipeline distribution.

InstaMAT Pipeline's primary purpose is to provide a trivial way to achieve a command-line or scripted execution of all Atom or Element graphs. Graph input parameters can be easily tweaked, whether modifying arithmetic values or loading resources from disk. Outputs can be exported in a variety of formats and due to the flexible nature of InstaMAT Pipeline, even complex jobs such as baking mesh data can be easily achieved. InstaMAT Pipeline's excellent UX and versatility enables it to be used anywhere from asset pipelines to server backends.

Advanced features include assembling packages or editing meta data, unit-testing your library and automatically generating the documentation for your in-house library.

<a name="prerequisites"></a>
## Prerequisites

InstaMAT Pipeline for Windows requires Windows 10 and later.
InstaMAT Pipeline for macOS requires macOS Big Sur 11.00 or later.

<a name="license"></a>
## License

<a name="machine-authorization"></a>
### Machine Authorization

Before InstaMAT Pipeline can be used, your workstation needs to be authorized. To authorize your workstation `cd` into the InstaMAT Pipeline directory, execute the following command and replace the placeholders with your actual license information:

	InstaMATPipeline -authorize <Email> <LicenseKey>

Your workstation is now authorized for use with InstaMAT. Make sure to deauthorize your workstation before uninstalling InstaMAT or you will not be able to authorize another workstation.

> Machine authorization for InstaMAT is system-wide. If you've already been using InstaMAT on your computer, there is no need to authorize your machine for InstaMAT Pipeline.
> 
> Make sure to deauthorize your workstation prior to uninstalling InstaMAT, or the seat/node will remain locked.

<a name="machine-deauthorization"></a>
### Machine Deauthorization

To deauthorize your workstation prior to uninstalling InstaMAT Pipeline, use the `-deauthorize` argument:

```
	InstaMATPipeline -deauthorize <Email> <LicenseKey>
```

> Deauthorization takes up to 24 hours to complete. Until the deauthorization cycle is fully complete, the seat/node will remain locked and cannot be used to activate another machine.{.is-info}

<a name="offline-authorization-enterprise"></a>
### Offline Authorization (Enterprise)

Enterprise licensees can make use of offline authorization in situations where a machine that needs to be activated has no access to the internet. In these cases, a machine that has an active internet connection can be used to create a license file on behalf of another machine.

First, it is necessary to acquire the machine key of the target machine by specifying the `-machineKey` argument:

```
    InstaMATPipeline -machineKey
```

InstaMAT Pipeline will now output the machine key to the console. Copy and paste the key to the machine that will fulfill the authorization request and specify the machine key together with the `authorizeKey` argument:

```
    InstaMATPipeline -authorizeKey <Key> <Filename> <Email> <LicenseKey>
```

InstaMAT Pipeline will now request a license file for the specified `<Key>` and write it to the specified `<Filename>`.

Copy the generated license file to the target machine and ingest it into the InstaMAT licensing system by specifying the `-ingestLicense` argument:

```
    InstaMATPipeline -ingestLicense <Filename>
```

The target machine will now be fully activated and ready for use with any of the tools that are part of the InstaMAT SDK.


<a name="atom-and-element-execution"></a>
## Atom and Element Execution

InstaMAT Pipeline allows executing Atom and Element Graphs from the command-line. To execute a graph, the `Execute` application mode needs to be specified through the `-mode` argument, optionally followed by the filename of the package that contains the Graph:

```
    InstaMATPipeline -mode Execute <Filename>
```

After setting the application mode, an additional set of program arguments becomes available that allows configuring the graph execution. The argument `-graph` specifies the graph that is executed, its output size, and the format of the output texture files:

```
    -graph <Name> <OutputWidth> <OutputHeight> <OutputFormat> <OutputPathFormat>
```

> InstaMAT Pipeline ships with a bundle of demo graphs that you can execute if you haven't created any graphs yet.{.is-info}

<a name="executing-a-graph"></a>
### Executing a Graph

The following example executes the graph `Arc Pavement` that is shipped with InstaMAT Pipeline:

```
    InstaMATPipeline -mode Execute -graph "ArcPavement" 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.tiff"
```

The argument `-mode Execute` enables the graph execution mode. No package filepath needs to be specified here because the graph is part of the InstaMAT Graph Library. The `-graph` argument is followed by:
    
  - the `<Name>` of the graph, `Arc Pavement`,
  - the `<OutputWidth>` and `<OutputHeight>`, set to `1024 1024`,
  - the `<OutputFormat>`, set to `Normalized8`,
  - and the `<OutputPathFormat>`.

An overview of supported output formats can be found in the section [Configuring the Execution Format](#configuring-the-execution-format). More information on how to configure the output paths can be found in the chapter [Configuring Outputs with InstaMAT Variables](#format-strings-with-InstaMAT-script-variables). 


<a name="executing-a-graph-from-an-external-package"></a>
### Executing a Graph from an External Package

The following example executes the graph `Aged Gold Icon` from an external package under the relative filepath `Environment/Packages/Materials/AgedGoldenInstaMAT.MAT`:

```
    InstaMATPipeline -mode Execute "Environment/Packages/Materials/AgedGoldenInstaMAT.MAT" -graph "Aged Golden Icon" 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.tiff"
```
As packages typically contain only a few graphs, the full graph name does not need to be specified. Instead, a file pattern that consists of the word beginning followed by an asterisk can be used:

```
    InstaMATPipeline -mode Execute "Environment/Packages/Materials/AgedGoldenInstaMAT.MAT" -graph "Aged*" 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.tiff"
```

<a name="configuring-the-execution-format"></a>
### Configuring the Execution Format

InstaMAT Pipeline can execute graphs at an arbitrary resolution and supports multipe execution formats:

  - `Normalized8`: 8 bits normalized per component
  - `Normalized16`: 16 bits normalized per component
  - `FullRange16`: 16 bits full range per component
  - `FullRange32`: 32 bits full range per component

The following example executes the graph `Moisture` from the InstaMAT library at a resolution of 2048x2048 and outputs a 32-bit texture:

```
    InstaMATPipeline -mode Execute "Environment/Packages/grunge/Moisture.MAT" -graph "Moisture" 2048 2048 FullRange32 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.tiff"
```

To execute the same graph at a 512x512 resolution and output a normalized 16-bit texture, the following command can be used:

```
    InstaMATPipeline -mode Execute "Environment/Packages/grunge/Moisture.MAT" -graph "Moisture" 512 512 Normalized16 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.tiff"
```

<a name="configuring-parameters"></a>
### Configuring Parameters

When executing a graph through InstaMAT Pipeline, its input parameters can be modified through command-line arguments. With the following pattern, any number of graph parameters can be set at once:

```
    -parameter <Name> <ParameterValue>
```

The `ParameterValue` must be JSON-formatted. Scalar values don't need to be put in quotes:
  
  - `94` represents an integer value
  - `94.83` represents a float with the value `94.83f`
  - `true` and `false` represent boolean values

Vector values are passed as JSON arrays:

  - `[ 1.0, 2.0, 3.0 ]` represents a float vector with 3 elements
  - `[ 1, 2 ]` represents an integer vector with 2 elements

String values must be passed a native JSON string with escaped quotes. The string `"\"InstaMAT\nis\namazing"\""` represents a string with the value:

```
    InstaMAT
    is
    amazing
```

>To change the execution seed value, use the `<Name>` "Seed" with an integer value in the range [0...100000]. {.is-info}
 
 The following command executes the graph `Text` with customized `Seed`, `Rotate`, `Scale`, `HorizontalAlignment` and `Text` parameters:

```
    InstaMATPipeline -mode Execute -graph Text 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.png" -parameter Seed 1005 -parameter Rotate 45.0 -parameter Scale "[ 0.66, 0.66]" -parameter HorizontalAlignment 0 -parameter Text "\"InstaMAT\nis\namazing"\""
```

Enumeration values for parameters such as the `HorizontalAlignment` must be passed as an integer that represents their enumeration index. Here, `0` corresponds to `Left`.

In addition to the modification of graph input parameters, a composition node such as `Levels` can be automatically generated to modify the graph output. This is enabled through the `compositionParameter` argument:

```
    -compositonParameter <CompositionNodeName> <OutputParameter> <InputParameter> <ParameterValue>
```

The command connects the `OutputParameter` of the executed graph into the image input parameter of the graph with the name `CompositionNodeName`. It then sets the `InputParameter` of the composition graph to `<ParameterValue>`. The previous example can be extended as follows to adjust the levels of the output:

```
    InstaMATPipeline -mode Execute -graph Text 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.png" -parameter Rotate 45.0 -parameter Scale "[ 0.66, 0.66]" -parameter HorizontalAlignment 0 -parameter Text "\"InstaMAT\nis\namazing"\"" -compositionParameter Levels Output "Luminance In" "[ 0.0 0.6 0.8 ]"
```

<a name="executing-a-graph-as-grayscale"></a>
### Executing a Graph as Grayscale

Certain graphs can be executed as colored or as a grayscale version and are called permutable. By default, InstaMAT Pipeline executes the colored version of a graph. To execute, the grayscale version, the argument `-grayscale` can be used. If the argument is specified for a graph that is not grayscale permutable, the graph is executed normally. The following command executes the grayscale permutation of the graph `Blue Noise`:

```
    InstaMATPipeline -mode Execute "Environment/Packages/noise/BlueNoise.MAT" -graph "Blue Noise" 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.png" -grayscale
```

<a name="filesystem-images-and-resources"></a>
### Filesystem Images and Resources

When executing a graph, resources can be loaded from disk and used as input parameters. Below, the previous example is further extended by loading a `Font` and a `Background` image from the `C:/` drive. Filepaths must be prefixed with the `file://` identifier so that InstaMAT can locate them on the local file system.

```
    InstaMATPipeline -mode Execute -graph Text 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.png" -parameter Rotate 45.0 -parameter Scale "[ 0.66, 0.66]" -parameter HorizontalAlignment 0 -parameter Text "\"InstaMAT\nis\namazing\"" -compositionParameter Levels Output "Luminance In" "[ 0.0 0.6 0.8 ]" -parameter Background "file://C:/Image.png" -parameter Font "file://C:/Font.ttf"
```

<a name="filtering-outputs"></a>
### Filtering Outputs

To avoid generating all graph outputs when only a few are required, output filtering can be used during graph execution. This can be done by appending the `-outputFilter <FilterPattern>` argument with the file pattern. Multiple filters can be separated by a semicolon. The command below loads a high poly mesh from the path `C:/SM_Game_MilitaryCrate_1mio.fbx` and bakes it onto the low poly mesh under the path `C:/SM_Game_MilitaryCrate_Target.fbx`.

```
    InstaMATPipeline -mode Execute -graph Bake 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.png" -parameter "Source Mesh" "file://C:/SM_Game_MilitaryCrate_1mio.fbx" -parameter "Target Mesh" "file://C:/SM_Game_MilitaryCrate_Target.fbx" -outputFilter "Tangent*;Ambient*"
```

The filter pattern instructs InstaMATPipeline to generate outputs that start with `Tangent` or `Ambient`. Only the `Tangent Space Normal` and `Ambient Occlusion` maps are generated while all outputs that do not match any of the filters are ignored.

> The output filter is applied to all graph outputs including both image and mesh outputs.{.is-info}

<a name="outputting-meshes"></a>
### Outputting Meshes

When executing Element Graphs that have an Element Mesh output, InstaMAT Pipeline can output mesh files. By default, the application outputs FBX files, but the file format can also be configured with the `-outputMeshFormat ` parameter followed by a file extension. Currently supported formats are FBX, OBJ and ILME (InstaLOD Mesh). The following command executes the UV Unwrap Graph and outputs the resulting mesh as an OBJ file.

```
    InstaMATPipeline -mode Execute -graph "Mesh UV Unwrap" 1024 1024 Normalized8 "Export/{GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.png" -parameter Mesh "file://C:/SM_Game_MilitaryCrate_Target.fbx" -outputMeshFormat .obj
```

<a name="format-strings-with-InstaMAT-script-variables"></a>
### Configuring Outputs with InstaMAT Variables

Format strings can be formatted using built-in InstaMAT Variables to configure the output textures. The format string determines the output directory, the file naming scheme and the file extension of the texture files.

Both relative and absolute file paths are supported. The following example executes the graph `Gradient Radial` which has a single output only and writes it to an absolute path:

```
    InstaMATPipeline -mode Execute -graph "Gradient Radial" 1024 1024 Normalized8 "C:/Textures/Radial Gradient.png"
```

The next example uses a relative path to write the texture into the directory `Export/`. If the directory does not exist, InstaMAT Pipeline creates it.

```
    InstaMATPipeline -mode Execute -graph "Gradient Radial" 1024 1024 Normalized8 "Export/Radial Gradient.png"
```

For graphs that have multiple outputs, a format string can be used to ensure a proper naming scheme. The following command executes the graph `Voronoi Fractal Sum`:

```
    InstaMATPipeline -mode Execute -graph "Voronoi Fractal Sum" 2048 2048 Normalized8 "Export/{YEAR}{MONTH}{DAY}{GRAPH.NAME}_{OUTPUT.NAME}_{FORMAT.WIDTH}x{FORMAT.HEIGHT}.png"
```

The format string used here instructs InstaMAT Pipeline to write the current date, the name of the graph, the name of the output, and the resolution of the output into the filename.

Instead of adding information to the filename, a folder structure can also be automatically created with a format string:

```
    InstaMATPipeline -mode Execute -graph "Voronoi Fractal Sum" 2048 2048 Normalized8 "Export/{GRAPH.CATEGORY}/{GRAPH.NAME}/{YEAR}{MONTH}{DAY}{OUTPUT.NAME}_{FORMAT.WIDTH}x{FORMAT.HEIGHT}.png"
```

<a name="InstaMAT-variables"></a>
#### InstaMAT Variables

The following InstaMAT Variables are available.

| Token                     | Description                                                       | Example               |
|---------------------------|-------------------------------------------------------------------|-----------------------|
|`{YEAR}`                   |The current year.                                                  | 2020                  |
|`{MONTH}`                  |The current month.                                                 | 04                    |
|`{DAY}`                    |The current day of the month.                                      | 09                    |
|`{RANDOM}`                 |Generates a random integer number.                                 | 1315341               |
|`{GRAPH.NAME}`             |The name of the graph.                                             | SmoothClouds          |
|`{GRAPH.FRIENDLYNAME}`     |The friendly UI name of the graph.                                 | Smooth Clouds         |
|`{GRAPH.CATEGORY}`         |The category of the graph.                                         | Noise                 |
|`{GRAPH.TYPE}`             |The type of the graph.                                             | Atom                  |
|`{OUTPUT.NAME}`            |The name of the output.                                            | BaseColor             |
|`{OUTPUT.FRIENDLYNAME}`    |The friendly UI name of the output.                                | Base Color            |
|`{OUTPUT.CATEGORY}`        |The category of the output.                                        | Material              |
|`{OUTPUT.TYPE}`            |The type of the output.                                            | ElementImage          |
|`{FORMAT.WIDTH}`           |The width of the output.                                           | 1024                  |
|`{FORMAT.HEIGHT}`          |The height of the output.                                          | 1024                  |
|`{FORMAT.TYPE}`            |The type of the output.                                            | Normalized16          |

The availability and contents of built-in variables are context-sensitive. Output related variables are typically available when exporting outputs. 

> Besides supporting InstaMAT Script variables, format strings can also evaluate platform-specific environment variables. To include an environment variable in a format string, reference the variable by name using the following syntax on all platforms: `${VARIABLE}`. Whenever the string is evaluated by InstaMAT, all environment variables are evaluated as well. {.is-info}

<a name="displaying-graph-object-information"></a>
## Displaying Graph Object Information

Information about a Graph Object can be displayed with InstaMAT Pipeline using the `-mode Info` argument followed by `-graphInfo <Name>`. This can be used to view graphs from the Library or any InstaMAT package. The graph `Text` from the InstaMAT library can be output with the command:

    InstaMATPipeline -mode Info -graphInfo Text

The output has a readable format that could be easily parsed by a web server or another application that integrates InstaMAT.

<a name="search"></a>
## Search

The `Search` mode allows querying information from the library or a package. The argument `-graphSearch` followed by a `<Query>` can be used to find all graphs that match the specified query. Using a `*` as `<Query>` will list all graphs. Additionally, a `<Category>` can be specified to filter for graphs within the category.

The command below searches the library for graphs matching the name `Ambient Occlusion`. The quotes are used because the graph name contains whitespace.

    InstaMATPipeline -mode Search -graphSearch "Ambient Occlusion"

A search for all graphs matching "Blend" in the "Image" category can be performed with the following command:

    InstaMATPipeline -mode Search -graphSearch Blend Image

To query all graphs in the package `Noise`, the following command can be used:

    InstaMATPipeline -mode Search "Environment/Packages/noise/Noise.MAT" -graphSearch *

The search results are output in the the JSON format.

<a name="package-assembly"></a>
## Package Assembly

Package assemblies bundle InstaMAT Atom and Element graphs, resources and meta data into a single package that can be easily shared across workstations. InstaMAT Pipeline enables the automated creation and maintenance of these packages for automated processes that may rely on external data.

<a name="creating-packages"></a>
### Creating Packages

To generate a package, InstaMAT Pipeline needs to be executed in the `Package` mode followed by the package path argument. If a package exists at the specified path, it is loaded. The following example generates a package with the name `TestPackage.MAT` in the directory `C:\Packages`:

    InstaMATPipeline -mode Package "/Packages/TestPackage.MAT"

<a name="adding-resources"></a>
### Adding Resources

Packages can contain a variety of resources such as models, images or fonts that can be used in the execution of InstaMAT Atom and Element graphs.

    InstaMATPipeline -mode Package "/Packages/TestPackage.MAT" -package Resource Add "/Models/CarHood.fbx"

The command above adds the `CarHood.fbx` file to the package `TestPackage.MAT`. Resources can be added, updated and deleted by providing `-package Resource` parameters with the specified modifiers:

  - `Add "<path>"` adds a resource from the specified `<path>` to the package.
  - `Delete "<path>"` deletes a resource under the specified `<path>` to the package.
  - `Update "<path>"` updates or if it doesn't exist adds a resource under the specified `<path>` to the package.

To delete a resource from the package, the `Delete` modifier needs to be applied to the resource:

    InstaMATPipeline -mode Package "/Packages/TestPackage.MAT" -package Resource Delete "/Models/CarHood.fbx"

<a name="modiyfying-package-meta-data"></a>
### Modifying Package Meta Data

Meta data can provide additional information in a package. It follows the `key` - `value` format with a value of any type being storable under a unique key. This command adds two meta data entries:

    InstaMATPipeline -mode Package "/Packages/TestPackage.MAT" -package MetaData Update "Author:InstaMaterial GmbH" -package MetaData Update "BuildDate:%DATE%"

 First, the `Author` is set to `InstaMaterial GmbH` and then the `BuildDate` meta data key is set to the current date of execution. The `%DATE%` variable used here is a Windows-specific system variable that retrieves the current date.

Meta data can be added, updated and deleted through the `-package MetaData` argument with additional parameters to add, delete or update meta entries:

  - `Add "<key:value>"` adds the meta data with the `key` - `value` pair to the package.
  - `Delete "<key:value>"` deletes the meta data with the `key` - `value` pair from the package.
  - `Update "<key:value>"` updates, the meta data with the `key` - `value` pair in the package. If the specified `key` does not exist, a new entry is created.

To delete the `Author` meta data, the modifier needs to be changed to `Delete`: 

    InstaMATPipeline -mode Package "/Packages/TestPackage.MAT" -package MetaData Delete "Author:InstaMaterial GmbH"

<a name="unit-testing"></a>
## Unit Testing

InstaMATPipeline can create fully visualized unit-tests for Element graphs to discover breaking changes in the resulting textures before they get hard to track down. 

The Unit test functionalities are executed in the `UnitTest` application mode:

    InstaMATPipeline -mode UnitTest

<a name="reference-generation"></a>
### Reference Generation

>References are the baseline that all resulting images are tested against. All graphs must produce the intended results before generating the reference images.

The command below generates reference images for all packages in the InstaMAT Pipeline folder:

    InstaMATPipeline -mode UnitTest -env "Environment/" -outputFolder "Reference/"

It is important to specify the environment with `-env <path>` of the packages to be sure that all dependencies are met and the graph execution proceeds without failure. The output images are generated in the Reference folder specified with `-outputFolder <path>`.

<a name="unit-test-execution"></a>
### Unit Test Execution

InstaMAT Pipeline compares on each execution all generated textures with their reference counterparts. The pixel by pixel comparison generates an error value if differences in the compared pixels are present. A test fails if the previously specified amount of pixels contains an error.

    InstaMATPipeline -env "Environment/" -mode UnitTest

The above command executes the test for all packages in the InstaMAT Pipeline folder and environment. Detailed statistics and descriptions of the unit test are logged to the console. 

<a name="result-evaluation"></a>
### Result Evaluation

The results of the unit test can be directly written into an HTML file. InstaMAT Pipeline generates previews of the tests with detailed listings of the test results. 

The command below creates a unit test output in the `UnitTestOutput/` directory:

    InstaMATPipeline -env "Environment/" -mode UnitTest -HTMLOutput "UnitTestOutput/"

Additionally, an HTML template can be provided that is used as the basis for the generated page for customized results:

    InstaMATPipeline -env "Environment/" -mode UnitTest -HTMLOutput "UnitTestOutput/" -HTMLTemplate "Template/InstaMAT.html"

<a name="automatic-documentation-generation"></a>
## Automatic Documentation Generation

InstaMAT Pipeline can automatically generate documentation for all packages. The generated markdown pages give an overview of all necessary information for a graph such as:

  - Graph output previews.
  - Detailed descriptions for graph inputs.
  - Detailed descriptions for graph outputs.
  - Package and graph meta data.

To generate the documentation, execute the following command: 

    InstaMATPipeline -mode GenerateDocumentation -env "Environment/" -outputFolder "Documentation/"

It's important to provide to load the library packages with `-env "<path>"` to make sure that all dependencies are loaded correctly. The optional `-outputFolder "<path>"` is used to specify a custom folder where the documentation is generated.

To keep the documentation tidy, the additional parameter `-excludeCategory <category>` can be used to prevent graphs from the specified category to generate output documents.

<a name="html-transformation"></a>
### HTML Transformation

To view the markdown pages from the web browser, tools such as [MkDocs](https://www.mkdocs.org) can be used.  

<a name="program-arguments"></a>
## Program Arguments
The following arguments can be specified when starting InstaMAT Pipeline.

    -env <Path>
    Loads all packages from <Path> and subdirectories.
    By default, InstaMAT Pipeline will load all packages from the current working directory.
    If InstaMAT Pipeline has been installed to a different location, <Path> should point to the installation directory of InstaMAT.
    Package environments will be loaded in the order queued, dependencies must be loaded first.

    -mode <ApplicationMode> (Path)
    Sets the application mode to one of [Execute, Info, UnitTest, GenerateDocumentation, Cook, Package]
    If the <ApplicationMode> is "Package", then a (Filepath) must be specified to the package.
    If the <ApplicationMode> is [Execute, Info], then a (Filepath) to a package may be specified.
        If no (Filepath) to a package is specified, only Atoms and Elements available in the library can be executed.
        If a package is specified, only Atoms and Elements available in the package can be executed.

    -graph <Name> <OutputWidth> <OutputHeight> <OutputFormat> <OutputPathFormat> [Requires Mode=Execute]
    Selects the Atom or Element graph with the specified <Name> for execution.
    If a package has been specified via the -mode argument.
    <Name> can be an OS file pattern string such as "Aged*" or "*".
        If a file pattern has been specified, the first executable graph that matches
        the pattern will be selected for execution.
    The parameters <OutputWidth> and <OutputHeight> specify the execution size in pixels.
    The <OutputFormat> specify the image format the execution. Must be one of [Normalized8, Normalized16, FullRange16, FullRange32].
    The <OutputPath> specifies the filename and type of the generated images.
    The <OutputPathFormat> supports InstaMAT format strings such as:
        {GRAPH.NAME}_{OUTPUT.TYPE}_{OUTPUT.NAME}.png
        Besides using InstaMAT's built-in variables, the InstaMAT format also supports
        using operating system specific environment variables.
        For more information, please consult the InstaMAT Pipeline documentation.
        Graph input parameters can be configured by appending one or more "-parameter" arguments.
 
    -grayscale [Requires Mode=Execute]
    Attempts to instantiate the graph that is selected for execution as grayscale permutation.
    NOTE: If the graph is not grayscale permutable, the execution will continue without permuting the graph.

    -parameter <Name> <ParameterValue> [Requires Mode=Execute]
    Changes the value of the Atom or Element graph input parameter with the specified <Name> to <ParameterValue>.
    An arithmetic <ParameterValue> is specified in JSON notation.
        Scalar values are passed as native JSON types:
            94.83 represents a float with the value 94.83f
            true represents a boolean true value
        String values must be passed a native JSON string with escaped quotes:
            \"InstaMAT\" represents a string with the value InstaMAT
        Array values are passed as JSON arrays:
            [ 1.0, 2.0, 3.0 ] represents a float vector with 3 elements
            [ 1, 2 ] represents an integer vector with 2 elements
    A file resource <ParameterValue> is specified as a relative or absolute path prefixed with the InstaMAT file protocol "file://"
    NOTE: Quotation marks are required to wrap the JSON or filepath value as a single program argument.
    NOTE: To change the execution seed, use the <Name> "Seed" with an integer values in the range [0...100000].

    -compositionParameter <CompositionNodeName> <OutputParameter> <InputParameter> <ParameterValue> [Requires Mode=Execute]
    Changes the <InputParameter> of the composition node with the <CompositionNodeName> for the specified <OutputParameter> of the execution graph.
    <CompositionNodeName> must be one of [Levels].
    The <InputParameter> must match the name of an input parameter of the composition node.
    The syntax of the <ParameterValue> matches the -parameter argument.

    -outputFilter <FilterPattern> [Requires Mode=Execute]
    Graph outputs that do not match the <FilterPattern> will not be exported to disk.
    The <FilterPattern> can be an OS file pattern string such as "Base*" or "*Normal*".
    Multiple patterns can be specified using a semicolon character ';'.
    By default, all graph outputs will be exported.

    -outputMeshFormat <FileExtension> [Requires Mode=Execute]
    Graph outputs of type ElementMesh will be exported with the specified file extension.
    If the file extension is not specified, the FBX file format will be used.
    <FileExtension> must be one of [.fbx, .obj, .ilme]

    -graphInfo <Name> [Requires Mode=Info]
    Selects the Atom or Element graph with the specified <Name> for info output.

    -package <Context: Resource, MetaData> <Task: Add, Update, Delete> <Value> [Requires Mode=Package]
    Queues a package operation. Package operations will be processed in the order they were queued.
    <Context> must be one of [Resource, MetaData].
        Resource: modifies package contents.
        MetaData: modifies package meta data.
    <Task> must be one of [Add, Update, Delete]
        Add: Adds a file or meta data entry.
        Update: Updates a file or meta data entry.
        Delete: Deletes a file or meta data entry.
    If <Context> is "Resource"
        <Value> must be a valid filepath.
    If <Context> is "MetaData"
        <Value> must be a key-value pair in the form <Key>:<Value>

    -outputFolder <Path> [Requires Mode=UnitTest, GenerateDocumentation, Cook]
    Sets the output folder for the generated content.

    -referenceFolder <Path> [Requires Mode=UnitTest]
    Sets the output folder for the reference images

    -mismatchFolder <Path> [Requires Mode=UnitTest]
    Sets the output folder for the mismatch images

    -HTMLOutput <Path> [Requires Mode=UnitTest]
    Sets the HTML output folder for the generated HTML report.

    -HTMLTemplate <TemplatePath> [Requires Mode=UnitTest and HTMLOutput]
    Sets the HTML template used for the generated HTML report

    -validateDocs [Requires Mode=UnitTest]
    Performs validation on inputs and graphs to ensure documentation is available.

    -category <Category> [Requires Mode=UnitTest, GenerateDocumentation]
    Adds the specified <Category> to the list of included categories.
    Multiple categories can be added by specifying the -category parameter multiple times.
    If the <Mode> is "GenerateDocumentation" and no category is specified, all categories will be output unless manually excluded.

    -excludeCategory <Category> [Requires Mode=GenerateDocumentation]
    Adds the specified <Category> to the list of excluded categories.
    Multiple categories can be added by specifying the -excludeCategory parameter multiple times.

    -imageFolderBaseURL <URL> [Requires Mode=GenerateDocumentation]
    Sets the base URL for the generated images. Default is "\".

    -authorize <Email> <LicenseKey>
    Authorizes this machine for use with InstaMAT Pipeline.
    NOTE: Please deauthorize your computer before uninstalling to avoid a locked seat.

    -deauthorize <Email> <LicenseKey>
    Deauthorizes this machine.
    NOTE: Deauthorization takes 24 hours to complete.

    -machineKey
    Retrieves the machine-specific authorization key.

    -authorizeKey <MachineKey> <Filename> <Email> <LicenseKey>
    Authorizes the machine with the <MachineKey> using <Email> and <LicenseKey> and writes the licensing file to <Filename>.
    This method is used to fulfill a license request on behalf of another machine.

    -ingestLicense <Path>
    Authorizes this machine using the license file at the specified <Path>.

    -licenseInfo
    Displays licensing information.

<a name="available-importexport-file-formats"></a>
## Available import/export image file formats
The following file formats can be imported and exported by InstaMAT.

- PNG (8bit and 16bit)
- TIFF
- TGA (8bit)
- BMP (8bit)
- EXR (16bit and 32bit)
- HDR (32bit)
- JPEG (import only)
- PSD (limited import only)

<a name="third-party-components"></a>
## Third Party Components
For information on additional third-party components licensed by InstaMAT, the InstaMAT SDK or InstaMAT Pipeline visit http://www.InstaMaterial.com/FOSS.

<a name="website"></a>
## Website
Please visit http://www.InstaMaterial.com to stay up to date!

Thank you for using InstaMAT.