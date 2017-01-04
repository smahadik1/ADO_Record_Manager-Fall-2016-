                                                           
			                  ****************Assignment No. 3******************	
                                                      ADO RecordManager CS525
1] Personnel Information:

      Name				  	  CWID				     Email-id
1) Shraddha Vijay Mahadik(Team Leader) 		A20385273 			smahadik1@hawk.iit.edu
2) Amruta Ashok Pimple				A20380183 			apimple@hawk.iit.edu	
3) Samruddhi Sunil Naik				A20381084 			snaik6@hawk.iit.edu
4) Sumanth Gouru	 			A20379873 			sgouru@hawk.iit.edu




Instructions to Execute the Code:

1) Go to root folder of project (Assignment3) using Terminal 

2) Type "make clean" command to delete the previosly compiled .o files.

3) Type "make" command which compiles the files including "test_assign3_1.c".

4) Type "make run" command that runs the "test_assign3_1.c" file.

5) Type "make test_expr" to compile the "test_expr.c".

6) Type "make run_expr" to run "run_expr.c". 

------------------------------------------------------------------------------------------------------------------------------------------------------------

We have developed the following:

1) Record Manager with all the required function
2) A Record with the Tombstone 

Overview:

1) Functions use two Structures named Table_Info and  Scan. 
	
	Table_Info:It maintains the all the pointers of bufferpool and the information of tuples and free page. 
	Scan: It maintains pointers of page handle in bufferpool and information about no of scans and conditional expressions.

2) Tombstone : Tombstone is a solution for deletion of tuples. We have used the first byte of every tuple with character byte of length 1.
				
				
					'0' :- It represents that slot is empty and ready for the insertion.
	                                '#' :- it is used for a non-empty slot.
					

3) Example of Record Data Structure: 

                                Tombstone: 1 Byte
                                First attribute: 4 bytes(integer)
                                Second attribute: String length (4 bytes)
                                Third attribute: 4 bytes(integer)                                  
  				
                                Record Size : 13 bytes
				Empty Record     : "0_ _ _ _ _ _"
				Non-Empty Record : "#1aaaa3"
				Deleted Record   : "03cccc5" 

4) Page 0 in the Page File does not contain any records. 
	It contains: It maintains the total number of tuples in the table and the first page with the Schema of the Table.
					
5) We have used Least frequently used as the Page replacement Algorithm since the page 0 is frequently used.
//initBufferPool(&t ->bm, name, size, RS_LFU, NULL);

----------------------------------------------------------------------------------------------------------------------------------------
