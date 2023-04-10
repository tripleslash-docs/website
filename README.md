![Logo](img/github-org-logo.png)

# tripleslash.io

# Overview

Thank you for visiting the site! [tripleslash.io](https://tripleslash.io) is home to a package documentation indexing engine. It's like Sandcastle or DocFx for .Net, except it's a 100% online service. Tripleslash can retrieve packages from [nuget](https://www.nuget.org/), scan all the assemblies, and build searchable API documentation for the users of your package.

## Features

- Acquire NuGet packages on-the-fly, scans all the assemblies, and constructs a full set of API documentation.
- *Recursively* builds documentation for all dependencies of the package.
- *Deep-links* all documentation articles across all packages in the dependency tree, and links Microsoft types back to Microsoft's documentation.
- Constructs a package-aware searchable index for namesapces, types, and members.
- Constructs a global search index for all namespaces and types.
- Finds and annotates API and documentation differences in different target framework assemblies and allows site users to filter by framework.
- Allows site users to see API surface area differences between versions and inspect the files in the package.
- Builds package statistics including top type usages, build stats, and documentation completion percentages.
- Supports decompiled source browsing thanks to [ILSpy](https://github.com/icsharpcode/ILSpy)

## Recommendations for developers

Tripleslash is proud to host your package's API documentation. Here are some guidelines for making it work the best for your project:

- Include project metadata in your sdk style `.csproj` file or `.nuspec` (e.g. author, projectSite, iconUrl, etc.). 
- Format your code documentation using Microsoft's [recommended XML tags for C# documentation](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/xmldoc/recommended-tags) guidelines.
- Leverage the following supported Sandcastle features:
    - `NamespaceDoc`
    - `<overloads>`
    - `<permission>`
- Provide code examples!
    ```cs
    <code language="csharp">
    /// code
    </code>
    ```
- Highlight areas of your documentation using tripleslash's `<note>` tag:
    ```cs
    /// <summary>
    /// This is a method
    /// </summary>
    /// <note type="note|tip|caution|warning|important|security">
    /// This is a note, tip, caution, warning, important, or security message.
    /// </note>
    ```        
- Link to Tripleslash from your docs/wiki using the following format:
  ```
  Link to packege overview page (non-version specific):
  https://tripleslash.io/docs/.net/<your-package-id>/@index`

  Link to package overview page (version-specific):
  https://tripleslash.io/docs/.net/<your-package-id>/<your-package-semver>/@index`

  Link to the API overview page:
  https://tripleslash.io/docs/.net/<your-package-id>/<your-package-semver>/api/@index`

  Link to a namespace or type:
  https://tripleslash.io/docs/.net/<your-package-id>/<your-package-semver>/api/<fully-qualified-type-name>
  ```

  Example: https://tripleslash.io/docs/.net/vertical-spectreconsolelogger/0.10.0-dev.20220814.14/@index
- [Report](https://github.com/tripleslash-docs/website/issues/new/choose) bugs or request features
