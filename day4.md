<img width="649" height="743" alt="Screenshot 2025-07-21 at 10 23 51 AM" src="https://github.com/user-attachments/assets/bcc5b082-78fc-4ce8-a699-fd0633dcfbc3" />
This is the track file where things are viewable.



<img width="989" height="936" alt="Screenshot 2025-07-21 at 9 36 12 PM" src="https://github.com/user-attachments/assets/f49ffa32-41b9-4a3a-86e3-5e6c4ad90a59" />
Layout in Magic with Grid.


<img width="757" height="758" alt="Screenshot 2025-07-22 at 9 45 28 PM" src="https://github.com/user-attachments/assets/33588da4-75c7-45e3-aef4-b57bdecf4edd" />
TNS stands for Total Negative Slack - The value above is "pretty high" so remidation must be done.


<img width="944" height="924" alt="Screenshot 2025-07-23 at 9 48 05 PM" src="https://github.com/user-attachments/assets/63dee8dd-9866-469a-8bb6-c40242743b5b" />

Because of "jitter" clock pulse width and clock edge has variation. This is due to things that are physically present from the clock generation.
This is representated as Uncertainty. For STA (setup timing anaylsis), because of how different edges interact, the clock window grows when you take into account Uncertanty.

So the new equation beocmes "theta < (T-S-S_uncertainty)"

<img width="1375" height="821" alt="Screenshot 2025-07-23 at 3 49 08 PM" src="https://github.com/user-attachments/assets/57acb2bc-9729-4d3f-a113-0629d98f9cc7" />


Base SDC file:
<img width="760" height="518" alt="Screenshot 2025-07-23 at 10 39 02 PM" src="https://github.com/user-attachments/assets/fe3bcaac-8cce-421d-bbc4-8be6a6c4b6be" />



<img width="705" height="456" alt="Screenshot 2025-07-24 at 10 17 57 PM" src="https://github.com/user-attachments/assets/413b45d2-ac8c-4264-8f37-fe8c0bea61a5" />

This is a method to allow clocks to propogate through the tree. Using an "enable pin" you can greatly reduce power consumption when you aren't using an entire section of the clock tree. Similarly for an or gate, propogation only happens to "Y" (output) when there is a 0 on the enable. This is called the Clock Gating Technique. However this only works due to the process underlined below. 


<img width="915" height="506" alt="Screenshot 2025-07-24 at 10 21 28 PM" src="https://github.com/user-attachments/assets/fd39a3c0-a1d1-4e9c-bb8c-fc3964979603" />
