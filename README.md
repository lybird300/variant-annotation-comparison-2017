# variant-annotation-comparison-2017

In 2014, I did some benchmarking of variant effect prediction algorithms. You can read about that in this [blog post](http://blog.goldenhelix.com/ajesaitis/the-sate-of-variant-annotation-a-comparison-of-annovar-snpeff-and-vep/).

I wanted to follow up on that work and see how the current batch of algorithms are preforming. [VEP](http://uswest.ensembl.org/info/docs/tools/vep/index.html) and [SnpEff](http://snpeff.sourceforge.net/) are the most commonly used algorithms these days, so I limited my analysis to them.

I used the same input VCF that I created originally. It contains all snps, all 1 base pair insertions and deletions, and 2 possible 2 and 3 base pair insertions and deletions at all locations spanning the CFTR gene with 100bp margins on either side.

You can annotate this vcf with each algorithm using the CWL scripts provided.

For VEP:

```
docker build --tag="andrewjesaitis/vep" -f Dockerfile.vep .
cwltool vep-workflow.cwl cftr-job-vep.yml
```

Similarly for SnpEff:

```
docker build --tag="andrewjesaitis/snpeff" -f Dockerfile.snpeff .
cwltool snpeff-workflow.cwl cftr-job-snpeff.yml
```

Then you can open the Jupyter Notebook and rerun all cells.

Otherwise just skip to the punchline and [open the notebook](https://github.com/andrewjesaitis/variant-annotation-comparison-2017/blob/master/Variant-Annotation-Comparsion-2017.ipynb) on Github.

I'm planning on writing this up in a blog post soon! Stay tuned!
