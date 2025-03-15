# Prophet Hyperparameters

Here's a comprehensive list of the key hyperparameters available in Prophet:

## Core Model Parameters
1. changepoint_prior_scale (default: 0.05)
  - Controls flexibility of the trend
  - Higher values allow more frequent trend changes (more wiggle)
  - Lower values create a more rigid trend line
  - Range: typically 0.001 to 0.5
2. seasonality_prior_scale (default: 10.0)
  - Controls strength of seasonality
  - Higher values allow stronger seasonal patterns
  - Lower values dampen seasonal effects
  - Range: typically 0.01 to 10.0
3. holidays_prior_scale (default: 10.0)
  - Controls impact of holidays on the forecast
  - Higher values allow holidays to have larger effects
  - Range: typically 0.01 to 10.0
4. seasonality_mode (default: 'additive')
  - Options: 'additive' or 'multiplicative'
  - Additive: seasonal effects are constant
  - Multiplicative: seasonal effects scale with trend level
5. changepoint_range (default: 0.8)
  - Proportion of history where changepoints are placed
  - 0.8 means changepoints only placed in first 80% of time series
  - Range: 0 to 1

## Specific Components

6. growth (default: 'linear')
  - Options: 'linear' or 'logistic'
  - Logistic requires setting capacity (carrying capacity for growth)
7. daily_seasonality (default: 'auto')
  - Options: True, False, or 'auto'
  - Controls whether daily seasonality is included
8. weekly_seasonality (default: 'auto')
  - Options: True, False, or 'auto'
  - Controls whether weekly seasonality is included
9. yearly_seasonality (default: 'auto')
  - Options: True, False, or 'auto'
  - Controls whether yearly seasonality is included

## Custom Seasonality Parameters

When adding custom seasonalities via add_seasonality():

10. period (required)
  - Period of the seasonality in days
11. fourier_order (default: 3)
  - Number of Fourier terms to use
  - Higher values allow more complex seasonal patterns
  - Typically 5-10 for yearly, 3-5 for weekly
12. prior_scale (default: uses seasonality_prior_scale)
  - Control strength of this specific seasonality
  - Can override the global seasonality_prior_scale
13. mode (default: uses seasonality_mode)
  - 'additive' or 'multiplicative' for this specific seasonality

## Additional Parameters

14. interval_width (default: 0.8)
  - Width of uncertainty intervals (80% by default)
  - Range: 0 to 1
15. mcmc_samples (default: 0)
  - Number of MCMC samples for parameter estimation
  - 0 uses MAP estimation, >0 uses MCMC for uncertainty
16. n_changepoints (default: 25)
  - Number of potential changepoints
