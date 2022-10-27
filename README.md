# Learn Disparity Space from Light Field via a Query Mechanism

# Intro: 
Learn not only a 2D disaprity map, but also a 2.5D disparity space from  Light Field

As one representation of the scene depth information in light field(LF), the disparity space is a 2.5-dimensional(2.5D) data composed of a point set $(x, y, d)$, a feature that is often overlooked in deep learning era yet. Current advanced learning-based methods usually adopt an end-to-end approach for LF disparity estimation: input 2D LF images and output the target 2D disparity map. These 2D to 2D methods tend to ignore the additional 0.5D disparity information, named disparity continuity in this paper, and fails to hold it when scene refocuses. Although traditional methods with spatial division could hold the continuity, slow speed and low precision limit its application, compared with those learning-based. To solve the above problem, we propose a query mechanism to learn 2.5D disparity space directly from light field images, rather than just a 2D disparity map. Firstly, we take samples directly from disparity space for learning, which complements the missing 0.5D information compared to those only use ground truth.  Secondly, three encoder networks are designed for LF encoding, including sub-aperture images(SAIs) based and epipolar plane images(EPIs) based encoding, to prove the generality of our query mechanism. Thirdly, we make the query process conditioned on disparity value $d$, then design a conditional residual block to perform spatial query by combining sampled $d$ with LF features extracted. At last, to extract the target disparity map from the 2.5D space learned , three query-based generation algorithms are proposed and compared in terms of efficiency and precision, including space query, point query and region query.   


# Some details:
1. Three encoder networks: EPI Volume(Query), EPI Patch(Query), Cost Volume(Query)
2. Three sampling strategies: Uniform Sampling, Gaussion Sampling, Iterative Sampling
3. One decoder network: a conditional-residual-block-based Decoder.
4. Three generation algorithms: Space Query, Point Query, Region Query.
5. Refinement: PixelNet
