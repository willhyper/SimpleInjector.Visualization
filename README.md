# SimpleInjector.Visualization

Visualize dependency tree configured in SimpleInjector DI container.

### Usage example

``` cs
// 1. Initialize the DI container and do the registrations
Container container = ...; 

// 2. Pick the root type
Type rootType = typeof(MyRootClass);

// 3. Build the collection of relations
var dependencies = Visualizer.BuildGraph(container, rootType);

// 4. Convert to Graphviz
var graphviz = dependencies.ToGraphViz();

// Copy-paste to a visualization tool (e.g. 
[webgraphviz.com](http://webgraphviz.com))
```

### Result example

![Dependency Graph](http://mikhail.io/2017/03/visualizing-dependency-tree-from-di-container/class-dependency-graph.png)

### The fork

This fork is to migrate Mikhail's repo in net452 to netcoreapp2.2.
The migration is largely done through
```
dotnet tool install --global Project2015To2017.Migrate2017.Tool
dotnet migrate-2017 wizard SimpleInjector.Visualization.sln
```
see https://github.com/hvanbakel/CsprojToVs2017

the last step is to change to <TargetFramework>netcoreapp2.2</TargetFramework>.
You can see the diff from commit history.



### Read more
[Visualizing Dependency Tree from DI Container](http://mikhail.io/2017/03/visualizing-dependency-tree-from-di-container/).
