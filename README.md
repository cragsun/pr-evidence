# pr-evidence

Cubo de imágenes de las PRs de **cragser.dev**. No hay código aquí: solo
capturas.

## Por qué existe

`cragsun/cragser.dev` es privado. GitHub sirve las imágenes del cuerpo de un
issue o un PR a través de camo, que las pide **sin autenticar**, así que
cualquier URL de un repo privado (`raw.githubusercontent.com`, un asset de
release, un gist ligado) se ve rota. Para que la sección «Imágenes» de una PR
enseñe algo, el fichero tiene que estar en un sitio público. Este repo es ese
sitio.

## Qué se sube, y qué no

Solo capturas de proyectos **`scope:public`** (blog, tracker, skills, los
Storybook), tomadas contra el build local. Las apps `scope:private`
(skill-manager, skill-practice) pintan el dossier personal del dueño y **no se
capturan aquí**: su PR enlaza el artifact y declara la exención.

## Cómo se organiza

```
cragser.dev/<año>/<rama>/<sha-del-commit>/<pantalla>.png
```

La ruta lleva el SHA del commit que se capturó, así que un fichero **nunca se
reescribe**: cada publicación añade, no pisa. Los enlaces de PRs viejas siguen
funcionando para siempre. Nada de `--force`, `amend` ni reescritura de
historia.

Lo sube `tools/pr-shots.mjs` del repo de la plataforma, y la regla que lo
gobierna es `docs/rules/workflow/pull-requests.md`.
