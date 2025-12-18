# Execute Sub-Workflow Node Issues

## The Problem

When creating workflows via JSON export/import, "Execute Sub-Workflow" nodes (formerly "Execute Workflow") become out of date.

**Error message**: "This node is out of date. Please upgrade by removing it and adding a new one"

## Why This Happens

The Execute Sub-Workflow node structure changes between n8n versions. Exported JSON files contain node configurations that may not match the current n8n version's expected format.

## Solution

1. Import the workflow JSON (Execute Sub-Workflow nodes will show errors)
2. Delete the old Execute Sub-Workflow nodes
3. Add fresh "Execute Sub-Workflow" nodes from the node palette
4. Select "Database" as source
5. Choose the target workflow from the dropdown

## Best Practice

When creating workflow JSON files for import:
- **Option 1**: Omit Execute Sub-Workflow nodes entirely and add them manually after import
- **Option 2**: Document which nodes need to be replaced after import in commit messages or documentation

This saves time vs. debugging why imported Execute Sub-Workflow nodes aren't working.
