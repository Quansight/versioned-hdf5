Versioned HDF5 Change Log
=========================

## 1.2.1 (2020-12-30)

## Minor Changes

- Python 3.6 support has been dropped. The lowest version of Python now
  supported is 3.7.
- Fix creating a completely empty sparse dataset
- Use ndindex.ChunkSize internally. This is the beginning of an overhaul that
  improves the performance of many operations. ndindex 1.5 or newer is now
  required.

## 1.2 (2020-11-17)

## Major Changes

- Add support for sparse datasets (`data=None`).
- Store the chunks on an attribute of the dataset.
- versioned-hdf5 is currently pinned to `h5py<3`. h5py 3 support will be added
  in a future version.
- `VersionedHDF5File[timestamp]` now returns the closest version before
  `timestamp` if there is no version at `timestamp`.

## 1.1 (2020-09-15)

### Major Changes

* Added support for shape-0 datasets.
* Fix a memory leak where in-memory datasets would not be garbage collected.
* Added support for empty datasets (size 0).
* Make sure versioned data is read-only after closing and reopening the file.
* Allow deleting groups and datasets between versions. Note that currently
  dataset metadata cannot change between versions, even if they are deleted in
  between.

### Minor Changes

* Most tests now use a temporary directory instead of writing a file in the
  current directory.
* Fix logic for handling trailing slashes with `in`.
* Automatically create intermediate groups when creating a dataset.
* Make indices that should give a scalar object do so instead of giving a
  shape () array.

## 1.0 (2020-08-03)

### Major Changes

* First release of Versioned-HDF5.
