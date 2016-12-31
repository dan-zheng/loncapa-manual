LON-CAPA
========

LON-CAPA is an open source web-based course management system created by Michigan State University. It helps to organize and present course websites, deliver and grade assignments, and manage student enrollment, assessment, and grading. (superscript)

Assignments in LON-CAPA are called problems. A problem consists of various resources, such as HTML for displaying text, CSS for styling the text, and Perl for adding functionality. This manual specifically focuses on creating resources for problems in LON-CAPA.

## Authoring Space

The Authoring Space is the environment in LON-CAPA where course resources are created and updated. Creating content involves both *authoring* the resource during editing, and then *publishing* the resource to make it available for use in courses.

Authoring Spaces have a directory structure. The interface is straightforward and intuitive: you can explore the various menus to see what actions are possible.

## Authoring Problems

To create a new problem, use the **Create a new directory or LON-CAPA document** menu and select **New Problem**. LON-CAPA provides sample problem templates which are highly recommended for beginners. They features different response types, which are explained later. Alternatively, one can create a blank problem and write from scratch.

Once you have make a selection, the problem will be displayed in testing mode. You can edit the problem by clicking the **Edit** button to open the colorful editor, or by clicking the **Edit XML** button to edit the raw problem XML.

This manual focuses on editing problems using XML.

- [Problem Structure](problem-structure.md)
- [Response Types](response-types.md)
- [HTML/CSS](html-css.md)
- [LaTeX](latex.md)
