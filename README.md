# Phylogenetic_Tree_Construction
1. Installs the required libraries by using `!pip install` commands. The libraries installed are:
   - `Bio`: A library for biological computation, including sequence analysis and phylogenetic tree construction.
   - `biopython`: A package that provides tools for computational biology.
   - `muscle`: A library for multiple sequence alignment.

2. Imports the necessary modules and classes from the installed libraries:
   - `Phylo` from `Bio` for phylogenetic tree manipulation and visualization.
   - `DistanceTreeConstructor` and `DistanceCalculator` from `Bio.Phylo.TreeConstruction` for constructing a distance-based phylogenetic tree.
   - `SeqIO` from `Bio` for reading sequence data from files.
   - `SeqRecord` from `Bio.SeqRecord` for creating sequence record objects.
   - `Seq` from `Bio.Seq` for creating sequence objects.
   - `MultipleSeqAlignment` from `Bio.Align` for creating a multiple sequence alignment object.
   - `matplotlib.pyplot` as `plt` for plotting and visualizing the tree.

3. Prompts the user to enter the path to a FASTA file. This file contains biological sequences that will be used for constructing the phylogenetic tree.

4. Reads the sequences from the FASTA file and stores them in a list named `sequences`. It also keeps track of the maximum sequence length encountered.

5. Aligns the sequences by padding or truncating them to the length of the longest sequence. The aligned sequences are stored in the list `aligned_sequences`.

6. Creates `SeqRecord` objects for each aligned sequence, assigning them unique identifiers. These objects are stored in the `records` list.

7. Creates a `MultipleSeqAlignment` object named `alignment` using the `records` list.

8. Calculates the pairwise distances between the aligned sequences using the `DistanceCalculator` with the 'identity' method. The distances are stored in a distance matrix (`dm`).

9. Constructs a phylogenetic tree from the distance matrix using the `DistanceTreeConstructor` with the UPGMA (Unweighted Pair Group Method with Arithmetic Mean) algorithm. The branch lengths of the tree represent the differences between the aligned sequences.

10. Adjusts the branch lengths of the tree by scaling them according to their differences.

11. Saves the constructed tree in the Newick format to a file named "Phylogenetic_Tree_Construction.nwk" using the `Phylo.write()` function.

12. Visualizes the constructed tree using `Phylo.draw()` and matplotlib. It creates a figure with a specified size, draws the tree on the axes, sets the title, saves the figure as "Phylogenetic_Tree_Construction.png", and then closes the figure.
