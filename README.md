# Analysis of HIV RNA-seq data using Telescope

We identified three experiments

### Peng dataset

[Peng, X. et al., 2014.](http://www.ncbi.nlm.nih.gov/pubmed/24850744) **Deep Sequencing of HIV-Infected Cells: Insights into Nascent Transcription and Host-Directed Therapy.** _Journal of virology_, 88(16), pp.8768–8782.

GEO: GSE53993

SRA: SRP035316



### Chang dataaset
[Chang, S.T. et al., 2011.](http://www.ncbi.nlm.nih.gov/pubmed/21933919) **Next-generation sequencing reveals HIV-1-mediated suppression of T cell activation and RNA processing and regulation of noncoding RNA expression in a CD4+ T cell line.** _mBio_, 2(5).

GEO: GSE38006

SRA: SRP013224


### Bushman dataset
[Sherrill-Mix, S., Ocwieja, K.E. & Bushman, F.D., 2015.](http://www.ncbi.nlm.nih.gov/pubmed/26377088) **Gene activity in primary T cells infected with HIV89.6: intron retention and induction of genomic repeats.** _Retrovirology_, 12(1), p.79.

SRA: SRP055981 (integration site data SRP057555)

### Download sample data

```bash
mkdir -p metadata/bushman
python scripts/get_sra_data.py --dest metadata/bushman SRP055981

mkdir -p metadata/peng
python scripts/get_sra_data.py --dest metadata/peng SRP035316

mkdir -p metadata/chang
python scripts/get_sra_data.py --dest metadata/chang SRP013224
```

| run_accession  |  study  |  run_bases  |  run_nspots  |  treatment  |  time  |  replicate  |  cell_type  |  library_type |
| -------------  |  -----  |  ---------  |  ----------  |  ---------  |  ----  |  ---------  |  ---------  |  ------------ |
| SRR497699  |  chang  |  2352153675  |  31362049  |  HIV  |  h12  |  1  |  SUPT1  |  polyA |
| SRR497700  |  chang  |  2670291600  |  35603888  |  HIV  |  h12  |  2  |  SUPT1  |  polyA |
| SRR497701  |  chang  |  2232788700  |  29770516  |  HIV  |  h12  |  3  |  SUPT1  |  polyA |
| SRR497702  |  chang  |  1795223400  |  23936312  |  HIV  |  h24  |  1  |  SUPT1  |  polyA |
| SRR497703  |  chang  |  1831434075  |  24419121  |  HIV  |  h24  |  2  |  SUPT1  |  polyA |
| SRR497704  |  chang  |  1752961125  |  23372815  |  HIV  |  h24  |  3  |  SUPT1  |  polyA |
| SRR497705  |  chang  |  2319900600  |  30932008  |  mock  |  h12  |  1  |  SUPT1  |  polyA |
| SRR497706  |  chang  |  2424815100  |  32330868  |  mock  |  h12  |  2  |  SUPT1  |  polyA |
| SRR497707  |  chang  |  2259134175  |  30121789  |  mock  |  h12  |  3  |  SUPT1  |  polyA |
| SRR497708  |  chang  |  2428788450  |  32383846  |  mock  |  h24  |  1  |  SUPT1  |  polyA |
| SRR497709  |  chang  |  1907110650  |  25428142  |  mock  |  h24  |  3  |  SUPT1  |  polyA |
| SRR1106189  |  peng  |  3321368100  |  18452045  |  HIV  |  h12  |  1  |  SUPT1  |  totalRNA |
| SRR1106190  |  peng  |  3200584500  |  17781025  |  HIV  |  h12  |  2  |  SUPT1  |  totalRNA |
| SRR1106191  |  peng  |  4092455520  |  22735864  |  HIV  |  h12  |  3  |  SUPT1  |  totalRNA |
| SRR1106192  |  peng  |  3926548980  |  21814161  |  HIV  |  h24  |  1  |  SUPT1  |  totalRNA |
| SRR1106193  |  peng  |  3305396520  |  18363314  |  HIV  |  h24  |  2  |  SUPT1  |  totalRNA |
| SRR1106194  |  peng  |  3391605360  |  18842252  |  HIV  |  h12  |  3  |  SUPT1  |  totalRNA |
| SRR1106195  |  peng  |  3183257700  |  17684765  |  mock  |  h12  |  1  |  SUPT1  |  totalRNA |
| SRR1106196  |  peng  |  2590251300  |  14390285  |  mock  |  h12  |  2  |  SUPT1  |  totalRNA |
| SRR1106197  |  peng  |  4100494860  |  22780527  |  mock  |  h12  |  3  |  SUPT1  |  totalRNA |
| SRR1106198  |  peng  |  2854784160  |  15859912  |  mock  |  h24  |  1  |  SUPT1  |  totalRNA |
| SRR1106199  |  peng  |  3302333640  |  18346298  |  mock  |  h24  |  3  |  SUPT1  |  totalRNA |
| SRR1106200  |  peng  |  3542572800  |  19680960  |  UV  |  h12  |  1  |  SUPT1  |  totalRNA |
| SRR1106201  |  peng  |  2943555120  |  16353084  |  UV  |  h12  |  2  |  SUPT1  |  totalRNA |
| SRR1106202  |  peng  |  3327833340  |  18487963  |  UV  |  h12  |  3  |  SUPT1  |  totalRNA |
| SRR1106203  |  peng  |  2751417720  |  15285654  |  UV  |  h24  |  1  |  SUPT1  |  totalRNA |
| SRR1106204  |  peng  |  3402487800  |  18902710  |  UV  |  h24  |  3  |  SUPT1  |  totalRNA |
| SRR1852858  |  bushman  |  23477460706  |  116225053  |  mock  |  h48  |  1  |  primary  |  polyA |
| SRR1852859  |  bushman  |  23739869412  |  117524106  |  mock  |  h48  |  2  |  primary  |  polyA |
| SRR1852860  |  bushman  |  23672186888  |  117189044  |  HIV  |  h48  |  1  |  primary  |  polyA |
| SRR1852861  |  bushman  |  22833920622  |  113039211  |  HIV  |  h48  |  2  |  primary  |  polyA |
| SRR1852881  |  bushman  |  23608835850  |  116875425  |  HIV  |  h48  |  3  |  primary  |  polyA |
