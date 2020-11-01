# FixedLengthFileProcess-ADF

# Input File

1000SENTHILKUMARTN626117
1001RAJKUMAR    AP754213
1002MEENA       MP890213  

# Expected output
emp_id,Emp_name,state,emp_contact

# Steps Followed

1. Import the data into Blop Storage
2. Create Azure Data Factory new connection
3. Create the DataFlow
4. Import data from Blob which contains single column
5. Select Schema Modifier "Derived Column" option & gave appropriate name
6. Create column one by one
    *) emp_id => select Expression => Choose substring => Required column is "column1", emp_id starts with 1, total length 4 => substring("column1",1,4)
    *) emp_name => select Expression => Choose substring => Required column is "column1", emp_name starts with 5, total length 12 => substring("column1",5,12)
    *) state => select Expression => Choose substring => Required column is "column1", state starts with 17, total length 2 => substring("column1",17,2)
    *) emp_contact => select Expression => Choose substring => Required column is "column1", emp_contact starts with 18 , total length 6 => substring("column1",18,6)
 7. Select Schema Modifier "Select" option
 8. Remove the "column1" and make sure remaining columns are correctly mapped or not
 9. Create the SINK => Blob Storage
 10. Once configured everything, Click DEBUG mode and validate it
 11. Create the pipeline and publish & trigge it
 
