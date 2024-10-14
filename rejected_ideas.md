## Rejected extension ideas

These are some ideas for the extensions that were considered and rejected or
removed:

 * At an earlier point of development we included a directive to set the
   default axis unit, which provided the option of not adding an axis unit to
   some positions. Early feedback suggested that this could lead to confusing
   results. It was also felt that potential worries over having to type out
   units "over and over" were already addressed by the named location
   mechanism.

 * At earlier stages of implementation we expected to include both the
   "centralized" syntax for variable values of the current specification and a
   "distributed" syntax that allowed values to be specified per-master (similar
   to the current "merging" system). We explored that path thoroughly but
   ultimately abandoned it for two main reasons. The first was that we felt it
   would be time-consuming to implement, and the feature file syntax should not
   be so hard to adopt.  The second reason was that the rules for matching up
   entries became quite complex once any differences in rule sequences—due to,
   for example, a sparse master—were allowed.

   We also felt that the system would most likely be used for large files
   generated from other sources such as UFO kerning data, and in those cases
   the "matching problem" was easier to solve in the script that processes that
   data.
