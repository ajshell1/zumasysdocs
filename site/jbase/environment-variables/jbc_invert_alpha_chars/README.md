# JBC_INVERT_ALPHA_CHARS

<PageHeader />

**Tags:**
<badge text='environment variables' vertical='middle' />

## Description

With this environment variable set the case of alphabetic characters entered with the jBC [INPUT](./../../jbc/input/README.md) statement is inverted.

## Values

1

## Default

None.

## Note

> The environment variable is ignored by the jBC [**IN**](./../../jbc/in) statement.

## Setting

It must be set before running a program otherwise the behavior of the INPUT statement is unaffected.

## UNIX

```
export JBC_INVERT_ALPHA_CHARS=1
```

## Windows

```
set JBC_INVERT_ALPHA_CHARS=1
```

Back to [Environment Variables](./../README.md)

<PageFooter />
