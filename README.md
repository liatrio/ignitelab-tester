# Pipeline for validating Ignitelab steps

##WARNING: This was tested in sandbox and is a WIP


This pipeline will execute the jenkins jobs for various solutions branches of the 
springtrader and springtrader-marketsummary for ignite labs. It in intended to 
be a semi-automated way of validating that the solutions in the ignite lab will
work properly for users.

It works by executing existing jobs on a jenkins instance in a consecutive order,
following the flow of the ignite lab.

Currently this only supports automation around lab 3-5 so the `springtrader` and
 `springtrader-marketplace` must have already been added via `@sparky add`


Note: this currently only validates labs 3-5, and expects that labs 1-2 will have
already been completed.



# Setup.

Make sure that you've completed labs 1,2 and this expects that your `sprintrader-marketsummary` is starting from 
the beginning of the lab.

1. `@sparky-sandbox add jknight-liatrio/springtrader-marketsummary`
1. `@sparky-sandbox add jknight-liatrio/ignitelab-tester`


Note: This process must be run end-to-end as the beginning of the process is a
`helm delete --purge marketsummary`


