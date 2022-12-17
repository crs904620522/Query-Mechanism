# Learn Disparity Space from Light Field via a Query Mechanism

# Intro: 
Learn not only a 2D disaprity map, but also a 2.5D disparity space from  Light Field

As one representation of scene depth information in light field(LF), disparity space is a 2.5-dimensional(2.5D) data composed of many disparity points $p(x, y, d)$, a feature that is often overlooked in deep learning era yet. Current learning-based methods usually adopt an end-to-end approach for LF disparity estimation: input 2D LF images and output the target 2D disparity map. These 2D to 2D methods tend to ignore the additional 0.5D space information, named disparity continuity in this paper, causing limited performance. Although traditional methods with label division can hold such continuity, slow speed and low precision limit its application. To solve the above problem, we propose a query mechanism to learn 2.5D disparity space directly from LF images, rather than just a 2D disparity map. Firstly, we sample data from disparity space directly for learning, which complements the missing 0.5D information compared to those only use ground truth.  Secondly, an encoder netwrok is used for LF encoding to extract scene geometric information, where we  have proposed four encoders for different LF representations processing, to prove the generality of our query mechanism. Thirdly, we make the query process conditioned on point $p(x, y, d)$, then design a conditional decoder to perform disparity query by combining sampled  point with LF features extracted. At last, to extract the target disparity map from the 2.5D space learned, three query-based generation algorithms are proposed and compared in terms of efficiency and precision, including space query, point query and region query. 


# Some details:
1. Four encoder networks: EPI-Query, Stack-Query, SAI-Query, MacPI-Query
2. Three sampling strategies: Space Uniform Sampling, Surface Gaussion Sampling, Query Iterative Sampling
3. One decoder network: a conditional-residual-block-based Decoder.
4. Three generation algorithms: Space Query, Point Query, Region Query.
5. Post Processing: BpCNet [Take your model further: a general post-refinement network for Light Field disparity estimation via BadPix correction]
