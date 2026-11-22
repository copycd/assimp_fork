# meshoptimizer (decoder subset)

Used by the glTF 2.0 importer to decode `EXT_meshopt_compression` / `KHR_meshopt_compression`
buffer views (see `code/AssetLib/glTF2/glTF2Asset.inl`, `BufferView::DecodeMeshopt`).

- Upstream: https://github.com/zeux/meshoptimizer
- Version: v1.3 (commit `9e1f07b159d3cb777f1c67ed31fc11fd117986f4`)
- License: MIT, see `LICENSE.md`

Only the files needed for decoding are included. They are copied unmodified from `src/`:

| File | Provides |
|---|---|
| `meshoptimizer.h` | public header |
| `vertexcodec.cpp` | `meshopt_decodeVertexBuffer` |
| `indexcodec.cpp` | `meshopt_decodeIndexBuffer`, `meshopt_decodeIndexSequence` |
| `vertexfilter.cpp` | `meshopt_decodeFilterOct`, `meshopt_decodeFilterQuat`, `meshopt_decodeFilterExp`, `meshopt_decodeFilterColor` |

To update, copy these four files and `LICENSE.md` from a newer release and update the version above.
The build can be disabled with `-DASSIMP_BUILD_MESHOPT=OFF`; files that require meshopt compression
are then rejected with an error.
