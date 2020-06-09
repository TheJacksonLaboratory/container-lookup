# Container-Lookup

Here's a list of curated docker and singularity containers available on the
web.

## Contributing

If you want to add a new tool, fork the repo and add a new line to
`externals.csv`. Then open a pull request.

## Usage

Two options:
1.  Just look at the CSV.
2.  Run the script `container-lookup`

### Script usage

Find containers interactively:
```{bash}
> container-lookup lftp
docker://dockito/lftp-client
```

List all containers:
```{bash}
> container-lookup --list
lftp,docker://dockito/lftp-client
...
```

Use it in a pipeline or something:
```{bash}
img=$(container-lookup QUERY -q)
[[ ! -z $img ]] && singularity run $img ... || echo "Couldn't find a container"
```

### Running on sumner

```{bash}
> module use -a /projects/robson-lab/modules
> module load container-lookup
> container-lookup 
```
