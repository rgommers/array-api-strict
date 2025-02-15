# array-api-strict Changelog

## 1.0 (????)

This is the first release of `array_api_strict`. It is extracted from
`numpy.array_api`, which was included as an experimental submodule in NumPy
versions prior to 2.0. Note that the commit history in this repository is
extracted from the git history of numpy/array_api/ (see the [README](README.md)).

Additionally, the following changes are new to `array_api_strict` from
`numpy.array_api` in NumPy 1.26 (the last NumPy feature release to include
`numpy.array_api`):

- ``array_api_strict`` was made more portable. In particular:

  - ``array_api_strict`` no longer uses ``"cpu"`` as its "device", but rather a
    separate ``CPU_DEVICE`` object (which is not accessible in the namespace).
    This is because "cpu" is not part of the array API standard.

  - ``array_api_strict`` now uses separate wrapped objects for dtypes.
    Previously it reused the ``numpy`` dtype objects. This makes it clear
    which behaviors on dtypes are part of the array API standard (effectively,
    the standard only requires ``==`` on dtype objects).

- ``numpy.array_api.nonzero`` now errors on zero-dimensional arrays, as
    required by the array API standard.

- Support for the optional [fft
  extension](https://data-apis.org/array-api/latest/extensions/fourier_transform_functions.html)
  was added.
