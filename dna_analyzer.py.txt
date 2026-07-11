from Bio.Seq import Seq
import matplotlib.pyplot as plt

# 1. Input: A sample DNA Sequence
dna_sequence = Seq("ATGCGATCGATCGATCGATCGATCGATCGATCGATCGATCGATC")
print("Original DNA Sequence:", dna_sequence)

# 2. Transcription: Convert DNA to RNA
rna_sequence = dna_sequence.transcribe()
print("Transcribed RNA Sequence:", rna_sequence)

# 3. Translation: Convert RNA to Protein Amino Acids
protein_sequence = rna_sequence.translate()
print("Translated Protein Sequence:", protein_sequence)

# 4. Data Analytics: Count individual nucleotide frequencies
nucleotide_counts = {
    'Adenine (A)': dna_sequence.count("A"),
    'Thymine (T)': dna_sequence.count("T"),
    'Guanine (G)': dna_sequence.count("G"),
    'Cytosine (C)': dna_sequence.count("C")
}

# 5. Visualisation: Generate a clean scientific chart
plt.figure(figsize=(8, 5))
plt.bar(list(nucleotide_counts.keys()), list(nucleotide_counts.values()), color=['#FF9999', '#66B3FF', '#99FF99', '#FFCC99'])
plt.title("Nucleotide Frequency Distribution Analysis", fontsize=14, fontweight='bold')
plt.xlabel("Nucleotide Base", fontsize=12)
plt.ylabel("Count Frequency", fontsize=12)
plt.grid(axis='y', linestyle='--', alpha=0.7)

# Save the plot automatically as an image file
plt.savefig("nucleotide_distribution.png")
print("Data chart generated successfully and saved as 'nucleotide_distribution.png'!")
