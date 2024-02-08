# .NET 5 Quality Assurance coding rules and best practices
An opinionated set of files and configurations usefull to enforce coding best practices and uniformity in .NET 5 projects

# Usage
Just copy all the files into the root of your target solution and/or related subfolders as needed (if and when an override/extension is required).

If your root already contains one or more of these file, you will need to merge them manually.


# Root folder
This folder represents the root directory containing all the projects of the solution, and contains the following files:

- **Directory.Build.props** → This is the backbone gluing together the other configuration files. It defines the basic NuGet dependencies (and the related configuration files) applied to all the projects in the root folder and its subfolders. 
- **.editorconfig** → Define an opinionated set of global rules applied to the editor and enforced into the build process via the Roslyn Analyzers referenced by _Directory.Build.props_:
  - **Lindhart.Analyser.MissingAwaitWarning** → [NuGet](https://www.nuget.org/packages/Lindhart.Analyser.MissingAwaitWarning/) / [GitHub](https://github.com/ykoksen/unused-task-warning)
  - **Microsoft.CodeAnalysis.FxCopAnalyzers** → [NuGet](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/) / [GitHub](https://github.com/dotnet/roslyn-analyzers)
  - **Microsoft.VisualStudio.Threading.Analyzers** → [NuGet](https://www.nuget.org/packages/Microsoft.VisualStudio.Threading.Analyzers/) / [GitHub](https://github.com/Microsoft/vs-threading)
  - **Philips.CodeAnalysis.DuplicateCodeAnalyzer** → [NuGet](https://www.nuget.org/packages/Philips.CodeAnalysis.DuplicateCodeAnalyzer/) / [GitHub](https://github.com/philips-software/roslyn-analyzers). This analyzer is also parametrized using the _DuplicateCode.Allowed.txt_ file
- **Global.ruleset** → define the code styling rules enforced by StyleCop and its _StyleCop.Analyzers_ NuGet package ([NuGet](https://www.nuget.org/packages/StyleCop.Analyzers/) / [GitHub](https://github.com/DotNetAnalyzers/StyleCopAnalyzers))
- **BannedSymbols.txt** → the configuration file used by the Roslyn Analyzer _Microsoft.CodeAnalysis.BannedApiAnalyzers_ ([NuGet](https://www.nuget.org/packages/Microsoft.CodeAnalysis.BannedApiAnalyzers/) / [GitHub](https://github.com/dotnet/roslyn-analyzers))
- **DuplicateCode.Allowed.txt** → the file containing the exceptions allowed by the _Philips.CodeAnalysis.DuplicateCodeAnalyzer_ ([NuGet](https://www.nuget.org/packages/Philips.CodeAnalysis.DuplicateCodeAnalyzer/) / [GitHub](https://github.com/philips-software/roslyn-analyzers))
- **RiderInspectionSettings.xml** → the configuration file used by [JetBrains Rider](https://www.jetbrains.com/rider/) for the editor inspections
