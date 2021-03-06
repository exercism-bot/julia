# How to implement a Julia concept exercise

This document describes how to implement a concept exercise for the Julia track.

**Please please please read the docs before starting.** Posting PRs without reading these docs will be a lot more frustrating for you during the review cycle, and exhaust Exercism's maintainers' time. So, before diving into the implementation, please read the following documents:

- [The features of v3][docs-features-of-v3].
- [Rationale for v3][docs-rationale-for-v3].
- [What are concept exercise and how they are structured?][docs-concept-exercises]

Please also watch the following video:

- [The Anatomy of a Concept Exercise][anatomy-of-a-concept-exercise].

As this document is generic, the following placeholders are used:

- `$slug`: the slug of the exercise in kebab-case (e.g. `calculator-conundrum`).
- `$concept_slug`: the slug of one of the exercise's concepts in kebab-case (e.g. `multiple-dispatch`).

Before implementing the exercise, please make sure you have a good understanding of what the exercise should be teaching (and what not). This information can be found in the exercise's GitHub issue. Having done this, please read the [Julia concept exercises introduction][concept-exercises].

To implement a concept exercise, the following files must be added:

```
languages
└── julia
    ├── runtests.jl
    ├── concepts
    |   └── $concept_slug
    |       ├── about.md
    |       └── links.json
    └── exercises
        └── concept
            └── $slug
                ├── .docs
                |   ├── instructions.md
                |   ├── introduction.md
                |   ├── hints.md
                |   └── source.md (required if there are third-party sources)
                ├── .meta
                |   |── config.json
                |   |── design.md
                |   └── exemplar.jl
                ├── $slug.jl
                ├── runtests.jl
                ├── Project.toml (optional)
                └── Manifest.toml (optional)
```

## Step 1: Add code files

The code files are track-specific and should be designed to help the student learn the exercise's concepts. The following Julia code files must be added (not necessarily in this order):

- `$slug.jl`: the stub implementation file, which is the starting point for students to work on the exercise.
- `runtests.jl`: the test suite.
- `.meta/exemplar.jl`: an exemplar implementation that passes all the tests.
- Project.toml (optional): if dependencies are required, provide this file for a reproducible environment.
- Manifest.toml (optional): if dependencies are required, provide this file for a reproducible environment.

Run `julia color=yes runtests.jl $slug` in the `/languages/julia/` directory to test the example solution.

## Step 2: Add documentation files

How to create the files common to all tracks is described in the [how to implement a concept exercise document][how-to-implement-a-concept-exercise].

## Inspiration

When implementing an exercise, it can be very useful to look at already implemented Julia exercises like the [multiple-dispatch][concept-exercise-multiple-dispatch] exercise. You can also check the exercise's [general concepts documents][reference] to see if other languages have already implemented an exercise for that concept.

## Help

If you have any questions regarding implementing the exercise, please post them as comments in the exercise's GitHub issue.

[concept-exercises]: ../exercises/concept/README.md
[how-to-implement-a-concept-exercise]: https://github.com/exercism/v3/blob/main/docs/maintainers/generic-how-to-implement-a-concept-exercise.md
[docs-concept-exercises]: https://github.com/exercism/v3/blob/main/docs/concept-exercises.md
[docs-rationale-for-v3]: https://github.com/exercism/v3/blob/main/docs/rationale-for-v3.md
[docs-features-of-v3]: https://github.com/exercism/v3/blob/main/docs/features-of-v3.md
[anatomy-of-a-concept-exercise]: https://www.youtube.com/watch?v=gkbBqd7hPrA
[concept-exercise-strings]: ../exercises/concept/encounters
