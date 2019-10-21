```py
def main():
    try:
        sheetIds = readConfig()
        command, param = readArgs()
        service = getSheetService()
        # ...
        if command == "edit":
            subcommand = param[0]
            lineIndex = int(param[1])
            transaction, noExplicitDate = parseTransaction(param[2])
            monthlySheetId = getMonthlySheetId(transaction[0], sheetIds)
            transactions = readTransactions(service, monthlySheetId, subcommand)
            validateLineIndex(lineIndex, transactions)
            if noExplicitDate is True:
                print("Only 3 fields were specified. Assigning original date to date field.")
                transaction[0] = transactions[lineIndex - 1][0]
            summary = readSummaryPage(service, monthlySheetId)
            validateCategory(subcommand, transaction, summary)
            transaction[0] = str(transaction[0])[:10]
            editTransaction(lineIndex, transaction, service, subcommand, monthlySheetId, summary.title)
            return
        # ...
    except UserWarning as e:
        print(str(e), file=sys.stderr)
```

```py
# parses transaction fields & inserts a date field (today) if not specified
def parseTransaction(params):
    transaction = [e.strip() for e in params.split(',')]
    noExplicitDate = len(transaction) is NUM_TRANSACTION_FIELDS - 1
    if noExplicitDate:
        transaction.insert(0, datetime.now())
    if len(transaction) != NUM_TRANSACTION_FIELDS:
        raise UserWarning("Invalid number of fields in transaction.")
    try:
        if float(transaction[1]) <= 0 or float(transaction[1]) > 99999:
            raise ValueError()
    except ValueError:
            raise UserWarning("Invalid transaction amount: {0}".format(transaction[1]))
    return transaction, noExplicitDate
```
