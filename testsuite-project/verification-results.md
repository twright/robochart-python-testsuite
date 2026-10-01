# Testsuite verification

This report is generated from [verification-results.csv](verification-results.csv). The source cases are [expressions](source-data/cases.csv) and [statements](source-data/statement_cases.csv).

## Summary

| Measure | Count |
| --- | ---: |
| Expression source cases | 548 |
| Statement source cases | 28 |
| Report rows | 576 |
| Distinct reported IDs | 576 |

Source coverage: **complete**. Each case gets the best context the generator can supply, including the shared fixtures. An unsupported case still has an entry here, with the evidence for its attribution.

## Outcomes

| Status | Meaning | Cases |
| --- | --- | ---: |
| `pass` | FDR's result matched the case's expected status, including deliberate mismatch tests. | 401 |
| `translator_defect` | FDR refuted the recorded Python observation of a supported case: evidence of a translator defect. | 6 |
| `unsupported_case` | The case expression is not valid RoboChart, even with the best context: a likely error in the case specification. | 76 |
| `unsupported_robotool` | The case is valid RoboChart, but a RoboTool defect or limitation prevents a verdict. | 93 |
| `failure` | The harness could not reach a verdict; not attributed to the case, RoboTool or the translator. | 0 |

## Categories of cases that did not pass

| Status | Category | Cases |
| --- | --- | ---: |
| `translator_defect` | `fdr_mismatch` | 6 |
| `unsupported_case` | `robochart_validation_error` | 7 |
| `unsupported_case` | `unsupported_robochart_syntax` | 69 |
| `unsupported_robotool` | `csp_generator_exception` | 72 |
| `unsupported_robotool` | `fdr_no_result` | 10 |
| `unsupported_robotool` | `oracle_representation_limit` | 11 |

## Cases that did not pass

### `translator_defect`: `fdr_mismatch` (6)

| Case | Reason | Log |
| --- | --- | --- |
| [set_range/004](cases/expressions/set_range/004.rct) | FDR reported mismatch, expected pass; same verdict with core_int {-4..3} | [log](verification-logs/0485_expression_set_range_004.log) |
| [set_range/008](cases/expressions/set_range/008.rct) | FDR reported mismatch, expected pass; same verdict with core_int {-4..3} | [log](verification-logs/0489_expression_set_range_008.log) |
| [set_range/009](cases/expressions/set_range/009.rct) | FDR reported mismatch, expected pass; same verdict with core_int {-3..3} | [log](verification-logs/0490_expression_set_range_009.log) |
| [set_range/012](cases/expressions/set_range/012.rct) | FDR reported mismatch, expected pass; same verdict with core_int {-4..8} | [log](verification-logs/0493_expression_set_range_012.log) |
| [set_range/013](cases/expressions/set_range/013.rct) | FDR reported mismatch, expected pass; same verdict with core_int {-3..8} | [log](verification-logs/0494_expression_set_range_013.log) |
| [set_range/014](cases/expressions/set_range/014.rct) | FDR reported mismatch, expected pass; same verdict with core_int {-3..8} | [log](verification-logs/0495_expression_set_range_014.log) |

### `unsupported_case`: `robochart_validation_error` (7)

| Case | Reason | Log |
| --- | --- | --- |
| [boolean_case/000](cases/expressions/boolean_case/000.rct) | RoboTool generator exited with exit status: 2 (RoboTool rejects the case expression itself: it is not valid RoboChart) | [log](verification-logs/0103_expression_boolean_case_000.log) |
| [matrix_index/000](cases/expressions/matrix_index/000.rct) | RoboTool generator exited with exit status: 2 (RoboTool rejects the case expression itself: it is not valid RoboChart) | [log](verification-logs/0339_expression_matrix_index_000.log) |
| [postfix_chain/000](cases/expressions/postfix_chain/000.rct) | RoboTool generator exited with exit status: 2 (RoboTool rejects the case expression itself: it is not valid RoboChart) | [log](verification-logs/0408_expression_postfix_chain_000.log) |
| [qualified/000](cases/expressions/qualified/000.rct) | RoboTool generator exited with exit status: 2 (RoboTool rejects the case expression itself: it is not valid RoboChart) | [log](verification-logs/0410_expression_qualified_000.log) |
| [qualified_attribute/000](cases/expressions/qualified_attribute/000.rct) | RoboTool generator exited with exit status: 2 (RoboTool rejects the case expression itself: it is not valid RoboChart) | [log](verification-logs/0411_expression_qualified_attribute_000.log) |
| [qualified_type/000](cases/expressions/qualified_type/000.rct) | RoboTool generator exited with exit status: 2 (RoboTool rejects the case expression itself: it is not valid RoboChart) | [log](verification-logs/0412_expression_qualified_type_000.log) |
| [transpose/000](cases/expressions/transpose/000.rct) | RoboTool generator exited with exit status: 2 (RoboTool rejects the case expression itself: it is not valid RoboChart) | [log](verification-logs/0526_expression_transpose_000.log) |

### `unsupported_case`: `unsupported_robochart_syntax` (69)

| Case | Reason | Log |
| --- | --- | --- |
| `tuple_empty/000` | RoboChart requires tuples to contain at least two values (the case expression is not valid RoboChart) | [log](verification-logs/0002_tuple_empty_000.log) |
| `tuple_single/000` | RoboChart requires tuples to contain at least two values (the case expression is not valid RoboChart) | [log](verification-logs/0003_tuple_single_000.log) |
| `record_empty/000` | RoboChart record literals require at least one field (the case expression is not valid RoboChart) | [log](verification-logs/0004_record_empty_000.log) |
| `since_entry/000` | RoboChart keyword state cannot name a state in sinceEntry (the case expression is not valid RoboChart) | [log](verification-logs/0006_since_entry_000.log) |
| `special_real/000` | RoboChart type names cannot be used as value expressions (the case expression is not valid RoboChart) | [log](verification-logs/0008_special_real_000.log) |
| `range_True_True_True/000` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0017_range_True_True_True_000.log) |
| `range_True_True_True/001` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0018_range_True_True_True_001.log) |
| `range_True_True_True/002` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0019_range_True_True_True_002.log) |
| `range_True_True_True/003` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0020_range_True_True_True_003.log) |
| `range_True_True_True/004` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0021_range_True_True_True_004.log) |
| `range_True_True_True/005` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0022_range_True_True_True_005.log) |
| `range_True_True_True/006` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0023_range_True_True_True_006.log) |
| `range_True_True_True/007` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0024_range_True_True_True_007.log) |
| `range_True_True_True/008` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0025_range_True_True_True_008.log) |
| `range_True_True_True/009` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0026_range_True_True_True_009.log) |
| `range_True_True_True/010` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0027_range_True_True_True_010.log) |
| `range_True_True_True/011` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0028_range_True_True_True_011.log) |
| `range_True_True_True/012` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0029_range_True_True_True_012.log) |
| `range_True_True_True/013` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0030_range_True_True_True_013.log) |
| `range_True_True_True/014` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0031_range_True_True_True_014.log) |
| `range_True_True_True/015` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0032_range_True_True_True_015.log) |
| `range_True_False_True/000` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0033_range_True_False_True_000.log) |
| `range_True_False_True/001` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0034_range_True_False_True_001.log) |
| `range_True_False_True/002` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0035_range_True_False_True_002.log) |
| `range_True_False_True/003` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0036_range_True_False_True_003.log) |
| `range_True_False_True/004` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0037_range_True_False_True_004.log) |
| `range_True_False_True/005` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0038_range_True_False_True_005.log) |
| `range_True_False_True/006` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0039_range_True_False_True_006.log) |
| `range_True_False_True/007` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0040_range_True_False_True_007.log) |
| `range_True_False_True/008` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0041_range_True_False_True_008.log) |
| `range_True_False_True/009` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0042_range_True_False_True_009.log) |
| `range_True_False_True/010` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0043_range_True_False_True_010.log) |
| `range_True_False_True/011` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0044_range_True_False_True_011.log) |
| `range_True_False_True/012` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0045_range_True_False_True_012.log) |
| `range_True_False_True/013` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0046_range_True_False_True_013.log) |
| `range_True_False_True/014` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0047_range_True_False_True_014.log) |
| `range_True_False_True/015` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0048_range_True_False_True_015.log) |
| `range_False_True_True/000` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0049_range_False_True_True_000.log) |
| `range_False_True_True/001` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0050_range_False_True_True_001.log) |
| `range_False_True_True/002` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0051_range_False_True_True_002.log) |
| `range_False_True_True/003` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0052_range_False_True_True_003.log) |
| `range_False_True_True/004` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0053_range_False_True_True_004.log) |
| `range_False_True_True/005` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0054_range_False_True_True_005.log) |
| `range_False_True_True/006` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0055_range_False_True_True_006.log) |
| `range_False_True_True/007` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0056_range_False_True_True_007.log) |
| `range_False_True_True/008` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0057_range_False_True_True_008.log) |
| `range_False_True_True/009` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0058_range_False_True_True_009.log) |
| `range_False_True_True/010` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0059_range_False_True_True_010.log) |
| `range_False_True_True/011` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0060_range_False_True_True_011.log) |
| `range_False_True_True/012` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0061_range_False_True_True_012.log) |
| `range_False_True_True/013` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0062_range_False_True_True_013.log) |
| `range_False_True_True/014` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0063_range_False_True_True_014.log) |
| `range_False_True_True/015` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0064_range_False_True_True_015.log) |
| `range_False_False_True/000` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0065_range_False_False_True_000.log) |
| `range_False_False_True/001` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0066_range_False_False_True_001.log) |
| `range_False_False_True/002` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0067_range_False_False_True_002.log) |
| `range_False_False_True/003` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0068_range_False_False_True_003.log) |
| `range_False_False_True/004` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0069_range_False_False_True_004.log) |
| `range_False_False_True/005` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0070_range_False_False_True_005.log) |
| `range_False_False_True/006` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0071_range_False_False_True_006.log) |
| `range_False_False_True/007` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0072_range_False_False_True_007.log) |
| `range_False_False_True/008` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0073_range_False_False_True_008.log) |
| `range_False_False_True/009` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0074_range_False_False_True_009.log) |
| `range_False_False_True/010` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0075_range_False_False_True_010.log) |
| `range_False_False_True/011` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0076_range_False_False_True_011.log) |
| `range_False_False_True/012` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0077_range_False_False_True_012.log) |
| `range_False_False_True/013` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0078_range_False_False_True_013.log) |
| `range_False_False_True/014` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0079_range_False_False_True_014.log) |
| `range_False_False_True/015` | RoboChart interval syntax requires an upper bound (the case expression is not valid RoboChart) | [log](verification-logs/0080_range_False_False_True_015.log) |

### `unsupported_robotool`: `csp_generator_exception` (72)

| Case | Reason | Log |
| --- | --- | --- |
| [exists1_False/000](cases/expressions/exists1_False/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0195_expression_exists1_False_000.log) |
| [exists1_False/001](cases/expressions/exists1_False/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0196_expression_exists1_False_001.log) |
| [exists1_False/002](cases/expressions/exists1_False/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0197_expression_exists1_False_002.log) |
| [exists1_False/003](cases/expressions/exists1_False/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0198_expression_exists1_False_003.log) |
| [exists1_False/004](cases/expressions/exists1_False/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0199_expression_exists1_False_004.log) |
| [exists1_False_bounded/000](cases/expressions/exists1_False_bounded/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0200_expression_exists1_False_bounded_000.log) |
| [exists1_False_bounded/001](cases/expressions/exists1_False_bounded/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0201_expression_exists1_False_bounded_001.log) |
| [exists1_False_bounded/002](cases/expressions/exists1_False_bounded/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0202_expression_exists1_False_bounded_002.log) |
| [exists1_False_bounded/003](cases/expressions/exists1_False_bounded/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0203_expression_exists1_False_bounded_003.log) |
| [exists1_False_bounded/004](cases/expressions/exists1_False_bounded/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0204_expression_exists1_False_bounded_004.log) |
| [exists1_True/000](cases/expressions/exists1_True/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0205_expression_exists1_True_000.log) |
| [exists1_True/001](cases/expressions/exists1_True/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0206_expression_exists1_True_001.log) |
| [exists1_True/002](cases/expressions/exists1_True/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0207_expression_exists1_True_002.log) |
| [exists1_True/003](cases/expressions/exists1_True/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0208_expression_exists1_True_003.log) |
| [exists1_True/004](cases/expressions/exists1_True/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0209_expression_exists1_True_004.log) |
| [exists1_True_bounded/000](cases/expressions/exists1_True_bounded/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0210_expression_exists1_True_bounded_000.log) |
| [exists1_True_bounded/001](cases/expressions/exists1_True_bounded/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0211_expression_exists1_True_bounded_001.log) |
| [exists1_True_bounded/002](cases/expressions/exists1_True_bounded/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0212_expression_exists1_True_bounded_002.log) |
| [exists1_True_bounded/003](cases/expressions/exists1_True_bounded/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0213_expression_exists1_True_bounded_003.log) |
| [exists1_True_bounded/004](cases/expressions/exists1_True_bounded/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0214_expression_exists1_True_bounded_004.log) |
| [exists_False/000](cases/expressions/exists_False/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0215_expression_exists_False_000.log) |
| [exists_False/001](cases/expressions/exists_False/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0216_expression_exists_False_001.log) |
| [exists_False/002](cases/expressions/exists_False/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0217_expression_exists_False_002.log) |
| [exists_False/003](cases/expressions/exists_False/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0218_expression_exists_False_003.log) |
| [exists_False/004](cases/expressions/exists_False/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0219_expression_exists_False_004.log) |
| [exists_False_bounded/000](cases/expressions/exists_False_bounded/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0220_expression_exists_False_bounded_000.log) |
| [exists_False_bounded/001](cases/expressions/exists_False_bounded/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0221_expression_exists_False_bounded_001.log) |
| [exists_False_bounded/002](cases/expressions/exists_False_bounded/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0222_expression_exists_False_bounded_002.log) |
| [exists_False_bounded/003](cases/expressions/exists_False_bounded/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0223_expression_exists_False_bounded_003.log) |
| [exists_False_bounded/004](cases/expressions/exists_False_bounded/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0224_expression_exists_False_bounded_004.log) |
| [exists_True/000](cases/expressions/exists_True/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0225_expression_exists_True_000.log) |
| [exists_True/001](cases/expressions/exists_True/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0226_expression_exists_True_001.log) |
| [exists_True/002](cases/expressions/exists_True/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0227_expression_exists_True_002.log) |
| [exists_True/003](cases/expressions/exists_True/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0228_expression_exists_True_003.log) |
| [exists_True/004](cases/expressions/exists_True/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0229_expression_exists_True_004.log) |
| [exists_True_bounded/000](cases/expressions/exists_True_bounded/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0230_expression_exists_True_bounded_000.log) |
| [exists_True_bounded/001](cases/expressions/exists_True_bounded/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0231_expression_exists_True_bounded_001.log) |
| [exists_True_bounded/002](cases/expressions/exists_True_bounded/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0232_expression_exists_True_bounded_002.log) |
| [exists_True_bounded/003](cases/expressions/exists_True_bounded/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0233_expression_exists_True_bounded_003.log) |
| [exists_True_bounded/004](cases/expressions/exists_True_bounded/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0234_expression_exists_True_bounded_004.log) |
| [forall_False/000](cases/expressions/forall_False/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0236_expression_forall_False_000.log) |
| [forall_False/001](cases/expressions/forall_False/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0237_expression_forall_False_001.log) |
| [forall_False/002](cases/expressions/forall_False/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0238_expression_forall_False_002.log) |
| [forall_False/003](cases/expressions/forall_False/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0239_expression_forall_False_003.log) |
| [forall_False/004](cases/expressions/forall_False/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0240_expression_forall_False_004.log) |
| [forall_False_bounded/000](cases/expressions/forall_False_bounded/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0241_expression_forall_False_bounded_000.log) |
| [forall_False_bounded/001](cases/expressions/forall_False_bounded/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0242_expression_forall_False_bounded_001.log) |
| [forall_False_bounded/002](cases/expressions/forall_False_bounded/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0243_expression_forall_False_bounded_002.log) |
| [forall_False_bounded/003](cases/expressions/forall_False_bounded/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0244_expression_forall_False_bounded_003.log) |
| [forall_False_bounded/004](cases/expressions/forall_False_bounded/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0245_expression_forall_False_bounded_004.log) |
| [forall_True/000](cases/expressions/forall_True/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0246_expression_forall_True_000.log) |
| [forall_True/001](cases/expressions/forall_True/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0247_expression_forall_True_001.log) |
| [forall_True/002](cases/expressions/forall_True/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0248_expression_forall_True_002.log) |
| [forall_True/003](cases/expressions/forall_True/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0249_expression_forall_True_003.log) |
| [forall_True/004](cases/expressions/forall_True/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0250_expression_forall_True_004.log) |
| [forall_True_bounded/000](cases/expressions/forall_True_bounded/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0251_expression_forall_True_bounded_000.log) |
| [forall_True_bounded/001](cases/expressions/forall_True_bounded/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0252_expression_forall_True_bounded_001.log) |
| [forall_True_bounded/002](cases/expressions/forall_True_bounded/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0253_expression_forall_True_bounded_002.log) |
| [forall_True_bounded/003](cases/expressions/forall_True_bounded/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0254_expression_forall_True_bounded_003.log) |
| [forall_True_bounded/004](cases/expressions/forall_True_bounded/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0255_expression_forall_True_bounded_004.log) |
| [multiple_variables/000](cases/expressions/multiple_variables/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0356_expression_multiple_variables_000.log) |
| [multiple_variables/001](cases/expressions/multiple_variables/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0357_expression_multiple_variables_001.log) |
| [multiple_variables/002](cases/expressions/multiple_variables/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0358_expression_multiple_variables_002.log) |
| [multiple_variables/003](cases/expressions/multiple_variables/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0359_expression_multiple_variables_003.log) |
| [multiple_variables/004](cases/expressions/multiple_variables/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0360_expression_multiple_variables_004.log) |
| [multiple_variables_bounded/000](cases/expressions/multiple_variables_bounded/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0361_expression_multiple_variables_bounded_000.log) |
| [multiple_variables_bounded/001](cases/expressions/multiple_variables_bounded/001.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0362_expression_multiple_variables_bounded_001.log) |
| [multiple_variables_bounded/002](cases/expressions/multiple_variables_bounded/002.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0363_expression_multiple_variables_bounded_002.log) |
| [multiple_variables_bounded/003](cases/expressions/multiple_variables_bounded/003.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0364_expression_multiple_variables_bounded_003.log) |
| [multiple_variables_bounded/004](cases/expressions/multiple_variables_bounded/004.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B6) | [log](verification-logs/0365_expression_multiple_variables_bounded_004.log) |
| [special_result/000](cases/expressions/special_result/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B10) | [log](verification-logs/0501_expression_special_result_000.log) |
| [string/000](cases/expressions/string/000.rct) | RoboTool generator exited with exit status: 255 (RoboTool bug B9) | [log](verification-logs/0503_expression_string_000.log) |

### `unsupported_robotool`: `fdr_no_result` (10)

| Case | Reason | Log |
| --- | --- | --- |
| [cast/001](cases/expressions/cast/001.rct) | FDR ended without a refinement result (RoboTool bug B12) | [log](verification-logs/0115_expression_cast_001.log) |
| [special_from/000](cases/expressions/special_from/000.rct) | FDR ended without a refinement result (RoboTool bug B11) | [log](verification-logs/0500_expression_special_from_000.log) |
| [special_to/000](cases/expressions/special_to/000.rct) | FDR ended without a refinement result (RoboTool bug B11) | [log](verification-logs/0502_expression_special_to_000.log) |
| [the_False/002](cases/expressions/the_False/002.rct) | FDR ended without a refinement result (RoboTool bug B8) | [log](verification-logs/0520_expression_the_False_002.log) |
| [the_False/003](cases/expressions/the_False/003.rct) | FDR ended without a refinement result (RoboTool bug B8) | [log](verification-logs/0521_expression_the_False_003.log) |
| [the_False_bounded/002](cases/expressions/the_False_bounded/002.rct) | FDR ended without a refinement result (RoboTool bug B8) | [log](verification-logs/0522_expression_the_False_bounded_002.log) |
| [the_False_bounded/003](cases/expressions/the_False_bounded/003.rct) | FDR ended without a refinement result (RoboTool bug B8) | [log](verification-logs/0523_expression_the_False_bounded_003.log) |
| [the_True/003](cases/expressions/the_True/003.rct) | FDR ended without a refinement result (RoboTool bug B8) | [log](verification-logs/0524_expression_the_True_003.log) |
| [the_True_bounded/003](cases/expressions/the_True_bounded/003.rct) | FDR ended without a refinement result (RoboTool bug B8) | [log](verification-logs/0525_expression_the_True_bounded_003.log) |
| [type_check/002](cases/expressions/type_check/002.rct) | FDR ended without a refinement result (RoboTool bug B12) | [log](verification-logs/0530_expression_type_check_002.log) |

### `unsupported_robotool`: `oracle_representation_limit` (11)

| Case | Reason | Log |
| --- | --- | --- |
| `decimal/000` | oracle cannot represent fractional real observation 2.5 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0001_decimal_000.log) |
| `since/000` | oracle cannot represent fractional real observation 7.5 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0005_since_000.log) |
| `inverse/000` | oracle cannot represent fractional real observation -1.9999999999999996 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0007_inverse_000.log) |
| `divide/002` | oracle cannot represent fractional real observation -1.5 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0009_divide_002.log) |
| `divide/003` | oracle cannot represent fractional real observation -0.42857142857142855 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0010_divide_003.log) |
| `divide/008` | oracle cannot represent fractional real observation -0.6666666666666666 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0011_divide_008.log) |
| `divide/011` | oracle cannot represent fractional real observation 0.2857142857142857 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0012_divide_011.log) |
| `divide/012` | oracle cannot represent fractional real observation -2.3333333333333335 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0013_divide_012.log) |
| `divide/014` | oracle cannot represent fractional real observation 3.5 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0014_divide_014.log) |
| `cast/000` | oracle cannot represent fractional real observation 2.5 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0015_cast_000.log) |
| `type_check/001` | oracle cannot represent fractional real observation 1.5 exactly (RoboTool limitation R1: integer-valued reals) | [log](verification-logs/0016_type_check_001.log) |

## Passing cases

| Case | Expected FDR result | Model |
| --- | --- | --- |
| add/000 | `pass` | [model](cases/expressions/add/000.rct) |
| add/001 | `pass` | [model](cases/expressions/add/001.rct) |
| add/002 | `pass` | [model](cases/expressions/add/002.rct) |
| add/003 | `pass` | [model](cases/expressions/add/003.rct) |
| add/004 | `pass` | [model](cases/expressions/add/004.rct) |
| add/005 | `pass` | [model](cases/expressions/add/005.rct) |
| add/006 | `pass` | [model](cases/expressions/add/006.rct) |
| add/007 | `pass` | [model](cases/expressions/add/007.rct) |
| add/008 | `pass` | [model](cases/expressions/add/008.rct) |
| add/009 | `pass` | [model](cases/expressions/add/009.rct) |
| add/010 | `pass` | [model](cases/expressions/add/010.rct) |
| add/011 | `pass` | [model](cases/expressions/add/011.rct) |
| add/012 | `pass` | [model](cases/expressions/add/012.rct) |
| add/013 | `pass` | [model](cases/expressions/add/013.rct) |
| add/014 | `pass` | [model](cases/expressions/add/014.rct) |
| add/015 | `pass` | [model](cases/expressions/add/015.rct) |
| and/000 | `pass` | [model](cases/expressions/and/000.rct) |
| and/001 | `pass` | [model](cases/expressions/and/001.rct) |
| and/002 | `pass` | [model](cases/expressions/and/002.rct) |
| and/003 | `pass` | [model](cases/expressions/and/003.rct) |
| associativity/000 | `pass` | [model](cases/expressions/associativity/000.rct) |
| attribute/000 | `pass` | [model](cases/expressions/attribute/000.rct) |
| call_args/000 | `pass` | [model](cases/expressions/call_args/000.rct) |
| call_empty/000 | `pass` | [model](cases/expressions/call_empty/000.rct) |
| caret_concat/000 | `pass` | [model](cases/expressions/caret_concat/000.rct) |
| caret_concat/001 | `pass` | [model](cases/expressions/caret_concat/001.rct) |
| caret_concat/002 | `pass` | [model](cases/expressions/caret_concat/002.rct) |
| caret_concat/003 | `pass` | [model](cases/expressions/caret_concat/003.rct) |
| caret_concat/004 | `pass` | [model](cases/expressions/caret_concat/004.rct) |
| caret_concat/005 | `pass` | [model](cases/expressions/caret_concat/005.rct) |
| caret_concat/006 | `pass` | [model](cases/expressions/caret_concat/006.rct) |
| caret_concat/007 | `pass` | [model](cases/expressions/caret_concat/007.rct) |
| caret_concat/008 | `pass` | [model](cases/expressions/caret_concat/008.rct) |
| comprehension_False_False/000 | `pass` | [model](cases/expressions/comprehension_False_False/000.rct) |
| comprehension_False_False/001 | `pass` | [model](cases/expressions/comprehension_False_False/001.rct) |
| comprehension_False_False/002 | `pass` | [model](cases/expressions/comprehension_False_False/002.rct) |
| comprehension_False_False/003 | `pass` | [model](cases/expressions/comprehension_False_False/003.rct) |
| comprehension_False_False/004 | `pass` | [model](cases/expressions/comprehension_False_False/004.rct) |
| comprehension_False_False_bounded/000 | `pass` | [model](cases/expressions/comprehension_False_False_bounded/000.rct) |
| comprehension_False_False_bounded/001 | `pass` | [model](cases/expressions/comprehension_False_False_bounded/001.rct) |
| comprehension_False_False_bounded/002 | `pass` | [model](cases/expressions/comprehension_False_False_bounded/002.rct) |
| comprehension_False_False_bounded/003 | `pass` | [model](cases/expressions/comprehension_False_False_bounded/003.rct) |
| comprehension_False_False_bounded/004 | `pass` | [model](cases/expressions/comprehension_False_False_bounded/004.rct) |
| comprehension_False_True/000 | `pass` | [model](cases/expressions/comprehension_False_True/000.rct) |
| comprehension_False_True/001 | `pass` | [model](cases/expressions/comprehension_False_True/001.rct) |
| comprehension_False_True/002 | `pass` | [model](cases/expressions/comprehension_False_True/002.rct) |
| comprehension_False_True/003 | `pass` | [model](cases/expressions/comprehension_False_True/003.rct) |
| comprehension_False_True/004 | `pass` | [model](cases/expressions/comprehension_False_True/004.rct) |
| comprehension_False_True_bounded/000 | `pass` | [model](cases/expressions/comprehension_False_True_bounded/000.rct) |
| comprehension_False_True_bounded/001 | `pass` | [model](cases/expressions/comprehension_False_True_bounded/001.rct) |
| comprehension_False_True_bounded/002 | `pass` | [model](cases/expressions/comprehension_False_True_bounded/002.rct) |
| comprehension_False_True_bounded/003 | `pass` | [model](cases/expressions/comprehension_False_True_bounded/003.rct) |
| comprehension_False_True_bounded/004 | `pass` | [model](cases/expressions/comprehension_False_True_bounded/004.rct) |
| comprehension_True_False/000 | `pass` | [model](cases/expressions/comprehension_True_False/000.rct) |
| comprehension_True_False/001 | `pass` | [model](cases/expressions/comprehension_True_False/001.rct) |
| comprehension_True_False/002 | `pass` | [model](cases/expressions/comprehension_True_False/002.rct) |
| comprehension_True_False/003 | `pass` | [model](cases/expressions/comprehension_True_False/003.rct) |
| comprehension_True_False/004 | `pass` | [model](cases/expressions/comprehension_True_False/004.rct) |
| comprehension_True_False_bounded/000 | `pass` | [model](cases/expressions/comprehension_True_False_bounded/000.rct) |
| comprehension_True_False_bounded/001 | `pass` | [model](cases/expressions/comprehension_True_False_bounded/001.rct) |
| comprehension_True_False_bounded/002 | `pass` | [model](cases/expressions/comprehension_True_False_bounded/002.rct) |
| comprehension_True_False_bounded/003 | `pass` | [model](cases/expressions/comprehension_True_False_bounded/003.rct) |
| comprehension_True_False_bounded/004 | `pass` | [model](cases/expressions/comprehension_True_False_bounded/004.rct) |
| comprehension_True_True/000 | `pass` | [model](cases/expressions/comprehension_True_True/000.rct) |
| comprehension_True_True/001 | `pass` | [model](cases/expressions/comprehension_True_True/001.rct) |
| comprehension_True_True/002 | `pass` | [model](cases/expressions/comprehension_True_True/002.rct) |
| comprehension_True_True/003 | `pass` | [model](cases/expressions/comprehension_True_True/003.rct) |
| comprehension_True_True/004 | `pass` | [model](cases/expressions/comprehension_True_True/004.rct) |
| comprehension_True_True_bounded/000 | `pass` | [model](cases/expressions/comprehension_True_True_bounded/000.rct) |
| comprehension_True_True_bounded/001 | `pass` | [model](cases/expressions/comprehension_True_True_bounded/001.rct) |
| comprehension_True_True_bounded/002 | `pass` | [model](cases/expressions/comprehension_True_True_bounded/002.rct) |
| comprehension_True_True_bounded/003 | `pass` | [model](cases/expressions/comprehension_True_True_bounded/003.rct) |
| comprehension_True_True_bounded/004 | `pass` | [model](cases/expressions/comprehension_True_True_bounded/004.rct) |
| concat/000 | `pass` | [model](cases/expressions/concat/000.rct) |
| concat/001 | `pass` | [model](cases/expressions/concat/001.rct) |
| concat/002 | `pass` | [model](cases/expressions/concat/002.rct) |
| concat/003 | `pass` | [model](cases/expressions/concat/003.rct) |
| concat/004 | `pass` | [model](cases/expressions/concat/004.rct) |
| concat/005 | `pass` | [model](cases/expressions/concat/005.rct) |
| concat/006 | `pass` | [model](cases/expressions/concat/006.rct) |
| concat/007 | `pass` | [model](cases/expressions/concat/007.rct) |
| concat/008 | `pass` | [model](cases/expressions/concat/008.rct) |
| conditional/000 | `pass` | [model](cases/expressions/conditional/000.rct) |
| conditional/001 | `pass` | [model](cases/expressions/conditional/001.rct) |
| conditional/002 | `pass` | [model](cases/expressions/conditional/002.rct) |
| conditional/003 | `pass` | [model](cases/expressions/conditional/003.rct) |
| conditional_lazy/000 | `pass` | [model](cases/expressions/conditional_lazy/000.rct) |
| divide/000 | `pass` | [model](cases/expressions/divide/000.rct) |
| divide/004 | `pass` | [model](cases/expressions/divide/004.rct) |
| divide/006 | `pass` | [model](cases/expressions/divide/006.rct) |
| divide/007 | `pass` | [model](cases/expressions/divide/007.rct) |
| divide/010 | `pass` | [model](cases/expressions/divide/010.rct) |
| divide/015 | `pass` | [model](cases/expressions/divide/015.rct) |
| double_negative/000 | `pass` | [model](cases/expressions/double_negative/000.rct) |
| empty_sequence/000 | `pass` | [model](cases/expressions/empty_sequence/000.rct) |
| enum_literal_resolution/000 | `pass` | [model](cases/expressions/enum_literal_resolution/000.rct) |
| equal/000 | `pass` | [model](cases/expressions/equal/000.rct) |
| equal/001 | `pass` | [model](cases/expressions/equal/001.rct) |
| equal/002 | `pass` | [model](cases/expressions/equal/002.rct) |
| equal/003 | `pass` | [model](cases/expressions/equal/003.rct) |
| equal/004 | `pass` | [model](cases/expressions/equal/004.rct) |
| equal/005 | `pass` | [model](cases/expressions/equal/005.rct) |
| equal/006 | `pass` | [model](cases/expressions/equal/006.rct) |
| equal/007 | `pass` | [model](cases/expressions/equal/007.rct) |
| equal/008 | `pass` | [model](cases/expressions/equal/008.rct) |
| equal/009 | `pass` | [model](cases/expressions/equal/009.rct) |
| equal/010 | `pass` | [model](cases/expressions/equal/010.rct) |
| equal/011 | `pass` | [model](cases/expressions/equal/011.rct) |
| equal/012 | `pass` | [model](cases/expressions/equal/012.rct) |
| equal/013 | `pass` | [model](cases/expressions/equal/013.rct) |
| equal/014 | `pass` | [model](cases/expressions/equal/014.rct) |
| equal/015 | `pass` | [model](cases/expressions/equal/015.rct) |
| false/000 | `pass` | [model](cases/expressions/false/000.rct) |
| greater/000 | `pass` | [model](cases/expressions/greater/000.rct) |
| greater/001 | `pass` | [model](cases/expressions/greater/001.rct) |
| greater/002 | `pass` | [model](cases/expressions/greater/002.rct) |
| greater/003 | `pass` | [model](cases/expressions/greater/003.rct) |
| greater/004 | `pass` | [model](cases/expressions/greater/004.rct) |
| greater/005 | `pass` | [model](cases/expressions/greater/005.rct) |
| greater/006 | `pass` | [model](cases/expressions/greater/006.rct) |
| greater/007 | `pass` | [model](cases/expressions/greater/007.rct) |
| greater/008 | `pass` | [model](cases/expressions/greater/008.rct) |
| greater/009 | `pass` | [model](cases/expressions/greater/009.rct) |
| greater/010 | `pass` | [model](cases/expressions/greater/010.rct) |
| greater/011 | `pass` | [model](cases/expressions/greater/011.rct) |
| greater/012 | `pass` | [model](cases/expressions/greater/012.rct) |
| greater/013 | `pass` | [model](cases/expressions/greater/013.rct) |
| greater/014 | `pass` | [model](cases/expressions/greater/014.rct) |
| greater/015 | `pass` | [model](cases/expressions/greater/015.rct) |
| greater_equal/000 | `pass` | [model](cases/expressions/greater_equal/000.rct) |
| greater_equal/001 | `pass` | [model](cases/expressions/greater_equal/001.rct) |
| greater_equal/002 | `pass` | [model](cases/expressions/greater_equal/002.rct) |
| greater_equal/003 | `pass` | [model](cases/expressions/greater_equal/003.rct) |
| greater_equal/004 | `pass` | [model](cases/expressions/greater_equal/004.rct) |
| greater_equal/005 | `pass` | [model](cases/expressions/greater_equal/005.rct) |
| greater_equal/006 | `pass` | [model](cases/expressions/greater_equal/006.rct) |
| greater_equal/007 | `pass` | [model](cases/expressions/greater_equal/007.rct) |
| greater_equal/008 | `pass` | [model](cases/expressions/greater_equal/008.rct) |
| greater_equal/009 | `pass` | [model](cases/expressions/greater_equal/009.rct) |
| greater_equal/010 | `pass` | [model](cases/expressions/greater_equal/010.rct) |
| greater_equal/011 | `pass` | [model](cases/expressions/greater_equal/011.rct) |
| greater_equal/012 | `pass` | [model](cases/expressions/greater_equal/012.rct) |
| greater_equal/013 | `pass` | [model](cases/expressions/greater_equal/013.rct) |
| greater_equal/014 | `pass` | [model](cases/expressions/greater_equal/014.rct) |
| greater_equal/015 | `pass` | [model](cases/expressions/greater_equal/015.rct) |
| iff/000 | `pass` | [model](cases/expressions/iff/000.rct) |
| iff/001 | `pass` | [model](cases/expressions/iff/001.rct) |
| iff/002 | `pass` | [model](cases/expressions/iff/002.rct) |
| iff/003 | `pass` | [model](cases/expressions/iff/003.rct) |
| implies/000 | `pass` | [model](cases/expressions/implies/000.rct) |
| implies/001 | `pass` | [model](cases/expressions/implies/001.rct) |
| implies/002 | `pass` | [model](cases/expressions/implies/002.rct) |
| implies/003 | `pass` | [model](cases/expressions/implies/003.rct) |
| index_first/000 | `pass` | [model](cases/expressions/index_first/000.rct) |
| index_last/000 | `pass` | [model](cases/expressions/index_last/000.rct) |
| integer/000 | `pass` | [model](cases/expressions/integer/000.rct) |
| lambda_False/000 | `pass` | [model](cases/expressions/lambda_False/000.rct) |
| lambda_False/001 | `pass` | [model](cases/expressions/lambda_False/001.rct) |
| lambda_False/002 | `pass` | [model](cases/expressions/lambda_False/002.rct) |
| lambda_False/003 | `pass` | [model](cases/expressions/lambda_False/003.rct) |
| lambda_True/002 | `pass` | [model](cases/expressions/lambda_True/002.rct) |
| lambda_True/003 | `pass` | [model](cases/expressions/lambda_True/003.rct) |
| less/000 | `pass` | [model](cases/expressions/less/000.rct) |
| less/001 | `pass` | [model](cases/expressions/less/001.rct) |
| less/002 | `pass` | [model](cases/expressions/less/002.rct) |
| less/003 | `pass` | [model](cases/expressions/less/003.rct) |
| less/004 | `pass` | [model](cases/expressions/less/004.rct) |
| less/005 | `pass` | [model](cases/expressions/less/005.rct) |
| less/006 | `pass` | [model](cases/expressions/less/006.rct) |
| less/007 | `pass` | [model](cases/expressions/less/007.rct) |
| less/008 | `pass` | [model](cases/expressions/less/008.rct) |
| less/009 | `pass` | [model](cases/expressions/less/009.rct) |
| less/010 | `pass` | [model](cases/expressions/less/010.rct) |
| less/011 | `pass` | [model](cases/expressions/less/011.rct) |
| less/012 | `pass` | [model](cases/expressions/less/012.rct) |
| less/013 | `pass` | [model](cases/expressions/less/013.rct) |
| less/014 | `pass` | [model](cases/expressions/less/014.rct) |
| less/015 | `pass` | [model](cases/expressions/less/015.rct) |
| less_equal/000 | `pass` | [model](cases/expressions/less_equal/000.rct) |
| less_equal/001 | `pass` | [model](cases/expressions/less_equal/001.rct) |
| less_equal/002 | `pass` | [model](cases/expressions/less_equal/002.rct) |
| less_equal/003 | `pass` | [model](cases/expressions/less_equal/003.rct) |
| less_equal/004 | `pass` | [model](cases/expressions/less_equal/004.rct) |
| less_equal/005 | `pass` | [model](cases/expressions/less_equal/005.rct) |
| less_equal/006 | `pass` | [model](cases/expressions/less_equal/006.rct) |
| less_equal/007 | `pass` | [model](cases/expressions/less_equal/007.rct) |
| less_equal/008 | `pass` | [model](cases/expressions/less_equal/008.rct) |
| less_equal/009 | `pass` | [model](cases/expressions/less_equal/009.rct) |
| less_equal/010 | `pass` | [model](cases/expressions/less_equal/010.rct) |
| less_equal/011 | `pass` | [model](cases/expressions/less_equal/011.rct) |
| less_equal/012 | `pass` | [model](cases/expressions/less_equal/012.rct) |
| less_equal/013 | `pass` | [model](cases/expressions/less_equal/013.rct) |
| less_equal/014 | `pass` | [model](cases/expressions/less_equal/014.rct) |
| less_equal/015 | `pass` | [model](cases/expressions/less_equal/015.rct) |
| let/000 | `pass` | [model](cases/expressions/let/000.rct) |
| matrix/000 | `pass` | [model](cases/expressions/matrix/000.rct) |
| membership/000 | `pass` | [model](cases/expressions/membership/000.rct) |
| membership/001 | `pass` | [model](cases/expressions/membership/001.rct) |
| membership/002 | `pass` | [model](cases/expressions/membership/002.rct) |
| membership/003 | `pass` | [model](cases/expressions/membership/003.rct) |
| modulo/000 | `pass` | [model](cases/expressions/modulo/000.rct) |
| modulo/002 | `pass` | [model](cases/expressions/modulo/002.rct) |
| modulo/003 | `pass` | [model](cases/expressions/modulo/003.rct) |
| modulo/004 | `pass` | [model](cases/expressions/modulo/004.rct) |
| modulo/006 | `pass` | [model](cases/expressions/modulo/006.rct) |
| modulo/007 | `pass` | [model](cases/expressions/modulo/007.rct) |
| modulo/008 | `pass` | [model](cases/expressions/modulo/008.rct) |
| modulo/010 | `pass` | [model](cases/expressions/modulo/010.rct) |
| modulo/011 | `pass` | [model](cases/expressions/modulo/011.rct) |
| modulo/012 | `pass` | [model](cases/expressions/modulo/012.rct) |
| modulo/014 | `pass` | [model](cases/expressions/modulo/014.rct) |
| modulo/015 | `pass` | [model](cases/expressions/modulo/015.rct) |
| multiply/000 | `pass` | [model](cases/expressions/multiply/000.rct) |
| multiply/001 | `pass` | [model](cases/expressions/multiply/001.rct) |
| multiply/002 | `pass` | [model](cases/expressions/multiply/002.rct) |
| multiply/003 | `pass` | [model](cases/expressions/multiply/003.rct) |
| multiply/004 | `pass` | [model](cases/expressions/multiply/004.rct) |
| multiply/005 | `pass` | [model](cases/expressions/multiply/005.rct) |
| multiply/006 | `pass` | [model](cases/expressions/multiply/006.rct) |
| multiply/007 | `pass` | [model](cases/expressions/multiply/007.rct) |
| multiply/008 | `pass` | [model](cases/expressions/multiply/008.rct) |
| multiply/009 | `pass` | [model](cases/expressions/multiply/009.rct) |
| multiply/010 | `pass` | [model](cases/expressions/multiply/010.rct) |
| multiply/011 | `pass` | [model](cases/expressions/multiply/011.rct) |
| multiply/012 | `pass` | [model](cases/expressions/multiply/012.rct) |
| multiply/013 | `pass` | [model](cases/expressions/multiply/013.rct) |
| multiply/014 | `pass` | [model](cases/expressions/multiply/014.rct) |
| multiply/015 | `pass` | [model](cases/expressions/multiply/015.rct) |
| negate/000 | `pass` | [model](cases/expressions/negate/000.rct) |
| negate/001 | `pass` | [model](cases/expressions/negate/001.rct) |
| negate/002 | `pass` | [model](cases/expressions/negate/002.rct) |
| negate/003 | `pass` | [model](cases/expressions/negate/003.rct) |
| negate/004 | `pass` | [model](cases/expressions/negate/004.rct) |
| negate/005 | `pass` | [model](cases/expressions/negate/005.rct) |
| negate/006 | `pass` | [model](cases/expressions/negate/006.rct) |
| negate/007 | `pass` | [model](cases/expressions/negate/007.rct) |
| negate/008 | `pass` | [model](cases/expressions/negate/008.rct) |
| negate/009 | `pass` | [model](cases/expressions/negate/009.rct) |
| negate/010 | `pass` | [model](cases/expressions/negate/010.rct) |
| negate/011 | `pass` | [model](cases/expressions/negate/011.rct) |
| negate/012 | `pass` | [model](cases/expressions/negate/012.rct) |
| negate/013 | `pass` | [model](cases/expressions/negate/013.rct) |
| negate/014 | `pass` | [model](cases/expressions/negate/014.rct) |
| negate/015 | `pass` | [model](cases/expressions/negate/015.rct) |
| not/000 | `pass` | [model](cases/expressions/not/000.rct) |
| not/001 | `pass` | [model](cases/expressions/not/001.rct) |
| not/002 | `pass` | [model](cases/expressions/not/002.rct) |
| not/003 | `pass` | [model](cases/expressions/not/003.rct) |
| or/000 | `pass` | [model](cases/expressions/or/000.rct) |
| or/001 | `pass` | [model](cases/expressions/or/001.rct) |
| or/002 | `pass` | [model](cases/expressions/or/002.rct) |
| or/003 | `pass` | [model](cases/expressions/or/003.rct) |
| parentheses/000 | `pass` | [model](cases/expressions/parentheses/000.rct) |
| parenthesized_type/000 | `pass` | [model](cases/expressions/parenthesized_type/000.rct) |
| precedence/000 | `pass` | [model](cases/expressions/precedence/000.rct) |
| range_False_False_False/000 | `pass` | [model](cases/expressions/range_False_False_False/000.rct) |
| range_False_False_False/001 | `pass` | [model](cases/expressions/range_False_False_False/001.rct) |
| range_False_False_False/002 | `pass` | [model](cases/expressions/range_False_False_False/002.rct) |
| range_False_False_False/003 | `pass` | [model](cases/expressions/range_False_False_False/003.rct) |
| range_False_False_False/004 | `pass` | [model](cases/expressions/range_False_False_False/004.rct) |
| range_False_False_False/005 | `pass` | [model](cases/expressions/range_False_False_False/005.rct) |
| range_False_False_False/006 | `pass` | [model](cases/expressions/range_False_False_False/006.rct) |
| range_False_False_False/007 | `pass` | [model](cases/expressions/range_False_False_False/007.rct) |
| range_False_False_False/008 | `pass` | [model](cases/expressions/range_False_False_False/008.rct) |
| range_False_False_False/009 | `pass` | [model](cases/expressions/range_False_False_False/009.rct) |
| range_False_False_False/010 | `pass` | [model](cases/expressions/range_False_False_False/010.rct) |
| range_False_False_False/011 | `pass` | [model](cases/expressions/range_False_False_False/011.rct) |
| range_False_False_False/012 | `pass` | [model](cases/expressions/range_False_False_False/012.rct) |
| range_False_False_False/013 | `pass` | [model](cases/expressions/range_False_False_False/013.rct) |
| range_False_False_False/014 | `pass` | [model](cases/expressions/range_False_False_False/014.rct) |
| range_False_False_False/015 | `pass` | [model](cases/expressions/range_False_False_False/015.rct) |
| range_False_True_False/000 | `pass` | [model](cases/expressions/range_False_True_False/000.rct) |
| range_False_True_False/001 | `pass` | [model](cases/expressions/range_False_True_False/001.rct) |
| range_False_True_False/002 | `pass` | [model](cases/expressions/range_False_True_False/002.rct) |
| range_False_True_False/003 | `pass` | [model](cases/expressions/range_False_True_False/003.rct) |
| range_False_True_False/004 | `pass` | [model](cases/expressions/range_False_True_False/004.rct) |
| range_False_True_False/005 | `pass` | [model](cases/expressions/range_False_True_False/005.rct) |
| range_False_True_False/006 | `pass` | [model](cases/expressions/range_False_True_False/006.rct) |
| range_False_True_False/007 | `pass` | [model](cases/expressions/range_False_True_False/007.rct) |
| range_False_True_False/008 | `pass` | [model](cases/expressions/range_False_True_False/008.rct) |
| range_False_True_False/009 | `pass` | [model](cases/expressions/range_False_True_False/009.rct) |
| range_False_True_False/010 | `pass` | [model](cases/expressions/range_False_True_False/010.rct) |
| range_False_True_False/011 | `pass` | [model](cases/expressions/range_False_True_False/011.rct) |
| range_False_True_False/012 | `pass` | [model](cases/expressions/range_False_True_False/012.rct) |
| range_False_True_False/013 | `pass` | [model](cases/expressions/range_False_True_False/013.rct) |
| range_False_True_False/014 | `pass` | [model](cases/expressions/range_False_True_False/014.rct) |
| range_False_True_False/015 | `pass` | [model](cases/expressions/range_False_True_False/015.rct) |
| range_True_False_False/000 | `pass` | [model](cases/expressions/range_True_False_False/000.rct) |
| range_True_False_False/001 | `pass` | [model](cases/expressions/range_True_False_False/001.rct) |
| range_True_False_False/002 | `pass` | [model](cases/expressions/range_True_False_False/002.rct) |
| range_True_False_False/003 | `pass` | [model](cases/expressions/range_True_False_False/003.rct) |
| range_True_False_False/004 | `pass` | [model](cases/expressions/range_True_False_False/004.rct) |
| range_True_False_False/005 | `pass` | [model](cases/expressions/range_True_False_False/005.rct) |
| range_True_False_False/006 | `pass` | [model](cases/expressions/range_True_False_False/006.rct) |
| range_True_False_False/007 | `pass` | [model](cases/expressions/range_True_False_False/007.rct) |
| range_True_False_False/008 | `pass` | [model](cases/expressions/range_True_False_False/008.rct) |
| range_True_False_False/009 | `pass` | [model](cases/expressions/range_True_False_False/009.rct) |
| range_True_False_False/010 | `pass` | [model](cases/expressions/range_True_False_False/010.rct) |
| range_True_False_False/011 | `pass` | [model](cases/expressions/range_True_False_False/011.rct) |
| range_True_False_False/012 | `pass` | [model](cases/expressions/range_True_False_False/012.rct) |
| range_True_False_False/013 | `pass` | [model](cases/expressions/range_True_False_False/013.rct) |
| range_True_False_False/014 | `pass` | [model](cases/expressions/range_True_False_False/014.rct) |
| range_True_False_False/015 | `pass` | [model](cases/expressions/range_True_False_False/015.rct) |
| range_True_True_False/000 | `pass` | [model](cases/expressions/range_True_True_False/000.rct) |
| range_True_True_False/001 | `pass` | [model](cases/expressions/range_True_True_False/001.rct) |
| range_True_True_False/002 | `pass` | [model](cases/expressions/range_True_True_False/002.rct) |
| range_True_True_False/003 | `pass` | [model](cases/expressions/range_True_True_False/003.rct) |
| range_True_True_False/004 | `pass` | [model](cases/expressions/range_True_True_False/004.rct) |
| range_True_True_False/005 | `pass` | [model](cases/expressions/range_True_True_False/005.rct) |
| range_True_True_False/006 | `pass` | [model](cases/expressions/range_True_True_False/006.rct) |
| range_True_True_False/007 | `pass` | [model](cases/expressions/range_True_True_False/007.rct) |
| range_True_True_False/008 | `pass` | [model](cases/expressions/range_True_True_False/008.rct) |
| range_True_True_False/009 | `pass` | [model](cases/expressions/range_True_True_False/009.rct) |
| range_True_True_False/010 | `pass` | [model](cases/expressions/range_True_True_False/010.rct) |
| range_True_True_False/011 | `pass` | [model](cases/expressions/range_True_True_False/011.rct) |
| range_True_True_False/012 | `pass` | [model](cases/expressions/range_True_True_False/012.rct) |
| range_True_True_False/013 | `pass` | [model](cases/expressions/range_True_True_False/013.rct) |
| range_True_True_False/014 | `pass` | [model](cases/expressions/range_True_True_False/014.rct) |
| range_True_True_False/015 | `pass` | [model](cases/expressions/range_True_True_False/015.rct) |
| record/000 | `pass` | [model](cases/expressions/record/000.rct) |
| sequence/000 | `pass` | [model](cases/expressions/sequence/000.rct) |
| set_duplicates/000 | `pass` | [model](cases/expressions/set_duplicates/000.rct) |
| set_empty/000 | `pass` | [model](cases/expressions/set_empty/000.rct) |
| set_range/000 | `pass` | [model](cases/expressions/set_range/000.rct) |
| set_range/001 | `pass` | [model](cases/expressions/set_range/001.rct) |
| set_range/002 | `pass` | [model](cases/expressions/set_range/002.rct) |
| set_range/003 | `pass` | [model](cases/expressions/set_range/003.rct) |
| set_range/005 | `pass` | [model](cases/expressions/set_range/005.rct) |
| set_range/006 | `pass` | [model](cases/expressions/set_range/006.rct) |
| set_range/007 | `pass` | [model](cases/expressions/set_range/007.rct) |
| set_range/010 | `pass` | [model](cases/expressions/set_range/010.rct) |
| set_range/011 | `pass` | [model](cases/expressions/set_range/011.rct) |
| set_range/015 | `pass` | [model](cases/expressions/set_range/015.rct) |
| short_circuit_and/000 | `pass` | [model](cases/expressions/short_circuit_and/000.rct) |
| short_circuit_or/000 | `pass` | [model](cases/expressions/short_circuit_or/000.rct) |
| spaced_empty_sequence/000 | `pass` | [model](cases/expressions/spaced_empty_sequence/000.rct) |
| subtract/000 | `pass` | [model](cases/expressions/subtract/000.rct) |
| subtract/001 | `pass` | [model](cases/expressions/subtract/001.rct) |
| subtract/002 | `pass` | [model](cases/expressions/subtract/002.rct) |
| subtract/003 | `pass` | [model](cases/expressions/subtract/003.rct) |
| subtract/004 | `pass` | [model](cases/expressions/subtract/004.rct) |
| subtract/005 | `pass` | [model](cases/expressions/subtract/005.rct) |
| subtract/006 | `pass` | [model](cases/expressions/subtract/006.rct) |
| subtract/007 | `pass` | [model](cases/expressions/subtract/007.rct) |
| subtract/008 | `pass` | [model](cases/expressions/subtract/008.rct) |
| subtract/009 | `pass` | [model](cases/expressions/subtract/009.rct) |
| subtract/010 | `pass` | [model](cases/expressions/subtract/010.rct) |
| subtract/011 | `pass` | [model](cases/expressions/subtract/011.rct) |
| subtract/012 | `pass` | [model](cases/expressions/subtract/012.rct) |
| subtract/013 | `pass` | [model](cases/expressions/subtract/013.rct) |
| subtract/014 | `pass` | [model](cases/expressions/subtract/014.rct) |
| subtract/015 | `pass` | [model](cases/expressions/subtract/015.rct) |
| true/000 | `pass` | [model](cases/expressions/true/000.rct) |
| tuple/000 | `pass` | [model](cases/expressions/tuple/000.rct) |
| type_check/000 | `pass` | [model](cases/expressions/type_check/000.rct) |
| unequal/000 | `pass` | [model](cases/expressions/unequal/000.rct) |
| unequal/001 | `pass` | [model](cases/expressions/unequal/001.rct) |
| unequal/002 | `pass` | [model](cases/expressions/unequal/002.rct) |
| unequal/003 | `pass` | [model](cases/expressions/unequal/003.rct) |
| unequal/004 | `pass` | [model](cases/expressions/unequal/004.rct) |
| unequal/005 | `pass` | [model](cases/expressions/unequal/005.rct) |
| unequal/006 | `pass` | [model](cases/expressions/unequal/006.rct) |
| unequal/007 | `pass` | [model](cases/expressions/unequal/007.rct) |
| unequal/008 | `pass` | [model](cases/expressions/unequal/008.rct) |
| unequal/009 | `pass` | [model](cases/expressions/unequal/009.rct) |
| unequal/010 | `pass` | [model](cases/expressions/unequal/010.rct) |
| unequal/011 | `pass` | [model](cases/expressions/unequal/011.rct) |
| unequal/012 | `pass` | [model](cases/expressions/unequal/012.rct) |
| unequal/013 | `pass` | [model](cases/expressions/unequal/013.rct) |
| unequal/014 | `pass` | [model](cases/expressions/unequal/014.rct) |
| unequal/015 | `pass` | [model](cases/expressions/unequal/015.rct) |
| vector/000 | `pass` | [model](cases/expressions/vector/000.rct) |
| whitespace/000 | `pass` | [model](cases/expressions/whitespace/000.rct) |
| assignment/mismatch | `mismatch` | [model](cases/statements/assignment/mismatch.rct) |
| assignment/pass | `pass` | [model](cases/statements/assignment/pass.rct) |
| boolean_sequence/empty | `pass` | [model](cases/statements/boolean_sequence/empty.rct) |
| boolean_sequence/singleton | `pass` | [model](cases/statements/boolean_sequence/singleton.rct) |
| bounded_scan/empty | `pass` | [model](cases/statements/bounded_scan/empty.rct) |
| bounded_scan/three | `pass` | [model](cases/statements/bounded_scan/three.rct) |
| conditional/mismatch | `mismatch` | [model](cases/statements/conditional/mismatch.rct) |
| conditional/pass | `pass` | [model](cases/statements/conditional/pass.rct) |
| conditional_threshold/above | `pass` | [model](cases/statements/conditional_threshold/above.rct) |
| conditional_threshold/at | `pass` | [model](cases/statements/conditional_threshold/at.rct) |
| conditional_threshold/below | `pass` | [model](cases/statements/conditional_threshold/below.rct) |
| event_order/mismatch | `mismatch` | [model](cases/statements/event_order/mismatch.rct) |
| event_order/pass | `pass` | [model](cases/statements/event_order/pass.rct) |
| input_event/lidar_range | `pass` | [model](cases/statements/input_event/lidar_range.rct) |
| input_event/pass | `pass` | [model](cases/statements/input_event/pass.rct) |
| mask_update/pass | `pass` | [model](cases/statements/mask_update/pass.rct) |
| nested_sequence_read/pass | `pass` | [model](cases/statements/nested_sequence_read/pass.rct) |
| prob_mask_update/pass | `pass` | [model](cases/statements/prob_mask_update/pass.rct) |
| pure_helper/mismatch | `mismatch` | [model](cases/statements/pure_helper/mismatch.rct) |
| pure_helper/pass | `pass` | [model](cases/statements/pure_helper/pass.rct) |
| record_construct/pass | `pass` | [model](cases/statements/record_construct/pass.rct) |
| record_nested/pass | `pass` | [model](cases/statements/record_nested/pass.rct) |
| record_update/pass | `pass` | [model](cases/statements/record_update/pass.rct) |
| sequence/mismatch | `mismatch` | [model](cases/statements/sequence/mismatch.rct) |
| sequence/pass | `pass` | [model](cases/statements/sequence/pass.rct) |
| sequence_concat/pass | `pass` | [model](cases/statements/sequence_concat/pass.rct) |
| sequence_index/pass | `pass` | [model](cases/statements/sequence_index/pass.rct) |
| sequence_size/pass | `pass` | [model](cases/statements/sequence_size/pass.rct) |
