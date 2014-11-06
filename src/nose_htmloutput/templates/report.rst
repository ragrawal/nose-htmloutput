Test Summary
=====================

.. csv-table::
   :header: "Class", "Fail", "Skip", "Success", "Total"
   :widths: 50, 10, 10, 10, 10

   {% for class, group in report.items() %}
   :ref:`{{class}} <{{class}}>`, {{group.stats.failures}},{{group.stats.skipped}},{{group.stats.passes}},{{group.stats.total}}
   {% endfor %}
   **Total**, {{stats.failures}},{{stats.skipped}},{{stats.passes}},{{stats.total}}


Test Details
======================
{% for class, group in report.items() %}
.. _{{class}}:

{{class}} ({{ group.stats.failures }} failures, {{ group.stats.errors }} errors)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
{% for test in group.tests %}
	- {{test.name}}: {{ test.status }}
{% endfor %}

{% endfor %}
