
# Q/A List

* convolution에서 특정 채널의 weight만 고정시킬 방법이 있을까요?

self.weight.requires_grad = False 로 설정

수정할 parameter를 filter 하는 방법이 있습니다. 
optimizer = optim.Adam( 
  filter(lambda p: p.requires_grad, model.parameters()),
  lr=hp.initial_learning_rate,
  betas=(hp.adam_beta1, hp.adam_beta2),
  weight_decay=0.0)
  
