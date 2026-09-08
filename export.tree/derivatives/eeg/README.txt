The "./derivatives/eeg" directory contains the preprocessed EEG data. These are the data used in the technical validation analyses of this paper.

The preprocessed EEG data is stored as separate "./eeg/sub-0X/sub-0X_ses-0X_preprocessed_eeg.h5" files for every subject and recording session, where each file consists of an array of shape (Trials, Channels, Times).

In addition, each subject has a "./eeg/sub-0X/sub-0X_eeg_metadata.npy" EEG metadata file, consisting of a Python dictionary with the following key-value pairs:

- "stimulus_id": Dictionary of 8 items, one for each of the 8 recording sessions, containing the video stimulus ID of all session-trials that were retained after preprocessing. Possible values are in the range [1, 1102]. You can use these stimulus IDs to link the EEG trials to the corresponding video stimuli.
- "run_number": Dictionary of 8 items, one for each of the 8 recording sessions, containing the run number of all session-trials that were retained after preprocessing. Possible values are in the range [1, 16]. You can use the "run_number" together with the "trial_number" variables to link the EEG trials to the corresponding eye-tracking trials (only for trials that survived trial-rejection during the preprocessing of both data types).
- "trial_number": Dictionary of 8 items, one for each of the 8 recording sessions, containing the trial number of all session-trials that were retained after preprocessing. Possible values are in the range [1, 66]. Note that the trial numbers refer to the full EEG dataset prior to trial rejection during preprocessing. You can use the "trial_number" together with the "run_number" variables to link the EEG trials to the corresponding eye-tracking trials (only for trials that survived trial-rejection during the preprocessing of both data types).
- "ch_names": List of EEG channel names.
- "times": Array of epoched EEG time points, in seconds, with respect to stimulus onset.
- "ncsnr": Noise ceiling signal-to-noise ratio (NCSNR) scores, computed for each EEG channel and time point using the preprocessed EEG responses for the 102 test video, following the method proposed in the Natural Scenes Dataset paper (Allen et al., 2022; https://doi.org/10.1038/s41593-021-00962-x).
- "noise_ceiling": Noise ceiling scores, computed for each EEG channel and time point using the preprocessed EEG responses for the 102 test video, following the method proposed in the Natural Scenes Dataset paper (Allen et al., 2022; https://doi.org/10.1038/s41593-021-00962-x).
