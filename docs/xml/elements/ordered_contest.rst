OrderedContest
==============

``OrderedContest`` encapsulates links to the information that comprises a contest and potential
ballot selections. ``OrderedContest`` elements can be collected within a
:doc:`BallotStyle <ballot_style>` to accurate depict exactly what will show up on a particular
ballot in the proper order.

+--------------------------+------------+------------+----------+---------------------------+---------------------------------+
| Tag                      | Data Type  | Required?  | Repeats? |Description                |Error Handling                   |
|                          |            |            |          |                           |                                 |
+==========================+============+============+==========+===========================+=================================+
| ContestId                | xs:IDREF   |**Required**| Single   |Links to elements that     |If the field is invalid or not   |
|                          |            |            |          |extend :doc:`ContestBase   |present, the implementation is   |
|                          |            |            |          |<contest_base>`.           |required to ignore the           |
|                          |            |            |          |                           |``OrderedContest`` element       |
|                          |            |            |          |                           |containing it.                   |
|                          |            |            |          |                           |                                 |
|                          |            |            |          |                           |                                 |
|                          |            |            |          |                           |                                 |
|                          |            |            |          |                           |                                 |
+--------------------------+------------+------------+----------+---------------------------+---------------------------------+
| OrderedBallotSelectionId | xs:IDREF   | Optional   | Repeats  |Links to elements that     |If the field is invalid or not   |
|                          |            |            |          |extend                     |present, the implementation is   |
|                          |            |            |          |:doc:`BallotSelectionBase  |required to ignore it. If no     |
|                          |            |            |          |<ballot_selection_base>`.  |``OrderedBallotSelectionId``     |
|                          |            |            |          |                           |elements are present, the        |
|                          |            |            |          |                           |presumed order of the selection  |
|                          |            |            |          |                           |will be the order of             |
|                          |            |            |          |                           |:doc:`BallotSelectionBase        |
|                          |            |            |          |                           |<ballot_selection_base>`-extended|
|                          |            |            |          |                           |elements referenced by the       |
|                          |            |            |          |                           |underlying :doc:`ContestBase     |
|                          |            |            |          |                           |<contest_base>`-extended         |
|                          |            |            |          |                           |elements.                        |
+--------------------------+------------+------------+----------+---------------------------+---------------------------------+

.. code-block:: xml
   :linenos:

   <OrderedContest id="oc20003abc">

      <ContestId>cc20003</ContestId>
      <OrderedBallotSelectionId>cs10961</OrderedBallotSelectionId>
      <OrderedBallotSelectionId>cs10962</OrderedBallotSelectionId>
      <OrderedBallotSelectionId>cs10963</OrderedBallotSelectionId>
   </OrderedContest>
