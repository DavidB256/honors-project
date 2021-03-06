# The Application of Ling-Term Machine Learning to Simulated Physical Environments

This is the Honors Project of David Bass, made for the purpose of earning the WJCC Honors Diploma.  It is a two-part project; the first part is to create a 2d physics engine and a graphics engine to display its output.  The second part is to research the efficacy of various machine learning techniques within the simulated physics environment.

All files whose names are in caps are AI training algorithms. GA="genetic algorithm", NN="neural network", PS="planetary system", TD="top down \[system]", SV="side view \[system]".

Most other files are called from the aforementioned ones.  environments.py stores previously-used physics environments and contains the Environments class, which is used to create world instances with objects specified in Environments.solids, and gravity specified by Environments.g_type and Environments.g_strength.  gene_functions.py stores classes of methods whose return values are weighted by organism genotypes in genetic algorithms, with one class for each AI training algorithm.  genetic_algorithm.py contains the Organism and Population classes, used for all of the initialization, mutation, natural selection, and genotype storage involved in a genetic algorithm.  neural_network.py contains functions necessary for constructing a neural network, feedforwarding, and backpropagating.  physics_engine.py contains all of the code to create solids in physics environments, move them, detect collisions among them, and resolve those collisions.  Its run_physics_engine function is used by AI training algorithms to piece all of these other classes and functions together so that the environment can be processed, tick by tick.

Files whose names end with "\_dna_testing" are used to take a closer look at a specific genotype produced by their namesake AI training algorithm.

run_physics_engine_indep.py is used to run the physics engine independently for a single environment.  How long it will run for, how much time it will increment with each update, and its display configuration can be controlled from the variables at the top of the file.  It outputs all data about each tick of the simulation into a text file (Make sure that there is a file called "output.txt" in the same folder as it when you run it!), provides that output data to the pygame-based graphics_engine.py for visual display if display==True, and then saves a screenshot of each display frame into the folder specified by save_loc if capture==True.  Note that enabling capture greatly slows down display speed, and will overwrite any previously-captured frames in the same file because each screenshot is named only for its tick number.  If capture==True but save_loc is not an existing file, the graphics engine will not run.

Finally, long_term.py runs the eponymous Long-Term Machine Learning algorithm in which all 3 environment paths are run in different orders. 

requirements.txt contains version of Python and versions of two external modules needed to run most of the code.

output.txt is just the output from the last-used physics simulation, but serves as a sample for what it should look like and to be overwritten when run_physics_engine_indep.py is used again.

And that's all!  Good luck :)
