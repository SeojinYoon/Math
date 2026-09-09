# Mahalanobis Distance

$$
D^2 = (\mu_A - \mu_B)^T \mathbf{\Sigma}^{-1} (\mu_A - \mu_B)
$$

## The Role of the Precision Matrix ($\mathbf{\Sigma}^{-1}$)

The precision matrix, $\mathbf{\Sigma}^{-1}$, defines a statistical metric that accounts for the covariance structure of the measurements rather than treating all dimensions as independent and equally scaled.

Its specific interpretation depends on **what covariance matrix $\mathbf{\Sigma}$ represents and the purpose of the analysis**.

### General Mahalanobis Distance

In the general case, $\mathbf{\Sigma}$ represents the covariance structure of the data.

The purpose is not necessarily to remove or normalize noise. Instead, Mahalanobis distance measures the difference between observations while accounting for the directions in which the data naturally vary together.

Therefore,

$$
\text{General Mahalanobis}
\rightarrow
\text{covariance-normalized distance}
$$

### Noise-Normalized Mahalanobis Distance in RSA / fMRI

In RSA or fMRI pattern analysis, the purpose is more specific: we want to compare condition-specific activation patterns while reducing the influence of measurement noise.

In this case, $\mathbf{\Sigma}$ is chosen to represent the **noise covariance** rather than the total covariance of the data.

The precision matrix then accounts for two important properties of the noise:

- **Individual noise normalization:** Dimensions with larger noise variance contribute less to the distance, effectively down-weighting noisier voxels.
- **Shared noise correction:** Correlated noise between voxels is taken into account, so directions in which multiple voxels commonly fluctuate together due to noise contribute less strongly.

Therefore,

$$
\text{RSA / fMRI Mahalanobis}
\rightarrow
\text{noise-normalized representational distance}
$$

Importantly, this is **not direct denoising**. Noise is not subtracted from the beta patterns. Instead, the distance metric is adjusted according to the estimated noise structure so that unreliable or strongly noise-correlated directions contribute less to the final distance.

---

## Mahalanobis Distance as Whitening

Mahalanobis distance can equivalently be interpreted as Euclidean distance after whitening:

$$
D^2
=
\left(
\mathbf{\Sigma}^{-1/2}(\mu_A-\mu_B)
\right)^T
\left(
\mathbf{\Sigma}^{-1/2}(\mu_A-\mu_B)
\right)
$$

Thus,

$$
\mathbf{\Sigma}^{-1}
\rightarrow
\text{Mahalanobis metric}
$$

whereas

$$
\mathbf{\Sigma}^{-1/2}
\rightarrow
\text{whitening transformation}.
$$

In the general Mahalanobis distance, whitening removes the covariance structure represented by $\mathbf{\Sigma}$.

In RSA/fMRI, because $\mathbf{\Sigma}$ is specifically chosen to represent noise covariance, whitening becomes **noise normalization**.

---

## Estimating $\mathbf{\Sigma}$: Why Use Residual or Within-Condition Variability?

Mahalanobis distance itself does **not** require $\mathbf{\Sigma}$ to be estimated from residuals.

The appropriate covariance matrix depends on the purpose of the analysis.

If the goal is simply to account for the overall covariance structure of the data, $\mathbf{\Sigma}$ may be estimated from the total data.

However, if the goal is to compare class or condition means while normalizing measurement noise, as in RSA/fMRI, $\mathbf{\Sigma}$ should ideally represent **within-condition noise variability rather than total covariance**.

The reason is that total covariance may contain both:

$$
\text{between-condition signal variance}
+
\text{within-condition noise variance}.
$$

If the between-condition signal is included in $\mathbf{\Sigma}$, genuine differences between conditions may themselves influence the metric used to normalize those differences.

Therefore, in noise-normalized classification or representational analyses, $\mathbf{\Sigma}$ is typically estimated from variability remaining after the condition-related signal structure has been removed.

### Standard Statistics / Classification

For repeated observations within a class or condition, this variability can be estimated by subtracting the corresponding class mean:

$$
\mathbf{\epsilon}_{i,c}
=
\mathbf{x}_{i,c}
-
\mathbf{\mu}_c
$$

The covariance of these deviations,

$$
\mathbf{\Sigma}_{noise}
=
\operatorname{Cov}(\mathbf{\epsilon}),
$$

reflects within-class or within-condition variability while excluding the mean differences between classes.

### fMRI Analysis: First-Level GLM

In fMRI, the same principle is commonly implemented using GLM residuals.

Given

$$
\mathbf{Y}
=
\mathbf{X}\mathbf{\beta}
+
\mathbf{\epsilon},
$$

the estimated residuals are

$$
\hat{\mathbf{\epsilon}}
=
\mathbf{Y}
-
\mathbf{X}\hat{\mathbf{\beta}}.
$$

These residuals represent the variability that remains unexplained by the modeled task regressors.

The voxel-by-voxel covariance of these residuals can then be used to estimate the noise covariance:

$$
\mathbf{\Sigma}_{noise}
=
\operatorname{Cov}(\hat{\mathbf{\epsilon}})
$$

and its inverse gives the corresponding noise precision matrix:

$$
\mathbf{\Sigma}_{noise}^{-1}.
$$

Thus, the general principle for noise-normalized Mahalanobis distance is:

$$
\boxed{
\text{remove the signal structure of interest}
\rightarrow
\text{estimate remaining covariance}
\rightarrow
\mathbf{\Sigma}_{noise}
\rightarrow
\mathbf{\Sigma}_{noise}^{-1}
}
$$

The exact method depends on the analysis. With repeated measurements, this may involve subtracting class or condition means. In first-level fMRI analysis, it is commonly achieved using GLM residuals.

### Core Principle

The distinction is therefore not simply **"Mahalanobis distance uses residuals."**

Rather:

$$
\boxed{
\text{The source of }\mathbf{\Sigma}
\text{ depends on what variability we want the distance to normalize.}
}
$$

For a general Mahalanobis distance, $\mathbf{\Sigma}$ can describe the overall covariance structure of the data.

For noise-normalized RSA/fMRI, $\mathbf{\Sigma}$ is specifically estimated to describe the noise covariance structure.

Using total covariance in this context could mix task-related differences with measurement noise. Estimating $\mathbf{\Sigma}$ from within-condition deviations or GLM residuals instead aims to characterize the covariance of variability that is not explained by the signal of interest.

Importantly, GLM residuals should not be interpreted as pure physiological or scanner noise. They contain all variability not explained by the fitted model, including physiological noise, scanner noise, motion-related effects, and potentially unmodeled neural activity.

---

## Spatial Whitening

### Analogy: Choir and Singers

Imagine that each voxel is a microphone recording one singer in a choir. Our goal is to compare the overall pattern of singing across different sections of a song.

However, the microphone signals contain noise with two important properties:

1. **Individual noise:** Some singers or microphones are inherently more variable than others. This corresponds to voxel-specific noise variance.
2. **Shared noise:** Multiple microphones may fluctuate together because of common disturbances, such as vibrations in the concert hall. This corresponds to noise covariance between voxels.

By observing the fluctuations that remain after accounting for the song being performed, we can estimate how unstable each microphone is and which microphones tend to fluctuate together.

To compare the singing patterns fairly, we do not subtract these fluctuations directly from the measured singing patterns. Instead, we use their covariance structure to determine how much each direction of pattern difference should be trusted.

A difference along a highly unstable direction is given less weight. Likewise, if several microphones commonly fluctuate together because of shared noise, a difference following that same direction is also given less weight.

Thus, in RSA/fMRI:

$$
\boxed{
\text{Residuals tell us how the microphones tend to fluctuate}
}
$$

$$
\boxed{
\text{The precision matrix tells us how much to trust each pattern difference}
}
$$

Mahalanobis distance therefore compares condition-specific patterns after accounting for both the reliability of individual voxels and the shared noise structure across voxels, rather than directly removing noise from the beta patterns.

## RSA toolbox

In RSA toolbox, there are two main approaches to estimate the noise covariance structure.

Here, noise can be understood as variability that is not explained by the signal of interest.

- **Noise estimated from measurement variability**
  - `prec_from_measurements`
  - Estimates the noise covariance matrix from repeated measurements.
  - It removes the mean pattern of each condition and uses the remaining **within-condition variability** to estimate the noise covariance.

- **Noise estimated from residuals**
  - `prec_from_residuals`
  - Estimates the noise covariance matrix from residuals.
  - It uses variability that remains after the fitted model has explained the modeled signal.

### Which one is better?

It mainly depends on how well the noise covariance can be estimated from the available samples.

`prec_from_residuals` often has an advantage because GLM residuals usually provide many time points. Therefore, the noise covariance can often be estimated more robustly.

In contrast, `prec_from_measurements` may have relatively few samples when the number of repetitions per condition is small. This can make the estimated noise covariance less stable and increase its uncertainty.

However, if many repeated measurements are available, `prec_from_measurements` can also provide a stable estimate of the noise covariance.

Therefore, neither method is always better. The preferable method depends on the amount and quality of the available residuals or repeated measurements.