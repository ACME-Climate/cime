set(pf_sources test_erf_r4.pf test_erf_r8.pf test_gamma_factorial.pf
  test_igamma.pf)

set(sources_needed shr_kind_mod.F90 shr_const_mod.F90 shr_infnan_mod.F90
  shr_strconvert_mod.F90 shr_log_mod.F90
  shr_sys_mod.nompi_abortthrows.F90 shr_spfn_mod.F90)

extract_sources("${sources_needed}" "${share_sources}" test_sources)

create_pFUnit_test(spfn spfn_test_exe "${pf_sources}" "${test_sources}")

declare_generated_dependencies(spfn_test_exe "${share_genf90_sources}")
