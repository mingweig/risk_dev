# Beneficient Risk Developer Coding Test #
This repo contains a coding test for potential risk developers.
We do not expect you to know [Dash](https://dash.plotly.com/) but expect you to be able to 
quickly learn whatever you need in order to finish the project through online resources yourself. 
Please feel free to add any comments in the code. After you are done, please zip the project folder and email the zip file 
to your recruiter who will send to us.

### How do I get set up? ###
1. Create a clean python environment with whatever environment manager you prefer (virtualenv, conda, etc.)
2. Activate environment created in step 1 
3. Execute ``pip install dash pandas`` to install dash and pandas
4. Launch app by running ``python app.py``

### Tasks for Candidate to Perform ###
The following tasks should be completed by the candidate in their preferred order:

* Complete the ``Observation.delete_matching`` method in cpi.py which contains detailed instructions.
* When the "Delete Matching Observations" button is clicked, the ``Observation.delete_matching`` method is called and 
  the database table, front-end table, and front-end graph are updated accordingly.
* When the "Graph Type" drop-down is set to "Item Price Over Time", multiple observations for the 
  same item that have the same price causes the point size to scale proportionately to the number of matching
  observations
* Implement the "Average Item Price by City" graph type so that when it is selected, it changes the graph to a grouped 
  bar graph where the height of a bar is the average price of an item in a city for the date in the "Date"
  field. The bars should be grouped together by item type and the color of each bar should correspond to the city that 
  the average item price applies to. [Example of a grouped bar graph](https://chartio.com/assets/24e451/tutorials/charts/grouped-bar-charts/c1fde6017511bbef7ba9bb245a113c07f8ff32173a7c0d742a4e1eac1930a3c5/grouped-bar-example-1.png)

### Bonus Tasks ###
* Please feel free to add any enhancements to the code that will make it production-level quality including:
  - Improving the layout, look, and feel of the app
  - Add data validations which make sense for the business logic
  - Improve the data formatting for cleanliness and to be inline with American business conventions
  - You are encouraged to refactor existing code if doing so will improve readability, extendability, performance, etc.
  - Add tests to verify the behavior and impact of code changes
* Any enhancements that you have added should be documented in the README.md section below called ``Enhancements``

### Grading Criteria ###
* Completion of the tasks specified and the bonus tasks
* Maintainability and readability of code written
* Thoughtful comments and descriptive variable names
* Code execution performance (there should be no noticeable delay to the user when changing graphs or deleting points)

### Who do I talk to? ###
* recruiting@beneficient.com

### Enhancements ###

1. **User Feedback with Alert Messages:**
   - Integrated `dash_bootstrap_components` to incorporate `dbc.Alert` components, providing immediate and clear feedback to users upon successful or failed operations such as saving or deleting observations.

2. **Robust Error Handling and Logging:**
   - Implemented try-except in callbacks to gracefully handle exceptions. Errors are logged using Python's `logging` module, for easier debugging and maintenance.

3. **Input Validation:**
   - Added `type='number'` to numerical input fields (`price-input` and `delete-n-observations`) to enforce correct data types and prevent invalid entries.

4. **Database / DataTable Configuration:**
   - Added `'ID'` column to make it easier to maintain data integrity,
   - Explicitly defined columns in the `dash_table.DataTable`, including hiding sensitive columns like `'ID'`. Implemented pagination and styling for improved readability and performance.

5. **Optimized Date Handling:**
   - Ensured consistent `datetime` formats for both the dataframe and user inputs. 
   - Implemented optional date filtering in the "Average Item Price by City" graph to allow users to view data for specific dates for `Average Item Price by City`

6. **Modular Code Structure:**
   - Organized code into clear, logical sections with comments for description, for easier maintenance and scalability.

7. **Graph Configuration for Enhanced Readability:**
   - Configured graphs with descriptive axis titles, legend titles, and hover data to make data insights more accessible and understandable. 

8. **Rounding Prices to Two Decimal Places:**
   - Ensured all price values are consistently displayed with two decimal places by implementing rounding during data generation and processing to enhances data consistency and readability, aligning with standard financial reporting practices.


