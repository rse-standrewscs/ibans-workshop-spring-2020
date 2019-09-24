This is the website for a workshop. It was created using a template
for [GAP days](https://www.gapdays.de/).

It is based on [Jekyll](https://jekyllrb.com/), a static website generator,
and the [hyde](https://github.com/poole/hyde/) template.

If you want to test site on your own machine, first install Jekyll (as
described on its website), then do this:
```
  git clone https://github.com/rse-standrewscs/ibans-workshop-spring-2020.git
  cd ibans-workshop-spring-2020
  jekyll serve -w
```
Now open a browser on http://localhost:4000/ to see a live preview
of the site.

== Steps for new workshop

To create a website for a new workshop, follow roughly the following
steps:

1. Copy the data of the previous workshop into a new repository.
   Add that repository under a suitable name at https://github.com/

2. Edit all relevant files; at the very least do the following:
    - _config.yml: update baseurl to match the name of the repository at github.
    - index.md
    - location.md
    - registration.html
      - the "registration_open" entry at the top can be used to
        enable / disable registration
      - Update the "form_api_token" value at the
        top of the file. See https://getsimpleform.com for more
        information. (Note that notification emails for new
        registrations are sent to a single email address. So I
        recommend setting up an address that can deliver to multiple people.)
      - Also update the "email" field at the top
      - edit the available arrival/departure date options in the form
      - edit the rest of the page suitably
    - _data/participants.yml
      - This contains the list of participants, in [YAML](https://en.wikipedia.org/wiki/YAML)
        format. Basic entries look like this:

            - name: John Doe
              affiliation: University of Nowhere

         Entries can be followed by links, e.g. to slides, other PDFs, etc.

            - name: John Doe
              affiliation: University of Nowhere
              links:
                "slides": http://bit.ly/gap-worksheets2015
                "photo": ../photo/john_doe.jpg


3. Optionally, edit program.tex, run pdflatex on it, and add the resulting
  PDF. Or, if you don't want to use it, just remove both the .tex and .pdf
