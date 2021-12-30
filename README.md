<h1>ResMLP: Feedforward networks for image classification with data-efficient training </h1>


![Model](https://github.com/dslisleedh/ResMLP-tensorflow2/blob/master/Model.PNG)
[arXiv](https://arxiv.org/abs/2105.03404)

<h3>
요약 :  
  
[MLP-Mixer](https://github.com/dslisleedh/MLPMixer-tensorflow2)와 거의 비슷한 형태를 가지고 있으나, Layer Normalization 대신 Affine Layer를 사용함. Affine layer는 Layer Normalization과 비슷하지만, Batch의 통계량을 사용하지 않기에 좀 더
Robust하고 Stable하며 Inference time에 추가적인 Cost를 소모하지 않음.  
</h3>
<h4>
개인적인 생각 : SELU 논문에서 External Normalization(BN, LN)은 속도저하를 유발한다 했었는데, 그것도 고려해봐야할듯.
</h4>


<h5>
주의 :  
Affine Layer는 Linear FC 전과 후에 하나씩들어감.  

Linear FC전의 Affine Layer("pre-normalization")는 기존 값과 비슷한 결과를 넣어주기 위해 a를 굉장히 작은 값으로, b를 1로 initialization하고,  
Linear FC 후의 Affine Layer("post-normalization")는 Shortcut-connection과 합쳐지더라도 비슷한 값이 유지되게 단순하게 매우 작은 값의 a만을 initialization하여 사용함.
</h5>
