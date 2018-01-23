..  Copyright (C)  Jaclyn Cohen.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Lab Exercise: Conditionals and Dictionary Mechanics
===================================================

.. activecode:: labex03

    **Your challenge:**

    Given this dictionary of United States state/commonwealth/area names (keys) and their populations (associated values),

    Write code that allows a user to enter a string of area names separated by commas (e.g. ``Michigan, California, Wyoming``) and ultimately print out the **total population of all of those entered states/areas whose individual populations are LESS than 5,000,000** (5 million). So for that example, the printed result should be *only the population of Wyoming* (both MI and CA have populations greater than 5 million)!

    See class handout for more detail. There are no tests for this activecode box. Check your code by trying examples where you know the correct answer!
    ~~~~
    # Dictionary provided here with names and populations
    states = { "California" : 39536653, "Texas" : 28304596, "Florida" : 20984400, "New York" : 19849399, "Pennsylvania" : 12805537, "Illinois" : 12802023, "Ohio" : 11658609, "Georgia" : 10429379, "North Carolina" : 10273419, "Michigan" : 9962311, "New Jersey" : 9005644, "Virginia" : 8470020, "Washington" : 7405743, "Arizona" : 7016270, "Massachusetts" : 6859819, "Tennessee" : 6715984 , "Indiana" : 6666818, "Missouri" : 6113532, "Maryland" : 6052177, "Wisconsin" : 5795483, "Colorado" : 5607154, "Minnesota" : 5576606, "South Carolina" : 5024369, "Alabama" : 4874747, "Louisiana" : 4684333, "Kentucky" : 4454189, "Oregon" : 4142776, "Oklahoma" : 3930864, "Connecticut" : 3588184, "Puerto Rico" : 3337177, "Iowa" : 3145711, "Utah" : 3101833, "Arkansas" : 3004279, "Nevada" : 2998039, "Mississippi" : 2984100, "Kansas" : 2913123, "New Mexico" : 2088070, "Nebraska" : 1920076, "West Virginia" : 1815857, "Idaho" : 1716943, "Hawaii" : 1427538, "New Hampshire" : 1342795, "Maine" : 1335907, "Rhode Island" : 1059639, "Montana" : 1050493, "Delaware" : 961939, "South Dakota" : 869666, "North Dakota" : 755393, "Alaska" : 739795, "District of Columbia" : 693972, "Vermont" : 623657, "Wyoming" : 579315, "Guam" : 167358, "U.S. Virgin Islands" : 107268, "American Samoa" : 51504, "Northern Mariana Islands" : 52263, "Midway Atoll" : 40, "Johnston Atoll" : 0, "Wake Island" : 150, "Palmyra Atoll" : 20}

    # Write the remainder of your code here...
