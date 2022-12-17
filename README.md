# architecture-as-code

## Diagrams

[Diagrams](https://diagrams.mingrammer.com/docs/getting-started/examples) permite que você desenhe a arquitetura do sistema de nuvem no código Python.

```python
from diagrams import Diagram
from diagrams.k8s.clusterconfig import HPA
from diagrams.k8s.compute import Deployment, Pod, ReplicaSet
from diagrams.k8s.network import Ingress, Service

with Diagram("Exposed Pod with 3 Replicas", show=False):
    net = Ingress("domain.com") >> Service("svc")
    net >> [Pod("pod1"),
            Pod("pod2"),
            Pod("pod3")] << ReplicaSet("rs") << Deployment("dp") << HPA("hpa")
```

![image](https://user-images.githubusercontent.com/34652880/208265627-1dcf2334-3fe6-446c-9566-2d31304a2860.png)

## Mermaid

[Mermaid](https://mermaid-js.github.io/mermaid/intro/) permite criar diagramas de fluxo, sequência, Gantt, classe etc. com JavaScript. O legal é que dá pra importar no html via CDN e rodar sem precisar instalar nada.

```html
<script type="module">
    import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@9/dist/mermaid.esm.min.mjs';
    mermaid.initialize({ startOnLoad: true });
</script>

<pre class="mermaid">
sequenceDiagram
    Consumer-->API: Book something
    API-->BookingService: Start booking process
    break when the booking process fails
        API-->Consumer: show failure
    end
    API-->BillingService: Start billing process
</pre>
```

![image](https://user-images.githubusercontent.com/34652880/208265136-7c08e2ed-f726-44dd-8c0f-b5b138e4c9b1.png)

> ### Importante
> Dá pra renderizar diagramas mermaid no próprio markdown do github. É só colocar o bloco de código como sendo da linguagem `mermaid`.

```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```

## Markmap

[Markmap](https://markmap.js.org/repl) permite visualizar arquivos markdown como mapas mentais.

```markdown
---
markmap:
  colorFreezeLevel: 2
---

# markmap

## Links

- <https://markmap.js.org/>
- [GitHub](https://github.com/gera2ld/markmap)

## Related Projects

- [coc-markmap](https://github.com/gera2ld/coc-markmap)
- [gatsby-remark-markmap](https://github.com/gera2ld/gatsby-remark-markmap)

## Features

- links
- **strong** ~~del~~ *italic* ==highlight==
- multiline
  text
- `inline code`
-
    ```js
    console.log('code block');
    ```
- Katex
  - $x = {-b \pm \sqrt{b^2-4ac} \over 2a}$
  - [More Katex Examples](#?d=gist:af76a4c245b302206b16aec503dbe07b:katex.md)
- Now we can wrap very very very very long text based on `maxWidth` option
```

![image](https://user-images.githubusercontent.com/34652880/208265471-a4bb2cd1-e862-4647-9bad-94c898d728cf.png)

> ### Importante
> Dá pra usar no VSCode.

![image](https://user-images.githubusercontent.com/34652880/208265773-4c8ff5c7-897c-4888-bcbe-7211300ea95d.png)


