# Configuration properties

[![Build Status (Travis)](https://travis-ci.org/skapral/configproperties.svg?branch=master)](https://travis-ci.org/skapral/configproperties)
[![Build status (AppVeyor)](https://ci.appveyor.com/api/projects/status/7d81mlu98r108krk/branch/master?svg=true)](https://ci.appveyor.com/project/skapral/configproperties/branch/master)
[![Codecov](https://codecov.io/gh/skapral/configproperties/branch/master/graph/badge.svg)](https://codecov.io/gh/skapral/configproperties)

A set of simple objects for reading configuration

## Quick start

Add Maven dependency

```
<dependency>
    <groupId>com.github.skapral.config</groupId>
    <artifactId>config-properties</artifactId>
    <version>x.y.z</version>
</dependency>
```

## Examples

1. Hardcoded HTTP port:

```
ConfigProperty port = new CpStatic(
    "8080"
);
```

2. HTTP port, read from PORT environment value:

```
ConfigProperty port = new CpEnvironment(
    "PORT"
);
```

3. HTTP port, read from PORT environment variable (default 5000 if there is no environment variable):

```
ConfigProperty port = new CpOneOf(
    new CpEnvironment(
        "PORT"
    ),
    new CpStatic(
        "8080"
    )
);
```