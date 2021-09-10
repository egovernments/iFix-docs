# Search Consumer

The search screen used to list the consumer based on various criteria. This would be the common search screen for all the transactions such as

1. Collect Payments
2. Download bills and receipts
3. Update consumer information

![Search Consumer](../../../.gitbook/assets/image%20%2836%29.png)

The consumer can be searched based on these parameters -

1. Owner Mobile Number - Should be able to search consumer records that matches the mobile number entered.
   1. OLD Mobile Number
   2. NEW Mobile Number
2. User should be able to search only when he/she enters full mobile number. Partial mobile number search is not allowed
3. Name of Consumer - Should be able to search consumer records that matches with the portion of the Name with text entered.
   1. OLD Name
   2. New Name
4. Name search can be done with partial name also.
5. Old Connection id - Should be able to search consumer records that matches the old Connection id entered.
6. New Connection id - Should be able to search consumer records that matches the New Connection id entered.

![Search Consumer Expanded](../../../.gitbook/assets/image%20%289%29.png)

1. As the user starts entering one field, other fields should be made non editable. When the user removes text/numbers entered in the field, other fields will be made accessible.
2. Show more, Show less expands and contracts the view
3. When the user search matches with only one record, show HH detail screen directly. No need to show intermediary search details screen.

**Search Result:**

![](../../../.gitbook/assets/image%20%2819%29.png)

The result set will have below information

1. Sub-Heading - Sub heading text should change dynamically on what type of search is carried out.
   1. Following consumers match search criteria with
      1. Phone Number as +91 - 7731045306
      2. Name as ABCxyZ
2. New Connection ID
3. Old Connection ID
4. Consumer’s Name
5. Phone Number
6. Address - Combination of Door Number, street number, Ward \(if applicable\)
7. On click of 'View Consumer Details', it should navigate to HH Details screen.

