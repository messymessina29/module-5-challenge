# module-5-challenge
I used the Xpert Learning Assistant a couple different times to aide me through this challenge.

The first instance was when it asked how to gather duplicate values in the Mice ID column as I was unaware of the duplicated method:
    dup_mice = combined_data_df[combined_data_df.duplicated(subset=['Mouse ID', 'Timepoint'], keep=False)]

The second instance was when it asked how to use the aggregate function to gather summary statistics which I also did not know how to use:
    summary_stats = clean_mice_df.groupby('Drug Regimen')['Tumor Volume (mm3)'].agg(['mean', 'median', 'var', 'std', 'sem'])

The third instance was when it asked how to calculate quartiles using a loop. I knew how to calculate the quartiles and any outliers in the data, but was unsure how to get values for each treatment and save it:
    
    for t in treatments:
    
    # Locate the rows which contain mice on each drug and get the tumor volumes
    treatment_data = max_merge.loc[max_merge['Drug Regimen'] == t, 'Tumor Volume (mm3)']
    
    # add subset 
    tumor_vol_data.append(treatment_data)
    
    