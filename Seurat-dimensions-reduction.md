               <!-- Dimensions reduction Section -->
                <h2 id="Seurat-dimensions-reduction" class="mt-5">Dimensions reduction</h2>
                <p>
                    The spatial transcriptomics datasets often contain tens of thousands of genes across tens of
                    thousands of spots or cells.
                    Demension reduction simplifies high-dimensional data into a lower-dimensional representation while
                    retaining the most important biological variation.
                    This aids in visualization, clustering, and downstream analyses.
                </p>
                <p>
                    Common techniques for dimension reduction:
                </p>
                <h4>Principal Component Analysis (PCA)</h4>
                <p>
                    Projects high-dimensional gene expression data into a set of orthogonal components.
                    Captures the largest variance in the dataset using fewer dimensions (principal components).
                </p>
                <!-- Code block toggle button -->
                <button class="btn btn btn-info float-right" type="button" data-toggle="collapse"
                    data-target="#SeuratPCACode" aria-expanded="false" aria-controls="SeuratPCACode">
                    Show/Hide Code
                </button>
                <!-- Collapsible code block -->
                <div class="collapse" id="SeuratPCACode">
                    <pre><code class="language-r">
st_data <- FindVariableFeatures(object = st_data)
st_data <- ScaleData(object = st_data)
st_data <- RunPCA(object = st_data)
                </code></pre>
                </div>

                <h4>Uniform Manifold Approximation and Projection (UMAP)</h4>
                <p>
                    Non-linear technique preserving global and local structures in the data.
                    Better suited for preserving clusters in noisy datasets compared to PCA.
                </p>
                <!-- Code block toggle button -->
                <button class="btn btn btn-info float-right" type="button" data-toggle="collapse"
                    data-target="#SeuratUMAPCode" aria-expanded="false" aria-controls="SeuratUMAPCode">
                    Show/Hide Code
                </button>
                <!-- Collapsible code block -->
                <div class="collapse" id="SeuratUMAPCode">
                    <pre><code class="language-r">
st_data <- FindNeighbors(object = st_data, dims = 1:30)  
st_data <- RunUMAP(object = st_data, dims = 1:30)   
                </code></pre>
                </div>