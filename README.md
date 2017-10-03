# guf-js
This repository contains the files that are needed for the implementation of the [OGC Geospatial User Feedback (GUF)](https://github.com/joanma747/nimmbus) implementation. Javs script code which provides the GUF implementation to any kind of portal where there is a need of User Feedback.

CKAN extension
=======
In order to add the GUF implementation to datasets in CKAN, the files need to be added to any CKAN extension:

1. place community_feedback.html file in templates/package/snippets/ folder in the CKAN extension

2. place the community_feedback.css and communityfeedback.js files in the public folder of the extension

3. make changes to templates/base file and add the following:
  ```
   <script src="/communityfeedback.js" type="text/javascript"></script>
  ```
   
4. in templates/package/read.html add the following:
   ```
      {% block dataset_feedback %}
        {% snippet "package/snippets/community_feedback.html", pkg=pkg %}
      {% endblock %}
   ```
