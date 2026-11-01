# Transformer Paper Notes

Notes on [*Attention Is All You Need*](https://arxiv.org/abs/1706.03762), Vaswani et al. (2017).

## Motivation

The Transformer replaces recurrence with attention, connecting distant positions and allowing more parallel computation during training.

## Scaled dot-product attention

```text
Attention(Q, K, V) = softmax(QKᵀ / √dₖ)V
```

| Symbol | Role |
| --- | --- |
| Q | Queries |
| K | Keys |
| V | Values |
| dₖ | Key dimension |

Scaled scores become softmax weights, which combine V.

## Multi-head attention

Separate learned projections compute attention in parallel. Their outputs are concatenated and projected. The base model uses eight heads; this is a configuration choice.

## Encoder and decoder

The original model has six encoder and six decoder layers, with feed-forward networks, residual connections, and layer normalization. Decoder self-attention masks future positions. During inference, generation proceeds one token at a time.

## Positional encoding

Sine and cosine functions at different frequencies encode positions. These vectors are added to token embeddings to provide order information.

## Takeaway

These are conceptual study notes, not an implementation or experimental reproduction.
