# Psuedo code

### `__init__`
This method initializes the DQN model with the given parameters.

```pseudo
class Dqn:
    method __init__(input_size, nb_action, gamma):
        set input_size
        set nb_action
        set gamma
        initialize neural network with input_size and nb_action
        initialize optimizer for the neural network
        initialize replay memory
```

### `getQValue`

This method returns the Q-value for a given state and action.


```pseudo
method getQValue(state, action):
    convert state to tensor
    get Q-values from the neural network for the given state
    return Q-value for the given action
```

### `computeValueFromQValue`

This method computes the maximum Q-value for a given state.

```pseudo
method computeValueFromQValue(state):
    convert state to tensor
    get Q-values from the neural network for the given state
    return the maximum Q-value
```

### `getAction`

This method returns an action based on the epsilon-greedy policy.

```pseudo
method getAction(state):
    generate a random number
    if random number < epsilon:
        return a random action
    else:
        return the action with the highest Q-value for the given state
        
```

### `update`

This method updates the Q-values based on the experience replay.

```pseudo
method update(state, action, reward, next_state):
    get the maximum Q-value for the next state
    compute the target Q-value
    get the current Q-value for the given state and action
    compute the loss between the target Q-value and the current Q-value
    perform a gradient descent step to minimize the loss
```