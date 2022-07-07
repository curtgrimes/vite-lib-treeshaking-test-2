# Vite lib treeshaking test part 2

This project imports from [vite-lib-treeshaking-test-part-1](https://github.com/curtgrimes/vite-lib-treeshaking-test-1), which exports two components:

1. A `MyGrid` component with `ag-grid` as a dependency (used as an example of a large dependency)
2. A `MyFoobarComponent` component that does not import `ag-grid`.

In this project, notice that App.vue does not import the `MyGrid` component from
the `vite-lib-treeshaking-test-1` module and only imports `MyFoobarComponent`.
However, [the build](https://github.com/curtgrimes/vite-lib-treeshaking-test-2/tree/main/dist/assets) contains the ag-grid dependency that is only required by the
`MyGrid` component and is unused in this project.
