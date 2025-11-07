# PRODUCT-DETAILS-TRACKER

     #include <stdio.h>
      struct Product
     {
    int product_id;
    char product_name[30];
    float price;
    };
    void main() 
    {
    struct Product products[100];
    int i, j, n;
    struct Product temp;
    printf("Enter number of products: ");
    scanf("%d", &n);
    printf("\nEnter details for products \n");
    for (i = 0; i < n; i++)
    {
        printf("Product name: ");
        scanf("%s", products[i].product_name);  // no '&' needed for strings
        printf("Product ID: ");
        scanf("%d", &products[i].product_id);
        printf("Price: ");
        scanf("%f", &products[i].price);
    }
    for (i = 0; i < n - 1; i++) 
    {
        for (j = i + 1; j < n; j++) 
    {
            if (products[i].price <= products[j].price )
          {
               temp = products[i];
                products[i] = products[j];
                products[j] = temp;
            }
        }
    }
    printf("\nProducts sorted by price (descending):\n");
    printf("%s %s %s\n", "Product Name  \t", "Product ID \t ", "Price \n");

     for (i = 0; i < n; i++)
      {
        printf("%s \t\t\t %d \t\t\t Rs.%f\n", products[i].product_name, products[i].product_id, products[i].price);
      }
    }
