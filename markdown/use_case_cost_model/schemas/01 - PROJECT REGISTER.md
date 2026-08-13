# Project Register Schema

## Purpose

Defines the identity, workflow status, baseline, and version metadata for one cost-modeling project.

## Fields

| Field | Required | Type / Allowed Values | Description |
|---|---:|---|---|
| Project ID | Yes | Text | Stable identifier, e.g. `PHIG-B4-CANCER` |
| Project Name | Yes | Text | Human-readable pilot/use-case name |
| Version | Yes | Text | Workflow state version |
| Workflow Status | Yes | Enum | Ingest / Stage 1 / Gate 1 / Stage 2 / Stage 3 / Gate 2 / Stage 4 / Review / Final |
| Authoritative Scope Source | Yes | Reference | Primary pilot proposal/description |
| Reference Baseline | Yes | Text | Normally Chronic Care Cascade |
| CCC Baseline Version | Preferred | Text | Workbook/report version used |
| Target Dollar Year | Preferred | Integer year | Model dollar basis |
| Created | Yes | Date | Creation date |
| Last Updated | Yes | Date | Last state change |
| Human Gate 1 Status | Yes | Enum | Pending / Approved / Approved with conditions |
| Human Gate 2 Status | Yes | Enum | N/A / Pending / Approved / Approved with conditions |
| Benchmark Report Version | Preferred | Text | Current report version |
| Cost Model Version | Preferred | Text | Current workbook version |
| Independent Review Status | Preferred | Enum | Not started / In review / Complete |
| Notes | No | Text | Material project-level notes |
