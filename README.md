# Jayant-R-Pujar
# restaurants Bill Genaretion using c code with GST included
#include <stdio.h>
#include <string.h>
#include <unistd.h>

int main() {
    int b, z, i, a, s, g = 0, bq, bill = 0, arr[5] = {0}, prr[5] = {0}, b_ki_value[5] = {0};
    int cgst = 0, sgst = 0;
    char ch = 'y', ok = 'y', order = 'y';
    const char *crr[5] = {NULL};

    printf("\t\tWelcome to Dalpat Restaurant\n\n");
    printf("Choose your meal plan :\n\n");
    printf("1. Breakfast\n2. Lunch\n3. Dinner\n\n");
    scanf("%d", &a);
    printf("\n");

    if (a == 1) {
        do {
            printf("\tChoose your order :\n\n\t");
            printf("1. Poha\t\t50/-\n\t");
            printf("2. Aloo Paratha\t60/-\n\t");
            printf("3. Dosa\t\t40/-\n\t");
            printf("4. Sandwich\t80/-\n\n\t");
        } while (ch == 'n');

        do {
            do {
                printf("Enter no.: ");
                scanf("%d", &b);
                b_ki_value[g] = b;

                if (b >= 1 && b <= 4) {
                    printf("\n\tTell us the Quantity: ");
                    scanf("%d", &bq);
                    arr[b - 1] = bq;  // Fixing index to match the array
                    ok = 'y';
                } else {
                    printf("\n\tInvalid Entry.. please try again\n\n\t");
                    ok = 'n';
                }
            } while (ok == 'n');

            printf("\n\tAdd more to your order: (Y or N) ?\n\t");
            scanf(" %c", &order);  // Updated to use scanf

            g++;

            switch (b) {
                case 1:
                    crr[0] = "Poha";
                    prr[0] = 50;
                    break;
                case 2:
                    crr[1] = "Aloo Paratha";
                    prr[1] = 60;
                    break;
                case 3:
                    crr[2] = "Dosa";
                    prr[2] = 40;
                    break;
                case 4:
                    crr[3] = "Sandwich";
                    prr[3] = 80;
                    break;
            }

        } while (order == 'y' || order == 'Y');
    } else if (a == 3) {
        do {
            printf("\tChoose your order :\n\n\t");
            printf("1. Tandoori Roti\t15/-\n\t");
            printf("2. Kadhai Paneer\t140/-\n\t");
            printf("3. Dal Chawal\t100/-\n\t");
            printf("4. Salad/Curd\t50/-\n\n\t");
        } while (ch == 'n');

        do {
            do {
                printf("Enter no.: ");
                scanf("%d", &b);
                b_ki_value[g] = b;

                if (b >= 1 && b <= 4) {
                    printf("\n\tTell us the Quantity: ");
                    scanf("%d", &bq);
                    arr[b - 1] = bq;
                    ok = 'y';
                } else {
                    printf("\n\tInvalid Entry.. please try again\n\n\t");
                    ok = 'n';
                }
            } while (ok == 'n');

            printf("\n\tAdd more to your order: (Y or N) ?\n\t");
            scanf(" %c", &order);

            g++;

            switch (b) {
                case 1:
                    crr[0] = "Tandoori Roti";
                    prr[0] = 15;
                    break;
                case 2:
                    crr[1] = "Kadhai Paneer";
                    prr[1] = 140;
                    break;
                case 3:
                    crr[2] = "Dal Chawal";
                    prr[2] = 100;
                    break;
                case 4:
                    crr[3] = "Salad/Curd";
                    prr[3] = 50;
                    break;
            }

        } while (order == 'y' || order == 'Y');
    } else if (a == 2) {
        do {
            printf("\tChoose your order :\n\n\t");
            printf("1. Veg Thali\t280/-\n\t");
            printf("2. Mini Thali\t150/-\n\t");
            printf("3. Salad/Papad\t45/-\n\t");
            printf("4. Veg Biryani\t90/-\n\n\t");
        } while (ch == 'n');

        do {
            do {
                printf("Enter no.: ");
                scanf("%d", &b);
                b_ki_value[g] = b;

                if (b >= 1 && b <= 4) {
                    printf("\n\tTell us the Quantity: ");
                    scanf("%d", &bq);
                    arr[b - 1] = bq;
                    ok = 'y';
                } else {
                    printf("\n\tInvalid Entry.. please try again\n\n\t");
                    ok = 'n';
                }
            } while (ok == 'n');

            printf("\n\tAdd more to your order: (Y or N) ?\n\t");
            scanf(" %c", &order);

            g++;

            switch (b) {
                case 1:
                    crr[0] = "Veg Thali";
                    prr[0] = 280;
                    break;
                case 2:
                    crr[1] = "Mini Thali";
                    prr[1] = 150;
                    break;
                case 3:
                    crr[2] = "Salad/Papad";
                    prr[2] = 45;
                    break;
                case 4:
                    crr[3] = "Veg Biryani";
                    prr[3] = 90;
                    break;
            }

        } while (order == 'y' || order == 'Y');
    }

    printf("\t\tGenerating your BILL....\n");
    for (i = 1; i <= 6; i++) {
        printf(".");
        sleep(1); // Sleep for 1 second to simulate processing
    }
    printf("\n");

    for (z = 1; z <= 60; z++) {
        printf("_");
    }
    printf("\n\t\t BILL Generated\n\t\t");

    for (z = 0; z < g; z++) {
        s = (prr[b_ki_value[z] - 1]) * (arr[b_ki_value[z] - 1]);
        bill += s;
        printf("\n\t%d. %s\t\t%dx%d\t: %d/-", z + 1, crr[b_ki_value[z] - 1], prr[b_ki_value[z] - 1], arr[b_ki_value[z] - 1], s);
    }
    printf("\n");

    for (z = 1; z <= 60; z++) {
        printf("_");
    }
    printf("\n\tSum total\t\t: %d/-", bill);
    sgst = (bill / 100) * 5;
    cgst = sgst;
    printf("\n\t\tCGST 5%%\t\t: %d/-", cgst);
    printf("\n\t\tSGST 5%%\t\t: %d/-", sgst);
    bill += sgst + cgst;
    printf("\n\tTotal Bill\t\t: %d/-", bill);

    getchar(); // Wait for user input before exiting
    return 0;
}
