PROJECT 3 IMPLEMENTATION 

mini_fat_write_in_block and mini_fat_read_in_block:
	For this functions, we used fopen, fread, fwrite, and fseek to read from file and write into file. We used these 		two functions as helper to implement some of other functions easily.
	
mini_fat_find_empty_block:
	We searched for empty block in the file system using block_map elements, we looped until finding empty one.
	
mini_fat_create:
	In this function, we created real binary file as a virtual disk file. 
	
mini_file_open:
	First, we tried to find file in the file system with the given file name. If it's not available in the file 	system, we create new file with the method mini_file_create_file when the file is opened for writing operation. 		Otherwise, we returned NULL. If the operation is writing operation and file is available in the system, we 	checked whether other write handles are open or not with for loop. If there is no other write handles are open 		assigned fields for new open file and returned it.
	
mini_file_write:

mini_file_read:

mini_file_seek:
	If the seek operation started from beginning of the file, we set curser position to offset. Otherwise, we moved 		curser by offset. Also, we compared new position with the size of the file before assigning new curser position.

mini_file_delete:
	First, we searched for the file in the given file system. If it exists and not open, we assigned its meta data 		block and data blocks to empty blocks, and we returned true. Otherwise, we returned false. Also, we used the 		vector_delete_value function to delete file.
