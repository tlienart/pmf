# pmf

## Installing PDMP

(Julia 0.5, x64 architecture)

```julia
Pkg.clone("https://github.com/alan-turing-institute/PDMP.jl.git")
```

## Data and preprocessing

Using the MovieLens 1M [Download](http://files.grouplens.org/datasets/movielens/ml-1m.zip).

File we care about `ratings.dat`.

```bash
wc -l ratings.dat
...
1000209 ratings.dat
```

It's got a crappy format


```bash
head ratings.dat
...
1::1193::5::978300760
1::661::3::978302109
1::914::3::978301968
```

The last column is a time stamp, we can get rid of the `::` with `sed`

```bash
sed s/::/,/g ratings.dat > ratings_filtered.csv
```

Put that in the `data/` folder.
