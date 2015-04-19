var cashRegister = {

    total: 0,
    
    lastTransactionAmount: 0,
    
    add: function(itemCost) {
    
        this.total += itemCost || 0;
        
        this.lastTransactionAmount = itemCost;
    },
    
    scan: function(item, quantity) {
    
        switch (item) {
        
        case "grapes": this.add(0.49 * quantity); break;
        
        case "candy": this.add(0.45 * quantity); break;
        
        case "peanuts": this.add(0.98 * quantity); break;
        
        case "cookies": this.add(1.00 * quantity); break;
        }
        
    },
    
    voidlastTransaction: function() {
    
        this.total = this.total - this.lastTransactionAmount;
    }
    
};

cashRegister.scan('cookies', 1);

console.log("Your total bill is " + cashRegister.total);
