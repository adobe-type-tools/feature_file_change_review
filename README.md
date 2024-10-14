# OpenType Feature File Specification Additions for Variable Values: Public Review

The Adobe Type Team has been working to extend the OpenType Feature File
Specification to add direct support for variable fonts. These additions will
provide a new workflow in which a single feature file can be applied to an
already-variable "base" font, producing a full OpenType font with layout
features (and other additional tables). Compared with the currently predominant
"merging" workflow, this new syntax makes it easier to reference designspace
locations in kerning or other values that are not associated with a given
master, eliminates the ambiguity of 0 values in a master font, and provides
other advantages.

We are introducing these specification changes in two stages:

 * Stage 1, which is now ready for public review, adds support for variable
   values.
 * Stage 2, which should be ready in the first half of 2025, will add support
   for feature variations (such as swapping one glyph for another based on axis
   range conditions).

Supporting these changes in our AFDKO toolset has required an extensive
modernization of much of its lower-level implementation, which is one reason
this project has taken longer than expected. However, the feature file syntax
is also used in many tools not built or provided by Adobe. We have no control
over whether our proposals are adopted by other toolsets, of course, but we
have tried to take the wider needs of the font development community into
account in developing these extensions. It is our hope that feature files will
continue to be more or less portable between different font development
toolchains. 

This specification review provides an opportunity for the Adobe type team to
answer questions about our choices, and if necessary to make adjustments to the
specification so that it is adopted as widely as possible.

Adobe is now accepting comments on the stage 1 work via this GitHub repository.
Start a [Discussion](https://github.com/adobe-type-tools/feature_file_change_review/discussions)
about whatever you would like to clarify, or add an
[Issue](https://github.com/adobe-type-tools/feature_file_change_review/issues) to raise the
possibility of adding to or changing the specification. (As always, it is
good practice to look through the lists of existing discussions and
issues to avoid duplication.)

The review period for stage 1 ends on January 15th 2025. 

The documentation provided includes:

 * A [style guide](https://adobe-type-tools.github.io/feature_file_change_review/Variable_Feature_Style_Guide).
   (This is probably the best place to start.)
 * A [revised specification](https://adobe-type-tools.github.io/feature_file_change_review/OpenTypeFeatureFileSpecification_diff.html) marked
   with the differences from the previous version.
 * An annotated ANTLR 4 format [grammar](https://adobe-type-tools.github.io/feature_file_change_review/Grammar_Diff.html).
 * A short list of [ideas that were rejected](https://adobe-type-tools.github.io/feature_file_change_review/rejected_ideas).

In addition to this documentation we are providing an [example
repository](https://github.com/adobe-fonts/vffirst-source-serif) with
the sources for the Source Serif 4 Variable roman font reorganized to use the
new workflow.  It explains how to install a beta version of AFDKO that builds
these sources, and how the feature files can be modified to experiment with
additional aspects of the grammar. (Note that this beta version of our toolset
is only partially tested and should not be used to attempt to build
production-quality fonts.)

## Who should review?

Anyone is free to comment on and ask questions about the changes to the
specification, but here is some guidance on whether and how you might want to
participate:

 * If you are only vaguely familiar with feature files, perhaps because you use
   a font editor that produces and compiles them for you "under the hood", you
   can probably trust that the developer of your editor will be reviewing these
   changes on your behalf.
 * If you author your own feature files but your use of them is fairly routine,
   you might read through the style guide to understand the new functionality,
   and reference parts of the revised specification if you have further
   questions.
 * If you make or have made extensive use of feature files to create fonts with
   unusual layout features or other characteristics, we recommend reviewing the
   style guide and specification to judge if you will be able to do what you
   need to and if there are aspects of the process that might be improved.
 * If you develop a tool that creates, processes, or consumes feature files, we
   recommend reviewing the proposed changes—including the ANTLR grammar—with an
   eye toward adopting the extended grammar in the future, and perhaps to
   engage with your community of users about it. If there are obstacles to that
   adoption, please raise them in issues or discussions in the review
   repository and we will try to work with you.

## A note about the scope and role of feature files in font development   

In reading the proposals you will notice that there is more than one way of
specifying a variable metric or anchor, and several optional features such as
named designspace locations. This flexibility is intentional, and reflects the
role of feature files as a "fallback" mechanism for less common layout needs
that may not be supported by an interactive font development system. The goal
of the specification has been, and continues to be, to provide almost all of
the functionality of the OpenType shaping tables in a form that can be authored
and reviewed by font designers and engineers.
