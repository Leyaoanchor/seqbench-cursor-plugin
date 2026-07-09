# SeqBench Plugin Manifest

Plugin manifests for adding the [SeqBench](https://seqbench.com) MCP server to Cursor and
Claude Code — a bioinformatics tool server built around batch processing, sequence/plasmid
visualization, and multi-tool workflow pipelines for DNA, RNA and protein sequence analysis.

## What it adds

An MCP server (`https://seqbench.com/api/mcp`, Streamable HTTP) exposing tools for:

- Batch (`/api/v1/batch`) and multi-tool workflow pipelines over a whole FASTA file
- Sequence & plasmid visualization: plasmid viewer, virtual gel, Sanger trace viewer
- Primer/oligo Tm, dimers and design
- Restriction sites & cloning simulation
- CRISPR guide design
- Protein properties & codon optimisation
- Translation & ORFs
- Sequence alignment & variant calling
- Sequence basics: reverse complement, GC content, format conversion

Full tool list and docs: [seqbench.com/mcp](https://seqbench.com/mcp).

## Install

**Cursor** — install from the Cursor Marketplace, or add manually to your MCP config:

```json
{
  "mcpServers": {
    "seqbench": {
      "url": "https://seqbench.com/api/mcp"
    }
  }
}
```

**Claude Code** — install from the `claude-plugins-community` marketplace, or load this repo
directly for development:

```bash
claude --plugin-dir /path/to/seqbench-cursor-plugin
```

No API key or account required. Every tool is a pure, deterministic function — nothing is
stored or persisted server-side.

## Repository layout

- `.cursor-plugin/plugin.json`, `.plugin/plugin.json` — Cursor plugin manifests
- `.claude-plugin/plugin.json` — Claude Code plugin manifest
- `.mcp.json` — shared MCP server config, read by both clients

## License

MIT — see [LICENSE](./LICENSE). This repository contains only plugin manifests; the SeqBench
service itself is at [seqbench.com](https://seqbench.com).
