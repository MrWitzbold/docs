page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.no_gradient


<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/tree/r2.0/tensorflow/python/framework/ops.py#L2493-L2525">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Specifies that ops of type `op_type` is not differentiable.

### Aliases:

* `tf.compat.v1.NoGradient`
* `tf.compat.v1.NotDifferentiable`
* `tf.compat.v1.no_gradient`
* `tf.compat.v2.no_gradient`


``` python
tf.no_gradient(op_type)
```



<!-- Placeholder for "Used in" -->

This function should *not* be used for operations that have a
well-defined gradient that is not yet implemented.

This function is only used when defining a new op type. It may be
used for ops such as <a href="../tf/size"><code>tf.size()</code></a> that are not differentiable.  For
example:

```python
tf.no_gradient("Size")
```

The gradient computed for 'op_type' will then propagate zeros.

For ops that have a well-defined gradient but are not yet implemented,
no declaration should be made, and an error *must* be thrown if
an attempt to request its gradient is made.

#### Args:


* <b>`op_type`</b>: The string type of an operation. This corresponds to the
  `OpDef.name` field for the proto that defines the operation.


#### Raises:


* <b>`TypeError`</b>: If `op_type` is not a string.