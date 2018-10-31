Greedy Algorithm:
In the greedy algorithm, all the philosophers try to pick up the fork to their left (and with 5 philosophers and 5 forks, they are all successful). Then they try to pick up the fork to their right, but since all the forks are taken, no philosopher can take the fork to the right and thus no philosopher can have the two forks required in order to be able to eat. As a result, no philosopher is able to eat and even if they all release their left forks and pick them back up again, no progress would be made as the same process would be replicated, therefore resulting in a deadlock. 

Greedy Algorithm with Waiter:
We can guarantee that no deadlock will occur if there is at least one philosopher who can grab a right fork and eat each iteration of the while loop in the greedy algorithm. Thus after all the philosophers pick up the fork to the left simultaneously, there must be at least one fork remaining unclaimed, available for a philosopher to pick up as their right fork and thus begin to eat. Note that rather than adding an extra fork and moving the fork around the table to allow every philosopher to eat, we can just limit the number of philosphers sitting down at the table at a time. 
If we let n be the number of forks, the maximum number of philosophers that can sit at the table at any one time such that we can guarantee no deadlock will occur is n-1. 
This way a philosopher will always have a right fork to pick up and a philosopher will always be able to eat. To allow all the philosophers to eat we can just rotate the philosophers around the table (and standing up) so that the philosopher initially standing up (not sitting at table) can eventually sit down and eat, and the philosophers currently sitting down can eventually rotate to the seat with two available forks (to the left and right) and eat. No deadlock will occur because the philosophers will be continuously moving to a different place and will be allowed to eat eventually. 

Talking Philosophers:
Let there be 5 philosophers sitting at a table. They all begin with dirty left forks. They all request a fork, and they all hold dirty forks, thus they're able to give their fork to another philosopher. If we label the philosophers 1-5, we would have the following:
1. Philosopher 1-5 request a fork in order. 
2. Philosopher 2 gives Philosopher 1 his (now clean) (right) fork. 
3. Philospher 3 gives Philosopher 2 his (now clean) fork. 
4. Philosopher 4 gives Philosopher 3 his (now clean) fork. 
5. Philosopher 5 gives Philosopher 4 his (now clean) fork. 
6. Philosopher 5 has a pending request for a fork, but Philosopher 1 is eating, so has to wait until 1 is done eating to get his fork. 
7. Philosopher 1 is done eating and has 2 dirty forks, so is able to pass both his forks to someone else. Meanwhile the other Philosophers holding forks have clean forks, so they will keep their forks. 
8. Philosopher 5 still has a pending request and then Philosophers 2-5 (in that order) request a fork. 
9. Philosopher 1 gives Philosopher 5 his (now clean) (left) fork. 
10. Philosopher 1 gives Philosopher 2 his (now clean) (right) fork. 
11. Philosopher 2 has 2 forks and can now eat, while no one else can pass/receive forks so they will wait until Philosopher 2 is done eating. (Note: Philosophers 3-5 have pending requests)
12. Afterwards Philosopher 2 gives a fork to Philosopher 3 (right fork) and 1 (left fork). 
13. Philosopher 3 eats and gives a fork to Philosopher 4 (right fork) and 2 (left fork), who have the next pending requests. 
14. Philosopher 4 eats and gives a fork to Philosopher 5 (right fork) and 3 (left fork), who have the next pending requests. 
15. Philosopher 5 eats and gives fork to Philosopher 1 (right fork) and 4 (left fork), who have next pending request. 
16. At this point, all Philosophers have eaten, Philosophers 2-4 have a left fork, and Philosopher 1 has two forks, so cycle repeats. 
Thus with 5 Philosophers, there will be no deadlock and all Philosophers will eat. 
