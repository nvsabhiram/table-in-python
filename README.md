# table-in-python
def getPriceOfProduct(data,product_name,province_name):
   
    #loop to run through the list/table data
    for x in data:
       
        # Checking if the product exists
        if x[0].casefold() == product_name.casefold():
           
            # Checking if it is provincial / national
            if ((x[2].casefold() == province_name.casefold()) and x[1].casefold()=="provincial"):
                return x[3] #returning provincial price if product is found and the region matches with "provincial"
           # checking if region is national to return national price
            elif (x[2] == "" and x[1].casefold()=="national"):
                return x[3]
           #to convey if the product is not found in the list
    else:
        return ("Product not found")                
           
input_data =[["Kale","Provincial","Ontario",5.99],["Kale","Provincial","Alberta",4.99],["Kale","National","",4.50],
             ["Celery","Provincial","Quebec",7.49],["Celery","National","",4.59],
             ["Lettuce","Provincial","Alberta",8.99],["Lettuce","National","",5.59],
             ["Parsley","National","",7.49],["Parsley","Provincial","Montreal",6.99],
             ["Broccoli","National","",9.49],["Broccoli","Provincial","Ottowa",11.99]]

result = getPriceOfProduct(input_data,"Broccoli","Quebec") #search here by changing product and province
print("Price of the product is: $",result)
