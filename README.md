TRACE-Net Anonymous Reproducibility Package
This repository contains the implementation materials for TRACE-Net. It is organized as an anonymous reproducibility package and contains source code, execution scripts, configuration files, verification tests, provenance documentation, and structured reference artifacts.
Repository contents
Path	Contents
configs/	YAML configuration files defining the study protocol, baseline specifications, and reporting settings.
docs/	Documentation describing the computational definitions, reproducibility protocol, and data-provenance records.
manifests/	JSON manifests for expected record counts and input-column contracts.
reference_logs/	Reference execution-trace files and their accompanying documentation.
reference_results/	Structured CSV artifacts for fold-level summaries, baseline comparisons, ablation settings, external-validation records, robustness checks, anchor counts, efficiency records, and inferential summaries.
scripts/	Command-line scripts for retrieving and preparing public sources, auditing data, building splits, training, ablation analysis, external evaluation, robustness analysis, statistical analysis, report construction, reference-artifact construction, and package verification.
src/trace_net/	TRACE-Net source package. It contains modules for data handling, normalization, leakage-aware splitting, temporal-anchor construction, model definition, training, loss functions, calibration, conformal procedures, adaptation, external evaluation, metrics, statistical routines, dataset utilities, and command-line execution.
tests/	Unit tests covering normalization, anchors, losses, adaptation, conformal procedures, metrics, and package contracts.


Main source modules
The src/trace_net/ package is divided into the following modules:
Module	Contents
data.py, datasets.py, normalization.py	Input handling, dataset utilities, and deterministic text normalization.
splitting.py, anchors.py, temporal.py	Group-aware partitioning, temporal-anchor construction, and temporal-effect utilities.
model.py, training.py, losses.py, runner.py	Model architecture, optimization workflow, objective functions, and experiment orchestration.
conformal.py, adaptation.py, groupdro.py	Conformal procedures, adaptation components, and group-robust optimization utilities.
external.py, metrics.py, statistics.py	External-evaluation procedures, metric calculation, and statistical analysis routines.
cli.py	Command-line entry points for package execution.


Execution and verification scripts
The scripts/ directory includes the following entry points:
- fetch_public_data.py — retrieves the public source materials required by the package.
- prepare_upworthy.py and prepare_mind.py — prepare the source-specific input records.
- audit_data.py — checks data records against the package contracts.
- build_splits.py — constructs the prespecified partitions.
- run_training.py and train_one.py — launch the training workflow.
- run_ablation.py, run_external.py, and run_robustness.py — launch the corresponding evaluation workflows.
- run_statistics.py and build_report.py — generate statistical and reporting artifacts.
- build_reference_artifacts.py — builds the supplied reference artifacts.
- verify_package.py — verifies package structure and declared contracts.
Configuration and documentation files
- configs/study.yaml defines study-level settings, partition rules, model settings, decision settings, and software/hardware fields.
- configs/baselines.yaml records the baseline-model specifications and shared input definitions.
- configs/reporting.yaml defines output and reporting settings.
- docs/METHODS_AND_FORMULAS.md records the computational definitions used by the implementation.
- docs/REPRODUCIBILITY.md records the execution order, partitioning safeguards, and run-record requirements.
- docs/DATA_PROVENANCE.md records the package-level data provenance information.
Package conventions
Runtime outputs are written separately from the immutable reference artifacts. The package uses configuration files and manifests to keep input contracts, execution settings, and verification checks explicit.
