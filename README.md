ruby-opensourceapi
==================

`haskell-opensource` is an API Wrapper that allows you to query the
Open Source License API with Haskell.

Example
-------

```haskell
import Network.Protocol.OpenSource.License (licenseById, olName)
import Control.Monad.Trans.Except (runExceptT)

main = do
    gpl <- runExceptT $ licenseById "LGPL-3.0"
    putStrLn $ case gpl of
        Right license -> show $ olName license
        Left  error   -> "Error during license request!" ++ show error
```

Installing
----------

```
cabal install opensource
```
