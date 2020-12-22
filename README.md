# K8s JsonPath

This repo contains sample **jsonpath** code related to **Kubernetes**.

# JSONPath Syntax

| JSONPath           | Description                                                          |
| ------------------ | -------------------------------------------------------------------- |
| `$`                | The root object/element                                              |
| `@`                | The current object/element                                           |
| `.` or `[]`        | Child member operator                                                |
| `..`               | Recursive descendant operator; JSONPath borrows this syntax from E4X |
| `*`                | Wildcard matching all objects/elements regardless their names        |
| `[]`               | Subscript operator                                                   |
| `[,]`              | Union operator for alternate names or array indices as a set         |
| `[start:end:step]` | Array slice operator borrowed from ES4 / Python                      |
| `?()`              | Applies a filter (script) expression via static evaluation           |
| `()`               | Script expression via static evaluation                              |

## Index

1. [Nodes](/nodes)
2. [Pods](/pods)

## About Us

k8s-jsonpath is maintained by:

<table>
  <tr>
    <td align="center"><a href="https://www.linkedin.com/in/hganguly/"><img src="https://avatars0.githubusercontent.com/u/5839433?s=88&u=6ed858dba3762eb0d929b48649b787ac9db112b7&v=4" width="100px;" alt="himadriganguly"/><br /><sub><b>Himadri Ganguly</b></sub></a><br /><a href="https://github.com/himadriganguly" title="Code">:octocat:</a> <a href="https://twitter.com/himadritech" title="Twitter">:bird:</a></td>
  </tr>
</table>

## Contributing

Please see our [CONTRIBUTING.md](/CONTRIBUTING.md).

## LICENSE

**k8s-jsonpath** is **GNU GPL3** licensed. See the LICENSE file for details.
