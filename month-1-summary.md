# Month 1 Summary: Wammakko Health Access Analysis

## Research Question
Which wards in Wammakko Local Government Area have settlements that sit more than 5 km away from a primary healthcare facility?

## Spatial Operation Ran
- **Operation:** Buffer (5,000 meters)
- **Reason:** To calculate physical healthcare accessibility zones across Wammakko LGA using projected units (EPSG:32631).

## Expectations
I expect the 5 km buffer tool to generate 25 individual circular polygons around the health facilities in Wammakko LGA. Given the heavy concentration of health facilities in the east, I expect substantial overlap in the eastern settlements, while the remote settlements in the north and west will fall outside the 5 km coverage zone.

## Actual Results
- **Output:** 25 circular buffer polygons (5 km radius each).
- **Observation:** The actual map confirms heavy buffer overlap in eastern Wammakko, leaving large clusters of rural settlements in the central, western, and northern wards completely outside the 5 km catchment area.

## Surprises & Observations
- Despite using a generous 5 km buffer radius, significant geographical gaps exist across rural Wammakko, highlighting severe spatial inequality in healthcare access.

## Outstanding Data Needs
- Population data per settlement to quantify the exact percentage of residents living outside the 5 km catchment area.