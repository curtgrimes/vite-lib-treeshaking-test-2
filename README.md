# Vite lib treeshaking test part 2

This project imports from [vite-lib-treeshaking-test-part-1](https://github.com/curtgrimes/vite-lib-treeshaking-test-1), which exports two components:

1. A `MyGrid` component with `ag-grid` as a dependency (used as an example of a large dependency)
2. A `MyFoobarComponent` component that does not import `ag-grid`.

In this project, notice that App.vue does not import the `MyGrid` component from
the `vite-lib-treeshaking-test-1` module and only imports `MyFoobarComponent`.
However, [the build](https://github.com/curtgrimes/vite-lib-treeshaking-test-2/tree/main/dist/assets) contains the ag-grid dependency that is only required by the
`MyGrid` component and is unused in this project.

[#8464](https://github.com/vitejs/vite/issues/8464) in the Vite project talks about a tree shaking issue that might be related to this. OP in that issue says that Vite v2.9.9 does not have the particular tree shaking problem that issue is about, so I tried both the latest prerelease of Vite in this main branch and also [vite@2.9.9 in this branch](https://github.com/curtgrimes/vite-lib-treeshaking-test-2/tree/with-vite-2.9.9), but I still experience the issue in both versions. I have also experienced the same issue in the latest stable version of Vite.
