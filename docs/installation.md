# Installation

## Stable release

To install `proteinsolver` into a new conda environment, run the following command:

```bash
conda create -n proteinsolver -c conda-forge -c kimlab -c ostrokach-forge proteinsolver
conda activate proteinsolver
```

This is the preferred method to install `proteinsolver`, as it will always install the most recent stable release and will also install all dependencies.

If you don't have [conda] installed, this [Python installation guide] can guide
you through the process.

[conda]: https://conda.io
[Python installation guide]: https://conda.io/docs/user-guide/install/index.html

## From sources

The sources for `proteinsolver` can be downloaded from the [GitLab repo].

You can either clone the public repository:

```bash
git clone git://gitlab.com/ostrokach/proteinsolver
```

Or download the [tarball]:

```bash
curl -OL https://gitlab.com/ostrokach/proteinsolver/repository/master/archive.tar
```

Once you have a copy of the source, you can install it with:

```bash
python setup.py install
```

***Warning: Using `pip` to install `proteinsolver` is not recommended since this method does not install the required dependencies.***

[GitLab repo]: https://gitlab.com/ostrokach/proteinsolver
[tarball]: https://gitlab.com/ostrokach/proteinsolver/repository/master/archive.tar
