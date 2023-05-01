Download Link: https://assignmentchef.com/product/solved-csc3002f-assignment-5-synchronization-part-ii
<br>
This assignment aims to give you experience in thread (and, by extension, process) synchronization using <strong>semaphores</strong>. In this project, you will write multithreaded programs in Java to solve <strong>three classic synchronization problems</strong>, using only semaphores.  A secondary aim is to give you experience in reading, understanding and correcting existing code.  The assignment is in three parts, increasing in difficulty.  The second part is described below. Part II: Dish washing with semaphores

In this simulation, you will correctly implement a simple simulation of dish-washing in a kitchen.  There are two roles: washer and dryer, with a shared rack between them for the wet dishes.  The washer washes dishes one-by-one, adding them to the rack for drying.  The dryer removes the wet dishes from the rack one-by-one to dry them.  There are several synchronization constraints to enforce to make this system work correctly:

<ul>

 <li>Only one person should access the shared rack at any point.</li>

 <li>When the rack is empty, the dryer must wait.</li>

 <li>When the rack is full, the washer must wait.</li>

 <li>The dryer cannot dry a dish before the washer has washed it.</li>

</ul>

<h2>1.1 Code skeleton: dishWashS</h2>

You <strong>must use</strong> and extend the dishWashS <strong>package provided</strong>, correctly implementing the WetDishRack            class (and all the methods), so that the           CleaningDishes   class will execute correctly, <strong>always</strong>.   <strong>Do not alter</strong> the

CleaningDishes   or the  Dryer and Washer  thread classes in the package

(although you must submit them).  You will need to inspect the various classes to see how they work – this is part of the assignment and <strong>no explanation other than the code will be given</strong>.

An <strong>example</strong> of a correct execution of            CleaningDishes   is:

Ø java       dishWashS.CleaningDishes  6          3          100     100

—Washer is washing dish #1

—Washer added dish #1 to rack.

—Dryer removed dish #1 from rack

—Washer is washing dish #2

—Washer added dish #2 to rack.

—Washer is washing dish #3

—Washer added dish #3 to rack.

—Washer is washing dish #4

—Washer added dish #4 to rack.

—Washer is washing dish #5

—Dryer is done with dish #1

—Dryer removed dish #2 from rack

—Washer added dish #5 to rack.

—Washer is washing dish #6

—Dryer is done with dish #2

—Dryer removed dish #3 from rack

—Washer added dish #6 to rack.

—Washer is DONE.

—Dryer is done with dish #3

—Dryer removed dish #4 from rack

—Dryer is done with dish #4

—Dryer removed dish #5 from rack

—Dryer is done with dish #5

—Dryer removed dish #6 from rack —Dryer is done with dish #6 —Dryer is DONE.

<h1>1         Code requirements</h1>

You will code your solutions in Java, adding to the skeleton code provided.

You may only use the <strong>Semaphore</strong> class in the java.util.concurrent library: <strong>no other Java synchronization constructs at all</strong>.

All code must be <strong>deadlock free. </strong>

The output must comply with the stated synchronization constraints and with the examples shown.