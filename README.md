# Modifications-AMPs-from-KP-ML
How it works:
Input:

seq: The original peptide sequence (a string of amino acid letters).

n_mutations: Number of amino acid positions to mutate (default 3).

min_charge: Minimum net positive charge expected in the mutated peptide (default 2).

max_length: Maximum allowed length for the peptide (default 20).

Steps:

Length check:
It first checks if the peptide length is between a minimum (6) and the specified maximum length (default 20).

If not, the function returns the original sequence unchanged (no mutation).

Mutation position selection:
Randomly selects n_mutations unique positions within the sequence to mutate.

Mutation choice:
For each chosen position:

With 70% chance, replace the amino acid with one from a "priority pool" — a set of amino acids that includes positively charged (like R, K), hydrophobic, and aromatic residues thought to enhance activity.

Otherwise, replace it with a random amino acid from the full set excluding the current one.

Charge check:
After mutations, calculates the net charge of the mutated peptide at physiological pH (7.0).

If the charge is below the minimum charge threshold (min_charge), it returns the mutated sequence anyway (the code comment suggests skipping but actual code returns mutated anyway).
(You could modify this behavior to reject mutations that reduce charge too much.)

Return mutated sequence:
Outputs the mutated peptide sequence as a string.


![image](https://github.com/user-attachments/assets/9ad1367d-04d9-417c-893a-4d2a51346745)
