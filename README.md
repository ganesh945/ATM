# ATM
{
  "cells": [
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "ZB0k5U00-JFK",
        "outputId": "8237a483-091e-41fd-8c32-c06516feab58"
      },
      "outputs": [
        {
          "metadata": {
            "tags": null
          },
          "name": "stdout",
          "output_type": "stream",
          "text": [
            "*******WELCOME TO BANK OF GANESH*******\n",
            "___________________________________________________________\n",
            "\n",
            "----------ACCOUNT CREATION----------\n"
          ]
        }
      ],
      "source": [
        "import random\n",
        "import sys\n",
        " \n",
        "class ATM():\n",
        "    def __init__(self, name, account_number, balance = 500000):\n",
        "        self.name = name\n",
        "        self.account_number = account_number\n",
        "        self.balance = balance\n",
        "         \n",
        "    def account_detail(self):\n",
        "        print(\"\\n----------ACCOUNT DETAIL----------\")\n",
        "        print(f\"Account Holder: {self.name.upper()}\")\n",
        "        print(f\"Account Number: {self.account_number}\")\n",
        "        print(f\"Available balance: Nu.{self.balance}\\n\")\n",
        "         \n",
        "    def deposit(self, amount):\n",
        "        self.amount = amount\n",
        "        self.balance = self.balance + self.amount\n",
        "        print(\"Current account balance: Nu.\", self.balance)\n",
        "        print()\n",
        " \n",
        "    def withdraw(self, amount):\n",
        "        self.amount = amount\n",
        "        if self.amount > self.balance:\n",
        "            print(\"Insufficient fund!\")\n",
        "            print(f\"Your balance is Nu.{self.balance} only.\")\n",
        "            print(\"Try with lesser amount than balance.\")\n",
        "            print()\n",
        "        else:\n",
        "            self.balance = self.balance - self.amount\n",
        "            print(f\"Nu.{amount} withdrawal successful!\")\n",
        "            print(\"Current account balance: Nu.\", self.balance)\n",
        "            print()\n",
        " \n",
        "    def check_balance(self):\n",
        "        print(\"Available balance: Nu.\", self.balance)\n",
        "        print()\n",
        " \n",
        "    def transaction(self):\n",
        "        print(\"\"\"\n",
        "            TRANSACTION \n",
        "        *********************\n",
        "            Menu:\n",
        "            1. Account Detail\n",
        "            2. Check Balance\n",
        "            3. Deposit\n",
        "            4. Withdraw\n",
        "            5. Exit\n",
        "        *********************\n",
        "        \"\"\")\n",
        "        \n",
        "        while True:\n",
        "            try:\n",
        "                option = int(input(\"Enter 1, 2, 3, 4 or 5:\"))\n",
        "            except:\n",
        "                print(\"Error: Enter 1, 2, 3, 4, or 5 only!\\n\")\n",
        "                continue\n",
        "            else:\n",
        "                if option == 1:\n",
        "                    atm.account_detail()\n",
        "                elif option == 2:\n",
        "                    atm.check_balance()\n",
        "                elif option == 3:\n",
        "                    amount = int(input(\"How much you want to deposit(Nu.):\"))\n",
        "                    atm.deposit(amount)\n",
        "                elif option == 4:\n",
        "                    amount = int(input(\"How much you want to withdraw(Nu.):\"))\n",
        "                    atm.withdraw(amount)\n",
        "                elif option == 5:\n",
        "                    print(f\"\"\"\n",
        "                printing receipt..............\n",
        "          ******************************************\n",
        "              Transaction is now complete.                         \n",
        "              Transaction number: {random.randint(10000, 1000000)} \n",
        "              Account holder: {self.name.upper()}                  \n",
        "              Account number: {self.account_number}                \n",
        "              Available balance: Nu.{self.balance}                    \n",
        " \n",
        "              Thanks for choosing us as your bank                  \n",
        "          ******************************************\n",
        "          \"\"\")\n",
        "                    SystemExit\n",
        " \n",
        "print(\"*******WELCOME TO BANK OF GANESH*******\")\n",
        "print(\"___________________________________________________________\\n\")\n",
        "print(\"----------ACCOUNT CREATION----------\")\n",
        "name = input(\"Enter your name: \")\n",
        "account_number = input(\"Enter your account number: \")\n",
        "print(\"Congratulations! Account created successfully......\\n\")\n",
        " \n",
        "atm = ATM(name, account_number)\n",
        " \n",
        "while True:\n",
        "    trans = input(\"Do you want to do any transaction?(y/n):\")\n",
        "    if trans == \"y\":\n",
        "        atm.transaction()\n",
        "    elif trans == \"n\":\n",
        "        print(\"\"\"\n",
        "    -------------------------------------\n",
        "   | Thanks for choosing us as your bank |\n",
        "   | Visit us again!                     |\n",
        "    -------------------------------------\n",
        "        \"\"\")\n",
        "        break\n",
        "    else:\n",
        "        print(\"Wrong command!  Enter 'y' for yes and 'n' for NO.\\n\")\n",
        "    "
      ]
    }
  ],
  "metadata": {
    "colab": {
      "provenance": []
    },
    "kernelspec": {
      "display_name": "Python 3",
      "name": "python3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "nbformat": 4,
  "nbformat_minor": 0
}
