.. _agent-states:

Agent states
=============

The life cycle of agents, from they are registered until they are removed, goes through 4 fundamental states which the following image schematizes:

.. thumbnail:: ../../images/manual/managing-agents/agent-status.png
    :title: Agent life cycle
    :align: center
    :width: 100%


- **Never conected:** The agent has been registered but has not yet contacted the manager.
- **Pending:** The agent has initiated the authentication protocol and is not yet complete. The manager will have created an ``agent-info`` file where it will save information about the agent that initiated the connection. If the agent spends more time than required in this state, may not be receiving the ACK from the manager.
- **Active:** The agent has been properly authenticated and can now report to the manager. The file created in pending state will have been instantiated.
- **Disconnected:** The manager considers the agent disconnected. It can be reached in two ways:
    - If the connection is through ``UDP``, the manager will understand that the agent has disconnected when he does not receive anything from it in half an hour.
    - If the connection is through ``TCP``, the manager will understand that the agent is disconnected immediately after the agent stops giving life signals.
