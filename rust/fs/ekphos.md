# run tests on fork

```sh
make test
cargo test
    Updating crates.io index
  Downloaded phf_generator v0.13.1
  Downloaded html5ever v0.35.0
  Downloaded base64-simd v0.8.0
  Downloaded precomputed-hash v0.1.1
  Downloaded string_cache_codegen v0.5.4
  Downloaded match_token v0.35.0
  Downloaded bit-set v0.8.0
  Downloaded objc2-io-surface v0.3.2
  Downloaded futf v0.1.5
  Downloaded markup5ever v0.35.0
  Downloaded instability v0.3.10
  Downloaded outref v0.5.2
  Downloaded mac v0.1.1
  Downloaded vsimd v0.8.0
  Downloaded phf_shared v0.13.1
  Downloaded phf_macros v0.13.1
  Downloaded bit-vec v0.8.0
  Downloaded objc2-core-video v0.3.2
  Downloaded web_atoms v0.1.3
  Downloaded string_cache v0.8.9
  Downloaded signal-hook-registry v1.4.7
  Downloaded objc2-quartz-core v0.3.2
  Downloaded phf v0.13.1
  Downloaded rand_xoshiro v0.7.0
  Downloaded xml5ever v0.35.0
  Downloaded objc2-core-data v0.3.2
  Downloaded rustls-pki-types v1.13.2
  Downloaded find-msvc-tools v0.1.5
  Downloaded clipboard-rs v0.3.1
  Downloaded block2 v0.6.2
  Downloaded tendril v0.4.3
  Downloaded dispatch2 v0.3.0
  Downloaded arboard v3.6.1
  Downloaded objc2-cloud-kit v0.3.2
  Downloaded zerocopy-derive v0.8.31
  Downloaded zune-jpeg v0.5.7
  Downloaded rustls-webpki v0.103.8
  Downloaded objc2-core-text v0.3.2
  Downloaded cc v1.2.49
  Downloaded objc2-core-image v0.3.2
  Downloaded objc2-core-graphics v0.3.2
  Downloaded fancy-regex v0.16.2
  Downloaded webpki-roots v1.0.4
  Downloaded markup5ever_rcdom v0.35.0+unofficial
  Downloaded htmd v0.5.0
  Downloaded rustls v0.23.35
  Downloaded objc2-app-kit v0.3.2
  Downloaded icy_sixel v0.5.0
  Downloaded ratatui-image v10.0.4
  Downloaded 49 crates (12.7MiB) in 2.32s (largest was `ratatui-image` at 5.7MiB)
   Compiling proc-macro2 v1.0.103
   Compiling unicode-ident v1.0.22
   Compiling quote v1.0.42
   Compiling libc v0.2.178
   Compiling cfg-if v1.0.4
   Compiling bitflags v2.10.0
   Compiling stable_deref_trait v1.2.1
   Compiling smallvec v1.15.1
   Compiling log v0.4.29
   Compiling serde_core v1.0.228
   Compiling libm v0.2.16
   Compiling autocfg v1.5.0
   Compiling siphasher v1.0.1
   Compiling memchr v2.7.6
   Compiling serde v1.0.228
   Compiling num-traits v0.2.19
   Compiling either v1.15.0
   Compiling thiserror v2.0.17
   Compiling new_debug_unreachable v1.0.6
   Compiling crossbeam-utils v0.8.21
   Compiling equivalent v1.0.2
   Compiling simd-adler32 v0.3.8
   Compiling foldhash v0.2.0
   Compiling objc2 v0.6.3
   Compiling syn v2.0.111
   Compiling allocator-api2 v0.2.21
   Compiling itertools v0.14.0
   Compiling hashbrown v0.16.1
   Compiling rayon-core v1.13.0
   Compiling zerocopy v0.8.31
   Compiling objc2-encode v4.1.0
   Compiling parking_lot_core v0.9.12
   Compiling crossbeam-epoch v0.9.18
   Compiling phf_shared v0.11.3
   Compiling adler2 v2.0.1
   Compiling crc32fast v1.5.0
   Compiling scopeguard v1.2.0
   Compiling lock_api v0.4.14
   Compiling miniz_oxide v0.8.9
   Compiling crossbeam-deque v0.8.6
   Compiling num-integer v0.1.46
   Compiling itoa v1.0.15
   Compiling rand_core v0.6.4
   Compiling anyhow v1.0.100
   Compiling rand v0.8.5
   Compiling num-bigint v0.4.6
   Compiling objc2-core-foundation v0.3.2
   Compiling parking_lot v0.12.5
   Compiling unicode-segmentation v1.12.0
   Compiling arrayvec v0.7.6
   Compiling phf_generator v0.11.3
   Compiling rayon v1.11.0
   Compiling flate2 v1.1.5
   Compiling as-slice v0.2.1
   Compiling built v0.8.0
   Compiling paste v1.0.15
   Compiling fnv v1.0.7
   Compiling av-scenechange v0.14.1
   Compiling ryu v1.0.20
   Compiling num-rational v0.4.2
   Compiling rustversion v1.0.22
   Compiling synstructure v0.13.2
   Compiling rav1e v0.8.1
   Compiling aligned v0.4.3
   Compiling nom v8.0.0
   Compiling core2 v0.4.0
   Compiling ident_case v1.0.1
   Compiling quick-error v2.0.1
   Compiling y4m v0.8.0
   Compiling pastey v0.1.1
   Compiling strsim v0.11.1
   Compiling bitstream-io v4.9.0
   Compiling darling_core v0.20.11
   Compiling string_cache_codegen v0.5.4
   Compiling phf_codegen v0.11.3
   Compiling maybe-rayon v0.1.1
   Compiling block2 v0.6.2
   Compiling simd_helpers v0.1.0
   Compiling getrandom v0.2.16
   Compiling noop_proc_macro v0.3.0
   Compiling weezl v0.1.12
   Compiling zune-core v0.4.12
   Compiling powerfmt v0.2.0
   Compiling shlex v1.3.0
   Compiling writeable v0.6.2
   Compiling find-msvc-tools v0.1.5
   Compiling imgref v1.12.0
   Compiling heck v0.5.0
   Compiling litemap v0.8.1
   Compiling serde_derive v1.0.228
   Compiling thiserror-impl v2.0.17
   Compiling zerofrom-derive v0.1.6
   Compiling yoke-derive v0.8.1
   Compiling equator-macro v0.4.2
   Compiling zerocopy-derive v0.8.31
   Compiling equator v0.4.2
   Compiling zerovec-derive v0.11.2
   Compiling aligned-vec v0.6.4
   Compiling zerofrom v0.1.6
   Compiling bytemuck_derive v1.10.2
   Compiling displaydoc v0.2.5
   Compiling v_frame v0.3.9
   Compiling yoke v0.8.1
   Compiling profiling-procmacros v1.0.17
   Compiling arg_enum_proc_macro v0.3.4
   Compiling av1-grain v0.2.5
   Compiling fax_derive v0.2.0
   Compiling profiling v1.0.17
   Compiling bytemuck v1.24.0
   Compiling zerovec v0.11.5
   Compiling num-derive v0.4.2
   Compiling fax v0.2.6
   Compiling zerotrie v0.2.3
   Compiling darling_macro v0.20.11
   Compiling strum_macros v0.27.2
   Compiling half v2.7.1
   Compiling loop9 v0.1.5
   Compiling cc v1.2.49
   Compiling zune-jpeg v0.4.21
   Compiling tinystr v0.8.2
   Compiling potential_utf v0.1.4
   Compiling deranged v0.5.5
   Compiling web_atoms v0.1.3
   Compiling icu_locale_core v2.1.1
   Compiling objc2-foundation v0.3.2
   Compiling castaway v0.2.4
   Compiling avif-serialize v0.8.6
   Compiling pxfm v0.1.27
   Compiling zune-inflate v0.2.54
   Compiling fdeflate v0.3.7
   Compiling num_threads v0.1.7
   Compiling icu_properties_data v2.1.2
   Compiling bit_field v0.10.3
   Compiling time-core v0.1.6
   Compiling color_quant v1.1.0
   Compiling static_assertions v1.1.0
   Compiling indoc v2.0.7
   Compiling byteorder-lite v0.1.0
   Compiling instability v0.3.10
   Compiling num-conv v0.1.0
   Compiling precomputed-hash v0.1.1
   Compiling unicode-width v0.2.0
   Compiling mac v0.1.1
   Compiling signal-hook v0.3.18
   Compiling lebe v0.5.3
   Compiling icu_normalizer_data v2.1.1
   Compiling zune-core v0.5.0
   Compiling rgb v0.8.52
   Compiling unicode-truncate v2.0.1
   Compiling zune-jpeg v0.5.7
   Compiling exr v1.74.0
   Compiling futf v0.1.5
   Compiling string_cache v0.8.9
   Compiling time v0.3.44
   Compiling image-webp v0.2.4
   Compiling gif v0.14.1
   Compiling compact_str v0.9.0
   Compiling moxcms v0.7.11
   Compiling png v0.18.0
   Compiling icu_provider v2.1.1
   Compiling strum v0.27.2
   Compiling ring v0.17.14
   Compiling tiff v0.10.3
   Compiling icu_collections v2.1.1
   Compiling darling v0.20.11
   Compiling qoi v0.4.1
   Compiling ravif v0.12.0
   Compiling kasuari v0.4.11
   Compiling convert_case v0.10.0
   Compiling phf v0.11.3
   Compiling lru v0.16.3
   Compiling errno v0.3.14
   Compiling signal-hook-registry v1.4.7
   Compiling rustix v1.1.2
   Compiling radium v0.7.0
   Compiling zeroize v1.8.2
   Compiling utf-8 v0.7.6
   Compiling rustls-pki-types v1.13.2
   Compiling tendril v0.4.3
   Compiling ratatui-core v0.1.0
   Compiling derive_more-impl v2.1.1
   Compiling indexmap v2.12.1
   Compiling mio v1.1.1
   Compiling image v0.25.9
   Compiling option-ext v0.2.0
   Compiling tap v1.0.1
   Compiling ref-cast v1.0.25
   Compiling rand_core v0.9.3
   Compiling palette v0.7.6
   Compiling by_address v1.2.1
   Compiling litrs v1.0.0
   Compiling palette_derive v0.7.6
   Compiling document-features v0.2.12
   Compiling wyz v0.5.1
   Compiling signal-hook-mio v0.2.5
   Compiling icu_normalizer v2.1.1
   Compiling icu_properties v2.1.2
   Compiling derive_more v2.1.1
   Compiling markup5ever v0.35.0
   Compiling safe_arch v0.9.3
   Compiling ref-cast-impl v1.0.25
   Compiling phf_shared v0.13.1
   Compiling line-clipping v0.3.5
   Compiling fast-srgb8 v1.0.0
   Compiling untrusted v0.9.0
   Compiling funty v2.0.0
   Compiling fastrand v2.3.0
   Compiling phf_generator v0.13.1
   Compiling ratatui-widgets v0.3.0
   Compiling bitvec v1.0.1
   Compiling idna_adapter v1.2.1
   Compiling crossterm v0.29.0
   Compiling wide v0.8.3
   Compiling objc2-core-data v0.3.2
   Compiling objc2-quartz-core v0.3.2
   Compiling objc2-cloud-kit v0.3.2
   Compiling objc2-core-image v0.3.2
   Compiling rand v0.9.2
   Compiling rand_xoshiro v0.7.0
   Compiling ppv-lite86 v0.2.21
   Compiling match_token v0.35.0
   Compiling objc2-core-video v0.3.2
   Compiling objc2-core-text v0.3.2
   Compiling objc2-core-graphics v0.3.2
   Compiling ordered-float v5.1.0
   Compiling aho-corasick v1.1.4
   Compiling percent-encoding v2.3.2
   Compiling bit-vec v0.8.0
   Compiling regex-syntax v0.8.8
   Compiling utf8_iter v1.0.4
   Compiling rustls v0.23.35
   Compiling rustix v0.38.44
   Compiling base64 v0.22.1
   Compiling serde_json v1.0.145
   Compiling thiserror v1.0.69
   Compiling once_cell v1.21.3
   Compiling idna v1.1.0
   Compiling quantette v0.5.1
   Compiling objc2-app-kit v0.3.2
   Compiling bit-set v0.8.0
   Compiling form_urlencoded v1.2.2
   Compiling regex-automata v0.4.13
   Compiling html5ever v0.35.0
   Compiling rand_chacha v0.3.1
   Compiling ratatui-crossterm v0.1.0
   Compiling ratatui-macros v0.7.0
   Compiling rustls-webpki v0.103.8
   Compiling phf_macros v0.13.1
   Compiling xml5ever v0.35.0
   Compiling dirs-sys v0.5.0
   Compiling webpki-roots v1.0.4
   Compiling toml_datetime v0.6.11
   Compiling serde_spanned v0.6.9
   Compiling thiserror-impl v1.0.69
   Compiling quick-xml v0.38.4
   Compiling ratatui-image v10.0.4
   Compiling winnow v0.7.14
   Compiling vsimd v0.8.0
   Compiling same-file v1.0.6
   Compiling toml_write v0.1.2
   Compiling linked-hash-map v0.5.6
   Compiling subtle v2.6.1
   Compiling outref v0.5.2
   Compiling base64-simd v0.8.0
   Compiling yaml-rust v0.4.5
   Compiling fancy-regex v0.16.2
   Compiling toml_edit v0.22.27
   Compiling walkdir v2.5.0
   Compiling plist v1.8.0
   Compiling phf v0.13.1
   Compiling markup5ever_rcdom v0.35.0+unofficial
   Compiling webpki-roots v0.26.11
   Compiling dirs v6.0.0
   Compiling icy_sixel v0.5.0
   Compiling ratatui v0.30.0
   Compiling url v2.5.7
   Compiling dirs-sys v0.4.1
   Compiling bincode v1.3.3
   Compiling unsafe-libyaml v0.2.11
   Compiling syntect v5.3.0
   Compiling ureq v2.12.1
   Compiling serde_yaml v0.9.34+deprecated
   Compiling dirs v5.0.1
   Compiling toml v0.8.23
   Compiling shellexpand v3.1.1
   Compiling htmd v0.5.0
   Compiling clipboard-rs v0.3.1
   Compiling arboard v3.6.1
   Compiling ekphos v0.20.10 (/Users/zach/Desktop/ekphos)
warning: unused variable: `i`
   --> src/vim/macro_record.rs:135:13
    |
135 |         for i in 0..100 {
    |             ^ help: if this is intentional, prefix it with an underscore: `_i`
    |
    = note: `#[warn(unused_variables)]` (part of `#[warn(unused)]`) on by default

warning: `ekphos` (bin "ekphos" test) generated 1 warning (run `cargo fix --bin "ekphos" -p ekphos --tests` to apply 1 suggestion)
    Finished `test` profile [unoptimized + debuginfo] target(s) in 50.13s
     Running unittests src/main.rs (target/debug/deps/ekphos-f92e2e976799aa00)

running 367 tests
test app::frontmatter::tests::test_parse_no_frontmatter ... ok
test editor::buffer::tests::test_from_lines ... ok
test app::frontmatter::tests::test_parse_unclosed_frontmatter ... ok
test editor::buffer::tests::test_get_text_range ... ok
test editor::buffer::tests::test_delete_char ... ok
test editor::buffer::tests::test_insert_char ... ok
test editor::buffer::tests::test_join_lines ... ok
test app::frontmatter::tests::test_parse_invalid_yaml ... ok
test editor::buffer::tests::test_new_buffer ... ok
test app::frontmatter::tests::test_parse_tags_multiline ... ok
test app::frontmatter::tests::test_parse_valid_frontmatter ... ok
test editor::buffer::tests::test_split_line ... ok
test editor::cursor::tests::test_selection_range ... ok
test editor::cursor::tests::test_word_back ... ok
test editor::cursor::tests::test_word_forward ... ok
test editor::history::tests::test_block_delete_cursor_restoration ... ok
test editor::history::tests::test_block_double_inverse_is_original ... ok
test editor::history::tests::test_cursor_position_preserved_on_redo ... ok
test editor::history::tests::test_cursor_position_preserved_on_undo ... ok
test editor::history::tests::test_double_inverse_is_original ... ok
test editor::history::tests::test_empty_line_insert ... ok
test editor::history::tests::test_inverse_block_insert ... ok
test editor::history::tests::test_inverse_block_delete ... ok
test editor::history::tests::test_inverse_delete ... ok
test editor::history::tests::test_inverse_join_line ... ok
test editor::history::tests::test_inverse_line_delete ... ok
test editor::history::tests::test_inverse_line_insert ... ok
test editor::history::tests::test_inverse_operations ... ok
test editor::history::tests::test_inverse_split_line ... ok
test editor::history::tests::test_line_delete_cursor_restoration ... ok
test editor::history::tests::test_line_insert_multiple_lines_cursor ... ok
test editor::history::tests::test_multiline_insert_inverse ... ok
test editor::history::tests::test_multiple_undo_redo_cycle ... ok
test editor::history::tests::test_new_edit_clears_redo ... ok
test editor::history::tests::test_record_and_undo ... ok
test editor::history::tests::test_redo ... ok
test highlight_worker::tests::test_cjk_code_block_content ... ok
test highlight_worker::tests::test_code_block_prevents_all_highlighting ... ok
test highlight_worker::tests::test_cjk_blockquote ... ok
test highlight_worker::tests::test_compute_wiki_links ... ok
test highlight_worker::tests::test_correct_column_positions ... ok
test highlight_worker::tests::test_details_tags_highlighting ... ok
test highlight_worker::tests::test_detect_frontmatter ... ok
test highlight_worker::tests::test_detect_header ... ok
test highlight_worker::tests::test_frontmatter_prevents_highlighting ... ok
test highlight_worker::tests::test_horizontal_rule_highlighting ... ok
test highlight_worker::tests::test_inline_code_prevents_inner_highlighting ... ok
test highlight_worker::tests::test_no_false_positive_bold ... ok
test highlight_worker::tests::test_no_false_positive_details_tags ... ok
test highlight_worker::tests::test_no_false_positive_horizontal_rules ... ok
test highlight_worker::tests::test_no_false_positive_headers ... ok
test highlight_worker::tests::test_no_false_positive_inline_code ... ok
test highlight_worker::tests::test_no_false_positive_italic ... ok
test highlight_worker::tests::test_no_false_positive_list_markers ... ok
test highlight_worker::tests::test_no_false_positive_links ... ok
test highlight_worker::tests::test_no_false_positive_wiki_links ... ok
test highlight_worker::tests::test_wiki_links_skip_code ... ok
test vim::command::tests::test_parse_empty ... ok
test vim::command::tests::test_parse_invalid ... ok
test vim::command::tests::test_parse_line_number ... ok
test vim::command::tests::test_parse_simple_commands ... ok
test vim::command::tests::test_parse_substitute_case_insensitive ... ok
test vim::command::tests::test_parse_substitute_different_delimiter ... ok
test vim::command::tests::test_parse_substitute_no_flags ... ok
test vim::command::tests::test_substitute_flags_parse ... ok
test vim::command::tests::test_parse_substitute_with_global ... ok
test vim::find::tests::test_double_reversed_is_original ... ok
test vim::find::tests::test_find_backward_at_position_1 ... ok
test vim::find::tests::test_find_backward_basic ... ok
test vim::find::tests::test_find_backward_at_start ... ok
test vim::find::tests::test_find_backward_first_char ... ok
test vim::find::tests::test_find_backward_multiple_occurrences ... ok
test vim::find::tests::test_find_backward_not_found ... ok
test vim::find::tests::test_find_backward_single_char_string ... ok
test vim::find::tests::test_find_forward_at_last_position ... ok
test vim::find::tests::test_find_forward_empty_string ... ok
test vim::find::tests::test_find_forward_basic ... ok
test vim::find::tests::test_find_forward_first_char ... ok
test vim::find::tests::test_find_forward_from_middle ... ok
test vim::find::tests::test_find_forward_multiple_occurrences ... ok
test vim::find::tests::test_find_forward_last_char ... ok
test vim::find::tests::test_find_forward_space ... ok
test vim::find::tests::test_find_forward_special_char ... ok
test vim::find::tests::test_find_newline_not_in_string ... ok
test vim::find::tests::test_find_not_found_backward ... ok
test vim::find::tests::test_find_not_found_forward ... ok
test vim::find::tests::test_find_same_char_at_position ... ok
test vim::find::tests::test_find_single_char_string ... ok
test vim::find::tests::test_find_unicode_char ... ok
test vim::find::tests::test_pending_find_backward ... ok
test vim::find::tests::test_find_tab ... ok
test vim::find::tests::test_pending_find_forward ... ok
test vim::find::tests::test_pending_find_till_backward ... ok
test highlight_worker::tests::test_panic_safety ... ok
test vim::find::tests::test_pending_find_till_forward ... ok
test vim::find::tests::test_reversed_backward_to_forward ... ok
test vim::find::tests::test_reversed_forward_to_backward ... ok
test vim::find::tests::test_reversed_preserves_char ... ok
test vim::find::tests::test_reversed_preserves_till ... ok
test vim::find::tests::test_till_backward_basic ... ok
test vim::find::tests::test_till_backward_stops_after_char ... ok
test vim::find::tests::test_till_forward_adjacent_char ... ok
test vim::find::tests::test_till_forward_stops_before_char ... ok
test vim::find::tests::test_till_forward_basic ... ok
test vim::find::tests::test_till_not_found_backward ... ok
test vim::find::tests::test_till_not_found_forward ... ok
test vim::macro_record::tests::test_empty_macro_not_saved ... ok
test vim::macro_record::tests::test_all_lowercase_registers ... ok
test vim::macro_record::tests::test_get_nonexistent_macro ... ok
test vim::macro_record::tests::test_get_macro_preserves_order ... ok
test vim::macro_record::tests::test_last_played_nonexistent_register ... ok
test vim::macro_record::tests::test_last_macro_initially_none ... ok
test vim::macro_record::tests::test_multiple_registers ... ok
test vim::macro_record::tests::test_last_played_updates ... ok
test vim::macro_record::tests::test_new_state ... ok
test vim::macro_record::tests::test_overwrite_macro ... ok
test vim::macro_record::tests::test_record_and_stop ... ok
test vim::macro_record::tests::test_record_key_while_not_recording ... ok
test vim::macro_record::tests::test_record_many_keys ... ok
test vim::macro_record::tests::test_record_single_key ... ok
test vim::macro_record::tests::test_record_key_with_modifiers ... ok
test vim::macro_record::tests::test_record_special_keys ... ok
test vim::macro_record::tests::test_set_last_played ... ok
test vim::macro_record::tests::test_start_recording ... ok
test vim::macro_record::tests::test_start_recording_clears_buffer ... ok
test vim::macro_record::tests::test_stop_without_start ... ok
test vim::macro_record::tests::test_start_recording_different_registers ... ok
test vim::marks::tests::test_all_lowercase_marks ... ok
test vim::marks::tests::test_delete_mark ... ok
test vim::marks::tests::test_delete_nonexistent_mark ... ok
test vim::marks::tests::test_all_uppercase_marks ... ok
test vim::marks::tests::test_delete_one_of_multiple ... ok
test vim::marks::tests::test_delete_and_rset ... ok
test vim::marks::tests::test_invalid_mark_number ... ok
test vim::marks::tests::test_invalid_mark_space ... ok
test vim::marks::tests::test_invalid_mark_symbol ... ok
test vim::marks::tests::test_last_change ... ok
test vim::marks::tests::test_last_insert ... ok
test vim::marks::tests::test_last_jump_backtick ... ok
test vim::marks::tests::test_last_jump_both_return_same ... ok
test vim::marks::tests::test_last_jump_single_quote ... ok
test vim::marks::tests::test_list_does_not_include_special_marks ... ok
test vim::marks::tests::test_list_marks_all ... ok
test vim::marks::tests::test_list_marks_empty ... ok
test vim::marks::tests::test_list_marks_sorted ... ok
test vim::marks::tests::test_lowercase_a ... ok
test vim::marks::tests::test_lowercase_z ... ok
test vim::marks::tests::test_mark_at_origin ... ok
test vim::marks::tests::test_mark_large_position ... ok
test vim::marks::tests::test_new_mark_map ... ok
test vim::marks::tests::test_set_and_get_mark ... ok
test vim::marks::tests::test_set_overwrites_mark ... ok
test vim::marks::tests::test_set_same_mark_multiple_times ... ok
test vim::marks::tests::test_special_marks_initially_none ... ok
test vim::marks::tests::test_special_marks_update ... ok
test vim::marks::tests::test_uppercase_and_lowercase_separate ... ok
test vim::marks::tests::test_uppercase_marks ... ok
test vim::mode::tests::test_default_mode ... ok
test vim::mode::tests::test_display_name ... ok
test vim::mode::tests::test_is_command ... ok
test vim::mode::tests::test_is_insert ... ok
test vim::mode::tests::test_is_normal ... ok
test vim::mode::tests::test_is_visual ... ok
test vim::mode::tests::test_operator_pending_display ... ok
test vim::motion::tests::test_big_word_back_at_start ... ok
test vim::motion::tests::test_big_word_back_basic ... ok
test vim::motion::tests::test_big_word_back_empty ... ok
test vim::motion::tests::test_big_word_back_punctuation ... ok
test vim::motion::tests::test_big_word_end_forward_at_end ... ok
test vim::motion::tests::test_big_word_end_forward_basic ... ok
test vim::motion::tests::test_big_word_end_forward_punctuation ... ok
test vim::motion::tests::test_big_word_forward_at_end ... ok
test vim::motion::tests::test_big_word_forward_basic ... ok
test vim::motion::tests::test_big_word_forward_empty ... ok
test vim::motion::tests::test_big_word_forward_punctuation ... ok
test vim::motion::tests::test_first_non_blank_all_whitespace ... ok
test vim::motion::tests::test_first_non_blank_empty ... ok
test vim::motion::tests::test_first_non_blank_mixed ... ok
test vim::motion::tests::test_first_non_blank_no_indent ... ok
test vim::motion::tests::test_first_non_blank_spaces ... ok
test vim::motion::tests::test_first_non_blank_tabs ... ok
test vim::motion::tests::test_is_word_char_letters ... ok
test vim::motion::tests::test_is_word_char_numbers ... ok
test vim::motion::tests::test_is_word_char_punctuation ... ok
test vim::motion::tests::test_is_word_char_underscore ... ok
test vim::motion::tests::test_matching_bracket_angle ... ok
test vim::motion::tests::test_matching_bracket_curly ... ok
test vim::motion::tests::test_matching_bracket_deep_nested ... ok
test vim::motion::tests::test_matching_bracket_empty_lines ... ok
test vim::motion::tests::test_matching_bracket_mixed_types ... ok
test vim::motion::tests::test_matching_bracket_multiline ... ok
test vim::motion::tests::test_matching_bracket_nested ... ok
test vim::motion::tests::test_matching_bracket_not_on_bracket ... ok
test vim::motion::tests::test_matching_bracket_parens ... ok
test vim::motion::tests::test_matching_bracket_unmatched ... ok
test vim::motion::tests::test_motion_is_exclusive ... ok
test vim::motion::tests::test_matching_bracket_square ... ok
test vim::motion::tests::test_motion_is_linewise ... ok
test vim::motion::tests::test_paragraph_backward_at_start ... ok
test vim::motion::tests::test_paragraph_backward_multiple_empty ... ok
test vim::motion::tests::test_paragraph_backward_basic ... ok
test vim::motion::tests::test_paragraph_forward_at_end ... ok
test vim::motion::tests::test_paragraph_forward_basic ... ok
test vim::motion::tests::test_paragraph_forward_empty_doc ... ok
test vim::motion::tests::test_paragraph_forward_multiple_empty ... ok
test vim::motion::tests::test_paragraph_forward_whitespace_only_line ... ok
test vim::motion::tests::test_word_back_at_start ... ok
test vim::motion::tests::test_word_back_basic ... ok
test vim::motion::tests::test_word_back_empty_string ... ok
test vim::motion::tests::test_word_back_col_beyond_line ... ok
test vim::motion::tests::test_word_back_multiple_spaces ... ok
test vim::motion::tests::test_word_back_punctuation ... ok
test vim::motion::tests::test_word_end_forward_at_end ... ok
test vim::motion::tests::test_word_end_forward_basic ... ok
test vim::motion::tests::test_word_end_forward_multiple_spaces ... ok
test vim::motion::tests::test_word_end_forward_punctuation ... ok
test vim::motion::tests::test_word_end_forward_short_words ... ok
test vim::motion::tests::test_word_forward_at_end ... ok
test vim::motion::tests::test_word_forward_basic ... ok
test vim::motion::tests::test_word_forward_empty_string ... ok
test vim::motion::tests::test_word_forward_multiple_spaces ... ok
test vim::motion::tests::test_word_forward_punctuation ... ok
test vim::motion::tests::test_word_forward_numbers ... ok
test vim::motion::tests::test_word_forward_single_char ... ok
test vim::motion::tests::test_word_forward_underscore ... ok
test vim::operator::tests::test_enters_insert_mode ... ok
test vim::operator::tests::test_modifies_buffer ... ok
test vim::operator::tests::test_operator_char ... ok
test vim::register::tests::test_all_numbered_registers ... ok
test vim::register::tests::test_append_to_empty_register ... ok
test vim::register::tests::test_all_lowercase_named_registers ... ok
test vim::register::tests::test_append_to_named ... ok
test vim::register::tests::test_characterwise_preserved ... ok
test vim::register::tests::test_clear_selection ... ok
test vim::register::tests::test_command_register ... ok
test vim::register::tests::test_command_register_initially_empty ... ok
test vim::register::tests::test_command_register_overwrite ... ok
test vim::register::tests::test_delete_shifts_numbered ... ok
test vim::register::tests::test_delete_to_named_register ... ok
test vim::register::tests::test_delete_shifts_up_to_9 ... ok
test vim::register::tests::test_delete_to_named_skips_numbered ... ok
test vim::register::tests::test_get_clipboard_registers ... ok
test vim::register::tests::test_get_for_paste_default ... ok
test vim::register::tests::test_get_for_paste_nonexistent_register ... ok
test vim::register::tests::test_get_invalid_register ... ok
test vim::register::tests::test_get_for_paste_selected ... ok
test vim::register::tests::test_get_small_delete_register ... ok
test vim::register::tests::test_get_unnamed_register ... ok
test vim::register::tests::test_is_clipboard_selected_named ... ok
test vim::register::tests::test_is_clipboard_selected_none ... ok
test vim::register::tests::test_is_clipboard_selected_plus ... ok
test vim::register::tests::test_is_clipboard_selected_star ... ok
test vim::register::tests::test_linewise_delete_not_small ... ok
test vim::register::tests::test_linewise_preserved_on_delete ... ok
test vim::register::tests::test_linewise_preserved_on_yank ... ok
test vim::register::tests::test_multiline_delete_not_small ... ok
test vim::register::tests::test_new_register_map ... ok
test vim::register::tests::test_numbered_register_0 ... ok
test vim::register::tests::test_search_register ... ok
test vim::register::tests::test_search_register_initially_empty ... ok
test vim::register::tests::test_search_register_overwrite ... ok
test vim::register::tests::test_select_changes_register ... ok
test vim::register::tests::test_small_delete ... ok
test vim::register::tests::test_small_delete_not_linewise ... ok
test vim::register::tests::test_select_register ... ok
test vim::register::tests::test_unnamed_register_initially_empty ... ok
test vim::register::tests::test_uppercase_get_returns_lowercase ... ok
test vim::register::tests::test_yank_characterwise ... ok
test vim::register::tests::test_yank_clears_selection ... ok
test vim::register::tests::test_yank_linewise ... ok
test vim::register::tests::test_yank_multiple_times ... ok
test vim::register::tests::test_yank_to_named ... ok
test vim::register::tests::test_yank_to_unnamed ... ok
test vim::tests::test_accumulate_count ... ok
test vim::tests::test_enter_command_mode ... ok
test vim::tests::test_enter_replace_mode ... ok
test vim::tests::test_enter_visual_block_mode ... ok
test vim::tests::test_enter_visual_mode ... ok
test vim::tests::test_exit_command_mode ... ok
test vim::tests::test_get_count_default ... ok
test vim::tests::test_get_count_with_value ... ok
test vim::tests::test_macros_initialized ... ok
test vim::tests::test_marks_initialized ... ok
test vim::tests::test_recorded_command_default ... ok
test vim::tests::test_reset_pending ... ok
test vim::tests::test_reset_pending_clears_mark_and_macro ... ok
test vim::tests::test_status_display_normal ... ok
test vim::tests::test_status_display_pending_g ... ok
test vim::tests::test_status_display_pending_macro ... ok
test vim::tests::test_status_display_pending_mark ... ok
test vim::tests::test_status_display_recording ... ok
test vim::tests::test_status_display_with_count ... ok
test vim::tests::test_vim_state_new ... ok
test vim::text_object::tests::test_delimiters_all ... ok
test vim::text_object::tests::test_find_big_word_bounds_around ... ok
test vim::text_object::tests::test_find_big_word_bounds_complex ... ok
test vim::text_object::tests::test_find_big_word_bounds_inner ... ok
test vim::text_object::tests::test_find_bounds_col_beyond_line ... ok
test vim::text_object::tests::test_find_bounds_empty_lines ... ok
test vim::text_object::tests::test_find_bounds_row_out_of_bounds ... ok
test vim::text_object::tests::test_find_bounds_whitespace_only ... ok
test vim::text_object::tests::test_find_bracket_bounds_angle ... ok
test vim::text_object::tests::test_find_bracket_bounds_at_open_bracket ... ok
test vim::text_object::tests::test_find_bracket_bounds_around ... ok
test vim::text_object::tests::test_find_bracket_bounds_complex_code ... ok
test vim::text_object::tests::test_find_bracket_bounds_curly ... ok
test vim::text_object::tests::test_find_bracket_bounds_cursor_after_closed_pair ... ok
test vim::text_object::tests::test_find_bracket_bounds_cursor_after_only_pair ... ok
test vim::text_object::tests::test_find_bracket_bounds_deeply_nested ... ok
test vim::text_object::tests::test_find_bracket_bounds_empty ... ok
test vim::text_object::tests::test_find_bracket_bounds_inner ... ok
test vim::text_object::tests::test_find_bracket_bounds_multiline ... ok
test vim::text_object::tests::test_find_bracket_bounds_multiline_around ... ok
test vim::text_object::tests::test_find_bracket_bounds_multiple_unmatched ... ok
test vim::text_object::tests::test_find_bracket_bounds_nested ... ok
test vim::text_object::tests::test_find_bracket_bounds_seek_forward_angle ... ok
test vim::text_object::tests::test_find_bracket_bounds_no_brackets ... ok
test vim::text_object::tests::test_find_bracket_bounds_seek_forward_around ... ok
test vim::text_object::tests::test_find_bracket_bounds_seek_forward_braces ... ok
test vim::text_object::tests::test_find_bracket_bounds_seek_forward_brackets ... ok
test vim::text_object::tests::test_find_bracket_bounds_seek_forward_parentheses ... ok
test vim::text_object::tests::test_find_bracket_bounds_seek_mid_line ... ok
test vim::text_object::tests::test_find_bracket_bounds_square ... ok
test vim::text_object::tests::test_find_bracket_bounds_unmatched ... ok
test vim::text_object::tests::test_find_bracket_bounds_unmatched_does_not_match_later_close ... ok
test vim::text_object::tests::test_find_paragraph_bounds_around ... ok
test vim::text_object::tests::test_find_bracket_bounds_unmatched_on_previous_line ... ok
test vim::text_object::tests::test_find_paragraph_bounds_at_empty_line ... ok
test vim::text_object::tests::test_find_paragraph_bounds_multiple_paragraphs ... ok
test vim::text_object::tests::test_find_paragraph_bounds_single_line ... ok
test vim::text_object::tests::test_find_paragraph_bounds_inner ... ok
test vim::text_object::tests::test_find_quote_bounds_around ... ok
test vim::text_object::tests::test_find_quote_bounds_backtick ... ok
test vim::text_object::tests::test_find_quote_bounds_at_quote_char ... ok
test vim::text_object::tests::test_find_quote_bounds_empty_quotes ... ok
test vim::text_object::tests::test_find_quote_bounds_inner ... ok
test vim::text_object::tests::test_find_quote_bounds_no_quotes ... ok
test vim::text_object::tests::test_find_quote_bounds_single_quote ... ok
test vim::text_object::tests::test_find_quote_bounds_unmatched_quote ... ok
test vim::text_object::tests::test_find_word_bounds_around ... ok
test vim::text_object::tests::test_find_word_bounds_around_trailing_space ... ok
test vim::text_object::tests::test_find_word_bounds_around_leading_space ... ok
test vim::text_object::tests::test_find_word_bounds_at_end ... ok
test vim::text_object::tests::test_find_word_bounds_at_start ... ok
test vim::text_object::tests::test_find_word_bounds_empty_line ... ok
test vim::text_object::tests::test_find_word_bounds_inner ... ok
test vim::text_object::tests::test_find_word_bounds_punctuation ... ok
test vim::text_object::tests::test_find_word_bounds_single_word ... ok
test vim::text_object::tests::test_find_word_bounds_with_underscore ... ok
test vim::text_object::tests::test_is_word_char_letters ... ok
test vim::text_object::tests::test_is_word_char_numbers ... ok
test vim::text_object::tests::test_is_word_char_punctuation ... ok
test vim::text_object::tests::test_is_word_char_underscore ... ok
test vim::text_object::tests::test_parse_angle_brackets ... ok
test vim::text_object::tests::test_parse_big_word ... ok
test vim::text_object::tests::test_parse_braces ... ok
test vim::text_object::tests::test_parse_brackets ... ok
test vim::text_object::tests::test_parse_invalid_object ... ok
test vim::text_object::tests::test_parse_invalid_scope ... ok
test vim::text_object::tests::test_parse_paragraph ... ok
test vim::text_object::tests::test_parse_parentheses ... ok
test vim::text_object::tests::test_parse_quotes ... ok
test vim::text_object::tests::test_parse_word ... ok
test highlight::tests::test_highlight_block_trailing_empty_line ... ok
test highlight::tests::test_highlight_block_cjk_no_panic ... ok
test highlight::tests::test_highlight_block_c_with_cjk_comments ... ok
test editor::history::tests::test_max_entries_limit ... ok

test result: ok. 367 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 1.41s
```
