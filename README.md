import java.util.ArrayList;
import java.util.List;

public class ExpenseTracker {
    private List<Expense> expenses;

    public ExpenseTracker() {
        this.expenses = new ArrayList<>();
    }

    public void addExpense(Expense expense) {
        this.expenses.add(expense);
    }

    public void removeExpense(Expense expense) {
        this.expenses.remove(expense);
    }

    public double getTotalExpensesForBudget(Budget budget) {
        double total = 0;
        for (Expense expense : this.expenses) {
            if (expense.getBudget().equals(budget)) {
                total += expense.getAmount();
            }
        }
        return total;
    }

    public List<Expense> getExpensesForBudget(Budget budget) {
        List<Expense> expensesForBudget = new ArrayList<>();
        for (Expense expense : this.expenses) {
            if (expense.getBudget().equals(budget)) {
                expensesForBudget.add(expense);
            }
        }
        return expensesForBudget;
    }
}
