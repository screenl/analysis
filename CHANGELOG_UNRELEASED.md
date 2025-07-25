# Changelog (unreleased)

## [Unreleased]

### Added

- in `unstable.v`:
  + lemma `subrKC`

- in `convex.v`:
  + definition `convex_quasi_associative`
    * implemented through a module `ConvexQuasiAssoc` containing
      `law` and helper lemmas
  + lemmas `convR_itv`, `convR_line_path`
- in `num_topology.v`
  + `topologicalType` instance on `R^o` for `R : numDomainType`

- in `tvs.v`
  + HB classes `TopologicalNmodule`, `TopologicalZmodule`, `TopologicalLmodule`
    `UniformNmodule`, `UniformZmodule`, `UniformLmodule`
  + notation `topologicalZmodType`
  + mixin `PreTopologicalNmodule_isTopologicalNmodule`,
    `TopologicalNmodule_isTopologicalZmodule`,
    `TopologicalZmodule_isTopologicalLmodule`,
    `PreUniformNmodule_isUniformNmodule`,
    `UniformNmodule_isUniformZmodule`,
    `PreUniformLmodule_isUniformLmodule`
  + structure `topologicalLmodule`
  + factories `PreTopologicalNmodule_isTopologicalZmodule`,
    `TopologicalNmodule_isTopologicalLmodule`,
    `PreUniformNmodule_isUniformZmodule`,
    `UniformNmodule_isUniformLmodule`
  + lemmas `sub_continuous`, `sub_unif_continuous`

- in `constructive_ereal.v`:
  + `inve` a total involutive inversion function on `\bar R`, denoted `^-1` in
     the `ereal_scope` coinciding with `x^-1%R` when `x != 0` but such that
     `0^-1 = +oo` and `-oo^-1 = -oo`,
  + notation `x / y` in `ereal_scope` for `x / y = x * y^-1`,
  + lemmas `inver`, `inveP`, `fine_invr`, `inve0`, `inve1`, `invey`, `invey`,
    `inveNy`, `inveK`, `invr_inj`, `inveN`, `inve_eq0`, `inve_ge0`, `inve_gt0`,
    `inv_gt0P`, `inve_lt0`, `inve_le0`, `inve_le0P`,
  + predicate `inveM_def` with notation `x *^-1? y` defining a sufficient
    condition for the inverse and product to commute, with lemmas `inveMP`,
    `inveM_defE`, `inveM` and `fin_inveM_def`,
  + compatibility lemma `mule_defE` to bridge the former definition of
    `mule_def` with the new one.
  + lemma `fin_numV`
  + lemmas `mulVe`, `lee_pV2`, `lte_pV2`, `ltee_pV2`, `inve_pge`, `inve_pgt`,
    `inve_ple`, `inve_plt`, `inve_gt1`, `inve_ge1`.

- in `lebesgue_integral_differentiation.v`:
  + lemma `nicely_shrinking_fin_num`

- in `normed_module.v`:
  + definition `pseudoMetric_normed`
  + factory `Lmodule_isNormed`
- in `num_normedtype.v`:
  + lemmas `gt0_cvgMrNy`, `gt0_cvgMry`

- in `probability.v`:
  + definition `exponential_pdf`
  + lemmas `exponential_pdf_ge0`, `lt0_exponential_pdf`,
    `measurable_exponential_pdf`, `exponential_pdfE`,
    `in_continuous_exponential_pdf`, `within_continuous_exponential_pdf`
  + definition `exponential_prob`
  + lemmas `derive1_exponential_pdf`, `exponential_prob_itv0c`,
    `integral_exponential_pdf`, `integrable_exponential_pdf`
- in `exp.v`
  + lemma `expR_ge1Dxn`
- in `classical_sets.v`
  + lemma `bigcup_mkord_ord`

- in `measure.v`:
  + definition `g_sigma_preimage`
  + lemma `g_sigma_preimage_comp`
  + definition `measure_tuple_display`
  + lemma `measurable_tnth`
  + lemma `measurable_fun_tnthP`
  + lemma `measurable_cons`
  + lemma `measurable_behead`

- in `lebesgue_integral_theory/lebesgue_integral_nonneg.v`:
  + lemmas `ge0_nondecreasing_set_nondecreasing_integral`,
           `ge0_nondecreasing_set_cvg_integral`,
           `le0_nondecreasing_set_nonincreasing_integral`,
	   `le0_nondecreasing_set_cvg_integral`
  + lemmas `sintegral_le_measure`, `ge0_integral_le_measure`

- in `set_interval.v`:
  + lemma `memB_itv`, `memB_itv0`
- in `lebesgue_integrable.v`:
  + lemma `integral_sum`

- in `constructive_ereal.v`:
  + lemmas `abse_prod`

- in `hoelder.v`:
  + lemmas `Lnorm_abse`, `Lfun_norm`
- in `lebesgue_integral_fubini.v`:
  + lemmas `integral21_prod_meas2`, `integral12_prod_meas2`

- in `lebesgue_integral_nonneg.v`:
  + lemma `ge0_integral_ereal_sup` (was a `Let`)

### Changed

- in `convex.v`:
  + convex combination operator `a <| t |> b` changed from
    `(1-t)a + tb` to `ta + (1-t)b`

- in `sequences.v`:
  + lemma `subset_seqDU`

- in `measure.v`:
  + lemmas `seqDU_measurable`, `measure_gt0`
  + notations `\forall x \ae mu, P`, `f = g %[ae mu in D]`, `f = g %[ae mu]`
  + instances `ae_eq_equiv`, `comp_ae_eq`, `comp_ae_eq2`, `comp_ae_eq2'`, `sub_ae_eq2`
  + lemma `ae_eq_comp2`
  + lemma `ae_foralln`
  + lemma `ae_eqe_mul2l`
  + definition `pushforward` (to take a function instead of a proof)

- new file `ess_sup_inf.v`:
  + lemma `measure0_ae`
  + definition `ess_esup`
  + lemmas `ess_supEae`, `ae_le_measureP`, `ess_supEmu0`, `ess_sup_ge`,
    `ess_supP`, `le_ess_sup`, `eq_ess_sup`, `ess_sup_cst`, `ess_sup_ae_cst`,
    `ess_sup_gee`, `abs_sup_eq0_ae_eq`, `abs_ess_sup_eq0`, `ess_sup_pZl`,
    `ess_supZl`, `ess_sup_eqNyP`, `ess_supD`, `ess_sup_absD`
  + notation `ess_supr`
  + lemmas `ess_supr_bounded`, `ess_sup_eqr0_ae_eq`, `ess_suprZl`,
    `ess_sup_ger`, `ess_sup_ler`, `ess_sup_cstr`, `ess_suprD`, `ess_sup_normD`
  + definition `ess_inf`
  + lemmas `ess_infEae`, `ess_infEN`, `ess_supEN`, `ess_infN`, `ess_supN`,
    `ess_infP`, `ess_inf_le`, `le_ess_inf`, `eq_ess_inf`, `ess_inf_cst`,
    `ess_inf_ae_cst`, `ess_inf_gee`, `ess_inf_pZl`, `ess_infZl`, `ess_inf_eqyP`,
    `ess_infD`
  + notation `ess_infr`
  + lemmas `ess_infr_bounded`, `ess_infrZl`, `ess_inf_ger`, `ess_inf_ler`,
    `ess_inf_cstr`

- in `simple_functions.v`:
  + lemma `mfunMn`

- in `hoelder.v`
  + lemmas `Lnorm0`, `Lnorm_cst1`
  + definition `hoelder_conjugate`
  + lemmas `hoelder_conjugate0`, `hoelder_conjugate1`, `hoelder_conjugate2`,
    `hoelder_conjugatey`, `hoelder_conjugateK`
  + lemmas `lerB_DLnorm`, `lerB_LnormD`, `eminkowski`
  + definition `finite_norm`
  + mixin `isLfunction` with field `Lfunction_finite`
  + structure `Lfunction`
  + notation `LfunType`
  + definition `Lequiv`
  + canonical `Lequiv_canonical`
  + definition `LspaceType`
  + lemma `LequivP`
  + record `LType`
  + coercion `LfunType_of_LType`
  + definition `Lspace` with notation `mu.-Lspace p`
  + lemma `Lfun_integrable`, `Lfun1_integrable`, `Lfun2_integrable_sqr`, `Lfun2_mul_Lfun1`
  + lemma `Lfun_scale`, `Lfun_cst`,
  + definitions `finLfun`, `Lfun`, `Lfun_key`
  + canonical `Lfun_keyed`
  + lemmas `sub_Lfun_mfun`, `sub_Lfun_finLfun`
  + definition `Lfun_Sub`
  + lemmas `Lfun_rect`, `Lfun_valP`, `LfuneqP`, `finite_norm_cst0`, `mfunP`, `LfunP`,
    `mfun_scaler_closed`
  + lemmas `LnormZ`, `Lfun_submod_closed`
  + lemmas `finite_norm_fine`, `ler_LnormD`,
    `LnormrN`, `fine_Lnormr_eq0`
  + lemma `fine_Lnormr_eq0`
  + lemma `Lfun_subset`, `Lfun_subset12`
  + lemma `Lfun_oppr_closed`
  + lemma `Lfun_addr_closed`
  + lemmas `poweR_Lnorm`, `oppe_Lnorm`
  + lemma `integrable_poweR`

- in `hoelder.v`:
  + lemmas `hoelder_conjugate_div`, `hoelder_div_conjugate`,
    `hoelder_Mconjugate`, `hoelder_conjugateP`,
    `hoelder_conjugate_eq1`, `hoelder_conjugate_eqNy`, `hoelder_conjugate_eqy`,
    `hoelder_conjugateNy`

- in `constructive_ereal.v`:
  + lemmas `div1e`, `divee`, `inve_eq1`, `Nyconjugate`

### Changed

- in `measure.v`:
  + notation `{ae mu, P}` (near use `{near _, _}` notation)
  + definition `ae_eq`
  + `ae_eq` lemmas now for `ringType`-valued functions (instead of `\bar R`)

- in `convex.v`:
  + definition `convex_realDomainType` generalized and
    renamed accordingly `convex_numDomainType`
- in `tvs.v`
  + HB class `UniformZmodule` now contains `TopologicalZmodule`
  + HB class `UniformLmodule` now contains `TopologicalLmodule`

- in `constructive_ereal.v`:
  + `mule` has special cases optimizing computation for +oo and -oo
  + `mule_def` has been rewritten to optimize computation in several cases.

- in `lebesgue_integral_nonneg.v`:
  + lemma `integral_abs_eq0` (remove redundant hypotheses)

- in `lebesgue_integral_differentiation.v`:
  + definition `iavg` (to use `inve`)

- in `measure.v`:
  + fourth argument of `probability_setT` is now explicit

- in `hoelder.v`:
  + generalized the quotient of Lspaces to all measurable functions rather than just Lp functions.
  + consequently,
    * updated notation for measurable functions from `LfunType` to `{mfun_ mu , U >-> V }`
    * renamed definitions and lemmas from `Lequiv`, `Lequiv_refl`, `Lequiv_sym`, `Lequiv_trans`,
      `LspaceType` to `ae_eq_op`, `ae_eq_op_refl`, `ae_eq_op_sym`, `ae_eq_op_trans`, `aeEqMfun`
   * renamed lemma `LequivP` to `ae_eqP`


### Renamed

- in `measure.v`
  + definition `ess_sup` moved to `ess_sup_inf.v`

- in `convex.v`
  + lemma `conv_gt0` to `convR_gt0`
- in `tvs.v`
  + HB class `TopologicalNmodule` moved to `PreTopologicalNmodule`
  + HB class `TopologicalZmodule` moved to `PreTopologicalZmodule`
  + HB class `TopologicalLmodule` moved to `PreTopologicalLmodule`
  + structure `topologicalLmodule` moved to `preTopologicalLmodule`
  + HB class `UniformNmodule` moved to `PreUniformNmodule`
  + HB class `UniformZmodule` moved to `PreUniformZmodule`
  + HB class `UniformLmodule` moved to `PreUniformLmodule`

- in `hoelder.v`:
  + `minkowski` -> `minkowski_EFin`

- in `lebesgue_integral_fubiniv.`:
  + `fubini1` -> `integral12_prod_meas1`
  + `fubini2` -> `integral21_prod_meas1`
- in `normed_module.v`:
  + `cvgZl` -> `cvgZr_tmp`
  + `is_cvgZl` -> `is_cvgZr_tmp`
  + `cvgZr` -> `cvgZl_tmp`
  + `is_cvgZr` -> `is_cvgZl_tmp`
  + `is_cvgZrE` -> `is_cvgZlE`
  + `cvgMl` -> `cvgMr_tmp`
  + `cvgMr` -> `cvgMl_tmp`
  + `is_cvgMr` -> `is_cvgMl_tmp`
  + `is_cvgMrE` -> `is_cvgMlE_tmp`
  + `is_cvgMl` -> `is_cvgMr_tmp`
  + `is_cvgMlE` -> `is_cvgMrE_tmp`
  + `limZl` -> `limZr_tmp`
  + `limZr` -> `limZl_tmp`
  + `continuousZr` -> `continuousZl_tmp`
  + `continuousZl` -> `continuousZr_tmp`
- in `realfun.v`:
  + `variationD` -> `variation_cat`

- in `lebesgue_integrable.v`:
  + `integral_fune_lt_pinfty` -> `integrable_lty`
  + `integral_fune_fin_num` -> `integrable_fin_num`

### Generalized

- in `derive.v`:
  + `derive_cst`, `derive1_cst`
- in `convex.v`
  + parameter `R` of `convType` from `realDomainType` to `numDomainType`
- in `hoelder.v`:
  + definition `Lnorm` generalized to functions with codomain `\bar R`
    (this impacts the notation `'N_p[f]`)
  + lemmas `Lnorm1`, `eq_Lnorm`, `Lnorm_counting` (from `f : _ -> R` to `f : _ -> \bar R`)

- in `probability.v`
  + lemma `cantelli`
  + lemmas `expectation_fin_num`, `expectationZl`, `expectationD`, `expectationB`, `expectation_sum`,
    `covarianceE`, `covariance_fin_num`, `covarianceZl`, `covarianceZr`, `covarianceNl`,
    `covarianceNr`, `covarianceNN`, `covarianceDl`, `covarianceDr`, `covarianceBl`, `covarianceBr`,
     `varianceE`, `variance_fin_num`, `varianceZ`, `varianceN`, `varianceD`, `varianceB`,
     `varianceD_cst_l`, `varianceD_cst_r`, `varianceB_cst_l`, `varianceB_cst_r`, `covariance_le`

- in `derive.v`:
  + lemmas `is_deriveX`, `deriveX`, `exp_derive`, `exp_derive1`

- in `lebesgue_integrable.v`:
  + lemma `integrable_sum`

### Deprecated

- in `set_interval.v`:
  + lemma `mem_1B_itvcc`

### Removed

- in `measure.v`:
  + definition `almost_everywhere_notation`
  + lemma `ess_sup_ge0`

- in `exp.v`:
  + notation `expRMm` (deprecated since 1.1.0)

- in `constructive_ereal.v`:
  + notations `lee_addl`, `lee_addr`, `lee_add2l`, `lee_add2r`, `lee_add`,
    `lee_sub`, `lee_add2lE`, `lee_oppl`, `lee_oppr`, `lte_oppl`, `lte_oppr`,
    `lte_add`, `lte_add2lE`, `lte_addl`, `lte_addr` (deprecated since 1.1.0)

- in `measure.v`:
  + notations `sub_additive`, `sigma_sub_additive`, `content_sub_additive`,
    `ring_sigma_sub_additive`, `Content_SubSigmaAdditive_isMeasure.Build`,
    `measure_sigma_sub_additive`, `measure_sigma_sub_additive_tail`,
    `Measure_isSFinite_subdef.Build`, `sfinite_measure_subdef`,
    `@SigmaFinite_isFinite.Build`, `FiniteMeasure_isSubProbability.Build`
    (deprecated since 1.1.0)

### Infrastructure

### Misc
