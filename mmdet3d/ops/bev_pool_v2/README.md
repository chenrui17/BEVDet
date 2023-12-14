# bev_pool_grad_kernel optimization
Optimized the bev_pool_v2 backward kernel.

## install & run ut
```
pip install -v -e .
cd BEVDet/mmdet3d/ops && python bev_pool.py
```
## test result
end to end speed up is up to 1.28X
```
# before optimize 
=====start======
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
cost:  11.621224641799927
====end===

# after optimize
=====start======
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
loss: tensor(36908.4531, device='cuda:0', grad_fn=<SumBackward0>)
cost:  9.005592823028564
====end===

```
## profile timeline
the kernel speed up is up to 500X

before optimize
![Alt text](ae5ac08f8b9c8404b3f1955eb91045b.png)
after optimize
![Alt text](d987c417f42f9900d4ebc821633296f.png)




