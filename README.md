Overview of layers in the JuvThermhab_7DEC_thresholds_May2024.gdb

 1) threshold_scenarios_watersheds_salmonbearing

       Thermal threshold for juvenile salmon set to 24°C from experiments with juvenile Chinook and Coho.
       
       EC temperatures modelled using a refit version of BC AugTw model.  Total of 9 scenarios were considered to account for uncertainty in the model predictions and variation in thermal sensitivity:
              • Prediction Intervals: 75%, 85%, and 95%
              • Thermal sensitivity parameter: low (0.5), average (0.72), high (1.0)
       
       Temperature estimates were classified as OVER or UNDER the 24°C threshold, and whether the threshold was IN or OUT of the prediction interval to create 4 classes of decreasing thermal suitability:
              • UNDER_OUT, UNDER_IN, OVER_IN, OVER_OUT
       
       10-character  field naming conventions for temperature classifications:
              • First character indicates thermal sensitivity: a = average (0.72), l = low (0.5), h = high (1.0)
              • 2nd and 3rd characters indicate prediction interval: 75= 75%, 85 = 85%, 95 = 95%
              • 5th character indicates global climate model: 0 = historical data, 9 = 6-member ensemble average (see Weller et al. 2023 for details)
              • 7-8th character indicates climate scenarios: 00 = historical data, 45 = RCP 4.5
              • 10th character is 20-year time period: 0 = 1981-2000, 1 = 2001-2020, 2 = 2021-2040, 3 = 2041-2060, 4 = 2061-2080, 5 = 2081-2100.
       
       For example, 'a85_9_45_5' is the classification of the EC prediction using the average thermal sensitivity and 85% prediction interval for the RCP 4.5 ensemble average in 2081-2100.

2) threshold_scenarios_salmonaccessible

Thermal threshold for juvenile salmon set to 24°C from experiments with juvenile Chinook and Coho.

EC temperatures modelled using a refit version of BC AugTw model.  Total of 9 scenarios were considered to account for uncertainty in the model predictions and variation in thermal sensitivity:
       •	Prediction Intervals: 75%, 85%, and 95%
       •	Thermal sensitivity parameter: low (0.5), average (0.72), high (1.0)

Temperature estimates were classified as OVER or UNDER the 24°C threshold, and whether the threshold was IN or OUT of the prediction interval to create 4 classes of decreasing thermal suitability:
       •	UNDER_OUT, UNDER_IN, OVER_IN, OVER_OUT

10-character  field naming conventions for temperature classifications:
       •	First character indicates thermal sensitivity: a = average (0.72), l = low (0.5), h = high (1.0)
       •	2nd and 3rd characters indicate prediction interval: 75= 75%, 85 = 85%, 95 = 95%
       •	5th character indicates global climate model: 0 = historical data, 9 = 6-member ensemble average (see Weller et al. 2023 for details)
       •	7-8th character indicates climate scenarios: 00 = historical data, 45 = RCP 4.5
       •	10th character is 20-year time period: 0 = 1981-2000, 1 = 2001-2020, 2 = 2021-2040, 3 = 2041-2060, 4 = 2061-2080, 5 = 2081-2100.

For example, 'a85_9_45_5' is the classification of the EC prediction using the average thermal sensitivity and 85% prediction interval for the RCP 4.5 ensemble average in 2081-2100.



3)	FRB_network_riparian_restoration_100m_segments
   
       Estimated delta Tw from delta canopy opening angle (Beechie et al. 2021, HARP model). Delta canopy opening angle calculated at 100-m intervals along the stream network for the Fraser basin. 'Current' canopy height estimated from GLAD_2020 forest height layer (~30m resolution, resampled to 25m to match provincial DEMs). 'Potential' canopy height estimated as the 80th percentile of current canopy height by biogeoclimatic zones for all non-water or glacier area within BC. 80th percentile is likely a conservative estimate of potential height. Where potential height was less than current height, potential height was revised to equal current (this ensure potential height is always at least as high as current conditions). Canopy opening angle was calculated separately for single and double-line rivers. 
       
       For single-line rivers:
       •	channel width was estimated using Fig 2 eqn in Eaton and Davidson 2022;
       •	canopy height was estimated at the sample point (i.e., along the stream line); canopy height along both banks was assumed identical (canopy layer resolution much coarser than predicted channel widths);
       •	topography not considered (e.g., bank height ignored due to insufficient resolution).
       
       For double-line rivers:
       •	transects were drawn perpendicular to flow direction and spanned 100m beyond the bank;
       •	canopy heights were added to provincial DEM to account for bank height and riparian topography since most double line rivers were wider than the canopy layer resolution;
       •	canopy heights were extracted at 10m intervals along the transect on each bank; maximum canopy angle (stream surface to canopy) was identified on each bank.
       
       Key data fields:
       •	opening_current: current conditions (~2020) canopy opening angle
       •	opening_potential: natural potential conditions canopy opening angle
       •	delta_opening: difference between current and potential opening angles
       •	delta_tw: predicted delta Tw based on delta_opening
       •	a85_0_00_1: scenario classification for 2001-2020 period based on EC predictions with average thermal sensitivity value and 85% prediction interval (current classification)
                       UNDER_OUT, UNDER_IN, OVER_IN, OVER_OUT
       •	a85_9_45_5: scenario classification for 2081-2100 period based on EC predictions with average thermal sensitivity value and 85% prediction interval under RCP45 ensemble
  	        (predicted future classification, assuming current canopy conditions)
                     	UNDER_OUT, UNDER_IN, OVER_IN, OVER_OUT
       •	rip_9_45_5: reclassification of a85_9_45_5 after applying delta_tw to EC predictions (predicted future classification, assuming natural potential canopy conditions)
                     	UNDER_OUT, UNDER_IN, OVER_IN, OVER_OUT


